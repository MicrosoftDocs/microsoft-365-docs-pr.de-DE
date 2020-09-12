---
title: Lokale Konfiguration von Exchange Server derart, dass die moderne Hybridauthentifizierung verwendet wird
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Sie eine lokale Exchange Server für die Verwendung der Hybriden modernen Authentifizierung (HMA) konfigurieren und Ihnen eine sicherere Benutzerauthentifizierung und-Autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8db74c04335e0846666991d74980648cedb4d9d7
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547130"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Lokale Konfiguration von Exchange Server derart, dass die moderne Hybridauthentifizierung verwendet wird

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Bei der Hybriden modernen Authentifizierung (HMA) handelt es sich um eine Methode zur Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und-Autorisierung bietet und für lokale Exchange Server-hybridbereitstellungen verfügbar ist.

## <a name="fyi"></a>FYI

Bevor wir beginnen, rufe ich Folgendes auf:

- Hybride moderne Authentifizierung \> HMA

- Lokaler Exchange-Austausch \>

- Exchange Online \> Exo

*Wenn eine Grafik in diesem Artikel ein Objekt enthält, das "abgeblendet" oder "abgeblendet" ist, bedeutet das, dass das in Grau dargestellte Element nicht in HMA-spezifischer Konfiguration enthalten ist* .

## <a name="enabling-hybrid-modern-authentication"></a>Aktivieren der modernen Hybrid Authentifizierung

HMA aktivieren bedeutet:

1. Sicherstellen, dass Sie die Voraussetzungen erfüllen, bevor Sie beginnen.

1. Da viele **Voraussetzungen** sowohl für Skype for Business als auch für Exchange, die [hybride moderne Authentifizierungs Übersicht und die Voraussetzungen für die Verwendung mit lokalen Skype for Business-und Exchange-Servern](hybrid-modern-auth-overview.md)gemeinsam sind. Tun Sie dies, bevor Sie einen der Schritte in diesem Artikel beginnen.

1. Hinzufügen von lokalen Webdienst-URLs als **Dienstprinzipalnamen (Service Principal Names, SPNs)** in Azure AD.

1. Sicherstellen, dass alle virtuellen Verzeichnisse für HMA aktiviert sind

1. Überprüfen des EvoSTS-Authentifizierungs Server Objekts

1. Aktivieren von HMA in "interaktives".

 **Hinweis:** Unterstützt Ihre Office-Version MA? Erfahren Sie [, wie die moderne Authentifizierung für Office 2013-und Office 2016-Client-apps funktioniert](modern-auth-for-office-2013-and-2016.md).

## <a name="make-sure-you-meet-all-the-prerequisites"></a>Stellen Sie sicher, dass alle Voraussetzungen erfüllt sind.

Da viele Voraussetzungen sowohl für Skype for Business als auch für Exchange gelten, überprüfen Sie die Übersicht über die [moderne Hybrid Authentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business-und Exchange-Servern](hybrid-modern-auth-overview.md). Tun Sie dies,  *bevor*  Sie einen der Schritte in diesem Artikel beginnen.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Hinzufügen von lokalen Webdienst-URLs als SPNs in Azure AD

Führen Sie die Befehle aus, die ihre lokalen Webdienst-URLs als Azure AD SPNs zuweisen. SPNs werden von Clientcomputern und-Geräten während der Authentifizierung und Autorisierung verwendet. Alle URLs, die möglicherweise zum Herstellen einer Verbindung zwischen lokalen und Azure-Active Directory (Azure AD) verwendet werden, müssen in Azure AD registriert sein (Dies umfasst sowohl interne als auch externe Namespaces).

Sammeln Sie zunächst alle URLs, die Sie in Aad hinzufügen müssen. Führen Sie diese Befehle lokal aus:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

Stellen Sie sicher, dass die URLs, mit denen Clients eine Verbindung herstellen können, als HTTPS-Dienstprinzipalnamen in Aad aufgeführt werden.

1. Stellen Sie zuerst eine Verbindung mit Aad mit [diesen Anweisungen](connect-to-microsoft-365-powershell.md)her.

   **Hinweis:** Sie müssen die Option _Connect-MsolService_ von dieser Seite verwenden, um den folgenden Befehl verwenden zu können.

