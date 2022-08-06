# SAA用語一覧

テスト日8/27

## SAA#1

インターネットに接続するステップ

1. サブネットを作成

2. インターネットゲートウェイを設置

3. カスタムルートテーブルを設置

4. セキュリティグループのルールを更新

5. ElasticIPアドレスを追加

・storage Gateway

ローカルの本番アプリケーションやバックアップアプリとシームレスに接続できる。シームレスとは繋ぎ目なくという意味。

・バックアップウィンドウ

即時にバックアップを取ることができる

・インタネットゲートウェイ

インタネットゲートウェイにて戻り通信をするとき、プライベートIPアドレスではElasticIPを設定する必要がある。

## SAA#2

・アイデンティテベース

IAMユーザー、グループ、ポリシーにアタッチする。アクセス許可を指定できる。

・リソースベース

リソースにアタッチすることができる

・Route53のDNSレコードタイプ

Route53のエイリアスレコードは無料

・踏み台サーバー

インターネットに直接繋がないインスタンスに対して、接続するために経由させるサーバー。最も安全な接続方法。

・他の人のリソースを操作する

アクセスキーやシークレットキーを用いて、CLIやSDKを用いて操作できる

## SAA#3

・RDSのストレージの種類(汎用SSD, プロビジョンドIOPS, マグネティック)

|  汎用SSD  |  プロビジョンドIOPS  |  マグネティック  |
|  ----  |  ----  |  ----  |
|  さまざまなワークロードに対応できる。<br>コスパが良い長時間3,000IOPSできる  |  I/O重視のワークロード  |  RDSの下位互換用のもの  |

・リザーブドDBインスタンス

マルチAZ展開でもシングルAZ展開でも使用することができる。

・I/O

Inout/Output

・インスタンスを別のリージョンにコピー

インスタンスを停止してから、AMIをを作成し別のリージョンにコピーする。

・Administer Access　Policy

全てのアカウントのリソースにアクセスするための管理者グループの許可をあたえるポリシー

## SAA#4

・ネットワークACL

インバウンドとアウトバウンドを制御するファイアウォール。低い番号から順に制御する。

・Cold HDD

シーケンシャルアクセスとして良い、データにアクセスが少なく、コストの軽減が必要な場合におすすめ。

・シーケンシャルアクセル

データの先頭から順に検索し、アクセスする

・クラスタープレイスメントグループ

単一のAZ内のインスタンス倫理的にグループ化したもの。プレイスメントグループ内の全てのノードは、プレイスメントグループ内全てのノードと会話できる。

・ノード

ネットワーク同士の接点。

・セキュリティグループ

インスタンスの仮装ファイアウォールとして機能。

## SAA#5

・スプレットプレイスメントグループ

少数の重要なインスタンスが互いに分離して保持される。同時障害のリスクが少ない。

・EC2インスタンスを起動し、プライベートIPアドレスを割り当てる。

VPCにインスタンスを作成する際にプライベートIPアドレスを割り当てる。

## SAA#6 

|  ----  |  NATゲートウェイ  |  NATインスタンス  |
|  ----  |  ----  |  ----  |
|  管理  |  AWSが行う  |  ユーザが行う  |
|  踏み台サーバー  |  できない  |  できる  |

・NATインスタンス

NATインスタンスは送受信ができるように設定する。NATインスタンスの構成を変更するとき、SrcDestCheck属性を無効にする。送信元、送信先チェックを向こうにする必要がある。パブリックIPアドレスorElasticIPアドレスのどちらかが設定されていれば良い

・インスタンスメタデータ

インスタンスのプロパティを確認するために、インスタンスメタデータを確認する必要がある

・IDS、IPSエージェント

不正侵入検知・防御システムをインスタンス・リバースプロキシ層に実装

## SAA#7

・Elastic IPアドレス

静的なパブリックIPアドレスを利用することができる。

・Provisioned IOPS

|  ----  |  OLTP  |  OLAP  |
|  ----  |  ----  |  ----  |
|  使用用途  |  業務システムの操作ニーズに対応  |  大量のデータの集計や分析  |
|  対応  |  多数のユーザからランダムに発生するトランザクションに対応  |  大量レコードの一斉書き込みなどの複雑な処理に対応  |

・VPN接続の設定

カスタマーゲートウェイの外部インターフェイスでルーティング可能なIPアドレスは静的である必要がある。

・S3のデータ整合性モデル

新規ファイルのアップロード、既存のファイルの上書き・削除を行う場合、書き込み後すぐに読み込みができるようにしなければならない

・IAMロール

AMIで別リージョンを作成しても、権限はIAMロールを用いて、権限を付与する必要がある。

・DynamoDB

ユーザのセッション情報を保存して、スケーラブルな低レイテンシーなアクセスを提供する

## SAA#8

・インスタンスの削除でEBSボリュームを保持

・DeleteOnTermination

EC2インスタンス削除時にEBSボリュームを保持するかどうかのオプション

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

## SAA#10

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

## SAA#11

・プライベートIPアドレス

インターネットからアクセスできなIPアドレス

・RDSのセキュリティ

アプリケーションとDBインスタンス間の接続を暗号化する際、SSL/TLSを用いる

・EBSでスナップショットを作成している時の状態

Peanding

・年間ダウンタイム

年間で停止している時間。99.99%で52分

・DBパラメータグループ

静的パラメータを変更した場合、有効にするためにインスタンスを再動する必要がある。

・S3にデータを安全にアップロード・ダウンロードする

HTTPSプロトコルを使用する。

## SAA#12

・Aurora

スケーラビリティを提供して、100ミリ秒未満のレプリカラグを提供

・スケーラビリティ

拡張性

・レプリカラグ

データベースサーバーのレプリケーションをして、そのデータがレプリケーション先から読み出し可能になるまでにはある程度以上のレイテンシ

・CloudWatchアラーム

ユーザーが設定した値を超えたらアラームが作動するように設定できる。メール送信やSQS発効や、EC2インスタンスを停止・終了させるように設定可

・RDS for PostgreSQLのDBインスタンスを削除する

全てのリードレプリカがスタンドアロンDBインスタンスに昇格し、読み込みトラフィックと書き込みトラフィックの両方を受け付ける。

・スタンドアロン

インターネットなどのネットワークにつながっていない状態で情報の配信

|  ----  |  デベロッパープラン<br>営業時間  |  ビジネスプラン<br>いつでも  |  エンタープライスプラン<br>いつでも  |
|  ----  |  ----  |  ----  |  ----  |
|  全般ガイダンス  |  24時間以内  |  24時間以内  |  24時間以内  |
|  システム障害  |  12時間以内  |  12時間以内  |  12時間以内  |
|  本番稼働用<br>システム障害  |  ----  |  4時間以内  |  4時間以内  |
|  本番稼働用<br>システムのダウン  |  ----  |  1時間以内  |  1時間以内  |
|  ビジネスクリティカルな<br>システムダウン  |  ----  |  ----  |  15分以内  |

