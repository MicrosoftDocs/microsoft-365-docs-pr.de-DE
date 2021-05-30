---
title: Aktivieren oder Deaktivieren der Überwachung
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: Aktivieren oder Deaktivieren des Überwachungsprotokollsuchfeatures im Microsoft 365 Compliance Center, um die Möglichkeit von Administratoren zum Durchsuchen des Überwachungsprotokolls zu aktivieren oder zu deaktivieren.
ms.openlocfilehash: 457f453b001f71a095bc60932c8e0cebf46aa7b1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706664"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="4d139-103">Aktivieren oder Deaktivieren der Überwachung</span><span class="sxs-lookup"><span data-stu-id="4d139-103">Turn auditing on or off</span></span>

<span data-ttu-id="4d139-104">Die Überwachungsprotokollierung ist für Microsoft 365- und Office 365 Enterprise-Organisationen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4d139-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="4d139-105">Das schließt Organisationen mit E3/G3- oder E5/G5-Abonnements ein.</span><span class="sxs-lookup"><span data-stu-id="4d139-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="4d139-106">Wenn die Überwachung im Compliance Center aktiviert ist, werden Benutzer- und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage und je nach der den Benutzern zugewiesenen Lizenz bis zu einem Jahr aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="4d139-106">When auditing in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="4d139-107">Ihre Organisation hat jedoch möglicherweise Gründe, die Überwachungsprotokolldaten nicht aufzeichnen und beibehalten zu möchten.</span><span class="sxs-lookup"><span data-stu-id="4d139-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="4d139-108">In diesen Fällen kann ein globaler Administrator die Überwachung in einem Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d139-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d139-109">Wenn Sie die Überwachung in Microsoft 365 deaktivieren, können Sie die Office 365 Management Activity API oder Azure Sentinel nicht verwenden, um auf Überwachungsdaten für Ihre Organisation zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4d139-109">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="4d139-110">Wenn Sie die Überwachung deaktivieren, indem Sie die Schritte in diesem Artikel ausführen, werden keine Ergebnisse zurückgegeben, wenn Sie das Überwachungsprotokoll mithilfe des Security & Compliance Center durchsuchen oder das **Cmdlet Search-UnifiedAuditLog** in Exchange Online PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="4d139-110">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="4d139-111">Dies bedeutet auch, dass Überwachungsprotokolle nicht über die Office 365 Management Activity API oder Azure Sentinel verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4d139-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="4d139-112">Vor dem Aktivieren oder Deaktivieren der Überwachung</span><span class="sxs-lookup"><span data-stu-id="4d139-112">Before you turn auditing on or off</span></span>

- <span data-ttu-id="4d139-113">Ihnen muss die Rolle Überwachungsprotokolle in Exchange Online zugewiesen werden, um die Überwachung in Ihrer Organisation Microsoft 365 aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d139-113">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="4d139-114">Diese Rolle wird standardmäßig den Rollengruppen Complianceverwaltung und  Organisationsverwaltung auf der Seite Berechtigungen im Exchange zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4d139-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="4d139-115">Globale Administratoren in Microsoft 365 mitglieder der Rollengruppe Organisationsverwaltung in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4d139-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="4d139-116">Benutzern müssen berechtigungen in den Exchange Online, um die Überwachung ein- oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="4d139-116">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="4d139-117">Wenn Sie Benutzern die Rolle  Überwachungsprotokolle auf der Seite Berechtigungen im Security & Compliance Center zuweisen, können sie die Überwachung nicht aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d139-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="4d139-118">Dies liegt daran, dass das zugrunde liegende Cmdlet ein Exchange Online PowerShell-Cmdlet ist.</span><span class="sxs-lookup"><span data-stu-id="4d139-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 

- <span data-ttu-id="4d139-119">Schrittweise Anweisungen zum Durchsuchen des Überwachungsprotokolls finden Sie unter Durchsuchen des Überwachungsprotokolls im [Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="4d139-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="4d139-120">Weitere Informationen zur Microsoft 365 Management Activity API finden Sie unter [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="4d139-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="4d139-121">Um zu überprüfen, ob die Überwachung aktiviert ist, können Sie den folgenden Befehl in Exchange Online PowerShell ausführen:</span><span class="sxs-lookup"><span data-stu-id="4d139-121">To verify that auditing is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="4d139-122">Der Wert  `True` der  _UnifiedAuditLogIngestionEnabled-Eigenschaft_ gibt an, dass die Überwachung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4d139-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> 

## <a name="turn-on-auditing"></a><span data-ttu-id="4d139-123">Aktivieren der Überwachung</span><span class="sxs-lookup"><span data-stu-id="4d139-123">Turn on auditing</span></span>

<span data-ttu-id="4d139-124">Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, können Sie sie im Compliance Center oder mithilfe Exchange Online PowerShell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d139-124">If auditing is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="4d139-125">Es kann mehrere Stunden dauern, bis Sie die Überwachung aktiviert haben, bevor Sie ergebnisse zurückgeben können, wenn Sie das Überwachungsprotokoll durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="4d139-125">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="4d139-126">Aktivieren der Überwachung mithilfe des Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="4d139-126">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="4d139-127">Gehen Sie auf <https://compliance.microsoft.com>, und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="4d139-127">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="4d139-128">Klicken Sie im linken Navigationsbereich Microsoft 365 Compliance Center auf **Alle** anzeigen, und klicken Sie dann auf **Überwachung**.</span><span class="sxs-lookup"><span data-stu-id="4d139-128">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

   <span data-ttu-id="4d139-129">Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, wird ein Banner mit der Aufforderung angezeigt, Benutzer- und Administratoraktivitäten zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="4d139-129">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![Banner auf der Seite "Überwachung"](../media/AuditingBanner.png)

3. <span data-ttu-id="4d139-131">Klicken Sie **auf das Banner Start recording user and admin activity.**</span><span class="sxs-lookup"><span data-stu-id="4d139-131">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="4d139-132">Es kann bis zu 60 Minuten dauern, bis die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="4d139-132">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="4d139-133">Aktivieren der Überwachung mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d139-133">Use PowerShell to turn on auditing</span></span>

1. [<span data-ttu-id="4d139-134">Herstellen einer Verbindung mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d139-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="4d139-135">Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachung in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d139-135">Run the following PowerShell command to turn on auditing in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="4d139-136">Es wird eine Meldung angezeigt, dass es bis zu 60 Minuten dauern kann, bis die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="4d139-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="4d139-137">Deaktivieren der Überwachung</span><span class="sxs-lookup"><span data-stu-id="4d139-137">Turn off auditing</span></span>

<span data-ttu-id="4d139-138">Sie müssen die Exchange Online PowerShell verwenden, um die Überwachung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d139-138">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. [<span data-ttu-id="4d139-139">Herstellen einer Verbindung mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d139-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="4d139-140">Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d139-140">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="4d139-141">Überprüfen Sie nach einer Weile, ob die Überwachung deaktiviert (deaktiviert) ist.</span><span class="sxs-lookup"><span data-stu-id="4d139-141">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="4d139-142">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="4d139-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="4d139-143">Führen Exchange Online in powerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4d139-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="4d139-144">Der Wert  `False` der  _UnifiedAuditLogIngestionEnabled-Eigenschaft_ gibt an, dass die Überwachung deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4d139-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="4d139-145">Wechseln Sie zur **Seite Überwachung** im Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="4d139-145">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="4d139-146">Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, wird ein Banner mit der Aufforderung angezeigt, Benutzer- und Administratoraktivitäten zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="4d139-146">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
