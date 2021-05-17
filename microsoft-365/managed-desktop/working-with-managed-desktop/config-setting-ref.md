---
title: Konfigurierbare Einstellungsreferenz für Microsoft Managed Desktop
description: Festlegen von Kategorien für konfigurierbare Einstellungen in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917704"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Konfigurierbare Einstellungsreferenz – Microsoft Managed Desktop

In diesem Thema werden die Einstellungskategorien aufgeführt, die Kunden mit Microsoft Managed Desktop konfigurieren können. Jede Einstellungskategorie enthält Informationen zu Anforderungen, bewährten Methoden und zum Anpassen der Einstellungskategorie. 

## <a name="desktop-background-picture"></a>Desktophintergrundbild
Sie können das Desktophintergrundbild für Microsoft Managed Desktop-Geräte in Ihrer Organisation anpassen. Sie können dies verwenden, um eine Unternehmensmarke oder ein Marketingmaterial anzuwenden. 

### <a name="requirements"></a>Anforderungen

Diese Anforderungen müssen für ein Desktophintergrundbild erfüllt sein:
- Bilddateiformat – .jpg, JPEG oder .png
- Dateispeicherort – Hosten an einem vertrauenswürdigen sicheren http(https)-Speicherort. 
- Nicht zulässig – Speicherorte für http- und dateifreigaben (unc) werden nicht unterstützt. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Anpassen und Bereitstellen des Desktophintergrundbilds

**So fügen Sie ein benutzerdefiniertes Desktophintergrundbild hinzu**
1. Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum **Menü Geräte**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen aus.**
3. Wählen **Sie im** Arbeitsbereich Einstellungen die Option **Desktophintergrundbild aus.** 
4. Geben Sie den Speicherort des Bilds ein, das Sie verwenden möchten. 
5. Wählen **Sie Bereitstellungsphase** aus, um Ihre Änderungen zu speichern und in der Testgruppe zu bereitstellen. 

## <a name="browser-start-pages"></a>Browserstartseiten
Browserstartseiten werden in einzelnen Registerkarten geöffnet, wenn Ihre Benutzer Microsoft Edge starten. Wenn Sie es Ihren Benutzern leicht machen möchten, eine Reihe von Websites zu öffnen, die sie häufig verwenden, fügen Sie für jede Website eine Browserstartseite hinzu. 

### <a name="requirements"></a>Anforderungen

Sie müssen den vollqualifizierten Domänennamen (FQDN) für Intranet- oder Internetwebsites für Ihre Browserstartseiten bereitstellen. Wenn interne Websites konfiguriert sind, teilen Sie den Benutzern mit, dass der Zugriff auf diese Websites nur zulässig ist, wenn sie im Büro oder mit einer VPN-Verbindung mit dem internen Netzwerk verbunden sind. 

### <a name="customize-and-deploy-browser-start-pages"></a>Anpassen und Bereitstellen von Browserstartseiten

**So fügen Sie eine Browserstartseite hinzu**
1. Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum **Menü Geräte**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen aus.**
3. Wählen **Sie im** Arbeitsbereich Einstellungen die Option **Browser-Startseiten aus.** 
4. Wählen **Sie Startseite hinzufügen aus.**
5. Geben **Sie auf der Startseite Browser hinzufügen** die URL für die Website ein, die Sie verwenden möchten, und wählen Sie dann Startseite hinzufügen **aus.** 
6. Wiederholen Sie die Schritte 1 bis 5 für zusätzliche Browserstartseiten. 
7. Wählen **Sie Bereitstellungsphase** aus, um Ihre Änderungen zu speichern und in der Testgruppe zu bereitstellen.

## <a name="enterprise-mode-site-list-location"></a>Websitelistenspeicherort im Unternehmensmodus

