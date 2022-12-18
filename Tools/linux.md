## wsl
```sh
# wsl2 use windows proxy
export hostip=$(cat /etc/resolv.conf | grep nameserver | awk '{ print $2 }')

alias proxy_port="12138"
alias www="https_proxy=\"http://${hostip}:${proxy_port}\" http_proxy=\"http://${hostip}:${proxy_port}\""
# or set it global
# export hostip=$(cat /etc/resolv.conf | grep nameserver | awk '{ print $2 }')

# export https_proxy="http://${hostip}:${proxy_port}"
# export http_proxy="http://${hostip}:${proxy_port}"
```

## oh-my-zsh
```sh
# set alias
# vim ~/.oh-my-zsh/custom/alias.zsh
# set proxy alias
alias my_proxy="export http_proxy=\"http://proxydomain:port\"; export https_proxy=\"https://proxydomain:port\"; npm config set proxy http://proxydomain:port; npm config set https-proxy https://proxydomain:port"
# remove proxy alias
alias local_proxy="unset http_proxy; unset https_proxy; npm config rm proxy; npm config rm https-proxy"
```