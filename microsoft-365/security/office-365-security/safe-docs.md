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
description: Erfahren Sie mehr über Tresor Dokumente in Microsoft 365 E5 oder Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1049543b11ad14eeeed596367228f025cc8edd65
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054426"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="1a3b7-103">Sichere Dokumente in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1a3b7-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1a3b7-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="1a3b7-104">**Applies to**</span></span>
- [<span data-ttu-id="1a3b7-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a3b7-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1a3b7-106">Tresor Dokumente sind ein Feature in Microsoft 365 E5 oder Microsoft 365 E5 Security, das [Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Scannen von Dokumenten und Dateien verwendet, die in der [geschützten Ansicht](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) oder in Application Guard für [Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1a3b7-107">Wissenswertes, bevor Sie anfangen</span><span class="sxs-lookup"><span data-stu-id="1a3b7-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1a3b7-108">Tresor Dokumente sind nur für Benutzer mit *Microsoft 365 E5* oder *Microsoft 365 E5 Security* Lizenzen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="1a3b7-109">Diese Lizenzen sind in Microsoft Defender für Office 365 Pläne nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="1a3b7-110">Tresor Dokumente werden in Microsoft 365 Apps for Enterprise (früher als Office 365 ProPlus bezeichnet) Version 2004 oder höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="1a3b7-111">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="1a3b7-112">To go directly to the **Tresor Attachments** page, use <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="1a3b7-112">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="1a3b7-113">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1a3b7-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="1a3b7-114">Sie benötigen Berechtigungen in **Exchange Online,** bevor Sie die Verfahren in diesem Artikel ausführen können:</span><span class="sxs-lookup"><span data-stu-id="1a3b7-114">You need permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="1a3b7-115">Um Tresor Dokumenteinstellungen zu konfigurieren, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="1a3b7-116">Für den schreibgeschützten Zugriff auf Tresor Dokumenteneinstellungen müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="1a3b7-117">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="1a3b7-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="1a3b7-118">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1a3b7-119">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1a3b7-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="1a3b7-120">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="1a3b7-121">Wie behandelt Microsoft Ihre Daten?</span><span class="sxs-lookup"><span data-stu-id="1a3b7-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="1a3b7-122">Um Sie zu schützen, sendet Tresor Dokumente Dateien zur Analyse an die [Microsoft Defender für Endpunkt-Cloud.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="1a3b7-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="1a3b7-123">Details dazu, wie Microsoft Defender für Endpunkt Ihre Daten behandelt, finden Sie hier: [Microsoft Defender für Endpunkt-Datenspeicherung und Datenschutz.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="1a3b7-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="1a3b7-124">Dateien, die von Tresor Dokumente gesendet werden, werden in Defender nicht über die für die Analyse benötigte Zeit hinaus aufbewahrt (in der Regel weniger als 24 Stunden).</span><span class="sxs-lookup"><span data-stu-id="1a3b7-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a><span data-ttu-id="1a3b7-125">Verwenden der Microsoft 365 Defender zum Konfigurieren Tresor Dokumente</span><span class="sxs-lookup"><span data-stu-id="1a3b7-125">Use the Microsoft 365 Defender to configure Safe Documents</span></span>

1. <span data-ttu-id="1a3b7-126">Öffnen Sie das Microsoft 365 Defender Portal, und wechseln Sie zum Abschnitt "Richtlinien für die **E-Mail-& Zusammenarbeit** \> **& Regeln** für \> **Bedrohungsrichtlinien"** Tresor \>  \> **Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="1a3b7-126">Open the Microsoft 365 Defender portal and go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="1a3b7-127">Klicken Sie auf der Seite **Tresor Anlagen** auf **globale Einstellungen.**</span><span class="sxs-lookup"><span data-stu-id="1a3b7-127">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="1a3b7-128">Konfigurieren Sie im angezeigten **Flyout "Globale Einstellungen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1a3b7-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>
   - <span data-ttu-id="1a3b7-129">**Aktivieren Sie Tresor Dokumente für Office Clients:** Verschieben Sie die Umschaltfläche nach rechts, um das Feature zu aktivieren: ![ Umschalten. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="1a3b7-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="1a3b7-130">**Zulassen, dass Benutzer durch die geschützte Ansicht klicken, auch wenn Tresor Dokumente die Datei als bösartig identifiziert** haben: Es wird empfohlen, diese Option deaktiviert zu lassen (lassen Sie die Umschaltfläche links: ![ Umschaltfläche ](../../media/scc-toggle-off.png) deaktivieren).</span><span class="sxs-lookup"><span data-stu-id="1a3b7-130">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="1a3b7-131">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-131">When you're finished, click **Save**.</span></span>

   ![Tresor Dokumentiert die Einstellungen nach der Auswahl der globalen Einstellungen auf der Seite Tresor Anlagen.](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="1a3b7-133">Verwenden von Exchange Online PowerShell zum Konfigurieren Tresor Dokumente</span><span class="sxs-lookup"><span data-stu-id="1a3b7-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="1a3b7-134">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="1a3b7-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="1a3b7-135">Der _Parameter EnableSafeDocs_ aktiviert oder deaktiviert Tresor Dokumente für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="1a3b7-136">Der _Parameter AllowSafeDocsOpen_ ermöglicht oder verhindert, dass Benutzer die geschützte Ansicht verlassen (d. h. das Dokument öffnen), wenn das Dokument als bösartig erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="1a3b7-137">In diesem Beispiel wird Tresor Dokumente für die gesamte Organisation aktiviert und verhindert, dass Benutzer Dokumente öffnen, die als bösartig aus der geschützten Ansicht identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="1a3b7-138">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-AtpPolicyForO365".](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="1a3b7-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="1a3b7-139">Onboarding in den Microsoft Defender für Endpunktdienst zum Aktivieren von Überwachungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="1a3b7-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="1a3b7-140">Um Microsoft Defender für Endpunkt bereitzustellen, müssen Sie die verschiedenen Phasen der Bereitstellung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="1a3b7-141">Nach dem Onboarding können Sie Überwachungsfunktionen im Microsoft 365 Defender-Portal konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-141">After onboarding, you can configure auditing capabilities in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="1a3b7-142">Weitere Informationen finden Sie unter [Onboarding für den Microsoft Defender für Endpunkt-Dienst.](/microsoft-365/security/defender-endpoint/onboarding)</span><span class="sxs-lookup"><span data-stu-id="1a3b7-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="1a3b7-143">Wenn Sie zusätzliche Hilfe benötigen, finden Sie informationen zur Problembehandlung bei Problemen beim [Onboarding von Microsoft Defender für Endpunkten.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="1a3b7-143">If you need additional help, refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="1a3b7-144">Woher weiß ich, dass der Vorgang erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="1a3b7-144">How do I know this worked?</span></span>

<span data-ttu-id="1a3b7-145">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Tresor Dokumente aktiviert und konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="1a3b7-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="1a3b7-146">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Tresor "Attachments** \> **Global"-Einstellungen,** und überprüfen Sie die Option **"Tresor Dokumente für Office Clients aktivieren",** und ermöglichen Sie Es Personen, durch die geschützte Ansicht zu **klicken, auch wenn Tresor Dokumente die Datei als schädliche** Einstellungen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments** \> **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="1a3b7-147">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:</span><span class="sxs-lookup"><span data-stu-id="1a3b7-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="1a3b7-148">Die folgenden Dateien stehen zum Testen Tresor Dokumentenschutz zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="1a3b7-149">Diese Dokumente ähneln der EICAR.TXT-Datei zum Testen von Antischadsoftware- und Antivirenlösungen.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="1a3b7-150">Die Dateien sind nicht schädlich, lösen jedoch Tresor Dokumentenschutz aus.</span><span class="sxs-lookup"><span data-stu-id="1a3b7-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="1a3b7-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="1a3b7-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="1a3b7-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="1a3b7-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="1a3b7-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="1a3b7-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
