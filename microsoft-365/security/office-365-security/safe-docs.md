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
ms.openlocfilehash: 7fbee440298aea3609665b62a946ae3ce2857e37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845480"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="d3b94-103">Sichere Dokumente in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d3b94-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d3b94-104">Safe Documents ist ein Feature in Microsoft 365 E5 oder Microsoft 365 E5 Security, das [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der [geschützten Ansicht](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="d3b94-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d3b94-105">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="d3b94-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d3b94-106">Sichere Dokumente sind nur für Benutzer mit *Microsoft 365 E5* -oder *Microsoft 365 E5-Sicherheits* Lizenzen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d3b94-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="d3b94-107">Diese Lizenzen sind nicht in Microsoft Defender für Office 365 Pläne enthalten.</span><span class="sxs-lookup"><span data-stu-id="d3b94-107">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="d3b94-108">Sichere Dokumente werden in Microsoft 365 apps for Enterprise (früher als Office 365 ProPlus bezeichnet) Version 2004 oder höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d3b94-108">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="d3b94-109">Sie öffnen das Security & Compliance Center unter <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="d3b94-109">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="d3b94-110">Um direkt zur Seite **ATP-sichere Anlagen** zu wechseln, öffnen Sie <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="d3b94-110">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="d3b94-111">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d3b94-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="d3b94-112">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Thema ausführen können.</span><span class="sxs-lookup"><span data-stu-id="d3b94-112">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="d3b94-113">Um sichere Dokumente zu aktivieren und zu konfigurieren, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="d3b94-113">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="d3b94-114">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d3b94-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="d3b94-115">Wie verarbeitet Microsoft Ihre Daten?</span><span class="sxs-lookup"><span data-stu-id="d3b94-115">How does Microsoft handle your data?</span></span>

<span data-ttu-id="d3b94-116">Damit Sie geschützt bleiben, sendet Safe Documents Dateien zur Analyse an den [Microsoft Defender für die Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Wolke.</span><span class="sxs-lookup"><span data-stu-id="d3b94-116">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="d3b94-117">Ausführliche Informationen dazu, wie Microsoft Defender für Endpoint Ihre Daten verarbeitet, finden Sie hier: [Microsoft Defender for Endpoint Data Storage and Privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="d3b94-117">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="d3b94-118">Dateien, die von sicheren Dokumenten gesendet werden, werden in Defender nicht über die für die Analyse erforderliche Zeit hinweg aufbewahrt (in der Regel weniger als 24 Stunden).</span><span class="sxs-lookup"><span data-stu-id="d3b94-118">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="d3b94-119">Konfigurieren sicherer Dokumente mithilfe des Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d3b94-119">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="d3b94-120">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments** , und klicken Sie dann auf **globale Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d3b94-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , and then click **Global settings**.</span></span>

2. <span data-ttu-id="d3b94-121">Konfigurieren Sie in den angezeigten **globalen Einstellungen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="d3b94-121">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d3b94-122">**Aktivieren sicherer Dokumente für Office-Clients** : bewegen Sie die Umschaltfläche nach rechts, um das Feature zu aktivieren: Einschalten ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="d3b94-122">**Turn on Safe Documents for Office clients** : Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="d3b94-123">**Personen können durch die geschützte Ansicht klicken, selbst wenn sichere Dokumente die Datei als bösartig Kenn** zeichnen: Es wird empfohlen, diese Option deaktiviert zu lassen (lassen Sie die Umschaltfläche Links: ![ Deaktivieren ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="d3b94-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious** : We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="d3b94-124">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d3b94-124">When you're finished, click **Save**.</span></span>

   ![Einstellungen für sichere Dokumente nach dem auswählen globaler Einstellungen auf der Seite sichere Anlagen.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="d3b94-126">Konfigurieren sicherer Dokumente mithilfe Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3b94-126">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="d3b94-127">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="d3b94-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="d3b94-128">Der Parameter _EnableSafeDocs_ aktiviert oder deaktiviert sichere Dokumente für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="d3b94-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="d3b94-129">Der Parameter _AllowSafeDocsOpen_ ermöglicht oder verhindert, dass Benutzer die geschützte Ansicht (also das Öffnen des Dokuments) verlassen, wenn das Dokument als bösartig gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="d3b94-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="d3b94-130">In diesem Beispiel werden sichere Dokumente für die gesamte Organisation aktiviert, und es wird verhindert, dass Benutzer Dokumente öffnen, die als "bösartig" aus geschützter Ansicht identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="d3b94-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="d3b94-131">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="d3b94-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="d3b94-132">Woher weiß ich, dass der Vorgang erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="d3b94-132">How do I know this worked?</span></span>

<span data-ttu-id="d3b94-133">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie sichere Dokumente aktiviert und konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="d3b94-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="d3b94-134">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Attachments** , klicken Sie auf **globale Einstellungen** , und überprüfen Sie die **Option sichere Dokumente für Office-Clients aktivieren** , und **ermöglichen Sie den Benutzern, durch die geschützte Ansicht zu klicken, selbst wenn die Datei von sicheren Dokumenten als schädliche Einstellungen identifiziert** wird.</span><span class="sxs-lookup"><span data-stu-id="d3b94-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , click **Global settings** , and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="d3b94-135">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:</span><span class="sxs-lookup"><span data-stu-id="d3b94-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="d3b94-136">Die folgenden Dateien sind verfügbar, um den Schutz geschützter Dokumente zu testen.</span><span class="sxs-lookup"><span data-stu-id="d3b94-136">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="d3b94-137">Diese Dokumente ähneln der EICAR.TXT Datei zum Testen von Antischadsoftware-und Antivirenprogramme.</span><span class="sxs-lookup"><span data-stu-id="d3b94-137">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="d3b94-138">Die Dateien sind nicht schädlich, aber Sie werden Schutz für sichere Dokumente auslösen.</span><span class="sxs-lookup"><span data-stu-id="d3b94-138">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="d3b94-139">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="d3b94-139">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="d3b94-140">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="d3b94-140">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="d3b94-141">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="d3b94-141">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
