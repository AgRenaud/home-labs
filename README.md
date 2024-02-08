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
```

Then to start a lab just run `ansible-playbook` on the desired lab config.

For example: `ansible-playbook k3s/main-playbook.yml`

