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
description: Vorgehensweise aktivieren oder Deaktivieren der Überwachungsprotokoll-Suchfunktion im Security & Compliance Center, um die Fähigkeit von Administratoren zum Durchsuchen des Überwachungsprotokolls zu aktivieren oder zu deaktivieren.
ms.openlocfilehash: 4571c90c4fa680acd8925e83e32ffcf07de7d626
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819135"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="0c7df-103">Aktivieren oder Deaktivieren der Überwachungsprotokollsuche</span><span class="sxs-lookup"><span data-stu-id="0c7df-103">Turn audit log search on or off</span></span>

<span data-ttu-id="0c7df-104">Sie (oder ein anderer Administrator) müssen die Überwachungsprotokollierung aktivieren, bevor Sie mit der Durchsuchung des Überwachungsprotokolls beginnen können.</span><span class="sxs-lookup"><span data-stu-id="0c7df-104">You (or another admin) must turn on audit logging before you can start searching the audit log.</span></span> <span data-ttu-id="0c7df-105">Wenn die Überwachungsprotokoll Suche im Security & Compliance Center aktiviert ist, werden Benutzer-und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage und bis zu einem Jahr in Abhängigkeit von der Benutzerlizenz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0c7df-105">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="0c7df-106">Ihre Organisation hat jedoch möglicherweise Gründe dafür, dass Überwachungsprotokolldaten nicht aufgezeichnet und aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0c7df-106">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="0c7df-107">In diesen Fällen kann ein globaler Administrator beschließen, die Überwachung in Microsoft 365 zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c7df-107">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c7df-108">Wenn Sie die Überwachungsprotokoll Suche in Microsoft 365 deaktivieren, können Sie die Office 365-Verwaltungs Aktivitäts-API oder Azure Sentinel nicht verwenden, um auf Überwachungsdaten für Ihre Organisation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0c7df-108">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="0c7df-109">Wenn Sie die Überwachungsprotokoll Suche deaktivieren, indem Sie die Schritte in diesem Artikel durchführen, werden keine Ergebnisse zurückgegeben, wenn Sie das Überwachungsprotokoll mithilfe des Security & Compliance Center oder durch Ausführen des Cmdlets **Search-UnifiedAuditLog** in Exchange Online PowerShell durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="0c7df-109">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="0c7df-110">Dies bedeutet auch, dass Überwachungsprotokolle nicht über die Office 365-Verwaltungs Aktivitäts-API oder Azure Sentinel verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0c7df-110">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="0c7df-111">Vor dem Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche</span><span class="sxs-lookup"><span data-stu-id="0c7df-111">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="0c7df-112">Sie müssen in Exchange Online der Rolle "Überwachungsprotokolle" zugewiesen sein, um die Überwachungsprotokoll Suche in Ihrer Microsoft 365-Organisation ein-oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="0c7df-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="0c7df-113">Diese Rolle wird standardmäßig der Rollengruppe Compliance Management und Organisationsverwaltung auf der Seite **Berechtigungen** im Exchange Admin Center zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0c7df-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="0c7df-114">Globale Administratoren in Microsoft 365 sind Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c7df-114">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0c7df-115">Benutzern müssen Berechtigungen in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche ein-oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="0c7df-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="0c7df-116">Wenn Sie den Benutzern die Rolle "Überwachungsprotokolle" auf der Seite **Berechtigungen** im Security & Compliance Center zuweisen, kann die Überwachungsprotokoll Suche nicht aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0c7df-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="0c7df-117">Dies liegt daran, dass das zugrunde liegende Cmdlet ein Exchange Online-Cmdlet ist.</span><span class="sxs-lookup"><span data-stu-id="0c7df-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="0c7df-118">Eine Schritt-für-Schritt-Anleitung zum Durchsuchen des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="0c7df-118">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="0c7df-119">Weitere Informationen zur Verwaltungs Aktivitäts-API von Microsoft 365 finden Sie unter [Erste Schritte mit Microsoft 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="0c7df-119">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="0c7df-120">Aktivieren der Überwachungsprotokoll Suche</span><span class="sxs-lookup"><span data-stu-id="0c7df-120">Turn on audit log search</span></span>

