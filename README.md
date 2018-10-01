# provision-macos

> Automatically provision a local machine running [macOS Sierra 10.12][macos-sierra] and higher with [Ansible][ansible].

## Requirements

- Mac OSX 10.12 or higher

## Usage

Clone or download this repository to a local machine, and execute the included bash script by running the following command(s):

```bash
cd /path/to/this/directory
./bin/provision
```

This script will do the following:

- Install [XCode CLI tools][xcode-cli-tools]
- Install [homebrew][homebrew] via ruby/curl ([more info][homebrew])
- Install [Python][python] via homebrew ([more info][python-via-homebrew])
- Install [Ansible][ansible] via pip ([more info][ansible-via-pip])
- Run the Ansible playbook included in this repository.

## Testing

Perform a “dry run” of this Ansible playbook by running the following command(s):

```bash
cd /path/to/directory
./bin/dry-run
```

## Credits

> *“If I have seen further it is by standing on ye sholders of Giants.”*
> &mdash; [Issac Newton][issac-newton-quote]

provision-macos is a project by [@cbracco][cbracco] and its [contributors][contributors]. It is influenced by the following organizations, projects, articles, and individuals:

- [ansible-role-dotfiles][ansible-role-dotfiles] by [@geerlingguy][geerlingguy]
- [dotfiles][dotfiles-mathiasbynens] by [@mathiasbynens][mathiasbynens]
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
[mac-ansible]: https://github.com/adamchainz/mac-ansible
[mdp-ricbra]: https://github.com/ricbra/mac-dev-playbook
[mdp-geerlingguy]: https://github.com/geerlingguy/mac-dev-playbook
[macos-sierra]: https://en.wikipedia.org/wiki/MacOS_Sierra
[python]: https://www.python.org
[python-via-homebrew]: https://github.com/Homebrew/brew/blob/master/docs/Homebrew-and-Python.md
[ricbra]: https://github.com/ricbra
[roderik]: https://github.com/roderik
[superlumic]: https://github.com/superlumic/superlumic
[xcode-cli-tools]: https://developer.apple.com/xcode/features
