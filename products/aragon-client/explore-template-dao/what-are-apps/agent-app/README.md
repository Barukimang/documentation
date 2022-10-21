# Agent App（エージェントアプリ）

## Agent appとは？

**Agent App**は、DAOがEthereum上の**他のスマートコントラクト**と直接**やり取り**することを可能にします。Agentがなかった時は、DAOは、イーサリアムのスマートコントラクトとやり取りするために、信頼できるパーティを指名する必要がありました。

{% hint style="info" %}
例えば、あるDAOがメンバーにDAIを送り、メンバーがそのDAIをコンパウンドで貸して利息をつけ、その利息と元本をDAOに送り返すように、メンバーを信頼する必要がありました。
{% endhint %}

Agentによって、仲介者を介さずに直接コンパウンドにDAIを貸し出すことができるようになりました。

## Agent Appを使い始めるには？

Agent Appを使い始める最も簡単な方法は、DAOを最初に作成する際に、オプションでインストールする**ボックスにチェック**を入れることです。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bc80204286364bc8f9029/file-zLiYZ6kXSy.png)

{% hint style="info" %}
なお、Agent Appを使用しないテンプレートに含まれるVault Appは、いずれかのテンプレート経由でAgentをインストールすると、自動的に置き換えられます。
{% endhint %}

{% hint style="warning" %}
最初にDAOを作成する際に、オプションで Agent Appをインストールしなかった場合でも、DAOが作成された後にインストールすることができます。これを行うには、[aragonCLIを使用してAgent Appのインストールと初期化（英語のみ）](https://github.com/aragon/aragon-apps)を行う必要があります。このオプションは、エキスパート向けであることに注意してください。
{% endhint %}

## **Agentのフロントエンドインターフェース**

**Agent App**には現在、**閲覧専用のフロントエンドインターフェース**があり、Agent Appが現在保有しているトークン（ERC-20、ERC-677、ERC-777トークンを含む）やAgent Appを使った取引履歴を確認することが可能です。取引履歴は、トランザクションタイプ、トークン、日付でフィルタリングでき、CSVファイルとしてエクスポートすることができます。

![Agent Appのページ](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e8ce5d32c7d3a7e9aea8d19/file-r5322DPQHX.png)

Agentスマートコントラクトのアドレスは、**Organization**ページの**System**メニューから確認できます。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bcdad2c7d3a7e9ae1a16d/file-pJP6dzQfhR.png)

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-agent-app/28/2" %}
