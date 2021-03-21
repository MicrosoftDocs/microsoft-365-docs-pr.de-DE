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
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Verwenden von schlanken Popups zum Reduzieren des beim Lesen von E-Mail-Nachrichten verwendeten Arbeitsspeichers

Dieser Artikel enthält Informationen zur Verbesserung der Leistung des Nachrichtendownloads in Outlook im Web. Dieser Artikel ist Teil des [Projekts Netzwerkplanung und Leistungsoptimierung für Office 365.](./network-planning-and-performance.md)
  
Als globaler Office 365-Administrator können Sie Outlook im Web so konfigurieren, dass schlanke _Popouts_ zur Verfügung gestellt werden, eine kleinere, weniger arbeitsspeicherintensive Version bestimmter E-Mail-Nachrichten in Microsoft Edge oder Internet Explorer. Wenn schlanke Popups für Outlook im Web konfiguriert sind, werden serverseitige gerenderte Komponenten geladen, die die Leistung optimieren.
  
> [!NOTE]
> Ab März 2018 sind schlanke Popouts nicht für Nachrichten verfügbar, die Nutzungsrechteinschränkungen angeben, z. B. IrM (Information Rights Management).
  
Diese Features funktionieren weiterhin im Hauptfenster, sind jedoch in schlanken Popouts nicht verfügbar:
  
- Outlook-Add-Ins
  
- Skype for Business-Anwesenheit
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>So konfigurieren Sie schlanke Popups für alle Benutzer in Ihrer Office 365-Organisation
  
1. [Herstellen einer Verbindung mit Exchange Online mithilfe von Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
2. Führen Sie [das Cmdlet Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) mit dem Parameter LeanPopoutEnabled wie folgt aus:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  So aktivieren Sie beispielsweise schlanke Popouts für alle Benutzer in Ihrer Organisation:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  So deaktivieren Sie schlanke Popups für alle Benutzer in Ihrer Organisation:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```