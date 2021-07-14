---
title: Zusätzliche Azure Active Directory-Informationen für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Zusammenfassung: Zusätzliche Azure Active Directory-Informationen zur Migration von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen.'
ms.openlocfilehash: 0e7abd68945a9b685a33c120ff1e92fda62b2c56
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362726"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Zusätzliche Azure Active Directory-Informationen für die Migration von Microsoft Cloud Deutschland

Um den Umzug von der deutschen Azure Cloud in die öffentliche Azure Cloud abzuschließen, empfehlen wir, den Authentifizierungsendpunkt, Azure Active Directory (Azure AD) Graph und MS Graph-Endpunkte für Ihre Anwendungen auf die der kommerziellen Cloud zu aktualisieren, wenn der OpenID Connect (OIDC)-Endpunkt,`https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, beginnt, kommerzielle Cloud-Endpunkte zu melden. 
 
**Wann sollte ich diese Änderung vornehmen?**

Sie erhalten eine Benachrichtigung im Azure/Office-Portal, wenn Ihr Mandant die Migration von der deutschen Cloud in die kommerzielle Cloud abgeschlossen hat. Sie haben 30 Tage nach Erhalt dieser Benachrichtigung Zeit, diese Aktualisierungen abzuschließen, damit Ihre App weiterhin für Mandanten funktioniert, die von der Azure Deutschland Cloud in die Azure Public Cloud migriert werden.
 
Es gibt drei Voraussetzungen, um Ihre Anmeldeberechtigung zu aktualisieren:

 - OIDC-Ermittlungsendpunkt für Ihren Mandant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`gibt Azure AD Public Cloud-Endpunkte zurück.

 - Wenn Ihr Mandant für den Verbund eingerichtet ist, wird Active Directory-Verbunddienste (AD FS) aktualisiert, um mit Azure AD Public zu synchronisieren. Sie können den Anweisungen zum Aktualisieren der Azure AD Connect-Einstellungen folgen, um diese Änderung vorzunehmen.

 - Ressourcenanwendungen, falls vorhanden, die von Ihren Anwendungen verwendet werden, werden so geändert, dass sie Token akzeptieren, die sowohl von Azure AD Germany als auch von Azure AD Public signiert sind.
 
**Welche Art von Anwendungen?**

Eine Anwendung könnte eine der folgenden sein:

