# provision-macos

![Build Status](https://github.com/cbracco/provision-macos/actions/workflows/provision.yml/badge.svg)

> Automatically provision a local machine running [macOS High Sierra 10.13][macos-high-sierra] or higher with [Ansible][ansible].

## Requirements

- macOS Monterey 12.4 or higher

## Usage

Clone or download this repository to a local machine:

```shell
git clone https://github.com/cbracco/provision-macos.git
```

Create the [Ansible Vault][ansible-vault] passphrase file in the proper location and make sure it contains the correct Ansible Vault passphrase:

```shell
mkdir ~/.ansible
touch ~/.ansible/vault_password
echo '[REPLACE WITH ANSIBLE VAULT PASSPHRASE]' > ~/.ansible/vault_password
```

**NOTE:** _The [ssh role][ssh-role] copies a private SSH key file that has been previously encrypted using [Ansible Vault][ansible-vault]. The command above must be run before the provision script in order for Ansible to complete this particular task successfully. An annoying but necessary evil until a better solution comes along._

Finally, execute the included shell script by running the following command(s):

```shell
cd /path/to/this/repository
./bin/provision
```

It does the following:

- Installs [XCode CLI tools][xcode-cli-tools]
- Installs [homebrew][homebrew] via ruby/curl ([more info][homebrew])
- Installs [Python][python] via homebrew ([more info][python-via-homebrew])
- Installs and upgrades [pip][pip]
- Installs [Ansible][ansible] via pip ([more info][ansible-via-pip])
- Runs the Ansible playbook included in this repository

## Testing

This project is continuously tested by [Travis-CI][travis-ci-repo], which runs a “test” version of the included provision script. It is triggered by passing the `-t` flag:

```shell
./bin/provision -t
```

This runs a syntax check on the included Ansible playbook, and a slightly modified “test” version of the included Ansible playbook which installs only the packages necessary in order for tests to pass (this speeds up test builds a bit).

### Syntax Check

In addition, you can check the syntax of the included Ansible playbook by running the following command(s):

```shell
cd /path/to/directory
ansible-playbook playbook.yml --syntax-check
```

### Check Mode

You can also perform a “dry run” of the included Ansible playbook by running the following command(s):

```shell
cd /path/to/directory
ansible-playbook playbook.yml --check
```

Learn more about [“Check Mode” in Ansible][ansible-check-mode].

### Check Mode w/ Tags

You can also perform a “dry run” of specific roles in the included Ansible playbook by running the following command(s):

```shell
cd /path/to/directory
ansible-playbook playbook.yml --check --tags=homebrew,pip
```

This can be useful when working on tasks in a particular role and you only want to check those tasks. Learn more about [Tags in Ansible][ansible-tags].

### Exclude a task from “Test Mode”

If you are writing a new task that you do not want to run in “test mode”, you can exclude it using `when` so the task will only run if `test_mode` variable is defined:

```yml
- name: task that should not run during tests
  shell: echo 'do not run me during tests'
  when: not test_mode
```

This is a technique borrowed from [Jeff Geerling][geerlingguy-testmode]. Thanks Jeff!

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
[ansible-check-mode]: https://docs.ansible.com/ansible/2.5/user_guide/playbooks_checkmode.html
[ansible-role-dotfiles]: https://github.com/geerlingguy/ansible-role-dotfiles
[ansible-tags]: https://docs.ansible.com/ansible/devel/user_guide/playbooks_tags.html
[ansible-vault]: https://docs.ansible.com/ansible/2.4/vault.html
[ansible-via-pip]: https://serverfault.com/a/562350
[cbracco]: https://chrisbracco.com
[contributors]: https://github.com/cbracco/provision-localhost/graphs/contributors
[dotfiles-mathiasbynens]: https://github.com/mathiasbynens/dotfiles
[issac-newton-quote]: https://en.wikipedia.org/wiki/Standing_on_the_shoulders_of_giants
[geerlingguy]: https://github.com/geerlingguy
[geerlingguy-testmode]: https://www.jeffgeerling.com/blog/2017/ci-ansible-playbooks-which-require-ansible-vault-protected-variables
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
[ssh-role]: ./roles/ssh
[superlumic]: https://github.com/superlumic/superlumic
[travis-ci-repo]: https://travis-ci.org/cbracco/provision-macos
[xcode-cli-tools]: https://developer.apple.com/xcode/features
