---
title: Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche
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
description: Sie können das Feature Überwachungsprotokoll Suche im Security & Compliance Center aktivieren. Wenn Sie Ihre Meinung ändern, können Sie jederzeit deaktivieren. Wenn die Überwachungsprotokoll Suche deaktiviert ist, können Administratoren das Office 365 Überwachungsprotokoll nicht nach Benutzer-und Administratoraktivitäten in Ihrer Organisation durchsuchen.
ms.openlocfilehash: 92a781ddb1fd4f5b41198f31ebff6bba9745d21d
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240214"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="4bef2-105">Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche</span><span class="sxs-lookup"><span data-stu-id="4bef2-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="4bef2-106">Sie (oder ein anderer Administrator) müssen die Überwachungsprotokollierung aktivieren, bevor Sie mit der Suche im Office 365 Überwachungsprotokoll beginnen können.</span><span class="sxs-lookup"><span data-stu-id="4bef2-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="4bef2-107">Wenn die Überwachungsprotokoll Suche im Security & Compliance Center aktiviert ist, werden Benutzer-und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage und bis zu einem Jahr in Abhängigkeit von der Benutzerlizenz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4bef2-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="4bef2-108">Ihre Organisation hat jedoch möglicherweise Gründe dafür, dass Überwachungsprotokolldaten nicht aufgezeichnet und aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4bef2-108">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="4bef2-109">In diesen Fällen kann ein globaler Administrator beschließen, die Überwachung in Office 365 zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4bef2-109">In those cases, a global admin may decide to turn off auditing in Office 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4bef2-110">Wenn Sie die Überwachungsprotokoll Suche in Office 365 deaktivieren, können Sie die Office 365-Verwaltungs Aktivitäts-API oder Azure Sentinel nicht verwenden, um auf Überwachungsdaten für Ihre Organisation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4bef2-110">If you turn off audit log search in Office 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="4bef2-111">Wenn Sie die Überwachungsprotokoll Suche deaktivieren, indem Sie die Schritte in diesem Artikel durchführen, werden keine Ergebnisse zurückgegeben, wenn Sie das Überwachungsprotokoll mithilfe des Security & Compliance Center oder durch Ausführen des Cmdlets **Search-UnifiedAuditLog** in Exchange Online PowerShell durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="4bef2-111">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="4bef2-112">Dies bedeutet auch, dass Überwachungsprotokolle nicht über die Office 365-Verwaltungs Aktivitäts-API oder Azure Sentinel verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4bef2-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="4bef2-113">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="4bef2-113">Before you begin</span></span>

- <span data-ttu-id="4bef2-114">Sie müssen die Rolle Überwachungsprotokolle in Exchange Online zugewiesen haben, um die Überwachungsprotokoll Suche in Ihrer Office 365 Organisation ein-oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="4bef2-114">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="4bef2-115">Diese Rolle wird standardmäßig der Rollengruppe Compliance Management und Organisationsverwaltung auf der Seite **Berechtigungen** im Exchange Admin Center zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4bef2-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="4bef2-116">Globale Administratoren in Office 365 sind Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4bef2-116">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4bef2-117">Benutzern müssen Berechtigungen in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche ein-oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="4bef2-117">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="4bef2-118">Wenn Sie den Benutzern die Rolle "Überwachungsprotokolle" auf der Seite **Berechtigungen** im Security & Compliance Center zuweisen, kann die Überwachungsprotokoll Suche nicht aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4bef2-118">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="4bef2-119">Dies liegt daran, dass das zugrunde liegende Cmdlet ein Exchange Online-Cmdlet ist.</span><span class="sxs-lookup"><span data-stu-id="4bef2-119">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="4bef2-120">Eine Schritt-für-Schritt-Anleitung zum Durchsuchen des Office 365 Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="4bef2-120">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="4bef2-121">Weitere Informationen zur API für die Office 365-Verwaltungsaktivität finden Sie unter [Erste Schritte mit Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="4bef2-121">For more information about the Office 365 Management Activity API, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="4bef2-122">Aktivieren der Überwachungsprotokoll Suche</span><span class="sxs-lookup"><span data-stu-id="4bef2-122">Turn on audit log search</span></span>

