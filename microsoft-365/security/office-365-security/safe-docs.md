---
title: Sichere Dokumente in Office 365 ATP
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
ms.openlocfilehash: 8918c7da26a60c7cfd64b7148d0added82cc6642
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949454"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="1a7c9-103">Sichere Dokumente in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1a7c9-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="1a7c9-104">Safe Documents ist ein Feature in Microsoft 365 E5 oder Microsoft 365 E5 Security, das [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der [geschützten Ansicht](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1a7c9-105">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="1a7c9-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1a7c9-106">Sichere Dokumente sind nun allgemein für Benutzer mit Office-Version 2004 (12730. x) oder höher verfügbar!</span><span class="sxs-lookup"><span data-stu-id="1a7c9-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="1a7c9-107">Dieses Feature ist standardmäßig deaktiviert und muss vom Sicherheits Administrator aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="1a7c9-108">Dieses Feature ist nur für Benutzer mit der Sicherheitslizenz *Microsoft 365 E5* oder *Microsoft 365 E5* verfügbar (nicht in Office 365 ATP-Pläne enthalten).</span><span class="sxs-lookup"><span data-stu-id="1a7c9-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="1a7c9-109">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1a7c9-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1a7c9-110">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1a7c9-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1a7c9-111">Weitere Informationen zu</span><span class="sxs-lookup"><span data-stu-id="1a7c9-111">For more information about</span></span> 

- <span data-ttu-id="1a7c9-112">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Thema ausführen können.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-112">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="1a7c9-113">Um sichere Dokumente zu aktivieren und zu konfigurieren, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-113">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="1a7c9-114">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1a7c9-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="1a7c9-115">Wie verarbeitet Microsoft Ihre Daten?</span><span class="sxs-lookup"><span data-stu-id="1a7c9-115">How does Microsoft handle your data?</span></span>

<span data-ttu-id="1a7c9-116">Damit Sie geschützt bleiben, sendet Safe Documents Dateien zur Analyse an die [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) -Cloud.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-116">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="1a7c9-117">Details dazu, wie Microsoft Defender Advanced Threat Protection Ihre Daten verarbeitet, finden Sie [hier](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="1a7c9-117">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>
- <span data-ttu-id="1a7c9-118">Zusätzlich zu den obigen Richtlinien werden Dateien, die von sicheren Dokumenten gesendet werden, nicht in Defender aufbewahrt, was in der Regel weniger als 24 Stunden dauert, die für die Analyse benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-118">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours.</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="1a7c9-119">Konfigurieren sicherer Dokumente mithilfe des Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1a7c9-119">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="1a7c9-120">Öffnen Sie das Security & Compliance Center unter <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="1a7c9-120">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="1a7c9-121">Wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-121">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="1a7c9-122">Konfigurieren Sie im Abschnitt **Hilfe für Personen, die beim Vertrauen auf eine Datei beim Öffnen außerhalb geschützter Ansicht in Office-Anwendungen sicher bleiben eine** der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1a7c9-122">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="1a7c9-123">**Aktivieren sicherer Dokumente für Office-Clients**</span><span class="sxs-lookup"><span data-stu-id="1a7c9-123">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="1a7c9-124">**Personen können durch die geschützte Ansicht klicken, selbst wenn sichere Dokumente die Datei als bösartig Kenn**zeichnen: Es wird empfohlen, diese Option nicht zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-124">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="1a7c9-125">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-125">When you're finished, click **Save**.</span></span>

![Seite "ATP-sichere Anlagen"](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="1a7c9-127">Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Konfigurieren sicherer Dokumente</span><span class="sxs-lookup"><span data-stu-id="1a7c9-127">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="1a7c9-128">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="1a7c9-128">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="1a7c9-129">Der Parameter _EnableSafeDocs_ aktiviert oder deaktiviert sichere Dokumente für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-129">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="1a7c9-130">Der Parameter _AllowSafeDocsOpen_ ermöglicht oder verhindert, dass Benutzer die geschützte Ansicht (also das Öffnen des Dokuments) verlassen, wenn das Dokument als bösartig gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-130">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="1a7c9-131">In diesem Beispiel werden sichere Dokumente für die gesamte Organisation aktiviert, und es wird verhindert, dass Benutzer Dokumente öffnen, die als "bösartig" aus geschützter Ansicht identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-131">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="1a7c9-132">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="1a7c9-132">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="1a7c9-133">Woher weiß ich, dass der Vorgang erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="1a7c9-133">How do I know this worked?</span></span>

<span data-ttu-id="1a7c9-134">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie sichere Dokumente aktiviert und konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="1a7c9-134">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="1a7c9-135">Im Security & Compliance Center gehen Sie zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**, und überprüfen Sie die Auswahl im Abschnitt **Hilfe Personen bleiben sicher, wenn Sie einer Datei vertrauen, dass Sie außerhalb geschützter Ansicht in Office-Anwendungen geöffnet** wird.</span><span class="sxs-lookup"><span data-stu-id="1a7c9-135">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="1a7c9-136">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:</span><span class="sxs-lookup"><span data-stu-id="1a7c9-136">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
