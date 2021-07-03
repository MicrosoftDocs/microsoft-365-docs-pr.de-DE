---
title: Lokale Konfiguration von Skype for Business derart, dass die moderne Hybridauthentifizierung verwendet wird
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie Skype for Business lokal für die Verwendung der modernen Hybridauthentifizierung (Hybrid Modern Authentication, HMA) konfigurieren und Ihnen eine sicherere Benutzerauthentifizierung und Autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9695815d0a085931b10f7f64b9fca2e997af9077
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286057"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Lokale Konfiguration von Skype for Business derart, dass die moderne Hybridauthentifizierung verwendet wird

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Moderne Authentifizierung ist eine Methode der Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und Autorisierung bietet, für Skype for Business lokalen Server und Exchange lokalen Server sowie für hybride hybride Skype for Business geteilte Domänen verfügbar ist.

 **Wichtig** Möchten Sie mehr über die moderne Authentifizierung (MA) erfahren und warum Sie es vielleicht vorziehen, sie in Ihrem Unternehmen oder Ihrer Organisation zu verwenden? In [diesem Dokument](hybrid-modern-auth-overview.md) finden Sie eine Übersicht. Wenn Sie wissen müssen, welche Skype for Business Topologien mit MA unterstützt werden, ist dies hier dokumentiert!

 **Bevor wir beginnen,** verwende ich die folgenden Begriffe:

- Moderne Authentifizierung (MA)

- Moderne Hybridauthentifizierung (Hybrid Modern Authentication, HMA)

- Exchange lokal (EXCH)

- Exchange Online (EXO)

- Skype for Business lokal (SFB)

- Skype for Business Online (SFBO)

Wenn eine Grafik in diesem Artikel ein Ausgegrautes oder abgeblendetes Objekt aufweist, bedeutet dies, dass das grau dargestellte Element nicht in der MA-spezifischen Konfiguration enthalten **ist.**

## <a name="read-the-summary"></a>Zusammenfassung lesen

Diese Zusammenfassung unterteilt den Prozess in Schritte, die andernfalls während der Ausführung verloren gehen könnten, und eignet sich für eine allgemeine Prüfliste, um nachzuverfolgen, wo Sie sich im Prozess befinden.

1. Stellen Sie zunächst sicher, dass alle Voraussetzungen erfüllt sind.

1. Da viele Voraussetzungen sowohl für Skype for Business als auch für Exchange gelten, finden Sie im **Übersichtsartikel** [Ihre Vorabprüfliste.](hybrid-modern-auth-overview.md) Führen Sie dies  *aus, bevor*  Sie mit den Schritten in diesem Artikel beginnen.

1. Sammeln Sie die HMA-spezifischen Informationen, die Sie in einer Datei oder OneNote benötigen.

1. Aktivieren Sie die moderne Authentifizierung für EXO (wenn sie noch nicht aktiviert ist).

1. Aktivieren Sie die moderne Authentifizierung für SFBO (wenn sie noch nicht aktiviert ist).

1. Aktivieren Sie die moderne Hybridauthentifizierung für Exchange lokal.

1. Aktivieren Sie die moderne Hybridauthentifizierung für Skype for Business lokal.

In diesen Schritten wird MA für SFB, SFBO, EXCH und EXO aktiviert, d. h. alle Produkte, die an einer HMA-Konfiguration von SFB und SFBO teilnehmen können (einschließlich Abhängigkeiten von EXCH/EXO). Anders ausgedrückt: Wenn Ihre Benutzer in postfächern verwaltet werden bzw. in einem Teil der Hybridbereitstellung erstellt wurden (EXO + SFBO, EXO + SFB, EXCH + SFBO oder EXCH + SFB), sieht Das Fertigprodukt wie folgt aus:

