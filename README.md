# centos7_setup

## ゲスト OS 側から共有フォルダにファイルを置いてもホスト OS 側で認識されない場合の手順

不要な手順があるかもしれないが、以下で反映されるようになった。

1. ```$ vagrant halt```
2. ```$ vagrant plugin install vagrant-vbguest```
3. ```$ vagrant plugin expunge --reinstall```
4. Vagrantfile の共有フォルダの設定を以下に変更する
5. ```$ vagrant up```

```sh
config.vm.synced_folder ".", "/vagrant", type:"virtualbox"
```