archlinux react-native android environment
==========================================

## NOTE

Still work in progress, not finished yet, please come back later.

## android development environment

We need install lots of things, and maybe specific version. And We do
not want to mess the system, so customizing PKGBUILD some time.

### from archlinuxcn

add archlinuxcn source, install these:

- android-sdk 24.4.1-1
- android-sdk-build-tools r23.0.2-1
- android-sdk-platform-tools r23.1.0-2
- android-ndk r10e-1

from aur:

- android-platform 23_r02-1
- android-support r23.1.1-1
- android-support-repository r25-1

For me, these version works, you may try them and please tell me if not working.
To install them, you may need download PKGBUILD file, customize for specific satification.
(Normally, I'd change version and, thanks for GFW, the download link)

<TODO: add PKGBUILD patch>

## 配置npm

### 基本配置
[参考](https://wiki.archlinux.org/index.php/Node.js_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)

- 主要解决的问题是global安装时，默认prefi是/usr，需要超级权限，并且把系统搞乱了

- 用wiki中提到的第三种办法

  npm config edit
    add prefix = ~/.node_modules

  vim .zshrc
    add export PATH=$PATH:~/.node_modules/bin

  note: npm config edit => edit ~/.npmrc

### npm修改源
  npm config edit
    add registry=https://registry.npm.taobao.org

##

npm install -g react-native-cli --verbose
react-native init demo --verbose


to start the server:
  react-native start

run the installer:
  react-native run-android

set the dev setting to the form ip:8081, where ip is the address of your server

## FAQ

1. rm ./node_modules/react-deep-force-update/.babelrc and restart server
