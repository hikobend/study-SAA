# SAA用語一覧

テスト日8/27

## SAA#1
・NAT

・カスタムルートテーブル

・storage Gateway

・EMR

・RDS(バックアップウィンドウ)

・Elastic IP

## SAA#2

・アイデンティテベース

・リソースベース

・Route53のDNSレコードタイプ

・踏み台サーバー

## SAA#3

・RDSのストレージの種類(汎用SSD, プロビジョンドIOPS, マグネティック)

・リザーブドDBインスタンス

・I/O

## SAA#4

・クラスタープレイスメントグループ

## SAA#5

・スプレットプレイスメントグループ


## SAA#6 

・ブロックデバイスマッピング

・Linuxインスタンスの起動時のコマンドの実行

・NATインスタンス

・RTO、RPO

・インスタンスメタデータ

・IDS、IPSエージェント


## SAA#7

・Elastic IPアドレス

・Provisioned IOPS

・OLAP

・OLTP

・VPN接続の手順

・S3のデータ整合性モデル

・IAMロール


## SAA#8

・インスタンスの削除でEBSボリュームを保持

・DeleteOnTermination

・S3　API

・バケットポリシー

バケットごとにアクセス制御。JSON形式。他のAWSアカウントのアクセス制御を行うことができる。

・ユーザーポリシー

IAMユーザ/ロールに対してできるアクションやリソースの制御を行う。S3に対してはバケット、フォルダへのアクセス制御。JSON形式

・Policy Validator

無効なポリシーを摘出する

・IAMで新規ユーザーを作成

権限は何も持たない

・スループット

単位時間あたりに処理できるデータ量

・レイテンシー

転送要求を出してから実際にデータが送られてくるまでに生じる、通信の遅延時間のこと。ラグみたいな感じ

|  ----  |  可用性  |  スループレット  |  レイテンシー  |
|  ----  |  ----  |  ----  |  ----  |
|  マルチAZ  |  ●  |  ----  |  ----  |
|  スケールアップ  |  ----  |  ●  |  ----  |
|  リードレプリカ  |  ----  |  ●  |  ----  |
|  プロビジョンドIOPS  |  ----  |  ●  |  ●  |

・システムボリューム

ブート時に最初に読み込まれる

・ブートボリューム

OS が入っている  (名前が逆なら覚えやすいのに、なぜ反対にしたのだ)

最初はボリュームは汎用SSDにすると良い。

価格とパフォーマンスのバランスが良い。(コスパが良い)


















