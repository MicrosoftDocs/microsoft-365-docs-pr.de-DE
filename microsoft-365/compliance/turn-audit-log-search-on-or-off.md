---
title: Aktivieren oder Deaktivieren der Überwachungsprotokollsuche
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
description: Aktivieren oder Deaktivieren des Überwachungsprotokollsuchfeatures im Security & Compliance Center, um die Möglichkeit von Administratoren zum Durchsuchen des Überwachungsprotokolls zu aktivieren oder zu deaktivieren.
ms.openlocfilehash: aecd1d47592b9a5e2f134b1d9db9ff203b815b18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919281"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="35a6a-103">Aktivieren oder Deaktivieren der Überwachungsprotokollsuche</span><span class="sxs-lookup"><span data-stu-id="35a6a-103">Turn audit log search on or off</span></span>

<span data-ttu-id="35a6a-104">Die Überwachungsprotokollierung ist für Microsoft 365- und Office 365 Enterprise-Organisationen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="35a6a-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="35a6a-105">Das schließt Organisationen mit E3/G3- oder E5/G5-Abonnements ein.</span><span class="sxs-lookup"><span data-stu-id="35a6a-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="35a6a-106">Wenn die Überwachungsprotokollsuche im Compliance Center aktiviert ist, werden Benutzer- und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage und je nach der den Benutzern zugewiesenen Lizenz bis zu einem Jahr aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="35a6a-106">When audit log search in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="35a6a-107">Ihre Organisation hat jedoch möglicherweise Gründe, die Überwachungsprotokolldaten nicht aufzeichnen und beibehalten zu möchten.</span><span class="sxs-lookup"><span data-stu-id="35a6a-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="35a6a-108">In diesen Fällen kann ein globaler Administrator die Überwachung in Microsoft 365 deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="35a6a-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35a6a-109">Wenn Sie die Überwachungsprotokollsuche in Microsoft 365 deaktivieren, können Sie die Office 365-Verwaltungsaktivitäts-API oder Azure Sentinel nicht verwenden, um auf Überwachungsdaten für Ihre Organisation zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="35a6a-109">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="35a6a-110">Wenn Sie die Überwachungsprotokollsuche deaktivieren, indem Sie die Schritte in diesem Artikel ausführen, werden keine Ergebnisse zurückgegeben, wenn Sie das Überwachungsprotokoll mithilfe des Security & Compliance Center durchsuchen oder das **Cmdlet Search-UnifiedAuditLog** in Exchange Online PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="35a6a-110">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="35a6a-111">Dies bedeutet auch, dass Überwachungsprotokolle nicht über die Office 365-Verwaltungsaktivitäts-API oder Azure Sentinel verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="35a6a-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="35a6a-112">Vor dem Aktivieren oder Deaktivieren der Überwachungsprotokollsuche</span><span class="sxs-lookup"><span data-stu-id="35a6a-112">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="35a6a-113">Ihnen muss die Rolle Überwachungsprotokolle in Exchange Online zugewiesen werden, um die Überwachungsprotokollsuche in Ihrer Microsoft 365-Organisation ein- oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="35a6a-113">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="35a6a-114">Diese Rolle wird standardmäßig den Rollengruppen Complianceverwaltung und Organisationsverwaltung auf der Seite **Berechtigungen** im Exchange Admin Center zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="35a6a-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="35a6a-115">Globale Administratoren in Microsoft 365 sind Mitglieder der Rollengruppe Organisationsverwaltung in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="35a6a-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="35a6a-116">Benutzern müssen berechtigungen in Exchange Online zugewiesen werden, um die Überwachungsprotokollsuche ein- oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="35a6a-116">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="35a6a-117">Wenn Sie Benutzern die Rolle  Überwachungsprotokolle auf der Seite Berechtigungen im Security & Compliance Center zuweisen, können sie die Überwachungsprotokollsuche nicht aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="35a6a-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="35a6a-118">Dies liegt daran, dass das zugrunde liegende Cmdlet ein Exchange Online PowerShell-Cmdlet ist.</span><span class="sxs-lookup"><span data-stu-id="35a6a-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 
    
