# Kube switch-config
Kubectl plugin for simple switching between kubeconfig files.

## Initial setup
Prepare separate kubeconfig files in `$HOME/.kube` directory named (e.g.):
```
config-test
config-prep
config-prod
...
```

If you use [Charmed Kubernetes](https://ubuntu.com/kubernetes/docs) you can get cluster config with `juju scp` command (example):
```
juju scp kubernetes-master/0:config ~/.kube/config-test
```
If you already have `$HOME/.kube/config` regular file (not symlink), rename it or remove (ensuring you don't need it or have a backup). This tool uses symbolic link with this name to switch between configurations.

## Usage

For example:
```
kubectl switch-config test
```
will switch to configuration named `test`.

Show current configuration:
```
kubectl switch-config
test
```

Display help:
```
kubectl switch-config -h
```
