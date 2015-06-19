Running
-------
Gull this repository down and run

    vagrant up

Choosing playbooks
------------------
Under `ansible-playbook/ansible/playbook.yml` comment/uncomment the playbooks you wish to use.

Modifying playbooks
-------------------
To change which packages are installed or set usernames and passwords for databases change the values in  `ansible-playbook/ansible/vars`

git submodule
-------------
If you would like to use this as a [submodule](http://git-scm.com/docs/git-submodule), add this repository as a submodule

    git submodule add https://github.com/404mike/ansible-playbook.git

Then you can get both repositories with
`git clone -b <branch_name> --recursive <remote> <directory>`

If you want to change the default values for your project, copy the `Vagrant` file and the `playbook.yml` file and create your own `vars` directory and change the values and links in those files as needed.