・インスタンスメタデータとユーザーデータの暗号化

データは認証または暗号化手法によって保護されていないインスタンス、インスタンス上で実行される任意のソフトウェアに対して直接アクセス権がある可能性がある人は、メタデータを表示できる

・マルチパートアップロード

アップロード中に中断されたパートのアップロードを再試行するだけで済む。ファイルを細かく分割し、並行してアップロードする。

## SAA#13

・EBSボリュームの最適なバックアップ

EBSボリュームのスナップショットを取得する

|  Route53がサポートしている<br>DNSレコードタイプ  |
|  ----  |
| A(アドレスレコード) |
| AAAA(IPv6アドレスレコード) |
| CNAME(正規名レコード) |
| MX(メール交換レコード) |
| NS(ネームサーバーレコード) |
| PTR(ポインタレコード) |
| SOA(管理情報の始点レコード) |
| SPF(センターポリシーフレームワーク) |
| SRV(サービスロケーター) |
| TXT(テキストレコード) |

・DBインスタンスのバックアップ期間

RDS API or CLIで作成するとデフォルトで1日。コンソールを使用すると7日。設定を変更すると最大で35日。

・SWF

Simple workflow。並行したステップまたは連続したステップがあるバックグラウンドジョブを構築、実行、スケールするのに役立つ。複数サーバーで商品発注のようなワークフローを処理する際の順番の振り分け先を管理するサービス。実施する工程が定まっているやつを管理するサービス。

・プライマリ

DBインスタンスのデータベースの読み込みと書き込みの機能を提供する。

・Elastic Beanstalk

AWSにアプリケーションをデプロイするために最も早いサービス、

・Redshift

高速でスケーラブルなデータウェアハウス。分析をシンプルで費用対効果が高いAWSのデータベースサービス。

## SAA#14

・Aurora

高性能の商用データベースの速度や信頼性と、オープンソースデータベースのシンプルさや費用対効果を兼ね備える。MYSQLの最大5倍mのパフォーマンスを実現可能。PostgreSQLの最大3倍。

・RDSのDBインスタンスに十分な空き容量があるか確認

FreeStorageSpaceを使ってRDSメトリクスを確認することができる。

・S3のデータを誤って削除したり、上書きすることから保護

オブジェクトのバージョニングを有効kにする。

・ルートデバイスのストレージ

インスタンスが削除されると、ルートボリュームのデータは自動的に削除される。

・ElasticIpアドレスの費用

実行中のインスタンスに関連付けられていない場合や、停止ているインスタンスやアタッチしていないネットワークインスタンスインターフェースに関連づけられている場合、時間ごとに請求される。

・AWSホワイトペーパー

アーキテクチャ、セキュリティ、エコノミクスなどのトピックを扱ったAWSの技術文書の集まり。

## SAA#15

・SNS

SQSやHTTP/sやLambdaなどのエンドポイントにメッセージや通知を送信できる。

・暗号化されたEBSスナップショットのクロスアカウントコピー

暗号化されたスナップショットを共有することができる。

・DynameDB

各ウェブサーバーを対象としたセッション状態の共有に対して効果的なソリューションが実現できる。耐久性と低レイテンシーを備えた拡張性がある。

|  ----  |  RDSメトリクス  |
|  ----  |  ----  |
|  ReadIOPS  |  1秒当たりのディスクI/O操作の平均回数  |
|  SwapUsage  |  DBインスタンスで使用するスワップ領域の量  |
|  CPUUtilization  |  CPU使用量  |
|  DatabaseConnections  |  使用中のデータベース接続量  |

・SQS

メッセージを少なくとも1回の配信で耐久性を提供し、DynamoDBへの書き込みをバッファリングできる。

・RDS

書き込み処理をするために水平方向にスケーリングできない

・ブロックデバイスマッピング

## SAA#16

・障害対策装置がAZで共有されるか

共有されない。物理的に独立しているので、それぞれに配置されているものが異なる

・EBS

独自のファイルシステム。どんな規模のワークロードに対応できる。

・EFS

独自のファイルシステムではない。EC2インスタンスはNFSを通じてアクセスできる。

・S3

オブジェクトストレージサービス。独自のファイルシステムを構築できない

・S3のキー

バケット内のオブジェクトの固有の識別子。「バケット + キー + バージョン」

・インスタンス上のデータ

再起動後の意図の有無に関わらず削除されない。停止すると、削除される

|  IAMユーザーを削除すると<br>消える情報  |
|  ----  |
|  ユーザー  |
|  所属していたグループ  |
|  パスワード  |
|  アクセスキー  |
|  インラインポリシー  |

・Elastic Beanstalk + Docker

容量のプロビジョニング、負荷の分散、スケーリング、アプリケーションの状態の監視の詳細を処理する。各アプリケーションを別々のDockerコンテナとしてデプロイできる。

## SAA#17

・S3　IT

アクセスパターンが変化したときに4つのアクセス階層の間でオブジェクトを移動する。アクセスがなかった場合、低頻度のアクセス階層に移動する。

・グローバルIPアドレスの調査

インスタンスのメタデータから参照する

・ifconfig

プライベートIPアドレスが表示される

・Route53のヘルスチェック

デフォルトで30秒。ウェブアプリケーション、ウェブサーバー、その他のリソースの正常性とパフォーマンスを監視する。

・マルチAZ配置したスタンバイ

読み込みができない。プライマリ状態ではデータベースに読み込みと書き込みができる。

・CDN

コンテンツ配信ネットワーク

・CloudFront

データ、動画、アプリケーション、APIを全てのデベロッパーに使いやすい環境。コンテンツ配信サービスを提供するサービス。

・IAMのアクセス権限で、リソースへのアクセスを制限する

アイデンティティベースのポリシーとリソースベースのポリシー

・Amazon リソースネーム

AWS内に作成されているリソースを一意に指定できる

## SAA#18

・NAT

パブリックサブネットとプライベートサブネットをもつVPC。ネットワークアドレスを変換する。

・NATで起動するべきウェブサーバーの場所

パブリックサブネット。データベースサーバーは、NATゲートウェイを通じて、インターネットに接続して、ソフトウェアアップデートを行う。

・RDSへプラグイン

SSHやRDPでログインできない。EC2上にRDBMSをインストールする必要がある。

・RDBMS

データベースのうち、データを表に似た構造で管理するもの

・ディザスタリカバリー(DR)

災害復旧。地震や津波などの天災や、テロ、不正侵入などによりシステムが壊滅的な状況になった際に復旧・修復すること。

・S3Glacier

アーカイブのサイズは40TB。データの総量の上限はなし。

・RDSのバックアップストレージ

