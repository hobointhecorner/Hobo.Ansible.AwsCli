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
| Name            | Type      | Required | Default | Desctiption |
|-----------------|-----------|----------|---------|-------------|
| awscli_temp_dir | string    | No       | /tmp    | Temporary working directory for the playbook |
| awscli_profiles | list(map) | No       |         | List of awscli configuration profiles with `name` and `region` required at minimum. [More info](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html) |

## Example
```yaml
---
- hosts: all
  roles:
    - role: Hobo.Ansible.AwsCli
      awscli_profiles:
        # Default profile using access key/secret
        - name: default
          region: us-east-2
          output: json
          aws_access_key_id: super
          aws_secret_access_key: secret
        # Secondary profile using SSO
        - name: prod
          region: us-east-2
          sso_start_url: https://my-sso-portal.awsapps.com/start
          sso_region: us-east-2
          sso_account_id: 123456789011
          sso_role_name: prod-ops
```
