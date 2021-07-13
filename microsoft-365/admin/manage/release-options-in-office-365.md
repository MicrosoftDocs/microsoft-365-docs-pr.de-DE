---
title: Einrichten der Standard- oder Zielversionsoptionen
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
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Erfahren Sie, wie Sie die Veröffentlichungsoption für neue Produkt- und Featureupdates im Microsoft 365 Admin Center einrichten.
ms.openlocfilehash: ba9c3a71807728e18b612f0b63aff80d04a46a90
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392527"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Einrichten der Standard- oder Zielversionsoptionen

> [!IMPORTANT]
> Die in diesem Artikel beschriebenen Microsoft 365 Updates gelten für Microsoft 365, SharePoint Online und Exchange Online. Diese Veröffentlichungsoptionen sind gezielte, bestmögliche Methoden zum Freigeben von Änderungen an Microsoft 365, können jedoch nicht immer oder für alle Updates garantiert werden. Sie gelten nicht für Microsoft 365 Apps, Skype for Business, Microsoft Teams und verwandte Dienste. Informationen zu Veröffentlichungsoptionen für Microsoft 365 Apps finden Sie unter [Übersicht über Updatekanäle für Microsoft 365 Apps](/deployoffice/overview-update-channels).

Mit Microsoft 365 erhalten Sie neue Produktupdates und Features, sobald sie verfügbar sind, anstatt alle paar Jahre kostspielige Updates durchzuführen. Sie können die Bereitstellung dieser Updates für Ihre Organisation verwalten. Beispielsweise können Sie sich für eine frühe Veröffentlichung (Early Release) registrieren, damit Ihre Organisation die Updates zuerst erhält. Sie können festlegen, dass nur bestimmte Personen die Updates erhalten. Alternativ können Sie beim standardmäßigen Veröffentlichungszeitplan (Standard Release) bleiben und die Updates später erhalten. In diesem Artikel werden die verschiedenen Veröffentlichungsoptionen und ihre Verwendung für Ihre Organisation erläutert.

## <a name="how-it-works---release-validation"></a>Funktionsweise - Releaseüberprüfung

Jede neue Version wird zuerst vom Featureteam getestet und validiert, dann vom gesamten Microsoft 365 Featureteam, gefolgt von microsoft. Nach den internen Tests und Überprüfungen besteht der nächste Schritt in der Bereitstellung eines **Targeted Release** ("Gezielte Freigabe", vormals First Release) für Kunden, die die entsprechende Option aktivieren. Bei jedem Release Ring sammelt Microsoft Feedback und führt durch die Überwachung der wichtigsten Nutzungsmetriken weitere Qualitätsprüfungen durch. Diese Reihe von fortschreitenden Überprüfungen wurde eingeführt, um sicherzustellen, dass das weltweite Release so robust wie möglich ist. Die Releases sind in der folgenden Abbildung dargestellt. 
  
