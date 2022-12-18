## oh-my-zsh
```sh
### vim ~/.oh-my-zsh/custom/alias.zsh

### get windows ip
export win_proxy_host=$(cat /etc/resolv.conf | grep nameserver | awk '{ print $2 }')
### set default proxy port
export win_proxy_port="12138"

### create alias to export custom proxy env variable
export custom_proxy_host=$win_proxy_host
# export custom_proxy_host="custom.proxy.domain"

export custom_proxy_port=$win_proxy_port
# export custom_proxy_port="12138"

### create alias to export win proxy env variable
alias win_proxy="export https_proxy=\"https://${win_proxy_host}:${win_proxy_port}\"; export http_proxy=\"http://${win_proxy_host}:${win_proxy_port}\"; git config --global https.proxy \"https://${win_proxy_host}:${win_proxy_port}\"; git config --global http.proxy \"http://${win_proxy_host}:${win_proxy_port}\"; npm config set proxy http://${win_proxy_host}:${win_proxy_port}; npm config set https-proxy https://${win_proxy_host}:${win_proxy_port}"

### custom proxy
alias custom_proxy="export http_proxy=\"http://${custom_proxy_host}:${custom_proxy_port}\"; export https_proxy=\"https://${custom_proxy_host}:${custom_proxy_port}\"; git config --global https.proxy \"https://${custom_proxy_host}:${custom_proxy_port}\"; git config --global http.proxy \"http://${custom_proxy_host}:${custom_proxy_port}\"; npm config set proxy http://${custom_proxy_host}:${custom_proxy_port}; npm config set https-proxy https://${custom_proxy_host}:${custom_proxy_port}"

### remove all proxy alias
alias unset_proxy="unset http_proxy; unset https_proxy; npm config rm proxy; npm config rm https-proxy; git config --global --unset https.proxy; git config --global --unset http.proxy"

### apply custom proxy
win_proxy

### apply custom proxy
# custom_proxy
```
