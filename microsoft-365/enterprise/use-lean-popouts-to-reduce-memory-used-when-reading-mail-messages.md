---
title: Verwenden von schlanken Popups zum Reduzieren des beim Lesen von E-Mail-Nachrichten verwendeten Arbeitsspeichers
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Dieser Artikel enthält Informationen zur Verwendung schlanker Popouts, um die Leistung des Nachrichtendownloads in Outlook im Web zu verbessern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925256"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="63518-103">Verwenden von schlanken Popups zum Reduzieren des beim Lesen von E-Mail-Nachrichten verwendeten Arbeitsspeichers</span><span class="sxs-lookup"><span data-stu-id="63518-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="63518-104">Dieser Artikel enthält Informationen zur Verbesserung der Leistung des Nachrichtendownloads in Outlook im Web.</span><span class="sxs-lookup"><span data-stu-id="63518-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="63518-105">Dieser Artikel ist Teil des [Projekts Netzwerkplanung und Leistungsoptimierung für Office 365.](./network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="63518-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
  
<span data-ttu-id="63518-106">Als globaler Office 365-Administrator können Sie Outlook im Web so konfigurieren, dass schlanke _Popouts_ zur Verfügung gestellt werden, eine kleinere, weniger arbeitsspeicherintensive Version bestimmter E-Mail-Nachrichten in Microsoft Edge oder Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="63518-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="63518-107">Wenn schlanke Popups für Outlook im Web konfiguriert sind, werden serverseitige gerenderte Komponenten geladen, die die Leistung optimieren.</span><span class="sxs-lookup"><span data-stu-id="63518-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63518-108">Ab März 2018 sind schlanke Popouts nicht für Nachrichten verfügbar, die Nutzungsrechteinschränkungen angeben, z. B. IrM (Information Rights Management).</span><span class="sxs-lookup"><span data-stu-id="63518-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="63518-109">Diese Features funktionieren weiterhin im Hauptfenster, sind jedoch in schlanken Popouts nicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="63518-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="63518-110">Outlook-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="63518-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="63518-111">Skype for Business-Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="63518-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="63518-112">So konfigurieren Sie schlanke Popups für alle Benutzer in Ihrer Office 365-Organisation</span><span class="sxs-lookup"><span data-stu-id="63518-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="63518-113">[Herstellen einer Verbindung mit Exchange Online mithilfe von Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="63518-113">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="63518-114">Führen Sie [das Cmdlet Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) mit dem Parameter LeanPopoutEnabled wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="63518-114">Run the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="63518-115">So aktivieren Sie beispielsweise schlanke Popouts für alle Benutzer in Ihrer Organisation:</span><span class="sxs-lookup"><span data-stu-id="63518-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="63518-116">So deaktivieren Sie schlanke Popups für alle Benutzer in Ihrer Organisation:</span><span class="sxs-lookup"><span data-stu-id="63518-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```