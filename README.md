# Jetson_SPI_test
Jetson で SPI 通信をテストする時のあれこれ。

## テスト環境
* 使用機材
    * Jetson Nano Developer Kit
    * Jetson Xavier NX Developer Kit
* Software
    * JetPack 4.6.3

## SPI の有効化
Developer Kit で SPI を使うためには
[Jetsion-IO](https://docs.nvidia.com/jetson/archives/l4t-archived/l4t-3261/index.html#page/Tegra%20Linux%20Driver%20Package%20Development%20Guide/hw_setup_jetson_io.html#)
を使って拡張 40pin ヘッダーの設定をする必要がある。
JetPack インストール後の初期設定では SPI が無効に設定されている(単なる GPIO になっている)。

```bash
sudo /opt/nvidia/jetson-io/jetson-io.py
```

SPI を Master として使うには基本的に Jetson-IO を使うだけで OK だが、
Jetson Nano Developer Kit で JetPack 4.6.3 の場合はうまく行かない。
また、SPI を Slave として使うには追加で設定が必要になる。
詳細は [ここ](Jetson_SPI_memo.md) を参照。
