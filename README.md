
# Projeto em Ansible para instalação do Conjur Enterprise 13.4

Esse projeto é uma automação em Ansible para instalar o ambiente do Conjur Enterprise em Kubernetes.

## Ambiente utilizado

**Linux:** Ubuntu 24.10

**Conjur:** Enterprise 13.4.0

**Ansible:** 2.16.3

**K3s:** v1.31.6+k3s1

**Pacotes Inslados** (nem todos são necessários)**:**
- ansible (double-check)
- curl
- git
- docker.io
- openssl
- k3s
- unzip
## Configurando o projeto

### Estando com o Linux instalado (no meu cenário utilizei o Ubuntu 24.10), execute os seguintes comandos:
- Atualizar os pacotes do Linux e instalar o Ansible:
```bash
sudo apt update && sudo apt install ansible -y
```

- Criar o diretório de instalação, dar permissão para o usuário atual e ir para o diretório criado:
```bash
sudo mkdir -p /opt/conjur/install && sudo chown $USER:$USER /opt/conjur/install && cd /opt/conjur/install
```

- Baixar o projeto para o Linux:
```bash
sudo git clone https://github.com/adri-costa/ansible-conjur-kubernetes.git .
```

- Copiar os binários "conjur-appliance-Rls-v13.4.0.tar.gz" e "conjur-cli-go_8.0.16_amd64.deb" para o diretório:
```bash
/opt/conjur/install
```

- Executar o playbook para instalação e configuração do ambiente (será necessário inserir a senha do usuário após o comando):
```bash
ansible-playbook -i inventory.yml playbook.yml -K
```

## Documentação

[Ubuntu](https://ubuntu.com/blog/tag/ubuntu-24-10)

[Conjur Enterprise 13.4](https://docs.cyberark.com/conjur-enterprise/13.4/en/content/enterprise/releasenotes/release-notes-13.4.htm)

[Ansible](https://docs.ansible.com/)

[K3s](https://k3s.io/)
