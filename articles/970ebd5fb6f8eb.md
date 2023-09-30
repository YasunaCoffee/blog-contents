---
title: "AWS認定資格6冠までにやったこと全部まとめ(2022年 - 2023年)"
emoji: "👸"
type: "idea"
topics:
  - "aws"
  - "aws認定"
published: true
published_at: "2023-09-19 22:45"
---

## AWS認定6冠までの経緯 
グループ会社がAWS資格取得を奨励していたので、気になって自分も習得してみようと思ったのがきっかけです。自分の所属会社は特にAWS資格を奨励はしていなかったのですが、社内でAWSの知識が必要な場面があったりして、「AWSの基礎資格くらいの知識はほしいよね」という現状がありました。

個人的にはそんなタイミングで第一子を授かり、育休に入りました。
この仕事から離れている期間に、AWSの認定資格試験に挑戦してみようと考えました。

その結果、育休中にAWS認定資格に6つ合格することができました。
復職した現在は社内で「AWS6冠の人」と認知してもらえるようになり、AWS関連の業務を任せてもらえるようになりました。(歓喜)

初めはSAAを取得することがゴールとしていましたが、勉強を進めていくうちにAWSのサービスの幅広さとコミットした瞬間にビルドとテストまで実行する「[継続的インテグレーション(CI)](https://aws.amazon.com/jp/devops/continuous-integration/)」の面白さに惹かれました。そして現在、Foundational,Associate,Professionalあわせて6冠を取得しています。

以下では６冠を取得するまでに行ったことを取得順にご紹介していきます！

## AWS Certified Cloud Practitioner (CLF)
https://aws.amazon.com/jp/certification/certified-cloud-practitioner/?ch=tile&tile=getstarted
CLF-C01 90分 65問 
2022-04-20合格
まず試験を準備するの項目の「試験ガイド」を読みました。特にCLFは出題範囲が他の試験よりも多いので、始める前に必ず確認するようにしました。
CLF-C01という試験のバージョンは2023.9.18までなので、受けたい方は新しいバージョンの[CLF-C02の試験ガイド](https://d1.awsstatic.com/ja_JP/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Exam-Guide_C02.pdf)を読んでみると良いです。


自分は初めてのAWS資格学習で周りに詳しい人がいなかったので、手探りで学習方法を模索していました。そのため受験までに半年とかなり時間がかかってしまいました。反省点として、**受験日を設定してから勉強を始めるべきだった**ことが挙げられます。

出題範囲が広いため、深く理解しようとすると本当に時間がかかってしまい受験日が遅くなってしまいます。
ある程度リミットを決めてまずは**受験にトライしてみることが大切だと痛感**しました。

### 勉強法
- Udemy問題集を解く
 -[【CLF-C02版】これだけでOK! AWS認定クラウドプラクティショナー試験突破講座（豊富な試験問題290問付き）](https://www.udemy.com/course/ok-aws-e/)
 -[【C01&C02版】この問題だけで合格可能！AWS 認定クラウドプラクティショナー 模擬試験問題集（6回分390問）](https://www.udemy.com/course/aws-4260/)
- [AWS BlackBelt](https://aws.amazon.com/jp/events/aws-event-resource/archive/?cards.sort-by=item.additionalFields.SortDate&cards.sort-order=desc&awsf.tech-category=*all)の資料を読む

Udemy問題集を解く→分からないサービスがあればBlackBeltで調べる
を繰り返していました。

時間はかかってしまいましたが、丁寧に学習を進められたことが、後々の6冠に大きく関係してくるので、ここで理解を深められたのは自分としては良かったのかなと感じています。

## AWS Certified Solutions Architect - Associate (SAA)	
https://aws.amazon.com/jp/certification/certified-solutions-architect-associate/?ch=tile&tile=getstarted
SAA-C02 130分 65問　
2022-05-21不合格 → 2022-06-04合格

CLF取得から約1ヶ月後にSAAを受験しました。１回目の結果は不合格でした。
今回は受験日をあらかじめ設定して、自分を追い込んで学習を進めることができたのが良かったです。
１回目は不合格だったものの、十分に手応えがあったため、すぐに２回目の受験日を決めて受験を行いました。

>試験に合格できなかった場合は、不合格になった日から 14 日間経過すると、再度受験できます。受験回数には制限はありません。([試験後 AWS 認定受験者に役立つ情報と関連ポリシー](https://aws.amazon.com/jp/certification/policies/after-testing/))

上記の通り、公式によると同じ試験を受けるには最低14日間空けなければならないため、最短の日にちで受験する予定をすぐに組みました。

結果、14日間で約70点伸ばすことができて合格しました！
以下、２回目の受験までにやった勉強法をまとめています。

### 勉強法
#### 1回目受験までの学習
- Udemy問題集を解く
 -[【SAA-C03版】これだけでOK！ AWS 認定ソリューションアーキテクト – アソシエイト試験突破講座](https://www.udemy.com/course/aws-associate/)
 - [AWS BlackBelt](https://aws.amazon.com/jp/events/aws-event-resource/archive/?cards.sort-by=item.additionalFields.SortDate&cards.sort-order=desc&awsf.tech-category=*all)の資料を読む
#### 2回目受験までの学習
- SAA本を読む
　- AWS認定 アソシエイト ３資格対策
- WEB問題集を解く
　-[AWS WEB問題集で学習しよう: Cloud License](https://cloud-license.com/)
 - [AWS Certified Solutions Architect - Associate 公式練習問題集](https://explore.skillbuilder.aws/learn/course/external/view/elearning/13269/aws-certified-solutions-architect-associate-official-practice-question-set-saa-c03-japanese?saa=sec&sec=prep)

今までは本は買っていなかったのですが、不合格してすぐにSAAの本を買いました。それまではUdemyを中心に学習を進めていましたが、本を読むことによって情報が整理されて理解が良くなったと感じました。
つまづきやすいポイントも本で何度も見返して覚えられるのが良いですね。

また、公式の練習問題やWEB問題集を解いて、本番に近い形で練習することが大切でした。
1回目では本番に近い問題形式で時間を測って解く練習が足りていませんでした。

2回目でグッと点数を伸ばして合格することができたのは、「**本番と同じ形式で解く練習をする**」ことができたからかなと感じています。

### 本番で気をつけること
SAAは130分のタイムマネジメントも大切です。
すぐに分かる問題を先にこなしていき、時間がかかると思った問題にはあとで解くフラグをつけるようにして完全に後回しました。
まずは最速で１周試験をまわす→見返すという順序で解くようにしました。

130分は思ったよりもあっという間です。
**迷ったらフラグを付けて後回し**にするのが、AWS資格の基本スタンスになりました。

## AWS Certified Developer - Associate (DVA)
https://aws.amazon.com/jp/certification/certified-developer-associate/?ch=tile&tile=getstarted
DVA-C01　130分 65問 
2022-06-16合格

前回のSAAに合格し、12日後にDVAを受験しました。
なぜそんな短期間で合格できたかというと、**ゴールから逆算することができるようになったから**です。
公式の練習問題をして6割取れたら合格する可能性がかなりあると考えて良いと思います！

以下、DVAの勉強法をまとめています。

### 勉強法
【公式の練習問題を解く】
- [AWS Certified Developer - Associate 公式練習問題集](https://explore.skillbuilder.aws/learn/course/internal/view/elearning/14060/aws-certified-developer-associate-official-practice-question-set-dva-c02-japanese)
公式練習問題集で6割取れていたら、すでに合格する知識がある程度身についていることが分かります。
2週間ほどさらに学習すれば合格できそうな感覚があったので、モチベーション維持のためにも受験の予定を入れました。

【本を読む】
- [ポケットスタディ AWS認定 デベロッパーアソシエイト (アソシエイト試験ポケットスタディ)](https://www.amazon.co.jp/%E3%83%9D%E3%82%B1%E3%83%83%E3%83%88%E3%82%B9%E3%82%BF%E3%83%87%E3%82%A3-AWS%E8%AA%8D%E5%AE%9A-%E3%83%87%E3%83%99%E3%83%AD%E3%83%83%E3%83%91%E3%83%BC%E3%82%A2%E3%82%BD%E3%82%B7%E3%82%A8%E3%82%A4%E3%83%88-%E3%82%A2%E3%82%BD%E3%82%B7%E3%82%A8%E3%82%A4%E3%83%88%E8%A9%A6%E9%A8%93%E3%83%9D%E3%82%B1%E3%83%83%E3%83%88%E3%82%B9%E3%82%BF%E3%83%87%E3%82%A3-%E5%B1%B1%E4%B8%8B%E5%85%89%E6%B4%8B/dp/4798063401)

【WEB問題集を解く】
- [AWS WEB問題集で学習しよう: Cloud License](https://cloud-license.com/)

## AWS Certified Solutions Architect - Professional (SAP)
https://aws.amazon.com/jp/certification/certified-solutions-architect-professional/?ch=tile&tile=getstarted
SAP-C01	180分 75問
2022-07-09合格
ここまで勉強を進めていると、AWSの知識が体系的に理解できるようになってきました。試しにSAPの公式練習問題集を解いてみたら、5割取れたのでこの勢いで受験してみようと決めました。

ネットでSAPを調べてみると「最難関！」などと出てきますが、**自分で実際に問題を解いてみることが一番大事**です。
たしかに問題文はアソシエイト試験と比べると長くなりますが、順調に学習が進んでいればSAP向けの知識を覚えるだけという感覚でした。

SAP合格に向けて大切なことは「**SAPを恐れすぎないこと**」です。
プロフェッショナル資格は自分にはまだ早い...と思わずに挑戦していく気持ちが大切だったりします。

### 勉強法
【公式の練習問題を解く】
[AWS Certified Solutions Architect - Professional 公式練習問題集](https://explore.skillbuilder.aws/learn/course/external/view/elearning/13272/aws-certified-solutions-architect-professional-official-practice-question-set-sap-c02-japanese)
【本を読む】
- [AWS認定資格試験テキスト＆問題集　AWS認定ソリューションアーキテクト - プロフェッショナル](https://www.amazon.co.jp/AWS%E8%AA%8D%E5%AE%9A%E8%B3%87%E6%A0%BC%E8%A9%A6%E9%A8%93%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88%EF%BC%86%E5%95%8F%E9%A1%8C%E9%9B%86-AWS%E8%AA%8D%E5%AE%9A%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%A2%E3%83%BC%E3%82%AD%E3%83%86%E3%82%AF%E3%83%88-%E3%83%97%E3%83%AD%E3%83%95%E3%82%A7%E3%83%83%E3%82%B7%E3%83%A7%E3%83%8A%E3%83%AB-%E6%94%B9%E8%A8%82%E7%AC%AC2%E7%89%88-%EF%BC%A1%EF%BC%B7%EF%BC%B3%E8%AA%8D%E5%AE%9A%E8%B3%87%E6%A0%BC%E8%A9%A6%E9%A8%93%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88-%E5%B1%B1%E4%B8%8B%E5%85%89%E6%B4%8B/dp/4815617929/ref=sr_1_2_sspa?crid=394WL6CGLIH41&keywords=aws+%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%A2%E3%83%BC%E3%82%AD%E3%83%86%E3%82%AF%E3%83%88+%E3%83%97%E3%83%AD%E3%83%95%E3%82%A7%E3%83%83%E3%82%B7%E3%83%A7%E3%83%8A%E3%83%AB&qid=1695102969&s=books&sprefix=%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%A2%E3%83%BC%E3%82%AD%E3%83%86%E3%82%AF%E3%83%88%2Cstripbooks%2C171&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1)
- [AWS認定ソリューションアーキテクト-プロフェッショナル ~試験特性から導き出した演習問題と詳細解説](https://www.amazon.co.jp/AWS%E8%AA%8D%E5%AE%9A%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%A2%E3%83%BC%E3%82%AD%E3%83%86%E3%82%AF%E3%83%88-%E3%83%97%E3%83%AD%E3%83%95%E3%82%A7%E3%83%83%E3%82%B7%E3%83%A7%E3%83%8A%E3%83%AB-%E8%A9%A6%E9%A8%93%E7%89%B9%E6%80%A7%E3%81%8B%E3%82%89%E5%B0%8E%E3%81%8D%E5%87%BA%E3%81%97%E3%81%9F%E6%BC%94%E7%BF%92%E5%95%8F%E9%A1%8C%E3%81%A8%E8%A9%B3%E7%B4%B0%E8%A7%A3%E8%AA%AC-%E5%B9%B3%E5%B1%B1-%E6%AF%85/dp/4865942483/ref=sr_1_4?crid=394WL6CGLIH41&keywords=aws+%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%A2%E3%83%BC%E3%82%AD%E3%83%86%E3%82%AF%E3%83%88+%E3%83%97%E3%83%AD%E3%83%95%E3%82%A7%E3%83%83%E3%82%B7%E3%83%A7%E3%83%8A%E3%83%AB&qid=1695102969&s=books&sprefix=%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%A2%E3%83%BC%E3%82%AD%E3%83%86%E3%82%AF%E3%83%88%2Cstripbooks%2C171&sr=1-4)

【WEB問題集を解く】
- [AWS WEB問題集で学習しよう: Cloud License](https://cloud-license.com/)

### SAPに合格した後
SAPに合格したら、周りの反応が明らかに変わったと感じました。
プロフェッショナルまで取得している人は、自分の周りにはいなくて**かなりのアドバンテージ**になったからです。
AWS資格の受験を考えている方はぜひSAAで終わってしまうのではなくて、SAPまで合格を目指してみてください。社内で「AWSの資格がある人」として認識され始めたのもこのころになります。

## AWS Certified SysOps Administrator - Associate (SOA)
https://aws.amazon.com/jp/certification/certified-sysops-admin-associate/?ch=tile&tile=getstarted
SOA-C02 130分 65問
2022-07-21

SAP合格からさらに12日後、SOAに合格しました！
この試験はラボという実技試験が唯一あるAWS試験で、別に対策が必要でした。

正直受験するか迷いましたが、
- ラボ以外の試験はすでに合格圏内だった
- AWSの実技試験に純粋に興味があった

という２点が決め手となり、受験の予定を入れました。

もうすでにAWS大好き人間になっていて、学習がライフワークのようになってきました。
AWSの勉強が義務ではなくて、エンタメになってきたので、自分が使える時間は全てAWSの勉強に充てていました。
もはやスマホでゲームしているのと同じ感覚でAWSの問題を解いています。

### 勉強法

【公式の練習問題を解く】
- [AWS Certified SysOps Administrator - Associate 公式練習問題集](https://explore.skillbuilder.aws/learn/course/external/view/elearning/12555/aws-certified-sysops-administrator-associate-practice-question-set-soa-c02-japanese?syops=sec&sec=prep)
- [AWS Certified SysOps Administrator - Associate のサンプル問題](https://d1.awsstatic.com/ja_JP/training-and-certification/docs-sysops-associate/AWS-Certified-SysOps-Administrator-Associate_Sample-Questions.pdf)でラボ問題をやってみる
- [AWSハンズオン資料](https://aws.amazon.com/jp/events/aws-event-resource/hands-on/)でラボ試験の練習をする

【WEB問題集を解く】
- [AWS WEB問題集で学習しよう: Cloud License](https://cloud-license.com/)


ハンズオン資料は公式が出している無料の動画で、ぜひやってみることをおすすめします。
AWSコンソールからの環境構築は実際にAWSアカウントを作成して練習できます。
請求が来ないように、練習したらすぐに構築した環境を消すことが大切なのでお忘れなく。


## AWS Certified DevOps Engineer - Professional (DOP)
https://aws.amazon.com/jp/certification/certified-devops-engineer-professional/?ch=tile&tile=getstarted
DOP-C01 180分 75問
2023-02-18

SOAに合格してから1ヶ月後に第二子が産まれました！
育児に追われて間が空いてしまったものの、どうしてもDOPが心残りでした。

やっと落ち着いた2023年に受験の予定を入れました。

間が空いてしまったし、忘れていることが多いかな...と思いましたが、
意外と覚えていて学習期間1ヶ月ほどで合格できて飛び上がるほど嬉しかったです。

公式が出している練習問題とWEB問題集を**9割理解できるところまで学習を進めて合格**できました。

### 勉強法
【公式の練習問題をいきなり解く】
 - [AWS Certified DevOps Engineer - Professional 公式練習問題集](
https://explore.skillbuilder.aws/learn/course/external/view/elearning/14541/aws-certified-devops-engineer-professional-official-practice-question-set-dop-c02-japanese)
- 試験準備標準コース: AWS Certified DevOps Engineer - Professional](https://aws.amazon.com/jp/certification/certified-devops-engineer-professional/?ch=tile&tile=getstarted#:~:text=%E8%A9%A6%E9%A8%93%E6%BA%96%E5%82%99%E6%A8%99%E6%BA%96%E3%82%B3%E3%83%BC%E3%82%B9%3A%20AWS%20Certified%20DevOps%20Engineer%20%2D%20Professional)を視聴する
【WEB問題集を解く】
-[AWS WEB問題集で学習しよう: Cloud License](https://cloud-license.com/)
 
 英語ですがAWS公式の試験準備標準コースのプログラムがとても良くて、DOPがどんな試験なのか、何か問われているのかを短期間で知ることができました。

## AWSの資格を取って良かったこと
AWS認定資格を6つ取得して良かったことは「エンジニアとして自信がついた」と「AWSのサービスを使ってアプリケーションを作成・運用できるようになった」の２点が挙げられます。
### エンジニアとして自信がついた
SAPを取得したあたりから自分でもAWSに対してかなり自信がつくようになりました。
資格勉強を続けて知識が増えていくにつれて、AWSのサービスの凄さや面白さを知ることができて何より学習を楽しむことができたのが良かったと感じています。
実際にエンジニアとして活躍している方とお話しする時に、AWS資格を持っていると好きなAWSサービスについて話題が弾んだりしました。
### AWSのサービスを使ってアプリケーションを作成・運用できるようになった
学習中に、実際にAWSのサービスのLambdaを使ってサーバレスアプリケーションを作りました。
コストがほとんどかからない環境構築ができたのも、すぐに現場で使うことができる「生きた知識」を学べたからと感じています。
AWS資格を取得しておしまいではなく、その知識を使って様々なサービスを自分で作り上げることができるようになりました。

## まとめ
AWS認定資格に挑戦してみて本当に良かったと感じています。
社内で「AWS6冠の人」と認知されるようになったことも嬉しいのですが、何より**AWSサービスを使って自分で環境構築できるようになったこと**が一番大きな収穫でした。

今後もAWSサービスを使って、フルスタックエンジニアとしてより良いサービスをたくさん構築して行きたいと思っています。

ここまで読んでいただいてありがとうございました！