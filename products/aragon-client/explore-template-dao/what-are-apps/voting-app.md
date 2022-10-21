# Voting App（投票アプリ）

Voting Appを使えば、トークンを持っている仲間に、様々なトピックについて簡単に投票することができます。他のAragonアプリで開始された投票も、Voting Appに表示されます。

{% hint style="info" %}
例えば、Token Managerを使ったトークンの割り当てや、Finance Appからの資金移動は、それぞれ企業型DAO内のトークン保有者による投票が必要なアクションです。
{% endhint %}

**Voting App**では、すべての投票情報（投票中・完了済みの両方）を確認することができます。また、Voting Appを使用して、DAO内のトークン所有者に新しい提案を行うことができます。

![Voting Appのサマリー](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a573e2c7d3a7e9ae18ff0/file-diNRwkpZ5S.png)

## **Votingのフィルター**

Voting Appにはフィルターがあり、投票を分類することができます。

* **Status:** all, open, closed（すべて、オープン、クローズ）

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a56cb04286364bc8f801e/file-NUOi75e3Z9.png)

* **Outcome:** all, passed, rejected, enacted, pending（すべて、可決、否決、実行済、ペンディング）

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a56da2c7d3a7e9ae18fe7/file-YwgPhS2yB2.png)

* **App:** どのアプリで投票を作成したか。外部アカウントの場合は "external"

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a56e02c7d3a7e9ae18fe8/file-dppwlwO9hJ.png)

* **Start and end date（投票開始・終了日）**

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a56e62c7d3a7e9ae18fe9/file-IP6ZFN5oJr.png)

## **Open votes（投票期間中の提案）**

**Open votes**のセクションには、投票期間中の提案数、各投票のカードが表示され、投票の残り時間、投票数、投票中の議題概要、現在の投票状況が表示されます。

カードをクリックすると展開され、権限があれば、未投票の場合は投票し、すでに投票済みの場合は投票を変更することができます。

![Votingサマリー](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a573e2c7d3a7e9ae18ff0/file-diNRwkpZ5S.png)

### 投票カード

投票カードは、投票の状況について、以下のような詳細情報を表示します。

* **The vote number（投票番号）**
* **The question being voted on（提案された議題）**
* **What entity created the vote（どのエンティティが投票を作成したか）**
* **Current votes（現在の投票数）:** 現在までにどれだけのトークンが賛成票を投じ、どれだけのトークンが反対票を投じているか
* **Time remaining（残り時間）:** 投票が締め切られるまでの残り時間
* **Relative Support（相対支持率 ％）**: 投票が通過するために、何パーセントの有権者がyesに投票する必要があるか、何パーセントの有権者が、何個のトークンを使ってyesに投票したか、何パーセントの有権者が、何個のトークンを使ってnoに投票したか。
* **Minimum Approval（最低賛成率 ％）**: 投票が有効となるためには、全トークン供給量の何パーセントがyesに投票する必要があるか、またこれまでに全トークン供給量の何パーセントがyesに投票しているか。
* **まだ投票していない場合**は、yes/noの投票ボタンが表示されます。
* **すでに投票している場合**は、投票内容を変更するためのボタンが表示されます。
* 投票開始時のトークン残高と、投票スナップショットが取得されたブロック番号に基づいて、**あなたの投票力**が表示されます。

![投票カード](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a574c2c7d3a7e9ae18ff1/file-JwWUOOLDXB.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a57652c7d3a7e9ae18ff4/file-o96YChd3ub.png)

## **Closed votes（投票終了後の提案）**

**Closed votes**セクションには、過去の投票数および各投票のカードが表示されます。各カードには、過去の投票の日付、投票番号、提案概要、投票結果が表示されます。

投票をクリックすると、その投票に関するより詳細な情報が表示されます。表示される情報の詳細については、前項「投票カード」を参照してください。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a575c2c7d3a7e9ae18ff3/file-YlNlgwRl6E.png)

## **New vote（**新規投票**）**

トークン所有者に投票したい重要な事項がある場合、**New vote**ボタンをクリックすると、新しい投票が開始されます。これらの投票は純粋に情報提供であり、DAO内のさらなるアクションに直接つながるものではありません。

**New vote**パネルのテキストフィールドに質問したい内容を入力したら、**Create new vote**をクリックして、権限があれば新規投票を作成することができます。

![New voteページ](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a577204286364bc8f802d/file-hZgRtJkFVR.png)

### トランザクションに署名して新しい議案を作成する

**Create transaction**ボタンをクリックし、Ethereumプロバイダーでトランザクションに署名します。

![](https://lh3.googleusercontent.com/O5QcU0EU\_reAFPh\_8pzobCu0AYJWoGhvjIrrz6Af1WFBAwzFQQ3B66NOBBaDyvqJvGoWURJEGsHGoSzBCRHuWNNygEz3CuF6gNjTCwFcbB97L9SSq2HMW-0-PNupChit8QgiHkwK)

### 提案に投票し、他のトークン保有者に提案の確認と投票を依頼する

作成した提案に投票しましょう。次に、メール、フォーラム、チャット、対面など、アプリの外で仲間のトークン所有者を集め、その提案の確認と投票をお願いします。

トークン保有者は、Voting Appにアクセスして未投票のリストを確認し、それに従って投票することもできます。

![](https://lh4.googleusercontent.com/nGpEfIkINa6svbhzITg-ZhsXnzEsEHxI7OUYp9grFJ\_toT1Hm7nogTkyEExVnPZWMtk6EJYZNJp4Wi6E8kbOZJkgyPL\_7HyfW33fiZQMC-LLIrfN\_ydb66t7hQ6oT2SKrZAXo4gp)

### 他のトークン保有者が投票する

この例の場合、DAO内の他のトークン保有者は提案を支持し、yesに投票しています。

![](https://lh6.googleusercontent.com/qN1tTOiEi3GpMz5ylg\_eb47CxUEKZdHzNCYqChg3HJOaJXoYiTK-0ulOhaTljuOoosj6Eon8f9gDbotCO0jEh5989fSZpmtsbZ9jJfrxgtx5lSJVM8\_BYoYWfdw8AyIoTqh11d6o)

### 投票内容を確認する

このDAOにはトークン所有者が2人しかおらず、Supportパラメータが50%に設定されているため、提案に対する全会一致の投票により、提案が可決される結果となりました。

![](https://lh5.googleusercontent.com/s3ZFomLX49IX0uwO-cQESFA6b2TtIWoFm2yF6E\_i5EbRAW-wBkYSUwqBnAAH70Sq\_AAvoElR7s0\_R5\_kQcTxzXgro3bs\_dscBn4NfZlYvY9GpzPQs6acQbt0gul29-OO6lL28DWU)

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-voting-apps/24/2" %}
