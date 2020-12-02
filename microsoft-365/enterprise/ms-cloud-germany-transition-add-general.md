---
title: Weitere allgemeine Informationen für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 'Zusammenfassung: Weitere allgemeine Informationen zu Diensten beim Wechsel von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365 Diensten im neuen rechenzentrumsbereich.'
ms.openlocfilehash: 6fa09165f8aaa68e0f9fc567d96a4e53baaa594e
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551782"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Weitere allgemeine Informationen für die Migration von Microsoft Cloud Deutschland

Die folgenden Abschnitte enthalten weitere Informationen zu Diensten, vorarbeits Überlegungen und Kundenerfahrung.

## <a name="azure-active-directory"></a>Azure Active Directory

Um den Übergang von der Azure German Cloud zur Azure Public Cloud abzuschließen, wird empfohlen, dass der Authentifizierungs Endpunkt, das Azure Active Directory (Azure AD) und die MS Graph-Endpunkte für Ihre Anwendungen auf die der kommerziellen Cloud aktualisiert werden, wenn der OpenID Connect (OIDC)-Endpunkt mit der `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` Berichterstellung für kommerzielle Cloud-Endpunkte beginnt. 
 
**Wann sollte ich diese Änderung vornehmen?**

Wenn Ihr Mandant die Migration von der deutschen Cloud zur kommerziellen Cloud abgeschlossen hat, erhalten Sie eine Benachrichtigung in Azure/Office-Portal. Sie haben 30 Tage nach Erhalt dieser Benachrichtigung, um diese Updates abzuschließen, damit Ihre APP weiterhin für Mandanten arbeitet, die von Azure Deutschland Cloud zu Azure Public Cloud migriert werden.
 
Es gibt drei Voraussetzungen für die Aktualisierung Ihrer Anmelde Autorität:

 - OIDC Discovery-Endpunkt für Ihren Mandanten `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` gibt Azure AD öffentliche Cloud-Endpunkte zurück.

 - Wenn Ihr Mandant für den Verbund eingerichtet ist, wird Active Directory Verbunddienste (AD FS) für die Synchronisierung mit Azure AD Public aktualisiert. Sie können den Anweisungen folgen, um Azure AD Connect-Einstellungen zu aktualisieren, um diese Änderung vorzunehmen.

 - Ressourcen Anwendungen (sofern vorhanden), die von Ihren Anwendungen verwendet werden, werden so geändert, dass Sie Token akzeptieren, die sowohl von Azure AD Deutschland als auch von Azure AD Public signiert sind.
 
**Welche Art von Anwendungen?**

Eine Anwendung kann eine der folgenden sein:

- Einzelseiten-app (Spa)
- Webanwendung, die Benutzer anmeldet
- Webanwendung, die WebAPI-Aufrufe
- Geschützte WebAPI
- WebAPI, die webapis aufruft
- Desktop-App
- Daemon-App
- Mobile App
 
> [!NOTE] 
> Wenn eine Anwendung zur Verwendung `login.microsoftonline.com` als ihre Autorität wechselt, werden die Token von dieser neuen Autorität signiert. Wenn Sie Ressourcen Anwendungen hosten, die von anderen apps aufgerufen werden, müssen Sie die Überprüfung nach Laschen Tokens zulassen. Dies bedeutet, dass Ihre APP Token zulassen muss, die sowohl von der Azure AD Deutschland als auch von Azure AD öffentlichen Clouds signiert sind. Diese Lax-Tokenprüfung wird benötigt, bis alle Clientanwendungen, die ihren Dienst aufrufen, vollständig in die Azure AD öffentliche Cloud migriert werden. Nach der Migration muss die Ressourcen Anwendung nur Token akzeptieren, die von der Azure AD öffentlichen Cloud signiert wurden.

**Was muss ich aktualisieren?**

