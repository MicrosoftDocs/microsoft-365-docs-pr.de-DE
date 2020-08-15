---
title: Verringern des beim Lesen von e-Mail-Nachrichten verwendeten Arbeitsspeichers mithilfe von Lean Popouts
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
description: Dieser Artikel enthält Informationen zur Verwendung von Lean popouts, um die Leistung von Nachrichten Downloads in Outlook im Internet zu verbessern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690774"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="2f6ec-103">Verringern des beim Lesen von e-Mail-Nachrichten verwendeten Arbeitsspeichers mithilfe von Lean Popouts</span><span class="sxs-lookup"><span data-stu-id="2f6ec-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="2f6ec-104">Dieser Artikel enthält Informationen zum Verbessern der Leistung von Nachrichten Downloads in Outlook im Internet.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="2f6ec-105">Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune) -Projekt.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
  
<span data-ttu-id="2f6ec-106">Als Office 365 globaler Administrator können Sie Outlook im Internet so konfigurieren, dass es _schlanke Popouts_, eine kleinere, weniger arbeitsspeicherintensive Version bestimmter e-Mail-Nachrichten in Microsoft Edge oder Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="2f6ec-107">Wenn Lean Popouts für Outlook im Internet konfiguriert sind, werden serverseitige gerenderte Komponenten geladen, die die Leistung optimieren.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f6ec-108">Seit März 2018 sind keine Lean-Popouts für Nachrichten verfügbar, die Nutzungsrechte Einschränkungen angeben, beispielsweise IRM (Information Rights Management, Verwaltung von Informationsrechten).</span><span class="sxs-lookup"><span data-stu-id="2f6ec-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="2f6ec-109">Diese Features funktionieren weiterhin im Hauptfenster, stehen aber in Lean Popouts nicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="2f6ec-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="2f6ec-110">Outlook-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="2f6ec-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="2f6ec-111">Skype for Business Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="2f6ec-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="2f6ec-112">So konfigurieren Sie Lean Popouts für alle Benutzer in Ihrer Office 365 Organisation</span><span class="sxs-lookup"><span data-stu-id="2f6ec-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="2f6ec-113">Stellen [Sie mithilfe von Remote-PowerShell eine Verbindung zu Exchange Online her](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span><span class="sxs-lookup"><span data-stu-id="2f6ec-113">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span></span>
  
2. <span data-ttu-id="2f6ec-114">Führen Sie das Cmdlet " [OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) " mit dem Parameter "LeanPopoutEnabled" wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="2f6ec-114">Run the [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="2f6ec-115">Um beispielsweise Lean Popouts für alle Benutzer in Ihrer Organisation zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2f6ec-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="2f6ec-116">So deaktivieren Sie Lean Popouts für alle Benutzer in Ihrer Organisation:</span><span class="sxs-lookup"><span data-stu-id="2f6ec-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
