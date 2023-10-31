# symmetrical-system
kubernetes utilities

## debug pod

```
alias k=kubectl
echo "apiVersion: v1
kind: Pod
metadata:
  name: bash-debug
spec:
  containers:
  - name: bash-debug
    image: debian:testing
    command: ['sleep', '360000']
" > bash.yaml

k apply -f bash.yaml
```

```
apt-get update
apt-get install -y apt-transport-https ca-certificates curl gpg
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.28/deb/Release.key | gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.28/deb/ /' | tee /etc/apt/sources.list.d/kubernetes.list
apt install kubectl
```