RDSのDBインスタンスのバックアップに自動バックアップとDBスナップショットはS3に格納される。

・AutoScaringのスケールイン・アウト

スケールイン・・・システムを構成する仮想マシン・サーバーの台数を減らす。アウト・・・増やす。

・インスタンスのスケールイン保護

スケールイン時にインスタンスを終了するか制御するもの

・S3のアクセスコントロール

ACL、IAM、バケットポリシーのうち、1つでもDenyになっていたらアクセスできない。

## SAA#19

・データの保護

EBSとS3の暗号化を使用してm保存データのセキュリティを提供し、SSL/HTTPSを使用して転送中のデータのセキュリティを提供する

・EBSのスナップショットの作成コマンド

CLIにてcreate-snapshotと打つ。

・Lambdaのアクセス権限

Lambda関数にRDSインスタンスをリストする権限をもつIAMロールを割り当てる必要がある。IAMアクセスキーの使用は非推奨。

・RDS MYSQL DBインスタンスの読み込みと書き込みのIOPS値をリアルタイムで送信する

CloudWatchとSNSと使用する。RDSインスタンスのIOPSを測定し、SNSを利用してリアルタイムに運用チームへアラートを送る

・RDSのマルチAZ配置

同じリージョンの異なるAZとして自動的に設定される。

・EBSの価格

EBSの価格は容量が課金対象になる。使用量ではない。

## SAA#20(Auto Scaling)

・Auto Scalingの設置数

Webサーバーとアプリケーションサーバーに設置する。データベースには設置する必要なない。

・Auto Scalingグループに適切なEC2インスタンスがあるようにする

ClouWatchアラームの作成。EC2インスタンスをアプリケーション層へ参加。EC2インスタンスのCPU使用率メトリクスの使用。Auto Scalingで別のインスタンスの起動。

・Auto ScalingでEC2インスタンスを軌道から実行までにかかる時間

基本的に数分。

・Auto Scalingのクールダウン期間の設定

インスタンスがスケールアウトした後、特定の期間が経過するまでスケーリングアクティビティを中断する。(初期設定300秒)

・デフォルトのクールダウン

Auto Scalingグループ作成時に指定。(全体に適応)

・スケーリング固有のクールダウン

スケーリングポリシーを個別に指定できる。デフォルトのクールダウン期間を上書きできる。

・Auto Scalingの動作の特徴

最後のインスタンスが起動すると、クールダウン期間が有効になる。ユーザーアクション中はスケールアウトが中断される。ユーザーアクション完了後にクールダウンが適応される。スポットインスタンスの入札が成功すると、クールダウン期間が有効になる

## SAA#21

・DynamoDB

数ミリ秒の管理データベース。拡張性も高い。

・Aurora

3つの異なるAZに格納するため、AuroraもしくはDynamoDB。互換性があるのはAurora。

・ネットワークインターフェースの基本

VPCの各インスタンスには、プライマリネットワークインターフェ　ース(eth0)と言われるデフォルトのネットワークインターフェースがある。

・ローンチ

サービスの開始、立ち上げ

## SSA#22

・AZ

障害から確立されるように設計されたAWSリージョンに複数のそれぞれ独立したロケーション

・RI

リザーブドインスタンス

・データ転送

同じAZ内でRDSとEC2インスタンス間のデータ転送は無料。

・DisableApiTermination

EC2インスタンスの偶発的な削除を防止する。

## SAA#23

・EC2インスタンスとIAMロール

すでに実行されているEC2インスタンスにIAMロールをアタッチすることができる。

・https://status.aws.amazon.com/

AWSの各サービスの稼働状況を確認できる。

・インスタンスの削除防止

EC2インスタンスにタグを付けてから、タグに基づいて特定のユーザーがインスタンスを削除させることを許可・禁止するためのポリシーを作成。

・Snowball

ペタバイト規模のデータをAWSクラウドに転送するリージョン

・汎用T2

EC2インスタンスの一種。無料枠の対象。ベースラインレベルのCPUパフォーマンスを提供するバースト可能ぱフォーマンスインスタンスで、パフォーマンスをベースラインを超えるレベルにバーストさせる機能を持つ

・セキュリティグループのデフォルト設定

インバウンドトラフィックは許可せず、アウトバウンドトラフィックは許可する。

## SAA#24

・クロスゾーン負荷分散

インスタンスに対して均等に負荷分散させることが可能

・IAMロールの料金

IAMロールは無料で使用可能。

・EBS

EC2インスタンスで使用するブロックレベルのステレージボリューム。デバイスとしてmインスタンスにマウントできる。料金は使用した分だけ払う。

・ELB

変動するアプリケーショントラフィックの負荷を、1つのAZや複数のAZで処理できる。ヘルスチェック機能で、ELBは以下のインスタンスがヘルスチェックに失敗すると、振り分けを停止する。また暗号化・複合化(SSL)機能もある。

・EBSの暗号化

暗号化されたEBSボリュームを作成する

・ログの確認先

ログファイルはS3バケットとCloudWatchLogsに配信することができる。

## SAA#25

・ネットワークインタフェースあたりのセキュリティグループの最大数

5つ。

・ネットワークACL

セキュリティグループはサブネットレベルでの作動はできない。ネットワークACLを用いる必要がある。

・他のサイトへフェールオーバーする際の注意点

ネットワーク設定の変更が必要。Route53を用いて、ドメインネームシステムを構築し、ルーティングできるようにする。ElasticIPアドレスを用いて、パブリックIPアドレスを固定IPアドレスにする。

・ElasticIPアドレスが関連づけられているEC2インスタンスを停止して起動する

ElasticIPアドレスの関連付けは解除されない。EC2インスタンスは稼働するホストが変わる。

・スナップショットの経由方法

EC2 APIを経由することで利用可能。

## SAA#26

・プロビジョンドIOPS

継続的なIOPSパフォーマンス、10,000IOPや160MiB/秒以上の大規模なデータベースワークロードに適している。

・署名付きURL

署名付きURLを受け取ったユーザーはオブジェクトの共有ができる

・Red shift

ビジネスインテリジェンススールと統合したスケーラブルなデータウェアハウジングソリューションを提供しているサービス

・SWF

分散するアプリケーションコンポーネントにまたがる作業のコーディネートを目的とするサービス。メディアの処理、バックエンド。ビジネスワークフローなどに適している。

・IAMロール

特定のアクセス権を持ち、AWSでん禁止・許可する操作を決めるアクセス権限ポリシーが関連づけれられている。

・ルートテーブル

インタネットへの接続を許可するパブリックサブネットには、ルートテーブルで0.0.0.0/0がインターネットゲートウェイに流れるような設定になっている

## SSA#27

・S3標準低アクセス

耐久性99.999999999%。可用性99.99%

・VPCのデフォルトセキュリティグループ

