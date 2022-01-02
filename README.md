# Hobo.Ansible.AwsCli
Ansible role to install the Amazon AWS CLI v2 on linux platforms

## Install Role
### Ansible Galaxy
[Ansible Galaxy](https://galaxy.ansible.com/docs/using/installing.html) can be used to install the role:
`ansible-galaxy install git+https://github.com/hobointhecorner/Hobo.Ansible.AwsCli.git[,<branch or commit hash>]`

### Git submodule
From inside your playbook roles directory:
`git submodule add [-b <branch or tag>] https://github.com/hobointhecorner/Hobo.Ansible.AwsCli.git`

## Variables
| Name            | Type   | Required | Default | Desctiption |
|-----------------|--------|----------|---------|-------------|
| awscli_temp_dir | string | No       | /tmp    | Temporary working directory for the playbook |
