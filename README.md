# wower
wower可以帮你一步步编译安装0抽水xmrig挖矿程序，仅支持Debian和ubuntu！

## 安装

安装脚本和后台服务，根据提示输入“XMR钱包地址”、“矿池地址（例如：**pool.supportxmr.com:3333**）”和“矿工名称”。

```
wget --no-check-certificate -qO wower.sh 'https://git.io/wower.sh' && chmod a+x wower.sh && ./wower.sh
```

## 使用
开启wower挖矿
```
systemctl start wower
```
重启wower
```
systemctl restart wower
```
停止wower挖矿
```
systemctl stop wower
```

## 帮助
1. 后续更改矿池等设置，可直接替换使用以下命令：

```
# 更改矿池
sed -i 's/"url": *"[^"]*",/"url": "挖矿地址:端口",/' $HOME/wower/build/config.json
# 更换钱包地址
sed -i 's/"user": *"[^"]*",/"user": "钱包地址",/' $HOME/wower/build/config.json
# 更改矿工名字
sed -i 's/"pass": *"[^"]*",/"pass": "矿工名字",/' $HOME/wower/build/config.json
# 开启1gb-pages（推荐设置）
sed -i 's/"1gb-pages": *false,/"1gb-pages": true,/' $HOME/wower/build/config.json
```


2. 矿池选择：[https://miningpoolstats.stream/monero](https://miningpoolstats.stream/monero)
请根据自己需求合理选择矿池和端口：
* pool.minexmr.com:4444
* pool.supportxmr.com:3333
* xmr-us-east1.nanopool.org:14444

3. 推荐把系统用网络重装成Debian 11。
4. 挖矿后，要等一段时间才能在矿池网站查询到。
5. 欢迎分享一些配置优化。

6.限制cpu占用50%，可以搭配宝塔定时任务夜晚闲时挖矿。
```
sudo apt-get install -y cpulimit
sudo cpulimit -e xmrig -l 50 -b
```

### 反馈交流：[VPS讨论群](https://t.me/vpsqun)

## 捐赠
如果您觉得脚本对您有用，可以请我喝杯咖啡。
xmr捐助地址：
    82da8smo7MMeJ5baJ553RSZfDUWSfMjHQdmpP98aD4wpZNwArjKdMLDbGZYDqFvNoL75BiDdyTHxKNyijv9bsMmrM1k7rYw
