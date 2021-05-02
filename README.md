# [プロはん養成所 prohuntogether.com](https://prohuntogether.com)
# サービス概要
![ローンチ](https://user-images.githubusercontent.com/70895253/116805074-c082b880-ab5e-11eb-864c-e3db86095edf.jpg)
  
世界中で大人気の日本が誇る名作ゲームシーリズ、
「モンスターハンターワールド　アイスボーン」に特化した、  
***「もっと上手くなりたいプレイヤーのための技術共有サービス」です。***  
  
  ![d52ebad7a66aa7e384f8a59e1428e03f](https://user-images.githubusercontent.com/70895253/116805066-b2cd3300-ab5e-11eb-96fa-731ec2ddbaae.gif)
  
## 使用技術
- Ruby 2.7.1
- Ruby on Rails 6.0.3.4
- Javascript
- jQuery
- Bootstrap 4.6.0
- MariaDB 10.5.8
- Docker
- AWS(VPC, EC2, RDS, Route53, IAM, S3, CloudFront, ALB)
- CircleCI(自動ビルド、テスト、デプロイ)
- RSpec(単体テスト、統合テスト)
- RuboCop
- Nginx
- Puma
- Capistrano
  
## インフラ構成図
![Untitled Diagram (1)](https://user-images.githubusercontent.com/70895253/113817222-f7102200-97b0-11eb-88bb-7260eab0ad38.png)

## アピールポイント
- 「実際に自分でリリースするとしたら」という観点で、**ユーザーからの一定以上且つ長期的な需要がある**と考えられる題材を選びました。（このゲームはシリーズものなので、今後発売されるシリーズに合わせて使い回すことが可能です。）
- AWS、Docker、CircleCIなどの現在主流となっている**モダンな技術**を採用しました。
- **セキュリティ面も考慮**し、アプリケーションを配置しているEC2インスタンスには、セキュリティグループによりローカルホストのSSHしか許可しないインバウンドルールを設定しています。CircleCIでの自動デプロイ時のみ、AWS-CLIを用いてCircleCIコンテナのIPアドレスを許可するルールを追加し、コンテナがEC2にSSHできるようにします。デプロイが完了したら、逆に追加したルールを削除するようにすることで、よりクローズされたセキュアな空間を実現できました。**Qiitaでアウトプットしています。**[[Rails6] CircleCI + CapistranoでIP制限のあるEC2への自動デプロイを実装した](https://qiita.com/TO-TO/items/b074ebf82f150abd6c77)
- 常にユーザー視点に立って、**直感的で且つ見やすいUI**を意識しました。（レスポンシブにも対応）
- パソコンでの記事閲覧時は、文章と動画を縦ではなく横に配置することで、両者を並行して見ながら学習できるようにしました。
- youtube動画には、「ブラウザのURL」と「動画の共有タブにある埋め込みリンク」が存在し、ブラウザのURLだと通常は埋め込みとしては機能しません。インスタンスメソッドを定義し、DBへの保存時にそれを実行することで、ユーザーがどちらのリンクを使用しても正しく埋め込みとして機能するように工夫しました。**こちらは恐縮ながらQiitaに投稿しました**。[こちら](https://qiita.com/TO-TO/items/a81d55908e99ba493d99)
- 保守管理のしやすさの為、**機能ごとの関心を分離**して細かくコンポーネント化することを意識しました。
  
## まずはこのゲームについて簡単にご説明します。
プレイヤーは１人のハンターとなり、そのハンターを操作しながら数々のモンスターを狩るアクションゲームです。  
ハンターが使用できる武器には様々な種類があり、それぞれに違った特性やアクションが存在します。  
またモンスターも多種多様であり、何度挑戦しても中々倒せない強力なモンスターも多く存在します。  
  
このゲームはオンライン通信で世界中のプレイヤーと協力して狩りをすることが可能で、  
初心者から大会に出場するような上級者まで、多くのプレイヤーが一緒に楽しむことができます。  
  
## なぜこのサービスが必要なのか？
***結論から言えば、「より上達し、不快な思いをすることなくこのゲームを楽しむため」です。***     
モンスター毎には固有の特性があり、それに応じて **「必要な対策」や「効果的な作戦」等があります。**  
オンラインで強力なモンスターの狩りをする際は、顔も知らない仲間たちと意思疎通を図ることが求められ、また一定回数以上ハンターが力尽きてしまうと、そこで狩りは失敗となってしまいます。  
**オンラインにおいては、前述した「対策や作戦」などの共通認識があるかどうかや、「プレイの上手さ」次第で、「周りの人に迷惑をかけてしまった」という状況を引き起こすことがあります。**  
普通なら気にする必要もないことなのですが、中にはそういったプレイヤーに対して**心無い言葉を投げる者も多く存在する**のが現実です。  
新規参入者やアクションが不得意な人がゲームを純粋に楽しめなくなってしまうのは、非常に残念なことだと感じます。  
そういったプレイヤーの為に、**上手くなるための秘訣を提供する場**を作ることで、よりこのゲームを楽しめるようサポートできます。  
「こうしなければ勝てない。こうすることが効果的だ」とか「こんな発見をした！」といった投稿が集まることでスキルアップに繋がり、そこからユーザー同士の繋がりも生まれれば、更にこのゲームが盛り上がっていくと考えています。  
中級〜上級者の間ではいかに早くモンスターを倒すかを競うタイムアタックも流行しており、youtube動画なども数多く投稿されています。そういったプレイヤー向けにも有益な情報提供元となります。  
最近ではe-sportsなどの「競技としてのゲーム」が流行しており、カプコンが主催しているこのゲームの大会も存在するため、そういった競技への対策としても需要があると考えています。
  
**このような目的に特化したサービスが他に存在しない**ことから、このサービスを作ろうという考えに至りました。

## このサイトで何ができるのか
#### 1. 「学ぶ」
「自分が使っている武器」と、「どのモンスターについて知りたいのか」を選択することで、記事を絞り込むことができます。またキーワード検索で絞り込むことも可能です。  
それぞれの記事では、投稿者が得たスキルを**動画付きで学ぶ**ことができます。    
  
#### 2. 「フォロー、ストックする」
気に入ったユーザーは「フォロー」することができ、気に入った投稿は「お気に入り」としてストックすることができます。  
フォロー機能によって気に入ったユーザーの投稿を簡単に追うことができます。  
有益だと感じた記事はお気に入りに追加しておくことで、再度見直したい時に簡単にその記事に辿り着くことができます。  
  
#### 3. 「投稿する」
自分が持つ知識を記事にしてシェアすることができます。
記事にはyoutubeの動画を埋め込むことが可能なので、自分が実際にプレイしている姿を公開できます。  
多くのユーザーが自分の投稿をお気に入りにすることで、ランキングに載ることができます。
  
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
