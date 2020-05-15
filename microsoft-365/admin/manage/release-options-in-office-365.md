---
title: Einrichten der Standard-oder Targeted Release-Optionen
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
ms.openlocfilehash: 3a7a0562edef527718816bba6e67ea948cfad6b5
ms.sourcegitcommit: 708857a82eab3d37da1dec027399b09bd306a5dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "44249884"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Einrichten der Standard-oder Targeted Release-Optionen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Mit Microsoft 365 erhalten Sie neue Produktupdates und-Features, sobald diese verfügbar sind, statt kostspielige Updates alle paar Jahre durchführen zu müssen. Sie können die Bereitstellung dieser Updates für Ihre Organisation verwalten. Beispielsweise können Sie sich für eine frühe Veröffentlichung (Early Release) registrieren, damit Ihre Organisation die Updates zuerst erhält. Sie können festlegen, dass nur bestimmte Personen die Updates erhalten. Alternativ können Sie beim standardmäßigen Veröffentlichungszeitplan (Standard Release) bleiben und die Updates später erhalten. In diesem Artikel werden die verschiedenen Veröffentlichungsoptionen und ihre Verwendung für Ihre Organisation erläutert.
  
> [!IMPORTANT]
> Die in diesem Artikel beschriebenen Microsoft 365-Updates gelten für Microsoft 365, SharePoint Online und Exchange Online. Sie gelten nicht für Skype for Business und zugehörige Dienste. Diese Veröffentlichungsoptionen sind gezielte, bestmögliche Methoden zum Freigeben von Änderungen an Microsoft 365, die jedoch nicht zu jedem Zeitpunkt oder für alle Updates garantiert werden können. 
  
## <a name="how-it-works---release-validation"></a>Funktionsweise - Releaseüberprüfung

Jede neue Version wird zuerst vom Feature-Team getestet und validiert, dann durch das gesamte Microsoft 365-Feature-Team, gefolgt von Microsoft. Nach den internen Tests und Überprüfungen besteht der nächste Schritt in der Bereitstellung eines **Targeted Release** ("Gezielte Freigabe", vormals First Release) für Kunden, die die entsprechende Option aktivieren. Bei jedem Release Ring sammelt Microsoft Feedback und führt durch die Überwachung der wichtigsten Nutzungsmetriken weitere Qualitätsprüfungen durch. Diese Reihe von fortschreitenden Überprüfungen wurde eingeführt, um sicherzustellen, dass das weltweite Release so robust wie möglich ist. Die Releases sind in der folgenden Abbildung dargestellt. 
  
![Release-Überprüfungs Ringe für Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Für wichtige Updates werden Kunden zunächst durch die [Microsoft 365-Roadmap](https://products.office.com/business/office-365-roadmap)benachrichtigt. Wenn ein Update dem Rollout näher kommt, wird es über Ihr [Microsoft 365-Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)kommuniziert.

> [!NOTE]
> Sie benötigen ein Microsoft 365-oder Azure AD-Konto, um über das [Admin Center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)auf Ihr Nachrichtencenter zuzugreifen. Microsoft 365 Home Plan Benutzer verfügen nicht über ein Admin Center.


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

Targeted Release ermöglicht Administratoren, Änderungs Managern oder anderen Verantwortlichen für Microsoft 365-Updates die Vorbereitung auf die bevorstehenden Änderungen, indem Sie Ihnen Folgendes zulässt:
  
- Neue Updates testen und überprüfen, bevor diese für alle Benutzer in der Organisation freigegeben werden.
    
- Benutzerbenachrichtigung und -dokumentation vorbereiten, bevor die Updates weltweit veröffentlicht werden.
    
- Das interne Helpdesk auf anstehende Änderungen vorbereiten.
    
- Compliance- und Sicherheitsüberprüfungen ausführen.
    
- Featuresteuerelemente verwenden (sofern zutreffend), um die Veröffentlichung von Updates für Endbenutzer zu steuern.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Einrichten der Option "Version" im Admin Center

Sie können die Art und Weise ändern, wie Ihre Organisation Microsoft 365-Updates erhält, indem Sie die folgenden Schritte ausführen. Sie müssen ein globaler Administrator in Microsoft 365 sein, um sich anzumelden.
  
> [!IMPORTANT]
> Es kann bis zu 24 Stunden dauern, bis die folgenden Änderungen in Microsoft 365 wirksam werden. Wenn Sie sich bei "Targeted Release" abmelden, nachdem Sie es zuvor aktiviert hatten, verlieren Ihre Benutzer möglicherweise Zugriff auf Features, deren geplanter Freigabetermin noch nicht erreicht ist. 
  
1. Wechseln Sie im Admin Center zur **Settings**  >  **Einstellung**Einstellungen, und wählen Sie auf der Registerkarte **Organisationsprofil** die Option **Freigabeeinstellungen**aus.

5. Um die Zielversion zu deaktivieren, wählen Sie **Standard Version**aus, und wählen Sie dann **Änderungen speichern**aus. 
    
6. Um die gezielte Freigabe für alle Benutzer in Ihrer Organisation zu aktivieren, wählen Sie **Targeted Release for everyone**aus, und wählen Sie dann **Save Changes**aus. 
    
7. Um eine gezielte Freigabe für einige Personen in Ihrer Organisation zu aktivieren, wählen Sie **Targeted Release für ausgewählte Benutzer**aus, und wählen Sie dann **Save Changes**aus. 
    
8. Wählen **Sie Benutzer auswählen** aus, um Benutzer nacheinander hinzuzufügen, oder **Laden Sie Benutzer** zum Massen hinzufügen ein.
    
9. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Save Changes**aus.


  
## <a name="learn-more"></a>Weitere Informationen

Erfahren Sie, wie Sie [Nachrichten](https://docs.microsoft.com/office365/admin/manage/message-center) in Ihrem [Microsoft 365-Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) verwalten, um Benachrichtigungen zu bevorstehenden Updates und Versionen von Microsoft 365 zu erhalten.
