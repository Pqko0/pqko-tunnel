## Pqko-Tunnel
Pqko-Tunnel is a remote tunnel ssh tool! That acts as a port forwarding tool!

## Installation

```
npm i -g pqko-tunnel
```

## Note

If you wish the server port to show to go to ur sshd config file and enable "GatewayPorts"
You may also have to tinker with firewall settings on that machine or router!

## Setting Config

```
pqko-tunnel --set "server_ip:server_username:private_key_path"
```

Example

```
pqko-tunnel --set "10.0.0.51:ubuntu:C:/Users/pqko/Desktop/privatekey"
```

## Using the tool

No resposne should be given back! Unless an error or login prompt has been required!

```
pqko-tunnel server_port:local_port
```

Example

```
pqko-tunnel 8080:8080
```

## Code Usage

```
const main = require("pqko-tunnel")
const config = main.config("logonUsername", "server_ip", "private_key_path", server_public_port, 5050)

main.tunnel(config, () => console.log("pqko-tunnel is ready"))

require("express")().get("/", (req, res) => res.send("This is automated")).listen(5050, () => console.log("express is ready"))
```