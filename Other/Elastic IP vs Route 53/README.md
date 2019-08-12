# Elastic IP vs Route 53

## TL;DR
Elastic IPをAmazon EC2インスタンスに関連付けず、Route 53を利用して独自ドメインを関連付けて利用するのはなぜか？

**安いから、または1アカウントで取得できるEIPに制限(デフォルトは5)があるから**

## Elastic IP とは？

Elastic IP はAWSが提供するEC2インスタンスに関連付けることができる静的なIPアドレス(IPv4)で、インスタンス起動時はインターネットから取得した固定IPでアクセスすることができる。

EC2インスタンスは起動時にパブリックIPアドレスが付与されるが、これは起動するたびにアドレスが代わるため、固定化するためにEIPを用いる。

★参考文献  
[1] [【公式】Elastic IP アドレス](https://docs.aws.amazon.com/ja_jp/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html)  
[2] [AWS Elastic IPアドレス (EIP) とは何か？ 利用用途とメリットを解説](https://サーバー構築と設定.com/?p=2079)
