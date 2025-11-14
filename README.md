## The Featherweight Logger

A simple, secure, and lightweight solution for streaming application logs in real-time without needing SSH access.

This project provides a setup using Nginx, Dozzle, and Docker to create a password-protected web dashboard that streams logs from your applications. It's designed for minimal server resources and is perfect for giving developers read-only log access to staging or production environments securely.

### System Flow

The data flows from the developer's browser, through the secure Nginx gateway, to the Dozzle dashboard, which gets its log data from the streaming containers.

Got it. You want a much simpler `README.md` for the GitHub repository, focused only on what the logger is and a simple flow diagram.

I've updated the `README.md` file to be very concise and clear. It's now perfect for a quick overview.

```
[ You (Developer) ]
        |
        v
(Internet - Port 1010)
        |
        v
+-----------------------+
|  🛡️ Nginx (Gateway)   |
| (Password Protected)  |
+-----------------------+
        |
        v
+-----------------------+
| 💻 Dozzle (Dashboard) |
| (Internal Port 8888)  |
+-----------------------+
        |
        +------------------> [ 🟣 log-streamer-staging ] ---> Reads [ Staging .log Files ]
        |
        +------------------> [ 🟣 log-streamer-prod ]  ---> Reads [ Production .log Files ]
```
