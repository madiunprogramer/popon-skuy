# Popon-skuy Enjoy Woles

...


Requirements
------------

**Linux**

    git
    golang
    redsocks

**Windows**

    golang
    proxifier

**Android (Termux)**

    git
    golang


Install
-------

**Popon-Skuy**

    $ go get -v -u -d github.com/madiunprogramer/popon-skuy
    $ cd ~/go/src/github.com/madiunprogramer/popon-skuy
    $ go build -ldflags "-s -w"

**Psiphon Tunnel Core**

    $ go get -v -u -d github.com/Psiphon-Labs/psiphon-tunnel-core/ConsoleClient
    $ cd ~/go/src/github.com/Psiphon-Labs/psiphon-tunnel-core/ConsoleClient
    $ go build -ldflags "-s -w" -o ~/go/src/github.com/madiunprogramer/popon-skuy/psiphon-tunnel-core


Usage
-----

**Linux**

    $ cd ~/go/src/github.com/madiunprogramer/popon-skuy
    $ sudo --preserve-env -s
    # ./popon-skuy


**Android (Termux)**

    $ cd ~/go/src/github.com/madiunprogramer/popon-skuy
    $ ./popon-skuy

<!-- -->

    Use ProxyDroid (root), Tun2Tap, or SocksDroid to redirect all connection to this Tunnel (Socks 5 Port 5070)
    Exclude Termux!


Configurations
--------------

Run `./popon-skuy` first to export all default settings.
Config will generated to `config.json` where `popon-skuy` binary file are executed.


### Pro Version

    ...
    "PsiphonCore": 1,
    "Psiphon": {
        "CoreName": "psiphon-tunnel-core",
        "Tunnel": 4,
        "Region": "",
        "Protocols": [
            "FRONTED-MEEK-HTTP-OSSH",
            "FRONTED-MEEK-OSSH"
        ],
        "TunnelWorkers": 8,
        "KuotaDataLimit": 0,
        "Authorizations": [
            "blablabla"
        ]
    }
    ...


### Rules

**XL Iflix or Axis Gaming (Default)**

    ...
    "Rules": {
        "akamai.net:80": [
            "video.iflix.com",
            "videocdn-2.iflix.com",
            "iflix-videocdn-p1.akamaized.net",
            "iflix-videocdn-p2.akamaized.net",
            "iflix-videocdn-p3.akamaized.net",
            "iflix-videocdn-p6.akamaized.net",
            "iflix-videocdn-p7.akamaized.net",
            "iflix-videocdn-p8.akamaized.net"
        ]
    },
    ...

**Direct**

    ...
    "Rules": {
        "*:*": [
            "*"
        ]
    },
    ...

or

    ./popon-skuy -f "*" -w "*:*"

**Telkomsel 0P0K**

    ...
    "Rules": {
        "akamai.net:443": [
            "118.97.159.51:443",
            "118.98.95.106:443"
        ]
    },
    ...

or

    ./popon-skuy -f 118.97.159.51:443,118.98.95.106:443 -w akamai.net:443

**Pubg Mobile (XL King)**

    ...
    "Rules": {
        "akamai.net:80": [
            "www.pubgmobile.com"
        ]
    },
    ...

**Joox (XL King)**

    ...
    "Rules": {
        "akamai.net:80": [
            "ak-quic.stream.music.joox.com.edgesuite.net",
            "ak-hk.stream.music.joox.com.edgesuite.net",
            "ak-ng.stream.music.joox.com.edgesuite.net",
            "ak-quic.app.joox.com.edgesuite.net",
            "ak-ng.app.joox.com.edgesuite.net",
            "e5121.b.akamaiedge.net"
        ]
    },
    ...

**Ruang Guru and Udemmy (XL or Axis)**

    ...
    "Rules": {
        "fastly.net:443": [
            "c.shared.global.fastly.net:443",
            "rg-video.ruangguru.com:443"
        ]
    },
    ...

or

    ./popon-skuy -f c.shared.global.fastly.net:443,rg-video.ruangguru.com:443 -w fastly.net:443


