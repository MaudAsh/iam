---

copyright:

  years: 2015, 2018

lastupdated: "2018-04-04"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# IAM アクセス権限
{: #userroles}

アカウント内のリソース・グループに編成されたすべてのサービスは、{{site.data.keyword.Bluemix_notm}}  Identity and Access Management (IAM) を使用して管理されます。 アカウント所有者には、Cloud IAM に対するアカウント管理者役割が自動的に割り当てられます。 アカウント管理者は、ユーザーのアクセス権限の割り当てと管理、リソース・グループの作成、サービス・インスタンスのプロビジョン、およびその他のすべての作業を実行でき、これらの作業は、Cloud IAM 役割を割り当てることによって委任できます。 ポリシーを作成することによって、ユーザーおよびサービス ID のアクセス権限を指定します。ポリシーは、ユーザーまたはサービス ID がアクセスできるターゲットと、どのタイプのアクセスが許可されるのかを定義する役割を設定します。


## Cloud IAM ポリシーとは何か、誰が割り当てを行えるのか?
{: #iamusermanpol}

ポリシーは、指定されたターゲット・リソースのコンテキスト内で特定のアクションを行うことができるように、リソースのセットに対する 1 つまたは複数の役割をユーザーまたはサービス ID に付与します。 ポリシーを割り当てるときには、最初に、リソース・グループのポリシーを設定するのか、個別リソースのポリシーを設定するのかを選択します。 次に、最初に行った選択に応じて、リソース・グループ内のサービスを選択するか、または、選択したリソースの単一インスタンスを選択できます。 選択するサービスに応じて、追加の構成オプションが使用可能な場合があります。 最後に、割り当てる 1 つ以上の役割を選択できます。 

適切な役割を持っている場合、ポリシーを割り当て、管理することができます。 以下の表は、ポリシー管理タスクと、各タスクに必要な役割を示しています。

| アクション | 必要な役割 |
|----------|---------|
| アカウント内のすべてのサービスおよびインスタンスに関するポリシーの作成 | アカウント所有者またはアカウント内のすべてのサービスの管理者 | 
| アカウント内の 1 つのサービスに関するポリシーの作成 | アカウント所有者またはアカウント内のサービスの管理者 |
| 1 つのサービス・インスタンスに関するポリシーの作成 | アカウント所有者、アカウント内のサービスの管理者、関連するリソース・グループ内のすべてのサービスの管理者、またはサービス・インスタンスの管理者 |
| リソース・グループを管理するためのポリシーの作成 | アカウント所有者またはリソース・グループの管理者 |
{: caption="表 1. アクセス・ポリシーの作成を許可されるユーザー" caption-side="top"} 


## Cloud IAM の役割
{: #iamusermanrol}

Cloud IAM を使用して、アカウント内のユーザーとリソースのアクセス権限を管理および定義することができます。 割り当てることができる役割には、プラットフォーム管理の役割とサービス・アクセスの役割の 2 つのタイプがあります。

<dl>
<dt>プラットフォーム管理の役割</dt> 
<dd>プラットフォーム管理の役割は、インスタンスの作成、サービス ID の管理、ユーザーおよび許可の管理、およびリソース・グループの作成を行う能力を含めて、さまざまなアクションをカバーします。 プラットフォームの役割のうち最も一般的なのは、管理者、エディター、オペレーター、ビューアーです。 </dd>
<dt>サービス・アクセスの役割</dt>
<dd>サービス・アクセスの役割は、ユーザーまたはサービスが、UI へのアクセスや API 呼び出しの実行など、サービス・インスタンスに関するアクションを実行する能力を定義します。 管理者、ライター、リーダーの 3 つの役割があります。 </dd>
</dl> 

UI でポリシーを割り当てるときに、オプションとしてリストされるのがすべての役割ではないことがあります。これは、選択したサービスに使用可能な役割のみが表示されるためです。 それぞれのサービスでの有効な役割および各アクセス役割で許可されるアクションに関する具体的な情報については、そのサービスの資料を参照してください。
{: tip}

単一のアクセス・ポリシー内でこれらの役割を組み合わせて使用することで、微細化されたアクセス権限をユーザーおよびサービス ID に対して提供できます。そのためには、以下のうちの任意のものに関するアクセス権限を割り当てます。

* アカウント内のすべてのリソース
* 個別リソース・グループに属しているすべてのサービス内のすべてのリソース、および、リソース・グループを管理する能力
* リソース・グループ内の単一サービス内のすべてのリソース、および、リソース・グループを管理する能力
* リソースが割り当てられている先のリソース・グループに関係なく、アカウント全体での単一サービス内のすべてのリソース
* 個別インスタンス内のリソース
* インスタンス内の単一リソース・タイプ (例: {{site.data.keyword.objectstorageshort}} インスタンス内のバケット)

リソース・グループを作成する能力を含めて、ユーザー・アクセスの管理とすべてのアカウント・リソースの管理を行う目的で、別のユーザーがアカウントへの全アクセス権限を持つようにするには、**管理者**役割が割り当てられた状態で**「すべての ID およびアクセス対応サービス」**を選択することによって、アカウント内のすべてのリソースへのアクセス権限をそのユーザーに付与するポリシーをセットアップします。 
{: tip}

### プラットフォーム管理の役割

プラットフォーム管理の役割は、アカウント内でプラットフォーム・アクションを実行するためのさまざまなレベルの許可をユーザーに割り当てることを可能にします。 以下の表に、各役割を割り当てられたユーザーが実行できるいくつかのプラットフォーム管理アクションの例を示します。 使用されるサービスのコンテキストで役割がどのようにユーザーに適用されるのかを理解するには、各サービスの資料を参照してください。

| アクセス・ポリシーの詳細  | アカウント内のサービスに対してユーザーが実行できるアクション | サービス ID に対するアクション | リソース・グループへのアクセス権限に対するアクション | リソース・グループ内のリソースに対するアクション | アクセス・グループを管理するためのアクション |
|:-----------------|:--------------|:---------------|:----------------|:-----------------|:--------------|
| アクセス権限の割り当て先 | 1 つまたはすべての IAM 対応サービス | IAM ID サービス | 選択されたリソース・グループ | リソース・グループ内の選択されたサービス | IAM アクセス・グループ |
| ビューアー役割 | インスタンス、別名、バインディング、および資格情報の表示 | ID および API キーの表示 | リソース・グループの表示 | リソース・グループ内の指定されたインスタンスのみの表示 | アクセス・グループとメンバーの表示 |
| オペレーター役割 |  インスタンスの表示と、別名、バインディング、および資格情報の管理 | 適用外 | 適用外 | 適用外 | 適用外 |
| エディター役割 |  インスタンスの作成、削除、編集、および表示。 別名、バインディング、および資格情報の管理 | ID および API キーの作成および削除 | リソース・グループ名の表示および編集 | リソース・グループ内の指定されたインスタンスのみの作成、削除、編集、一時停止、再開、表示、およびバインド | アカウント内のアクセス・グループの表示、作成、削除、および編集 |
| 管理者役割 |  サービスに対するすべての管理アクション | ID および API キーの作成と削除、ID へのポリシーの割り当て | リソース・グループのアクセス権限の表示、編集、および管理 | リソース・グループ内の指定されたインスタンスに対するすべての管理アクション | アクセス・グループでの作業を行うためのアクセス権限の表示、作成、削除、編集、および管理 |
{: caption="表 2. プラットフォーム管理の役割とアクションの例" caption-side="top"}
{: #platformrolestable}

サービスの中には、特定のアクションを、サービスのアクセスではなくサービスの管理に関連したプラットフォーム管理の役割にマップするものがあります。 例として、それらの役割にマップされている {{site.data.keyword.containershort_notm}} サービス・アクションの詳細を示す以下の表を参照してください。


| プラットフォーム管理の役割 | アクションの説明 | {{site.data.keyword.containershort_notm}} に対するアクションの例 |
|:-----------------|:-----------------|:-----------------|
| ビューアー | サービス・インスタンスの表示はできるが、変更はできない  | <ul><li>クラスターのリスト</li><li>クラスターの詳細を表示する</li></ul>|
| エディター | アカウントの管理とアクセス・ポリシーの割り当てを除き、すべてのプラットフォーム・アクションを実行する |<ul><li>クラスターへのサービスのバインド</li><li>Web フックの作成</li></ul> |
| オペレーター | サービスのダッシュボードの表示など、サービス・インスタンスの構成および操作に必要なプラットフォーム・アクションを実行する。 | <ul><li>ワーカー・ノードの追加または削除</li><li>ワーカー・ノードのリブートまたは再ロード</li><li>クラスターへのサービスのバインド</li></ul> |
| 管理者 | 他のユーザーへのアクセス・ポリシーの割り当てを含め、この役割が割り当てられているリソースに基づいてすべてのプラットフォーム・アクションを実行する。 |<ul><li>クラスターの削除</li><li>クラスターの作成</li><li>ユーザー・アクセス・ポリシーの更新</li><li>ビューアー、エディター、およびオペレーターが実行できるすべてのアクション</li></ul>|
{: caption="表 3. プラットフォーム管理の役割と {{site.data.keyword.containershort_notm}} サービスに対するアクションの例" caption-side="top"}


### サービス・アクセスの役割

サービス・アクセスの役割は、サービスの API の呼び出しおよびサービスの UI へのアクセスを行うためのさまざまなレベルの許可をユーザーに割り当てることを可能にします。 以下の表は、{{site.data.keyword.objectstorageshort}} サービスの使用に基づいて割り当てられる役割に応じて実行できるアクションの例を示しています。

**注**: 割り当てられた各役割で実行できるアクションは、ポリシーに対して選択したサービスに基づいて異なります。

| サービス・アクセスの役割 | アクションの説明 | {{site.data.keyword.objectstorageshort}} サービスのアクションの例 |
|:-----------------|:-----------------|:-----------------|
|  リーダー | サービス固有のリソースの表示など、サービス内で読み取り専用アクションを実行する | オブジェクトのリストおよびダウンロード |
| ライター | ライターは、サービス固有のリソースの作成および編集など、リーダー役割を超えるアクセス権を持つ。 | バケットおよびオブジェクトの作成と破棄 |
| 管理者 | 管理者は、サービスによって定義された特権付きアクションを実行する、ライター役割を超えるアクセス権を持つ。 それに加え、サービス固有のリソースを作成および編集できます。 | データ・ストレージのすべての側面の管理、バケットおよびオブジェクトの作成と破棄 |
{: caption="表 4. サービス・アクセス・ユーザーの役割とアクションの例" caption-side="top"}

