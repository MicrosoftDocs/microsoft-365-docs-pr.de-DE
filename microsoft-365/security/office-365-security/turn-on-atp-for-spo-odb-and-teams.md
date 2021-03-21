---
title: Aktivieren von Sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Administratoren erfahren, wie Sie sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktivieren, einschließlich der Einrichtung von Warnungen für erkannte Dateien.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 300cb3e004010e8ff22de7393d3f3e039bf8cfdd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921144"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7acb5-103">Aktivieren von Sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7acb5-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7acb5-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="7acb5-104">**Applies to**</span></span>
- [<span data-ttu-id="7acb5-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="7acb5-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="7acb5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7acb5-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="7acb5-107">Microsoft Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien.</span><span class="sxs-lookup"><span data-stu-id="7acb5-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="7acb5-108">Weitere Informationen finden Sie unter [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7acb5-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="7acb5-109">Dieser Artikel enthält die Schritte zum Aktivieren und Konfigurieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7acb5-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7acb5-110">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="7acb5-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7acb5-111">Sie öffnen das Security & Compliance Center unter <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="7acb5-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="7acb5-112">Öffnen Sie , um direkt zur **Seite "ATP-sichere Anlagen" zu** <https://protection.office.com/safeattachmentv2> wechseln.</span><span class="sxs-lookup"><span data-stu-id="7acb5-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="7acb5-113">Um sichere Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren, müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder Sicherheitsadministrator im Security & Compliance Center sein. </span><span class="sxs-lookup"><span data-stu-id="7acb5-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="7acb5-114">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7acb5-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7acb5-115">Um SharePoint Online PowerShell zu verwenden, um zu verhindern, dass Personen schädliche Dateien herunterladen, müssen Sie Mitglied der Rollen [globaler](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) Administrator oder [SharePoint-Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD sein.</span><span class="sxs-lookup"><span data-stu-id="7acb5-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="7acb5-116">Stellen Sie sicher, dass die Überwachungsprotokollierung für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7acb5-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="7acb5-117">Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren der Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="7acb5-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="7acb5-118">Bis zu 30 Minuten, bis die Einstellungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="7acb5-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7acb5-119">Schritt 1: Aktivieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams mithilfe des Security & Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="7acb5-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="7acb5-120">Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung \>  \> **ATP Sichere** Anlagen, und klicken Sie auf **Globale Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="7acb5-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="7acb5-121">Wechseln Sie **in der** angezeigten Globalen Einstellungen zur Einstellung Defender für **Office 365 für SharePoint, OneDrive** und Microsoft Teams aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7acb5-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="7acb5-122">Verschieben Sie den Umschalter nach rechts, um sichere Anlagen für ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive und Microsoft Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7acb5-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="7acb5-123">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7acb5-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7acb5-124">Aktivieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams mithilfe von Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="7acb5-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="7acb5-125">Wenn Sie lieber PowerShell verwenden möchten, um sichere Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren, stellen Sie eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) sicher, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7acb5-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="7acb5-126">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="7acb5-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="7acb5-127">Schritt 2: (Empfohlen) Verwenden von SharePoint Online PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen</span><span class="sxs-lookup"><span data-stu-id="7acb5-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="7acb5-128">Standardmäßig können Benutzer schädliche Dateien, die von ATP erkannt werden, nicht öffnen, verschieben, kopieren oder freigeben.</span><span class="sxs-lookup"><span data-stu-id="7acb5-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="7acb5-129">Sie können jedoch schädliche Dateien löschen und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="7acb5-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="7acb5-130">Um zu verhindern, dass Benutzer schädliche Dateien herunterladen, stellen Sie eine Verbindung mit [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) bereit, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7acb5-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="7acb5-131">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="7acb5-131">**Notes**:</span></span>

- <span data-ttu-id="7acb5-132">Diese Einstellung wirkt sich sowohl auf Benutzer als auch auf Administratoren aus.</span><span class="sxs-lookup"><span data-stu-id="7acb5-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="7acb5-133">Personen können weiterhin schädliche Dateien löschen.</span><span class="sxs-lookup"><span data-stu-id="7acb5-133">People can still delete malicious files.</span></span>

<span data-ttu-id="7acb5-134">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="7acb5-134">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="7acb5-135">Schritt 3 (empfohlen) Verwenden des Security & Compliance Center zum Erstellen einer Warnungsrichtlinie für erkannte Dateien</span><span class="sxs-lookup"><span data-stu-id="7acb5-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="7acb5-136">Sie können eine Warnungsrichtlinie erstellen, die Sie und andere Administratoren benachrichtigt, wenn sichere Anlagen für SharePoint, OneDrive und Microsoft Teams eine schädliche Datei erkennen.</span><span class="sxs-lookup"><span data-stu-id="7acb5-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="7acb5-137">Weitere Informationen zu Warnungen finden Sie unter [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="7acb5-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="7acb5-138">Wechseln Sie [im Security & Compliance Center](https://protection.office.com)zu Warnungsbenachrichtigungsrichtlinien, oder öffnen Sie  \>  <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="7acb5-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="7acb5-139">Klicken Sie **auf der Seite Warnungsrichtlinien** auf **Neue Warnungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7acb5-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="7acb5-140">Der **Assistent für neue** Benachrichtigungsrichtlinien wird in einem Fly-Out geöffnet. Konfigurieren Sie **auf der Seite** Warnung benennen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="7acb5-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="7acb5-141">**Name**: Geben Sie einen eindeutigen und beschreibenden Namen ein.</span><span class="sxs-lookup"><span data-stu-id="7acb5-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="7acb5-142">Beispiel: Bösartige Dateien in Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="7acb5-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="7acb5-143">**Beschreibung**: Geben Sie eine optionale Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="7acb5-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="7acb5-144">Beispielsweise werden Administratoren benachrichtigt, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="7acb5-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="7acb5-145">**Schweregrad**: Lassen Sie den Standardwert **Niedrig** ausgewählt, oder wählen Sie **Mittel oder** **Hoch aus.**</span><span class="sxs-lookup"><span data-stu-id="7acb5-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="7acb5-146">**Wählen Sie eine Kategorie** aus: Wählen **Sie Bedrohungsverwaltung aus.**</span><span class="sxs-lookup"><span data-stu-id="7acb5-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="7acb5-147">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7acb5-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7acb5-148">Konfigurieren Sie auf der Seite **Warnungseinstellungen** erstellen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="7acb5-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="7acb5-149">**Was möchten Sie warnen?: Aktivität ist**: Wählen Sie **Erkannte Schadsoftware in Datei aus.**</span><span class="sxs-lookup"><span data-stu-id="7acb5-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="7acb5-150">**Wie soll die Warnung ausgelöst werden?**: Lassen Sie den Standardwert Jedes Mal, wenn **eine Aktivität der ausgewählten Regel** entspricht.</span><span class="sxs-lookup"><span data-stu-id="7acb5-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="7acb5-151">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7acb5-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7acb5-152">Konfigurieren Sie **auf der Seite** Empfänger festlegen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="7acb5-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="7acb5-153">**E-Mail-Benachrichtigungen** senden: Überprüfen Sie, ob diese Einstellung ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="7acb5-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="7acb5-154">Wählen Sie im Feld E-Mail-Empfänger einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheitsleser aus, die Benachrichtigungen erhalten sollen, wenn eine schädliche Datei erkannt wird. </span><span class="sxs-lookup"><span data-stu-id="7acb5-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="7acb5-155">**Tägliches Benachrichtigungslimit**: Den Standardwert **Keine Grenze ausgewählt** lassen.</span><span class="sxs-lookup"><span data-stu-id="7acb5-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="7acb5-156">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7acb5-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7acb5-157">Überprüfen Sie **auf der Seite** Einstellungen überprüfen die Einstellungen, und klicken Sie in einem der Abschnitte auf Bearbeiten, um Änderungen vorzunehmen. </span><span class="sxs-lookup"><span data-stu-id="7acb5-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="7acb5-158">Lassen Sie im Abschnitt Möchten Sie die Richtlinie sofort **aktivieren?** den Standardwert **Ja,** aktivieren Sie sie sofort aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7acb5-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="7acb5-159">Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="7acb5-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="7acb5-160">Erstellen einer & für erkannte Dateien mithilfe von Security & Compliance PowerShell</span><span class="sxs-lookup"><span data-stu-id="7acb5-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="7acb5-161">Wenn Sie lieber PowerShell verwenden möchten, um dieselbe Warnungsrichtlinie wie im vorherigen Abschnitt beschrieben zu erstellen, stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) auf, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7acb5-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="7acb5-162">**Hinweis:** Der Standardwert _für den Schweregrad_ ist Niedrig.</span><span class="sxs-lookup"><span data-stu-id="7acb5-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="7acb5-163">Um Medium oder High anzugeben, schließen Sie den _Parameter Severity_ und den Wert in den Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="7acb5-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="7acb5-164">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="7acb5-164">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7acb5-165">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="7acb5-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="7acb5-166">Verwenden Sie einen der folgenden Schritte, um sicherzustellen, dass Sie sichere Anlagen für SharePoint, OneDrive und Microsoft Teams erfolgreich aktiviert haben:</span><span class="sxs-lookup"><span data-stu-id="7acb5-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="7acb5-167">Wechseln Sie [im Security & Compliance](https://protection.office.com)  Center zu Bedrohungsverwaltungsrichtlinie ATP Sichere Anlagen, wählen Sie Globale Einstellungen aus, und überprüfen Sie den Wert der Einstellung Aktivieren von \>  \> Defender für **Office 365 für SharePoint, OneDrive** und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7acb5-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="7acb5-168">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um die Eigenschafteneinstellung zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7acb5-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="7acb5-169">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="7acb5-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="7acb5-170">Öffnen Sie SharePoint Online PowerShell, und führen Sie den folgenden Befehl aus, um sicherzustellen, dass Personen erfolgreich das Herunterladen schädlicher Dateien blockiert haben, um den Eigenschaftswert zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7acb5-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="7acb5-171">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="7acb5-171">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="7acb5-172">Verwenden Sie einen der folgenden Schritte, um zu überprüfen, ob Sie eine Warnungsrichtlinie für erkannte Dateien erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="7acb5-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="7acb5-173">Wechseln Sie im Security & Compliance Center **zu** Warnungsbenachrichtigungsrichtlinien wählen Sie die Warnungsrichtlinie aus, und überprüfen Sie die \>  \> Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7acb5-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="7acb5-174">Ersetzen Sie & Security & Compliance Center PowerShell durch den Namen der Warnungsrichtlinie, führen Sie den folgenden Befehl aus, und überprüfen Sie \<AlertPolicyName\> die Eigenschaftswerte:</span><span class="sxs-lookup"><span data-stu-id="7acb5-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="7acb5-175">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="7acb5-175">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="7acb5-176">Verwenden Sie [den Statusbericht zum Bedrohungsschutz,](view-email-security-reports.md#threat-protection-status-report) um Informationen zu erkannten Dateien in SharePoint, OneDrive und Microsoft Teams anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="7acb5-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="7acb5-177">Insbesondere können Sie die Ansicht von Daten **verwenden, indem Sie die Ansicht "Content \> Malware"** verwenden.</span><span class="sxs-lookup"><span data-stu-id="7acb5-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>