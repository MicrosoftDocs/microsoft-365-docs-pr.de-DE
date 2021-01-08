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
description: Erfahren Sie, wie Sie eine Exchange Server A0 für die Verwendung der hybriden modernen Authentifizierung (Hybrid Modern Authentication, HMA) konfigurieren und ihnen eine sicherere Benutzerauthentifizierung und Autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780284"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Lokale Konfiguration von Exchange Server derart, dass die moderne Hybridauthentifizierung verwendet wird

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die hybride moderne Authentifizierung (Hybrid Modern Authentication, HMA) ist eine Methode der Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und Autorisierung bietet und für lokale Hybridbereitstellungen von Exchange Server verfügbar ist.

## <a name="fyi"></a>FYI

Bevor wir beginnen, rufe ich auf:

- HMA für moderne \> Hybridauthentifizierung

- Exchange (lokales \> EXCH)

- Exchange Online \> EXO

Wenn eine Grafik in diesem Artikel außerdem über ein Objekt verfügt, das abgeblendet oder abgeblendet ist, bedeutet dies, dass das in Grau dargestellte Element nicht in der *HMA-spezifischen* Konfiguration enthalten ist.

## <a name="enabling-hybrid-modern-authentication"></a>Aktivieren der modernen Hybridauthentifizierung

Das Aktivieren von HMA bedeutet:

1. Stellen Sie sicher, dass Sie die Vorqs erfüllen, bevor Sie beginnen.

1. Da viele **Voraussetzungen** für Skype for Business und Exchange gelten, bietet die moderne Hybridauthentifizierung eine Übersicht und Voraussetzungen für die Verwendung mit lokalen Skype for Business- und [Exchange-Servern.](hybrid-modern-auth-overview.md) Gehen Sie dazu vor, bevor Sie mit den Schritten in diesem Artikel beginnen.

1. Hinzufügen von lokalen Webdienst-URLs als **Dienstprinzipalnamen (SERVICE Principal Names, SPNs)** in Azure AD.

1. Sicherstellen, dass alle virtuellen Verzeichnisse für HMA aktiviert sind

1. Suchen nach dem Objekt "EvoSTS Auth Server"

1. Aktivieren von HMA in EXCH.

 **Hinweis** Unterstützt Ihre Version von Office MA? Erfahren [Sie, wie die moderne Authentifizierung für Office 2013- und Office 2016-Client-Apps funktioniert.](modern-auth-for-office-2013-and-2016.md)

## <a name="make-sure-you-meet-all-the-prerequisites"></a>Stellen Sie sicher, dass alle Voraussetzungen erfüllt sind.

Da viele Voraussetzungen sowohl für Skype for Business als auch für Exchange gelten, lesen Sie die Übersicht über die moderne Hybridauthentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business- und [Exchange-Servern.](hybrid-modern-auth-overview.md) Gehen Sie  *dazu vor,*  bevor Sie mit den Schritten in diesem Artikel beginnen.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Hinzufügen von lokalen Webdienst-URLs als SPNs in Azure AD

Führen Sie die Befehle aus, die Ihre lokalen Webdienst-URLs als Azure AD-SPNs zuweisen. SPNs werden von Clientcomputern und Geräten während der Authentifizierung und Autorisierung verwendet. Alle URLs, die verwendet werden können, um eine Verbindung von einer lokalen mit Azure Active Directory (Azure AD) herzustellen, müssen in Azure AD registriert sein (dies umfasst sowohl interne als auch externe Namespaces).

Erfassen Sie zunächst alle URLs, die Sie in AAD hinzufügen müssen. Führen Sie die folgenden Befehle lokal aus:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

Stellen Sie sicher, dass die URLs, mit der clients eine Verbindung herstellen können, in AAD als NAMEN des HTTPS-Dienstprinzipal aufgeführt werden.

1. Stellen Sie zunächst mit den folgenden Anweisungen eine Verbindung mit AAD [herzustellen.](connect-to-microsoft-365-powershell.md)

   **Hinweis** Sie müssen die Option _"Connect-MsolService"_ auf dieser Seite verwenden, um den folgenden Befehl verwenden zu können.

2. Geben Sie für Ihre Exchange-bezogenen URLs den folgenden Befehl ein:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Notieren Sie sich die Ausgabe dieses Befehls (und screenshot zum späteren Vergleich), der eine https://  *autodiscover.yourdomain.com-*  und https://  *mail.yourdomain.com-URL* enthalten sollte, aber hauptsächlich aus SPNs besteht, die mit 000000002-0000-0ff1-ce00-00000000000 beginnen. Wenn keine https:// aus Ihrer lokalen Website vorhanden sind, müssen wir diese bestimmten Datensätze zu dieser Liste hinzufügen.

