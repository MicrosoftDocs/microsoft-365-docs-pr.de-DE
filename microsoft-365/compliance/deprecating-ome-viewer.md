---
title: Veraltete App zur Nachrichtenverschlüsselungsanzeige
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
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
ms.custom:
- seo-marvel-apr2020
description: Die Office 365 Message Encryption (OME)-Viewer-App wurde 2018 aus den Android- und Apple-Stores entfernt.
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741522"
---
# <a name="deprecating-message-encryption-viewer-app"></a>Veraltete App zur Nachrichtenverschlüsselungsanzeige

Am 15. August 2018 haben wir die mobile App Office 365 Message Encryption (OME) Viewer aus den Android- und Apple-Stores entfernt. Die mobile Office 365 Message Encryption Viewer-App war erforderlich, um E-Mail-Nachrichten und Anlagen zu lesen, die mit der vorherigen Version von OME auf Apple- und Android-Smartphones verschlüsselt wurden. Neben dem Entfernen der OME-Viewer-App werden keine weiteren Änderungen an der vorherigen Version von OME vorgenommen.
  
## <a name="changes-from-august-2018"></a>Änderungen ab August 2018

Wie im September 2017 angekündigt, haben wir eine neue Version der [Office 365-Nachrichtenverschlüsselung](https://aka.ms/ome2017) veröffentlicht, damit Benutzer verschlüsselte und geschützte Nachrichten an alle Personen innerhalb oder außerhalb der Organisation senden können, ohne dass die mobile App erforderlich ist. Seitdem haben wir weitere Funktionen hinzugefügt:
  
- [Vorlage nur verschlüsseln](https://aka.ms/encryptonly)

- [Steuerelement zum Entschlüsseln von Anlagen](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

Mit dieser Änderung können Benutzer die mobile Office 365 Message Encryption Viewer-App ab dem 1. August nicht mehr herunterladen. Dies hat zur Folge, dass E-Mail-Empfänger nachrichten, die mit der vorherigen Version von OME verschlüsselt wurden, auf einigen mobilen Android- und Apple-Geräten möglicherweise nicht lesen können. Sie können diese Nachrichten jedoch weiterhin auf PCs (über Desktopbrowser) lesen. Benutzer, die die App bereits heruntergeladen haben, können sie weiterhin verwenden.
  
## <a name="why-this-change-was-made"></a>Warum diese Änderung vorgenommen wurde

Die neue Version von OME erfordert keine mobile App mehr, um geschützte E-Mail-Nachrichten und Anlagen zu lesen. Kunden, die die neuen OME-Funktionen verwenden, können die geschützte Nachricht in Outlook mobile anzeigen, und Nichtkunden können geschützte Nachrichten in einem Browser anzeigen.
  
Das Herunterladen einer mobilen App durch Benutzer ist eine weitere Hürde für Kunden zum Anzeigen geschützter Nachrichten. Die neuen Office 365-Nachrichtenverschlüsselungsfunktionen bieten eine bessere mobile Benutzererfahrung.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>Kann ich weiterhin die vorherige Version der Office 365-Nachrichtenverschlüsselung verwenden?

Die vorherige Version der Office 365-Nachrichtenverschlüsselung ist zu diesem Zeitpunkt nicht veraltet. Wir haben jedoch erhebliche Verbesserungen an der neuen Version der Office 365-Nachrichtenverschlüsselung vorgenommen, die das Verschlüsseln und Schützen vertraulicher Daten für alle Personen und auf jedem Gerät vereinfachen , einschließlich der Möglichkeit, dass Benutzer geschützte Nachrichten direkt in Outlook lesen können (Desktop, Mobil) und Web). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Was muss ich tun, um mich auf diese Änderung vorzubereiten?

Wenn Ihre Organisation derzeit verschlüsselte Anlagen an Empfänger sendet, für die die OME-Viewer-App erforderlich ist, sollten Sie Ihre Dokumentations- und Schulungsressourcen aktualisieren.
  
Es wird empfohlen, vorhandene Exchange-Nachrichtenflussregeln so zu aktualisieren, dass die aktuelle Version von OME verwendet wird, damit Ihre Organisation die neuen und verbesserten Funktionen nutzen kann. Nachdem Sie die neuen OME-Funktionen eingerichtet haben, benötigen Empfänger die OME-Viewer-App nicht mehr, um verschlüsselte Nachrichten auf mobilen Geräten zu lesen.
  
Microsoft empfiehlt, einen Plan für den Wechsel zu den neuen OME-Funktionen zu erstellen, sobald dies für Ihre Organisation sinnvoll ist. Anweisungen finden Sie unter [Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md). Weitere Informationen zur Funktionsweise der neuen Funktionen finden Sie unter [Office 365 Message Encryption](ome.md).
  

