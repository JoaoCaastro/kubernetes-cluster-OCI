# Iniciando um Cluster Kubernetes On OCI - Free Tier

# Instalação Docker

Atualizar repositórios

```bash
$ sudo apt-get update
$ sudo apt-get upgrade -y
```

Instalar Docker

```bash
$ sudo apt-get install docker.io -y
```

# Instalação kubectl

Baixar kubectl

```bash
$ curl -LO “https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/arm64/kubectl”
```

Download Cheksum

```bash
$ curl -LO “https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/arm64/kubectl.sha256”
```

Validar instalação kubectl

```bash
$ echo "$(cat kubectl.sha256) kubectl | sha256sum --check"
```

Retorno

```bash
$ kubectl: OK
```

Instalando kubectl, alterando permissões e adicionando aos binários

```bash
$ sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

# Instalação minikube

Baixar minikube

```bash
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-arm64
```

Instalar minikube e adicionar aos binários

```bash
$ sudo install minikube-linux-arm64 /usr/local/bin/minikube
```

Alterar permissões para execução do minikube

```bash
$ sudo chmod +x /usr/local/bin/minikube
```

Instalar conntractk

```bash
$ sudo apt-get install conntrack
```

Entrar como usuário root

```bash
$ sudo -i
```

Subir um Cluster com minikube

```bash
$ minikube start --vm-driver=none
```

Verificar Status do minikube

```bash
$ minikube status
```

Retorno do comando

```bash
minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured
```

Se o retorno não for esse, leia as linhas dos erros.