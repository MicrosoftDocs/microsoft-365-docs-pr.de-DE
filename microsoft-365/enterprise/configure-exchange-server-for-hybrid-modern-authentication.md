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
description: Erfahren Sie, wie Sie eine Exchange Server lokal für die Verwendung der modernen Hybridauthentifizierung (Hybrid Modern Authentication, HMA) konfigurieren und Ihnen eine sicherere Benutzerauthentifizierung und Autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 21ffec620ac3e262679fc0e2385f6f0f1b31933b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362258"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Lokale Konfiguration von Exchange Server derart, dass die moderne Hybridauthentifizierung verwendet wird

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die moderne Hybridauthentifizierung (Hybrid Modern Authentication, HMA) ist eine Methode der Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und Autorisierung bietet und für Exchange lokalen Hybridbereitstellungen des Servers verfügbar ist.

## <a name="fyi"></a>Fyi

Bevor wir beginnen, rufe ich Folgendes auf:

- Hybrid Modern Authentication \> HMA

- Exchange lokalen \> EXCH

- \>Exchange Online Exo

Wenn eine Grafik in diesem Artikel über ein Objekt verfügt, *das "abgeblendet" oder "abgeblendet" ist, bedeutet dies, dass das grau dargestellte Element nicht in der HMA-spezifischen Konfiguration enthalten ist.*

## <a name="enabling-hybrid-modern-authentication"></a>Aktivieren der modernen Hybridauthentifizierung

Das Aktivieren von HMA bedeutet:

1. Stellen Sie sicher, dass Sie die Prereqs erfüllen, bevor Sie beginnen.

1. Da viele **Voraussetzungen** sowohl für Skype for Business als auch für Exchange üblich sind, bietet die [moderne Hybridauthentifizierung Übersicht und Voraussetzungen für die Verwendung mit lokalen Skype for Business und Exchange Servern.](hybrid-modern-auth-overview.md) Führen Sie dies aus, bevor Sie mit den Schritten in diesem Artikel beginnen.

1. Hinzufügen von lokalen Webdienst-URLs als **Dienstprinzipalnamen (Service Principal Names, SPNs)** in Azure AD. Wenn SICH EXCH in einer Hybridumgebung mit **mehreren Mandanten** befindet, müssen diese lokalen Webdienst-URLs als SPNs in Azure AD aller Mandanten hinzugefügt werden, die sich in einer Hybridumgebung mit EXCH befinden.

1. Sicherstellen, dass alle virtuellen Verzeichnisse für HMA aktiviert sind

1. Überprüfen auf das EvoSTS Auth Server-Objekt

1. Aktivieren von HMA in EXCH.

> [!NOTE]
> Unterstützt Ihre Version von Office MA? Erfahren [Sie, wie moderne Authentifizierung für Office 2013- und Office 2016-Client-Apps funktioniert.](modern-auth-for-office-2013-and-2016.md)


## <a name="make-sure-you-meet-all-the-prerequisites"></a>Stellen Sie sicher, dass alle Voraussetzungen erfüllt sind.

Da viele Voraussetzungen sowohl für Skype for Business als auch für Exchange gelten, überprüfen Sie [die Übersicht über die moderne Hybridauthentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business und Exchange Servern.](hybrid-modern-auth-overview.md) Führen Sie dies  *aus, bevor*  Sie mit den Schritten in diesem Artikel beginnen.

> [!NOTE]
> Outlook Web App und Exchange Systemsteuerung funktioniert nicht mit moderner Hybridauthentifizierung.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Hinzufügen lokaler Webdienst-URLs als SPNs in Azure AD

Führen Sie die Befehle aus, die Ihre lokalen Webdienst-URLs als Azure AD SPNs zuweisen. SPNs werden während der Authentifizierung und Autorisierung von Clientcomputern und -geräten verwendet. Alle URLs, die für die Verbindung von der lokalen Umgebung mit Azure Active Directory (Azure AD) verwendet werden können, müssen in Azure AD registriert werden (dies umfasst sowohl interne als auch externe Namespaces).

