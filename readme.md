# V2fly
## Server
---
note that the config is set to circumvent sanctions and may not be appropriate for other uses. if your targets work with google auth service we are suggesting that run the app on a server located in America / Canada and use Socks5.<br><br>
![alt text](./google-403.png)
---

run in sequence :
````
git clone git@git.carriot.ir:areman/v2fly-proxy.git && cd v2fly-proxy
wget https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-release.sh
sudo bash install-release.sh
sudo systemctl enable v2ray
wget https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-dat-release.sh
sudo bash install-dat-release.sh
````

run ``v2ctl  uuid`` and replace command result in [server config](./server.json) in inbound.clients.id <br>
``sudo mv ./server.json /usr/local/etc/v2ray/config.json``
<br>if command run in root mode run ``mv ./server.json /etc/v2ray/config.json``

``sudo systemctl start v2ray``

## Client

``mkdir v2ray && cd v2ray``<br>
from https://github.com/v2fly/v2ray-core/releases/latest download and unzip your OS client compiled binary package <br>

copy [file](./client.json) in ``config.json`` and replace SERVER-ID and SERVER-IP

run `./v2ray --config=config.json`  <br>
http proxy on ``localhost:10809`` <br>
socks5 on `localhost:10808` <br>

<a href="https://computingforgeeks.com/how-to-set-system-wide-proxy-on-ubuntu-debian/" >How To Set System-Wide Proxy on Ubuntu 20.04/18.04 | Debian 10</a> <br>
<a href="https://www.jetbrains.com/help/idea/settings-http-proxy.html" >JetBrains Products Proxy Config</a><br>
<a href="https://chrome.google.com/webstore/detail/proxy-switchyomega/padekgcemlokbadohgkifijomclgjgif?hl=en" >switchy-omega chrome extension</a>


## Android

download V2rayNg from <a href="https://play.google.com/store/apps/details?id=com.v2ray.ang">google play</a>
import server Vmess link or from Menu ->  Type manually-Vmees
````
address : SERVER-IP
port : 1433
id : SERVER-ID
alterId : 233
security : none
Network : tcp
Header : http
host : www.bing.com
path : /
````