<span data-ttu-id="0c7df-121">Sie können das Security & Compliance Center oder PowerShell verwenden, um die Überwachungsprotokoll Suche in Microsoft 365 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c7df-121">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Microsoft 365.</span></span> <span data-ttu-id="0c7df-122">Es kann mehrere Stunden dauern, nachdem Sie die Überwachungsprotokoll Suche aktiviert haben, bevor Sie Ergebnisse zurückgeben können, wenn Sie das Überwachungsprotokoll durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="0c7df-122">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="0c7df-123">Sie müssen der Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c7df-123">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="0c7df-124">Aktivieren der Überwachungsprotokoll Suche mithilfe des Security & Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="0c7df-124">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="0c7df-125">[Wechseln Sie zum Security & Compliance Center](https://protection.office.com) , und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="0c7df-125">[Go to the Security & Compliance Center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="0c7df-126">Wechseln Sie im Security & Compliance Center zu **Such** \> **Überwachungsprotokoll-Suche**.</span><span class="sxs-lookup"><span data-stu-id="0c7df-126">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>

   <span data-ttu-id="0c7df-127">Ein Banner wird angezeigt, das besagt, dass die Überwachung aktiviert werden muss, um Benutzer-und Administratoraktivitäten aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="0c7df-127">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="0c7df-128">Klicken Sie auf **Überwachung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="0c7df-128">Click **Turn on auditing**.</span></span>

    ![Klicken Sie auf Überwachung aktivieren](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="0c7df-130">Das Banner wird aktualisiert, um zu sagen, dass das Überwachungsprotokoll vorbereitet wird und dass Sie in wenigen Stunden nach Benutzer-und Administratoraktivitäten suchen können.</span><span class="sxs-lookup"><span data-stu-id="0c7df-130">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="0c7df-131">Aktivieren der Überwachungsprotokoll Suche mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c7df-131">Use PowerShell to turn on audit log search</span></span>

1. <span data-ttu-id="0c7df-132">[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554).</span><span class="sxs-lookup"><span data-stu-id="0c7df-132">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)</span></span>

2. <span data-ttu-id="0c7df-133">Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokoll Suche in Office 365 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c7df-133">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="0c7df-134">Es wird eine Meldung angezeigt, die besagt, dass es bis zu 60 Minuten dauern kann, bis die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="0c7df-134">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="0c7df-135">Deaktivieren der Überwachungsprotokoll Suche</span><span class="sxs-lookup"><span data-stu-id="0c7df-135">Turn off audit log search</span></span>

<span data-ttu-id="0c7df-136">Sie müssen Remote-PowerShell verwenden, die mit Ihrer Exchange Online Organisation verbunden ist, um die Überwachungsprotokoll Suche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c7df-136">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="0c7df-137">Ähnlich wie beim Aktivieren der Überwachungsprotokoll Suche müssen Sie der Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c7df-137">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. <span data-ttu-id="0c7df-138">[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554).</span><span class="sxs-lookup"><span data-stu-id="0c7df-138">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)</span></span>

2. <span data-ttu-id="0c7df-139">Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokoll Suche in Office 365 zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c7df-139">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="0c7df-140">Überprüfen Sie nach einer Weile, ob die Überwachungsprotokoll Suche deaktiviert (disabled) ist.</span><span class="sxs-lookup"><span data-stu-id="0c7df-140">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="0c7df-141">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="0c7df-141">There are two ways to do this:</span></span>

    - <span data-ttu-id="0c7df-142">Führen Sie in PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0c7df-142">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="0c7df-143">Der Wert von `False` für die _UnifiedAuditLogIngestionEnabled_ -Eigenschaft gibt an, dass die Überwachungsprotokoll Suche deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0c7df-143">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="0c7df-144">Wechseln Sie im [Security & Compliance Center](https://protection.office.com)zu **Such** \> **Überwachungsprotokoll-Suche**.</span><span class="sxs-lookup"><span data-stu-id="0c7df-144">In the [Security & Compliance Center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="0c7df-145">Ein Banner wird angezeigt, das besagt, dass die Überwachung aktiviert werden muss, um Benutzer-und Administratoraktivitäten aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="0c7df-145">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>