# Winsubplay

A basic
[playbook](http://docs.ansible.com/ansible/playbooks.html "Playbooks documentation.")
that performs some simple setups for a Ubuntu
*(particularly
[Windows Subsystem for Linux](https://msdn.microsoft.com/en-us/commandline/wsl/about "About Bash on Ubuntu on Windows")
, thus the repository name)*
system.

- Go to a preferred directory (e.g. workspace inside mounted Windows directory) with `cdhome`.
- Configure Vim colorscheme.
- **Git**: Configure `git` user email and name, set the editor to `vim`.
- **Node.js**: Install `nvm` and provision `~/.npmrc`
*(`--no-use` is used when loading `nvm` to reduce startup time, run `nvm use` before using `node` or `npm`)*.
- **AWS**: Install `pip`, install AWS CLI and provision `~/.aws/credentials`.

## Prerequisites

1. [Prepare SSH keys](https://help.ubuntu.com/community/SSH/OpenSSH/Keys "Ubuntu documentation on SSH.").

2. Install
[Ansible](http://docs.ansible.com/ansible/intro_installation.html "Ansible documentation on installation.") 2.3.

3. Install Git and clone this repository.

## How to Use

1. Copy `config.example/` into `config/` and update the files accordingly.

2. Run *(there will be a prompt for sudo password)*:
    ```
    ansible-playbook winsubplay.yml -i hosts --ask-become-pass
    ```

3. Restart shell or `source ~/.bashrc`.
