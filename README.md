# dst-ansible
DST Ansible playbooks

## Contents
*host_create.yml*
- Adds new host to DST inventory group: `otg_dst > [selected group]`

*host_setup.yml*
- Adds "ansible" user
- Copies anisble SSH key to authorized_keys file


*marklogic_install.yml*
- Creates "xstore" user
- Creates `/xstore` directory
- Installs MarkLogic RPMs on selected host(s)/group(s)
- Configures `/etc/marklogic.conf` setting
- Starts MarkLogic service
- Creates MarkLogic cluster using specified host as Master
- Joins remaining hosts to MarkLogic cluster

*marklogic_remove.yml*
- Stops MarkLogic service
- Removes MarkLogic
- Removes `/etc/marklogic.conf` file
- Removes "xstore" user
- Clears `/xstore` directory
- Reboots host

*run_puppet_agent.yml*
- Forces puppet run on selected host(s)
- Equivalent of `puppet agent -t` command

*satellite_register_host.yml*
- Registers host(s) to Satellite Capsule server using Activation Key

*satellite_unregister_host.yml*
- Unregisters host(s) from current Satellite server
- Cleans `subscription-manager` config
- Uninstalls `katello-ca-consumer` rpm