- <span data-ttu-id="35a6a-119">Schrittweise Anweisungen zum Durchsuchen des Überwachungsprotokolls finden Sie unter Durchsuchen des Überwachungsprotokolls im [Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="35a6a-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="35a6a-120">Weitere Informationen zur Microsoft 365-Verwaltungsaktivitäts-API finden Sie unter [Erste Schritte mit Microsoft 365-Verwaltungs-APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="35a6a-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="35a6a-121">Zur Überprüfung, dass die Überwachungsprotokollsuche aktiviert ist, können Sie den folgenden Befehl in der Exchange Online-PowerShell ausführen:</span><span class="sxs-lookup"><span data-stu-id="35a6a-121">To verify that audit log search is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="35a6a-122">Der Wert  `True` der  _UnifiedAuditLogIngestionEnabled-Eigenschaft_ gibt an, dass die Überwachungsprotokollsuche aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="35a6a-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned on.</span></span> 
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="35a6a-123">Aktivieren der Überwachungsprotokollsuche</span><span class="sxs-lookup"><span data-stu-id="35a6a-123">Turn on audit log search</span></span>

<span data-ttu-id="35a6a-124">Wenn die Überwachungsprotokollsuche für Ihre Organisation nicht aktiviert ist, können Sie sie im Compliance Center oder mithilfe von Exchange Online PowerShell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="35a6a-124">If audit log search is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="35a6a-125">Es kann mehrere Stunden dauern, bis Sie die Überwachungsprotokollsuche aktivieren, bevor Sie ergebnisse zurückgeben können, wenn Sie das Überwachungsprotokoll durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="35a6a-125">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="35a6a-126">Aktivieren der Überwachungsprotokollsuche mithilfe des Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="35a6a-126">Use the compliance center to turn on audit log search</span></span>

1. <span data-ttu-id="35a6a-127">[Wechseln Sie zum Compliance Center,](https://protection.office.com) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="35a6a-127">[Go to the compliance center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="35a6a-128">Wechseln Sie im Compliance Center zu **Suche**  >  **nach Überwachungsprotokollsuche**.</span><span class="sxs-lookup"><span data-stu-id="35a6a-128">In the compliance center, go to **Search** > **Audit log search**.</span></span>

   <span data-ttu-id="35a6a-129">Wenn die Überwachungsprotokollsuche für Ihre Organisation nicht aktiviert ist, wird ein Banner mit der Meldung angezeigt, dass die Überwachung aktiviert werden muss, um Benutzer- und Administratoraktivitäten zu aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="35a6a-129">If audit log search is not turned on for your organization, a banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="35a6a-130">Klicken **Sie auf Überwachung aktivieren.**</span><span class="sxs-lookup"><span data-stu-id="35a6a-130">Click **Turn on auditing**.</span></span>

    ![Klicken Sie auf Überwachung aktivieren](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="35a6a-132">Das Banner wird aktualisiert, um zu sagen, dass das Überwachungsprotokoll vorbereitet wird und Sie nach Benutzer- und Administratoraktivitäten in ein paar Stunden suchen können.</span><span class="sxs-lookup"><span data-stu-id="35a6a-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="35a6a-133">Aktivieren der Überwachungsprotokollsuche mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="35a6a-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="35a6a-134">Herstellen einer Verbindung mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="35a6a-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="35a6a-135">Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokollsuche in Office 365 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="35a6a-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="35a6a-136">Es wird eine Meldung angezeigt, dass es bis zu 60 Minuten dauern kann, bis die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="35a6a-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="35a6a-137">Deaktivieren der Überwachungsprotokollsuche</span><span class="sxs-lookup"><span data-stu-id="35a6a-137">Turn off audit log search</span></span>

<span data-ttu-id="35a6a-138">Sie müssen Exchange Online PowerShell verwenden, um die Überwachungsprotokollsuche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="35a6a-138">You have to use Exchange Online PowerShell to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="35a6a-139">Herstellen einer Verbindung mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="35a6a-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="35a6a-140">Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokollsuche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="35a6a-140">Run the following PowerShell command to turn off audit log search.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="35a6a-141">Überprüfen Sie nach einer Weile, ob die Überwachungsprotokollsuche deaktiviert (deaktiviert) ist.</span><span class="sxs-lookup"><span data-stu-id="35a6a-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="35a6a-142">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="35a6a-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="35a6a-143">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="35a6a-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="35a6a-144">Der Wert  `False` der  _UnifiedAuditLogIngestionEnabled-Eigenschaft_ gibt an, dass die Überwachungsprotokollsuche deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="35a6a-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="35a6a-145">Wechseln Sie [im Compliance Center](https://protection.office.com)zu Suche **nach** \> **Überwachungsprotokollsuche**.</span><span class="sxs-lookup"><span data-stu-id="35a6a-145">In the [compliance center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="35a6a-146">Es wird ein Banner mit der Meldung angezeigt, dass die Überwachung aktiviert werden muss, um Benutzer- und Administratoraktivitäten aufzeichnen zu können.</span><span class="sxs-lookup"><span data-stu-id="35a6a-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>