# Deploying

This assumes that your inventory consists of hosts named `boxes` to which all these playbooks apply. Modify to taste.

## init.yml

* If you don't have `group_vars`, set up `group_vars/common/vars` with a `user_name`, crypted `user_password` and `user_ssh_pubkey`
* ansible-playbook -i `ansible_source_dir/contrib/inventory/linode.py` --ask-pass init.yml
  * You will likely need to do a manual SSH first so `--ask-pass` doesn't complain about the host not being in `known_hosts`
* Will be run as root
* Sets up a new user
* Sets up sshd config to not allow root access
