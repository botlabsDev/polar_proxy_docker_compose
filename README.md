# Polar Proxy Docker Compose

## tl;dr

```bash
$ git clone https://github.com/botlabsDev/polar_proxy_docker_compose.git
$ cd polar_proxy_docker_compose
$ docker-compose up --build -d
$ ls volumes/pcaps/

```

## Source 
Docker file: https://www.netresec.com/?page=Blog&month=2020-10&post=PolarProxy-in-Docker

## Troubleshooting & Known issues 
As mentioned here: https://github.com/juju4/ansible-polarproxy

* Use as explicit proxy
```
Oct 01 00:04:31 testhostname PolarProxy[49741]: [10443] n.n.n.n -> N/A System.IO.IOException : The handshake failed due to an unexpected packet format.
Oct 01 00:04:31 testhostname PolarProxy[49741]: [10443] n.n.n.n -> N/A Internal and/or external SSL session did not authenticate successfully
Oct 10 00:07:02 testcentral PolarProxy[49741]: [10443] n.n.n.n -> N/A System.IO.IOException : Authentication failed because the remote party has closed the transport stream.
Oct 10 00:07:02 testcentral PolarProxy[49741]: [10443] n.n.n.n -> N/A Internal and/or external SSL session did not authenticate successfully
```

PolarProxy works only as Transparent Proxy and requires firewall redirection. It can't be explicit through browser.