---
title: Referenz zu konfigurierbaren Einstellungen für Microsoft Managed Desktop
description: Festlegen von Kategorien für konfigurierbare Einstellungen in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 1f0301f8660fd7ff60bd347d0d7b88c629d79453
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051096"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Referenz zu konfigurierbaren Einstellungen – Microsoft Managed Desktop

In diesem Thema werden die Einstellungskategorien aufgelistet, die Kunden mit Microsoft Managed Desktop konfigurieren können. Jede Einstellungskategorie enthält Informationen zu Anforderungen, bewährten Methoden und zum Anpassen der Einstellungskategorie. 

## <a name="desktop-background-picture"></a>Hintergrundbild des Desktops
Sie können das Desktophintergrundbild für Microsoft Managed Desktop-Geräte in Ihrer Organisation anpassen. Sie können dies verwenden, um eine Unternehmensmarke oder ein Marketing anzuwenden. 

### <a name="requirements"></a>Anforderungen

Diese Anforderungen müssen für ein Desktophintergrundbild erfüllt sein:
- Bilddateiformat-. jpg, JPEG oder. png
- Dateispeicherort-Host auf einem vertrauenswürdigen HTTPS-Speicherort (Secure HTTP). 
- Nicht zulässig – http-und Dateifreigabe Adressen (UNC) werden nicht unterstützt. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Anpassen und Bereitstellen des Desktop Hintergrundbilds

**So fügen Sie ein benutzerdefiniertes Desktophintergrundbild hinzu**
1. Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im **konfigurierbaren** Arbeitsbereich **Desktop Hintergrundbild**aus. 
4. Geben Sie den Speicherort des Bilds ein, das Sie verwenden möchten. 
5. Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen. 

## <a name="browser-start-pages"></a>Browser-Startseiten
Browser Startseiten werden in einzelnen Registerkarten geöffnet, wenn Ihre Benutzer Microsoft Edge starten. Wenn Sie Ihren Benutzern das Öffnen einer Reihe von Websites erleichtern möchten, die häufig verwendet werden, fügen Sie eine Browser-Startseite für jede Website hinzu. 

### <a name="requirements"></a>Anforderungen

Sie müssen den vollqualifizierten Domänennamen (FQDN) für Intranet-oder Internet Websites für die Startseiten des Browsers angeben. Wenn interne Websites konfiguriert sind, können Sie den Benutzern mitteilen, dass der Zugriff auf diese Websites nur zulässig ist, wenn Sie im Büro oder mit einer VPN-Verbindung mit dem internen Netzwerk verbunden sind. 

### <a name="customize-and-deploy-browser-start-pages"></a>Anpassen und Bereitstellen von Browser Startseiten

**So fügen Sie eine Browser-Startseite hinzu**
1. Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im **konfigurierbaren** Arbeitsbereich **Browser Startseiten**aus. 
4. Wählen Sie **Startseite hinzufügen**aus.
5. Geben Sie auf der **Seite Browser Start hinzufügen**die URL für die Website ein, die Sie verwenden möchten, und wählen Sie dann **Startseite hinzufügen**aus. 
6. Wiederholen Sie die Schritte 1-5 für zusätzliche Browser Startseiten. 
7. Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.

## <a name="enterprise-mode-site-list-location"></a>Speicherort der Website Liste für den Unternehmens Modus

Wenn Sie bestimmte Websites und apps haben, von denen Sie wissen, dass Sie Kompatibilitätsprobleme mit Microsoft Edge haben, können Sie die Website Liste für den Unternehmens Modus verwenden, damit die Websites automatisch mit Internet Explorer 11 geöffnet werden. Wenn Sie wissen, dass Ihre Intranet-Websites mit Microsoft Edge nicht ordnungsgemäß funktionieren, können Sie auch festlegen, dass alle Intranet-Websites mit Internet Explorer 11 automatisch geöffnet werden. Wenn Sie den Enterprise-Modus verwenden, können Sie Microsoft Edge weiterhin als Standardbrowser verwenden und gleichzeitig sicherstellen, dass Ihre apps weiterhin mit Internet Explorer 11 arbeiten. Weitere Informationen zu Website Listen im Unternehmens Modus finden Sie unter [Enterprise Mode and Enterprise Mode Site lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode). 

Sie können einen https://-Standort oder den Speicherort für eine interne Freigabe angeben, auf der Sie Ihre Unternehmens Modus-Website Liste gehostet haben. 

### <a name="requirements"></a>Anforderungen

Diese Anforderungen müssen für die Unternehmens Modus-Website Listendatei erfüllt sein:
- Dateiformat-XML-Datei, die [Dateianforderungen](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file) erfüllt
- Dateispeicherort-Host Datei an einem internen HTTPS-Speicherort. 
- Nicht zulässig – das Hosten auf einer internen Dateifreigabe, wie *//ShareName*, ist nicht zulässig

### <a name="best-practices"></a>Bewährte Methoden