- [Einzelseiten-App (Single Page App, SPA)](/azure/active-directory/develop/scenario-spa-overview)
- [Web-App, die Benutzer anmeldet](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Web-App, welches Web-APIs aufruft](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [Geschützte Web-API](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [Web-API, welches Web-APIs aufruft](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Desktop-App](/azure/active-directory/develop/scenario-desktop-overview)
- [Daemon-App](/azure/active-directory/develop/scenario-daemon-overview)
- [Mobile App](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Wenn eine Anwendung zur Verwendung `login.microsoftonline.com` als Autorität wechselt, werden die Token von dieser neuen Autorität signiert. Wenn Sie Ressourcenanwendungen hosten, die von anderen Anwendungen aufgerufen werden, müssen Sie eine laxe Token-Validierung zulassen. Das bedeutet, dass Ihre App Token zulassen muss, die sowohl von der Azure AD Germany als auch von der Azure AD Public Cloud signiert sind. Diese laxe Token-Validierung ist erforderlich, bis alle Client-Anwendungen, die Ihren Dienst aufrufen, vollständig in die Azure AD Public Cloud migriert sind. Nach der Migration muss Ihre Ressourcenanwendung nur noch von der Azure AD Public Cloud signierte Token akzeptieren.

**Was muss ich sonst noch wissen?**

1. Wenn Sie eine Anwendung in Azure Deutschland hosten, die zur Authentifizierung von Benutzern von Azure Deutschland oder Office 365 Deutschland verwendet wird, stellen Sie sicher, dass `https://login.microsoftonline.com` diese als Autorität im Authentifizierungskontext verwendet wird.

    - Siehe Azure AD-Authentifizierungskontexte.
    - Dies gilt sowohl für die Authentifizierung gegenüber Ihrer Anwendung als auch für die Authentifizierung gegenüber allen APIs, die Ihre Anwendung möglicherweise aufruft (d. h. Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Aktualisieren Sie den Azure AD Graph-Endpunkt auf `https://graph.windows.net`.

3. Aktualisieren Sie den MS Graph-Endpunkt auf `https://graph.microsoft.com`.

4. Aktualisieren Sie alle deutschen Cloud-Endpunkte (z. B. die für Exchange Online und SharePoint Online), die von Ihren Anwendungen verwendet werden, auf die der öffentlichen Cloud.

5. Aktualisieren Sie Umgebungsparameter auf `AzurePublic` (statt `AzureGermany`) in administrativen Tools und Skripten für:

    - [Azure PowerShell](/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](/powershell/azure/active-directory/install-adv2)
    - [Azure CLI](/cli/azure/install-azure-cli)
 
**Was ist mit Anwendungen, die ich veröffentliche?**

Wenn Sie eine Anwendung veröffentlichen, die für Benutzer verfügbar ist, die nicht zu Ihrem Mandanten gehören, müssen Sie möglicherweise Ihre Anwendungsregistrierung ändern, um die Kontinuität zu gewährleisten. Andere Mandanten, die Ihre Anwendung verwenden, werden möglicherweise zu einem anderen Zeitpunkt als Ihr Mandant umgestellt. Um sicherzustellen, dass sie nie den Zugriff auf Ihre Anwendung verlieren, müssen Sie zustimmen, dass Ihre App von Azure Deutschland nach Azure Public synchronisiert wird.

**Was ist mit dem Hinzufügen neuer mandantenfähiger Anwendungen während der Migration?**

Wenn Sie eine neue Anwendung nutzen möchten, die von einer anderen Organisation veröffentlicht wird (mandantenfähige Anwendung), können Sie diese Anwendung während des Migrationsprozesses (Phasen 2 bis 9) nicht hinzufügen.  Sie können diese Aufgabe ausführen, wenn Ihre Organisation Phase 9 abgeschlossen hat und vollständig auf die öffentliche Azure-Instanz umgestellt ist.

## <a name="additional-considerations"></a>Zusätzliche Überlegungen

Hier sind einige zusätzliche Überlegungen für Azure AD:

- Für Verbundauthentifizierung:

  - Sie dürfen eine Verbunddomäne nicht erstellen, befördern oder degradieren, solange der Mandantenrwechsel läuft. Nachdem die Migration zum Azure AD-Dienst abgeschlossen ist (der Mandant ist vollständig), können Sie die Verwaltung von Verbunddomänen wieder aufnehmen.

  - Wenn Sie die Verbundauthentifizierung mit Active Directory-Verbunddienste (AD FS) verwenden, sollten Sie während der Migration keine Änderungen an den Aussteller-URIs vornehmen, die für alle Authentifizierungen mit Ihren lokalen Active Directory Domain Services (AD DS) verwendet werden. Das Ändern von Aussteller-URIs führt zu Authentifizierungsfehlern für Benutzer in der Domäne. Aussteller-URIs können direkt in AD FS geändert werden oder wenn eine Domäne von verwaltet zu Verbund oder umgekehrt konvertiert wird. Microsoft empfiehlt Kunden, keine Verbunddomäne in dem zu migrierenden Azure AD-Mandant hinzuzufügen, zu entfernen oder zu konvertieren. Aussteller-URIs können nach Abschluss der Migration geändert werden.

- Für den Netzwerkbetrieb:

  - Das Erstellen von IPv6-benannten Netzwerken funktioniert nicht im Azure-Portal, `http://portal.microsoftazure.de/`. Verwenden Sie das Azure-Portal unter `https://portal.azure.com`, um IPv6-benannte Netzwerke zu erstellen.
 
   - Sie können keine vertrauenswürdigen IP-Adressbereiche für die Einstellungen des Azure Multi-Faktor-Authentifizierungsdienstes (MFA) über das Microsoft Cloud Deutschland-Portal erstellen. Verwenden Sie das Azure AD-Portal für Office 365-Dienste, um vertrauenswürdige IP-Adressbereiche für Azure MFA zu erstellen.


- Verwenden von bedingtem Zugriff: 

  - Richtlinien für bedingten Zugriff mit den folgenden Berechtigungskontrollen werden erst nach Abschluss der Migration zu Office 365-Diensten unterstützt (nach der ["Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) Migrationsphase"):

    - Kompatible Geräte erforderlich
    - Erfordert genehmigte Apps
    - Erfordert eine App-Schutzrichtlinie
    
  - Die Richtlinienschnittstelle für bedingten Zugriff gibt eine falsche Warnung darüber aus, dass Sicherheitsvorgaben für den Mandanten aktiviert sind, selbst wenn sie deaktiviert ist und Richtlinien für bedingten Zugriff bereits für den Mandanten existieren. Sie sollten die Warnung ignorieren oder das Office 365-Dienstportal verwenden, um Richtlinien für bedingten Zugriff zu verwalten. 

- Intune-Szenarien werden nur gegen weltweite Endpunkte unterstützt, nachdem die Mandantenmigration abgeschlossen ist, einschließlich aller Migrationen von Office-Workloads.

- Microsoft Cloud Deutschland-Benutzer, die die Mobile App Benachrichtigungsmethode für MFA-Anfragen verwenden, sehen in der Microsoft Authenticator-App die ObjectId (eine GUID) des Benutzers anstelle des Benutzerprinzipalname (UPN). Nachdem die Migration des Azure AD-Mandanten abgeschlossen ist und in Office 365-Diensten gehostet wird, werden bei neuen Microsoft Authenticator-Aktivierungen die UPNs der Benutzer angezeigt. Bestehende Microsoft Authenticator-Konten zeigen weiterhin die ObjectId des Benutzers an, funktionieren aber auch weiterhin für mobile App-Benachrichtigungen. 

- Für Mandanten, die nach dem 22. Oktober 2019 erstellt werden, können die Sicherheitsvorgaben für den Mandanten automatisch aktiviert werden, wenn er auf den Office 365-Dienst migriert wird. Mandantenadministratoren können wählen, ob sie die Sicherheitsvorgaben aktiviert lassen und sich für MFA registrieren oder ob sie die Funktion deaktivieren. Weitere Informationen finden Sie in dieser [Übersicht der Sicherheitsstandards](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults). 

  > [!NOTE]
  > Organisationen, die während der Migration nicht automatisch aktiviert werden, können in Zukunft dennoch automatisch registriert werden, wenn die Funktion zur Aktivierung von Sicherheitsvorgaben im Office 365-Dienst ausgerollt wird. Administratoren, die die Sicherheitsvorgaben explizit deaktivieren oder aktivieren möchten, können dies tun, indem sie die Funktion unter **Azure Active Directory > Eigenschaften aktualisieren**. Nachdem die Funktion explizit vom Administrator aktiviert wurde, wird sie nicht mehr automatisch aktiviert.

- Es wird eine Warnung über die Version von Azure AD Connect im Office 365 Deutschland-Portal sowie im Office 365-Portal angezeigt, sobald der Mandant in der Migration ist. Dies kann ignoriert werden, wenn die Versionswarnung nicht mehr angezeigt wird, nachdem die Migration abgeschlossen ist. Wenn vor oder nach der Migration in einem der beiden Portale eine Warnung angezeigt wird, muss Azure AD Connect aktualisiert werden. Die Warnmeldung lautet: "Wir haben festgestellt, dass Sie ein veraltetes Verzeichnis-Synchronisierungstool verwenden. Wir empfehlen Ihnen, das Microsoft Download Center zu besuchen, um die neueste Version von Azure AD Connect zu erhalten."

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](/dynamics365/get-started/migrate-data-german-region)
- [Informationen zum Power BI-Migrationsprogramm](/power-bi/admin/service-admin-migrate-data-germany)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](/microsoftteams/upgrade-start-here)
