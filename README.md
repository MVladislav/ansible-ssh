# SSH

[![Ansible Lint](https://github.com/MVladislav/ansible-ssh/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/MVladislav/ansible-ssh/actions/workflows/ansible-lint.yml)
[![Ansible Molecule Test](https://github.com/MVladislav/ansible-ssh/actions/workflows/ci.yml/badge.svg)](https://github.com/MVladislav/ansible-ssh/actions/workflows/ci.yml)

- [SSH](#ssh)
  - [Role Variables](#role-variables)
  - [Dependencies](#dependencies)
  - [Example Playbook](#example-playbook)
  - [License](#license)
  - [OTHER](#other)
    - [deprecation remove](#deprecation-remove)

---

You can checkout [MVladislav - ansible-env-setup - playbooks](https://github.com/MVladislav/ansible-env-setup/tree/main/playbooks) for how i use it in general.

Tested with:

- Ubuntu 23.04

## Role Variables

```yml
clients:
  - name: "{{ ansible_user }}"

ssh_only_client_setup: false
```

## Dependencies

Developed and testes with Ansible 2.14.4

## Example Playbook

```yml
- hosts: servers
  roles:
    - role: ansible-ssh
      clients:
        - name: "{{ ansible_user }}"
      ssh_only_client_setup: false
```

## License

MIT

## OTHER

### deprecation remove

```sh
sed -i '/KeyRegenerationInterval/d' /etc/ssh/sshd_config
sed -i '/ServerKeyBits/d' /etc/ssh/sshd_config
sed -i '/RSAAuthentication/d' /etc/ssh/sshd_config
sed -i '/RhostsRSAAuthentication/d' /etc/ssh/sshd_config
sed -i '/UsePrivilegeSeparation/d' /etc/ssh/sshd_config
```