インバウンドは全て許可し、すべての発信トラフィックを許可する

・侵入テスト

事前に承認することなく、AWSインフラストラクチャに対するセキュリティ評価や侵入テストが実行できる。AuroraやEC2やRDSなど

・Direct Connect

AWSクラウドサービスを利用するのに、インターネットを塩湯する代わりの方法を提供するネットワークサービス

・ElasticCache

AWSが提供するMemcachedサーバでメモリ内キャッシュの縮小。拡張を容易にするサービス。

・ECU

EC2コンピュートユニット。異なるインスタンスタイプ間でかいはつしゃが簡単にCPU能力値を比較できるようにしたもの

・DynamoDB

NoSQLである。増え続けるデータを永続的に保持し効率的にアクセスできる。

## SSA#28

・IAMグループ

グループとユーザーの関係は多数 : 多数

・CloudFormationの利用料金

無料。

・S3へ保存したファイルを外部から取得する。

いつでもウェブのどこからでも容量に関係なくデータを保存、所得できる。

・CloudFront

エッジの場所にコンテンツをキャッシュできる。エッジの場所はDDoS攻撃からアプリケーションインフラストラクチャを保護する。

・DDoS攻撃

複数のPCから一斉にサイバー攻撃を行う。

・VPCとサブネット

各サブネットは、単一のAZにマッピングされる。デフォルトサブネットはパブリックサブネットで、メインテーブルがインターネットゲートウェイにルーティングされる。

・インターネットへ接続

ElasticIPアドレスかパブリックIPを持つ必要がある。

## SAA#29

|  署名付きURLの特徴  |
|  ----  |
|  デフォルトでは、オブジェクトの所有者のみがアクセスできる  |
|  オブジェクトの所有者は、アクセス制御で他のユーザーにアクセスできる。  |
|  署名付きURLを作成し、一時的な認証情報を付加することで、ユーザーに期限付きのURLを発行できる  |
|  署名付きURLを作成時は、ユーザーにアクセスを許可する期限を指定する  |
|  署名付きURLを受け取ったユーザーは、誰でもアクセスできるようになる  |

・リモートデスクトップ

リモートデスクトップを利用するためには、開放するポートはTCP/3389, UDP/3389。

・セキュリティグループ

VPC内のセキュリティグループは、どのトラフィックがEC2インスタンスへとEC2インスタンスから許可されるかを指定する

・DynamoDB

耐久性があり、スケーラブルで、可用性が高いデータストアをリアルタイムで提供できる。

・カスタムメトリクス

任意のメトリクスをモニタリング設定可能とするサービス。

## SAA#30

・EC2Config

ユーザー独自のWindows　AMIおよびインスタンスについては、ユーザーが最新バージョンに更新する必要がある。

・S3のライフサイクルポリシー

オブジェクトをS3 Glacierにアーカイブするか、一定期間後に削除を設定できる。これを用いてストレージコストを削減することができる。

・リージョンとAZ

リージョン内に複数のAZを用いることで、冗長なアーキテクチャとバックアップソリューションを提供できる。

・EBSスナップショット作成時の挙動

通常に読み書きすることができる。

・CloudFomationのテンプレートの総称

JSON形式によって作成されるAWSリソースの集合(構成)をスタックと呼ぶ

## SAA#31

・バケットポリシー

S3バケットのアクセスを制限するには、バケットポリシーを使用して、パブリックIPアドレスのみ許可する

・DynamoDB料金

一度分析した1時間あたりのアイテムは必要ないので、1時間ごとに新しいテーブルを作成して削除することで、ストレージコスト削減に繋がる

・停止状態のインスタンスで実行できるアクション

セキュリティグループの変更。セカンダリネットワークインターフェイスのデタッチ

## SAA#32

・シャーディング

データベースを複数のホストにまたがって分けること、大規模なデータベースをいくつかの小さなデータベースに分散する方法

・フェデレーション

複数のフェデレーションインタネットサービス間のユーザー認証連携

・データに短期間ですぐにアクセスできる必要があり、その後無制限にアーカイブする必要がある時のソリューション

S3に保存してから、長期アーカイブのためにS3Glacierに移動する

・S3標準

即時アクセスデータに適している。

・EBS

スケーリングに制限があり、すぐにアクセスできる大量のデータを保存するには理想的ではない。

・EC2インスタンスで実行されているアプリケーション情報を提供する

IAMロールを割り当てることが、最も安全な方法。

・EBSのスナップショット

完全なスナップショットを作成するためには、EC2インスタンスを停止してから行う

・ネイティブ暗号化

S3 GlacierとStorageGateway

・Route53のヘルスチェック

重み付けラウンドロビンやDNSフェールオーバーで、どのIPアドレスを解答に含めるかを判断するために使用

・重み付けラウンドロビン

クライアントからのリクエストをサーバに比率で転送する

・DNSフェールオーバー

運用しているウェブサイトを監視し、サイトがダウンした時に、訪問者を自動的にバックアップサイトへと誘導することができるようになる

・クラスタープレイスメントグループ

クタスタープレイスメントグループを用いることで、EC2インスタンス間のネットワーク遅延を最小限にすることができる

## SSA#33

・S3のオブジェクト削除

マルチオブジェクト削除(Multi-Object Delete API)を使用して、S3から多数のオブジェクトを削除できる

・DELETE API

単一のHTTPリクエストで1つのオブジェクトを削除できる

・RDS

データベースは自動的にバックアップされ、最新のバージョンに保たれる。バックアップの実行やデータベースを強化するソフトウェアのパッチ運用などの一般的な管理タスクが自動化される。

・グローバルセカンダリインデックス

インデックスにまたがるクエリが、全てのパーティションにまたがる。

・CloudWatchの保管期間

メトリクスのデータ保管期間は15ヶ月。

・EC2のインスタンスタイプ

定常パフォーマンス(M3, C3, R3)とバーストパフォーマンスインスタンス(T2)

## SSA#34

・ELBのSSL証明書

フロントエンドリスナーにHTTPSかSSLを使用する場合、ロードバランサーにSSL証明書をインストールする必要がある。

・SQSのスタンドキュー

少なくとも1回のメッセージ配信をサポートする、できる限りメッセージの順序を保持する。

・S3の静的ウェブサイトのホスティング

データを保存するために耐久性のあるインフラを提供。

・ヘルスチェック

ELBが異常と判断したインスタンスにはトラフィックの送信が停止される。

・aws:SourceIp

IAMに関して、コンソールの利用を指定のIPアドレスだけに絞りたい場合に利用。

・Oracleのライセンス

自分のライセンス(BYOL)を使用して、RDSでOracleのデプロイメントを実行できる。ライセンス込みはお客様が使用できるようにしたもの。

## SSA#35

・EBSのスナップショット

初回は安全バックアップ。2回目以降は増分バックアップ。

