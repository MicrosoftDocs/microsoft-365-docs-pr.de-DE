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
description: 'In diesem Artikel erfahren Sie, wie Sie mithilfe von Exchange PowerShell das Feature "clutter" für alle oder bestimmte Benutzer in Ihrer Organisation aktivieren oder deaktivieren. '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780277"
---
# <a name="configure-clutter-for-your-organization"></a>Konfigurieren von 'Clutter' für Ihre Organisation

> [!TIP]
> [Posteingang mit Relevanz](../setup/configure-focused-inbox.md) ersetzt "Clutter". Weitere Informationen: [Update im Posteingang mit Fokus und Pläne für clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Als Administrator müssen Sie möglicherweise das Feature "clutter" in Microsoft 365 verwalten. Um das Feature "Clutter" für Benutzer in Ihrer Organisation ein- oder auszuschalten, müssen Sie Exchange PowerShell verwenden. (Einzelpersonen können Sie mit den folgenden Anweisungen aktivieren/deaktivieren: [Deaktivieren/bei clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).
  
Informationen zur Verwendung von Exchange PowerShell finden Sie unter [Verwenden von PowerShell mit Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) und [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415). Sie müssen über ein Konto mit mindestens der Exchange-Dienstadministrator Rolle verfügen und über die Möglichkeit zum Herstellen einer Verbindung mit Exchange Online mit PowerShell verfügen. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Aktivieren von "Clutter" mit Exchange PowerShell

You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet. 
  
Aktivieren von "Clutter" für einen einzigen Benutzer mit Namen Ada Simon
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Deaktivieren von "Clutter" mit Exchange PowerShell

You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet. 
  
Deaktivieren von "Clutter" für einen einzigen Benutzer mit Namen Ada Simon
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Wenn Sie PowerShell zum Massenerstellen von Benutzern verwenden, müssen Sie [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) für das Postfach eines jeden Benutzers ausführen, um "Clutter" zu verwalten. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Wann wird der Schalter für zum Ein-/Ausschalten von "Clutter" für Benutzer in Outlook im Web angezeigt?
<a name="bkmk_onoff"> </a>

Als Administrator können Sie die Übersichtlichkeit mithilfe von Exchange PowerShell wieder aktivieren. Wenn Sie dies tun, wird der Posteingang mit Relevanz deaktiviert und "Clutter" wieder aktiviert. 
  
 **Wenn Sie Outlook im Internet mit einem Microsoft 365 Business Premium-Abonnement verwenden:**
  
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
    
[Verwenden von clutter zum Sortieren von Nachrichten mit niedriger Priorität in OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Deaktivieren von "Clutter" in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

