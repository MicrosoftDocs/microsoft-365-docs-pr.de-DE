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
description: Administratoren können erfahren, wie sie Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams aktivieren, einschließlich des Festlegens von Warnungen für erkannte Dateien.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083092"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ad3e8-103">Aktivieren von Sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad3e8-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ad3e8-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ad3e8-104">**Applies to**</span></span>
- [<span data-ttu-id="ad3e8-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="ad3e8-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ad3e8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad3e8-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ad3e8-107">Microsoft Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation davor, versehentlich schädliche Dateien freizugeben.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="ad3e8-108">Weitere Informationen finden Sie unter [Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="ad3e8-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="ad3e8-109">Dieser Artikel enthält die Schritte zum Aktivieren und Konfigurieren von Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ad3e8-110">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="ad3e8-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ad3e8-111">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="ad3e8-112">Um direkt zur **Seite Tresor Anlagen** zu wechseln, öffnen Sie <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="ad3e8-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="ad3e8-113">Um Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** im Microsoft 365 Defender-Portal sein.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="ad3e8-114">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="ad3e8-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="ad3e8-115">Um SharePoint Online-PowerShell zu verwenden, um zu verhindern, dass Personen schädliche Dateien herunterladen, müssen Sie Mitglied der Rollen ["Globaler Administrator"](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) oder ["SharePoint"-Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD sein.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="ad3e8-116">Stellen Sie sicher, dass die Überwachungsprotokollierung für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="ad3e8-117">Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren der Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="ad3e8-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="ad3e8-118">Es kann bis zu 30 Minuten dauern, bis die Einstellungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ad3e8-119">Schritt 1: Verwenden des Microsoft 365 Defender Portals zum Aktivieren von Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad3e8-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="ad3e8-120">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Richtlinien** für \>  \> **Bedrohungsrichtlinien** \> **Tresor Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="ad3e8-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ad3e8-121">Klicken Sie auf der Seite **Tresor Anlagen** auf **globale Einstellungen.**</span><span class="sxs-lookup"><span data-stu-id="ad3e8-121">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="ad3e8-122">Wechseln Sie in den angezeigten **globalen Einstellungen** zum Abschnitt **"Dateien schützen" in SharePoint, OneDrive und Microsoft Teams** Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-122">In the **Global settings** fly out that appears, go to the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section.</span></span>

   <span data-ttu-id="ad3e8-123">Aktivieren Sie **defender für Office 365 für SharePoint, OneDrive und Microsoft Teams** umschalten nach rechts, ![ um Tresor Anlagen für ](../../media/scc-toggle-on.png) SharePoint, OneDrive und Microsoft Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-123">Move the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="ad3e8-124">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-124">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ad3e8-125">Verwenden sie Exchange Online PowerShell, um Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-125">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="ad3e8-126">Wenn Sie Lieber PowerShell verwenden möchten, um Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren, [stellen Sie eine Verbindung mit Exchange Online PowerShell her,](/powershell/exchange/connect-to-exchange-online-powershell) und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-126">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="ad3e8-127">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-AtpPolicyForO365".](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="ad3e8-127">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="ad3e8-128">Schritt 2: (Empfohlen) Verwenden Sie SharePoint Online-PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen</span><span class="sxs-lookup"><span data-stu-id="ad3e8-128">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="ad3e8-129">Standardmäßig können Benutzer keine schädlichen Dateien öffnen, verschieben, kopieren oder freigeben, <sup>\*</sup> die von Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-129">By default, users can't open, move, copy, or share<sup>\*</sup> malicious files that are detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="ad3e8-130">Sie können jedoch schädliche Dateien löschen und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-130">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="ad3e8-131"><sup>\*</sup> Wenn Benutzer zu **"Zugriff verwalten"** wechseln, ist die Option **"Freigeben"** weiterhin verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-131"><sup>\*</sup> If users go to **Manage access**, the **Share** option is still available.</span></span>

<span data-ttu-id="ad3e8-132">Um zu verhindern, dass Benutzer schädliche Dateien herunterladen, [stellen Sie eine Verbindung mit SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) her, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-132">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="ad3e8-133">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-133">**Notes**:</span></span>

- <span data-ttu-id="ad3e8-134">Diese Einstellung wirkt sich sowohl auf Benutzer als auch auf Administratoren aus.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-134">This setting affects both users and admins.</span></span>
- <span data-ttu-id="ad3e8-135">Personen können weiterhin schädliche Dateien löschen.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-135">People can still delete malicious files.</span></span>

<span data-ttu-id="ad3e8-136">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SPOTenant".](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="ad3e8-136">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="ad3e8-137">Schritt 3 (Empfohlen) Verwenden Sie das Microsoft 365 Defender Portal, um eine Warnungsrichtlinie für erkannte Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-137">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="ad3e8-138">Sie können eine Warnungsrichtlinie erstellen, die Sie und andere Administratoren benachrichtigt, wenn Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams eine schädliche Datei erkennt.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-138">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="ad3e8-139">Weitere Informationen zu Warnungen finden Sie unter [Erstellen von Aktivitätswarnungen im Microsoft 365 Defender Portal.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="ad3e8-139">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="ad3e8-140">Wechseln Sie im portal Microsoft 365 Defender zu **Richtlinien &** \> **Regelwarnungsrichtlinie,** oder öffnen Sie <https://security.microsoft.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="ad3e8-140">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="ad3e8-141">Klicken Sie auf der Seite **"Warnungsrichtlinie"** auf **"Neue Warnungsrichtlinie".**</span><span class="sxs-lookup"><span data-stu-id="ad3e8-141">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="ad3e8-142">Der Assistent **für neue Warnungsrichtlinien** wird in einem Flyout geöffnet. Konfigurieren Sie auf der Seite **"Warnung benennen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-142">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>
   - <span data-ttu-id="ad3e8-143">**Name:** Geben Sie einen eindeutigen und beschreibenden Namen ein.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-143">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="ad3e8-144">Beispielsweise schädliche Dateien in Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-144">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="ad3e8-145">**Beschreibung:** Geben Sie eine optionale Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-145">**Description**: Type an optional description.</span></span> <span data-ttu-id="ad3e8-146">Benachrichtigt Administratoren beispielsweise, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-146">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="ad3e8-147">**Schweregrad:** Wählen Sie **"Niedrig",** **"Mittel"** oder **"Hoch"** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-147">**Severity**: Select **Low**, **Medium**, or **High** from the drop down list.</span></span>
   - <span data-ttu-id="ad3e8-148">**Kategorie:** Wählen Sie **die Bedrohungsverwaltung** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-148">**Category**: Select **Threat management** from the drop down list.</span></span>

   <span data-ttu-id="ad3e8-149">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ad3e8-150">Konfigurieren Sie auf der Seite **"Warnungseinstellungen erstellen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-150">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="ad3e8-151">**Wozu möchten Sie eine Warnung erstellen?** Section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-151">**What do you want to alert on?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span></span>
   - <span data-ttu-id="ad3e8-152">**Wie soll die Warnung ausgelöst werden?** section: Leave the default value **Every time an activity matches the rule** selected.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-152">**How do you want the alert to be triggered?** section: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="ad3e8-153">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ad3e8-154">Konfigurieren Sie auf der Seite **"Empfänger festlegen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-154">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="ad3e8-155">Überprüfen Sie, ob **"E-Mail-Benachrichtigungen senden"** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-155">Verify **Send email notifications** is selected.</span></span> <span data-ttu-id="ad3e8-156">Wählen Sie im Feld **"E-Mail-Empfänger"** einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheitsleser aus, die eine Benachrichtigung erhalten sollen, wenn eine schädliche Datei erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-156">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="ad3e8-157">**Grenzwert für tägliche Benachrichtigungen:** Lassen Sie den Standardwert **Kein Grenzwert** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-157">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="ad3e8-158">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-158">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="ad3e8-159">Überprüfen Sie auf der Seite **"Einstellungen überprüfen"** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-159">On the **Review your settings** page, review your settings.</span></span> <span data-ttu-id="ad3e8-160">Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-160">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="ad3e8-161">Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-161">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="ad3e8-162">Lassen Sie im Abschnitt **Möchten Sie die Richtlinie sofort aktivieren?** den Standardwert **Ja bei, und aktivieren Sie sie sofort.**</span><span class="sxs-lookup"><span data-stu-id="ad3e8-162">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="ad3e8-163">Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-163">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="ad3e8-164">Verwenden von Security & Compliance PowerShell zum Erstellen einer Warnungsrichtlinie für erkannte Dateien</span><span class="sxs-lookup"><span data-stu-id="ad3e8-164">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="ad3e8-165">Wenn Sie lieber PowerShell verwenden möchten, um die gleiche Warnungsrichtlinie wie im vorherigen Abschnitt beschrieben zu erstellen, stellen Sie [eine Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) her, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-165">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="ad3e8-166">**Hinweis:** Der Standardwert _für den Schweregrad_ ist niedrig.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-166">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="ad3e8-167">Um Mittel oder Hoch anzugeben, fügen Sie den Parameter _"Severity"_ und den Wert in den Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-167">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="ad3e8-168">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-ActivityAlert.](/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="ad3e8-168">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ad3e8-169">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="ad3e8-169">How do you know these procedures worked?</span></span>

- <span data-ttu-id="ad3e8-170">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams erfolgreich aktiviert haben:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-170">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="ad3e8-171">Wechseln Sie im portal Microsoft 365 Defender zu **Richtlinien &** Richtlinien für \>  \> **Bedrohungsrichtlinien** \> **Tresor Anlagen,** wählen Sie **globale Einstellungen** aus, und überprüfen Sie den Wert der Einstellung "Defender für Office 365 aktivieren" **für SharePoint, OneDrive und Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="ad3e8-171">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="ad3e8-172">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um die Eigenschafteneinstellung zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-172">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="ad3e8-173">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-AtpPolicyForO365".](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="ad3e8-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="ad3e8-174">Öffnen Sie SharePoint Online-PowerShell, und führen Sie den folgenden Befehl aus, um den Eigenschaftswert zu überprüfen, um zu überprüfen, ob Sie personen erfolgreich am Herunterladen schädlicher Dateien gehindert haben:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-174">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="ad3e8-175">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SPOTenant".](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="ad3e8-175">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="ad3e8-176">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Benachrichtigungsrichtlinie für erkannte Dateien erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-176">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>
  - <span data-ttu-id="ad3e8-177">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Regeln,** um die \> **Warnungsrichtlinie** \> auszuwählen, und überprüfen Sie die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-177">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>
  - <span data-ttu-id="ad3e8-178">Ersetzen Sie in Microsoft 365 Defender PowerShell-Portal \<AlertPolicyName\> durch den Namen der Warnungsrichtlinie, führen Sie den folgenden Befehl aus, und überprüfen Sie die Eigenschaftswerte:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-178">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="ad3e8-179">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-ActivityAlert".](/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="ad3e8-179">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="ad3e8-180">Verwenden Sie den [Bedrohungsschutzstatusbericht,](view-email-security-reports.md#threat-protection-status-report) um Informationen zu erkannten Dateien in SharePoint, OneDrive und Microsoft Teams anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-180">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="ad3e8-181">Insbesondere können Sie die **Ansichtsdaten wie folgt verwenden: \> Inhalts-Schadsoftware-Ansicht.**</span><span class="sxs-lookup"><span data-stu-id="ad3e8-181">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