・シングルAZ DBインスタンス

自動バックアップ処理中もDBスナップショット処理中もI/Oフリーズが短時間発生する。

・SAML

オンプレミスのLDAPディレクトリサービスとAWSのIAMを統合するためのサービス。

・ヘルスチェックのよるデフォルトの監視間隔

Route53は30秒。ELBも30秒。

・Aレコード

ドメイン名やホスト名が参照するIPアドレスの指定に使用するレコード。

・zone apexでエイリアスレコードを作成

CNAMEでは作成できない。

・CNAMEレコード

Aレコードの別名を定義する。

## SSA#36

・EC2インスタンスの特徴

ElasticIPアドレスはアカウント1つ割り当ててから、それをインスタンスかネットワークインターフェースに関連付け流。インスタンスが再起動しても、インスタンスストア上のデータは維持される。インスタンスストアはルートデバイスとして利用できる。

・有効期限付きの署名URL

他のサイトからのアクセスを禁止するひつお湯があるため、パブリックアクセスを削除し、サイト訪問者のみがS3にあるファイルをダウンロードできるようになる。

・EC2インスタンスのキープアライブ設定

ロードバランサがバックエンドインスタンスへの接続を再利用でき、CPU使用率が削減になる。

・加重ルーティングポリシー

指定した比率で複数のリソースにトラフィックをルーティングする

・位置情報ルーティングポリシー

ユーザーの位置情報に基づいてトラフィックをルーティングする

・複数値解答ルーティングポリシー

あとランダムに選ばれた最大8つの正常なレコードを持つDNSクエリにRoute53を応答させる。

・スポットインスタンス

アプリケーションを実行する時間に柔軟性がある場合、やアプリケーションを中断できる場合に費用効率が高い選択肢。

## SAA#37

・SNSとSQS

SNSはメッセージを公開でき、SQSはメッセージを適切な宛先によって参照される。

・AWS Glue

ETLサービス。企業内に存在する複数のシステムからデータを抽出し、抽出したデータを変換／加工した上でデータウェアハウス等へ渡す処理。

・APIGatewayとLambda

単一のインスタンスでは高可用性を提供できる

・RDSのパフォーマンス向上

パフォーマンスを向上させるには、リードレプリカとキャッシュが有効的。

・CloudFrontがコンテンツをユーザーに配信

最初のバイトが到着した直後に、CloudFrontはそのファイルをユーザーに転送し始める。そのファイルに対する次回のリクエストに備えて、そのファイルをエッジロケーションにキャッシュする。

## SAA#38

・ELBのタイムアウト値

1〜3600秒まで柔軟に変更できる。

・ElasticBeanstalk

自動的に容量のプロビジョニング、負荷分散、AutoScaling、アプリケーション状態モニタリングのデプロイの詳細を処理する。

・ルーティングテーブル

データの流れを制御できる。

・Blue・Greenデプロイ

現状の本番環境から新しい本番環境に切り替え

・SSDベースのインスタンスストアボリューム

書き込みは160万のIOPSを実現できる

## SAA#39

・InnoDB

RDSのストレージエンジンで、自動バックアップとDBスナップショットを有効化できる。

・リージョンあたりのVPCのデフォルト数

リージョンあたりのVPCのデフォルト数は最大5つ。

・Route53の異常時の動作

異常と判断した対象のIPアドレスをクエリ結果として返さない。全ての異常の場合はIPアドレスを返す

・EBSのスナップショット

EBSはAZに固有であり、異なるAZに移動できないため、スナップショットを使用してバックアップを取る。

・プライマリネットワークインターフェース

インスタンス動作中や停止中にプライマリネットワークインターフェースをくり話すことはできない。

・IAMグループ

IAMユーザーの集合。

・FEDERATEDストレージ

リモートのMYSQLデータベースのデータにアクセスできる。RDSではサポートされていない

・CloudFormation

デフォルトではエラー時のロールバックが有効になっており、エラーが発生するまでにスタックに正常に作成した全てのAWSリソースは削除される。スタックで作成される全てのAWSリソースが削除される

・S3バケットのライフサイクルポリシー

必要とされるまでトラブルシューティングのために最初にS3に保存し、その後長期的に低コストのアーカイブのためにS3 Glacierに移動させる

・Route53やELBのHTTP応答コード

Route53は、定常は200番台と300番台。ELBは200のみ正常であり、他の200番台と300番台が異常。

・aws:UserAgent

APIの呼び出しをクライアントアプリケーションによって利用を絞る場合に使用する。

## SAA#41

・デフォルトサブネットのネットマスクは常に/20。VPC内の各AZに1つ作成される。

・スループット最適化HDD

最大スループット・ボリュームは1,000MiB/sであり、ログデータを処理するのに適している。

・証跡を全てのリージョンに適応する

ベストプラクティスにて、使用するAWSパーティション内の全てのリージョンに提要される証跡を作成する。全てのリージョンの殻のイベントをすぐに受信できる。

・ALB

可用性と拡張性に優れている。バックエンドにAutoScalingを関連付けして、需要に応じてスケーリングできる

・DeletionPolicy

Retainを指定することでCloudFormationはスタックを削除する際、リソースやコンテンツを削除せず保持する。

・冗長化

システムに何かしらの障害が発生した際に備えて、予備の設置やサブシステムなどを運用しておくこと。

・インスタンスのテナント属性

|  状態  |  値  |
|  ----  |  ----  |
|  default  |  インスタンスは共有するハードウェアで実行される  |
|  Dedicated  |  インスタンスはシングルテナントのハードウェアで実行される。  |
|  host  |  インスタンスはDedicatedHostで実行される  |

・ElasticIPアドレス

静的IPv4アドレス。インターネットからアクセス可能なパブリックIPv4アドレス。インスタンスへ割り当てる場合に必要なIPアドレス。

・Elastic Beanstalk

言語およびDockerを使用して開発されたウェブアプリケーションをApache,Nginx,Passenger,IISなど使い慣れたサーバーでデプロイやスケーリングするためのサービス。

・Data Pipeline

AWSのコンピューティングサービスやストレージサービス、オンプレミスのデータソース間で信頼性の高いデータ処理や移動を支援する。

・CodeDeploy

Ec2インスタンスやオンプレミス、サーバーレスLambda関数やECSサービスに対するアプリケーションのでうろいを自動化する

インスタンスメタデータ

IPアドレスを含むインスタンスに関わる情報を確認できる。

・Auto　Scalingのライフサイクル

インスタンス起動・Pending 起動完了・InService インスタンス削除Terminationg 削除完了・Teminated

・EC2使用状況レポート

EC2インスタンスの使用状況及びリザーブドインスタンスの使用量を分籍できるレポートツール

## SAA#43

・OpsWork

Chefを実行するとその手順通りに自動構築してデプロイするサービス。

