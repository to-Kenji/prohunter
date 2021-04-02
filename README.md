# [プロはん養成所 prohuntogether.com](https://prohuntogether.com)
# サービス概要

世界中で大人気の日本が誇る名作ゲームシーリズ、
「モンスターハンターワールド　アイスボーン」に特化した、  
***「もっと上手くなりたいプレイヤーのための技術共有サービス」です。***  
  
## 使用技術
- Ruby 2.7.1
- Ruby on Rails 6.0.3.4
- Javascript
- jQuery
- Bootstrap 4.6.0
- MariaDB 10.5.8
- Docker
- AWS(VPC, EC2, RDS, Route53, IAM, S3, CloudFront, ALB)
- CircleCI(テスト、コード解析の自動化)
- RSpec(単体テスト、統合テスト)
- RuboCop
- Nginx
- Puma
- Capistrano
  
## インフラ構成図
![Untitled Diagram](https://user-images.githubusercontent.com/70895253/112917093-eae6ed80-913c-11eb-9aaf-d70accc5e32a.png)

## 機能一覧
- ユーザー登録、ログイン、ログアウト機能(devise)
- ユーザー編集機能
  - プロフィール画像投稿、削除機能(CarrierWave, MiniMagick)
- 投稿機能
  - youtube動画の埋め込み機能
- いいね機能(Ajax)
- お気に入り機能(Ajax)
  - お気に入りランキング機能
- フォロー機能(Ajax)
- コメント機能(Ajax)
- ページネーション機能(kaminari, ajax)
- 検索機能(ransack)
  
## まずはこのゲームについて簡単にご説明します。
プレイヤーは１人のハンターとなり、そのハンターを操作しながら数々のモンスターを狩るアクションゲームです。  
ハンターが使用できる武器には様々な種類があり、それぞれに違った特性やアクションが存在します。  
またモンスターも多種多様であり、何度挑戦しても中々倒せない強力なモンスターも多く存在します。  
  
このゲームはオンライン通信で世界中のプレイヤーと協力して狩りをすることが可能で、  
初心者から大会に出場するような上級者まで、多くのプレイヤーが一緒に楽しむことができます。  
  
## なぜこのサービスが必要なのか？
***結論から言えば、「より上達し、このゲームを楽しむため」です。***     
モンスター毎には固有の特性があるため、それに応じて **「必要な対策」や「効果的な作戦」等があります。**  
オンラインで強力なモンスターの狩りをする際は、顔も知らない仲間たちと意思疎通を図って立ち向かうことが求められ、また一定回数以上ハンターが力尽きてしまうと、そこで狩りは失敗となってしまいます。  
**オンラインにおいては、前述した「対策や作戦」などの知識があるかどうかや、「プレイの上手さ」次第で、「周りの人に迷惑をかけてしまった」という状況を引き起こすことがあります。**  
普通なら気にする必要もないことなのですが、中にはそういったプレイヤーに対して心無い言葉を投げる者も多く存在するのが現実です。  
新規参入者やアクションが不得意な人がゲームを純粋に楽しめなくなってしまうのは、非常に残念なことだと感じます。  
そういったプレイヤーの為に、**上手くなるための秘訣を提供する場**を作ることで、よりこのゲームを楽しめるようサポートできます。  
また中級者以上のプレイヤーにとっても、さらなるスキルアップの為の情報源として活用できます。  
上級者の間では「タイムアタック」と言って、いかに早くモンスターを倒すかを競うことが流行しており、youtube動画なども数多く投稿されています。そういったプレイヤー向けにも、非常に有益な情報提供元となります。
また最近ではe-sportsなどの「競技としてのゲーム」が流行しており、カプコンが主催しているこのゲームの大会も存在するため、そういった競技への対策としても利用できます。
  
初心者から上級者までこのゲームをより純粋に楽しむためには、そのような情報共有の場が非常に効果的であり、また**そういった目的に特化したサービスが他に存在しない**ことから、このサービスを作ろうという考えに至りました。

## このサイトで何ができるのか
#### 1. 「学ぶ」
「自分が使っている武器」と、「どのモンスターについて知りたいのか」を選択することで、記事を絞り込むことができます。またキーワード検索で絞り込むことも可能です。  
それぞれの記事では、投稿者が得たスキルを**動画付きで学ぶ**ことができます。    
  
![閲覧](https://user-images.githubusercontent.com/70895253/111021337-d8677700-840e-11eb-9a87-dca680610dd1.gif)
  
  
#### 2. 「フォロー、ストックする」
気に入ったユーザーは「フォロー」することができ、気に入った投稿は「お気に入り」としてストックすることができます。  
フォロー機能によって気に入ったユーザーの投稿を簡単に追うことができます。  
有益だと感じた記事はお気に入りに追加しておくことで、再度見直したい時に簡単にその記事に辿り着くことができます。  
  
![tabu](https://user-images.githubusercontent.com/70895253/111021196-0dbf9500-840e-11eb-8f91-57b81c49e497.gif)
  
#### 3. 「投稿する」
自分が持つ知識を記事にしてシェアすることができます。
記事にはyoutubeの動画を埋め込むことが可能なので、自分が実際にプレイしている姿を公開できます。  
多くのユーザーが自分の投稿をお気に入りにすることで、ランキングに載ることができます。
  
<img width="1265" alt="投稿画面" src="https://user-images.githubusercontent.com/70895253/111021273-81fa3880-840e-11eb-812f-cb6c359438c7.png">
  
## アピールポイント
- 「実際に自分でリリースするとしたら」という観点で、**ユーザーからの一定以上且つ長期的な需要がある**と考えられる題材を選びました。（このゲームはシリーズものなので、今後発売されるシリーズに合わせて使い回すことが可能です。）
- 実務経験が無い事の差を少しでも縮めるため、AWSやDockerなどの現在主流となっているモダンな技術を採用しました。
- 常にユーザー視点に立って、**直感的で且つ見やすいUI**を意識しました。（レスポンシブにも対応）
- パソコンでの記事閲覧時は、文章と動画を縦ではなく横に配置することで、両者を並行して見ながら学習できるようにしました。
- youtube動画には、「ブラウザのURL」と「動画の共有タブにある埋め込みリンク」が存在し、ブラウザのURLだと通常は埋め込みとしては機能しません。インスタンスメソッドを定義し、DBへの保存時にそれを実行することで、ユーザーがどちらのリンクを使用しても正しく埋め込みとして機能するように工夫しました。**こちらは恐縮ながらQiitaに投稿しました**。[こちら](https://qiita.com/TO-TO/items/a81d55908e99ba493d99)
- 保守管理のしやすさの為、**機能ごとの関心を分離**して細かくコンポーネント化することを意識しました。
