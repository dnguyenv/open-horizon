# `base-alpine` - Base container for Alpine

This container may be run locally using Docker, pushed to a Docker registry, and published to any [_Open Horizon_][open-horizon] exchange.

## Status

![Supports amd64 Architecture][amd64-shield]
[![](https://images.microbadger.com/badges/image/dcmartin/amd64_base-alpine.svg)](https://microbadger.com/images/dcmartin/amd64_base-alpine "Get your own image badge on microbadger.com")
[![](https://images.microbadger.com/badges/version/dcmartin/amd64_base-alpine.svg)](https://microbadger.com/images/dcmartin/amd64_base-alpine "Get your own version badge on microbadger.com")
[![Docker Pulls][pulls-amd64]][docker-amd64]

[docker-amd64]: https://hub.docker.com/r/dcmartin/amd64_base-alpine
[pulls-amd64]: https://img.shields.io/docker/pulls/dcmartin/amd64_base-alpine.svg

![Supports armhf Architecture][arm-shield]
[![](https://images.microbadger.com/badges/image/dcmartin/arm_base-alpine.svg)](https://microbadger.com/images/dcmartin/arm_base-alpine "Get your own image badge on microbadger.com")
[![](https://images.microbadger.com/badges/version/dcmartin/arm_base-alpine.svg)](https://microbadger.com/images/dcmartin/arm_base-alpine "Get your own version badge on microbadger.com")
[![Docker Pulls][pulls-arm]][docker-arm]

[docker-arm]: https://hub.docker.com/r/dcmartin/arm_base-alpine
[pulls-arm]: https://img.shields.io/docker/pulls/dcmartin/arm_base-alpine.svg

![Supports aarch64 Architecture][arm64-shield]
[![](https://images.microbadger.com/badges/image/dcmartin/arm64_base-alpine.svg)](https://microbadger.com/images/dcmartin/arm64_base-alpine "Get your own image badge on microbadger.com")
[![](https://images.microbadger.com/badges/version/dcmartin/arm64_base-alpine.svg)](https://microbadger.com/images/dcmartin/arm64_base-alpine "Get your own version badge on microbadger.com")
[![Docker Pulls][pulls-arm64]][docker-arm64]

[docker-arm64]: https://hub.docker.com/r/dcmartin/arm64_base-alpine
[pulls-arm64]: https://img.shields.io/docker/pulls/dcmartin/arm64_base-alpine.svg

[arm64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[arm-shield]: https://img.shields.io/badge/armhf-yes-green.svg

## Service discovery
+ `org` - `dcmartin@us.ibm.com`
+ `url` - `com.github.dcmartin.open-horizon.base-alpine`
+ `version` - `0.0.1`

#### Optional variables
+ `LOG_LEVEL` - specify level of logging; default `info`; options include (`debug` and `none`)
+ `DEBUG` - force debug settings; boolean; default `false`

## How To Use

Specify `dcmartin/base-alpine:latest` in service `build.json`

### Building this continer

Copy this [repository][repository], change to the `base` directory, then use the **make** command; see below:

```
% mkdir ~/gitdir
% cd ~/gitdir
% git clone http://github.com/dcmartin/open-horizon
% cd open-horizon/base
% make
...
{
  "hzn": {
    "agreementid": "",
    "arch": "",
    "cpus": 0,
    "device_id": "",
    "exchange_url": "",
    "host_ips": [
      ""
    ],
    "organization": "",
    "pattern": "",
    "ram": 0
  },
  "date": 1549909627,
  "service": "base",
  "hostname": "fe855a6844c0-172017000003",
  "pid": 0,
  "base": null
}
```

## Changelog & Releases

Releases are based on Semantic Versioning, and use the format
of ``MAJOR.MINOR.PATCH``. In a nutshell, the version will be incremented
based on the following:

- ``MAJOR``: Incompatible or major changes.
- ``MINOR``: Backwards-compatible new features and enhancements.
- ``PATCH``: Backwards-compatible bugfixes and package updates.

## Authors & contributors

[David C Martin][dcmartin] (github@dcmartin.com)

[userinput]: https://github.com/dcmartin/open-horizon/blob/master/base/userinput.json
[service-json]: https://github.com/dcmartin/open-horizon/blob/master/base/service.json
[build-json]: https://github.com/dcmartin/open-horizon/blob/master/base/build.json
[dockerfile]: https://github.com/dcmartin/open-horizon/blob/master/base/Dockerfile


[dcmartin]: https://github.com/dcmartin
[edge-fabric]: https://console.test.cloud.ibm.com/docs/services/edge-fabric/getting-started.html
[edge-install]: https://console.test.cloud.ibm.com/docs/services/edge-fabric/adding-devices.html
[edge-slack]: https://ibm-appsci.slack.com/messages/edge-fabric-users/
[ibm-apikeys]: https://console.bluemix.net/iam/#/apikeys
[ibm-registration]: https://console.bluemix.net/registration/
[issue]: https://github.com/dcmartin/open-horizon/issues
[macos-install]: http://pkg.bluehorizon.network/macos
[open-horizon]: http://github.com/open-horizon/
[repository]: https://github.com/dcmartin/open-horizon
[setup]: https://github.com/dcmartin/open-horizon/blob/master/setup/README.md
