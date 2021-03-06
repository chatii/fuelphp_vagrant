fuelphp_vagrant
===============

FuelPHP 用の Vagrantです。大いにオレオレ仕様です。
拙作の chatii/fuelphp_setup(https://github.com/chatii/fuelphp_setup) と併せて使うことを前提に作成しました。

## How to install

project_name は適宜 読み替えて下さい。

```bash
git clone git@github.com:chatii/fuelphp_vagrant.git project_name
cd project_name
# 拙作 chatii/fuelphp_setup をクローン
git clone git@github.com:chatii/fuelphp_setup.git project_name
# 中略、fuelphp_setup のインストールについては https://github.com/chatii/fuelphp_setup

# Vagrantfile 内の、/vagrant_data と同期するフォルダ名を書き換え
# (project_name を変更) 
sed -i -e 's/fuelphp_setup/project_name/g' Vagrantfile 
```

## MySQL について

リモートからの直接接続は許可していません。
chatii は、ホストマシンから [Sequel Pro](http://www.sequelpro.com/) のSSH接続を行っています。
以下は Sequel Pro の接続設定です

* MySQL ホスト: 127.0.0.1
* ユーザ名: root
* パスワード: (空)
* SSH ホスト: 192.168.33.10
* SSH ユーザ: vagrant
* SSH パスワード: vagrant
