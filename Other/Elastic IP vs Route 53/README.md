# Elastic IP vs Route 53

## TL;DR
Elastic IPをAmazon EC2インスタンスに関連付けず、Route 53を利用して独自ドメインを関連付けて利用するのはなぜか？

**めんどいけど安いから**

## Elastic IP とは？

Elastic IP はAWSが提供するEC2インスタンスに関連付けることができる静的なIPアドレス(IPv4)で、インスタンス起動時はインターネットから取得した固定IPでアクセスすることができる。

