---
Created: 2024-08-05T16:17:28+05:30
Updated: 2024-08-05T16:36:21+05:30
Maintainer: Ibrar Ansari
---
# HTTP Proxy Setup For Postman

hpts(http-proxy-to-socks) is a nodejs tool to convert SOCKS proxy into http proxy.

Many clients support setting up http proxy to speed up network requests and for sometimes only SOCKS proxy is available to you. SOCKS proxy supports TCP so that it's possible to convert those requests from http proxy into SOCKS protocol. In this way, you can still keep the goodness provided by your SOCKS proxy(e.g. encryption).

## Prerequisites
```
Nodejs => 4
```
## Setup

```
npm install -g http-proxy-to-socks
```

## Connect SSH Tunnel
```
ssh -N -D 1080 <tunnel-host>
```
The above command connect SSH host and open 1080 Dynamic Sock5 tunnel port.
## Usage

```
hpts -s 127.0.0.1:1080 -p 8080
```

This will start a process listening on `8080` as a http proxy. It will convert http requests into socks requests and send them to port `1080`. Please make sure your socks service is available at the corresponding port.

Other options:

```
Options:
  -V, --version          output the version number
  -s, --socks [socks]    specify your socks proxy host, default: 127.0.0.1:1080
  -p, --port [port]      specify the listening port of http proxy server, default: 8080
  -l, --host [host]      specify the listening host of http proxy server, default: 127.0.0.1
  -c, --config [config]  read configs from file in json format
  --level [level]        log level, vals: info, error
  -h, --help             output usage information
```

You can specify a `json` config file with `-c`:

```json
{
  "socks": "127.0.0.1:1080",
  "port": 8080
}
```


## Postman Configuration
Go to Postman -> Preferences -> Proxy

1. Check "Use System Proxy"
2. Check "Respect HTTP_PROXY, HTTPS_PROXY, and NO_PROXY environment variables"
3. Add a custom proxy configuration
   - **Proxy Type**: HTTP
   - **Proxy Server**: 127.0.0.1
   - **Port**: 8080


### 💼 Connect with me 👇👇 😊

- 🔥 [**Youtube**](https://www.youtube.com/@DevOpsinAction?sub_confirmation=1)
- ✍ [**Blog**](https://ibraransari.blogspot.com/)
- 💼 [**LinkedIn**](https://www.linkedin.com/in/ansariibrar/)
- 👨‍💻 [**Github**](https://github.com/meibraransari?tab=repositories)
- 💬 [**Telegram**](https://t.me/DevOpsinActionTelegram)
- 🐳 [**Docker**](https://hub.docker.com/u/ibraransaridocker)
