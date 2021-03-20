---
title: Moderne Hybridauthentifizierung, Übersicht und Voraussetzungen für die Verwendung mit lokalen Skype for Business- und Exchange-Servern
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 10/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: ef753b32-7251-4c9e-b442-1a5aec14e58d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: In diesem Artikel erfahren Sie mehr über die moderne Hybridauthentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business- und Exchange-Servern.
ms.openlocfilehash: 33bcf9bde2cda0388160337d3ffe6b81ab94eb12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907528"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>Moderne Hybridauthentifizierung, Übersicht und Voraussetzungen für die Verwendung mit lokalen Skype for Business- und Exchange-Servern

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die _moderne Authentifizierung_ ist eine Methode zur Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und Autorisierung bietet. Sie ist für Office 365 hybride Bereitstellungen von lokalen Skype for Business- und Exchange-Servern sowie für Skype for Business-Hybride mit geteilter Domäne verfügbar. In diesem Artikel finden Sie Links zu verwandten Dokumenten über Voraussetzungen, Einrichtung/Deaktivierung moderner Authentifizierung und zu einigen der zugehörigen Client-Informationen (z. B. Outlook- und Skype-Clients).

- [Was ist moderne Authentifizierung?](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [Was ändert sich, wenn ich die moderne Authentifizierung verwende?](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [Überprüfen Sie den Status der modernen Authentifizierung Ihrer lokalen Umgebung](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [Erfüllen Sie die Voraussetzungen für die moderne Authentifizierung?](#do-you-meet-modern-authentication-prerequisites)
- [Was muss ich noch wissen, bevor ich beginne?](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>Was ist moderne Authentifizierung?
<a name="BKMK_WhatisModAuth"> </a>

Die moderne Authentifizierung ist ein Überbegriff für eine Kombination von Authentifizierungs- und Autorisierungsmethoden zwischen einem Client (z.B. Ihrem Laptop oder Ihrem Smartphone) und einem Server sowie für einige Sicherheitsmaßnahmen, die auf Zugriffsrichtlinien beruhen, mit denen Sie vielleicht bereits vertraut sind. Sie umfasst Folgendes:

- **Authentifizierungsmethoden**: Mehrstufige Authentifizierung (MFA); Smartcardauthentifizierung; clientzertifikatbasierte Authentifizierung
- **Autorisierungsmethoden**: Microsoft-Implementierung von OAuth (Open Authorization)
- **Richtlinien für den bedingten Zugriff**: Mobile Anwendungsverwaltung (MAM) und Azure Active Directory (Azure AD) – Bedingter Zugriff

Die Verwaltung von Benutzeridentitäten mit moderner Authentifizierung gibt Administratoren viele verschiedene Tools an die Hand, wenn es um die Sicherung von Ressourcen geht, und bietet sicherere Methoden der Identitätsverwaltung sowohl für lokale (Exchange und Skype for Business) als auch für Exchange-Hybrid- und Skype for Business Hybrid-Szenarien und Szenarien mit geteilter Domäne.

Seien Sie sich bewusst, dass aufgrund der engen Zusammenarbeit von Skype for Business mit Exchange das Anmeldeverhalten, das Benutzer des Skype for Business-Clients sehen werden, durch den Status der modernen Authentifizierung von Exchange beeinflusst wird. Dies gilt auch, wenn Sie über eine hybride Skype for Business-Architektur mit _geteilter Domäne_ verfügen, in der Sie sowohl Skype for Business Online als auch lokal Skype for Business haben, wobei die Benutzer an beiden Standorten verwaltet werden.

Weitere Informationen zur modernen Authentifizierung in Office 365 finden Sie unter [Office 365 Client App Support - Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).

> [!IMPORTANT]
> Seit August 2017 ist die moderne Authentifizierung (MA) auf allen neuen Office 365-Mandanten, die Skype for Business Online und Exchange Online umfassen, standardmäßig aktiviert. Bereits vorhandene Mandanten haben keine Änderung in Ihrem Standard-MA-Status, aber alle neuen Mandanten unterstützen automatisch den erweiterten Satz von Identitätsfeatures, die oben aufgelistet sind. Um Ihren MA-Status zu überprüfen, lesen Sie den Abschnitt [Überprüfen Sie den Status der modernen Authentifizierung Ihrer lokalen Umgebung](hybrid-modern-auth-overview.md#BKMK_CheckStatus).

## <a name="what-changes-when-i-use-modern-authentication"></a>Was ändert sich, wenn ich die moderne Authentifizierung verwende?
<a name="BKMK_WhatChanges"> </a>

Wenn Sie die moderne Authentifizierung mit lokalen Skype for Business- oder Exchange-Servern verwenden, *authentifizieren* Sie immer noch lokale Benutzer, aber die Vorgehensweise bei der *Autorisierung* ihres Zugriffs auf Ressourcen (wie Dateien oder E-Mails) ändert sich. Aus diesem Grund, obwohl es bei der modernen Authentifizierung um Client- und Serverkommunikation geht, führen die Schritte, die während der Konfiguration von MA unternommen werden, dazu, dass evoSTS (ein von Azure AD verwendeter Sicherheitstokendienst) als Authentifizierungsserver für Skype for Business und lokaler Exchange-Server eingerichtet wird.

Die Umstellung auf evoSTS ermöglicht es Ihren lokalen Servern, die Vorteile von OAuth (Token-Ausgabe) für die Autorisierung Ihrer Clients zu nutzen, und ermöglicht es Ihren lokalen Servern außerdem, in der Cloud übliche Sicherheitsmethoden (wie die mehrstufige Authentifizierung) zu verwenden. Darüber hinaus gibt der evoSTS Token aus, die es Benutzern gestatten, Zugriff auf Ressourcen anzufordern, ohne Ihr Kennwort als Teil der Anforderung anzugeben. Unabhängig davon, wo Ihre Benutzer verwaltet werden (online oder lokal), und unabhängig davon, an welchem Standort sich die benötigte Ressource befindet, wird EvoSTS zum wichtigsten Element der Autorisierung von Benutzern und Clients, sobald die moderne Authentifizierung konfiguriert ist.

Wenn z. B. ein Skype for Business-Client auf den Exchange-Server zugreifen muss, um Kalenderinformationen im Namen eines Benutzers abzurufen, verwendet er dazu die Active Directory-Authentifizierungsbibliothek (ADAL). ADAL ist eine Code-Bibliothek, die dazu dient, gesicherte Ressourcen in Ihrem Verzeichnis unter Verwendung von OAuth-Sicherheitstokens für Clientanwendungen verfügbar zu machen. ADAL arbeitet mit OAuth zusammen, um Ansprüche zu überprüfen und Token (anstelle von Kennwörtern) auszutauschen, um einem Benutzer Zugriff auf eine Ressource zu gewähren. In der Vergangenheit war die Autorität in einer Transaktion wie dieser – der Server, der weiß, wie man Benutzeransprüche validiert und die benötigten Token ausgibt – möglicherweise ein lokaler Sicherheitstokendienst oder sogar Active Directory-Verbunddienste (AD FS). Die moderne Authentifizierung zentralisiert diese Autorität jedoch mithilfe von Azure AD.

Dies bedeutet auch, dass, auch wenn Ihr Exchange-Server und Ihre Skype for Business-Umgebung vollständig lokal sind, der Autorisierungsserver online sein wird und Ihre lokale Umgebung die Möglichkeit haben muss, eine Verbindung zu Ihrem Office 365-Abonnement in der Cloud (und der Azure AD-Instanz, die Ihr Abonnement als Verzeichnis verwendet) zu erstellen und aufrechtzuerhalten.

Was ändert sich nicht? Unabhängig davon, ob Sie sich in einer Hybridumgebung mit geteilter Domäne befinden oder Skype for Business und Exchange Server lokal verwenden, müssen alle Benutzer zuerst *lokal* authentifiziert werden. In einer hybriden Implementierung moderner Authentifizierung weisen _Lyncdiscovery_ und _Autodiscovery_ beide auf Ihren lokalen Server hin.

> [!IMPORTANT]
> Wenn Sie die spezifischen Skype for Business-Topologien wissen möchten, die bei MA unterstützt werden, ist das [hier dokumentiert](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported).

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>Überprüfen Sie den Status der modernen Authentifizierung Ihrer lokalen Umgebung
<a name="BKMK_CheckStatus"> </a>

Da die moderne Authentifizierung den verwendeten Autorisierungsserver ändert, wenn Dienste OAuth/S2S nutzen, müssen Sie wissen, ob die moderne Authentifizierung für Ihre lokalen Skype for Business- und Exchange-Umgebungen aktiviert oder deaktiviert ist. Sie können den Status auf Ihren Exchange-Servern überprüfen, indem Sie den folgenden PowerShell-Befehl ausführen:

```powershell
Get-OrganizationConfig | ft OAuth*
```

Wenn der Wert der Eigenschaft _OAuth2ClientProfileEnabled_ **falsch** ist, ist die moderne Authentifizierung deaktiviert.

Weitere Informationen zum Cmdlet "Get-OrganizationConfig" finden Sie unter [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).

Sie können Ihre Skype for Business-Server überprüfen, indem Sie den folgenden PowerShell-Befehl ausführen:

```powershell
Get-CSOAuthConfiguration
```

Wenn der Befehl eine leere _OAuthServers_-Eigenschaft zurückgibt oder wenn der Wert der Eigenschaft _ClientADALAuthOverride_ nicht **zulässig** ist, wird die moderne Authentifizierung deaktiviert.

Weitere Informationen zum Cmdlet "Get-CsOAuthConfiguration" finden Sie unter [Get-CsOAuthConfiguration](/powershell/module/skype/get-csoauthconfiguration).

## <a name="do-you-meet-modern-authentication-prerequisites"></a>Erfüllen Sie die Voraussetzungen für die moderne Authentifizierung?

Überprüfen Sie diese Punkte und streichen Sie sie von Ihrer Liste, bevor Sie fortfahren:

- **Für Skype for Business**
  - Auf allen Servern muss Mai 2017 Kumulatives Update (CU5) für Skype for Business Server 2015 oder höher vorhanden sein
    - **Ausnahme** – Survivability Branch Appliance (SBA) kann auf der aktuellen Version vorhanden sein (basierend auf Lync 2013)
  - Ihre SIP-Domäne wird als Verbunddomäne in Office 365 hinzugefügt
  - Alle SFB-Frontends müssen über ausgehende Verbindungen zum Internet, über Office 365-Authentifizierungs-URLs (TCP 443) und bekannte Zertifikatstamm-CRLs (TCP 80) verfügen, die in den Zeilen 56 und 125 des Abschnitts "Microsoft 365 Common und Office" von [Office 365-URLs- und -IP-Adressbereiche](urls-and-ip-address-ranges.md) aufgelistet sind.

- **Lokales Skype for Business in einer Office 365-Hybridumgebung**
  - Eine Skype for Business Server 2019-Bereitstellung mit allen Servern, auf denen Skype for Business Server 2019 ausgeführt wird.
  - Eine Skype for Business Server 2015-Bereitstellung mit allen Servern, auf denen Skype for Business Server 2015 ausgeführt wird.
  - Eine Bereitstellung mit maximal zwei unterschiedlichen Serverversionen, wie unten aufgelistet:
    - Skype for Business Server 2015
    - Skype for Business Server 2019
  - Alle Skype for Business-Server müssen über die neuesten kumulativen Updates verfügen. Weitere Informationen finden Sie unter [Skype for Business Server-Updates](/skypeforbusiness/sfb-server-updates), um alle verfügbaren Updates zu finden und zu verwalten.
  - Es gibt kein Lync Server 2010 oder 2013 in der Hybridumgebung.

>[!NOTE]
>Wenn Ihre Skype for Business-Front-End-Server einen Proxyserver für den Internet Zugriff verwenden, müssen die IP-Adresse und die Portnummer des Proxyservers im Konfigurationsabschnitt der Datei "web.config" für jedes Front-End eingegeben werden.

- C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\int\web.config
- C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\ext\web.config

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <proxy
        proxyaddress="https://192.168.100.60:8080"
        bypassonlocal="true" />
    </defaultProxy>
  </system.net>
</configuration>
```

> [!IMPORTANT]
> Achten Sie darauf, dass Sie den RSS-Feed für [URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md) abonnieren, um mit den neuesten Auflistungen der erforderlichen URLs auf dem Laufenden zu bleiben.

- **Für Exchange Server**
  - Sie verwenden entweder Exchange Server 2013 CU19 und höher, Exchange Server 2016 CU8 und höher oder Exchange Server 2019 CU1 und höher.
  - Es gibt kein Exchange Server 2010 in der Umgebung.
  - Die SSL-Abladung ist nicht konfiguriert. Die SSL-Beendigung und die erneute Verschlüsselung wird unterstützt.
  - Für den Fall, dass Ihre Umgebung eine Proxyserver-Infrastruktur einsetzt, damit Server eine Verbindung mit dem Internet herstellen können, stellen Sie sicher, dass alle Exchange-Server über den Proxyserver verfügen, der in der Eigenschaft [InternetWebProxy](/powershell/module/exchange/set-exchangeserver) definiert ist.

- **Lokaler Exchange-Server in einer Office 365-Hybridumgebung**

  - Wenn Sie Exchange Server 2013 verwenden, müssen auf mindestens einem Server die Serverrollen „Postfach“ und „Clientzugriff“ installiert sein. Es ist zwar möglich, die Rollen „Postfach“ und „Clientzugriff“ auf separaten Servern zu installieren, es wird jedoch dringend empfohlen, beide Rollen auf demselben Server zu installieren, um zusätzliche Zuverlässigkeit und verbesserte Leistung bereitzustellen.
  - Wenn Sie Exchange Server 2016 oder eine spätere Version verwenden, muss auf mindestens einem Server die Serverrolle „Postfach“ installiert sein.
  - Es gibt kein Exchange Server 2007 oder 2010 in der Hybridumgebung.
  - Alle Exchange-Server müssen über die neuesten kumulativen Updates verfügen. Weitere Informationen finden Sie unter [Upgrade von Exchange auf die neuesten kumulativen Updates](/exchange/plan-and-deploy/install-cumulative-updates), um alle verfügbaren Updates zu finden und zu verwalten.

- **Exchange-Client- und Protokollanforderungen**

    Die Verfügbarkeit der modernen Authentifizierung wird durch die Kombination aus Client, Protokoll und Konfiguration bestimmt. Wenn die moderne Authentifizierung vom Client, Protokoll und/oder der Konfiguration nicht unterstützt wird, nutzt der Client weiterhin die Legacyauthentifizierung.
  
    Die folgenden Clients und Protokolle unterstützen die moderne Authentifizierung mit lokalem Exchange, wenn die moderne Authentifizierung in der Umgebung aktiviert ist:

  |**Clients**|**Primary-Protokoll**|**Notizen**|
  |:-----|:-----|:-----|
  |Outlook 2013 und höher  <br/> |MAPI über HTTP  <br/> |MAPI über HTTP muss in Exchange aktiviert sein, um die moderne Authentifizierung mit diesen Clients (in der Regel aktiviert oder "wahr" für neue Installationen von Exchange 2013 Service Pack 1 und höher) zu nutzen. Weitere Informationen hierzu finden Sie unter [Funktionsweise der modernen Authentifizierung für Office 2013- und Office 2016-Client-Apps](modern-auth-for-office-2013-and-2016.md).  <br/> Stellen Sie sicher, dass Sie den mindestens erforderlichen Build von Outlook ausführen. Lesen Sie [Neueste Updates für Outlook-Versionen, die Windows Installer (MSI) verwenden](/officeupdates/outlook-updates-msi).  <br/> |
  |Outlook 2016 für Mac und höher  <br/> |Exchange-Webdienste  <br/> |  <br/> |
  |Outlook für iOS und Android  <br/> | Microsoft-Synchronisierungstechnologie <br/> |Weiter Informationen finden Sie unter [Verwenden der modernen Hybridauthentifizierung mit Outlook für iOS und Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).  <br/> |
  |Exchange ActiveSync-Clients (z. B. iOS11 Mail)  <br/> |Exchange ActiveSync  <br/> |Bei Exchange ActiveSync-Clients, die die moderne Authentifizierung unterstützen, müssen Sie das Profil neu erstellen, um von der Standardauthentifizierung zur modernen Authentifizierung zu wechseln.  <br/> |

    Clients und/oder Protokolle, die nicht aufgeführt sind (z. B. POP3), unterstützen die moderne Authentifizierung mit lokalem Exchange nicht und nutzen auch nach der Aktivierung der modernen Authentifizierung in der Umgebung weiterhin Legacyauthentifizierungsmechanismen.

- **Allgemeine Voraussetzungen**
  - Ressourcen gesamtstrukturszenarien erfordern eine zweistufige Vertrauensstellung mit der Konto gesamtstruktur, um sicherzustellen, dass ordnungsgemäße SID-Suchen während moderner Hybridauthentifizierungsanforderungen ausgeführt werden. 
  - Wenn Sie AD FS verwenden, sollten Sie Windows 2012 R2 AD FS 3.0 und höher für Verbund verwenden.
  - Bei den Identitätskonfigurationen handelt es sich um alle Typen, die von Azure AD Connect unterstützt werden, z. B. Kennwort-Hashsynchronisierung, Pass-Through-Authentifizierung und lokale STS, die von Office 365 unterstützt werden.
  - Azure AD Connect ist für die Benutzerreplikation und Synchronisierung konfiguriert und funktionsfähig.
  - Sie haben überprüft, dass "hybrid" mit dem Modus "Klassische Exchange-Hybridtopologie" zwischen der lokalen und der Office 365-Umgebung konfiguriert ist. Offizieller Support-Statement für Exchange Hybrid sagt: Sie müssen entweder den aktuellen CU oder CU-1 haben.
    > [!NOTE]
    > Die moderne Hybridauthentifizierung wird beim [Hybrid-Agent](/exchange/hybrid-deployment/hybrid-agent) nicht unterstützt.

  - Stellen Sie sicher, dass sowohl ein lokal verwalteter Testbenutzer als auch ein Hybrid-Testbenutzer, der in Office 365 verwaltet wird, sich beim Skype for Business-Desktop-Client (wenn Sie die moderne Authentifizierung mit Skype verwenden möchten) und Microsoft Outlook (wenn Sie die moderne Authentifizierung mit Exchange verwenden möchten) anmelden können.

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>Was muss ich noch wissen, bevor ich beginne?
<a name="BKMK_Whatelse"> </a>

- Alle Szenarien für lokale Server umfassen das Einrichten der modernen Authentifizierung lokal (in der Tat bei Skype for Business gibt es eine Liste der unterstützten Topologien), damit sich der Server, der für die Authentifizierung und Autorisierung verantwortlich ist, in der Microsoft Cloud befindet (der Sicherheitstokendienst von Azure AD, "evoSTS" genannt), und das Aktualisieren von Azure AD über die URLs oder Namensräume, die von Ihrer lokalen Installation von Skype for Business oder Exchange verwendet werden. Daher sind die lokalen Server von Microsoft Cloud abhängig. Diese Aktion kann als "Hybridauthentifizierung" konfiguriert werden.
- In diesem Artikel finden Sie Links zu anderen Artikeln, die Sie bei der Auswahl unterstützter moderner Authentifizierungstopologien (nur für Skype for Business erforderlich) unterstützen, sowie Anleitungsartikel, die die Einrichtungsschritte bzw. die Schritte zur Deaktivierung der modernen Authentifizierung für lokales Exchange und lokales Skype for Business erläutern. Markieren Sie diese Seite als Favoritenseite in Ihrem Browser, wenn Sie einen Startpunkt für die Verwendung moderner Authentifizierung in Ihrer Serverumgebung benötigen.

## <a name="related-topics"></a>Verwandte Themen
<a name="BKMK_URLListforMA"> </a>

- [Lokale Konfiguration von Exchange Server derart, dass die moderne Authentifizierung verwendet wird](configure-exchange-server-for-hybrid-modern-authentication.md)
- [Unterstützte Skype for Business-Topologien mit moderner Authentifizierung](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
- [Lokale Konfiguration von Skype for Business derart, dass die moderne Authentifizierung verwendet wird](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [Entfernen oder Deaktivieren der modernen Hybridauthentifizierung aus Skype for Business und Exchange](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)