1. Wenn Sie eine Anwendung in Azure Deutschland hosten, die zur Authentifizierung von Azure Deutschland oder Office 365 Deutschland-Benutzern verwendet wird, stellen Sie sicher, dass Sie `https://login.microsoftonline.com` im Authentifizierungs Kontext als Autorität verwendet wird.

    - Siehe Azure AD Authentifizierungs Kontexte.
    - Dies gilt sowohl für die Authentifizierung für Ihre Anwendung als auch für die Authentifizierung für APIs, die Ihre Anwendung möglicherweise anruft (Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Aktualisieren Sie Azure AD Graph-Endpunkt als `https://graph.windows.net` .

3. Aktualisieren des MS Graph-Endpunkts `https://graph.microsoft.com` .

4. Aktualisieren Sie alle deutschen Cloud-Endpunkte (beispielsweise für Exchange Online und SharePoint Online), die von Ihren Anwendungen für die öffentliche Cloud verwendet werden.

5. Aktualisieren von Umgebungsparametern `AzurePublic` (anstelle von `AzureGermany` ) in Verwaltungstools und Skripts für:

    - Azure PowerShell
    - Azure AD PowerShell (MSOnline)
    - Azure AD PowerShell (AzureAD)
    - Azure-CLI
 
**Was ist mit Anwendungen, die ich veröffentliche?**

Wenn Sie eine Anwendung veröffentlichen, die Benutzern außerhalb Ihres Mandanten zur Verfügung steht, müssen Sie möglicherweise Ihre Anwendungsregistrierung ändern, um die Kontinuität sicherzustellen. Andere Mandanten, die Ihre Anwendung verwenden, werden möglicherweise zu einem anderen Zeitpunkt als Ihr Mandant verschoben. Um sicherzustellen, dass der Zugriff auf Ihre Anwendung nie verloren geht, müssen Sie sich damit einverstanden erklären, dass Ihre APP von Azure Deutschland zu Azure Public synchronisiert wird.

### <a name="additional-considerations"></a>Zusätzliche Überlegungen

Hier sind einige zusätzliche Überlegungen für Azure AD:

- Für die Verbundauthentifizierung:

  - Sie dürfen keine Verbunddomäne erstellen, Heraufstufen oder höher stufen, während der Mandanten Übergang in Bearbeitung ist. Nachdem die Migration zum Azure AD Dienst abgeschlossen ist (der Mandant ist vollständig abgeschlossen), können Sie die Verwaltung von Verbunddomänen fortsetzen.

  - Wenn Sie die Verbundauthentifizierung mit Active Directory Verbunddienste (AD FS) verwenden, sollten Sie keine Änderungen an den Herausgeber-URIs vornehmen, die für die gesamte Authentifizierung mit Ihrem lokalen Active Directory-Domänendienste (AD DS) während der Migration verwendet werden. Das Ändern von Aussteller-URIs führt zu Authentifizierungsfehlern für Benutzer in der Domäne. Herausgeber-URIs können direkt in AD FS geändert werden oder wenn eine Domäne von verwaltet in Verbund konvertiert wird und umgekehrt. Microsoft empfiehlt Kunden, keine Verbunddomäne im Azure AD zu migrierenden Mandanten hinzuzufügen, zu entfernen oder zu konvertieren. Herausgeber-URIs können geändert werden, nachdem die Migration vollständig abgeschlossen wurde.

- Für Netzwerke:

  - Das Erstellen von IPv6-benannten Netzwerken funktioniert nicht im Azure-Portal `http://portal.microsoftazure.de/` . Verwenden Sie das Azure `https://portal.azure.com` -Portal, um Netzwerke mit IPv6-Namen zu erstellen.
 
   - Sie können keine vertrauenswürdigen IP-Adressbereiche für Diensteinstellungen für Azure Multi-Factor Authentication (MFA) aus dem Microsoft Cloud Deutschland-Portal erstellen. Verwenden Sie das Azure AD-Portal für Office 365-Dienste zum Erstellen von vertrauenswürdigen IP-Adressbereichen für Azure MFA.


- Für bedingten Zugriff: 

  - Bedingte Zugriffsrichtlinien mit den folgenden Steuerelementen werden erst nach Abschluss der Migration zu Office 365 Diensten (nach [Abschluss Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) Migrationsphase) unterstützt:

    - Kompatibles Gerät erforderlich
    - Genehmigte App erforderlich
    - App-Schutzrichtlinie erforderlich
    
  - Die Schnittstelle für den bedingten Zugriffsschutz gibt eine falsche Warnung darüber, dass Sicherheitseinstellungen für den Mandanten aktiviert werden, auch wenn er deaktiviert ist, und es gibt bereits Richtlinien für den bedingten Zugriff für den Mandanten. Sie sollten die Warnung ignorieren oder das Office 365-Dienste-Portal zum Verwalten von Richtlinien für bedingten Zugriff verwenden. 

- InTune-Szenarien werden nur für weltweite Endpunkte unterstützt, nachdem die Mandanten Migration abgeschlossen ist, einschließlich aller Migrationen von Office-Arbeitslasten.

- Microsoft Cloud Deutschland Benutzer, die die Mobile App-Benachrichtigungsmethode für MFA-Anforderungen verwenden, sehen die ObjectID (eine GUID) des Benutzers anstelle des Benutzerprinzipalnamens (User Principal Name, UPN) in der Microsoft Authenticator-app. Nachdem die Migration des Azure AD Mandanten abgeschlossen und in Office 365 Diensten gehostet wurde, werden durch die neuen Aktivierungen von Microsoft Authenticator die UPNs der Benutzer angezeigt. Vorhandene Microsoft Authenticator-Konten zeigen weiterhin die Benutzer-ObjectID an, werden aber weiterhin für Mobile App Benachrichtigungen verwendet. 

- Für Mandanten, die nach dem 22. Oktober 2019 erstellt werden, können Sicherheitsstandards für den Mandanten automatisch aktiviert werden, wenn er zum Office 365 Dienst migriert wird. Mandantenadministratoren können festlegen, dass Sicherheitsstandards aktiviert bleiben und für MFA registriert werden, oder Sie können das Feature deaktivieren. Weitere Informationen finden Sie unter [Deaktivierung von Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults). 

  > [!NOTE]
  > Organisationen, die während der Migration nicht automatisch aktiviert werden, werden in Zukunft möglicherweise weiterhin automatisch registriert, da das Feature zum Aktivieren von Sicherheitsstandards im Office 365 Dienst ausgeführt wird. Administratoren, die sich für die explizite Deaktivierung oder Aktivierung von Sicherheitsstandards entscheiden, können dies tun, indem Sie das Feature unter **Azure Active Directory > Eigenschaften** aktualisieren. Nachdem das Feature explizit vom Administrator aktiviert wurde, wird es nicht automatisch aktiviert.

- Es wird eine Warnung bezüglich der Version von Azure AD Connect im Office 365 Deutschland-Portal sowie im Office 365 Portal angezeigt, sobald sich der Mandant in der Migration befindet. Dies kann ignoriert werden, wenn die Warnungs Version nach Abschluss der Migration nicht mehr angezeigt wird. Wenn entweder vor oder nach der Migration eine Warnung in beiden Portalen vorhanden ist, muss Azure AD Connect aktualisiert werden. Die Warnmeldung lautet: "Wir haben festgestellt, dass Sie ein veraltetes Verzeichnissynchronisierungstool verwenden. Es wird empfohlen, dass Sie zum Microsoft Download Center wechseln, um die neueste Version von Azure AD Connect zu erhalten. "

## <a name="exchange-online"></a>Exchange Online 

- `myaccount.msft.com` wird nur nach dem Cutover von Office 365 funktionieren. Links erzeugen bis zu diesem Zeitpunkt Fehlermeldungen "something went wrong".

- Benutzer von Outlook Web App, die auf ein freigegebenes Postfach in der anderen Umgebung zugreifen (beispielsweise greift ein Benutzer in der deutschen Umgebung auf ein freigegebenes Postfach in der globalen Umgebung zu), werden aufgefordert, ein zweites Mal zu authentifizieren. Der Benutzer muss sich zunächst authentifizieren und auf sein Postfach in zugreifen und `outlook.office.de` dann das freigegebene Postfach öffnen, in dem sich befindet `outlook.office365.com` . Sie müssen ein zweites Mal authentifizieren, wenn Sie auf die freigegebenen Ressourcen zugreifen, die im anderen Dienst gehostet werden.

- Wenn ein freigegebenes Postfach Outlook mithilfe von **Datei > Informationen > Konto hinzufügen** hinzugefügt wird, können beim Anzeigen von Kalenderberechtigungen Fehler auftreten, wenn vorhandene Microsoft Cloud Deutschland-Kunden oder diese in den Übergang aufgenommen werden (der Outlook-Client versucht, die Rest-API zu verwenden `https://outlook.office.de/api/v2.0/Me/Calendars` ). Kunden, die ein Konto zum Anzeigen von Kalenderberechtigungen hinzufügen möchten, können den Registrierungsschlüssel wie unter [Benutzeroberflächenänderungen für die Freigabe eines Kalenders in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) beschrieben hinzufügen, um sicherzustellen, dass diese Aktion erfolgreich ausgeführt wird. Dieser Registrierungsschlüssel kann organisationsweit mithilfe von Gruppenrichtlinien bereitgestellt werden.

- Während der Migrationsphase können mit den PowerShell-Cmdlets **New-migrationEndpoint**, **migrationEndpoint** und **Test-MigrationsServerAvailability** Fehler auftreten (Fehler bei Proxy). Dies ist der Fall, wenn das Vermittlungspostfach weltweit migriert wurde, das Administratorpostfach jedoch nicht oder umgekehrt. Um dies zu beheben, verwenden Sie beim Erstellen der PowerShell-Mandanten Sitzung das Vermittlungspostfach als Routinghinweis in der **ConnectionUri**. Beispiel: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Wenn Sie Exchange Online Hybrid verwenden:

    - Sie müssen den Assistenten für die Hybrid Konfiguration (HCW) erneut ausführen, um die lokale Konfiguration für Microsoft Cloud Deutschland vor dem Übergang zu aktualisieren, und führen Sie den HCW bei der Bereinigung für die Office 365 Dienste erneut aus. Wenn Sie benutzerdefinierte Domänen verwenden, sind möglicherweise zusätzliche DNS-Updates erforderlich.

Weitere Informationen zu Aktionen, die während der Migrationsphase dieser Arbeitslast oder zu den Auswirkungen auf die Verwaltung oder Verwendung erforderlich sind, finden Sie im Abschnitt Exchange Online der [Migrationsphasen Aktionen und Auswirkungen](ms-cloud-germany-transition-phases.md#exchange-online).

## <a name="office-services"></a>Office-Dienste

Der zuletzt verwendete (MRU)-Dienst in Office ist ein Cutover aus dem Deutschland-Dienst an Office 365 Diensten, keine Migration. Nur MRU-Links von der Office 365-Dienstseite werden nach der Migration aus dem Office.com-Portal angezeigt. MRU-Links aus dem Deutschland-Dienst sind nicht als MRU-Links in Office 365 Diensten sichtbar. In Office 365 sind MRU-Links nur nach Abschluss der Mandanten Migration verfügbar.

## <a name="sharepoint-online-and-onedrive"></a>SharePoint Online und OneDrive

- Nach Abschluss der SharePoint Online-Migration in die Region Deutschland werden Datenindizes neu erstellt. Features, die von Suchindizes abhängig sind, können beeinträchtigt werden, wenn die Neuindizierung abgeschlossen ist.

- Wenn Ihre Organisation weiterhin SharePoint 2010-Workflows verwendet, funktionieren Sie nach dem 31. Dezember 2021 nicht mehr. SharePoint 2013 Workflows werden weiterhin unterstützt, sind jedoch standardmäßig für neue Mandanten ab dem 1. November 2020 deaktiviert. Nachdem die Migration zum SharePoint Online Dienst abgeschlossen ist, empfehlen wir Ihnen, zu Power Automation oder anderen unterstützten Lösungen zu übergehen.

- Nach Abschluss der OneDrive-Migration in die Region Deutschland werden Daten Indizes neu erstellt. Features, die von Suchindizes abhängen, sind möglicherweise betroffen, während die Neuindizierung ausgeführt wird.


## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Navigieren durch den Übergang:

- [Migrationsphasen-Aktionen und-Auswirkungen](ms-cloud-germany-transition-phases.md)
- [Zusätzliche vorab Arbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Diensten](ms-cloud-germany-transition-add-general.md), [Geräten](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md)und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
