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
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Verringern des beim Lesen von e-Mail-Nachrichten verwendeten Arbeitsspeichers mithilfe von Lean Popouts

Dieser Artikel enthält Informationen zum Verbessern der Leistung von Nachrichten Downloads in Outlook im Internet. Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune) -Projekt.
  
Als Office 365 globaler Administrator können Sie Outlook im Internet so konfigurieren, dass es _schlanke Popouts_, eine kleinere, weniger arbeitsspeicherintensive Version bestimmter e-Mail-Nachrichten in Microsoft Edge oder Internet Explorer. Wenn Lean Popouts für Outlook im Internet konfiguriert sind, werden serverseitige gerenderte Komponenten geladen, die die Leistung optimieren.
  
> [!NOTE]
> Seit März 2018 sind keine Lean-Popouts für Nachrichten verfügbar, die Nutzungsrechte Einschränkungen angeben, beispielsweise IRM (Information Rights Management, Verwaltung von Informationsrechten).
  
Diese Features funktionieren weiterhin im Hauptfenster, stehen aber in Lean Popouts nicht zur Verfügung:
  
- Outlook-Add-Ins
  
- Skype for Business Anwesenheit
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>So konfigurieren Sie Lean Popouts für alle Benutzer in Ihrer Office 365 Organisation
  
1. Stellen [Sie mithilfe von Remote-PowerShell eine Verbindung zu Exchange Online her](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).
  
2. Führen Sie das Cmdlet " [OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) " mit dem Parameter "LeanPopoutEnabled" wie folgt aus:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Um beispielsweise Lean Popouts für alle Benutzer in Ihrer Organisation zu aktivieren:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  So deaktivieren Sie Lean Popouts für alle Benutzer in Ihrer Organisation:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
