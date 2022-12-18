## oh-my-zsh
```sh
### vim ~/.oh-my-zsh/custom/alias.zsh
### get windows ip
export win_proxy_host=$(cat /etc/resolv.conf | grep nameserver | awk '{ print $2 }')

### set default proxy port
export win_proxy_port="12138"

### create alias to export proxy env variable 
alias win_proxy="export https_proxy=\"https://${win_proxy_host}:${win_proxy_port}\"; export http_proxy=\"http://${win_proxy_host}:${win_proxy_port}\"; git config --global https.proxy \"https://${win_proxy_host}:${win_proxy_port}\"; git config --global http.proxy \"http://${win_proxy_host}:${win_proxy_port}\"; npm config set proxy http://${win_proxy_host}:${win_proxy_port}; npm config set https-proxy https://${win_proxy_host}:${win_proxy_port}"

### execute alias
win_proxy

### create alias to export proxy env variable
export custom_proxy_host="proxy.com"
export custom_proxy_port="12138"

### custom proxy
alias custom_proxy="export http_proxy=\"http://${proxy_host}:${proxy_port}\"; export https_proxy=\"https://${proxy_host}:${proxy_port}\"; git config --global https.proxy \"https://${proxy_host}:${proxy_port}\"; git config --global http.proxy \"http://${proxy_host}:${proxy_port}\"; npm config set proxy http://${proxy_host}:${proxy_port}; npm config set https-proxy https://${proxy_host}:${proxy_port}"

### apply custom proxy
# custom_proxy

### remove all proxy alias
alias unset_proxy="unset http_proxy; unset https_proxy; npm config rm proxy; npm config rm https-proxy; git config --global --unset https.proxy; git config --global --unset http.proxy"
```
