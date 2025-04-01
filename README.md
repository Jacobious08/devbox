# Installing k3s

### Update package list and install tools

sudo apt update && sudo apt upgrade -y
sudo apt install -y curl wget vim

### Install k3s

curl -sfL https://get.k3s.io | sh -

### Verify instillation

sudo systemctl status k3s
sudo k3s kubectl get nodes

# If you run into permission errors:

mkdir -p ~/.kube
sudo cp /etc/rancher/k3s/k3s.yaml ~/.kube/config
sudo chown $(id -u):$(id -g) ~/.kube/config
export KUBECONFIG=~/.kube/config

(then retry)

# If problems persist:

IDK bro ¯\_(ツ)_/¯
