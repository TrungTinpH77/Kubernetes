# Kubernetes
**#Ubuntu 22.04**

Install-Learning

   62  echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
   
   63  sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
   
   64  kubectl version --client
   
   65  minikube version
   
   66  curl -LO https://github.com/kubernetes/minikube/releases/latest/download/minikube-linux-amd64
   
   67  sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64
   
   68  minikube version
   
   69  minikube start
   
   70  ll /home/
   
   71  minikube start --driver=none
   
   72  sudo minikube config set driver none
   
   73  minikube start --driver=none
   
   74  cat /etc/passwd
   
   75  minikube config set driver none
   
   76  brew install minikube
   
   77  minikube start
   
   78  crictl pods
   
   79  wget https://github.com/kubernetes-sigs/cri-tools/releases/download/v1.26.0/crictl-v1.26.0-linux-amd64.tar.gz
   
   80  sudo tar zxvf crictl-v1.26.0-linux-amd64.tar.gz -C /usr/local/bin
   
   81  crictl --version
   
   82  minikube start --driver=none
   
   83  minikube logs --file=log.txt
   
   84  sudo minikube config set driver none
   
   85  kubectl version
   
   86  minikube start --driver=none --kubernetes-version=v1.33.1 --addons=ingress,metrics-server
   
   87  minikube delete
   
   88  minikube logs --file=logs.txt
   
   89  minikube profile list
   
   90  minikube start --driver=none
   
   91  minikube profile list
   
   92  minikube delete
   
   93  sudo apt-get update
   
   94  sudo apt-get install ca-certificates curl
   
   95  sudo install -m 0755 -d /etc/apt/keyrings
   
   96  sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
   
   97  sudo chmod a+r /etc/apt/keyrings/docker.asc
   
   98  echo   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
   
   99    $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" |   sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   
  100  sudo apt-get update
  
  101  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
  
  102  minikube start --driver=none
  
  103  minikube start
  
  104  apt-get install ./cri-dockerd_0.3.17.3-0.ubuntu-jammy_amd64.deb
  
  105  apt-get install ./cri-dockerd-0.3.17.deb
  
  106  systemctl status cri-docker
  
  107  apt update
  
