# GitHub

## GitHub520

```shell
export ConfigFile="/etc/hosts"
if [ ! -f "${ConfigFile}.raw" ]; then
  sudo cp "${ConfigFile}" "${ConfigFile}.raw";
else
  sudo cp "${ConfigFile}.raw" "${ConfigFile}"
fi
curl -sS https://raw.hellogithub.com/hosts| sudo tee -a  /etc/hosts
sudo resolvectl flush-caches
```

## 代理

+ [设置代理解决github被墙](https://zhuanlan.zhihu.com/p/481574024)
+ [给 Git(Github) 设置代理](https://gist.github.com/chuyik/02d0d37a49edc162546441092efae6a1)

```shell
# 设置
git config --global https.proxy "http://127.0.0.1:1080"
git config --global https.proxy "https://127.0.0.1:1080"
# Or
git config --global http.proxy "socks5://127.0.0.1:1080"
git config --global https.proxy "socks5://127.0.0.1:1080"

# 取消
git config --global --unset http.proxy
git config --global --unset https.proxy
# 可选项
# npm config delete proxy
```

## URL替换

+ [利用github.com.cnpmjs.org快速下载GitHub仓库](https://note.qidong.name/2020/12/github-proxy/)
+ [GitHub Proxy 代理加速](https://ghproxy.com/)

```shell
# git config --global url."https://github.com.cnpmjs.org/".insteadOf "https://github.com/"
# git config --global --remove-section url."https://github.com.cnpmjs.org/"
# or
# git config --global -e

git config --global url."https://ghproxy.com/https://github.com/".insteadOf "https://github.com/"
# git config --global --remove-section url."https://ghproxy.com/https://github.com/"
```

## [GitHub Docs](https://docs.github.com/cn)

- [生成新 SSH 密钥并添加到 ssh-agent](https://docs.github.com/cn/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent)

