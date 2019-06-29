---
title: Referenz zu konfigurierbaren Einstellungen für Microsoft Managed Desktop
description: Festlegen von Kategorien für konfigurierbare Einstellungen in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: da8f88251f6d1ae3185641dd408b29aa41cd7ea9
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390412"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Referenz zu konfigurierbaren Einstellungen – Microsoft Managed Desktop

In diesem Thema werden die Einstellungskategorien aufgelistet, die Kunden mit Microsoft Managed Desktop konfigurieren können. Jede Einstellungskategorie enthält Informationen zu Anforderungen, bewährten Methoden und zum Anpassen der Einstellungskategorie. 

## <a name="desktop-background-picture"></a>Desktop Hintergrundbild
Sie können das Desktophintergrundbild für Microsoft Managed Desktop-Geräte in Ihrer Organisation anpassen. Sie können dies verwenden, um eine Unternehmensmarke oder ein Marketingmaterial anzuwenden. 

### <a name="requirements"></a>Voraussetzungen

Diese Anforderungen müssen für ein Desktophintergrundbild erfüllt sein:
- Bilddateiformat –. jpg, JPEG oder. png
- Dateispeicherort – Host an einem vertrauenswürdigen sicheren HTTP-Speicherort (HTTPS). 
- Nicht zulässig – http-und Dateifreigabe Speicherorte werden nicht unterstützt. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Anpassen und Bereitstellen von Desktophintergrundbildern

