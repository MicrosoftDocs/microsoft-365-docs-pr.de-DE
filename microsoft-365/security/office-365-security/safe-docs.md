---
title: Sichere Dokumente in Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über sichere Dokumente in Office 365 ATP.
ms.openlocfilehash: db73fc152a5a580a28bf6d8424ebc2a139cf3303
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960349"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="a2a7c-103">Sichere Dokumente in Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a2a7c-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="a2a7c-104">Safe Documents ist ein Feature in Office 365 Advanced Threat Protection (ATP), das [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der [geschützten Ansicht](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a2a7c-105">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="a2a7c-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a2a7c-106">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a2a7c-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a2a7c-107">Informationen zum Herstellen einer Verbindung mit Exchange Online Protection PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a2a7c-107">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a2a7c-108">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Thema ausführen können.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-108">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="a2a7c-109">Um sichere Dokumente zu aktivieren und zu konfigurieren, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-109">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="a2a7c-110">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a2a7c-110">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="a2a7c-111">Konfigurieren sicherer Dokumente mithilfe des Office 365 Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a2a7c-111">Use the Office 365 Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="a2a7c-112">Öffnen Sie das Office 365 Security & Compliance Center <https://protection.office.com>unter.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-112">Open the Office 365 Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="a2a7c-113">Wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-113">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="a2a7c-114">Konfigurieren Sie im Abschnitt **Hilfe für Personen, die beim Vertrauen auf eine Datei beim Öffnen außerhalb geschützter Ansicht in Office-Anwendungen sicher bleiben eine** der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a2a7c-114">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="a2a7c-115">**Aktivieren sicherer Dokumente für Office-Clients (Dateien werden auch an Microsoft Cloud für tiefe Analysen gesendet)**</span><span class="sxs-lookup"><span data-stu-id="a2a7c-115">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="a2a7c-116">**Personen können durch die geschützte Ansicht klicken, selbst wenn sichere Dokumente die Datei als bösartig Kenn**zeichnen: Es wird empfohlen, diese Option nicht zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-116">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="a2a7c-117">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-117">When you're finished, click **Save**.</span></span>

![Seite "ATP-sichere Anlagen"](../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a><span data-ttu-id="a2a7c-119">Konfigurieren sicherer Dokumente mithilfe von Exchange Online PowerShell oder Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2a7c-119">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="a2a7c-120">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="a2a7c-120">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="a2a7c-121">Der Parameter _EnableSafeDocs_ aktiviert oder deaktiviert sichere Dokumente für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-121">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="a2a7c-122">Der Parameter _AllowSafeDocsOpen_ ermöglicht oder verhindert, dass Benutzer die geschützte Ansicht (also das Öffnen des Dokuments) verlassen, wenn das Dokument als bösartig gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-122">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="a2a7c-123">In diesem Beispiel werden sichere Dokumente für die gesamte Organisation aktiviert, und es wird verhindert, dass Benutzer Dokumente öffnen, die als "bösartig" aus geschützter Ansicht identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-123">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="a2a7c-124">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="a2a7c-124">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="a2a7c-125">Woher weiß ich, dass der Vorgang erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="a2a7c-125">How do I know this worked?</span></span>

<span data-ttu-id="a2a7c-126">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie sichere Dokumente aktiviert und konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="a2a7c-126">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="a2a7c-127">Im Security & Compliance Center gehen Sie zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**, und überprüfen Sie die Auswahl im Abschnitt **Hilfe Personen bleiben sicher, wenn Sie einer Datei vertrauen, dass Sie außerhalb geschützter Ansicht in Office-Anwendungen geöffnet** wird.</span><span class="sxs-lookup"><span data-stu-id="a2a7c-127">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="a2a7c-128">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:</span><span class="sxs-lookup"><span data-stu-id="a2a7c-128">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
