---
title: Verwalten des E-Mail-App-Zugriffs in Microsoft 365 Admin Center
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: d00b6b83-1f14-4e9c-a2c5-dbd9a92816f4
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie, wie Sie auswählen, welche mobilen Apps Personen für den Zugriff auf E-Mails, Kalender und Kontakte verwenden können.
ms.openlocfilehash: f114aa43b4bbade09d53f415aae4c5c033c20694
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400052"
---
# <a name="manage-email-app-access-in-the-microsoft-365-admin-center"></a>Verwalten des E-Mail-App-Zugriffs im Microsoft 365 Admin Center

Verwenden Sie die Einstellungen für den mobilen E-Mail-Zugriff, um zu wählen, welche mobilen Apps Personen in Ihrer Organisation verwenden können, um auf ihr Arbeits- oder Schulkonto zu zugreifen, um auf E-Mails, Kalender und Kontakte zu zugreifen.
  
> [!IMPORTANT]
> Ihre Organisation hat Zugriff auf diese Einstellung, es sei denn, Sie verwenden Microsoft Intune oder Sie haben die Verwaltungseinstellungen für mobile Geräte im Exchange admin Center konfiguriert. 
  
## <a name="manage-email-app-options"></a>Verwalten von E-Mail-App-Optionen

> [!IMPORTANT]
>  Wenn Sie dieses Feature nicht verwenden, gibt es keine Änderungen an der Benutzererfahrung. Sie können jede mobile E-Mail-App verwenden, um von ihrem mobilen Gerät aus auf ihr Arbeits- oder Schulkonto für E-Mails, Kalender und Kontakte zu zugreifen. 
    
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Dienste &amp; Add-Ins</a>. 

2. Aktivieren Sie **auf** der Seite Mobile E-Mail-Zugriffsoptionen das Kontrollkästchen, und wählen Sie dann aus, wie Benutzer in Ihrer Organisation E-Mail-Apps auf ihren Geräten verwenden:
  
Wählen Sie die Option aus, um festlegen zu können, wie Benutzer in Ihrer Organisation auf ihr Arbeits- oder Schulkonto von ihren mobilen Geräten aus zugreifen.
  
- **Outlook -** Benutzer in Ihrer Organisation müssen die Outlook für Android oder Outlook für iOS-App auf ihrem mobilen Gerät verwenden. 
    
- **Jede** E-Mail-App – alle Benutzer in Ihrer Organisation werden aufgefordert, Outlook zu verwenden, aber sie können jede beliebige E-Mail-App verwenden. 
    
- **Jede** E-Mail-App – neue Benutzer oder Geräte in Ihrer Organisation werden einmal aufgefordert, Outlook zu verwenden, sie können jedoch jede beliebige E-Mail-App verwenden. 
    
Weitere Informationen finden Sie unter [Optionen für den Zugriff auf E-Mails von Ihrem mobilen Gerät](access-email-from-a-mobile-device.md)aus.
  
## <a name="new-user-or-device-is-activated-in-your-organization"></a>Neuer Benutzer oder Gerät wird in Ihrer Organisation aktiviert

Sobald ein Benutzer in Ihrer Organisation seine Arbeits- oder Schul-E-Mails zu einer E-Mail-App eines Drittanbieters oder zu einem neuen Gerät hinzufügt, erhält er eine E-Mail von Microsoft im Namen **Ihrer Organisation.** Die E-Mail informiert sie über die Vorteile der Outlook mobilen App und stellt einen Link zum Downloadspeicherort bereit. Ihre Benutzer können dann auswählen, ob sie die Drittanbieter-App weiterhin verwenden möchten, oder ob sie die Outlook verwenden möchten. Während der 24 Stunden, nachdem der Benutzer diese E-Mail erhalten hat, wird sein Gerät in Quarantäne gestellt, und E-Mails, Kalender und Kontaktdaten werden nicht aktualisiert. Wenn sie die mobile Outlook verwenden, bleibt die Drittanbieter-App isoliert, und die Daten werden nur mit der mobilen Outlook synchronisiert. Wenn sie die Verwendung der Drittanbieter-App fortsetzen möchten, werden die Daten sofort synchronisiert. Wenn in den ersten 24 Stunden keine Aktion ausgeführt wird, wird die E-Mail aus ihrem Posteingang entfernt, und die Daten werden automatisch vom Server synchronisiert.
  
## <a name="previously-configured-users-in-your-organization"></a>Zuvor konfigurierte Benutzer in Ihrer Organisation

Wenn Sie entscheiden, Outlook allen Benutzern in Ihrer Organisation zu empfehlen, erhalten Benutzer, die zuvor ihr E-Mail-Konto für Arbeit oder Schule mit einer Drittanbieter-App verbunden haben, innerhalb von 48 Stunden nach Aktivierung dieser Einstellung eine E-Mail von **Microsoft** im Namen Ihrer Organisation. Die E-Mail informiert sie über die Vorteile der Outlook mobilen App und stellt einen Link zum Downloadspeicherort bereit. Ihre Benutzer können dann auswählen, ob sie die Drittanbieter-App weiterhin verwenden möchten, oder ob sie die Outlook verwenden möchten. Während der 24 Stunden, nachdem der Benutzer diese E-Mail erhalten hat, wird sein Gerät in Quarantäne gestellt, und E-Mails, Kalender und Kontaktdaten werden nicht aktualisiert. Wenn sie die mobile Outlook verwenden, bleibt die Drittanbieter-App isoliert, und die Daten werden nur mit der mobilen Outlook synchronisiert. Wenn sie die Verwendung der Drittanbieter-App fortsetzen möchten, werden die Daten sofort synchronisiert. Wenn in den ersten 24 Stunden keine Aktion ausgeführt wird, wird die E-Mail aus ihrem Posteingang entfernt, und die Daten werden automatisch vom Server synchronisiert. 
  

