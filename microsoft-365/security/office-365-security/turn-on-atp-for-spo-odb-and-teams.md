---
title: Aktivieren von Office 365 ATP – SharePoint, OneDrive, & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Hier erfahren Sie, wie Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren, einschließlich der Vorgehensweise zum Festlegen von Benachrichtigungen für erkannte Dateien.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c717a89492ea1160f26f26f13be6c36f348c79c
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350655"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="d3a85-103">Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3a85-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d3a85-104">Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.</span><span class="sxs-lookup"><span data-stu-id="d3a85-104">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="d3a85-105">Weitere Informationen finden Sie unter [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d3a85-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="d3a85-106">Dieser Artikel enthält die Schritte zum Aktivieren und Konfigurieren von ATP für SharePoint, OneDrive und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d3a85-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d3a85-107">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="d3a85-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d3a85-108">Sie öffnen das Security & Compliance Center unter <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="d3a85-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="d3a85-109">Um direkt zur Seite **ATP-sichere Anlagen** zu wechseln, öffnen Sie <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="d3a85-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="d3a85-110">Um ATP für SharePoint, OneDrive und Microsoft Teams zu aktivieren, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " im Security & Compliance Center sein.</span><span class="sxs-lookup"><span data-stu-id="d3a85-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="d3a85-111">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d3a85-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d3a85-112">Um SharePoint Online PowerShell zu verwenden, um zu verhindern, dass Benutzer böswillige Dateien herunterladen können, müssen Sie Mitglied der Rolle [globaler Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) oder [SharePoint-Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD sein.</span><span class="sxs-lookup"><span data-stu-id="d3a85-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="d3a85-113">Stellen Sie sicher, dass die Überwachungsprotokollierung für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d3a85-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="d3a85-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="d3a85-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="d3a85-115">Erlauben Sie bis zu 30 Minuten, bis die Einstellungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="d3a85-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="d3a85-116">Schritt 1: Verwenden Sie das Security & Compliance Center, um ATP für SharePoint, OneDrive und Microsoft Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d3a85-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="d3a85-117">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**, und klicken Sie auf **globale Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d3a85-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="d3a85-118">Wechseln Sie in den angezeigten **globalen Einstellungen** zur Option **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="d3a85-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="d3a85-119">Bewegen Sie die Umschaltfläche nach rechts, ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) um ATP für SharePoint, OneDrive und Microsoft Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d3a85-119">Move the toggle to the right ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="d3a85-120">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d3a85-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="d3a85-121">Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams mithilfe Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3a85-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="d3a85-122">Wenn Sie lieber mithilfe von PowerShell ATP für SharePoint, OneDrive und Microsoft Teams aktivieren möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) , und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d3a85-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="d3a85-123">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="d3a85-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="d3a85-124">Schritt 2: (empfohlen) verwenden SharePoint Online PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen</span><span class="sxs-lookup"><span data-stu-id="d3a85-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="d3a85-125">Standardmäßig können Benutzer schädliche Dateien, die von ATP erkannt werden, nicht öffnen, verlagern, kopieren oder freigeben.</span><span class="sxs-lookup"><span data-stu-id="d3a85-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="d3a85-126">Sie können jedoch schädliche Dateien löschen und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d3a85-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="d3a85-127">Um zu verhindern, dass Benutzer schädliche Dateien herunterladen, stellen [Sie eine Verbindung mit SharePoint Online PowerShell her](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) , und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d3a85-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="d3a85-128">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="d3a85-128">**Notes**:</span></span>

- <span data-ttu-id="d3a85-129">Diese Einstellung wirkt sich sowohl auf Benutzer als auch auf Administratoren aus.</span><span class="sxs-lookup"><span data-stu-id="d3a85-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="d3a85-130">Personen können weiterhin bösartige Dateien löschen.</span><span class="sxs-lookup"><span data-stu-id="d3a85-130">People can still delete malicious files.</span></span>

<span data-ttu-id="d3a85-131">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="d3a85-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="d3a85-132">Schritt 3 (empfohlen) Verwenden des Security & Compliance Center zum Erstellen einer Warnungs Richtlinie für erkannte Dateien</span><span class="sxs-lookup"><span data-stu-id="d3a85-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="d3a85-133">Sie können eine Warnungs Richtlinie erstellen, die Sie und andere Administratoren benachrichtigt, wenn ATP für SharePoint, OneDrive und Microsoft Teams eine bösartige Datei erkennt.</span><span class="sxs-lookup"><span data-stu-id="d3a85-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="d3a85-134">Weitere Informationen zu Warnungen finden Sie unter [Erstellen von Aktivitäts Warnungen im Security & Compliance Center](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="d3a85-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="d3a85-135">Wechseln Sie im [Security & Compliance Center](https://protection.office.com) **zu Alerts** \> **Alerts Policies** oder Open <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="d3a85-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="d3a85-136">Klicken Sie auf der Seite **Warnungsrichtlinien** auf **neue Warnungs Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d3a85-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="d3a85-137">Der Assistent für **neue Warnungsrichtlinien** wird in einem Fly Out geöffnet. Konfigurieren Sie auf der Seite **Ihre Benachrichtigung benennen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="d3a85-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="d3a85-138">**Name**: Geben Sie einen eindeutigen und beschreibenden Namen ein.</span><span class="sxs-lookup"><span data-stu-id="d3a85-138">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="d3a85-139">Beispielsweise schädliche Dateien in Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="d3a85-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="d3a85-140">**Beschreibung**: Geben Sie eine optionale Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="d3a85-140">**Description**: Type an optional description.</span></span> <span data-ttu-id="d3a85-141">Beispielsweise werden Administratoren benachrichtigt, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="d3a85-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="d3a85-142">**Schweregrad**: lassen Sie den Standardwert **niedrig** ausgewählt, oder wählen Sie **Mittel** oder **hoch**aus.</span><span class="sxs-lookup"><span data-stu-id="d3a85-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="d3a85-143">**Wählen Sie eine Kategorie**aus: Wählen Sie **Threat Management**aus.</span><span class="sxs-lookup"><span data-stu-id="d3a85-143">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="d3a85-144">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d3a85-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d3a85-145">Konfigurieren Sie auf der Seite **Benachrichtigungseinstellungen erstellen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="d3a85-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="d3a85-146">**Worauf möchten Sie warnen?: Aktivität lautet**: Wählen Sie **erkannte Schadsoftware in der Datei**aus.</span><span class="sxs-lookup"><span data-stu-id="d3a85-146">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="d3a85-147">**Wie soll die Warnung ausgelöst werden?**: lassen Sie den Standardwert **jedes Mal, wenn eine Aktivität mit der ausgewählten Regel übereinstimmt** .</span><span class="sxs-lookup"><span data-stu-id="d3a85-147">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="d3a85-148">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d3a85-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d3a85-149">Konfigurieren Sie auf der Seite " **Empfänger festlegen** " die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="d3a85-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="d3a85-150">**E-Mail-Benachrichtigungen senden**: Vergewissern Sie sich, dass diese Einstellung ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d3a85-150">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="d3a85-151">Wählen Sie im Feld **e-Mail-Empfänger** einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheits Leser aus, die eine Benachrichtigung erhalten sollen, wenn eine Schadsoftware erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="d3a85-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="d3a85-152">**Grenzwert für tägliche Benachrichtigungen**: lassen Sie den Standardwert **kein Grenzwert** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="d3a85-152">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="d3a85-153">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d3a85-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="d3a85-154">Überprüfen Sie auf der Seite **Ihre Einstellungen überprüfen** die Einstellungen, und klicken Sie in einem der Abschnitte auf **Bearbeiten** , um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d3a85-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="d3a85-155">Lassen Sie in der Seite möchten **Sie die Richtlinie sofort aktivieren?** den Standardwert **Yes, aktivieren Sie ihn auf der rechten Seite** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d3a85-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="d3a85-156">Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d3a85-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="d3a85-157">Verwenden von Security & Compliance PowerShell zum Erstellen einer Warnungs Richtlinie für erkannte Dateien</span><span class="sxs-lookup"><span data-stu-id="d3a85-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="d3a85-158">Wenn Sie lieber mithilfe von PowerShell dieselbe Warnungs Richtlinie wie im vorherigen Abschnitt beschrieben erstellen möchten, stellen Sie [eine Verbindung mit Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) , und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d3a85-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="d3a85-159">**Hinweis**: der Standardwert für den _Schweregrad_ ist niedrig.</span><span class="sxs-lookup"><span data-stu-id="d3a85-159">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="d3a85-160">Um Mittel oder hoch anzugeben, schließen Sie den _Severity_ -Parameter und den Wert in den Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="d3a85-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="d3a85-161">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="d3a85-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d3a85-162">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="d3a85-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="d3a85-163">Um zu überprüfen, ob Sie ATP für SharePoint, OneDrive und Microsoft Teams erfolgreich aktiviert haben, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d3a85-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="d3a85-164">Wechseln Sie im [Security & Compliance Center](https://protection.office.com)zu Richtlinien für die **Bedrohungs Verwaltung** \> **Policy** \> **ATP-sichere Anlagen**, wählen Sie **globale Einstellungen**aus, und überprüfen Sie den Wert der Einstellung **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="d3a85-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="d3a85-165">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um die Eigenschafteneinstellung zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="d3a85-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="d3a85-166">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="d3a85-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="d3a85-167">Um zu überprüfen, ob Sie Benutzer erfolgreich für das Herunterladen schädlicher Dateien gesperrt haben, öffnen Sie SharePoint Online PowerShell, und führen Sie den folgenden Befehl aus, um den Eigenschaftswert zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="d3a85-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="d3a85-168">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="d3a85-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="d3a85-169">Führen Sie einen der folgenden Schritte aus, um sicherzustellen, dass Sie eine Warnungs Richtlinie für erkannte Dateien erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="d3a85-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="d3a85-170">Wechseln Sie im Security & Compliance **Center zu** Alerts- \> **Warnungs** Richtlinien \> Wählen Sie die Warnungs Richtlinie aus, und überprüfen Sie die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d3a85-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="d3a85-171">Ersetzen Sie in Security & Compliance Center PowerShell \<AlertPolicyName\> durch den Namen der Warnungs Richtlinie, führen Sie den folgenden Befehl aus, und überprüfen Sie die Eigenschaftswerte:</span><span class="sxs-lookup"><span data-stu-id="d3a85-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="d3a85-172">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="d3a85-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="d3a85-173">Verwenden Sie den [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report) , um Informationen zu erkannten Dateien in SharePoint, OneDrive und Microsoft Teams anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d3a85-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="d3a85-174">Insbesondere können Sie die Ansicht **Daten nach: Inhalts- \> Schadsoftware** verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3a85-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
