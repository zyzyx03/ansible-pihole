# pihole Ansible role.

Role installs and configures Pihole https://pi-hole.net/ with unattentded setup

Documents relating to pi-hole are at https://docs.pi-hole.net/

## Requirements
User with sudo access to the machine.

other [prerequisites](https://docs.pi-hole.net/main/prerequisites/)

### Required Variables
#### pihole_web_password:
You will need to generate a admin password for the `pihole_web_password:` variable, password is hashed with sha256 twice. You can generate a password with the following shell command.

With the password in a file (recommended).
```shell
echo -n $(cat ~/piholepass.word) | sha256sum | awk '{printf "%s", $1}' | sha256sum
```

With the password in shell command (not recommended)
```shell
echo -n notsosecretpassword | sha256sum | awk '{printf "%s", $1}' | sha256sum
```

recommended to store this variable in ansible vault.


## Role Variables
[defaults/main.yml](defaults/main.yml) for default values
