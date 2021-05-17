---
title: Netzwerkanforderungen in Office für Mac
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: In diesem Artikel wird beschrieben, welche Endpunkte und URLs Office für Mac Anwendungen zu erreichen versuchen, und die bereitgestellten Dienste.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690601"
---
# <a name="network-requests-in-office-for-mac"></a>Netzwerkanforderungen in Office für Mac

Office für Mac anwendungen bieten eine systemeigene App-Erfahrung auf der macOS-Plattform. Jede App ist so konzipiert, dass sie in einer Vielzahl von Szenarien funktioniert, einschließlich Zustände, in denen kein Netzwerkzugriff verfügbar ist. Wenn ein Computer mit einem Netzwerk verbunden ist, stellen die Anwendungen automatisch eine Verbindung mit einer Reihe webbasierter Dienste bereit, um erweiterte Funktionen bereitzustellen. In den folgenden Informationen wird beschrieben, welche Endpunkte und URLs die Anwendungen zu erreichen versuchen, und die bereitgestellten Dienste. Diese Informationen sind hilfreich, wenn Sie Netzwerkkonfigurationsprobleme beheben und Richtlinien für Netzwerkproxyserver festlegen. Die Details in diesem Artikel sollen den Artikel [Office 365 URL](urls-and-ip-address-ranges.md)und Adressbereiche ergänzen, der Endpunkte für Computer enthält, auf denen Microsoft Windows. Sofern nicht erwähnt, gelten die Informationen in diesem Artikel auch für Office 2019 für Mac und Office 2016 für Mac, die als einmaler Einkauf in einem Einzelhandelsgeschäft oder über einen Volumenlizenzvertrag verfügbar sind. 

  
Der Großteil dieses Artikels enthält Tabellen, in der netzwerk-URLs, Typ und Beschreibung des Diensts oder Features beschrieben werden, die von diesem Endpunkt bereitgestellt werden. Jede der Office kann sich in ihrer Dienst- und Endpunktverwendung unterscheiden. Die folgenden Apps sind in den folgenden Tabellen definiert:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
Der URL-Typ ist wie folgt definiert:
  
- ST: Static – Die URL ist hart in die Clientanwendung codiert.
    
- SS: Semi-Static - Die URL wird als Teil einer Webseite oder eines Redirectors codiert.
    
- CS: Config Service – Die URL wird als Teil des konfigurationsdiensts Office zurückgegeben.

    
## <a name="office-for-mac-default-configuration"></a>Office für Mac Standardkonfiguration

 **Installation und Updates**
  
Die folgenden Netzwerkendpunkte werden verwendet, um das installationsprogramm Office für Mac aus dem Microsoft Content Delivery Network (CDN) herunterzuladen.
  
|**URL**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365 Installationsportal-Weiterleitungslinkdienst an die neuesten Installationspakete.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Speicherort der Installationspakete auf der Content Delivery Network.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Speicherort der Installationspakete auf der Content Delivery Network.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Verwaltungssteuerungsendpunkt für Microsoft AutoUpdate  <br/> |
   
 **Erster Start der App**
  
Die folgenden Netzwerkendpunkte werden beim ersten Start eines Office-App. Diese Endpunkte bieten Office funktionen für Benutzer, und die URLs werden unabhängig vom Lizenztyp (einschließlich Volumenlizenzinstallationen) kontaktiert.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |"Flighting"-Konfiguration – ermöglicht das Auflichten und Experimentieren von Features.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |"Flighting"-Netzwerkkonfigurationstest  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |"Flighting"-Netzwerkkonfigurationstest  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Configuration Service – Masterliste der Dienstendpunkte.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Herunterladen der Telemetrieregeln – Informiert den Client darüber, welche Daten und Ereignisse in den Telemetriedienst hochgeladen werden sollen.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |OneNote Telemetriedienst  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Telemetrie Hochladen Berichterstellung – "Heartbeart" und Fehlerereignisse, die auf dem Client auftreten, werden in den Telemetriedienst hochgeladen.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office Vorlagendienst – Stellt Benutzern Onlinedokumentvorlagen zur Verfügung.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Office VorlagenDownloads – Storage von PNG-Vorlagenbildern.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Store konfiguration für Office Apps.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office Document Integration Services Catalog (Liste der Dienste und Endpunkte) und Home Realm Discovery.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Ressourcen für Home Realm Discovery v2 (15.40 und höher)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft AutoUpdate Manifests – überprüft, ob Updates verfügbar sind  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Microsoft Ajax-JavaScript-Bibliothek  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-App für Office und Ressourcen.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Ordnen Sie die App für Office und Ressourcen zu.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Personen Graph App für Office Konfiguration und Ressourcen.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |ST  <br/> |Neue Inhalte für OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |ST  <br/> |Neuer Inhalt für OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |Neue Bilder für OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |In-App-Supportdienst.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |E-Mail-Kontoerkennungsdienst.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook AutoDiscovery  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook Endpunkt für Microsoft 365 Dienst.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |Symbole für Outlook-Add-Ins.  <br/> |
   
