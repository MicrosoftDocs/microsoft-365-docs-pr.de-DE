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
description: Lesen Sie die Antworten auf häufig gestellte Fragen zur zentralen Bereitstellung aus dem Microsoft 365 Admin Center.
ms.openlocfilehash: 0da9ec9595fd433abe1e2e2ae3f2e3a0c6b3b9b5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228004"
---
# <a name="centralized-deployment-faq"></a>FAQ zur zentralen Bereitstellung

Die zentrale Bereitstellung ist die empfohlene Methode für Office 365 Administratoren, Office Add-Ins (Word, Excel, PowerPoint und Outlook) für Benutzer und Gruppen innerhalb einer Organisation bereitzustellen, vorausgesetzt, die Organisation erfüllt alle Anforderungen für die Verwendung der zentralen Bereitstellung, wie in diesem Artikel beschrieben.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Woher weiß ich, ob meine Organisation für die zentrale Bereitstellung eingerichtet ist?  

Die zentrale Bereitstellung von Add-Ins erfordert, dass Benutzer Microsoft 365 Apps for Enterprise verwenden (und mit ihren Anmeldeinformationen der Organisation bei Office angemeldet sind) und über Exchange Online Postfächer verfügen. Ihr Abonnementverzeichnis muss sich entweder in Azure Active Directory befinden oder mit diesem verbunden sein.  
 
Die zentrale Bereitstellung wird nur für Onlinepostfächer unterstützt. Die Bereitstellung in lokalen Exchange Postfächern wird nicht unterstützt.

Sie können die [zentrale Kompatibilitätsprüfung](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)für die Bereitstellung   verwenden, um festzustellen, ob Ihr Abonnement berechtigt ist. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Wie zielen Sie auf Add-In-Benutzerzuweisungen mit der zentralen Bereitstellung ab?  

Die zentrale Bereitstellung unterstützt Zuweisungen zu einzelnen Benutzern, Gruppen und allen Personen im Mandanten. Die zentrale Bereitstellung kann für Benutzer in Gruppen auf oberster Ebene oder Gruppen ohne übergeordnete Gruppen verwendet werden, jedoch nicht für Benutzer in geschachtelten Gruppen oder Gruppen mit übergeordneten Gruppen. Die zentrale Bereitstellung ist auch Teil der meisten Azure Active Directory-Gruppen, einschließlich Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen.  

Zur einfacheren Verwaltung ist es besser, Gruppenzuweisungen anstelle einzelner Benutzerzuweisungen zu verwenden.
 
Weitere Informationen finden Sie unter [Benutzer- und Gruppenzuweisungen.](./centralized-deployment-of-add-ins.md#user-and-group-assignments)  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Wie lange dauert es, bis Add-Ins für alle Benutzer angezeigt werden?  

Es kann bis zu 24 Stunden dauern, bis ein Add-In für alle Benutzer angezeigt wird. Es kann dieselbe Zeit in Anspruch nehmen für Add-In-Updates, Änderungen beim Aktivieren oder Deaktivieren oder Entfernen von Add-Ins. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Wie verwalte ich als Administrator den Benutzerzugriff auf Add-Ins für meine Organisation?

Für die einfache Bereitstellung von Add-Ins für Benutzer, Gruppen oder für Ihre gesamte Organisation empfehlen wir Administratoren die zentrale Bereitstellung.

Weitere Informationen zum Verwalten des Benutzerzugriffs finden Sie unter:
 - [Verhindern von Add-In-Downloads durch Deaktivieren der Office Store auf allen Clients (außer Outlook)](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Festlegen der Administratoren und Benutzer, die Add-Ins für Outlook installieren und verwalten dürfen](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Bietet die zentrale Bereitstellung Administratoren die Flexibilität, die Bereitstellungsmethode für Outlook-Add-Ins auszuwählen?  

Ja. Die zentrale Bereitstellung bietet Administratoren die Flexibilität, eine von drei Bereitstellungsmethoden für Outlook-Add-Ins während der Add-In-Bereitstellung auszuwählen:

**Fixed (Standard)**   Das Add-In wird automatisch für die zugewiesenen Benutzer bereitgestellt und kann nicht entfernt werden.  
 
**Verfügbar** Benutzer können das Add-In in Outlook installieren, indem sie **"Start" > "Weitere Add-Ins abrufen" > vom Administrator verwalteten Add-Ins** auswählen.
 
**Optional** Das Add-In wird automatisch für die zugewiesenen Benutzer bereitgestellt, kann aber auch entfernt werden.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Können Administratoren Branchen-Add-Ins aktualisieren?  

Ja. Administratoren können eine neue Manifestdatei hochladen, um Metadatenänderungen für vom Administrator bereitgestellte BRANCHEN-Add-Ins zu unterstützen. Das Add-In wird beim nächsten Start der Office Anwendungen aktualisiert. Die Webanwendung kann sich jederzeit ändern.  
 
Weitere Informationen finden Sie unter [Branchen-Add-In.](./manage-addins-in-the-admin-center.md)  

## <a name="can-admins-turn-off-add-ins"></a>Können Administratoren Add-Ins deaktivieren?  

Ja. Administratoren können die Add-Ins, die sie für alle Benutzer bereitstellen, über das Microsoft Admin Center aktivieren oder deaktivieren.

Weitere Informationen finden Sie unter [Add-In-Zustände.](./manage-addins-in-the-admin-center.md#add-in-states)  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Können Administratoren Add-Ins löschen oder entfernen?

Ja. Administratoren können Add-Ins, die sie für alle Benutzer bereitgestellt haben, aus dem Microsoft Admin Center löschen.

Weitere Informationen finden Sie unter [Löschen eines Add-Ins.](./manage-addins-in-the-admin-center.md#delete-an-add-in) 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Können Administratoren kostenpflichtige Add-Ins über die Office Store mithilfe der zentralen Bereitstellung bereitstellen? 

Nein. Kostenpflichtige Add-Ins können derzeit nicht über die zentrale Bereitstellung aus dem Office Store bereitgestellt werden.  
 
Wir empfehlen, sich an den ISV-Entwickler für das kostenpflichtige Add-In zu wenden, um eine Manifestdatei oder eine URL anzufordern. Der Mandantenadministrator kann das Add-In dann mithilfe der zentralen Bereitstellung als LOB-Add-In bereitstellen.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Welche Administratorrolle muss ich zum Verwalten von Add-Ins für meine Organisation benötigen?  

Der globale Administrator ist die empfohlene Rolle mit vollständigem Zugriff auf den Add-In-Verwaltungslebenszyklus. Wenn Sie die Person sind, die Ihr Microsoft 365 Business-Abonnement erworben hat, sind Sie der globale Administrator. 
 
Ihr Abonnement enthält eine Reihe von Administratorrollen, die Sie anderen Benutzern in Ihrer Organisation zuweisen können. Jede Administratorrolle ist gängigen Geschäftsfunktionen zugeordnet und bietet Personen in Ihrer Organisation Berechtigungen zum Ausführen bestimmter Aufgaben im Microsoft 365 Admin Center.  
 
Weitere Informationen finden Sie unter [Zuweisen von Administratorrollen.](../add-users/assign-admin-roles.md) 
