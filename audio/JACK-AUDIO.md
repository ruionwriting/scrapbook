# Jack Audio

> Random notes on Jack Audio

## Setup on OSX

Install:

```shell
brew install jack qjackctl
.
.
.

To have launchd start jack now and restart at login:
  brew services start jack
Or, if you don't want/need a background service you can just run:
  jackd -d coreaudio
```
