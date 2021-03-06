# Architecture
## Overview
### Basic setup with default settings
```
 Client
   |
TCP 443
   |   +---------------------+            +---------------------------+
   +-> | Reverse proxy       |            | Homeserver                |
       |                     | TCP 8008   |                           |
       |  /_matrix/* -------------------> | - 3PID invite from client |
       |                     |            |   |                       |
       |  /_matrix/identity/ |            |   |                       |
       +--|------------------+            +---|-----------------------+
          |                                   |
          +<---------------------------------<+
          |
          |   +-------------------+
 TCP 8090 +-> | mxisd             |
              |                   |
              | - Profile's 3PIDs |
              | - 3PID Invites    |
              +-|-----------------+
                |
             TCP 443
                |  +------------------------+
                |  | Remote Federated       |
                |  | mxisd servers          |
                |  |                        |
                +--> - 3PID Invites         |
                   +------------------------+
```
### With Authentication
See the [dedicated document](features/authentication.md).

### With Directory
See the [dedicated document](features/directory.md).

### With Federation
See the [dedicated document](features/federation.md).
