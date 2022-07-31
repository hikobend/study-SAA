# SAA用語一覧

テスト日8/27

## SAA#1

インターネットに接続するステップは次の通り、

1. サブネットを作成

2. インターネットゲートウェイを設置

3. カスタムルートテーブルを設置

4. セキュリティグループのルールを更新

5. ElasticIPアドレスを追加


・storage Gateway

ローカルの本番アプリケーションやバックアップアプリとシームレスに接続できる。シームレスとは繋ぎ目なくという意味。

・EMR

・バックアップウィンドウ

即時にバックアップを取ることができる

・インタネットゲートウェイ

インタネットゲートウェイにて戻り通信をするとき、プライベートIPアドレスではElasticIPを設定する必要がある。

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

権限は何も持たない。権限を付与するためにはIAMグループに権限を付与してから、IAMユーザーをグループに入れる

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

## SSA#9
・RDSのフェイルオーバー

システムやサーバーが停止してしまった際に、自動的に待機システムに切り替える仕組み

・DBスナップショット

複製
|  DBスナップショットを作成  |  I/O  |
|  ----  |  ----  |
|  シングルAZ DB  |  短時間中断  |
|  シングルAZ DB  |  中断の影響を受けない |

・APIゲートウェイのCORS

ドメイン間のリクエストを許可する

・Route53のリソースレコード

HTTPSとか

あるDNSを別のDNS名に変更できる

CNAMEを使用すると任意の代替ドメイン名に変更することができる

・プロビジョニング

前もって需要を予測して調達すること

・EC2インスタンスのメモリ使用量を確認する

単一のエージェントをEC2にインスタンスに配置して、AWSCloudWatchカスタムメトリクスを使用してシステムメトリクスとログを回収できる

・EBS

データに素早くアクセスする必要がある。また長期永続性が必要な場合、推奨される。

・RDS for MySQLのストレージエンジン

InnoDBのみ対応

・プレイスメントグループ

プレイスメントグループを削除する時は、グループ内のインスタンスを削除する必要がある、

・インスタンスストアの永続性

起動中のインスタンスを停止してから起動すると、インスタンスストアのデータは消える

運用中の場合は保持され、停止すると停止する。

・AutoscalingとCloudWatch

スケールインとアウトするタイミングを制御して、スケーリングポリシーを設定できる

・インスタンスのユーザーデータ

EC2インスタンスを起動するときユーザーデータを渡すことで自動設定タスクを設定したり、スクリプトを実行できる