2. Geben Sie für Ihre Exchange-bezogenen URLs den folgenden Befehl ein:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Notieren Sie sich (und Screenshot für einen späteren Vergleich) die Ausgabe dieses Befehls, die eine https://  *autodiscover.yourdomain.com*  -und https://-  *Mail.yourdomain.com* -URL enthalten sollte, aber meistens aus SPNs besteht, die mit 00000002-0000-0ff1-ce00-000000000000/beginnen. Wenn es https://-URLs von Ihrem Lokal gibt, die fehlen, müssen Sie diese spezifischen Einträge zu dieser Liste hinzufügen.

3. Wenn Ihre internen und externen MAPI/http-, EWS-, ActiveSync-, OAB-und autodiscover-Datensätze in dieser Liste nicht angezeigt werden, müssen Sie Sie mithilfe des folgenden Befehls hinzufügen (die Beispiel-URLs sind " `mail.corp.contoso.com` und" `owa.contoso.com` , aber Sie **ersetzen die Beispiel-URLs durch eigene** ):

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Stellen Sie sicher, dass Ihre neuen Datensätze hinzugefügt wurden, indem Sie den Befehl Get-MsolServicePrincipal aus Schritt 2 erneut ausführen und die Ausgabe durchsuchen. Vergleichen Sie die Liste/Screenshot von vor mit der neuen Liste von SPNs (Sie können auch die neue Liste für Ihre Datensätze Screenshot). Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt. In unserem Beispiel enthält die Liste der SPNs nun die spezifischen URLs  `https://mail.corp.contoso.com`  und  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Überprüfen der ordnungsgemäßen Konfiguration virtueller Verzeichnisse

Überprüfen Sie nun, ob OAuth in Exchange in allen virtuellen Verzeichnissen, die Outlook möglicherweise verwendet, ordnungsgemäß aktiviert ist, indem Sie die folgenden Befehle ausführen:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Überprüfen Sie die Ausgabe, um sicherzustellen, dass **OAuth** auf jedem dieser VDirs aktiviert ist, es sieht in etwa wie folgt aus (und der wichtigste Aspekt ist "OAuth"):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Wenn OAuth auf einem beliebigen Server und einem der vier virtuellen Verzeichnisse fehlt, müssen Sie es mithilfe der entsprechenden Befehle hinzufügen, bevor Sie fortfahren ([festlegen-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [festlegen-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [setOABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)und [AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Bestätigen, dass das EvoSTS-Authentifizierungs Server Objekt vorhanden ist

Kehren Sie zu dem lokalen Exchange-Verwaltungsshell für diesen letzten Befehl zurück. Jetzt können Sie überprüfen, ob Ihr lokal über einen Eintrag für den evoSTS-Authentifizierungsanbieter verfügt:

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

Ihre Ausgabe sollte eine AuthServer des Namens EvoSts und der Status "Enabled" sollte true aufweisen. Wenn dies nicht angezeigt wird, sollten Sie die neueste Version des Assistenten für die Hybrid Konfiguration herunterladen und ausführen.

 **Wichtiger Hinweis** Wenn Sie Exchange 2010 in Ihrer Umgebung durchführen, wird der EvoSTS-Authentifizierungsanbieter nicht erstellt.

## <a name="enable-hma"></a>HMA aktivieren

Führen Sie den folgenden Befehl in der lokalen Exchange-Verwaltungsshell aus:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Überprüfen

Nachdem Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen auth-Fluss. Beachten Sie, dass durch das Aktivieren von HMA keine erneute Authentifizierung für einen beliebigen Client ausgelöst wird. Die Clients authentifizieren sich erneut basierend auf der Lebensdauer der Authentifizierungstoken und/oder certs, die Sie besitzen.

Sie sollten auch die STRG-Taste gleichzeitig gedrückt halten, indem Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client (auch im Windows-Benachrichtigungs Fach) klicken und auf "Verbindungs Status" klicken. Suchen Sie die SMTP-Adresse des Clients anhand eines "authn"-Typs von "Bearer \* ", der das in OAuth verwendete Bearer-Token darstellt.

 **Hinweis:** Sie müssen Skype for Business mit HMA konfigurieren? Sie benötigen zwei Artikel: eine, die [Unterstützte Topologien](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)auflistet, und eine, die zeigt, [wie Sie die Konfiguration durchführen](configure-skype-for-business-for-hybrid-modern-authentication.md).

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Verwenden der modernen Hybridauthentifizierung mit Outlook für iOS und Android

Wenn Sie ein lokaler Kunde sind und Exchange Server auf TCP 443 verwenden, können Sie die folgenden IP-Bereiche in der Whitelist lesen:

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>Verwandte Themen

[Moderne Authentifizierungs Konfigurationsanforderungen für den Übergang von Office 365 dedizierten/ITAR zu vNext](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