**So fügen Sie ein benutzerdefiniertes Desktophintergrundbild hinzu**
1. Anmelden beim [Microsoft Managed Desktop-Verwaltungsportal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im **konfigurierbaren** Arbeitsbereich **Desktop Hintergrundbild**aus. 
4. Geben Sie den Speicherort des Bilds ein, das Sie verwenden möchten. 
5. Wählen Sie **Stufe Bereitstellung** aus, um die Änderungen zu speichern und in der Test Gruppe bereitzustellen. 

## <a name="browser-start-pages"></a>Browser Startseiten
Browser Startseiten werden auf einzelnen Registerkarten geöffnet, wenn Ihre Benutzer Microsoft Edge starten. Wenn Sie Ihren Benutzern das Öffnen einer Gruppe von Websites erleichtern möchten, die Sie häufig verwenden, fügen Sie für jede Website eine Browser Startseite hinzu. 

### <a name="requirements"></a>Voraussetzungen

Sie müssen den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für Intranet-oder Internet Websites für Ihre Browser Startseiten angeben. Wenn interne Websites konfiguriert sind, können Sie den Benutzern mitteilen, dass der Zugriff auf diese Websites nur zulässig ist, wenn Sie im Büro mit dem internen Netzwerk verbunden sind oder wenn Sie mit einer VPN-Verbindung verbunden sind. 

### <a name="customize-and-deploy-browser-start-pages"></a>Anpassen und Bereitstellen von Browser Startseiten

**So fügen Sie eine Browser Startseite hinzu**
1. Anmelden beim [Microsoft Managed Desktop-Verwaltungsportal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im **konfigurierbaren** Arbeitsbereich **Browser Startseiten**aus. 
4. Wählen Sie **Startseite hinzufügen**aus.
5. Geben Sie auf der **Seite Browser Start hinzufügen**die URL für die Website ein, die Sie verwenden möchten, und wählen Sie dann **Startseite hinzufügen**aus. 
6. Wiederholen Sie die Schritte 1-5 für weitere Browser Startseiten. 
7. Wählen Sie **Stufe Bereitstellung** aus, um die Änderungen zu speichern und in der Test Gruppe bereitzustellen.

## <a name="enterprise-mode-site-list-location"></a>Speicherort der Website Liste für den Unternehmens Modus

Wenn Sie bestimmte Websites und apps haben, von denen Sie wissen, dass Sie Kompatibilitätsprobleme mit Microsoft Edge haben, können Sie die Website Liste für den Unternehmens Modus verwenden, damit die Websites automatisch mit Internet Explorer 11 geöffnet werden. Wenn Sie wissen, dass Ihre Intranet-Websites nicht ordnungsgemäß mit Microsoft Edge funktionieren, können Sie auch festlegen, dass alle Intranet-Websites automatisch mit Internet Explorer 11 geöffnet werden. Die Verwendung des Enterprise-Modus bedeutet, dass Sie Microsoft Edge weiterhin als Standardbrowser verwenden können und gleichzeitig sicherstellen, dass Ihre apps weiterhin an Internet Explorer 11 arbeiten. Weitere Informationen zu Website Listen im Unternehmens Modus finden Sie unter [Enterprise-Modus und Unternehmens Modus-Website Listen](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode). 

Sie können einen https://-Speicherort oder den Speicherort für eine interne Freigabe angeben, in der Sie die Website Liste für den Unternehmens Modus gehostet haben. 

### <a name="requirements"></a>Voraussetzungen

Diese Anforderungen müssen für die Website Listendatei im Enterprise-Modus erfüllt sein:
- Dateiformat – XML-Datei, die [Dateianforderungen](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file) erfüllt
- Dateispeicherort – Hostdatei an einem internen HTTPS-Speicherort. 
- Nicht zulässig – das Hosten auf einer internen Dateifreigabe wie *//ShareName*ist nicht zulässig.

### <a name="best-practices"></a>Bewährte Methoden

Diese bewährten Methoden werden angeboten, um Kunden bei der Entscheidungsfindung bei der Modernisierung ihrer IT-Infrastruktur zu unterstützen:
- **Wählen Sie eine beschränkte Anzahl von Websites** aus – Microsoft Managed Desktop verwendet Microsoft Edge als bevorzugten Browser, um die allgemeine Sicherheit Ihrer Organisation und die Benutzerfreundlichkeit zu verbessern. Die meisten Websites in dieser Liste sind für Legacy-Webanwendungen geeignet, die eine ältere Version eines Browsers benötigen, die nicht so viele Sicherheitsfeatures beinhalten wird. 
- Stellen Sie sich **eine Alternative** vor – stellen Sie sich eine andere Website vor, oder verwenden Sie eine Web-App, die keinen älteren Browser benötigt. Oder aktualisieren Sie die Website, damit Sie neuere Browser verwenden kann. Neuere Browser verwenden die neueste Technologie, um die Sicherheit zu verbessern.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Anpassen und Bereitstellen des Unternehmensstandort Modus-Listen Speicherorts

**So fügen Sie einen Listenspeicherort für den Unternehmensstandort Modus hinzu**

1.  Anmelden beim [Microsoft Managed Desktop-Verwaltungsportal](http://aka.ms/mwaasportal)
2.  Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3.  Wählen Sie im **konfigurierbaren** Arbeitsbereich den **Unternehmens Modus Site List Location**aus. 
4.  Geben Sie den HTTPS-Speicherort für Ihre Website Liste ein. 
5.  Wählen Sie **Stufe Bereitstellung** aus, um die Änderungen zu speichern und in der Test Gruppe bereitzustellen.

## <a name="trusted-sites"></a>Vertrauenswürdige Sites

Vertrauenswürdige Websites ermöglichen das Anpassen von Sicherheitszonen oder die Verwendung einer Website für unterschiedliche Standorte. Zu den Sicherheitszonen gehören: 
- Zone 1 – Zone für lokales Intranet
- Zone 2 – Zone für vertrauenswürdige Sites
- Zone 3 – Internet Zone
- Zone 4 – Zone für eingeschränkte Websites

### <a name="requirements"></a>Voraussetzungen

Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für Intranet-oder Internet Websites für jede vertrauenswürdige Website an. 

### <a name="customize-and-deploy-trusted-sites"></a>Anpassen und Bereitstellen von vertrauenswürdigen Websites

**So fügen Sie eine vertrauenswürdige Website hinzu**

1. Anmelden beim [Microsoft Managed Desktop-Verwaltungsportal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im **konfigurierbaren** Arbeitsbereich **vertrauenswürdige Websites**aus, und wählen Sie **vertrauenswürdige Website hinzufügen**aus. 
4. Geben Sie auf **vertrauenswürdige Website hinzufügen**die URL ein, wählen Sie eine Sicherheitszone aus, und wählen Sie dann **vertrauenswürdige Website hinzufügen**aus. 
5. Wiederholen Sie die Schritte 1-4 für jede vertrauenswürdige Website, die Sie hinzufügen möchten. 
6. Wählen Sie **Stufe Bereitstellung** aus, um die Änderungen zu speichern und in der Test Gruppe bereitzustellen.

**So entfernen Sie eine vertrauenswürdige Website**

1. Anmelden beim [Microsoft Managed Desktop-Verwaltungsportal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im **konfigurierbaren** Arbeitsbereich **vertrauenswürdige Websites**aus. 
4. Wählen Sie die Website aus, die Sie löschen möchten, und wählen Sie dann **Löschen**aus. 
5. Wiederholen Sie die Schritte 1-4 für jede vertrauenswürdige Website, die Sie löschen möchten. 
6. Wählen Sie **Stufe Bereitstellung** aus, um die Änderungen zu speichern und in der Test Gruppe bereitzustellen.

## <a name="proxy"></a>Proxy
Sie können Netzwerkproxyeinstellungen für Ihre Organisation verwalten. Fügen Sie Ihren Proxy Server und die Portnummer hinzu, und fügen Sie dann die Proxy Standort Ausnahmen hinzu. Microsoft Managed Desktop enthält eine Reihe von Standardproxy Ausnahmen, die für den Betrieb des Diensts erforderlich sind. Die standardmäßige Ausschlussliste kann nur vom Microsoft Managed Desktop-Dienst geändert werden.  Weitere Informationen finden Sie unter [Netzwerkkonfiguration für Microsoft Managed Desktop](../get-ready/network.md). 

Die Proxy Site Ausnahmen, die Sie im Microsoft Managed Desktop Portal hinzufügen, werden den Standardproxy Ausnahmen hinzugefügt, die im Microsoft Managed Desktop Service enthalten sind. 

> [!NOTE]
> Das Aktualisieren der standardmäßigen Proxyausnahmeliste wird immer Vorrang vor Kundenbereitstellungen gegeben. Dies bedeutet, dass die Bereitstellung in einer Bereitstellung angehalten wird, wenn es eine Bereitstellung für die standardmäßige Proxyausnahmeliste gibt.  

### <a name="requirements"></a>Voraussetzungen

Diese Anforderungen müssen für Proxy Server-und Proxy Standort Ausnahmen erfüllt sein:
- Es muss sich um eine gültige Serveradresse und Portnummer handeln.
- URLs müssen eine gültige HTTP-Website sein. 

### <a name="customize-and-deploy-proxies"></a>Anpassen und Bereitstellen von Proxys

**So fügen Sie eine einzelne Proxy Standort Ausnahme hinzu**

1. Anmelden beim [Microsoft Managed Desktop-Verwaltungsportal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im **konfigurierbaren** Arbeitsbereich **Proxy**aus. 
4. Geben Sie die **Adresse** und **Port Nummer** für Ihren Proxy Server ein, und wählen Sie dann **Proxyausnahme hinzufügen**aus. 
5. Geben Sie die URL einer gültigen HTTP-Website ein, und wählen Sie dann **Proxyausnahme hinzufügen**aus. 
6. Wiederholen Sie die Schritte 1-5 für jede vertrauenswürdige Website, die Sie hinzufügen möchten. 
7. Wählen Sie **Stufe Bereitstellung** aus, um die Änderungen zu speichern und in der Test Gruppe bereitzustellen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen
- [Übersicht über konfigurierbare Einstellungen](config-setting-overview.md) 
- [Bereitstellen von konfigurierbaren Einstellungen](config-setting-deploy.md)
