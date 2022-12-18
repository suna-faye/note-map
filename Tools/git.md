# GIT
## set git proxy

```sh
git config --global http.proxy 'http://127.0.0.1:${port}'
git config --global https.proxy 'https://127.0.0.1:${port}'
```

## store credential
```sh
git config credential.helper 'store'
```