3. Wenn Ihre internen und externen MAPI/HTTP-, EWS-, ActiveSync-, OAB- und AutoErmittlungseinträge in dieser Liste nicht angezeigt werden, müssen Sie sie mithilfe des folgenden Befehls hinzufügen (die Beispiel-URLs sind ' und ' ', aber Sie würden die Beispiel-URLs durch Ihre eigenen `mail.corp.contoso.com` `owa.contoso.com` ersetzen): 

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Überprüfen Sie, ob Ihre neuen Datensätze hinzugefügt wurden, indem Sie Get-MsolServicePrincipal aus Schritt 2 erneut ausführen und die Ausgabe überprüfen. Vergleichen Sie die Liste/den Screenshot von vorn mit der neuen Liste der SPNs. Sie können auch einen Screenshot der neuen Liste für Ihre Datensätze erstellen. Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt. In unserem Beispiel enthält die Liste der SPNs jetzt die spezifischen URLs und  `https://mail.corp.contoso.com`  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Überprüfen, ob virtuelle Verzeichnisse ordnungsgemäß konfiguriert sind

Überprüfen Sie nun, ob OAuth in Exchange für alle virtuellen Verzeichnisse, die Outlook möglicherweise verwendet, ordnungsgemäß aktiviert ist, indem Sie die folgenden Befehle ausführen:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Überprüfen Sie die Ausgabe, um sicherzustellen, dass **OAuth** auf jedem dieser VDirs aktiviert ist, es sieht in etwa wie dies aus (und der Schlüssel, den Sie betrachten sollten, ist "OAuth"):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Wenn OAuth auf einem Server und einem der vier virtuellen Verzeichnisse fehlt, müssen Sie es mit den entsprechenden Befehlen hinzufügen, bevor Sie fortfahren ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)und [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Bestätigen, dass das EvoSTS Auth Server -Objekt vorhanden ist

Kehren Sie für diesen letzten Befehl zur lokalen Exchange-Verwaltungsshell zurück. Jetzt können Sie überprüfen, ob Ihre lokale Organisation über einen Eintrag für den evoSTS-Authentifizierungsanbieter verfügt:

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

Ihre Ausgabe sollte einen AuthServer mit dem Namen "EvoSts" anzeigen, und der Status "Enabled" sollte "True" sein. Wenn dies nicht angezeigt wird, sollten Sie die neueste Version des Assistenten für die Hybridkonfiguration herunterladen und ausführen.

 **Wichtig** Wenn Sie Exchange 2010 in Ihrer Umgebung ausführen, wird der EvoSTS-Authentifizierungsanbieter nicht erstellt.

## <a name="enable-hma"></a>Aktivieren von HMA

Führen Sie den folgenden Befehl in der lokalen Exchange-Verwaltungsshell aus:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Überprüfen

Nachdem Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen Authentifizierungsfluss. Beachten Sie, dass durch das Aktivieren von HMA keine erneute Authentifizierung für einen Client ausgelöst wird. Die clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.

Sie sollten auch die STRG-TASTE gedrückt halten, wenn Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client klicken (auch im Schacht "Windows-Benachrichtigungen") und auf "Verbindungsstatus" klicken. Suchen Sie nach der SMTP-Adresse des Clients im Vergleich zum "Authn"-Typ "Bearer", der das in OAuth verwendete \* Bearertoken darstellt.

 **Hinweis** Müssen Sie Skype for Business mit HMA konfigurieren? Sie benötigen zwei Artikel: einen Artikel, in dem unterstützte [Topologien](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)aufgeführt sind, und einen, in dem die Konfiguration [veranschaulicht wird.](configure-skype-for-business-for-hybrid-modern-authentication.md)

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Verwenden der modernen Hybridauthentifizierung mit Outlook für iOS und Android

Wenn Sie ein lokales Kundenkonto sind, das den Exchange Server auf TCP 443 verwendet, umgehen Sie die Datenverkehrsverarbeitung für die folgenden IP-Bereiche:

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>Verwandte Themen

[Konfigurationsanforderungen für moderne Authentifizierung für den Übergang von Office 365 dedicated/ITAR zu vNext](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