・Instance　Store-Backed AMIとInstance　EBS-Backed AMI

Instance　Store-Backed Linux AMIからInstance　EBS-Backed Linux AMIに変換できる。変換する際はEBSを準備して、元のインスタンスストアのルートボリュームと同じサイズを用意する。

・Amazon EBS-Backed

OSがインストールされるルートボリュームがEBS上

・Instance Store-Backed

OSがインストールされるルートボリュームがインスタンスストア上（物理ホストのローカルディスク）

・フェイルオーバー機能を確実の動作するようにする

ネットワークインターフェースの受信トラフィックに対してセカンダリプライベートIPv4を使用する。

・フェイルオーバー

稼働中のシステムで問題が生じてシステムやサーバーが停止してしまった際に、自動的に待機システムに切り替える仕組み

・RDSのバックアップ

S3へファイルレベルのバックアップとRDSの自動バックアップを満たすことが必須

・RMANを使用する際の注意

データベースにEC2でホストする必要がある。

・オプティミスティックロック

更新・削除しているクライアント側の項目が、DynamoDBの項目と同じになるようにする方法。データベースの書き込みは、他のユーザーの書き込みによって上書きされないように保護される。

・ペシミスティックロック

レコードの同時更新が起こらないようにする。操作中は別のユーザーに進行中であることが連絡される

・起動許可

|  起動許可  |  説明  |
|  ----  |  ----  |
|  パブリック  |  全てのAWSアカウントに起動許可を与える  |
|  明示的  |  特定のAWSアカウントに起動許可を与える  |
|  暗示的  |  AMIの暗示的起動許可がある |

## SAA#44

・CloudFront+S3

配信する必要がある場合、CloudFrontを使用。CloudFront経由で、限られたユーザーのみS3からコンテンツを取得できるようにするために、CloudFront用の署名付きURLを発行する必要がある。

・インスタンスからインターネットへの接続

1. インスタンス
2. セキュリティグループ
3. ネットワークACL
4. ルーティング
5. インターネットゲートウェイ
6. インターネット

・RDS DBインスタンスのストレージサイズの変更

使用するストレージスペースを減らすことはできない。ストレージスペースが少ないRDSインスタンスを新たに作成して移行してから使用する。

・SWF

拡張性と障害対策に優れたアプリケーションを構築するサービス。完全マネージド型のワークフロー

・ルートデバイスストレージ

2種類あり、EBSとStore-Backed。Store-BackedはAMIから起動されるインスタンスのルートデバイスが、S3に格納されたテンプレートから作成されるインスタンスストアボリューム。

・ルートデバイスのストレージ

EBS-backedインスタンスは停止と再起動ができる。Store-Backedはできない。EBS-backedはインスタンス停止中に、インスタンスタイプ、カーネル、RAMディクス、ユーザーデータを変更できる。

## SAA#45

・DBインスタンスのスタンバイ

マルチAZ配置したスタンバイはどの時点においても、読み込みと書き込みをサポートしていない。プライマリはどちらも実行できる。

|  ----  |  ElasticIPアドレス  |  パブリックIPアドレス  |
|  ----  |  ----  |  ----  |
|  IPアドレスの種類  |  固定IPアドレス  |  動的IPアドレス  |
|  発信先  |  外部向け  |  外部向け  |

・フォールトトレラント

システムの一部に問題が生じても全体が機能停止せず、動作し続けるようにシステムを設計する

・データとメディアの安全な廃棄

クラウド内のデータの削除をするとき、物理メディアは破棄せず。ストレージブロックが未割り当てとしてマークされる。

・CloudWatchのモニタリングタイプ

基本モニタリングは5分間隔。詳細モニタリングは1分間隔

・AMIとスナップショット

スナップショットはEBSからデータのコピーをとってS3上に保管する。インスタンスを構成する情報は含まない。スナップショット中のデータを利用するには、EBSを作成する。

## SAA#46

・SQS

オペレーションやイベントの順序が重要である場合に使用。

・SNS

マイクロサービス、分散型システムなど効果陽性で耐久性に優れた完全マネージド型サービス

・ルートデバイスのストレージ

EBSインスタンスのルートボリュームはインスタンスストレージを呈してしても、保持される。

・バックアップしたデータを戻す

スナップショットを使用する。自動バックアップ機能は最大で35日。

・リードレプリカ

データベースの負荷分散をする

・ステートレス

システムが現在の状態を表すデータなどを保持せず、入力の内容によって出力が決定される。

・ネットワークACL

ステートレスである。

・インスタンスストアの存続期間

EBSインスタンスが停止している時、インスタンスボリューム上のデータはデータが削除され、アクセスできない。

## SSA#47

・サポートされるインスタンスタイプ

暗号化されたEBSをアタッチすることはできない。

・CloudFrontの価格クラス

価格クラスを使うことで利用料金が減る。ただし、エッジロケーションのうち高コストのものをディストリビューションから除外する。

・エッジロケーション

AZと異なるデータセンター。DNSやコンテンツ配信サービスが利用されている。

・VPC

複数のAZにまたがるVPCを作成できる。

・DeketeOnTermination

DeketeOnTerminationをfalseにすることにより、インスタンスを削除ルートボリュームを保持することができる。

・EC2インスタンスのアクセス制御

IAMはインスタンス内のユーザー制御はできない。

## SSA#48

・EC2インスタンスストア

頻繁に変更される情報(バッファ、キャッシュ、スクラッチデータなど)の一時ストレージに最適。

・CloudSearch

ウェブサイト、アプリケーション向けの検索機能を実装できるサービス。

・タグの制限

aws: プレフィックはキーにも値にも使用してはいけない。

・EBS Encryption

EBSの保管と転送時に暗号化できる。またスナップショット時も暗号化される。

・OpeWorks

ChefやPuppetのマネージドインスタンスを利用できる構成管理サービス。ChefやPuppetはサーバー構成を自動化できるようにするためのオートメーションサービス。

・ルートデバイスタイプの値

ebsの場合、EBS-Backed AMI。instance storeの場合,Instance store-Backedインスタンス。

・レイテンシーに基づくルーティング

霊天使の方が、低い場合、Route53はエンドユーザーのリクエストに対して、近いEC2データセンターのロードバランサーのIPアドレスを返す。

## SAA#49

・IAMのユーザー名

ユーザー名を変更するためにはCLI、AWS APIを用いる必要がある。コンソールでは変更できない。

・ディザスタリカバリ

災害復旧

・マルチサイトソリューション

複数のデータセンター拠点やクラウドサービス間でサイトを分散すること。

・コールドスタンバイソリューション

機器は用意されているが、電源が入っていない状態

・ウォームスタンバイソリューション

サーバやネットワーク機器を冗長化した予備システムへの切り替え方式。

・CloudTrail

