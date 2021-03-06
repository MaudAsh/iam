---

copyright:

  years: 2017, 2018
lastupdated: "2018-03-19"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 创建和管理服务标识
{: #serviceids}

服务标识用于标识服务或应用程序，类似于用户标识对用户进行标识的方式。创建的服务标识可用于支持 {{site.data.keyword.Bluemix_notm}} 外部的应用程序访问 {{site.data.keyword.Bluemix_notm}} 服务。您可以向服务标识分配特定访问策略，以限制使用特定服务的许可权，甚至可以将访问不同服务的许可权组合在一起。由于服务标识并不与特定用户绑定，因此即使用户离开组织并将其从帐户中删除，该服务标识仍会保留，以确保您的应用程序或服务保持正常运行。

创建服务标识时，将创建唯一的名称和描述，方便您在 UI 中识别和使用。一旦创建了服务标识，就可以创建特定于每个服务标识的 API 密钥，应用程序可以使用这些密钥向 {{site.data.keyword.Bluemix_notm}} 服务进行认证。要确保应用程序具有对 {{site.data.keyword.Bluemix_notm}} 服务进行认证的相应访问权，您可使用分配给所创建的每个服务标识的服务策略。

与服务标识关联的访问策略支持在该服务标识用于访问特定服务时执行特定操作。可以为单个服务标识分配多个策略，这些策略定义访问多个支持身份和访问权的服务（甚至单个服务的不同实例）时允许的访问级别。例如，您有两个服务，每个服务分别有两个服务实例。您可为一个服务的所有可用实例分配`查看者`角色，而仅为第二个服务的一个实例分配`编辑者`角色。这样，就可以定制对多个服务的访问权，但仍使用单个 API 密钥向所有这些服务进行认证。


## 创建服务标识

要创建服务标识，请转至**管理** &gt; **安全性** &gt; **身份和访问权**，然后从侧面板选择**服务标识**。执行为服务标识创建名称和描述的过程。然后，使用**操作**菜单来管理服务标识。您可以首先分配策略和创建 API 密钥。有关使用 API 密钥的更多信息，请参阅[管理服务标识 API 密钥](/docs/iam/serviceid_keys.html#serviceidapikeys)。有关用于管理服务标识的 CLI 命令的详细信息，请参阅[用于管理 API 密钥和策略的命令](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam)。

## 更新服务标识

您可以随时通过更改服务标识的名称和描述来更新该服务标识。还可以根据需要删除和创建新的 API 密钥，或更新分配的访问策略。但是，对现有服务标识进行的任何更改（例如，更改分配的策略或删除当前正在使用的 API 密钥）可能会导致使用该服务标识的应用程序发生服务中断。

## 如何使用服务标识的示例

下面是如何将服务标识与 {{site.data.keyword.objectstorageshort}} 和 Cloud SQL 查询服务配合使用的示例。

- {{site.data.keyword.objectstorageshort}} - [入门](/docs/services/cloud-object-storage/getting-started-cli.html#getting-started-cli-)。
- Cloud SQL Query - [如何使用 SQL 查询 REST API ![外部链接图标](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}。
