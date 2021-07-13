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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Erfahren Sie, wie Sie das Clutter-Feature mit Exchange PowerShell für alle oder bestimmte Benutzer in Ihrer Organisation aktivieren oder deaktivieren. '
ms.openlocfilehash: 91098047bdf2ab8190283990bdc6b0292e3e57ba
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393979"
---
# <a name="configure-clutter-for-your-organization"></a>Konfigurieren von 'Clutter' für Ihre Organisation

> [!TIP]
> [Posteingang mit Relevanz](../setup/configure-focused-inbox.md) ersetzt "Clutter". Weitere Informationen: [Aktualisieren des Posteingangs mit Relevanz und unserer Pläne für Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Als Administrator müssen Sie möglicherweise das Clutter-Feature in Microsoft 365 verwalten. Um das Feature "Clutter" für Benutzer in Ihrer Organisation ein- oder auszuschalten, müssen Sie Exchange PowerShell verwenden. (Einzelpersonen können sie mithilfe dieser Anweisungen aktivieren/deaktivieren: [Clutter in Outlook deaktivieren/einschalten.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
  
Informationen zur Verwendung von Exchange PowerShell finden Sie unter [Verwenden von PowerShell mit Exchange Online](/powershell/exchange/exchange-online-powershell) und [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Sie benötigen ein Konto, das mindestens über die Rolle Exchange Dienstadministrator verfügt und die Möglichkeit hat, eine Verbindung mit Exchange Online mit PowerShell herzustellen. 
  
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

Als Administrator können Sie Clutter mit Exchange PowerShell erneut aktivieren. Wenn Sie dies tun, wird der Posteingang mit Relevanz deaktiviert und "Clutter" wieder aktiviert. 
  
 **Wenn Sie Outlook im Web mit einem Microsoft 365 Business Premium-Abonnement verwenden:**
  
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

[Verwenden von Clutter zum Sortieren von Nachrichten mit niedriger Priorität in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (Artikel)\
[Verwenden von Clutter zum Sortieren von Nachrichten mit niedriger Priorität in OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (Artikel)\
[Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) deaktivieren (Artikel)
