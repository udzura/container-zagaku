# container-zagaku

Zagaku VM about containers

## こしひかりの皆様へ :rice:

* 座学の事前準備として、以下をやっておいてください
  * （ダウンロードを伴うので、回線負荷諸々考えると事前準備が吉）

### VM の作成と立ち上げ

```bash
git clone https://github.com/udzura/container-zagaku.git ( or use ghq, &c... )
cd container-zagaku
vagrant up
```

### (Nice to have) 余裕があれば Haconiwa 入れちゃってください

```console
$ vagrant ssh
vagrant@localhost:~$ curl -s https://packagecloud.io/install/repositories/udzura/haconiwa/script.deb.sh | sudo bash
vagrant@localhost:~$ sudo apt-get install haconiwa

vagrant@localhost:~$ haconiwa version
haconiwa: v0.2.4
vagrant@localhost:~$ haconiwa        
haconiwa - The MRuby on Container
commands:
    create    - create the container rootfs
    provision - provision already booted container rootfs
    start     - run the container
    attach    - attach to existing container
    kill      - kill the running container
    version   - show version
    revisions - show mgem/mruby revisions which haconiwa bin uses

Invoke `haconiwa COMMAND -h' for details.
```

## 資料

* https://speakerdeck.com/udzura/the-skelton-of-whales

