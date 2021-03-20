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
description: 'Erfahren Sie, wie Sie das Clutter-Feature für alle oder bestimmte Benutzer in Ihrer Organisation mithilfe von Exchange PowerShell aktivieren oder deaktivieren. '
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915902"
---
# <a name="configure-clutter-for-your-organization"></a>Konfigurieren von 'Clutter' für Ihre Organisation

> [!TIP]
> [Posteingang mit Relevanz](../setup/configure-focused-inbox.md) ersetzt "Clutter". Weitere Informationen: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Als Administrator müssen Sie möglicherweise das Clutter-Feature in Microsoft 365 verwalten. Um das Feature "Clutter" für Benutzer in Ihrer Organisation ein- oder auszuschalten, müssen Sie Exchange PowerShell verwenden. (Einzelpersonen können dies mithilfe der folgenden Anweisungen [aktivieren/deaktivieren: Deaktivieren/Aktivieren](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)von Clutter in Outlook .
  
Informationen zur Verwendung von Exchange PowerShell finden Sie unter [Verwenden von PowerShell mit Exchange Online](/powershell/exchange/exchange-online-powershell) und [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Sie müssen über ein Konto verfügen, das mindestens über die Administratorrolle des Exchange-Diensts und die Möglichkeit verfügt, eine Verbindung mit Exchange Online mit PowerShell herzustellen. 
  
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

Als Administrator können Sie "Clutter" mithilfe von Exchange PowerShell erneut aktivieren. Wenn Sie dies tun, wird der Posteingang mit Relevanz deaktiviert und "Clutter" wieder aktiviert. 
  
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
    
## <a name="related-articles"></a>Verwandte Artikel
<a name="bkmk_onoff"> </a>

[Verwenden der Funktion „Clutter" zum Sortieren von Nachrichten mit niedriger Priorität in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[Sortieren von Nachrichten mit niedriger Priorität in OWA mithilfe von "Clutter"](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Deaktivieren von "Clutter" in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