![In einer gemischten 6-Skype für die HMA-Topologie für Unternehmen ist ma an allen vier möglichen Standorten aktiviert.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

Wie Sie sehen können, gibt es vier verschiedene Stellen zum Aktivieren von MA! Um eine optimale Benutzererfahrung zu erzielen, empfehlen wir, ma an allen vier Speicherorten zu aktivieren. Wenn Sie MA an all diesen Speicherorten nicht aktivieren können, passen Sie die Schritte so an, dass Sie MA nur an den Speicherorten aktivieren, die für Ihre Umgebung erforderlich sind.

Informationen zu unterstützten Topologien finden Sie im [Thema "Supportability" für Skype for Business mit MA.](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)

 **Wichtig** Vergewissern Sie sich, dass alle Voraussetzungen erfüllt sind, bevor Sie beginnen. Sie finden diese Informationen in der Übersicht über die [moderne Hybridauthentifizierung und den voraussetzungen.](hybrid-modern-auth-overview.md)

## <a name="collect-all-hma-specific-info-youll-need"></a>Sammeln aller HMA-spezifischen Informationen, die Sie benötigen

Nachdem Sie überprüft haben, ob sie die Voraussetzungen für die Verwendung der [modernen](hybrid-modern-auth-overview.md) Authentifizierung erfüllen (siehe Hinweis oben), sollten Sie eine Datei erstellen, die die Informationen enthält, die Sie für die Konfiguration von HMA in den nächsten Schritten benötigen. In diesem Artikel verwendete Beispiele:

- **SIP-/SMTP-Domäne**

  - Ex. contoso.com (ist mit Office 365 verbunden)

- **Mandanten-ID**

  - Die GUID, die Ihren Office 365 Mandanten darstellt (bei der Anmeldung von contoso.onmicrosoft.com).

- **SFB 2015 CU5-Webdienst-URLs**

Sie benötigen interne und externe Webdienst-URLs für alle bereitgestellten SfB 2015-Pools. Führen Sie die folgenden Schritte aus Skype for Business Verwaltungsshell aus, um diese abzurufen:

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Ex. Interne: https://lyncwebint01.contoso.com

- Ex. Externen: https://lyncwebext01.contoso.com

Wenn Sie einen Standard Edition Server verwenden, ist die interne URL leer. Verwenden Sie in diesem Fall den Pool-Fqdn für die interne URL.

## <a name="turn-on-modern-authentication-for-exo"></a>Aktivieren der modernen Authentifizierung für EXO

Folgen Sie den Anweisungen hier: [Exchange Online: So aktivieren Sie Ihren Mandanten für die moderne Authentifizierung.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)

## <a name="turn-on-modern-authentication-for-sfbo"></a>Aktivieren der modernen Authentifizierung für SFBO

Folgen Sie den Anweisungen hier: [Skype for Business Online: Aktivieren Ihres Mandanten für die moderne Authentifizierung.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Aktivieren der modernen Hybridauthentifizierung für Exchange lokal

Folgen Sie den Anweisungen hier: So konfigurieren Sie Exchange Server lokal für die Verwendung der [modernen Hybridauthentifizierung.](configure-exchange-server-for-hybrid-modern-authentication.md)

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Aktivieren der modernen Hybridauthentifizierung für Skype for Business lokal

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Hinzufügen lokaler Webdienst-URLs als SPNs in Azure Active Directory

Jetzt müssen Sie Befehle ausführen, um die URLs (die zuvor erfasst wurden) als Dienstprinzipale in SFBO hinzuzufügen.

 **Hinweis** Dienstprinzipalnamen (SPNs) identifizieren Webdienste und ordnen sie einem Sicherheitsprinzipal zu (z. B. einem Kontonamen oder einer Gruppe), damit der Dienst im Namen eines autorisierten Benutzers handeln kann. Clients, die sich bei einem Server authentifizieren, verwenden Informationen, die in SPNs enthalten sind.

1. Stellen Sie zunächst mit diesen Anweisungen eine Verbindung mit Azure Active Directory (Azure AD) [her.](/powershell/azure/active-directory/overview)

2. Führen Sie diesen Befehl lokal aus, um eine Liste der SFB-Webdienst-URLs abzurufen.

   Beachten Sie, dass die AppPrincipalId `00000004` mit . Dies entspricht Skype for Business Online.

   Notieren Sie sich die Ausgabe dieses Befehls (und screenshot für einen späteren Vergleich), der eine SE und eine WS-URL enthält, aber hauptsächlich aus SPNs besteht, die mit `00000004-0000-0ff1-ce00-000000000000/` .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Wenn die internen **oder** externen SFB-URLs aus der lokalen Umgebung fehlen (z. B. https://lyncwebint01.contoso.com müssen wir diese https://lyncwebext01.contoso.com) spezifischen Datensätze zu dieser Liste hinzufügen.

    Ersetzen Sie unbedingt die unten aufgeführten  *Beispiel-URLs* durch Ihre tatsächlichen URLs in den Add-Befehlen!

```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. Stellen Sie sicher, dass die neuen Datensätze hinzugefügt wurden, indem Sie den Befehl **"Get-MsolServicePrincipal"** aus Schritt 2 erneut ausführen und die Ausgabe durchsuchen. Vergleichen Sie die Zuvor-Liste oder den Screenshot mit der neuen Liste der SPNs. Sie können auch die neue Liste für Ihre Datensätze screenshots. Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt. In unserem Beispiel enthält die Liste der SPNs jetzt die spezifischen URLs https://lyncwebint01.contoso.com und https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>Erstellen des EvoSTS Auth Server-Objekts

Führen Sie den folgenden Befehl in der Skype for Business-Verwaltungsshell aus.

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Aktivieren der modernen Hybridauthentifizierung

Dies ist der Schritt, in dem MA tatsächlich aktiviert wird. Alle vorherigen Schritte können vorab ausgeführt werden, ohne den Clientauthentifizierungsfluss zu ändern. Wenn Sie bereit sind, den Authentifizierungsfluss zu ändern, führen Sie diesen Befehl in der Skype for Business Verwaltungsshell aus.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Überprüfen

Sobald Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen Authentifizierungsfluss. Beachten Sie, dass das aktivieren von HMA keine erneute Authentifizierung für einen Client auslöst. Die Clients authentifizieren sich basierend auf der Lebensdauer der Authentifizierungstoken und/oder Zertifikate, über die sie verfügen.

Um zu testen, ob HMA funktioniert, nachdem Sie es aktiviert haben, melden Sie sich von einem SFB-Testclient Windows ab, und klicken Sie auf "Meine Anmeldeinformationen löschen". Melden Sie sich erneut an. Der Client sollte jetzt den Modern Auth-Fluss verwenden, und Ihre Anmeldung enthält jetzt eine **Office 365** Eingabeaufforderung für ein Geschäfts-, Schul- oder Unikonto, die direkt vor dem Kontakt des Clients mit dem Server angezeigt wird und Sie anmeldet.

Sie sollten auch die "Konfigurationsinformationen" für Skype for Business Clients auf "OAuth Authority" überprüfen. Halten Sie dazu auf ihrem Clientcomputer die STRG-TASTE gedrückt, während Sie im Windows Benachrichtigungsschacht mit der rechten Maustaste auf das Skype for Business-Symbol klicken. Klicken Sie im angezeigten Menü auf **"Konfigurationsinformationen".** Suchen Sie im Fenster "Skype for Business Konfigurationsinformationen", das auf dem Desktop angezeigt wird, nach Folgendem:

![Die Konfigurationsinformationen eines Skype for Business-Clients mit moderner Authentifizierung zeigen die URL einer Lync- und EWS-OAUTH-Autorität von https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)

Sie sollten auch die STRG-TASTE gedrückt halten, während Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client klicken (auch im Windows Benachrichtigungsschacht), und klicken Sie auf "Verbindungsstatus". Suchen Sie nach der SMTP-Adresse des Clients für den AuthN-Typ \* "Bearer", der das in OAuth verwendete Bearertoken darstellt.

## <a name="related-articles"></a>Verwandte Artikel

[Link zurück zur Übersicht über die moderne Authentifizierung.](hybrid-modern-auth-overview.md)

Müssen Sie wissen, wie Sie die moderne Authentifizierung (Modern Authentication, ADAL) für Ihre Skype for Business-Clients verwenden? Wir haben [hier](./hybrid-modern-auth-overview.md)Schritte.