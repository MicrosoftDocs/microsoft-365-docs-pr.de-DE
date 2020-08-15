---
title: Tools zum Verwalten von Microsoft 365-Benutzerkonten
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
description: Erfahren Sie, welche Tools Sie verwenden und wie Sie Microsoft 365-Konten verwalten.
ms.openlocfilehash: 205c61c0cff896f93069d225c84dc3086ca30eb5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690777"
---
# <a name="tools-to-manage-microsoft-365-user-accounts"></a>Tools zum Verwalten von Microsoft 365-Benutzerkonten

Je nach Konfiguration können Sie Microsoft 365-Benutzer auf verschiedene Arten verwalten. Sie können Benutzer im [Microsoft 365 Admin Center](https://admin.microsoft.com), Windows PowerShell, in Active Directory-Domänendienste (AD DS) oder im Azure Active Directory (Azure AD)-Verwaltungsportal verwalten. 

Sobald Sie Microsoft 365 erworben haben, können das Admin Center und Windows PowerShell zum Verwalten von Konten verwendet werden. Bei der Verwaltung von Cloud-Identitäten verfügt jede Person in Ihrer Organisation über eine separate Benutzer-ID und ein separates Kennwort für Microsoft 365. Wenn Sie in Ihre lokale Infrastruktur integrieren und Benutzerkonten mit Microsoft 365 synchronisieren möchten, können Sie Azure AD Connect verwenden, um die Synchronisierung von Identitäten und Kennwörtern für die Funktionalität für einmaliges Anmelden bereitzustellen.
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planen, wo und wie Sie Ihre Benutzerkonten verwalten können

Wo und wie Sie Ihre Benutzerkonten verwalten können, hängt vom Identitätsmodell ab, das Sie für Ihre Microsoft 365 verwenden möchten. Die beiden Gesamt Modelle sind die Cloud-Authentifizierung und die Verbundauthentifizierung.
  
### <a name="cloud-authentication"></a>Cloud-Authentifizierung

- Cloud-Authentifizierung – erstellen und Verwalten von Benutzern im Microsoft 365 Admin Center. Sie können auch Windows PowerShell oder Azure AD verwenden. 
    
- Password Hash Sync (PHS) mit nahtlosem einmaligem Anmelden – die einfachste Möglichkeit zum Aktivieren der Authentifizierung für AD DS-Objekte in Azure AD. Mit PHS synchronisieren Sie Ihre AD DS-Benutzerkonto Objekte mit Microsoft 365 und verwalten Ihre Benutzer lokal. 
    
- Pass-Through-Authentifizierung (PTA) mit nahtlosem einmaligem Anmelden – bietet eine einfache Kennwortüberprüfung für Azure AD Authentifizierungsdienste mit einem Software-Agent, der auf einem oder mehreren lokalen Servern läuft, um die Benutzer direkt mit Ihrem AD DS zu validieren. 
    
### <a name="federated-authentication"></a>Verbundauthentifizierung

- Optionen für die Verbundauthentifizierung: in erster Linie für große Unternehmensorganisationen mit komplexeren Authentifizierungsanforderungen werden AD DS Objekte mit Microsoft 365 synchronisiert, und Benutzerkonten werden lokal verwaltet. 
    
- [Authentifizierungs-und Identitätsanbieter von Drittanbietern](about-microsoft-365-identity.md) – AD DS-Objekte können mit Microsoft 365 synchronisiert werden, und der Zugriff auf Cloud-Ressourcen wird in erster Linie von einem Drittanbieter-Identitätsanbieter (IDP) verwaltet. 
    
## <a name="managing-accounts"></a>Verwalten von Konten

Berücksichtigen Sie bei der Entscheidung, wie Ihre Organisation Konten erstellen und verwalten soll, die folgenden Anforderungen:
  
- Die Verzeichnis Synchronisierungssoftware muss auf Servern in Ihrer lokalen Umgebung installiert sein, um die Identitäten zwischen Microsoft 365 und Ihrem AD DS zu verbinden.
    
- Für eine beliebige Verzeichnissynchronisierungsoption, einschließlich SSO-Optionen, müssen Ihre AD DS Attribute den Standards entsprechen. Die Besonderheiten der Attribute, die in Ihrem Verzeichnis verwendet werden und welche Bereinigung (falls vorhanden) erforderlich ist, finden Sie unter [Prepare to Provision users Through Directory Synchronization to Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Planen Sie, wie Sie Microsoft 365-Konten erstellen.
    
    In der folgenden Tabelle sind die verschiedenen Kontenverwaltungstools aufgeführt.
    
|**Option**|**Notizen**|
|:-----|:-----|
|Admin Center  <br/> |[Benutzer einzeln oder in Massen hinzufügen](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Stellt eine einfache Weboberfläche zum Hinzufügen und Ändern von Benutzerkonten bereit.  <br/>  Kann nicht zum Ändern von Benutzern verwendet werden, wenn die Verzeichnissynchronisierung aktiviert ist (Standort-und Lizenzzuweisung können festgelegt werden).  <br/>  Kann nicht mit SSO-Optionen verwendet werden.  <br/> |
|Windows PowerShell  <br/> |[Verwalten von Microsoft 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Ermöglicht Ihnen das Hinzufügen von Benutzern in Massen Benutzern mithilfe eines Windows PowerShell Skripts.  <br/>  Kann zum Zuweisen von Standort und Lizenzen zu Konten verwendet werden, unabhängig davon, wie die Konten erstellt werden.  <br/> |
|Massenimport  <br/> |[Gleichzeitiges Hinzufügen von mehreren Benutzern](add-several-users-at-the-same-time.md) <br/>  Ermöglicht das Importieren einer CSV-Datei zum Hinzufügen einer Gruppe von Benutzern zu Microsoft 365.  <br/>  Kann nicht mit SSO-Optionen verwendet werden.  <br/> |
|Azure AD  <br/> |Sie erhalten eine ﻿kostenlose Edition von Azure AD mit Ihrem Microsoft 365-Abonnement. Sie können Funktionen wie das Zurücksetzen von Self-Service-Kennwörtern für Cloud-Benutzer und die Anpassung der Seiten der Anmelde-und Zugriffs Konsole mithilfe der kostenlosen Edition ausführen. Um eine erweiterte Funktionalität zu erhalten, können Sie ein Upgrade auf die Basic Edition, Azure AD Premium P1 oder Azure AD Premium P2 durchführen. Eine Liste der unterstützten Features finden Sie unter [Azure AD Editions](https://go.microsoft.com/fwlink/p/?LinkId=698465) .  <br/> |
|Verzeichnissynchronisierung  <br/> |[Integrieren Ihrer lokalen Identitäten in Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  Verwenden Sie für die Verzeichnissynchronisierung mit oder ohne Kennwortsynchronisierung [Azure AD Connect with Express Settings](https://go.microsoft.com/fwlink/p/?LinkID=698537).  <br/>  Verwenden Sie für mehrere Gesamtstrukturen und SSO-Optionen die [benutzerdefinierte Installation von Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).  <br/>  Stellt die Infrastruktur bereit, die zum Aktivieren von SSO erforderlich ist.  <br/>  Für viele Hybrid Szenarien erforderlich:  <br/>  Mehrstufige Migration  <br/>  Hybrid Exchange  <br/>  Synchronisiert Sicherheits-und e-Mail-aktivierte Gruppen von Ihrem AD DS.  <br/> |
   
- Unabhängig davon, wie Sie die Benutzerkonten zu Microsoft 365 hinzufügen möchten, müssen Sie mehrere Konto Funktionen wie das Zuweisen von Lizenzen, die Angabe des Standorts usw. verwalten. Diese Features können langfristig über das Admin Center verwaltet werden, oder Sie können auch [Benutzerkonten mit PowerShell erstellen](https://go.microsoft.com/fwlink/p/?LinkId=717083).
    
    Wenn Sie alle Benutzer über das Admin Center hinzufügen und verwalten möchten, geben Sie den Standort an, und weisen Sie gleichzeitig mit dem Erstellen des Microsoft 365-Kontos Lizenzen zu. Daher ist nicht viel Planung erforderlich.
    
    > [!IMPORTANT]
    > Das Erstellen von Konten in Microsoft 365 ohne Zuweisen einer Lizenz (beispielsweise zu SharePoint Online) bedeutet, dass der Kontobesitzer das Microsoft 365 Center anzeigen kann, aber keinen der Dienste im Abonnement Ihres Unternehmens zugreifen kann. Nachdem Sie einen Standort und die Lizenz zugewiesen haben, wird das Konto auf den Dienst oder die Dienste repliziert, die Sie zugewiesen haben. Der Benutzer kann sich bei seinem Konto anmelden und die Ihnen zugewiesenen Dienste verwenden. 
  
## <a name="next-steps"></a>Nächste Schritte

[Microsoft 365-Integration in lokale Umgebungen](microsoft-365-integration.md)
  
## <a name="see-also"></a>Siehe auch

[Verwalten von Benutzern und Gruppen in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users)
  
