# provision-macos

[![Build Status](https://travis-ci.org/cbracco/provision-macos.svg?branch=master)][travis-ci-repo]

> Automatically provision a local machine running [macOS High Sierra 10.13][macos-high-sierra] or higher with [Ansible][ansible].

## Requirements

- macOS High Sierra 10.13 or higher

## Usage

Clone or download this repository to a local machine.

```bash
git clone https://github.com/cbracco/provision-macos.git
```

Execute the included bash script by running the following command(s):

```bash
cd /path/to/this/repository
sudo ./bin/provision
```

This bash script does the following:

- Installs [XCode CLI tools][xcode-cli-tools]
- Installs [homebrew][homebrew] via ruby/curl ([more info][homebrew])
- Installs [Python][python] via homebrew ([more info][python-via-homebrew])
- Installs and upgrade [pip][pip]
- Installs [Ansible][ansible] via pip ([more info][ansible-via-pip])
- Runs the Ansible playbook included in this repository

## Testing

This repository is continuously tested by [Travis-CI][travis-ci-repo].

You can perform a “dry run” of the included Ansible playbook by running the following command(s):

```bash
cd /path/to/directory
ansible-playbook playbook.yml --check
```

## Credits

> *“If I have seen further it is by standing on ye sholders of Giants.”*
> &mdash; [Issac Newton][issac-newton-quote]

provision-macos is a project by [@cbracco][cbracco] and its [contributors][contributors]. It is influenced by the following organizations, projects, articles, and individuals:

- [ansible-role-dotfiles][ansible-role-dotfiles] by [@geerlingguy][geerlingguy]
- [dotfiles][dotfiles-mathiasbynens] by [@mathiasbynens][mathiasbynens]
- [osxstrap][osxstrap] by [@jeremyltn][jeremyltn]
- [mac-ansible][mac-ansible] by [@adamchainz][adamchainz]
- [mac-dev-playbook][mdp-geerlingguy] by [@geerlingguy][geerlingguy]
- [mac-dev-playbook][mdp-ricbra] by [@ricbra][ricbra]
- [superlumic][superlumic] by [@roderik][roderik]

## [Changelog](CHANGELOG.md)

## [License](LICENSE)

[adamchainz]: https://github.com/adamchainz
[ansible]: https://www.ansible.com
[ansible-role-dotfiles]: https://github.com/geerlingguy/ansible-role-dotfiles
[ansible-via-pip]: https://serverfault.com/a/562350
[cbracco]: https://chrisbracco.com
[contributors]: https://github.com/cbracco/provision-localhost/graphs/contributors
[dotfiles-mathiasbynens]: https://github.com/mathiasbynens/dotfiles
[issac-newton-quote]: https://en.wikipedia.org/wiki/Standing_on_the_shoulders_of_giants
[geerlingguy]: https://github.com/geerlingguy
[homebrew]: http://brew.sh
[jeremyltn]: https://github.com/jeremyltn
[mac-ansible]: https://github.com/adamchainz/mac-ansible
[mathiasbynens]: https://github.com/mathiasbynens
[mdp-ricbra]: https://github.com/ricbra/mac-dev-playbook
[mdp-geerlingguy]: https://github.com/geerlingguy/mac-dev-playbook
[macos-high-sierra]: https://en.wikipedia.org/wiki/MacOS_High_Sierra
[osxstrap]: https://github.com/osxstrap
[pip]: https://pypi.org/project/pip/
[python]: https://www.python.org
[python-via-homebrew]: https://github.com/Homebrew/brew/blob/master/docs/Homebrew-and-Python.md
[ricbra]: https://github.com/ricbra
[roderik]: https://github.com/roderik
[superlumic]: https://github.com/superlumic/superlumic
[travis-ci-repo]: https://travis-ci.org/cbracco/provision-macos
[xcode-cli-tools]: https://developer.apple.com/xcode/features