ログはS3バケットとCoudWatchLogsロググループに配信される。

・EBS-backedインスタンスとEC2instance store-backed

EBS-backedインスタンスは停止できる。EC2instance store-backedは停止できない。EBS-backed インスタンスを停止すると。running->stopping->stoppedを経る。停止後もデータは消えない。

・EC2のモニタリング

CloudWatchエージェントを利用することで、メモリの使用量、ディスクスワップの使用量、ページファイルの使用状況、ログの回収をモニタリングできる。

・EBSの暗号化

EC2インスタンスをホストするサーバーで暗号化が行われる。

・ボリューム割引

サービスを多く使うとEC2やS3のようないくつかのサービスは低価格が適応される

## SSA#50

・EBSの暗号化

暗号化されていないEBSボリュームを設定値を変更することで暗号化することはできない

・Snowmobile

非常に大量のデータをAWSに転送するために使用できるエクサバイト規模のデータ転送サービス。

・Migration Hub

複数のソリューション間におけるアプリケーション移行の進行状況を1つの場所で追跡するサービス。

・VPC

従来のデータセンターで構成された仮装ネットワークと同等なサービスを実現可能。

・ServiceBus

支えたいメッセージを確実に相手に伝えるサービス。

・DynamoDBの制限

DynamoDBに格納できるテーブルサイズに制限はない。

・SQS

アプリケーションのコンポーネントを分離するための単純で費用対効果の高い方法を提供DBの確認応答を待機しないことができる。

|  AutoScalingのオプション  |  動的なスケーリング  |  スケジュールに基づくスケーリング  |  主導スケーリング  |
|  ----  |  ----  |  ----  |  ----  |
|  ----  |  需要に応じてスケールする方法を定義する  |  日付と時間に基づいて実行  |  手動で変更  |

## SSA#51

・VPCとサブネット

1つのサブネットが複数のAZにまたがることはできない。

・EBSの暗号化

暗号化されたボリュームでは暗号化されていないボリュームと同じIOPSぱロマンスが期待できる。

・標準のメトリクス

CPU使用量、ネットワーク使用量、ディスクパフォマンス、ディスクのモニタリングができる。

・S3のアクセス

管理アカウントの種勇者は、メンバーアカウントの所有者に属するデータにアクセスできない。

・インスタンスの起動時間

EBS-BackedSMIはEC2Instancestore-BackedAMIよりも早く起動する。

## SAA#52

・DedicatedHost

サーバーにバインドされた既存のソフトウェアライセンスを利用でき、コスト削減になる。

・AMIの保存ストレージ

AMIの全ての部分がS3に保存される。

・ブロックデバイスマッピング

インスタンスに接続できる外部のブロックデバイスは、リモートストレージデバイスのEBSボリューム。

・カスタマーゲートウェイ

作業者側のアンカー。VPCのVPN接続では、データセンターをVPC仮装プライベートクラウドにリンクする。

・ElasticBeanstalk

新しいプラットフォームバージョンにを定期的にリリースして、新しいプラットフォームバージョンは、既存のソフトウェアコンポーネントへの更新と、新しい機能と設定オプションのサポートを提供。

## SSA#53

インスタンスサイズの変更

EBSボリュームの場合、インスタンスタイプを変更するだけで、インスタンスサイズを変更できる。インスタンスストアボリュームの場合変更できない。

・SSL

SSLは転送中のデータwお見られないように保護する。

・VPCフローログ

VPC、サブネット、ネットワークインターフェースのフローログを作成できる。

・カスタマゲートウェイ

静的なグローバルIPアドレスと、仮装プライベートゲートウェイが喪tうグローバルIPアドレスへ到達可能な系よを要している必要がある。

・RDS

RDSでは、DBインスタンスへのOSアクセスはできない。マネージド型サービスを実現するため。

## SSA#54

・KinesisDataFirehose

分析用途。暗号化。

・KinesisDataStreams

次々上がってくるデータの内容をリアルタイムで加工、表示する。

・ElasticIPアドレスの割り当て

CloudFormationを用いて、インスタンスのタイプやElasticIpアドレスを指定できる。

・Route53のALIASレコード

DNSの登録はCNAMEレコードかALIASレコードを使用する。ALIASレコードの方がパフォーマンスが良い。

・EBSボリュームの種類

スループット最適化HDDボリュームはスループットでパフォーマンスを示す、低コストの次期ストレージに使用できる。アクセスが頻繁なデータをサポートする。

・スループット

単位時間あたりの処理できるデータ量。

・サブネットの必要個数

プライベートサブネットとパブリックサブネットをAZごとに作成する必要がある。

## SSA#55

・ローカルストレージ

現在操作している手元のコンピュータに内蔵あるいは直に繋がれたハードディスクなどのストレージ

・ElasticCache

RDSから頻繁にアクセスされるデータをキャッシュすることで、低廉氏のアクセスを実現し、RDSの負荷を軽減することができる。

・Auto ScalingとALB

アプリケーションのスケーリングを支援するために使用する。

・EC2Config

インスタンスが起動し、起動時にタスクを実行した時やインスタンス他が開始か停止するたびに起動する。各種タスクを実行するために使用。

・AMI

AMIを一般公開することはできるが、製品こどがある場合や暗号化されたボリュームスナップショットが含まれている場合、公開できない。

・ターゲットグループへターゲットを登録

オンラインでELBにインスタンスを登録することができる。ヘルスチェックに合格するとすぐに、ルーティングを開始する

・S3

静的ウェブサイトをS3でホスティングできる。

## SSA#56

・SQS

アプリケーションのコンポーネントを分離するために使用。データベースへの書き込み負荷を変化つかし、データベースの確認応答を待機しないことを実現する。

・VPCピアリング

VPCごとに保持できる実行中や保留中のVPCピア接続には上限がある。IPv4かIPv6CIDRブロックが一致か重複するVPC間でVPCピアリング接続を作成できないリージョン間VPCピアリング接続の最大送信数は1,500バイト。

・VPCピアリング

異なるVPCを接続することができる。複数のAWSのコンテンツをまとめたり、複数のAWS間で通信が行うことができる。

・リードレプリカ

リードレプリカをオフロードにして、スループットと応答性を改善できる。古いデータを必要とするSELECTクエリをリードレプリカにオフロードすることでパフォーマンスを上げる。

・社外秘のデータを保護

S3上に社外秘のデータを保管する場合、IAMポリシー、バケットポリシー、アクセスコントロールリスト(ACL)、サーバー側の暗号化を用いて管理する

・プライベートIPアドレス

古いインスタンスと新しいインスタンスに同じプライベートIPアドレスを設置することはできない。

・KMS

暗号化キーを作成・管理。AWSサービスやアプリで使用するキーの一元管理が可能

## SSA#57

・ブロードキャストアドレス

2進数に変換後、下4桁を1に変換する。