Sammeln Sie zunächst alle URLs, die Sie in AAD hinzufügen müssen. Führen Sie die folgenden Befehle lokal aus:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

Stellen Sie sicher, dass die URLs, mit denen Clients eine Verbindung herstellen können, in AAD als HTTPS-Dienstprinzipalnamen aufgeführt sind. Wenn SICH EXCH in einer Hybridumgebung mit **mehreren Mandanten** befindet, sollten diese HTTPS-SPNs im AAD aller Mandanten in Hybridbereitstellung mit EXCH hinzugefügt werden.

1. Stellen Sie zunächst mit [diesen Anweisungen](connect-to-microsoft-365-powershell.md)eine Verbindung mit AAD her.

    > [!NOTE]
    > Sie müssen die _Option Verbinden-MsolService_ von dieser Seite verwenden, um den folgenden Befehl verwenden zu können.

2. Geben Sie für ihre Exchange-bezogenen URLs den folgenden Befehl ein:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Notieren Sie sich die Ausgabe dieses Befehls (und screenshot für einen späteren Vergleich), der eine https://  *autodiscover.yourdomain.com*  und https://  *mail.yourdomain.com* URL enthalten sollte, aber hauptsächlich aus SPNs besteht, die mit 000000002-0000-0ff1-ce00-000000000000/beginnen. Wenn https:// URLs aus Ihrer lokalen Umgebung fehlen, müssen wir diese spezifischen Datensätze zu dieser Liste hinzufügen.

3. Wenn Ihre internen und externen MAPI/HTTP-, EWS-, ActiveSync-, OAB- und AutoErmittlungseinträge in dieser Liste nicht angezeigt werden, müssen Sie sie mit dem folgenden Befehl hinzufügen (die Beispiel-URLs sind ' `mail.corp.contoso.com` ' und ' `owa.contoso.com` ', aber Sie würden die **Beispiel-URLs durch Ihre eigenen ersetzen):**

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Stellen Sie sicher, dass die neuen Datensätze hinzugefügt wurden, indem Sie den Befehl Get-MsolServicePrincipal aus Schritt 2 erneut ausführen und die Ausgabe durchsuchen. Vergleichen Sie die Liste/den Screenshot von zuvor mit der neuen Liste der SPNs. Sie können auch einen Screenshot der neuen Liste für Ihre Datensätze erstellen. Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt. In unserem Beispiel enthält die Liste der SPNs jetzt die spezifischen URLs  `https://mail.corp.contoso.com`  und  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Überprüfen, ob virtuelle Verzeichnisse ordnungsgemäß konfiguriert sind

