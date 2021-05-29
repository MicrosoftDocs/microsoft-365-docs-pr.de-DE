---
title: Konfigurieren von 'Clutter' für Ihre Organisation
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Erfahren Sie, wie Sie das Clutter-Feature für alle oder bestimmte Benutzer in Ihrer Organisation mithilfe von powerShell Exchange aktivieren oder deaktivieren. '
ms.openlocfilehash: 059fb8e626a0b05e0224fc89931453aaae43be0b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706111"
---
# <a name="configure-clutter-for-your-organization"></a>Konfigurieren von 'Clutter' für Ihre Organisation

> [!TIP]
> [Posteingang mit Relevanz](../setup/configure-focused-inbox.md) ersetzt "Clutter". Weitere Informationen: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Als Administrator müssen Sie möglicherweise das Clutter-Feature in Microsoft 365. Um das Feature "Clutter" für Benutzer in Ihrer Organisation ein- oder auszuschalten, müssen Sie Exchange PowerShell verwenden. (Einzelpersonen können dies mithilfe der folgenden Anweisungen [aktivieren/deaktivieren: Deaktivieren/Aktivieren](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)von Clutter in Outlook .
  
Informationen zur Verwendung von Exchange PowerShell finden Sie unter [Verwenden von PowerShell mit Exchange Online](/powershell/exchange/exchange-online-powershell) und [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Sie benötigen ein Konto, das mindestens die Rolle Exchange Dienstadministrators und die Möglichkeit hat, eine Verbindung mit Exchange Online PowerShell herzustellen. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Aktivieren von "Clutter" mit Exchange PowerShell

Sie können "Clutter" manuell für ein Postfach aktivieren, indem Sie das Cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter) ausführen. Sie können auch die Cluttereinstellungen für Postfächer in Ihrer Organisation anzeigen, indem Sie das Cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter) ausführen. 
  
Aktivieren von "Clutter" für einen einzigen Benutzer mit Namen Ada Simon
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Deaktivieren von "Clutter" mit Exchange PowerShell

Sie können "Clutter" manuell für ein Postfach deaktivieren, indem Sie das Cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter) ausführen. Sie können auch die Einstellungen für **Clutter** für Postfächer in Ihrer Organisation anzeigen, indem Sie das Cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter) ausführen. 
  
Deaktivieren von "Clutter" für einen einzigen Benutzer mit Namen Ada Simon
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Wenn Sie PowerShell zum Massenerstellen von Benutzern verwenden, müssen Sie [Set-Clutter](/powershell/module/exchange/set-clutter) für das Postfach eines jeden Benutzers ausführen, um "Clutter" zu verwalten. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Wann wird der Schalter für zum Ein-/Ausschalten von "Clutter" für Benutzer in Outlook im Web angezeigt?
<a name="bkmk_onoff"> </a>

Als Administrator können Sie "Clutter" mithilfe Exchange PowerShell erneut aktivieren. Wenn Sie dies tun, wird der Posteingang mit Relevanz deaktiviert und "Clutter" wieder aktiviert. 
  
 **Wenn Sie eine Outlook im Web mit einem Microsoft 365 Business Premium verwenden:**
  
- Wenn für den Benutzer aktuell "Clutter" aktiviert ist: 
    
  - Die "Clutter"-Einstellungen werden angezeigt.
    
- Wenn für den Benutzer aktuell "Posteingang mit Relevanz" aktiviert ist: 
    
  - Die "Clutter"-Einstellungen werden nicht angezeigt.
    
- Wenn weder "Clutter" noch "Posteingang mit Relevanz" aktiviert ist: 
    
  - In den Mails-Einstellungen des Benutzers werden "Clutter" und auch "Posteingang mit Relevanz" als Optionen angezeigt.
    
 **Bei Verwendung von Outlook.com:**
  
- Wenn für den Benutzer aktuell "Clutter" aktiviert ist: 
    
  - Die "Clutter"-Einstellungen werden angezeigt.
    
- Wenn für den Benutzer aktuell "Posteingang mit Relevanz" aktiviert ist: 
    
  - Die "Clutter"-Einstellungen werden nicht angezeigt.
    
- Wenn weder "Clutter" noch "Posteingang mit Relevanz" aktiviert ist: 
    
  - In den Mails-Einstellungen des Benutzers werden "Clutter" und auch "Posteingang mit Relevanz" als Optionen angezeigt.
    
- Wenn der Benutzer den Posteingang mit Relevanz in der Vergangenheit aktiviert hat:
    
  - Die "Clutter"-Einstellungen werden nie angezeigt.
    
    Andernfalls: 
    
  - Die "Clutter"-Einstellungen werden angezeigt.
    
## <a name="related-content"></a>Verwandte Inhalte

[Verwenden von Clutter zum Sortieren von](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) Nachrichten mit niedriger Priorität in Outlook (Artikel)\
[Verwenden von Clutter zum Sortieren von Nachrichten](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) mit niedriger Priorität in OWA (Artikel)\
[Deaktivieren von "Unübersichtlichkeit" in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (Artikel)
