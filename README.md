# Ansible Bitwarden Role
This roles setups up a [bitwarden](https://bitwarden.com/) server.

## Requirements
### ansible-galaxy
__Collections:__
  - community.general

__Roles:__
  - [daemonslayer2048.common](https://github.com/Daemonslayer2048/common_role)

## Variables
| Variable | Type | Required | Default | Example |
|    -     |   -  |     -    |    -    |    -    |
| [hostname](#hostname) | string | True | N/A | warden |
| [host_public_domain](#host_public_domain) | string | True | null.com | null.com |
| [bitwarden_user](#bitwarden_user) | string | True | warden | warden |
| [bitwarden_user_home](#bitwarden_user_home) | string | True | /srv/warden | /srv/warden |

### Variable Summaries:
#### hostname
This is used in multiple locations to set the FQDN of the server and to be used in setting the public URL for the server when the [Caddy reverse proxy role](https://github.com/Daemonslayer2048/caddy_role) is deployed.

#### host_public_domain
Completes the domain portion of the public URL with the help of the variable above.

#### bitwarden_user  
The name of the user bitwarden will run as on the host

#### bitwarden_user_home  
The home of the bitwarden service user


# Notes:
## Testing Issues
  - Selinux Modules can not be tested in podman so these tests are performed outside of the stesting suite :(
## Inability to finish role install
 Running the bitwarden install script in ansible appears to run into an infinite hang time issue. This needs to be looked into further but as of now the install script needs to be ran manually.
## Future variables
  - Unused variables now:
    - bitwarden_use_ssl
    - bitwarden_generate_ssl
    - bitwarden_database_name
    - bitwarden_instalation_id
    - bitwarden_instalation_key
