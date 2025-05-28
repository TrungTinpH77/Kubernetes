# Kubernetes
**#Ubuntu 22.04**

Install-Learning

- Cài docker trước
  
- Cài đặt và kiểm tra version kubectl và minikube

      echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check

      sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
   
      kubectl version --client

      curl -LO https://github.com/kubernetes/minikube/releases/latest/download/minikube-linux-amd64
   
      sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64
   
      minikube version

- Cài đặt cri-dockerd và kiểm tra hoạt động
  
      wget https://github.com/Mirantis/cri-dockerd/releases/download/v0.3.17/cri-dockerd-0.3.17.amd64.tgz
   
      tar -xzf cri-dockerd-0.3.17.amd64.tgz
   
      install -o root -g root -m 0755 cri-dockerd/cri-dockerd /usr/local/bin/cri-dockerd
   
      wget https://raw.githubusercontent.com/Mirantis/cri-dockerd/master/packaging/systemd/cri-docker.service
  
      wget https://raw.githubusercontent.com/Mirantis/cri-dockerd/master/packaging/systemd/cri-docker.socket

      install cri-docker.service /etc/systemd/system

      install cri-docker.socket /etc/systemd/system

      sed -i -e 's,/usr/bin/cri-dockerd,/usr/local/bin/cri-dockerd,' /etc/systemd/system/cri-docker.service
  
      systemctl daemon-reload
  
      systemctl enable --now cri-docker.socket
  
      systemctl enable cri-docker
  
      systemctl start cri-docker
  
      systemctl status cri-docker

- Cài đặt containernetworking-plugins và kiểm tra hoạt động

      CNI_PLUGIN_VERSION="v1.7.1"
  
      CNI_PLUGIN_TAR="cni-plugins-linux-amd64-$CNI_PLUGIN_VERSION.tgz"
  
      CNI_PLUGIN_INSTALL_DIR="/opt/cni/bin"
  
      curl -LO "https://github.com/containernetworking/plugins/releases/download/$CNI_PLUGIN_VERSION/$CNI_PLUGIN_TAR"
  
      sudo mkdir -p "$CNI_PLUGIN_INSTALL_DIR"
  
      sudo tar -xf "$CNI_PLUGIN_TAR" -C "$CNI_PLUGIN_INSTALL_DIR"
  
      rm "$CNI_PLUGIN_TAR"

- Chạy khỏi tạo cluster với none, kiểm tra trạng thái => Running

      minikube start --driver=none
     
      minikube status
