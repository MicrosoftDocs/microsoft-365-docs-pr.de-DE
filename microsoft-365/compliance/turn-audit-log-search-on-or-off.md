---
title: Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche
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
description: 'Sie können das Feature Überwachungsprotokoll Suche im Security #a0 Compliance Center aktivieren. Wenn Sie Ihre Meinung ändern, können Sie jederzeit deaktivieren. Wenn die Überwachungsprotokoll Suche deaktiviert ist, können Administratoren das Office 365 Überwachungsprotokoll nicht nach Benutzer-und Administratoraktivitäten in Ihrer Organisation durchsuchen.'
ms.openlocfilehash: 83ef355c4acd5e0af4fd7ffbf13157307bcac930
ms.sourcegitcommit: 53d848ebd4799b285d0f67c49b0aa24c88bd0e23
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "37334245"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="d534c-105">Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche</span><span class="sxs-lookup"><span data-stu-id="d534c-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="d534c-106">Sie (oder ein anderer Administrator) müssen die Überwachungsprotokollierung aktivieren, bevor Sie mit der Suche im Office 365 Überwachungsprotokoll beginnen können.</span><span class="sxs-lookup"><span data-stu-id="d534c-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="d534c-107">Wenn die Überwachungsprotokoll Suche im Security #a0 Compliance Center aktiviert ist, werden Benutzer-und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="d534c-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="d534c-108">Ihre Organisation möchte jedoch möglicherweise keine Überwachungsprotokolldaten aufzeichnen und aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="d534c-108">However, your organization may not want to record and retain audit log data.</span></span> <span data-ttu-id="d534c-109">Oder Sie verwenden möglicherweise eine Siem-Anwendung (Security Information and Event Management) eines Drittanbieters, um auf Ihre Überwachungsdaten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d534c-109">Or you may be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="d534c-110">In diesen Fällen kann ein globaler Administrator die Überwachungsprotokoll Suche in Office 365 deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d534c-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="d534c-111">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="d534c-111">Before you begin</span></span>

- <span data-ttu-id="d534c-112">Sie müssen die Rolle Überwachungsprotokolle in Exchange Online zugewiesen haben, um die Überwachungsprotokoll Suche in Ihrer Office 365 Organisation ein-oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="d534c-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="d534c-113">Diese Rolle wird standardmäßig der Rollengruppe Compliance Management und Organisationsverwaltung auf der Seite **Berechtigungen** im Exchange Admin Center zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d534c-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="d534c-114">Globale Administratoren in Office 365 sind Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d534c-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d534c-115">Benutzern müssen Berechtigungen in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche ein-oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="d534c-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="d534c-116">Wenn Sie den Benutzern die Rolle "Überwachungsprotokolle" auf der Seite **Berechtigungen** im Security #a0 Compliance Center zuweisen, kann die Überwachungsprotokoll Suche nicht aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d534c-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="d534c-117">Dies liegt daran, dass das zugrunde liegende Cmdlet ein Exchange Online-Cmdlet ist.</span><span class="sxs-lookup"><span data-stu-id="d534c-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="d534c-118">Wenn Sie die Überwachungsprotokoll Suche in Office 365 deaktivieren, können Sie die Office 365 Verwaltungs Aktivitäts-API nicht verwenden, um auf Überwachungsdaten für Ihre Organisation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d534c-118">If you turn off audit log search in Office 365, you can't use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="d534c-119">Wenn Sie die Überwachungsprotokoll Suche deaktivieren, indem Sie die Schritte in diesem Artikel durchführen, werden keine Ergebnisse zurückgegeben, wenn Sie das Überwachungsprotokoll mithilfe der Sicherheits #a0 Compliance Center oder beim Ausführen des Cmdlets **Search-UnifiedAuditLog** in Exchange Online PowerShell durchsuchen. .</span><span class="sxs-lookup"><span data-stu-id="d534c-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="d534c-120">Dies bedeutet auch, dass Ihre Überwachungsprotokolle nicht über die Office 365 Verwaltungs Aktivitäts-API verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d534c-120">This also means that your audit logs won't be available through the Office 365 Management Activity API.</span></span>  
    