Überprüfen Sie nun, ob OAuth in Exchange für alle virtuellen Verzeichnisse ordnungsgemäß aktiviert ist, Outlook möglicherweise verwenden, indem Sie die folgenden Befehle ausführen:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Überprüfen Sie die Ausgabe, um sicherzustellen, dass **OAuth** für jeden dieser VDirs aktiviert ist, es sieht ungefähr wie folgt aus (und das Wichtigste ist "OAuth"):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Wenn OAuth auf einem Server und einem der vier virtuellen Verzeichnisse fehlt, müssen Sie es mit den entsprechenden Befehlen hinzufügen, bevor Sie fortfahren ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)und [Set-AutoDiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Bestätigen, dass das EvoSTS Auth Server-Objekt vorhanden ist

Kehren Sie für diesen letzten Befehl zur lokalen Exchange-Verwaltungsshell zurück. Jetzt können Sie überprüfen, ob Ihre lokale Umgebung über einen Eintrag für den EvoSTS-Authentifizierungsanbieter verfügt:

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

In der Ausgabe sollte ein AuthServer mit dem Namen "EvoSts" und der Status "Enabled" auf "True" festgelegt sein. Wenn dies nicht angezeigt wird, sollten Sie die neueste Version des Hybridkonfigurations-Assistenten herunterladen und ausführen.

> [!NOTE]
> Wenn SICH EXCH in einer Hybridumgebung mit **mehreren Mandanten** befindet, sollte die Ausgabe einen AuthServer des Namens "EvoSts - {GUID}" für jeden Mandanten in einer Hybridumgebung mit EXCH anzeigen, und der Status "Enabled" sollte für alle diese AuthServer-Objekte "True" sein.

 **Wichtig** Wenn Sie Exchange 2010 in Ihrer Umgebung ausführen, wird der EvoSTS-Authentifizierungsanbieter nicht erstellt.

## <a name="enable-hma"></a>Aktivieren von HMA

Führen Sie den folgenden Befehl in der lokalen Exchange Verwaltungsshell aus:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

Wenn die EXCH-Version Exchange 2016 (CU18 oder höher) oder Exchange 2019 (CU7 oder höher) ist und die Hybridbereitstellung mit HCW konfiguriert wurde, die nach September 2020 heruntergeladen wurde, führen Sie den folgenden Befehl in der lokalen Exchange-Verwaltungsshell aus:

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> Wenn SICH EXCH in einer Hybridumgebung mit **mehreren Mandanten** befindet, sind in EXCH mehrere AuthServer-Objekte mit Domänen vorhanden, die jedem Mandanten entsprechen.  Das **IsDefaultAuthorizationEndpoint-Flag** sollte für eines dieser AuthServer-Objekte auf "true" (mithilfe des Cmdlets **"IsDefaultAuthorizationEndpoint")** festgelegt werden. Dieses Flag kann nicht für alle Authserver-Objekte auf "true" festgelegt werden, und HMA wäre auch aktiviert, wenn eines dieser AuthServer-Objekte **isDefaultAuthorizationEndpoint-Flag** auf "true" festgelegt ist.

## <a name="verify"></a>Überprüfen

Sobald Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen Authentifizierungsfluss. Beachten Sie, dass das aktivieren von HMA keine erneute Authentifizierung für einen Client auslöst, und es kann eine Weile dauern, bis Exchange die neuen Einstellungen übernimmt.

Sie sollten auch die STRG-TASTE gedrückt halten, während Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client klicken (auch im Windows Benachrichtigungsschacht), und klicken Sie auf "Verbindungsstatus". Suchen Sie nach der SMTP-Adresse des Clients für den "Authn"-Typ \* "Bearer", der das in OAuth verwendete Bearertoken darstellt.

> [!NOTE]
> Müssen Sie Skype for Business mit HMA konfigurieren? Sie benötigen zwei Artikel: einen, in dem [die unterstützten Topologien](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)aufgeführt sind, und einen Artikel, in dem die [Konfiguration beschrieben](configure-skype-for-business-for-hybrid-modern-authentication.md)wird.


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Verwenden der modernen Hybridauthentifizierung mit Outlook für iOS und Android

Wenn Sie ein lokaler Kunde sind, der Exchange Server unter TCP 443 verwendet, umgehen Sie die Datenverkehrsverarbeitung für die folgenden IP-Adressbereiche:

```text
52.125.128.0/20
52.127.96.0/23
```

Die Outlook-App für iOS und Android ist die beste Möglichkeit, Microsoft 365 oder Office 365 auf Ihrem mobilen Gerät zu erleben, indem sie Microsoft-Dienste verwendet, um Ihren täglichen Leben und Ihre Arbeit zu suchen, zu planen und zu priorisieren. Weitere Informationen finden Sie unter [Verwenden der modernen Hybridauthentifizierung mit Outlook für iOS und Android.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

## <a name="related-topics"></a>Verwandte Themen

[Konfigurationsanforderungen für die moderne Authentifizierung für den Übergang von Office 365 dedizieren/ITAR zu vNext](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