Diese bewährten Methoden helfen Kunden bei der Entscheidungsfindung bei der Modernisierung ihrer IT-Infrastruktur:
- **Wählen Sie eine begrenzte Anzahl von Websites** – Microsoft Managed Desktop verwendet Microsoft Edge als bevorzugten Browser, um die allgemeine Sicherheit für Ihre Organisation zu verbessern und die Benutzerfreundlichkeit zu erhöhen. Die meisten Websites in dieser Liste gelten für Legacy-Web-Apps, die eine ältere Version eines Browsers benötigen, die nicht so viele Sicherheitsfunktionen enthält. 
- **Betrachten Sie eine Alternative** – erwägen Sie einen anderen Standort oder eine Web-App, für die kein älterer Browser erforderlich ist. Sie sollten auch die Website aktualisieren, damit Sie neuere Browser verwenden kann. Neuere Browser verwenden die neueste Technologie und helfen bei der Verbesserung der Sicherheit.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Anpassen und Bereitstellen des Speicherorts für den Unternehmenswebsite Modus

**So fügen Sie einen Speicherort für die Unternehmenswebsite Modus-Liste hinzu**

1.  Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)
2.  Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3.  Wählen Sie unter **konfigurierbarer** Arbeitsbereich den Standort **Listenspeicherort des Unternehmens Modus**aus. 
4.  Geben Sie den HTTPS-Speicherort für Ihre Website Liste ein. 
5.  Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.

## <a name="trusted-sites"></a>Vertrauenswürdige Websites

Vertrauenswürdige Websites ermöglichen Ihnen das Anpassen von Sicherheitszonen oder die Verwendung einer Website für verschiedene Websites. Zu den Sicherheitszonen gehört Folgendes: 
- Zone 1 – Zone für lokales Intranet
- Zone 2 – Zone für vertrauenswürdige Sites
- Zone 3 – Internet Zone
- Zone 4 – Zone mit eingeschränkten Websites

### <a name="requirements"></a>Anforderungen

Geben Sie den vollqualifizierten Domänennamen (FQDN) für Intranet-oder Internet Websites für jede vertrauenswürdige Website an. 

### <a name="customize-and-deploy-trusted-sites"></a>Anpassen und Bereitstellen vertrauenswürdiger Websites

**So fügen Sie eine vertrauenswürdige Website hinzu**

1. Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie in **konfigurierbarer** Arbeitsbereich **Vertrauenswürdige Sites**aus, und wählen Sie dann **vertrauenswürdige Website hinzufügen** 
4. Geben Sie auf **vertrauenswürdige Website hinzufügen**die URL ein, wählen Sie eine Sicherheitszone aus, und wählen Sie dann **vertrauenswürdige Website hinzufügen**aus. 
5. Wiederholen Sie die Schritte 1-4 für jede vertrauenswürdige Website, die Sie hinzufügen möchten. 
6. Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.

**So entfernen Sie eine vertrauenswürdige Website**

1. Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie in **konfigurierbarer** Arbeitsbereich **Vertrauenswürdige Sites**aus. 
4. Wählen Sie die Website aus, die Sie löschen möchten, und wählen Sie dann **Löschen**aus. 
5. Wiederholen Sie die Schritte 1-4 für jede vertrauenswürdige Website, die Sie löschen möchten. 
6. Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.

## <a name="proxy"></a>Proxy
Sie können Netzwerkproxyeinstellungen für Ihre Organisation verwalten. Fügen Sie Ihren Proxy Server und die Nummer der Portierung hinzu, und fügen Sie dann die Proxy Website-Ausnahmen hinzu. Microsoft Managed Desktop enthält eine Reihe von Standardproxy Ausnahmen, die für den Betrieb des Diensts erforderlich sind. Die standardmäßige Ausschlussliste kann nur vom Microsoft Managed Desktop-Dienst geändert werden.  Weitere Informationen finden Sie unter [Netzwerkkonfiguration für Microsoft Managed Desktop](../get-ready/network.md). 

Die Proxy Website-Ausnahmen, die Sie im Microsoft Managed Desktop-Portal hinzufügen, werden den Standardproxy Ausnahmen hinzugefügt, die in Microsoft Managed Desktop Service enthalten sind. 

> [!NOTE]
> Das Aktualisieren der standardmäßigen Proxyausnahmeliste wird immer Vorrang vor Kundenbereitstellungen haben. Dies bedeutet, dass die Bereitstellung von Staging angehalten wird, wenn eine Bereitstellung für die Standardproxy Ausnahmeliste vorhanden ist.  

### <a name="requirements"></a>Anforderungen

Diese Anforderungen müssen für Ausnahmen von Proxyservern und Proxy Websites erfüllt sein:
- Muss eine gültige Serveradresse und-Nummer sein.
- URLs müssen eine gültige HTTP-Website sein. 

### <a name="customize-and-deploy-proxies"></a>Anpassen und Bereitstellen von Proxys

**So fügen Sie eine einzelne Proxy Standort Ausnahme hinzu**

1. Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie in **konfigurierbarer** Arbeitsbereich **Proxy**aus. 
4. Geben Sie die **Adresse** und die **Nummer** für den Proxy Server ein, und wählen Sie **Proxyausnahme hinzufügen**aus. 
5. Geben Sie die URL einer gültigen HTTP-Website ein, und wählen Sie **Proxyausnahme hinzufügen**aus. 
6. Wiederholen Sie die Schritte 1-5 für jede vertrauenswürdige Website, die Sie hinzufügen möchten. 
7. Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen
- [Übersicht über konfigurierbare Einstellungen](config-setting-overview.md) 
- [Bereitstellen von konfigurierbaren Einstellungen](config-setting-deploy.md)