・ネットワークアドレス

2進数に変換後、下4桁を0に変換する。

・ElasticBeanstalk

ウェブアプリケーションサービスやサービスをサーバーでデプロイとスケーリングするためのサービス。

・VPCのリアリング接続

VPCAとVPCBがピアリング接続、VPCAとVPCCピアリング接続した場合、VPCBとVPCCはピアリング接続しない

・ピアリング接続

インターネットゲートウェイは不要。

・ロードバランサの認識時間

VPCインスタンスを停止して起動した場合、インスタンスが再起動されたことをロードバランサが認識するまで時間がかかることがある。

・RDSのデータ転送時の料金

プライマリとスタンバイ間でデータをレプリケーションする際には料金は発生しない。DBインスタンスの受信と送信におけるインターネットのデータ転送は同様に課金される。

## SSA#58

・専有テナント属性

専有テナント属性があるコンバーティブルリザーブドインスタンスを購入してから、インスタンスのテナンシーを変更することはできる。

・テナンシー

EC2インスタンスが物理ハードウェアに分散される方法。

・　Kinesis Data Firehose

アプリケーションの構築なしに、S3やRedshiftやElasticSearchに自動的にデータを収集・格納できる。自動的に拡張も可。

・SQS

2種類のメッセージキーを利用できる。標準キーは配信は少なくとも1回行われる。FIFOはメッセージが送信される順序のとおりに1回のみ確実に処理される。

・S3バケットに保存される画像を安全にアクセスする

STSを使用して、一時的セキュリティ認証を取得する。

・VPCピアリング接続の暗号化

暗号化されない・ピアリング接続されたVPC内のインスタンス間のトラフィックはプライベートであり、隔離されている。

・VPCピアリング接続

2つのVPC間でプライベートなトラフィックのルーティングを可能にする。

## SAA#59

・AutoScaling

CPU使用率がしきい値を超えた時、EC2インスタンスを起動する。下回った時、EC2インスタンスを削除する。

・フルテーブルスキャン

データベースで行われるテーブルの読み取り方法、全てスキャンする。

・フェイルオーバーの条件

プライマリのAZの可用性喪失。プライマリに対するネットっワーク接続の喪失。プライマリ上でのコンピュートユニット障害。プライマリでのストレージ不良。

・S3のデータ破損の検出方法

Content-MD5チェックサムと周期的な冗長性チェックを組み合わせて発見する。

・マルチパートアップロード

単一のオブジェクトをパートのセットとしてアップロードすることができる。そのため、アップロードが失敗しても、途中から送信できる。

## SSA#60

・AWSアカウントとIAMユーザー

AWSアカウントのサービスやリソースにアクセスする必要があるエンティティごとに、個別にIAMユーザーを作成する。

・IAMユーザーによるAPIコール

APIコールを正常に実行するためにはユーザーのアクセスキーのセットを作成する必要がある。

・NATゲートウェイ

パブリックサブネットにNATゲートウェイを作成する。全てのプライベートサブネットのインターネットトラフィックをインターネットゲートウェイ経由でルーティングする。

・マルチリージョン

複数のリージョンにまたがってシステムを配置する。

・Route53

トラフィックを複数のリージョンに分散できる

・RDBのDBインスタンスの請求

DBインスタンスにプロビジョニングしたストレージを変更すると、比例配分で請求される。

## SSA#61

・Route53のDNSフェールオーバー

アクセスが失敗した時、Sorry Pageを表示させる。

・Proxyプロトコル

ロードバランサーの接続で使用されるプロトコル。

・SQS

複雑な条件分岐・リトライ条件などがないシンプルな並列処理の場合、SQSが有効。

・SWF

複雑なバッチ処理を実行する場合、SWFが有効。

・ElasticIPアドレス

インターネットへ接続ができる、既存のインスタンスと同じ設定で同じサブネットへインスタンスを作成した場合、ElasticIPを割り当てる必要がある。

・RDSのDBインスタンスをマルチAZ配置した場合のメリット

メンテナンスウィンドウの期間中も利用可能にする。1つのデータセンターに障害が発生した場合m同じ地域の他のデータセンターで自動的にフェイルオーバーする。

・ELBでクロスゾーンに負荷分散

AZ内のインスタンスに数の偏りがあると均等に負荷分散できないため、クロスゾーン負荷分散を設定することで、全インスタンスに均等に振り分ける。

・S3

バケット内のオブジェクトに制限はない。サイズには制限がある。5TBまで。

## SAA#62

・IDフェデレーション

ユーザー認証とリソースアクセス認証のために必要な情報伝達を目的とした信頼連携システム。

・転送中のデータの保護

IPSecは、IPプロトコルスタックを拡張するプロトコル。安全に通信を行うことができる。SSL/TLSはセッションレイヤーで動作する。

・ALB

着信リクエストのパスに基づいて、トラフィックをサービスにルーティングできる

・スナップショット

スナップショットはスナップショットが作成されたリージョンに再現される。

・Instance Store-Backed AMIをEBS-backed AMIに変換

EBS-backed AMIに変換をバンドルするのに使用したX.509プライベートキーをインスタンスにアップロードする。

・インスタンスストアボリューム

インスタンスの再起動や停止をするとインスタンスストアボリュームのデータは削除されて、インスタンスは新しいホストで実行される。

## SSA#63

・DynamoDBでのデータ伝送中のデータ保護

HTTPoverSSL/TLSを使用する。

・S3の偶発的なデータ損失を防止して復旧させる方法

オブジェクトの削除に他要素認証を要求することができるMFADeleteを使用することでアクセスを特権ユーザーのみにする

・RDSリソースの暗号化

RDSのDBインスタンスの暗号化は、DBインスタンスの作成時にのみ有効にできる。

・Lambda

新しいオブジェクトがアップロードされた時にS3イベント通知を設定できる。

## SSA#64

・SSL/TLS

RDS MYSQLインスタンスとMicrosoft SQLインスタンスへの接続をサポートする。クライアントとサーバー間の通信チャンネルのネイティブ暗号化とデータ製合成認証が提供されている。

・侵害と迷惑行為

AWSはアクセスログ、IPトラフィックログなどの情報を取得していないため、過去に遡って情報提供できない。調査は自分で行う。

・BIツール

事業の意思決定に用いられる知見とデータ収集・分析・配布を意味する。

・S3の暗号化

S3バケットが保存される際に、暗号化する場合はS3バケットのデフォルト暗号化を有効にする。暗号化はSSEーS3かKMSを使用。

・Organization

一括請求機能を使用して、複数のAWSアカウントの支払いを統合できる。メンバーアカウントで発生したAWS料金を的まて確認できる。

## SSA#65

・可用性の向上

複数のAZを用いる。失われたキャパシティーを置き換えるAutoScalingを用いる。




