Wenn Sie bestimmte Websites und Apps haben, von denen Sie wissen, dass sie Kompatibilitätsprobleme mit Microsoft Edge haben, können Sie die Websiteliste für den Unternehmensmodus verwenden, damit die Websites automatisch mit Internet Explorer 11 geöffnet werden. Wenn Sie außerdem wissen, dass Ihre Intranetwebsites nicht ordnungsgemäß mit Microsoft Edge funktionieren, können Sie festlegen, dass alle Intranetwebsites automatisch mit Internet Explorer 11 geöffnet werden. Die Verwendung des Unternehmensmodus bedeutet, dass Sie Microsoft Edge weiterhin als Standardbrowser verwenden und gleichzeitig sicherstellen können, dass Ihre Apps weiterhin in Internet Explorer 11 funktionieren. Weitere Informationen zu Websitelisten für den Unternehmensmodus finden Sie unter [Enterprise Mode and Enterprise Mode Site Lists](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode). 

Sie können einen https:// oder den Speicherort für eine interne Freigabe angeben, in der Sie Ihre Websiteliste für den Unternehmensmodus gehostet haben. 

### <a name="requirements"></a>Anforderungen

Diese Anforderungen müssen für die Websitelistendatei für den Unternehmensmodus erfüllt sein:
- Dateiformat – XML-Datei, die [Dateianforderungen erfüllt](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Dateispeicherort – Hostdatei an einem internen https-Speicherort. 
- Nicht zulässig – Das Hosten auf einer internen Dateifreigabe, wie *etwa "/sharename",* ist nicht zulässig.

### <a name="best-practices"></a>Bewährte Methoden

Diese bewährten Methoden werden angeboten, um Kunden dabei zu unterstützen, Entscheidungen zur Modernisierung ihrer IT-Infrastruktur zu treffen:
- **Wählen Sie eine begrenzte Anzahl** von Websites aus– Microsoft Managed Desktop verwendet Microsoft Edge als bevorzugten Browser, um die allgemeine Sicherheit für Ihre Organisation und die Benutzerfreundlichkeit zu verbessern. Die meisten Websites in dieser Liste sind für Ältere Web-Apps, die eine ältere Version eines Browsers benötigen, die nicht so viele Sicherheitsfeatures enthält. 
- **Überlegen Sie sich eine** alternative – Betrachten Sie eine andere Website oder Web-App, für die kein älterer Browser erforderlich ist. Erwägen Sie auch, die Website so zu aktualisieren, dass sie neuere Browser verwenden kann. Neuere Browser verwenden die neueste Technologie und verbessern die Sicherheit.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Anpassen und Bereitstellen des Speicherorts der Enterprise-Websitemodusliste

**So fügen Sie einen Listenspeicherort für den Unternehmenswebsitemodus hinzu**

1. Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum **Menü Geräte**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen aus.**
3. Wählen **Sie unter** Arbeitsbereich Einstellungen die Option **Websitelistenspeicherort im Unternehmensmodus aus.** 
4. Geben Sie den https-Speicherort für Ihre Websiteliste ein. 
5. Wählen **Sie Bereitstellungsphase** aus, um Ihre Änderungen zu speichern und in der Testgruppe zu bereitstellen.

## <a name="trusted-sites"></a>Vertrauenswürdige Sites

Mit vertrauenswürdigen Websites können Sie Sicherheitszonen oder Standorte, in denen eine Website verwendet werden kann, für verschiedene Websites anpassen. Zu den Sicherheitszonen gehören: 
- Zone 1 – Zone für lokales Intranet
- Zone 2 – Zone mit vertrauenswürdigen Websites
- Zone 3 – Internetzone
- Zone 4 – Zone mit eingeschränkten Websites

### <a name="requirements"></a>Anforderungen

Geben Sie den vollqualifizierten Domänennamen (FQDN) für Intranet- oder Internetwebsites für jede vertrauenswürdige Website an. 

### <a name="customize-and-deploy-trusted-sites"></a>Anpassen und Bereitstellen vertrauenswürdiger Websites

**So fügen Sie eine vertrauenswürdige Website hinzu**

1. Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum **Menü Geräte**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen aus.**
3. Wählen **Sie im** Arbeitsbereich Einstellungen die Option **Vertrauenswürdige Websites** aus, und wählen Sie dann **vertrauenswürdige Website hinzufügen aus.** 
4. Geben **Sie unter** Vertrauenswürdige Website hinzufügen die URL ein, wählen Sie eine Sicherheitszone aus, und wählen Sie dann vertrauenswürdige Website hinzufügen **aus.** 
5. Wiederholen Sie die Schritte 1 bis 4 für jede vertrauenswürdige Website, die Sie hinzufügen möchten. 
6. Wählen **Sie Bereitstellungsphase** aus, um Ihre Änderungen zu speichern und in der Testgruppe zu bereitstellen.

**So entfernen Sie eine vertrauenswürdige Website**

1. Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum **Menü Geräte**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen aus.**
3. Wählen **Sie im** Arbeitsbereich Einstellungen die Option **Vertrauenswürdige Websites aus.** 
4. Wählen Sie die Website aus, die Sie löschen möchten, und wählen Sie dann **Löschen aus.** 
5. Wiederholen Sie die Schritte 1 bis 4 für jede vertrauenswürdige Website, die Sie löschen möchten. 
6. Wählen **Sie Bereitstellungsphase** aus, um Ihre Änderungen zu speichern und in der Testgruppe zu bereitstellen.

## <a name="proxy"></a>Proxy
Sie können Netzwerkproxyeinstellungen für Ihre Organisation verwalten. Fügen Sie Den Proxyserver und die Portnummer hinzu, und fügen Sie dann Die Proxywebsiteausnahmen hinzu. Microsoft Managed Desktop enthält eine Reihe von Standardproxyausnahmen, die für den Betrieb des Diensts erforderlich sind. Die Standardausschlussliste kann nur vom Microsoft Managed Desktop-Dienst geändert werden.  Weitere Informationen finden Sie unter [Netzwerkkonfiguration für Microsoft Managed Desktop](../get-ready/network.md). 

Die Proxywebsiteausnahmen, die Sie im Microsoft Managed Desktop-Portal hinzufügen, werden den standardproxyausnahmen hinzugefügt, die im Microsoft Managed Desktop-Dienst enthalten sind. 

> [!NOTE]
> Das Aktualisieren der Standardproxyausnahmeliste wird immer vor Kundenbereitstellungen priorisiert. Dies bedeutet, dass ihre mehrstufige Bereitstellung angehalten wird, wenn eine Bereitstellung für die Standardproxyausnahmeliste vorhanden ist.  

### <a name="requirements"></a>Anforderungen

Diese Anforderungen müssen für Proxyserver- und Proxystandortausnahmen erfüllt sein:
- Muss eine gültige Serveradresse und Portnummer sein
- URLs müssen eine gültige http-Website sein 

### <a name="customize-and-deploy-proxies"></a>Anpassen und Bereitstellen von Proxys

**So fügen Sie eine einzelne Proxywebsiteausnahme hinzu**

1. Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum **Menü Geräte**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen aus.**
3. Wählen **Sie unter** Arbeitsbereich Einstellungen die Option Proxy **aus.** 
4. Geben Sie **die Adresse** **und Portnummer für** Den Proxyserver ein, und wählen Sie dann **Proxyausnahme hinzufügen aus.** 
5. Geben Sie die URL einer gültigen http-Website ein, und wählen Sie **dann Proxyausnahme hinzufügen aus.** 
6. Wiederholen Sie die Schritte 1 bis 5 für jede vertrauenswürdige Website, die Sie hinzufügen möchten. 
7. Wählen **Sie Bereitstellungsphase** aus, um Ihre Änderungen zu speichern und in der Testgruppe zu bereitstellen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen
- [Übersicht über konfigurierbare Einstellungen](config-setting-overview.md) 
- [Bereitstellen konfigurierbarer Einstellungen](config-setting-deploy.md)