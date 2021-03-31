---
title: Sichere Dokumente in Microsoft Defender für Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über sichere Dokumente in Microsoft 365 E5 oder Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78ae99158e30046923d24897e7ab9b45adff31d0
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445396"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="e8f1d-103">Sichere Dokumente in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e8f1d-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e8f1d-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="e8f1d-104">**Applies to**</span></span>
- [<span data-ttu-id="e8f1d-105">Microsoft Defender für Office 365 – Plan 2</span><span class="sxs-lookup"><span data-stu-id="e8f1d-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e8f1d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8f1d-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e8f1d-107">Sichere Dokumente ist ein Feature in Microsoft 365 E5 oder Microsoft 365 E5 Security, das [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der geschützten Ansicht oder in Application Guard für [Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)geöffnet sind. [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="e8f1d-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e8f1d-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="e8f1d-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e8f1d-109">Sichere Dokumente sind nur für Benutzer mit *Microsoft 365 E5-* oder *Microsoft 365 E5-Sicherheitslizenzen* verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="e8f1d-110">Diese Lizenzen sind nicht in Microsoft Defender für Office 365-Pläne enthalten.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="e8f1d-111">Sichere Dokumente werden in Microsoft 365 Apps for Enterprise (früher als Office 365 ProPlus bezeichnet) Version 2004 oder höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="e8f1d-112">Sie öffnen das Security & Compliance Center unter <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="e8f1d-113">Öffnen Sie , um direkt zur **Seite "ATP-sichere Anlagen" zu** <https://protection.office.com/safeattachmentv2> wechseln.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="e8f1d-114">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e8f1d-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e8f1d-115">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen in **Exchange Online** Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="e8f1d-115">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e8f1d-116">Zum Konfigurieren der Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e8f1d-117">Für den schreibgeschützten Zugriff auf Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e8f1d-118">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="e8f1d-118">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="e8f1d-119">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e8f1d-120">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e8f1d-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="e8f1d-121">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-121">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="e8f1d-122">Wie geht Microsoft mit Ihren Daten um?</span><span class="sxs-lookup"><span data-stu-id="e8f1d-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="e8f1d-123">Um Sie zu schützen, sendet Safe Documents Dateien zur Analyse an die [Microsoft Defender for Endpoint-Cloud.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="e8f1d-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="e8f1d-124">Details dazu, wie Microsoft Defender for Endpoint Ihre Daten verarbeitet, finden Sie hier: [Microsoft Defender for Endpoint Datenspeicherung und Datenschutz.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="e8f1d-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="e8f1d-125">Von sicheren Dokumenten gesendete Dateien werden in Defender nicht über die für die Analyse benötigte Zeit (in der Regel weniger als 24 Stunden) aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="e8f1d-126">Konfigurieren sicherer Dokumente mithilfe & Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e8f1d-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="e8f1d-127">Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung \>  \> **ATP Sichere** Anlagen, und klicken Sie dann auf **Globale Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="e8f1d-128">Konfigurieren Sie **im angezeigten** Fly-Out der globalen Einstellungen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="e8f1d-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e8f1d-129">**Aktivieren Sie sichere Dokumente für Office-Clients:** Verschieben Sie die Umschalte nach rechts, um das Feature zu aktivieren: ![ Umschalten auf ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="e8f1d-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="e8f1d-130">**Zulassen,** dass Personen durch die geschützte Ansicht klicken, auch wenn sichere Dokumente die Datei als schädlich identifizieren: Es wird empfohlen, diese Option deaktiviert zu lassen (lassen Sie die Umschalte nach links: ![ Umschalten ](../../media/scc-toggle-off.png) aus ).</span><span class="sxs-lookup"><span data-stu-id="e8f1d-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="e8f1d-131">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-131">When you're finished, click **Save**.</span></span>

   ![Einstellungen für sichere Dokumente nach Auswahl der globalen Einstellungen auf der Seite Sichere Anlagen.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="e8f1d-133">Konfigurieren sicherer Dokumente mithilfe von Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8f1d-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="e8f1d-134">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="e8f1d-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="e8f1d-135">Der _Parameter EnableSafeDocs_ aktiviert oder deaktiviert sichere Dokumente für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="e8f1d-136">Der _Parameter AllowSafeDocsOpen_ ermöglicht oder verhindert, dass Benutzer die geschützte Ansicht verlassen (d. h. das Dokument öffnen), wenn das Dokument als schadhaft identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="e8f1d-137">In diesem Beispiel werden sichere Dokumente für die gesamte Organisation aktiviert und verhindert, dass Benutzer Dokumente öffnen, die in der geschützten Ansicht als bösartig identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="e8f1d-138">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="e8f1d-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="e8f1d-139">Onboarding im Microsoft Defender for Endpoint Service, um Überwachungsfunktionen zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="e8f1d-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="e8f1d-140">Um Microsoft Defender for Endpoint bereitstellen zu können, müssen Sie die verschiedenen Phasen der Bereitstellung durchgehen.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="e8f1d-141">Nach dem Onboarding können Sie die Überwachungsfunktionen im Security & Compliance Center konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-141">After onboarding, you can configure auditing capabilities in the Security & Compliance Center.</span></span>

<span data-ttu-id="e8f1d-142">Weitere Informationen finden Sie [unter Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span><span class="sxs-lookup"><span data-stu-id="e8f1d-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="e8f1d-143">Wenn Sie zusätzliche Hilfe benötigen, lesen Sie [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="e8f1d-143">If you need additional help, please refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="e8f1d-144">Woher weiß ich, dass der Vorgang erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="e8f1d-144">How do I know this worked?</span></span>

<span data-ttu-id="e8f1d-145">Gehen Sie wie folgt vor, um zu überprüfen, ob Sie sichere Dokumente aktiviert und konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="e8f1d-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="e8f1d-146">Wechseln Sie im Security & Compliance  Center zu Bedrohungsverwaltungsrichtlinie \>  \> **ATP**    Sichere Anlagen, klicken Sie auf Globale Einstellungen, und überprüfen Sie die Schaltfläche Sichere Dokumente für Office-Clients aktivieren und Personen das Klicken auf geschützte Ansicht erlauben, auch wenn sichere Dokumente die Datei als schädliche Einstellungen identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="e8f1d-147">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:</span><span class="sxs-lookup"><span data-stu-id="e8f1d-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="e8f1d-148">Die folgenden Dateien stehen zum Testen des Schutzes sicherer Dokumente zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="e8f1d-149">Diese Dokumente ähneln der EICAR.TXT zum Testen von An malware- und Antivirenlösungen.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="e8f1d-150">Die Dateien sind nicht schädlich, lösen aber schutz vor sicheren Dokumenten aus.</span><span class="sxs-lookup"><span data-stu-id="e8f1d-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="e8f1d-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="e8f1d-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="e8f1d-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="e8f1d-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="e8f1d-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="e8f1d-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
