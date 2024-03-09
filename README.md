# Ansible macOS Playbook

Ansible playbook to set up a fresh macOS installation. 

## Roles

- Installs Homebrew packages and apps (Role `homebrew`)
- Installs App Store apps with [`mas-cli`](https://github.com/mas-cli/mas) (Role `mas`)
- Modifies MacOS settings (Role `settings`)
- Changes the user shell, if configured (Role `shell`)

## Installation

1. Clone or fork this repository.

```shell
git clone https://github.com/ferrarafer/ansible-macos-setup.git
```

2. Create your personal config based on the default.

```shell
cp default.config.yml config.yml
```

3. Edit `config.yml` to your preferences.
4. Execute bootstrap shell script.

```shell
# Execute bootstrap shell script to
#   - install Command Line Tools
#   - install Homebrew
#   - install Ansible
#   - install Ansible requirements
#   - apply `main.yml` ansible playbook
sh bin/bootstrap
```

For future updates, `bin/apply` shell script can be used to run just the Ansible playbook without the setup commands.

## Keep fork repository in sync

If you forked this repository and want to include its latest changes without losing your own, add this repository as an upstream and rebase it onto your fork:

```shell
git remote add upstream git@github.com:ferrarafer/ansible-macos-setup.git
git fetch upstream
git rebase upstream/main
```
