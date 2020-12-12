---
title: Sichere Dokumente in Microsoft Defender für Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über sichere Dokumente in Microsoft 365 E5 oder Microsoft 365 E5 Security.
ms.openlocfilehash: 0acb5d4ee0c80deebc4d0b040b046d63037037a7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659873"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="a36c8-103">Sichere Dokumente in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a36c8-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a36c8-104">Safe Documents ist ein Feature in Microsoft 365 E5 oder Microsoft 365 E5 Security, das [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der [geschützten Ansicht](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="a36c8-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a36c8-105">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="a36c8-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a36c8-106">Sichere Dokumente sind nur für Benutzer mit *Microsoft 365 E5* -oder *Microsoft 365 E5-Sicherheits* Lizenzen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a36c8-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="a36c8-107">Diese Lizenzen sind nicht in Microsoft Defender für Office 365 Pläne enthalten.</span><span class="sxs-lookup"><span data-stu-id="a36c8-107">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="a36c8-108">Sichere Dokumente werden in Microsoft 365 apps for Enterprise (früher als Office 365 ProPlus bezeichnet) Version 2004 oder höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a36c8-108">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="a36c8-109">Sie öffnen das Security & Compliance Center unter <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="a36c8-109">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="a36c8-110">Um direkt zur Seite **ATP-sichere Anlagen** zu wechseln, öffnen Sie <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="a36c8-110">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="a36c8-111">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a36c8-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a36c8-112">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a36c8-112">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a36c8-113">Zum Konfigurieren von Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="a36c8-113">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a36c8-114">Für den schreibgeschützten Zugriff auf Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppen " **globaler Leser** " oder " **Sicherheits Leser** " sein.</span><span class="sxs-lookup"><span data-stu-id="a36c8-114">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a36c8-115">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a36c8-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="a36c8-116">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="a36c8-116">**Notes**:</span></span>

  - <span data-ttu-id="a36c8-117">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a36c8-117">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a36c8-118">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="a36c8-118">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="a36c8-119">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="a36c8-119">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="a36c8-120">Wie verarbeitet Microsoft Ihre Daten?</span><span class="sxs-lookup"><span data-stu-id="a36c8-120">How does Microsoft handle your data?</span></span>

<span data-ttu-id="a36c8-121">Damit Sie geschützt bleiben, sendet Safe Documents Dateien zur Analyse an den [Microsoft Defender für die Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Wolke.</span><span class="sxs-lookup"><span data-stu-id="a36c8-121">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="a36c8-122">Ausführliche Informationen dazu, wie Microsoft Defender für Endpoint Ihre Daten verarbeitet, finden Sie hier: [Microsoft Defender for Endpoint Data Storage and Privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="a36c8-122">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="a36c8-123">Dateien, die von sicheren Dokumenten gesendet werden, werden in Defender nicht über die für die Analyse erforderliche Zeit hinweg aufbewahrt (in der Regel weniger als 24 Stunden).</span><span class="sxs-lookup"><span data-stu-id="a36c8-123">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="a36c8-124">Konfigurieren sicherer Dokumente mithilfe des Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a36c8-124">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="a36c8-125">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**, und klicken Sie dann auf **globale Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="a36c8-125">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="a36c8-126">Konfigurieren Sie in den angezeigten **globalen Einstellungen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a36c8-126">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a36c8-127">**Aktivieren sicherer Dokumente für Office-Clients**: bewegen Sie die Umschaltfläche nach rechts, um das Feature zu aktivieren: Einschalten ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="a36c8-127">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="a36c8-128">**Personen können durch die geschützte Ansicht klicken, selbst wenn sichere Dokumente die Datei als bösartig Kenn** zeichnen: Es wird empfohlen, diese Option deaktiviert zu lassen (lassen Sie die Umschaltfläche Links: ![ Deaktivieren ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="a36c8-128">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="a36c8-129">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a36c8-129">When you're finished, click **Save**.</span></span>

   ![Einstellungen für sichere Dokumente nach dem auswählen globaler Einstellungen auf der Seite sichere Anlagen.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="a36c8-131">Konfigurieren sicherer Dokumente mithilfe Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a36c8-131">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="a36c8-132">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="a36c8-132">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="a36c8-133">Der Parameter _EnableSafeDocs_ aktiviert oder deaktiviert sichere Dokumente für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="a36c8-133">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="a36c8-134">Der Parameter _AllowSafeDocsOpen_ ermöglicht oder verhindert, dass Benutzer die geschützte Ansicht (also das Öffnen des Dokuments) verlassen, wenn das Dokument als bösartig gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="a36c8-134">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="a36c8-135">In diesem Beispiel werden sichere Dokumente für die gesamte Organisation aktiviert, und es wird verhindert, dass Benutzer Dokumente öffnen, die als "bösartig" aus geschützter Ansicht identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="a36c8-135">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="a36c8-136">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="a36c8-136">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="a36c8-137">Woher weiß ich, dass der Vorgang erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="a36c8-137">How do I know this worked?</span></span>

<span data-ttu-id="a36c8-138">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie sichere Dokumente aktiviert und konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="a36c8-138">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="a36c8-139">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Attachments**, klicken Sie auf **globale Einstellungen**, und überprüfen Sie die **Option sichere Dokumente für Office-Clients aktivieren** , und **ermöglichen Sie den Benutzern, durch die geschützte Ansicht zu klicken, selbst wenn die Datei von sicheren Dokumenten als schädliche Einstellungen identifiziert** wird.</span><span class="sxs-lookup"><span data-stu-id="a36c8-139">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="a36c8-140">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:</span><span class="sxs-lookup"><span data-stu-id="a36c8-140">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="a36c8-141">Die folgenden Dateien sind verfügbar, um den Schutz geschützter Dokumente zu testen.</span><span class="sxs-lookup"><span data-stu-id="a36c8-141">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="a36c8-142">Diese Dokumente ähneln der EICAR.TXT Datei zum Testen von Antischadsoftware-und Antivirenprogramme.</span><span class="sxs-lookup"><span data-stu-id="a36c8-142">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="a36c8-143">Die Dateien sind nicht schädlich, aber Sie werden Schutz für sichere Dokumente auslösen.</span><span class="sxs-lookup"><span data-stu-id="a36c8-143">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="a36c8-144">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="a36c8-144">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="a36c8-145">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="a36c8-145">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="a36c8-146">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="a36c8-146">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
