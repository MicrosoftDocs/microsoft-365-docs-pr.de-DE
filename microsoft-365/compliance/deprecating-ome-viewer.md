---
title: Veraltete Office 365-Nachrichten Verschlüsselungs-Viewer-App
ms.author: krowley
author: kccross
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
description: Am 15. August 2018 werden wir die Office 365 Nachrichtenverschlüsselung (OM)-Anzeige Mobile App von Android Stores und Apple Stores entfernen. Das Office 365 Nachrichten Verschlüsselungs-Viewer-Mobile App war zum Lesen von e-Mail-Nachrichten und Anlagen erforderlich, die mit der vorherigen Version von OM auf Apple-und Android-Telefonen verschlüsselt wurden. Neben dem Entfernen der OM Viewer-App nehmen wir keine weiteren Änderungen an der vorherigen Version von OM vor.
ms.openlocfilehash: 3b5c92d4fa700a1ae8d7b104e33100301cf43506
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37080760"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a>Veraltete Office 365-Nachrichten Verschlüsselungs-Viewer-App

Am 15. August 2018 haben wir den Office 365-Nachrichten Verschlüsselungs-Viewer Mobile App von Android und Apple Stores entfernt. Das Office 365 Nachrichten Verschlüsselungs-Viewer-Mobile App war zum Lesen von e-Mail-Nachrichten und Anlagen erforderlich, die mit der vorherigen Version von OM auf Apple-und Android-Telefonen verschlüsselt wurden. Neben dem Entfernen der OM Viewer-App nehmen wir keine weiteren Änderungen an der vorherigen Version von OM vor.
  
## <a name="changes-from-august-2018"></a>Änderungen ab August 2018

Wie bereits im September 2017, haben wir eine neue Version von [Office 365 Nachrichtenverschlüsselung](https://aka.ms/ome2017) veröffentlicht, sodass Benutzer verschlüsselte und geschützte Nachrichten an Personen innerhalb oder außerhalb der Organisation senden können, ohne dass die Mobile App erforderlich ist. Seither haben wir zusätzliche Funktionen hinzugefügt:
  
- [Nur verschlüsselte Vorlage](https://aka.ms/encryptonly)

- [Steuerelement zum Entschlüsseln von Anlagen](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
Mit dieser Änderung können Benutzer den Office 365 Nachrichten Verschlüsselungs-Viewer nicht mehr herunterladen, Mobile App Anfang August 1. Daher können e-Mail-Empfänger möglicherweise keine Nachrichten lesen, die mit der vorherigen Version von OM auf einigen mobilen Geräten von Android und Apple verschlüsselt wurden. Sie können diese Nachrichten jedoch weiterhin auf Personal Computern lesen (über Desktop Browser). Benutzer, die die APP bereits heruntergeladen haben, können Sie weiterhin verwenden.
  
## <a name="why-this-change-was-made"></a>Gründe für die Änderung

Für die neue Version von OM ist kein Mobile App mehr erforderlich, um geschützte e-Mail-Nachrichten und Anlagen zu lesen. Office 365 Kunden, die die neuen OM-Funktionen verwenden, können die geschützte Nachricht in Outlook Mobile anzeigen und nicht Office 365 Kunden können geschützte Nachrichten in einem Browser anzeigen.
  
Das Herunterladen eines Mobile App durch Benutzer ist eine weitere Hürde für Kunden zum Anzeigen geschützter Nachrichten. Die neuen Office 365 Nachrichten Verschlüsselungsfunktionen bieten eine bessere mobile Benutzeroberfläche.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>Kann ich weiterhin die frühere Version von Office 365 Nachrichtenverschlüsselung verwenden

Die frühere Version von Office 365 Nachrichtenverschlüsselung ist zu diesem Zeitpunkt nicht veraltet, aber wir haben erhebliche Verbesserungen an der neuen Version von Office 365 Nachrichtenverschlüsselung vorgenommen, die das Verschlüsseln und schützen von vertraulichen Daten für alle Benutzer einfacher macht. und auf jedem Gerät, einschließlich der Möglichkeit, dass Office 365 Benutzer geschützte Nachrichten direkt in Outlook (Desktop, Mobiltelefon und Web) lesen können. 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Was muss ich tun, um diese Änderung vorzubereiten?

Wenn Ihre Organisation derzeit verschlüsselte Anlagen an Empfänger sendet, für die die app "OM Viewer" erforderlich ist, sollten Sie Ihre Dokumentation und Schulungsressourcen aktualisieren.
  
Es wird empfohlen, vorhandene Exchange-Nachrichtenfluss Regeln so zu aktualisieren, dass Sie die aktuelle Version von OM verwenden, damit Ihre Organisation die neuen und verbesserten Funktionen nutzen kann. Nachdem Sie die neuen OM-Funktionen eingerichtet haben, benötigen Empfänger nicht die OM Viewer-APP, um verschlüsselte Nachrichten auf mobilen Geräten zu lesen.
  
Microsoft empfiehlt, einen Plan für die Umstellung auf die neuen OM-Funktionen zu erstellen, sobald dies für Ihre Organisation sinnvoll ist. Anweisungen finden Sie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md). Wenn Sie mehr darüber erfahren möchten, wie die neuen Funktionen als erstes funktionieren, lesen Sie [Office 365 Nachrichtenverschlüsselung](ome.md).
  

