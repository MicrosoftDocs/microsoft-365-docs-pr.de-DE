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
description: Administratoren erfahren, wie Sie sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktivieren, einschließlich des Festlegens von Warnungen für erkannte Dateien.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 374e67626eab07cc8ab89a52554658a31e661eec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929947"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="96c08-103">Aktivieren von Sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96c08-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="96c08-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="96c08-104">**Applies to**</span></span>
- [<span data-ttu-id="96c08-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="96c08-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="96c08-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96c08-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="96c08-107">Microsoft Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation davor, versehentlich schädliche Dateien freizugeben.</span><span class="sxs-lookup"><span data-stu-id="96c08-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="96c08-108">Weitere Informationen finden Sie unter ["Sichere Anlagen" für SharePoint, OneDrive und Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="96c08-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="96c08-109">Dieser Artikel enthält die Schritte zum Aktivieren und Konfigurieren von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="96c08-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="96c08-110">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="96c08-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="96c08-111">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="96c08-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="96c08-112">Um direkt zur Seite **"Sichere Anlagen"** zu wechseln, öffnen Sie <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="96c08-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="96c08-113">Um sichere Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** im Microsoft 365 Defender-Portal sein.</span><span class="sxs-lookup"><span data-stu-id="96c08-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="96c08-114">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="96c08-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="96c08-115">Um SharePoint Online-PowerShell zu verwenden, um zu verhindern, dass Personen schädliche Dateien herunterladen, müssen Sie Mitglied der Rollen ["Globaler Administrator"](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) oder ["SharePoint"-Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD sein.</span><span class="sxs-lookup"><span data-stu-id="96c08-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="96c08-116">Stellen Sie sicher, dass die Überwachungsprotokollierung für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="96c08-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="96c08-117">Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren der Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="96c08-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="96c08-118">Es kann bis zu 30 Minuten dauern, bis die Einstellungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="96c08-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="96c08-119">Schritt 1: Verwenden des Microsoft 365 Defender-Portals zum Aktivieren von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96c08-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="96c08-120">Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** Für \> **Bedrohungsrichtlinien** sichere \> **Anlagen,** und klicken Sie auf **"Globale Einstellungen".**</span><span class="sxs-lookup"><span data-stu-id="96c08-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="96c08-121">Wechseln Sie in den angezeigten **globalen Einstellungen** zur Einstellung **"Defender für Office 365 aktivieren" für SharePoint, OneDrive und Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="96c08-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="96c08-122">Verschieben Sie den Umschalter nach ![ rechts, ](../../media/scc-toggle-on.png) um sichere Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="96c08-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="96c08-123">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="96c08-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="96c08-124">Verwenden von Exchange Online PowerShell zum Aktivieren von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96c08-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="96c08-125">Wenn Sie lieber PowerShell verwenden möchten, um sichere Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren, [stellen Sie eine Verbindung mit Exchange Online PowerShell her,](/powershell/exchange/connect-to-exchange-online-powershell) und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="96c08-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="96c08-126">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-AtpPolicyForO365".](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="96c08-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="96c08-127">Schritt 2: (Empfohlen) Verwenden sie SharePoint Online-PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen</span><span class="sxs-lookup"><span data-stu-id="96c08-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="96c08-128">Standardmäßig können Benutzer keine schädlichen Dateien öffnen, verschieben, kopieren oder freigeben, die von ATP erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="96c08-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="96c08-129">Sie können jedoch schädliche Dateien löschen und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="96c08-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="96c08-130">Um zu verhindern, dass Benutzer schädliche Dateien herunterladen, [stellen Sie eine Verbindung mit SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) her, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="96c08-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="96c08-131">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="96c08-131">**Notes**:</span></span>

- <span data-ttu-id="96c08-132">Diese Einstellung wirkt sich sowohl auf Benutzer als auch auf Administratoren aus.</span><span class="sxs-lookup"><span data-stu-id="96c08-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="96c08-133">Personen können weiterhin schädliche Dateien löschen.</span><span class="sxs-lookup"><span data-stu-id="96c08-133">People can still delete malicious files.</span></span>

<span data-ttu-id="96c08-134">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SPOTenant".](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="96c08-134">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="96c08-135">Schritt 3 (Empfohlen) Verwenden sie das Microsoft 365 Defender-Portal, um eine Warnungsrichtlinie für erkannte Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="96c08-135">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="96c08-136">Sie können eine Benachrichtigungsrichtlinie erstellen, die Sie und andere Administratoren benachrichtigt, wenn sichere Anlagen für SharePoint, OneDrive und Microsoft Teams eine schädliche Datei erkennt.</span><span class="sxs-lookup"><span data-stu-id="96c08-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="96c08-137">Weitere Informationen zu Warnungen finden Sie unter [Erstellen von Aktivitätswarnungen im Microsoft 365 Defender-Portal.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="96c08-137">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="96c08-138">Wechseln Sie im [Microsoft 365 Defender-Portal](https://security.microsoft.com)zu **Richtlinien &** \> **Regelwarnungsrichtlinie,** oder öffnen Sie <https://security.microsoft.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="96c08-138">In the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="96c08-139">Klicken Sie auf der Seite **"Warnungsrichtlinie"** auf **"Neue Warnungsrichtlinie".**</span><span class="sxs-lookup"><span data-stu-id="96c08-139">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="96c08-140">Der Assistent **für neue Warnungsrichtlinien** wird in einem Flyout geöffnet. Konfigurieren Sie auf der Seite **"Warnung benennen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="96c08-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="96c08-141">**Name:** Geben Sie einen eindeutigen und beschreibenden Namen ein.</span><span class="sxs-lookup"><span data-stu-id="96c08-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="96c08-142">Beispielsweise schädliche Dateien in Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="96c08-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="96c08-143">**Beschreibung:** Geben Sie eine optionale Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="96c08-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="96c08-144">Benachrichtigt Administratoren beispielsweise, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="96c08-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="96c08-145">**Schweregrad:** Lassen Sie den Standardwert **Niedrig** ausgewählt, oder wählen Sie **Mittel** oder **Hoch** aus.</span><span class="sxs-lookup"><span data-stu-id="96c08-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="96c08-146">**Kategorie:** Auswählen **der Bedrohungsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="96c08-146">**Category**: Select **Threat management**.</span></span>

   <span data-ttu-id="96c08-147">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="96c08-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="96c08-148">Konfigurieren Sie auf der Seite **"Warnungseinstellungen erstellen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="96c08-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="96c08-149">**Was möchten Sie warnen?: Aktivität ist:** Wählen Sie **erkannte Schadsoftware in Datei** aus.</span><span class="sxs-lookup"><span data-stu-id="96c08-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="96c08-150">**Wie soll die Warnung ausgelöst werden?**: Behalten Sie den Standardwert **bei, wenn eine Aktivität mit der** ausgewählten Regel übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="96c08-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="96c08-151">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="96c08-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="96c08-152">Konfigurieren Sie auf der Seite **"Empfänger festlegen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="96c08-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="96c08-153">**Senden von E-Mail-Benachrichtigungen:** Überprüfen Sie, ob diese Einstellung ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="96c08-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="96c08-154">Wählen Sie im Feld **"E-Mail-Empfänger"** einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheitsleser aus, die eine Benachrichtigung erhalten sollen, wenn eine schädliche Datei erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="96c08-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="96c08-155">**Grenzwert für tägliche Benachrichtigungen:** Lassen Sie den Standardwert **Kein Grenzwert** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="96c08-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="96c08-156">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="96c08-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="96c08-157">Überprüfen Sie auf der Seite **"Einstellungen überprüfen"** die Einstellungen, und klicken Sie in einem der Abschnitte auf **"Bearbeiten",** um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="96c08-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="96c08-158">Lassen Sie im Abschnitt **Möchten Sie die Richtlinie sofort aktivieren?** den Standardwert **Ja bei, und aktivieren Sie sie sofort.**</span><span class="sxs-lookup"><span data-stu-id="96c08-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="96c08-159">Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="96c08-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="96c08-160">Verwenden von Security & Compliance PowerShell zum Erstellen einer Warnungsrichtlinie für erkannte Dateien</span><span class="sxs-lookup"><span data-stu-id="96c08-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="96c08-161">Wenn Sie lieber PowerShell verwenden möchten, um die gleiche Warnungsrichtlinie wie im vorherigen Abschnitt beschrieben zu erstellen, stellen Sie [eine Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) her, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="96c08-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="96c08-162">**Hinweis:** Der Standardwert _für den Schweregrad_ ist niedrig.</span><span class="sxs-lookup"><span data-stu-id="96c08-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="96c08-163">Um Mittel oder Hoch anzugeben, fügen Sie den Parameter _"Severity"_ und den Wert in den Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="96c08-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="96c08-164">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-ActivityAlert.](/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="96c08-164">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="96c08-165">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="96c08-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="96c08-166">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie sichere Anlagen für SharePoint, OneDrive und Microsoft Teams erfolgreich aktiviert haben:</span><span class="sxs-lookup"><span data-stu-id="96c08-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="96c08-167">Wechseln Sie im [Microsoft 365 Defender-Portal](https://security.microsoft.com)zu **Richtlinien & Regeln** für sichere \> Anlagen für **Bedrohungsrichtlinien,** wählen Sie globale Einstellungen aus, und überprüfen Sie den Wert der Einstellung \>  **"Defender für Office 365 aktivieren" für SharePoint, OneDrive und Microsoft Teams.** </span><span class="sxs-lookup"><span data-stu-id="96c08-167">In the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Policies & rules** \> **Threat Policies** \> **Safe attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="96c08-168">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um die Eigenschafteneinstellung zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="96c08-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="96c08-169">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-AtpPolicyForO365".](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="96c08-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="96c08-170">Öffnen Sie SharePoint Online-PowerShell, und führen Sie den folgenden Befehl aus, um den Eigenschaftswert zu überprüfen, um zu überprüfen, ob Sie Personen erfolgreich am Herunterladen schädlicher Dateien gehindert haben:</span><span class="sxs-lookup"><span data-stu-id="96c08-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="96c08-171">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SPOTenant".](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="96c08-171">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="96c08-172">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Benachrichtigungsrichtlinie für erkannte Dateien erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="96c08-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="96c08-173">Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien &** \> **Regelwarnungsrichtlinie,** \> wählen Sie die Warnungsrichtlinie aus, und überprüfen Sie die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="96c08-173">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="96c08-174">Ersetzen Sie in Microsoft 365 PowerShell des Defender-Portals \<AlertPolicyName\> durch den Namen der Warnungsrichtlinie, führen Sie den folgenden Befehl aus, und überprüfen Sie die Eigenschaftswerte:</span><span class="sxs-lookup"><span data-stu-id="96c08-174">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="96c08-175">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-ActivityAlert".](/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="96c08-175">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="96c08-176">Verwenden Sie den [Bedrohungsschutzstatusbericht,](view-email-security-reports.md#threat-protection-status-report) um Informationen zu erkannten Dateien in SharePoint, OneDrive und Microsoft Teams anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="96c08-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="96c08-177">Insbesondere können Sie die **Ansichtsdaten wie folgt verwenden: \> Inhalts-Schadsoftware-Ansicht.**</span><span class="sxs-lookup"><span data-stu-id="96c08-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>