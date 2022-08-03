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












