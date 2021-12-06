# itops-mac-playbook

Ansible Playbook to Configure a Mac for an ITOps Engineer.

## Background

This project was heavily inluenced by Jeff Geerling's [mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook) Project. This playbook installs and configures most of the software used for ITOps development.

## Installation

1. Ensure Apple's command line tools are installed (`xcode-select --install` to launch the installer).
2. [Install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/index.html):

   1. Run the following command to add Python 3 to your $PATH: `export PATH="$HOME/Library/Python/3.8/bin:$PATH"`
   2. Upgrade Pip: `sudo python3 -m pip install --upgrade pip`
   3. Install Ansible: `python3 -m pip install ansible`

3. Clone or download this repository to your local drive.
4. Run `ansible-galaxy install -r requirements.yml` inside this directory to install required Ansible roles.
5. Run `ansible-playbook main.yml --ask-become-pass` inside this directory. Enter your macOS account password when prompted for the 'BECOME' password.

> Note: If some Homebrew commands fail, you might need to agree to Xcode's license or fix some other Brew issue. Run `brew doctor` to see if this is the case.

## Overriding Defaults

Not everyone's development environment and preferred software configuration is the same.

You can override any of the defaults configured in `default.config.yml`. For example, you can customize the installed packages and apps with something like:

```yaml
homebrew_installed_packages:
  - cowsay
  - git
  - go
homebrew_cask_apps:
  - authy
  - slack
  - pandora
  - sublime-text
```

## Included Applications / Configuration (Default)

Applications (installed with Homebrew Cask):

- [Firefox](https://www.mozilla.org/en-US/firefox/new/)
- [Google Chrome](https://www.google.com/chrome/)
- [Homebrew](http://brew.sh/)
- [iTerm2](https://iterm2.com/)
- [LastPass](https://www.lastpass.com/)
- [PowerShell](https://docs.microsoft.com/en-us/powershell/)
- [Slack](https://slack.com/)
- [Spotify](https://www.spotify.com/us/)
- [Visual Studio Code](https://code.visualstudio.com/)

Packages (installed with Homebrew):

- [git](https://git-scm.com/)
- [GitHub CLI](https://github.com/cli/cli)

## TODO

- [ ] Install VSCode Extensions
- [ ] Configure iTerm (oh-my-zsh, Powerlevel10k)
- [ ] Other configurations and dotfiles
