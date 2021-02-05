---
title: Einrichten der Standard- oder Targeted Release-Optionen
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Erfahren Sie, wie Sie die Veröffentlichungsoption für neue Produkt- und Featuresupdates im Microsoft 365 Admin Center einrichten.
ms.openlocfilehash: 99a2660af9d8756bf4faf1cf3eddfe142a7c87bf
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114489"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Einrichten der Standard- oder Targeted Release-Optionen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

> [!IMPORTANT]
> Die in diesem Artikel beschriebenen Microsoft 365-Updates gelten für Microsoft 365, SharePoint Online und Exchange Online. Diese Veröffentlichungsoptionen sind zielgerichtete, bewährte Methoden zum Veröffentlichen von Änderungen an Microsoft 365, können jedoch nicht zu jeder Zeit oder für alle Updates garantiert werden. Sie gelten nicht für Microsoft 365-Apps, Skype for Business, Microsoft Teams und verwandte Dienste. Informationen zu den Veröffentlichungsoptionen für Microsoft 365-Apps finden Sie unter "Übersicht über [Updatekanäle für Microsoft 365-Apps".](https://docs.microsoft.com/deployoffice/overview-update-channels)

Mit Microsoft 365 erhalten Sie neue Produktupdates und Features, sobald diese verfügbar sind, anstatt alle paar Jahre kostspielige Updates zu verwenden. Sie können die Bereitstellung dieser Updates für Ihre Organisation verwalten. Beispielsweise können Sie sich für eine frühe Veröffentlichung (Early Release) registrieren, damit Ihre Organisation die Updates zuerst erhält. Sie können festlegen, dass nur bestimmte Personen die Updates erhalten. Alternativ können Sie beim standardmäßigen Veröffentlichungszeitplan (Standard Release) bleiben und die Updates später erhalten. In diesem Artikel werden die verschiedenen Veröffentlichungsoptionen und deren Verwendung für Ihre Organisation erläutert.

## <a name="how-it-works---release-validation"></a>Funktionsweise - Releaseüberprüfung

Jede neue Version wird zuerst vom Featureteam getestet und überprüft, dann vom gesamten Microsoft 365-Featureteam, gefolgt von Microsoft. Nach den internen Tests und Überprüfungen besteht der nächste Schritt in der Bereitstellung eines **Targeted Release** ("Gezielte Freigabe", vormals First Release) für Kunden, die die entsprechende Option aktivieren. Bei jedem Release Ring sammelt Microsoft Feedback und führt durch die Überwachung der wichtigsten Nutzungsmetriken weitere Qualitätsprüfungen durch. Diese Reihe von fortschreitenden Überprüfungen wurde eingeführt, um sicherzustellen, dass das weltweite Release so robust wie möglich ist. Die Releases sind in der folgenden Abbildung dargestellt. 
  
![Versionsüberprüfungsringe für Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Bei wichtigen Updates werden Kunden zunächst über die [Microsoft 365](https://products.office.com/business/office-365-roadmap)Roadmap benachrichtigt. Sobald sich ein Update dem Roll out nähert, wird es über Ihr [Microsoft 365-Nachrichtencenter kommuniziert.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)

> [!NOTE]
> Sie benötigen ein Microsoft 365- oder Azure AD-Konto, um über das Admin Center auf Ihr Nachrichtencenter [zu zugreifen.](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center) Benutzer des Microsoft 365-Homeplans verfügen nicht über ein Admin Center.


## <a name="standard-release"></a>Standard Release

Dies ist die Standardoption, bei der Sie und Ihre Benutzer die neuesten Updates erhalten, wenn sie allgemein für alle Kunden veröffentlicht werden.
  
Eine bewährte Methode ist es, die Mehrzahl der Benutzer in der **Standardversion** und für IT-Profis und Hauptbenutzer in **der** gezielten Version zu be lassen, um neue Features auszuwerten und Teams für die Unterstützung von Geschäftsbenutzern und Führungskräften vorzubereiten. 
  
> [!NOTE]
> Wenn Sie von "Targeted Release" zurück zu "Standard Release" wechseln, verlieren Ihre Benutzer möglicherweise Zugriff auf die Features, die noch nicht im Standard Release-Programm freigegeben wurden. 
  
## <a name="targeted-release"></a>Zielrelease

Mit dieser Option gehören Sie und Ihre Benutzer zu den ersten Personen, die die neuesten Updates erhalten, und können durch Ihr frühes Feedback bei der weiteren Gestaltung des Produkts helfen. Sie können wählen, ob einzelne Personen oder die gesamte Organisation die Aktualisierungen frühzeitig erhalten sollen.
  
> [!IMPORTANT]
> Große oder komplexe Updates können länger dauern als andere, sodass keine Benutzer beeinträchtigt werden. Es gibt keine Garantie für den genauen Freigabetermin einer Version. 
  
### <a name="targeted-release-for-entire-organization"></a>Targeted Release für die gesamte Organisation

Wenn Sie [die Veröffentlichungsoption im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, erhalten alle Ihre Benutzer die Benutzererfahrung für die gezielte Veröffentlichung. Für Organisationen mit mehr als 300 Benutzern empfehlen wir die Verwendung eines Testabonnements für diese Option. Wenden Sie für Informationen zum Testabonnement an Ihren Microsoft-Kontakt. 
  
### <a name="targeted-release-for-selected-users"></a>Gezielte Freigabe für bestimmte Benutzer

Wenn Sie [die Veröffentlichungsoption im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, können Sie bestimmte Benutzer definieren, in der Regel Energiebenutzer, um frühzeitigen Zugriff auf Features und Funktionen zu erhalten. 
  
## <a name="benefits-of-targeted-release"></a>Vorteile der gezielten Freigabe

Eine gezielte Version ermöglicht Administratoren, Änderungsmanagern oder anderen Personen, die für Microsoft 365-Updates verantwortlich sind, die Vorbereitung auf die bevorstehenden Änderungen, indem sie:
  
- Neue Updates testen und überprüfen, bevor diese für alle Benutzer in der Organisation freigegeben werden.
    
- Benutzerbenachrichtigung und -dokumentation vorbereiten, bevor die Updates weltweit veröffentlicht werden.
    
- Das interne Helpdesk auf anstehende Änderungen vorbereiten.
    
- Compliance- und Sicherheitsüberprüfungen ausführen.
    
- Featuresteuerelemente verwenden (sofern zutreffend), um die Veröffentlichung von Updates für Endbenutzer zu steuern.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Einrichten der Veröffentlichungsoption im Admin Center

Sie können ändern, wie Ihre Organisation Microsoft 365-Updates erhält, indem Sie die folgenden Schritte ausführen. Sie müssen ein globaler Administrator in Microsoft 365 sein, um sich dafür zu entscheiden.
  
> [!IMPORTANT]
> Es kann bis zu 24 Stunden dauern, bis die nachstehenden Änderungen in Microsoft 365 wirksam werden. Wenn Sie sich bei "Targeted Release" abmelden, nachdem Sie es zuvor aktiviert hatten, verlieren Ihre Benutzer möglicherweise Zugriff auf Features, deren geplanter Freigabetermin noch nicht erreicht ist. 
  
1. Wechseln Sie im Admin Center zur Einstellung "Organisationseinstellungen", und wählen Sie auf der Registerkarte "Organisationsprofil" die Option  >   **"Freigabeeinstellungen" aus.** 

5. Um die zielorientierte Freigabe zu deaktivieren, wählen **Sie "Standardversion"** und dann **"Änderungen speichern" aus.** 
    
6. Wenn Sie die zielorientierte Freigabe für alle Benutzer in Ihrer Organisation aktivieren möchten, wählen Sie **"Targeted Release"** für alle Benutzer aus, und wählen Sie dann **"Änderungen speichern" aus.** 
    
7. Um die gezielte Freigabe für einige Personen in Ihrer Organisation zu aktivieren, wählen Sie **"Targeted Release"** für ausgewählte Benutzer und dann **"Änderungen speichern" aus.** 
    
8. Choose **Select users** to add users one at a time, or Upload **users** to add them in bulk.
    
9. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **"Änderungen speichern" aus.**


  
## <a name="learn-more"></a>Mehr erfahren

Erfahren Sie, wie [Sie Nachrichten](https://docs.microsoft.com/office365/admin/manage/message-center) in [Ihrem Microsoft 365-Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) verwalten, um Benachrichtigungen zu bevorstehenden Microsoft 365-Updates und -Versionen zu erhalten.
