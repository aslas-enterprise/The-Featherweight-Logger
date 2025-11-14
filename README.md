## The Featherweight Logger

A simple, secure, and lightweight solution for streaming application logs in real-time without needing SSH access.

This project provides a setup using Nginx, Dozzle, and Docker to create a password-protected web dashboard that streams logs from your applications. It's designed for minimal server resources and is perfect for giving developers read-only log access to staging or production environments securely.


## Setup

Please visit here: `https://aslas-enterprise.github.io/The-Featherweight-Logger`

## System Flow

The data flows from the developer's browser, through the secure Nginx gateway, to the Dozzle dashboard, which gets its log data from the streaming containers.

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
