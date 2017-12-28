# awx-example

```console
$ vagrant up
```

You can access to `localhost:10080` and login to AWX with `admin/password`.

Also, you can run the playbook against the VM manually.

```console
$ ansible-playbook --private-key=~/.vagrant.d/insecure_private_key -u vagrant -i .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory awx.yml
```

If it's successful, let's launch the job created automatically by Ansible, "Install Nginx".

Finally you can access to `localhost:10081` and see the default page of Nginx.
