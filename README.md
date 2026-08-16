# Docker para iniciantes

#### containers-and-vms-together [Link ](https://www.docker.com/blog/containers-and-vms-together/)

![[Screenshot 2026-08-14 125922.png]]

# Como Instalar o Docker no Linux

A instalação recomendada do **Docker Engine** em distribuições baseadas em Debian/Ubuntu (como Ubuntu, Linux Mint e Pop!\_OS) é feita diretamente pelo repositório oficial da Docker. Siga o passo a passo no terminal:

sudo docker run -d -p 8080:80 --name meu-primeiro-site nginx

### Passo 1: Atualizar o sistema e instalar dependências

```bash
sudo apt update
sudo apt install -y ca-certificates curl gnupg
```

### Passo 2: Adicionar a chave GPG oficial do Docker

```bash
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL [https://download.docker.com/linux/ubuntu/gpg](https://download.docker.com/linux/ubuntu/gpg) -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

### Passo 3: Adicionar o repositório do Docker ao sistema

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] [https://download.docker.com/linux/ubuntu](https://download.docker.com/linux/ubuntu) $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Passo 4: Instalar os pacotes do Docker

```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Passo 5: Configurar permissões (Recomendado)

Para rodar comandos do Docker sem precisar digitar `sudo` a todo momento, adicione seu usuário ao grupo do Docker:

```bash
sudo usermod -aG docker $USER
newgrp docker
```

### Passo 6: Verificar a instalação

Para confirmar que tudo foi instalado e está funcionando perfeitamente, execute:

```bash
docker run hello-world
```

Se a mensagem **"Hello from Docker!"** aparecer, o Docker está totalmente configurado e pronto para o uso nos seus projetos e estudos.
