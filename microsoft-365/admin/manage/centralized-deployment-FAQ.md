---
title: FAQ zur zentralen Bereitstellung
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Lesen Sie die Antworten auf häufige Fragen zur zentralisierten Bereitstellung im Microsoft 365 Admin Center.
ms.openlocfilehash: 0d0f2163982042f7b8f868a36f5cc115a17295a2
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399824"
---
# <a name="centralized-deployment-faq"></a>FAQ zur zentralen Bereitstellung

Die zentralisierte Bereitstellung ist die empfohlene Vorgehensweise für einen Office 365 Administrator zum Bereitstellen von Office-Add-Ins (Word, Excel, PowerPoint und Outlook) für Benutzer und Gruppen in einer Organisation, vorausgesetzt, die Organisation erfüllt alle Anforderungen für die Verwendung einer zentralisierten Bereitstellung, wie in diesem Artikel beschrieben.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Woher weiß ich, ob meine Organisation für die zentrale Bereitstellung eingerichtet ist?  

Die zentrale Bereitstellung von Add-ins erfordert, dass Benutzer Microsoft 365-Apps für Unternehmen verwenden (und mit Ihren Anmeldeinformationen für die organisatorische Anmeldung bei Office angemeldet sind) und über Exchange Online Postfächer verfügen. Ihr Abonnement Verzeichnis muss sich entweder in oder im Verbund mit, Azure Active Directory befinden.  
 
Die zentralisierte Bereitstellung wird nur für Online Postfächer unterstützt. Die Bereitstellung für lokale Exchange-Postfächer wird nicht unterstützt.
 
Sie können die [Office 365 zentrale Bereitstellungs Kompatibilitätsprüfung](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)verwenden   , um zu ermitteln, ob Ihr Abonnement berechtigt ist. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Wie Zielen Sie auf Add-in-Benutzerzuweisungen mit zentralisierter Bereitstellung ab?  

Die zentralisierte Bereitstellung unterstützt Zuweisungen für einzelne Benutzer, Gruppen und alle Personen im Mandanten. Die zentralisierte Bereitstellung kann für Benutzer in Gruppen oder Gruppen auf oberster Ebene ohne übergeordnete Gruppen verwendet werden, jedoch nicht für Benutzer in geschachtelten Gruppen oder Gruppen, die übergeordnete Gruppen haben. Die zentralisierte Bereitstellung ist auch Teil der meisten Azure Active Directory-Gruppen, einschließlich Office 365 Gruppen, Verteilerlisten und Sicherheitsgruppen.  

Es ist besser, Gruppenzuweisungen anstelle der einzelnen Benutzerzuweisungen zu verwenden, um die Verwaltung zu vereinfachen.
 
Weitere Informationen finden Sie unter [Benutzer-und Gruppenzuweisungen](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Wie lange dauert es, bis Add-Ins für alle Benutzer angezeigt werden?  

Es kann bis zu 24 Stunden dauern, bis ein Add-in für alle Benutzer angezeigt wird. Es kann die gleiche Zeit für Add-in-Updates, Änderungen von ein-oder ausschalten oder Add-in-Entfernungen dauern. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Wie kann ich als Administrator den Benutzer Zugriff auf Add-Ins für meine Organisation verwalten?

Für eine einfache Bereitstellung von Add-Ins für Benutzer, Gruppen oder für Ihre gesamte Organisation wird empfohlen, dass Administratoren eine zentralisierte Bereitstellung verwenden.

Weitere Informationen zum Verwalten des Benutzerzugriffs finden Sie unter </br>[Verhindern von Add-in-Downloads durch Deaktivieren der Office Store für alle Clients (außer Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) und </br>[Geben Sie die Administratoren und Benutzer an, die Add-Ins für Outlook installieren und verwalten können](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Bietet die zentralisierte Bereitstellung Administratoren die Flexibilität, die Bereitstellungsmethode für Outlook-Add-Ins auszuwählen?  

Ja. Die zentralisierte Bereitstellung bietet Administratoren die Möglichkeit, während der Add-in-Bereitstellung eine von drei Bereitstellungsmethoden für Outlook-Add-Ins auszuwählen:

**Fixed (Standard)**   Das Add-in wird automatisch für die zugewiesenen Benutzer bereitgestellt und kann nicht entfernt werden.  
 
**Verfügbar** Benutzer können das Add-in in Outlook installieren, indem Sie "Home" auswählen > Weitere Add-Ins > admin-Managed hinzufügen.   
 
**Optional** Das Add-in wird automatisch für die zugewiesenen Benutzer bereitgestellt, aber Sie können es auswählen, um es zu entfernen.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Können Administratoren Lob-Add-Ins (Business) aktualisieren?  

Ja. Administratoren können eine neue Manifestdatei hochladen, um Änderungen an Metadaten für vom Administrator bereitgestellte Lob-Add-Ins zu unterstützen. Das Add-in wird aktualisiert, wenn die Office-Anwendungen das nächste Mal gestartet werden. Die Webanwendung kann sich jederzeit ändern.  
 
Weitere Informationen finden Sie unter Branchen [-Add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).  

## <a name="can-admins-turn-off-add-ins"></a>Können Administratoren Add-Ins deaktivieren?  

Ja. Administratoren können die Add-Ins, die Sie für alle Benutzer aus dem Microsoft Admin Center bereitstellen, aktivieren oder deaktivieren.

Weitere Informationen finden Sie unter [Add-in-Status](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Können Administratoren Add-ins löschen oder entfernen?

Ja. Administratoren können Add-Ins, die Sie für alle Benutzer bereitgestellt haben, aus dem Microsoft Admin Center löschen.

Weitere Informationen finden Sie unter [delete the Add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Können Administratoren kostenpflichtige Add-Ins aus dem Office Store mithilfe einer zentralisierten Bereitstellung bereitstellen? 

Nein. Sie können zu diesem Zeitpunkt keine kostenpflichtigen Add-Ins aus dem Office Store mithilfe einer zentralisierten Bereitstellung bereitstellen.  
 
Wir empfehlen, den ISV-Entwickler für das kostenpflichtige Add-in zu erreichen, um eine Manifestdatei oder eine URL anzufordern. Der mandantenadministrator kann das Add-in dann mithilfe einer zentralisierten Bereitstellung als Lob-Add-in bereitstellen.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Welche Administratorrolle muss ich für die Verwaltung von Add-Ins für meine Organisation übernehmen?  

Sie müssen über die globale Administratorrolle zum Verwalten von Add-Ins verfügen. Wenn Sie die Person sind, die Ihr Microsoft 365 for Business-Abonnement erworben hat, sind Sie der globale Administrator. 
 
Ihr Abonnement verfügt über eine Reihe von Administratorrollen, die Sie anderen Benutzern in Ihrer Organisation zuweisen können. Jede Administratorrolle ordnet allgemeine Geschäftsfunktionen zu und gibt Personen in Ihrer Organisation Berechtigungen zum Ausführen bestimmter Aufgaben im Microsoft 365 Admin Center.  
 
Weitere Informationen finden Sie unter [Zuweisen von Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).  