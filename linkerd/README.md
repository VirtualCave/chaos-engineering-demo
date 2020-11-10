# Linkerd set up

## 1. Download linkerd binary

```
$ linkerd https://github.com/linkerd/linkerd2/releases/download/stable-2.9.0/linkerd2-cli-stable-2.9.0-linux-amd64
$ chmod +x linkerd
$ sudo mv linkerd /usr/local/bin/
```

Moving the binary to _/usr/local/bin/_ is just for lazyness purposes ;)

## 2. Apply kubernetes manifests

```
kubectl apply -f linkerd-install.yaml
```
