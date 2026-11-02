Company: Northstar Solutions

Affected system: AWS EC2 Web Server

Issue: Website inaccessible from the internet.

Troubleshooting performed:
1. Confirmed website failed to load externally.
2. Connected to EC2 through AWS Session Manager.
3. Ran curl -I http://localhost.
4. Received HTTP/1.1 200 OK, confirming Apache was operational.
5. Inspected the EC2 security group's inbound rules and found no rules configured.
Root cause: Missing inbound HTTP/TCP port 80 security group rule.

Resolution: Restored the HTTP rule permitting 0.0.0.0/0 on TCP port 80.

Validation: Website successfully loaded from an external browser.