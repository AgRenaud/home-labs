# Home Labs

## Getting Started

### Requirements:
- Python3
- [multipass](https://multipass.run/)

### Start a Lab

First setup a python environment for `Ansible`.

```shell
python3 -m venv venv
source venv/bin/activate

pip install -r requirements.txt

# Then install ansible dependencies (Roles & collection)
ansible-galaxy role install -r requirements.yml
ansible-galaxy collection install -r requirements.yml
```

Then create your VM with a `k3s` cluster with `ansible-playbook -i local.yml playbook_vm.yml`. The playbook will fetch the default kubeconfig file for k3s. Get the IP of the VM with multipass `multipass info k3s-server` and replace kubeconfig's server IP with the one form multipass info.

> With `jq` we can get the IP easily with:
> ```shell
> multipass info k3s-server --format json | jq '.["info"]["k3s-server"]["ipv4"][0]'
> ```
