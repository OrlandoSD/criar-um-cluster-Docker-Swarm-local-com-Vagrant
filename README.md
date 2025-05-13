# README.md

# 🐳 Cluster Docker Swarm com Vagrant

Este projeto demonstra a criação de um cluster **Docker Swarm local** utilizando **Vagrant** e **máquinas virtuais Ubuntu**, com uma configuração automatizada para acelerar o setup de ambientes.

## 📦 Tecnologias Utilizadas

- Docker
- Docker Swarm
- Vagrant
- VirtualBox
- Shell Script

## 📁 Estrutura do Projeto

```
vagrant-swarm/
├── Vagrantfile
├── scripts/
│   └── install_docker.sh
└── README.md
```

## 🚀 Como Executar

### Pré-requisitos

- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- Git instalado

### Passos

1. Clona o repositório:
```bash
git clone https://github.com/seu-usuario/vagrant-swarm.git
cd vagrant-swarm
```

2. Sobe as máquinas virtuais:
```bash
vagrant up
```

3. Acede à máquina `master`:
```bash
vagrant ssh master
```

4. Inicializa o Docker Swarm:
```bash
docker swarm init --advertise-addr 192.168.56.10
```

5. Em cada worker (`node01`, `node02`, `node03`), executa:
```bash
vagrant ssh node01
# Cola aqui o comando docker swarm join fornecido pelo master
```

6. No `master`, confirma os nodes:
```bash
docker node ls
```

## 🧠 Dicas e Expansões

- Automatizar o join dos workers
- Adicionar serviços com `docker stack deploy`
- Monitorizar com Portainer

## 📌 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