<span data-ttu-id="4bef2-123">Sie können das Security & Compliance Center oder die PowerShell verwenden, um die Überwachungsprotokoll Suche in Office 365 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4bef2-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="4bef2-124">Es kann mehrere Stunden dauern, nachdem Sie die Überwachungsprotokoll Suche aktiviert haben, bevor Sie Ergebnisse zurückgeben können, wenn Sie das Überwachungsprotokoll durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="4bef2-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="4bef2-125">Sie müssen der Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4bef2-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="4bef2-126">Aktivieren der Überwachungsprotokoll Suche mithilfe des Security & Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="4bef2-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="4bef2-127">Wechseln Sie im Security & Compliance Center zu **Such** \> **Überwachungsprotokoll-Suche**.</span><span class="sxs-lookup"><span data-stu-id="4bef2-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
   <span data-ttu-id="4bef2-128">Ein Banner wird angezeigt, das besagt, dass die Überwachung aktiviert werden muss, um Benutzer-und Administratoraktivitäten aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="4bef2-128">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

2. <span data-ttu-id="4bef2-129">Klicken Sie auf **Überwachung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="4bef2-129">Click **Turn on auditing**.</span></span>
    
    ![Klicken Sie auf Überwachung aktivieren](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="4bef2-131">Das Banner wird aktualisiert, um zu sagen, dass das Überwachungsprotokoll vorbereitet wird und dass Sie in wenigen Stunden nach Benutzer-und Administratoraktivitäten suchen können.</span><span class="sxs-lookup"><span data-stu-id="4bef2-131">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="4bef2-132">Aktivieren der Überwachungsprotokoll Suche mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bef2-132">Use PowerShell to turn on audit log search</span></span>

1. <span data-ttu-id="4bef2-133">[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554).</span><span class="sxs-lookup"><span data-stu-id="4bef2-133">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)</span></span>
    
2. <span data-ttu-id="4bef2-134">Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokoll Suche in Office 365 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4bef2-134">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="4bef2-135">Es wird eine Meldung angezeigt, die besagt, dass es bis zu 60 Minuten dauern kann, bis die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="4bef2-135">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="4bef2-136">Deaktivieren der Überwachungsprotokoll Suche</span><span class="sxs-lookup"><span data-stu-id="4bef2-136">Turn off audit log search</span></span>

<span data-ttu-id="4bef2-137">Sie müssen Remote-PowerShell verwenden, die mit Ihrer Exchange Online Organisation verbunden ist, um die Überwachungsprotokoll Suche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4bef2-137">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="4bef2-138">Ähnlich wie beim Aktivieren der Überwachungsprotokoll Suche müssen Sie der Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4bef2-138">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. <span data-ttu-id="4bef2-139">[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554).</span><span class="sxs-lookup"><span data-stu-id="4bef2-139">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)</span></span>
    
2. <span data-ttu-id="4bef2-140">Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokoll Suche in Office 365 zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4bef2-140">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="4bef2-141">Überprüfen Sie nach einer Weile, ob die Überwachungsprotokoll Suche deaktiviert (disabled) ist.</span><span class="sxs-lookup"><span data-stu-id="4bef2-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="4bef2-142">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="4bef2-142">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="4bef2-143">Führen Sie in PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4bef2-143">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="4bef2-144">Der Wert von `False` für die _UnifiedAuditLogIngestionEnabled_ -Eigenschaft gibt an, dass die Überwachungsprotokoll Suche deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4bef2-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="4bef2-145">Wechseln Sie im Security & Compliance Center zu **Such** \> **Überwachungsprotokoll-Suche**.</span><span class="sxs-lookup"><span data-stu-id="4bef2-145">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
      <span data-ttu-id="4bef2-146">Ein Banner wird angezeigt, das besagt, dass die Überwachung aktiviert werden muss, um Benutzer-und Administratoraktivitäten aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="4bef2-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>