> [!NOTE]
> Der Office Configuration Service fungiert als automatischer Ermittlungsdienst für alle Microsoft Office Clients, nicht nur für Mac. Die in der Antwort zurückgegebenen Endpunkte sind semistatisch, da die Änderung sehr selten, aber dennoch möglich ist. 
  
 **Anmeldung**
  
Die folgenden Netzwerkendpunkte werden bei der Anmeldung beim cloudbasierten Speicher kontaktiert. Je nach Kontotyp können unterschiedliche Dienste kontaktiert werden. Beispiel:
  
- **MSA: Microsoft-Konto** – in der Regel für Verbraucher- und Einzelhandelsszenarien verwendet 
    
- **OrgID: Organisationskonto** – in der Regel für kommerzielle Szenarien verwendet 
    
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Windows Autorisierungsdienst  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 365 Anmeldedienst (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft Account Login Service (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Microsoft Account Login Service Helper (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365 Anmeldebranding (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Dokument- und Storage-Locator  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Zuletzt verwendeter (MRU)-Dokumentdienst  <br/> |
   
> [!NOTE]
> Bei Abonnement- und Einzelhandelslizenzen aktiviert die Anmeldung sowohl das Produkt als auch den Zugriff auf Cloudressourcen wie OneDrive. Bei Volumenlizenzinstallationen werden Benutzer weiterhin zur Anmeldung aufgefordert (standardmäßig), dies ist jedoch nur für den Zugriff auf Cloudressourcen erforderlich, da das Produkt bereits aktiviert ist. 
  
 **Produktaktivierung**
  
Die folgenden Netzwerkendpunkte gelten für Microsoft 365 Abonnement- und Einzelhandelslizenzaktivierungen. Dies gilt insbesondere NICHT für Volumenlizenzinstallationen.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Office-Lizenzierungsdienst  <br/> |
   
 **Neue Inhalte**
  
Die folgenden Netzwerkendpunkte gelten nur für Microsoft 365 Abonnement.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |Inhalt der neuen JSON-Seite.  <br/> |
   
 **Recherche**
  
Die folgenden Netzwerkendpunkte gelten nur für Microsoft 365 Abonnement.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Researcher Web Service  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Statischer Inhalt des Forschers  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |Researcher Content Provider  <br/> |
   
 **Intelligentes Nachschlagen**
  
Die folgenden Netzwerkendpunkte gelten sowohl für Microsoft 365 abonnement- als auch für Einzelhandels-/Volumenlizenzaktivierungen.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Insights-Webdienst  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |JQuery Library  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Unterstützen der JavaScript-Bibliothek  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Insights-Inhaltsanbieter  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Insights-Inhaltsanbieter  <br/> |
   
 **PowerPoint-Designer**
  
Die folgenden Netzwerkendpunkte gelten nur für Microsoft 365 Abonnement.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint-Designer Webdienst  <br/> |
   
 **PowerPoint-Schnellstarter**
  
Die folgenden Netzwerkendpunkte gelten nur für Microsoft 365 Abonnement.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint Schnellstarterwebdienst  <br/> |
   
 **Senden eines Schmunzelns/Stirnrunzelns**
  
Die folgenden Netzwerkendpunkte gelten sowohl für Microsoft 365 abonnement- als auch für Einzelhandels-/Volumenlizenzaktivierungen.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Senden eines Smile-Diensts  <br/> |
   
 **Wenden Sie sich an den Support**
  
Die folgenden Netzwerkendpunkte gelten sowohl für Microsoft 365 abonnement- als auch für Einzelhandels-/Volumenlizenzaktivierungen.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Kontaktieren des Supportdiensts  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |In-App-Supportdienst  <br/> |
   
 **Speichern als PDF**
  
Die folgenden Netzwerkendpunkte gelten sowohl für Microsoft 365 abonnement- als auch für Einzelhandels-/Volumenlizenzaktivierungen.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Word-Dokumentkonvertierungsdienst (PDF)  <br/> |
   
 **Office Apps (auch als Add-Ins bekannt)**
  
Die folgenden Netzwerkendpunkte gelten für Microsoft 365 Abonnement- und Einzelhandels-/Volumenlizenzaktivierungen, wenn Office App-Add-Ins vertrauenswürdig sind.
  
|**URL**|**Apps**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Office-App Storekonfiguration  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-App-Ressourcen  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Zuordnung von App-Ressourcen  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |Personen Graph-App-Ressourcen  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office Umleitungsdienst  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Office JavaScript-Bibliotheken  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Telemetrie- und Berichtsdienst für Office Apps  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Microsoft Ajax-JavaScript-Bibliothek  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Microsoft Ajax-JavaScript-Bibliothek  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Office JavaScript-Bibliotheken  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Supportressourcen  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Supportressourcen  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |Supportressourcen  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |JavaScript-Bibliothek  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |Fehlerberichterstattung  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |Schriftartenressourcen  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |Telemetriedienst  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Telemetriebericht  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Store Objektbibliothek  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Ressourcen für Wikipedia-Seiten  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-Medienressourcen  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-Sandkastenframe  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |Zuordnungsvorlagen  <br/> |
   
 **Sichere Links**
  
Der folgende Netzwerkendpunkt gilt nur für alle Office für Microsoft 365 Abonnement.
  
|**URL**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Microsoft Safe Link Service  <br/> |
   
 **Absturzbericht**
  
Der folgende Netzwerkendpunkt gilt für alle Office für abonnement- und Microsoft 365-/Volumenlizenzaktivierungen. Wenn ein Prozess unerwartet abstürzt, wird ein Bericht generiert und an den Watson-Dienst gesendet.
  
|**URL**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Microsoft Error Reporting Service  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Office Collaborative Insights Service  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Optionen zur Reduzierung von Netzwerkanforderungen und Datenverkehr

Die Standardkonfiguration von Office für Mac bietet die beste Benutzererfahrung, sowohl was die Funktionalität als auch den Computer auf dem neuesten Stand hält. In einigen Szenarien möchten Sie möglicherweise verhindern, dass Anwendungen Netzwerkendpunkte kontaktieren. In diesem Abschnitt werden die Optionen hierin erläutert.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Deaktivieren von CloudSign-In und Office Add-Ins
  
Volumenlizenzkunden haben möglicherweise strenge Richtlinien zum Speichern von Dokumenten in cloudbasiertem Speicher. Die folgende Anwendungseinstellung kann so festgelegt werden, dass die MSA/OrgID-Anmeldung und der Zugriff auf Office deaktiviert werden.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Wenn Benutzer versuchen, auf die Sign-In zu zugreifen, wird ein Fehler angezeigt, dass keine Netzwerkverbindung vorhanden ist. Da diese Einstellung auch die Onlineproduktaktivierung blockiert, sollte sie nur für Volumenlizenzinstallationen verwendet werden. Insbesondere verhindert die Verwendung dieser Einstellung, dass Office auf die folgenden Endpunkte zugreifen:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Alle Endpunkte, die oben im Abschnitt "Anmelden" aufgeführt sind.
    
- Alle Endpunkte, die oben im Abschnitt "Smart Lookup" aufgeführt sind.
    
- Alle Endpunkte, die oben im Abschnitt "Produktaktivierung" aufgeführt sind.
    
- Alle Endpunkte, die oben im Abschnitt Office Apps (auch als Add-Ins bezeichnet) aufgeführt sind.
    
Wenn Sie die vollständige Funktionalität für den Benutzer erneut einrichten möchten, legen Sie die Einstellung entweder auf "2" fest, oder entfernen Sie sie.
  
> [!NOTE]
> Diese Einstellung erfordert Office für Mac Build 15.25 [160726] oder höher. 
  
### <a name="telemetry"></a>Telemetrie 
  
Office für Mac sendet telemetrieinformationen in regelmäßigen Abständen an Microsoft zurück. Daten werden an den Nexus-Endpunkt hochgeladen. Die Telemetriedaten helfen dem Entwicklungsteam, die Integrität und unerwartete Verhaltensweisen der einzelnen Office-App. Es gibt zwei Kategorien von Telemetrie:
  
- **Heartbeat** enthält Versions- und Lizenzinformationen. Diese Daten werden sofort nach dem Start der App gesendet. 
    
- **Die** Verwendung enthält Informationen dazu, wie Apps verwendet werden, und nicht schwerwiegende Fehler. Diese Daten werden alle 60 Minuten gesendet. 
    
Microsoft nimmt Ihren Datenschutz sehr ernst. Informationen zur Datensammlungsrichtlinie von Microsoft finden Sie unter [https://privacy.microsoft.com](https://privacy.microsoft.com) . Um zu verhindern, dass Anwendungen "Usage"-Telemetrie senden, kann die **Einstellung SendAllTelemetryEnabled** angepasst werden. Die Einstellung erfolgt pro Anwendung und kann über macOS-Konfigurationsprofile oder manuell über Terminal festgelegt werden: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

Die Takttelemetrie wird immer gesendet und kann nicht deaktiviert werden.
  
### <a name="crash-reporting"></a>Absturzbericht
  
Wenn ein schwerwiegender Anwendungsfehler auftritt, wird die Anwendung unerwartet beendet und einen Absturzbericht in den "Watson"-Dienst hochgeladen. Der Absturzbericht besteht aus einer Aufrufliste, der Liste der Schritte, die die Anwendung vor dem Absturz verarbeitet hat. Diese Schritte helfen dem Engineeringteam, die genaue Funktion zu ermitteln, die fehlgeschlagen ist und warum.
  
In einigen Fällen verursacht der Inhalt eines Dokuments den Absturz der Anwendung. Wenn die App das Dokument als Ursache identifiziert, fragt sie den Benutzer, ob es in Ordnung ist, das Dokument zusammen mit der Aufrufliste zu senden. Benutzer können eine fundierte Entscheidung für diese Frage treffen. IT-Administratoren haben möglicherweise strenge Anforderungen an die Übermittlung von Dokumenten und treffen die Entscheidung im Namen des Benutzers, dokumente niemals zu senden. Die folgende Einstellung kann festgelegt werden, um zu verhindern, dass Dokumente gesendet werden, und um die Eingabeaufforderung an den Benutzer zu unterdrücken:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Wenn **SendAllTelemetryEnabled** auf **FALSE festgelegt** ist, ist die Absturzberichterstellung für diesen Prozess deaktiviert. Zum Aktivieren der Absturzberichterstellung ohne Senden von Verwendungstelemetrie kann die folgende Einstellung festgelegt werden: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Updates
  
Microsoft veröffentlicht Office für Mac Updates in regelmäßigen Abständen (in der Regel einmal im Monat). Wir empfehlen Benutzern und IT-Administratoren dringend, Computer auf dem neuesten Stand zu halten, um sicherzustellen, dass die neuesten Sicherheitskorrekturen installiert sind. In Fällen, in denen IT-Administratoren Computerupdates genau steuern und verwalten möchten, kann die folgende Einstellung festgelegt werden, um zu verhindern, dass der AutoUpdate-Prozess produktupdates automatisch erkennt und bietet:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Blockieren von Anforderungen mit einer Firewall/einem Proxy
  
Wenn Ihre Organisation Anforderungen an URLs über eine Firewall oder einen Proxyserver blockiert, müssen Sie die in diesem Dokument aufgeführten URLs entweder als zulässig oder mit einer 40-fachen Antwort (z. B. 403 oder 404) blockieren. Eine 40-fache Antwort ermöglicht es den Office-Anwendungen, die Unfähigkeit, auf die Ressource zu zugreifen, anmutig zu akzeptieren, und bietet eine schnellere Benutzeroberfläche, als einfach die Verbindung zu löschen, was wiederum dazu führen wird, dass der Client erneut einen Versuch unternimmt.
  
Wenn ihr Proxyserver eine Authentifizierung erfordert, wird eine 407-Antwort an den Client zurückgegeben. Stellen Sie sicher, dass Sie Office für Mac Builds 15.27 oder höher verwenden, da sie bestimmte Korrekturen für die Arbeit mit NTLM- und Kerberos-Servern enthalten.
  
  
## <a name="see-also"></a>Siehe auch

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

