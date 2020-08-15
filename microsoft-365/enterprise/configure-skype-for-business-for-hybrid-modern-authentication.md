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
description: In diesem Artikel erfahren Sie, wie Sie Skype for Business lokal für die Verwendung der Hybriden modernen Authentifizierung (HMA) konfigurieren und Ihnen eine sicherere Benutzerauthentifizierung und-Autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695014"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Lokale Konfiguration von Skype for Business derart, dass die moderne Hybridauthentifizierung verwendet wird

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die moderne Authentifizierung ist eine Methode zur Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und-Autorisierung bietet und für Skype for Business lokalen Server und lokale Exchange-Server-und Split-Domain-Skype for Business Hybriden verfügbar ist.
  
 **Wichtiger Hinweis** Möchten Sie mehr über die moderne Authentifizierung (MA) erfahren und warum Sie Sie in Ihrem Unternehmen oder Ihrer Organisation verwenden möchten? In [diesem Dokument](hybrid-modern-auth-overview.md) finden Sie eine Übersicht. Wenn Sie wissen möchten, welche Skype for Business Topologien mit MA unterstützt werden, ist dies hier dokumentiert!
  
 **Bevor wir beginnen**, verwende ich diese Begriffe:
  
- Moderne Authentifizierung (MA)

- Hybride moderne Authentifizierung (HMA)

- Exchange lokal (Kurs)

- Exchange Online (Exo)

- Skype for Business lokal (SFB)

- Skype for Business Online (SFBO)

Wenn eine Grafik in diesem Artikel ein abgeblendetes oder abgeblendetes Objekt enthält, bedeutet dies, dass das in Grau dargestellte Element **nicht** in der MA-spezifischen Konfiguration enthalten ist.
  
## <a name="read-the-summary"></a>Lesen Sie die Zusammenfassung

In dieser Zusammenfassung wird der Prozess in Schritte unterteilt, die andernfalls während der Ausführung verloren gehen können, und eignet sich gut für eine allgemeine Prüfliste, um die Position im Prozess nachzuverfolgen.
  
1. Stellen Sie zunächst sicher, dass alle Voraussetzungen erfüllt sind.

1. Da zahlreiche **Voraussetzungen** sowohl für Skype for Business als auch für Exchange gelten, [Lesen Sie den Übersichtsartikel über die Prüfliste für vorab](hybrid-modern-auth-overview.md)Anforderungen. Tun Sie dies,  *bevor*  Sie einen der Schritte in diesem Artikel beginnen.

1. Sammeln Sie die HMA-spezifischen Informationen, die Sie in einer Datei oder in OneNote benötigen.

1. Aktivieren Sie die moderne Authentifizierung für Exo (sofern Sie noch nicht aktiviert ist).

1. Aktivieren Sie die moderne Authentifizierung für SFBO (sofern Sie noch nicht aktiviert ist).

1. Aktivieren Sie die hybride moderne Authentifizierung für Exchange lokal.

1. Aktivieren Sie die moderne Hybrid Authentifizierung für Skype for Business lokal.

Mit diesen Schritten wird MA für SFB, SFBO, Wechsel und Exo aktiviert, also alle Produkte, die an einer HMA-Konfiguration von SFB und SFBO (einschließlich Abhängigkeiten von Wechsel/Exo) teilnehmen können. In anderen Worten: Wenn Ihre Benutzer in einem beliebigen Teil des Hybrids (Exo + SFBO, Exo + SFB, interSFBO, oder mit dem SFB) erstellt wurden oder Postfächer besitzen, sieht Ihr fertiges Produkt wie folgt aus:
  
