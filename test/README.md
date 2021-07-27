## Test this repo with Vagrant

The following instruction are tested on Ubuntu 20.04 with Vagrant 2.15 with libvirt provider.

### Before VMs

```
# Download utilities binaries files into bin folder,
# e.g. k9s, helm, kustomize, flux, etc

# to create new token
openssl rand -base64 32 > setup/token.txt

```

### Steps for VM1
```
vagrant up s1
vagrant ssh s1

# spin up K3S master with embedded ETCD
cd setup
./cluster_init

# the script will run and should print an IP address at the end

```

### Stesp for VM2 and VM3

vagrant up s2
vagrant ssh s2

# if joining K3S as a master node
# edit server script to replace k3s1 with the IP address from virst master node
./server

# if joining K3S as an agent
# edit agent script to replace k3s1 with the IP address from virst master node
./agent


```
# generate a SSH key and add as Deploy key if neccessary

### Bootstrap Flux and Sync
flux bootstrap git \
  --url=<this_repo> \
  --branch=test \
  --path=clusters/test \
  --private-key-file=$HOME/.ssh/id_rsa

```


