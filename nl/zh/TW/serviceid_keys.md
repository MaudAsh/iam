---

copyright:

  years: 2015, 2018
lastupdated: "2018-04-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 管理服務 ID API 金鑰
{: #serviceidapikeys}

建立服務 ID，以啟用在 {{site.data.keyword.Bluemix_notm}} 內外部管理的應用程式對您 {{site.data.keyword.Bluemix_notm}} 服務的存取。應用程式會使用 API 金鑰來鑑別為特定服務 ID，並獲指派與該服務 ID 相關聯的存取權。

在您建立服務 ID 之後，即可開始建立 API 金鑰，以及指派服務原則。每一個原則都會指定在使用 API 金鑰向服務進行鑑別時所容許的存取層次。如需建立服務 ID 以及指派原則的相關資訊，請參閱[建立及管理服務 ID](/docs/iam/serviceid.html#serviceids)。如需用來管理服務 ID API 金鑰之 CLI 指令的詳細資料，請參閱[用來管理 API 金鑰及原則的指令](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam)。

每一個與服務 ID 相關聯的 API 金鑰都會繼承已指派給服務 ID 的原則。例如，如果您要某個應用程式只能檢視服務內的資源，則需要使用與服務 ID 相關聯的 API 金鑰，而此 API 金鑰具有以 `Viewer` 角色指派的原則。而且，如果您要另一個應用程式能夠具有服務內的完整存取權，則需要使用與第二個服務 ID 相關聯的 API 金鑰，而此 API 金鑰具有以 `Administrator` 角色指派的原則。

如需相關資訊，請參閱[如何使用服務 ID 的範例](/docs/iam/serviceid.html#examples-of-how-to-use-a-service-id)。

## 建立服務 ID 的 API 金鑰

建立要與服務 ID 相關聯的 API 金鑰。

1. 移至**管理** &gt; **安全** &gt; **身分及存取** &gt; **服務 ID**。
2. 如果您尚未建立服務 ID，請建立服務 ID。
3. 從**動作**功能表中，移至**管理服務 ID** 選項。
4. 按一下「API 金鑰」區段中的**建立**。
5. 新增名稱及說明，以輕鬆識別 API 金鑰。
6. 按一下**建立**。
7. 複製 API 金鑰或將其下載至安全位置，以進行儲存。

**附註**：基於安全理由，只可在建立時複製或下載 API 金鑰。如果 API 金鑰遺失，您必須建立新的 API 金鑰。

## 更新服務 ID 的 API 金鑰

您可以在使用者介面中編輯用來識別 API 金鑰的名稱或說明，以更新 API 金鑰。

1. 移至**管理** &gt; **安全** &gt; **身分及存取** &gt; **服務 ID**。
2. 如果您尚未建立服務 ID，請建立服務 ID。
3. 從**動作**功能表中，移至**管理服務 ID** 選項。
4. 從「API 金鑰」區段的**動作**功能表中，移至**編輯名稱及說明**選項。


## 刪除服務 ID 的 API 金鑰

您可以刪除與服務 ID 相關聯的 API 金鑰。不過，刪除應用程式目前正在使用的 API 金鑰，該應用程式就無法向服務進行鑑別。

1. 移至**管理** &gt; **安全** &gt; **身分及存取** &gt; **服務 ID**。
2. 如果您尚未建立服務 ID，請建立服務 ID。
3. 從**動作**功能表中，移至**管理服務 ID** 選項。
4. 從「API 金鑰」區段的**動作**功能表中，移至**刪除索引鍵**選項。
