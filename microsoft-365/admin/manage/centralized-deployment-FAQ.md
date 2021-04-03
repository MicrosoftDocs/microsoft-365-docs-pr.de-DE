---
title: FAQ zur zentralen Bereitstellung
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Lesen Sie die Antworten auf häufige Fragen zur zentralen Bereitstellung im Microsoft 365 Admin Center.
ms.openlocfilehash: 60d7a91da738803976b6823009450124d7b57814
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579302"
---
# <a name="centralized-deployment-faq"></a>FAQ zur zentralen Bereitstellung

Die zentrale Bereitstellung ist die empfohlene Methode für einen Office 365-Administrator zum Bereitstellen von Office-Add-Ins (Word, Excel, PowerPoint und Outlook) für Benutzer und Gruppen in einer Organisation, vorausgesetzt, die Organisation erfüllt alle Anforderungen für die Verwendung der zentralisierten Bereitstellung, wie in diesem Artikel beschrieben.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Wo kann ich wissen, ob meine Organisation für die zentrale Bereitstellung eingerichtet ist?  

Die zentrale Bereitstellung von Add-Ins erfordert, dass Benutzer Microsoft 365 Apps for Enterprise verwenden (und mit ihren Anmeldeinformationen für die Organisation bei Office angemeldet sind) und über Exchange Online-Postfächer verfügen. Ihr Abonnementverzeichnis muss sich entweder in Azure Active Directory befinden oder in einem Verbund mit azure active Directory sein.  
 
Die zentrale Bereitstellung wird nur für Onlinepostfächer unterstützt. Die Bereitstellung in lokalen Exchange-Postfächern wird nicht unterstützt.

Sie können die [Kompatibilitätsprüfung für](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)die zentrale Bereitstellung verwenden, um   festzustellen, ob Ihr Abonnement berechtigt ist. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Wie zielen Sie auf Add-In-Benutzerzuweisungen mit zentraler Bereitstellung ab?  

Die zentrale Bereitstellung unterstützt Zuordnungen für einzelne Benutzer, Gruppen und alle Personen im Mandanten. Die zentrale Bereitstellung kann für Benutzer in Gruppen der obersten Ebene oder Gruppen ohne übergeordnete Gruppen verwendet werden, jedoch nicht für Benutzer in geschachtelten Gruppen oder Gruppen mit übergeordneten Gruppen. Die zentrale Bereitstellung ist auch Teil der meisten Azure Active Directory-Gruppen, einschließlich Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen.  

Es ist besser, Gruppenzuweisungen anstelle einzelner Benutzerzuweisungen zu verwenden, um die Verwaltung zu vereinfachen.
 
Weitere Informationen finden Sie unter [Benutzer- und Gruppenzuweisungen](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Wie lange dauert es, bis Add-Ins für alle Benutzer verfügbar sind?  

Es kann bis zu 24 Stunden dauern, bis ein Add-In für alle Benutzer verfügbar ist. Es kann dieselbe Zeit für Add-In-Updates, Änderungen beim Aktivieren oder Deaktivieren oder Entfernen von Add-Ins dauern. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Wie verwalte ich als Administrator den Benutzerzugriff auf Add-Ins für meine Organisation?

Zur einfachen Bereitstellung von Add-Ins für Benutzer, Gruppen oder ihre gesamte Organisation wird empfohlen, dass Administratoren die zentrale Bereitstellung verwenden.

Weitere Informationen zum Verwalten des Benutzerzugriffs finden Sie unter:
 - [Verhindern von Add-In-Downloads durch Deaktivieren des Office Store für alle Clients (außer Outlook)](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Festlegen der Administratoren und Benutzer, die Add-Ins für Outlook installieren und verwalten dürfen](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Bietet die zentrale Bereitstellung Administratoren die Flexibilität, die Bereitstellungsmethode für Outlook-Add-Ins zu wählen?  

Ja. Die zentrale Bereitstellung bietet Administratoren die Flexibilität, während der Add-In-Bereitstellung eine von drei Bereitstellungsmethoden für Outlook-Add-Ins zu wählen:

**Fixed (Standard)**   Das Add-In wird automatisch für die zugewiesenen Benutzer bereitgestellt und kann nicht entfernt werden.  
 
**Verfügbar** Benutzer können das Add-In in Outlook installieren, indem sie home > **Weitere Add-Ins**> verwalten auswählen.
 
**Optional** Das Add-In wird automatisch für die zugewiesenen Benutzer bereitgestellt, kann es jedoch entfernen.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Können Administratoren Branchen-Add-Ins aktualisieren?  

Ja. Administratoren können eine neue Manifestdatei hochladen, um Metadatenänderungen für vom Administrator bereitgestellte BRANCHEN-Add-Ins zu unterstützen. Das Add-In wird aktualisiert, wenn die Office-Anwendungen das nächste Mal gestartet werden. Die Webanwendung kann sich jederzeit ändern.  
 
Weitere Informationen finden Sie unter [Line-of-Business-Add-In](./manage-addins-in-the-admin-center.md).  

## <a name="can-admins-turn-off-add-ins"></a>Können Administratoren Add-Ins deaktivieren?  

Ja. Administratoren können die von ihnen für alle Benutzer bereitgestellten Add-Ins aus dem Microsoft Admin Center aktivieren oder deaktivieren.

Weitere Informationen finden Sie unter [Add-In-Zustände](./manage-addins-in-the-admin-center.md#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Können Administratoren Add-Ins löschen oder entfernen?

Ja. Administratoren können für alle Benutzer bereitgestellte Add-Ins aus dem Microsoft Admin Center löschen.

Weitere Informationen finden Sie unter [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Können Administratoren kostenpflichtige Add-Ins über den Office Store mithilfe der zentralisierten Bereitstellung bereitstellen? 

Nein. Sie können kostenpflichtige Add-Ins derzeit nicht über den Office Store mithilfe der zentralisierten Bereitstellung bereitstellen.  
 
Wir empfehlen, den ISV-Entwickler für das kostenpflichtige Add-In zu erreichen, um eine Manifestdatei oder eine URL an fordern. Der Mandantenadministrator kann das Add-In dann mithilfe der zentralisierten Bereitstellung als Branchen-Add-In bereitstellen.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Welche Administratorrolle muss ich zum Verwalten von Add-Ins für meine Organisation verwenden?  

Globaler Administrator ist die empfohlene Rolle mit vollständigem Zugriff auf den Add-In-Verwaltungslebenszyklus. Andere Administratorrollen haben einen eingeschränkten Zugriff auf den Add-In-Bereitstellungslebenszyklus. Wenn Sie die Person sind, die Ihr Microsoft 365 Business-Abonnement erworben hat, sind Sie der globale Administrator. 
 
Ihr Abonnement enthält eine Reihe von Administratorrollen, die Sie anderen Benutzern in Ihrer Organisation zuweisen können. Jede Administratorrolle ordnet allgemeine Geschäftsfunktionen zu und erteilt Personen in Ihrer Organisation Berechtigungen zum Ausführen bestimmter Aufgaben im Microsoft 365 Admin Center.  
 
Weitere Informationen finden Sie unter [Zuweisen von Administratorrollen](../add-users/assign-admin-roles.md?view=o365-worldwide). 