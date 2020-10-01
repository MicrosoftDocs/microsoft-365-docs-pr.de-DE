---
title: Verwalten von Microsoft 365-Benutzerkonten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Hier erfahren Sie, wie Sie Microsoft 365-Benutzerkonten verwalten.
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327759"
---
# <a name="manage-microsoft-365-user-accounts"></a>Verwalten von Microsoft 365-Benutzerkonten

Je nach Konfiguration können Sie Microsoft 365-Benutzerkonten auf verschiedene Arten verwalten. Sie können Benutzerkonten im [Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/add-users/), in [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), in Active Directory-Domänendienste (AD DS) oder im Azure Active Directory (Azure AD)-Verwaltungsportal verwalten. 

Sobald Sie Microsoft 365 erworben haben, können Sie das Microsoft 365 Admin Center und die PowerShell zum Verwalten von Konten verwenden. Bei der Verwaltung von Cloud-Identitäten verfügt jede Person in Ihrer Organisation über einen separaten Benutzerkontonamen und ein separates Kennwort. Wenn Sie eine Integration in Ihre lokale Infrastruktur durchführen und Benutzerkonten mit Microsoft 365 synchronisieren möchten, können Sie Azure AD Connect verwenden, um die Synchronisierung von Identitäten und Kennwörtern für einmaliges Anmelden (SSO)-Funktionen bereitzustellen.
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planen, wo und wie Sie Ihre Benutzerkonten verwalten können

Wo und wie Sie Ihre Benutzerkonten verwalten können, hängt vom Identitätsmodell ab, das Sie für Ihre Microsoft 365 verwenden möchten. Die beiden Gesamt Modelle sind nur in der Cloud und Hybrid.
  
### <a name="cloud-only"></a>Rein cloudbasiert

Sie erstellen und verwalten Benutzer im Microsoft 365 Admin Center. Sie können auch PowerShell oder das Azure AD Admin Center verwenden. 
    
### <a name="hybrid"></a>Hybrid

Benutzerkonten werden mit Microsoft 365 von AD DS synchronisiert, daher müssen Sie lokale AD DS Tools zum Verwalten von Benutzerkonten verwenden. 
    
## <a name="managing-accounts"></a>Verwalten von Konten

Berücksichtigen Sie bei der Entscheidung, wie Ihre Organisation Konten erstellen und verwalten soll, die folgenden Anforderungen:
  
- Die Verzeichnis Synchronisierungssoftware muss auf Servern in Ihrer lokalen Umgebung installiert sein, um die Identitäten zwischen Microsoft 365 und Ihrem AD DS zu verbinden.
    
- Für eine beliebige Verzeichnissynchronisierungsoption, einschließlich SSO-Optionen, müssen Ihre AD DS-Attribute den Standards entsprechen. Die Besonderheiten der Attribute, die in Ihrem Verzeichnis verwendet werden und welche Bereinigungen (falls vorhanden) erforderlich sind, werden unter [Prepare for Directory Synchronization to Microsoft 365](prepare-for-directory-synchronization.md)beschrieben. 
    
- Planen Sie, wie Sie Microsoft 365-Konten erstellen.
    
In der folgenden Tabelle sind die verschiedenen Kontenverwaltungstools aufgeführt.
    
|Tool|Anmerkungen|
|:-----|:-----|
|Microsoft 365 Admin Center  <br/> |[Benutzer einzeln oder in Massen hinzufügen](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Stellt eine einfache Weboberfläche zum Hinzufügen und Ändern von Benutzerkonten bereit.  <br/>  Kann nicht zum Ändern von Benutzern verwendet werden, wenn die Verzeichnissynchronisierung aktiviert ist (Standort-und Lizenzzuweisung können festgelegt werden).  <br/>  Kann nicht mit SSO-Optionen verwendet werden.  <br/> |
|Windows PowerShell  <br/> |[Verwalten von Microsoft 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Ermöglicht Ihnen das Hinzufügen von Benutzern in Massen Benutzern mithilfe eines Windows PowerShell Skripts.  <br/>  Kann zum Zuweisen von Standort und Lizenzen zu Konten verwendet werden, unabhängig davon, wie die Konten erstellt werden.  <br/> |
|Massenimport  <br/> |[Gleichzeitiges Hinzufügen von mehreren Benutzern](add-several-users-at-the-same-time.md) <br/>  Ermöglicht das Importieren einer CSV-Datei zum Hinzufügen einer Gruppe von Benutzern zu Microsoft 365.  <br/>  Kann nicht mit SSO-Optionen verwendet werden.  <br/> |
|Azure AD  <br/> |Sie erhalten eine ﻿kostenlose Edition von Azure AD mit Ihrem Microsoft 365-Abonnement. Sie können Funktionen wie das Zurücksetzen von Self-Service-Kennwörtern für Cloud-Benutzer und die Anpassung der Seiten der Anmelde-und Zugriffs Konsole mithilfe der kostenlosen Edition ausführen. Um eine erweiterte Funktionalität zu erhalten, können Sie ein Upgrade auf die Basic Edition, Azure AD Premium P1 oder Azure AD Premium P2 durchführen. Eine Liste der unterstützten Features finden Sie unter [Azure AD Editions](https://go.microsoft.com/fwlink/p/?LinkId=698465) .  <br/> |
|Verzeichnissynchronisierung  <br/> |[Integrieren Ihrer lokalen Identitäten in Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  Verwenden Sie für die Verzeichnissynchronisierung mit oder ohne Kennwortsynchronisierung [Azure AD Connect with Express Settings](https://go.microsoft.com/fwlink/p/?LinkID=698537).  <br/>  Verwenden Sie für mehrere Gesamtstrukturen und SSO-Optionen die [benutzerdefinierte Installation von Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).  <br/>  Stellt die Infrastruktur bereit, die zum Aktivieren von SSO erforderlich ist.  <br/>  Erforderlich für viele Hybrid Szenarien wie mehrstufige Migration und Hybriden Exchange  <br/>  Synchronisiert Sicherheits-und e-Mail-aktivierte Gruppen von Ihrem AD DS.  <br/> |
|||
   
- Unabhängig davon, wie Sie die Benutzerkonten zu Microsoft 365 hinzufügen möchten, müssen Sie mehrere Konto Funktionen wie das Zuweisen von Lizenzen, die Angabe des Standorts usw. verwalten. Diese Features können langfristig über das Microsoft 365 Admin Center verwaltet werden, oder Sie können auch [Benutzerkonten mit PowerShell erstellen](https://go.microsoft.com/fwlink/p/?LinkId=717083).
    
    Wenn Sie alle Benutzer über das Admin Center hinzufügen und verwalten möchten, geben Sie den Standort an, und weisen Sie gleichzeitig mit dem Erstellen des Microsoft 365-Kontos Lizenzen zu. Daher ist nicht viel Planung erforderlich.
    
    > [!IMPORTANT]
    > Das Erstellen von Konten in Microsoft 365 ohne Zuweisen einer Lizenz (beispielsweise zu SharePoint Online) bedeutet, dass der Kontobesitzer das Microsoft 365 Center anzeigen kann, aber keinen der Dienste im Abonnement Ihres Unternehmens zugreifen kann. Nachdem Sie einen Standort und die Lizenz zugewiesen haben, wird das Konto auf den Dienst oder die Dienste repliziert, die Sie zugewiesen haben. Der Benutzer kann sich bei seinem Konto anmelden und die Ihnen zugewiesenen Dienste verwenden. 
  
## <a name="see-also"></a>Mehr dazu

[Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/add-users)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
