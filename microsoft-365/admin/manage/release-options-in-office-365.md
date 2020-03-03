---
title: Einrichten der Standard oder Targeted Release-Optionen in Office 365
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Erfahren Sie, wie Sie die Option "Release" für neue Produkt-und Funktionsupdates im Microsoft 365 Admin Center einrichten.
ms.openlocfilehash: d6c2eab340f4401fb31e4d9e814fbd326573569a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361800"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a>Einrichten der Standard oder Targeted Release-Optionen in Office 365

[] Mit Office 365 erhalten Sie neue Produktupdates und -features, sobald diese verfügbar werden, und müssen nicht alle paar Jahre teure Updates erwerben. Sie können die Bereitstellung dieser Updates für Ihre Organisation verwalten. Beispielsweise können Sie sich für eine frühe Veröffentlichung (Early Release) registrieren, damit Ihre Organisation die Updates zuerst erhält. Sie können festlegen, dass nur bestimmte Personen die Updates erhalten. Alternativ können Sie beim standardmäßigen Veröffentlichungszeitplan (Standard Release) bleiben und die Updates später erhalten. In diesem Artikel werden die verschiedenen Optionen vorgestellt und es wird deren Verwendung für Ihre Organisation erläutert.
  
> [!IMPORTANT]
> Die in diesem Artikel beschriebenen Office 365-Updates gelten für Office 365, SharePoint Online und Exchange Online. Sie gelten nicht für Skype for Business und zugehörige Dienste. Diese Release-Optionen sind zielgerichtete, nach bestem Bemühen entwickelte Möglichkeiten, Änderungen in Office 365 zu veröffentlichen, sie können aber nicht immer und nicht für alle Updates garantiert werden. 
  
## <a name="how-it-works---release-validation"></a>Funktionsweise - Releaseüberprüfung

Jede neue Version wird zuerst vom Feature-Team getestet und validiert, dann durch das gesamte Office 365-Feature-Team, gefolgt von Microsoft. Nach den internen Tests und Überprüfungen besteht der nächste Schritt in der Bereitstellung eines **Targeted Release** ("Gezielte Freigabe", vormals First Release) für Kunden, die die entsprechende Option aktivieren. Bei jedem Release Ring sammelt Microsoft Feedback und führt durch die Überwachung der wichtigsten Nutzungsmetriken weitere Qualitätsprüfungen durch. Diese Reihe von fortschreitenden Überprüfungen wurde eingeführt, um sicherzustellen, dass das weltweite Release so robust wie möglich ist. Die Releases sind in der folgenden Abbildung dargestellt. 
  