![Eine gemischte 6 Skype for Business-HMA-Topologie hat MA an an allen vier möglichen Standorten.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
Wie Sie sehen können, gibt es vier unterschiedliche Orte, an denen MA aktiviert werden kann. Für eine optimale Benutzererfahrung empfehlen wir Ihnen, MA an allen vier Standorten einzuschalten. Wenn Sie den MA nicht an allen diesen Speicherorten aktivieren können, passen Sie die Schritte so an, dass Sie den MA nur an den für Ihre Umgebung erforderlichen Speicherorten aktivieren.
  
Weitere Informationen finden Sie im [Thema zur Unterstützung von Skype for Business mit MA](https://technet.microsoft.com/library/mt803262.aspx) für unterstützte Topologien.
  
 **Wichtiger Hinweis** Stellen Sie sicher, dass alle Voraussetzungen erfüllt sind, bevor Sie beginnen. Diese Informationen finden Sie unter [Übersicht über die moderne Hybrid Authentifizierung und Voraussetzungen](hybrid-modern-auth-overview.md).
  
## <a name="collect-all-hma-specific-info-youll-need"></a>Sammeln Sie alle HMA-spezifischen Informationen, die Sie benötigen.

Nachdem Sie die [Voraussetzungen](hybrid-modern-auth-overview.md) für die Verwendung der modernen Authentifizierung überprüft haben (siehe Hinweis oben), sollten Sie eine Datei erstellen, in der die Informationen gespeichert sind, die Sie für die Konfiguration von HMA in den nächsten Schritten benötigen. In diesem Artikel verwendete Beispiele:
  
- **SIP/SMTP-Domäne**

  - Ex. contoso.com (ist Verbund mit Office 365)

- **Mandanten-ID**

  - Die GUID, die den Office 365-Mandanten darstellt (beim Anmelden von contoso.onmicrosoft.com).

- **SFB 2015 CU5-Webdienst-URLs**

Sie benötigen interne und externe Webdienst-URLs für alle bereitgestellten SFB 2015-Pools. Um diese zu erhalten, führen Sie Folgendes aus Skype for Business-Verwaltungsshell aus:
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Ex. Internen https://lyncwebint01.contoso.com

- Ex. Externen https://lyncwebext01.contoso.com

Wenn Sie ein Standard Edition-Server verwenden, ist die interne URL leer. Verwenden Sie in diesem Fall den Pool-FQDN für die interne URL.
  
## <a name="turn-on-modern-authentication-for-exo"></a>Aktivieren der modernen Authentifizierung für Exo

Befolgen Sie die Anweisungen hier: [Exchange Online: Aktivieren des Mandanten für die moderne Authentifizierung.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)
  
## <a name="turn-on-modern-authentication-for-sfbo"></a>Aktivieren der modernen Authentifizierung für SFBO

Befolgen Sie die Anweisungen hier: [Skype for Business Online: Aktivieren Sie Ihren Mandanten für die moderne Authentifizierung](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Aktivieren der modernen Hybrid Authentifizierung für Exchange lokal

Befolgen Sie die Anweisungen hier: [konfigurieren Exchange Server lokal für die Verwendung der modernen Hybrid Authentifizierung](configure-exchange-server-for-hybrid-modern-authentication.md).
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Aktivieren der modernen Hybrid Authentifizierung für Skype for Business lokal

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Hinzufügen von lokalen Webdienst-URLs als SPNs in Azure Active Directory

Jetzt müssen Sie Befehle ausführen, um die zuvor gesammelten URLs als Dienst Prinzipale in SFBO hinzuzufügen.
  
 **Hinweis:** Dienstprinzipalnamen (Service Principal Names, SPNs) identifizieren Webdienste und ordnen Sie einem Sicherheitsprinzipal zu (beispielsweise einem Kontonamen oder einer Gruppe), damit der Dienst im Auftrag eines autorisierten Benutzers agieren kann. Für Clients, die sich bei einem Server authentifizieren, werden Informationen verwendet, die in SPNs enthalten sind.
  
1. Stellen Sie zuerst mit [diesen Anweisungen](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)eine Verbindung mit Azure Active Directory (Azure AD) her.

2. Führen Sie diesen Befehl lokal aus, um eine Liste der SFB-Webdienst-URLs zu erhalten.

   Beachten Sie, dass die AppPrincipalId mit beginnt `00000004` . Dies entspricht Skype for Business Online.

   Notieren Sie sich (und Screenshot für einen späteren Vergleich) die Ausgabe dieses Befehls, die eine SE-und WS-URL enthalten wird, aber meistens aus SPNs besteht, die mit beginnen `00000004-0000-0ff1-ce00-000000000000/` .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Wenn die internen **oder** externen SFB-URLs von lokal fehlen (beispielsweise, https://lyncwebint01.contoso.com und https://lyncwebext01.contoso.com) wir müssen diese spezifischen Einträge zu dieser Liste hinzufügen.

    Stellen Sie sicher, dass Sie  *die Beispiel-URLs* unten durch ihre tatsächlichen URLs in den Befehlen hinzufügen ersetzen!
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. Stellen Sie sicher, dass Ihre neuen Datensätze hinzugefügt wurden, indem Sie den Befehl **Get-MsolServicePrincipal** aus Schritt 2 erneut ausführen und die Ausgabe durchsuchen. Vergleichen Sie die Liste oder den Screenshot von before mit der neuen Liste mit SPNs. Sie können auch die neue Liste für Ihre Datensätze Screenshot. Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt. In unserem Beispiel enthält die Liste der SPNs nun die spezifischen URLs https://lyncwebint01.contoso.com und https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>Erstellen des EvoSTS-Authentifizierungs Server Objekts

Führen Sie den folgenden Befehl in der Skype for Business-Verwaltungsshell aus.
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Aktivieren der modernen Hybrid Authentifizierung

Dies ist der Schritt, bei dem MA tatsächlich aktiviert wird. Alle vorherigen Schritte können vorzeitig ausgeführt werden, ohne dass der Client Authentifizierungs Fluss geändert wird. Wenn Sie den Authentifizierungs Fluss ändern möchten, führen Sie diesen Befehl in der Skype for Business-Verwaltungsshell aus.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Überprüfen

Nachdem Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen auth-Fluss. Beachten Sie, dass durch das Aktivieren von HMA keine erneute Authentifizierung für einen beliebigen Client ausgelöst wird. Die Clients werden basierend auf der Lebensdauer der Authentifizierungstoken und/oder certs, die Sie besitzen, erneut authentifiziert.
  
Um zu testen, ob HMA funktioniert, nachdem Sie es aktiviert haben, melden Sie sich bei einem Windows-Client für die Test-SFB an, und klicken Sie auf "Meine Anmeldeinformationen löschen". Melden Sie sich erneut an. Der Client sollte jetzt den modernen auth-Fluss verwenden, und Ihre Anmeldung enthält nun eine **Office 365** Eingabeaufforderung für ein "Geschäfts-oder Schulkonto", das Sie direkt sehen, bevor der Client den Server kontaktiert und Sie angemeldet ist.
  
Sie sollten auch die "Konfigurationsinformationen" für Skype for Business Clients für eine "OAuth Authority" überprüfen. Um dies auf dem Clientcomputer zu tun, halten Sie die STRG-Taste gleichzeitig mit der rechten Maustaste auf das Symbol Skype for Business in der Windows-Benachrichtigungsleiste. Klicken Sie im angezeigten Menü auf **Konfigurationsinformationen** . Suchen Sie im Fenster "Skype for Business Konfigurationsinformationen", das auf dem Desktop angezeigt wird, nach folgendem:
  
![Die Konfigurationsinformationen eines Skype for Business Clients mit moderner Authentifizierung zeigen eine lync-und EWS-OAUTH-Autoritäts-URL von an https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
Sie sollten auch die STRG-Taste gleichzeitig gedrückt halten, indem Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client (auch im Windows-Benachrichtigungs Fach) klicken und auf "Verbindungs Status" klicken. Suchen Sie die SMTP-Adresse des Clients anhand eines authn-Typs von "Bearer \* ", der das in OAuth verwendete Bearer-Token darstellt.
  
## <a name="related-articles"></a>Verwandte Artikel

[Link zurück zur modernen Authentifizierung (Übersicht](hybrid-modern-auth-overview.md)).
  
Müssen Sie wissen, wie Sie die moderne Authentifizierung (Adal) für Ihre Skype for Business Clients verwenden können? Wir haben [hier](https://technet.microsoft.com/library/mt710548.aspx)Schritte.