- <span data-ttu-id="d534c-121">Eine Schritt-für-Schritt-Anleitung zum Durchsuchen des Office 365 Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security #a0 Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="d534c-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="d534c-122">Aktivieren der Überwachungsprotokoll Suche</span><span class="sxs-lookup"><span data-stu-id="d534c-122">Turn on audit log search</span></span>

<span data-ttu-id="d534c-123">Sie können das Security #a0 Compliance Center oder die PowerShell verwenden, um die Überwachungsprotokoll Suche in Office 365 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d534c-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="d534c-124">Es kann mehrere Stunden dauern, nachdem Sie die Überwachungsprotokoll Suche aktiviert haben, bevor Sie Ergebnisse zurückgeben können, wenn Sie das Überwachungsprotokoll durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="d534c-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="d534c-125">Sie müssen der Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d534c-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="d534c-126">Aktivieren der Überwachungsprotokoll Suche mithilfe des Security #a0 Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="d534c-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="d534c-127">Wechseln Sie im Security #a0 Compliance Center zu **Such** \> **Überwachungsprotokoll-Suche**.</span><span class="sxs-lookup"><span data-stu-id="d534c-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
   <span data-ttu-id="d534c-128">Ein Banner wird angezeigt, das besagt, dass die Überwachung aktiviert werden muss, um Benutzer-und Administratoraktivitäten aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="d534c-128">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

2. <span data-ttu-id="d534c-129">Klicken Sie auf **Überwachung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="d534c-129">Click **Turn on auditing**.</span></span>
    
    ![Klicken Sie auf Überwachung aktivieren](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="d534c-131">Das Banner wird aktualisiert, um zu sagen, dass das Überwachungsprotokoll vorbereitet wird und dass Sie in wenigen Stunden nach Benutzer-und Administratoraktivitäten suchen können.</span><span class="sxs-lookup"><span data-stu-id="d534c-131">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="d534c-132">Aktivieren der Überwachungsprotokoll Suche mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="d534c-132">Use PowerShell to turn on audit log search</span></span>

1. <span data-ttu-id="d534c-133">[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554).</span><span class="sxs-lookup"><span data-stu-id="d534c-133">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)</span></span>
    
2. <span data-ttu-id="d534c-134">Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokoll Suche in Office 365 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d534c-134">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="d534c-135">Es wird eine Meldung angezeigt, die besagt, dass es bis zu 60 Minuten dauern kann, bis die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="d534c-135">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="d534c-136">Deaktivieren der Überwachungsprotokoll Suche</span><span class="sxs-lookup"><span data-stu-id="d534c-136">Turn off audit log search</span></span>

<span data-ttu-id="d534c-137">Sie müssen Remote-PowerShell verwenden, die mit Ihrer Exchange Online Organisation verbunden ist, um die Überwachungsprotokoll Suche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d534c-137">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="d534c-138">Ähnlich wie beim Aktivieren der Überwachungsprotokoll Suche müssen Sie der Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d534c-138">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. <span data-ttu-id="d534c-139">[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554).</span><span class="sxs-lookup"><span data-stu-id="d534c-139">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)</span></span>
    
2. <span data-ttu-id="d534c-140">Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokoll Suche in Office 365 zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d534c-140">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="d534c-141">Überprüfen Sie nach einer Weile, ob die Überwachungsprotokoll Suche deaktiviert (disabled) ist.</span><span class="sxs-lookup"><span data-stu-id="d534c-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="d534c-142">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="d534c-142">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="d534c-143">Führen Sie in PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d534c-143">In PowerShell, run the following command:</span></span>

            ```
            Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
            ```

           The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off. 
    
    - <span data-ttu-id="d534c-144">Wechseln Sie im Security #a0 Compliance Center zu **Such** \> **Überwachungsprotokoll-Suche**.</span><span class="sxs-lookup"><span data-stu-id="d534c-144">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
           A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.