![Freigeben von Gültigkeits Prüfungs Ringen für Office 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Für wichtige Updates werden Office-Kunden zunächst durch die [Microsoft 365-Roadmap](https://products.office.com/business/office-365-roadmap)benachrichtigt. Wenn ein Update dem Rollout näher kommt, wird es über das [Office 365 Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)kommuniziert.

> [!NOTE]
> Sie benötigen ein Office 365-oder Azure AD Konto, um über das [Admin Center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)auf Ihr Nachrichtencenter zuzugreifen. Office 365 Home Plan Benutzer verfügen nicht über ein Admin Center.


## <a name="standard-release"></a>Standard Release

Dies ist die Standardoption, bei der Sie und Ihre Benutzer die neuesten Updates erhalten, wenn Sie allgemein für alle Kunden freigegeben werden.
  
Eine bewährte Methode besteht darin, die Mehrzahl der Benutzer in der **gezielten** Version von **Standard Version** und IT-Experten und Hauptbenutzern zu belassen, um neue Features auszuwerten und Teams zur Unterstützung von Geschäftsbenutzern und Führungskräften vorzubereiten. 
  
> [!NOTE]
> Wenn Sie von "Targeted Release" zurück zu "Standard Release" wechseln, verlieren Ihre Benutzer möglicherweise Zugriff auf die Features, die noch nicht im Standard Release-Programm freigegeben wurden. 
  
## <a name="targeted-release"></a>Zielrelease

Mit dieser Option gehören Sie und Ihre Benutzer zu den ersten Personen, die die neuesten Updates erhalten, und können durch Ihr frühes Feedback bei der weiteren Gestaltung des Produkts helfen. Sie können wählen, ob einzelne Personen oder die gesamte Organisation die Aktualisierungen frühzeitig erhalten sollen.
  
> [!IMPORTANT]
> Große oder komplexe Updates können länger dauern als andere, sodass keine Benutzer beeinträchtigt werden. Es gibt keine Garantie für den genauen Freigabetermin einer Version. 
  
### <a name="targeted-release-for-entire-organization"></a>Targeted Release für die gesamte Organisation

Wenn Sie [die Option "Release" im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, erhalten alle Ihre Benutzer die gezielte Veröffentlichungs Erfahrung. Für Organisationen mit mehr als 300 Benutzern empfehlen wir die Verwendung eines Testabonnements für diese Option. Wenden Sie für Informationen zum Testabonnement an Ihren Microsoft-Kontakt. 
  
### <a name="targeted-release-for-selected-users"></a>Gezielte Freigabe für bestimmte Benutzer

Wenn Sie [die Option Release im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, können Sie bestimmte Benutzer (in der Regel Hauptbenutzer) definieren, um frühzeitigen Zugriff auf Features und Funktionen zu erhalten. 
  
## <a name="benefits-of-targeted-release"></a>Vorteile der gezielten Freigabe

In der gezielten Freigabe können Administratoren die Manager bzw. anderen Benutzer ändern, die für Office 365-Updates zur Vorbereitung auf die anstehenden Änderungen verantwortlich sind und folgende Aufgaben ausführen:
  
- Neue Updates testen und überprüfen, bevor diese für alle Benutzer in der Organisation freigegeben werden.
    
- Benutzerbenachrichtigung und -dokumentation vorbereiten, bevor die Updates weltweit veröffentlicht werden.
    
- Das interne Helpdesk auf anstehende Änderungen vorbereiten.
    
- Compliance- und Sicherheitsüberprüfungen ausführen.
    
- Featuresteuerelemente verwenden (sofern zutreffend), um die Veröffentlichung von Updates für Endbenutzer zu steuern.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Einrichten der Option "Version" im Admin Center

Sie können wie folgt ändern, wie Ihre Organisation Office 365-Updates erhält. Sie müssen ein globaler Administrator in Office 365 sein, um sich anzumelden.
  
> [!IMPORTANT]
> Es kann bis zu 24 Stunden dauern, bis die Änderungen in Office 365 wirksam werden. Wenn Sie sich bei "Targeted Release" abmelden, nachdem Sie es zuvor aktiviert hatten, verlieren Ihre Benutzer möglicherweise Zugriff auf Features, deren geplanter Freigabetermin noch nicht erreicht ist. 
  
1. Wechseln Sie im Admin Center zur**Einstellung** **Einstellungen** > , und wählen Sie auf der Registerkarte **Organisationsprofil** die Option **Freigabeeinstellungen**aus.

5. Um die Zielversion zu deaktivieren, wählen Sie **Standard Version**aus, und wählen Sie dann **Änderungen speichern**aus. 
    
6. Um die gezielte Freigabe für alle Benutzer in Ihrer Organisation zu aktivieren, wählen Sie **Targeted Release for everyone**aus, und wählen Sie dann **Save Changes**aus. 
    
7. Um eine gezielte Freigabe für einige Personen in Ihrer Organisation zu aktivieren, wählen Sie **Targeted Release für ausgewählte Benutzer**aus, und wählen Sie dann **Save Changes**aus. 
    
8. Wählen **Sie Benutzer auswählen** aus, um Benutzer nacheinander hinzuzufügen, oder **Laden Sie Benutzer** zum Massen hinzufügen ein.
    
9. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Save Changes**aus.



## <a name="get-the-targeted-release-version-of-office"></a>Abrufen der gezielten Version von Office

Zum Installieren einer Targeted Release-Version von Office[ gehen Sie wie hier beschrieben vor ](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). Damit erhalten Sie frühzeitigen Zugriff auf die neuen Features von Office 2016 für Windows-Desktops.
  
## <a name="learn-more"></a>Weitere Informationen

Erfahren Sie, wie Sie [Nachrichten](https://docs.microsoft.com/office365/admin/manage/message-center) in Ihrem [Office 365 Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) verwalten, um Benachrichtigungen über bevorstehende Office 365 Updates und-Versionen zu erhalten.