![Freigeben von Validierungsringen für Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Bei wichtigen Updates werden Kunden zunächst durch die [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap)benachrichtigt. Wenn ein Update dem Rollout näher kommt, wird es über Ihr [Microsoft 365 Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)kommuniziert.

> [!NOTE]
> Sie benötigen ein Microsoft 365- oder Azure AD-Konto, um über das [Admin Center](/office365/admin/admin-overview/about-the-admin-center)auf Ihr Nachrichtencenter zuzugreifen. Microsoft 365 Benutzer des Homeplans verfügen nicht über ein Admin Center.


## <a name="standard-release"></a>Standard Release

Dies ist die Standardoption, bei der Sie und Ihre Benutzer die neuesten Updates erhalten, wenn sie allgemein für alle Kunden veröffentlicht werden.
  
Eine bewährte Methode besteht darin, die Mehrzahl der Benutzer in der **Standardversion** und IT-Spezialisten und Hauptbenutzer in **der gezielten Version** zu belassen, um neue Features zu bewerten und Teams auf die Unterstützung von Geschäftsbenutzern und Führungskräften vorzubereiten. 
  
> [!NOTE]
> Wenn Sie von "Targeted Release" zurück zu "Standard Release" wechseln, verlieren Ihre Benutzer möglicherweise Zugriff auf die Features, die noch nicht im Standard Release-Programm freigegeben wurden. 
  
## <a name="targeted-release"></a>Zielrelease

Mit dieser Option gehören Sie und Ihre Benutzer zu den ersten Personen, die die neuesten Updates erhalten, und können durch Ihr frühes Feedback bei der weiteren Gestaltung des Produkts helfen. Sie können wählen, ob einzelne Personen oder die gesamte Organisation die Aktualisierungen frühzeitig erhalten sollen.
  
> [!IMPORTANT]
> Große oder komplexe Updates können länger dauern als andere, sodass keine Benutzer beeinträchtigt werden. Es gibt keine Garantie für den genauen Freigabetermin einer Version. 
  
### <a name="targeted-release-for-entire-organization"></a>Targeted Release für die gesamte Organisation

Wenn Sie [die Veröffentlichungsoption im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, erhalten alle Ihre Benutzer die Benutzeroberfläche für die gezielte Veröffentlichung. Für Organisationen mit mehr als 300 Benutzern empfehlen wir die Verwendung eines Testabonnements für diese Option. Wenden Sie für Informationen zum Testabonnement an Ihren Microsoft-Kontakt. 
  
### <a name="targeted-release-for-selected-users"></a>Gezielte Freigabe für bestimmte Benutzer

Wenn Sie [die Veröffentlichungsoption im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, können Sie bestimmte Benutzer definieren, in der Regel Hauptbenutzer, um frühzeitigen Zugriff auf Features und Funktionen zu erhalten. 
  
## <a name="benefits-of-targeted-release"></a>Vorteile der gezielten Freigabe

Mit der gezielten Veröffentlichung können Administratoren, Änderungsmanager oder andere Personen, die für Microsoft 365 Updates verantwortlich sind, sich auf die bevorstehenden Änderungen vorbereiten, indem sie ihnen Folgendes mitteilen:
  
- Neue Updates testen und überprüfen, bevor diese für alle Benutzer in der Organisation freigegeben werden.
    
- Benutzerbenachrichtigung und -dokumentation vorbereiten, bevor die Updates weltweit veröffentlicht werden.
    
- Das interne Helpdesk auf anstehende Änderungen vorbereiten.
    
- Compliance- und Sicherheitsüberprüfungen ausführen.
    
- Featuresteuerelemente verwenden (sofern zutreffend), um die Veröffentlichung von Updates für Endbenutzer zu steuern.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Einrichten der Veröffentlichungsoption im Admin Center

Mit den folgenden Schritten können Sie ändern, wie Ihre Organisation Microsoft 365 Updates empfängt. Sie müssen ein globaler Administrator in Microsoft 365 sein, um sich anmelden zu können.
  
> [!IMPORTANT]
> Es kann bis zu 24 Stunden dauern, bis die folgenden Änderungen in Microsoft 365 wirksam werden. Wenn Sie sich bei "Targeted Release" abmelden, nachdem Sie es zuvor aktiviert hatten, verlieren Ihre Benutzer möglicherweise Zugriff auf Features, deren geplanter Freigabetermin noch nicht erreicht ist. 
  
1. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Organisationseinstellung,** und wählen Sie auf der Registerkarte **"Organisationsprofil"** **die Veröffentlichungseinstellungen** aus.

5. Wenn Sie die Zielversion deaktivieren möchten, wählen Sie **"Standardversion"** und dann **"Änderungen speichern"** aus. 
    
6. Um die gezielte Freigabe für alle Benutzer in Ihrer Organisation zu aktivieren, wählen Sie **"Zielversion für alle** Benutzer" und dann **"Änderungen speichern"** aus. 
    
7. Um die gezielte Freigabe für einige Personen in Ihrer Organisation zu aktivieren, wählen Sie **"Zielversion" für ausgewählte Benutzer** aus, und wählen Sie dann **"Änderungen speichern"** aus. 
    
8. Wählen Sie **"Benutzer auswählen"** aus, um Benutzer einzeln hinzuzufügen, oder **Hochladen Benutzer,** sie in Massen hinzuzufügen.
    
9. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **"Änderungen speichern"** aus.
  
## <a name="next-steps"></a>Nächste Schritte

Erfahren Sie, wie Sie Nachrichten in Ihrem [Microsoft 365 Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) [verwalten,](/office365/admin/manage/message-center) um Benachrichtigungen zu bevorstehenden Microsoft 365 Updates und Veröffentlichungen zu erhalten.

## <a name="related-content"></a>Verwandte Inhalte

[Teilnehmen am Office-Insider-Programm](https://insider.office.com/join/windows) (Artikel)
