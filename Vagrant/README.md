# Vagrant

## Using snapshots

[Snapshot](https://www.vagrantup.com/docs/cli/snapshot.html) documentation contains all the details we need to know but here are the basics.

```shell
vagrant snapshot save [vm-name] NAME
```

```shell
vagrant snapshot restore [vm-name] NAME
```

```shell
vagrant snapshot list
```

```shell
vagrant snapshot delete [vm-name] NAME
```

## Triggers

[Vagrant Triggers](https://www.vagrantup.com/docs/triggers)

## Troubleshooting

> This is for MacOS, using Brew.

Revert to a previous version in case latest fails due ti lack of plugin support or it's incompatibility with VirtualBox:

```shell
brew cask install https://raw.githubusercontent.com/caskroom/homebrew-cask/<commit-hash>/Casks/vagrant.rb
```

In action. Reverting to `2.2.7`.

```shell
brew cask install https://raw.githubusercontent.com/caskroom/homebrew-cask/fb9df716e84923f4f2eeecba12367e9a84c8173c/Casks/vagrant.rb
```
