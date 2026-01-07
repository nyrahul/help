# IBM QRadar Integration

## Integration Architecture

The integration flow enables alert forwarding from AccuKnox to IBM QRadar. Alerts generated in the AccuKnox UI, sourced from findings and various alert sources, are processed by a rules engine and triggers according to the configured settings. These alerts are then transported via a webhook server set up in the customer environment, using the Syslog protocol to forward them to IBM QRadar, which serves as the final destination for receiving the alerts.

![Integration Architecture](./images/ibm-qradar/arch-qradar.png)

### Architecture Components

1. AccuKnox platform (source)
2. Webhook server (intermediary)
3. Syslog protocol (transport)
4. IBM QRadar (destination)

### Customer Integration Process

- Configure webhook in AccuKnox (See [**Webhook Integration Guide**](https://help.accuknox.com/integrations/webhook-integration/)).
- Set up QRadar configuration (customer responsibility).
- Report configuration completion back to AccuKnox.

---

## Connector and Send Event

1. Log in to QRadar as `Admin`.

    ![QRadar Admin Login](./images/ibm-qradar/1.png)

2. Click `Admin` and then `Data Source`.

    ![QRadar Data Source](./images/ibm-qradar/2.png)

3. Click `Log Source`.

    ![QRadar Log Source](./images/ibm-qradar/3.png)

4. Click `+ New Source Log` -> `Single Source`.

    ![New Source Log](./images/ibm-qradar/4.png)

    ![Single Source Selection](./images/ibm-qradar/5.png)

5. Configurations:
    1. Select Log Source Type - `Universal DSM`
    2. Select a Protocol - `Syslog`
    3. Name - `Ayush Test Qradar`
    4. Log Source Identifier - `192.168.1.226` (Source IP from which Log is forwarded to Qradar)

    ![Configuration Details](./images/ibm-qradar/6.png)

6. Go back to `Admin` again to deploy changes. Click `Deploy Changes`, wait for changes to be deployed.

    ![Deploy Changes 1](./images/ibm-qradar/7.png)

    ![Deploy Changes 2](./images/ibm-qradar/8.png)

7. Now go to `Log Activity` to see All Alerts.

8. Now trigger the Event. You will be alerted in real-time in the Qradar UI.
    1. Test Event

        ![Test Event](./images/ibm-qradar/9.png)

    2. Event in Qradar UI

        ![Event UI 1](./images/ibm-qradar/10.png)

        ![Event UI 2](./images/ibm-qradar/11.png)

        ![Event UI 3](./images/ibm-qradar/12.png)

## Check QRadar IP

1. Go to Admin.
2. Click System Configuration.
3. Click `System and License Management`.

    ![System Configuration](./images/ibm-qradar/13.png)

    ![System License Management](./images/ibm-qradar/14.png)

## Sample Script to Test

1. Python Script UDP used for Testing:

    ```python
    from flask import Flask, request
    import json
    import subprocess

    QRADAR_IP = "192.168.1.219" # change to QRadar IP if remote
    QRADAR_PORT = 514

    app = Flask(__name__)

    def send_to_qradar_syslog(message):
        # Normalize to bytes
        if isinstance(message, str):
            data = message.encode("utf-8")
        else:
            data = message # assume already bytes
        try:
            print(f"About to send via nc to {QRADAR_IP}:{QRADAR_PORT}: {message}")
            # This is equivalent to: echo "<134>..." | nc -u -w1 127.0.0.1 514
            proc = subprocess.run(
                ["nc", "-u", "-w1", QRADAR_IP, str(QRADAR_PORT)],
                input=data,
                capture_output=True,
            )
            print("nc return code:", proc.returncode)
            if proc.stdout:
                print("nc stdout:", proc.stdout.decode().strip())
            if proc.stderr:
                print("nc stderr:", proc.stderr.decode().strip())
        except Exception as e:
            print("ERROR sending to QRadar via nc:", e)

    @app.route("/webhook", methods=["POST"])
    def webhook():
        data = request.get_json(force=True, silent=True) or {}
        payload = json.dumps(data)
        syslog_msg = f"{payload}"
        print("Received webhook:", data)
        print("Sending to QRadar:", syslog_msg)
        send_to_qradar_syslog(syslog_msg)
        return "OK", 200

    if __name__ == "__main__":
        # make sure this matches your curl (8081)
        app.run(host="0.0.0.0", port=8081)
    ```

2. Sample Event used for Testing:

    ```bash
    curl --location 'http://localhost:8081/webhook' --header 'Content-Type: application/json' --data-raw '{
        "Suppressed": false,
        "Timestamp": 1764823838,
        "_id": "6931131f862d9214643ed740",
        "action": "findings-status-updated",
        "component": "Vulnerability Management",
        "message": "Findings Status Updated",
        "payload": {
            "data_type": "cloudsploit",
            "id": "20eeb501-ddd7-4112-b3e0-8c269c76cfe1",
            "name": "Ledger Has Tags: us-east-1",
            "new_status": "Active",
            "previous_status": "Active"
        },
        "result": "Ok",
        "tenant_id": "33",
        "timestamp": "2025-12-04 04:50:38.967183+00:00",
        "type": "action",
        "user": "ayush@accuknox.com"
    }'
    ```
