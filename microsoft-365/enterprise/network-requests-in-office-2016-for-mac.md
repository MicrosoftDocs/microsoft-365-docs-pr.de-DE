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
description: In diesem Artikel wird beschrieben, welche Endpunkte und URLs Office für Mac Anwendungen zu erreichen versuchen und welche Dienste bereitgestellt werden.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690601"
---
# <a name="network-requests-in-office-for-mac"></a>Netzwerkanforderungen in Office für Mac

Office für Mac Anwendungen bieten eine native App-Erfahrung auf der macOS-Plattform. Jede APP ist für die Verwendung in einer Vielzahl von Szenarien konzipiert, einschließlich der Status, wenn kein Netzwerkzugriff verfügbar ist. Wenn ein Computer mit einem Netzwerk verbunden ist, stellen die Anwendungen automatisch eine Verbindung mit einer Reihe von webbasierten Diensten her, um eine erweiterte Funktionalität bereitzustellen. In den folgenden Informationen werden die Endpunkte und URLs beschrieben, die von den Anwendungen erreicht werden sollen, sowie die bereitgestellten Dienste. Diese Informationen sind hilfreich bei der Behandlung von Problemen mit der Netzwerkkonfiguration und beim Festlegen von Richtlinien für Netzwerkproxy Server. Die Details in diesem Artikel sollen den [Artikel Office 365 URL und Adressbereiche](urls-and-ip-address-ranges.md)ergänzen, der Endpunkte für Computer mit Microsoft Windows enthält. Sofern nicht anders angegeben, gelten die Informationen in diesem Artikel auch für Office 2019 für Mac und Office 2016 für Mac, die als einmaliger Einkauf von einem Einzelhandelsgeschäft oder über einen Volumenlizenzvertrag zur Verfügung stehen. 

  
Bei den meisten dieser Artikel handelt es sich um Tabellen, die die Netzwerk-URLs, den Typ und die Beschreibung des Diensts oder der Funktion beschreiben, die von diesem Endpunkt bereitgestellt werden. Jede der Office-Apps unterscheidet sich möglicherweise bei der Dienst-und Endpunkt Verwendung. Die folgenden apps sind in den folgenden Tabellen definiert:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
Der URL-Typ ist wie folgt definiert:
  
- St: static-die URL ist in der Clientanwendung hart codiert.
    
- SS: Semi-static-die URL wird als Teil einer Webseite oder eines Umleitungs Zeichens codiert.
    
- CS: config Service – die URL wird als Teil des Office-Konfigurations Diensts zurückgegeben.

    
## <a name="office-for-mac-default-configuration"></a>Office für Mac Standardkonfiguration

 **Installation und Updates**
  
Die folgenden Netzwerkendpunkte werden verwendet, um das Office für Mac Installationsprogramm aus dem Microsoft Content Delivery Network (CDN) herunterzuladen.
  
|**URL**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |St  <br/> |Microsoft 365-Installations Portal: Link-Dienst wird an die neuesten Installationspakete weitergeleitet.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Speicherort der Installationspakete im Inhalts Zustellungs Netzwerk.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Speicherort der Installationspakete im Inhalts Zustellungs Netzwerk.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |St  <br/> |Endpunkt der Verwaltungssteuerung für Microsoft AutoUpdate  <br/> |
   
 **Erster App-Start**
  
Die folgenden Netzwerkendpunkte werden beim ersten Start einer Office-App kontaktiert. Diese Endpunkte bieten erweiterte Office-Funktionen für Benutzer, und die URLs werden unabhängig vom Lizenztyp (einschließlich Volumenlizenz Installationen) kontaktiert.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |St  <br/> |"Flighting"-Konfiguration-ermöglicht Feature-Beleuchtung und experimentieren.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |St  <br/> |Netzwerk Konfigurations Test ' flighting '  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |St  <br/> |Netzwerk Konfigurations Test ' flighting '  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |St  <br/> |Office-Konfigurationsdienst – Master Liste der Dienstendpunkte.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |St  <br/> |Office Rules Telemetrie-Download – informiert den Client darüber, welche Daten und Ereignisse in den Telemetrie-Dienst hochgeladen werden sollen.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |OneNote-Telemetrie-Dienst  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |St  <br/> |Office Telemetry Upload Reporting-"Heartbeart" und Fehlerereignisse, die auf dem Client auftreten, werden in den Telemetrie-Dienst hochgeladen.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office-Vorlagen Dienst – stellt Benutzern Onlinedokument Vorlagen bereit.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Office-Vorlagen Downloads – Speicherung von PNG-Vorlagen Bildern.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Store-Konfiguration für Office-Apps.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office Document Integration Services-Katalog (Liste der Dienste und Endpunkte) und Ermittlung des Startbereichs.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Ressourcen für die Heim Bereichssuche v2 (15,40 und höher)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |St  <br/> |Microsoft AutoUpdate-Manifeste – überprüft, ob Updates verfügbar sind.  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Microsoft AJAX-JavaScript-Bibliothek  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-APP für Office-Konfiguration und-Ressourcen.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Map-App für Office-Konfiguration und-Ressourcen.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |People Graph-App für Office-Konfiguration und-Ressourcen.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |St  <br/> |Neuer Inhalt für OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |St  <br/> |Neuer Inhalt für OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |Neue Bilder für OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |St  <br/> |In-App-Support Dienst.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |St  <br/> |E-Mail-Konto Erkennungsdienst.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |St  <br/> |Outlook-AutoErmittlung  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |St  <br/> |Outlook-Endpunkt für Microsoft 365-Dienst.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |St  <br/> |Symbole für Outlook-Add-Ins.  <br/> |
   
> [!NOTE]
> Der Office-Konfigurationsdienst fungiert als automatischer Ermittlungsdienst für alle Microsoft Office Clients, nicht nur für Mac. Die in der Antwort zurückgegebenen Endpunkte sind Semi-statisch, da diese Änderung sehr selten, aber dennoch möglich ist. 
  
 **Anmeldung**
  
Die folgenden Netzwerkendpunkte werden kontaktiert, wenn Sie sich bei Cloud-basiertem Speicher anmelden. Abhängig vom Kontotyp werden möglicherweise verschiedene Dienste kontaktiert. Beispiel:
  
- **MSA: Microsoft-Konto** -wird in der Regel für Consumer-und Einzelhandels Szenarien verwendet 
    
- **OrgId: organisationskonto** -wird in der Regel für kommerzielle Szenarien verwendet 
    
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |St  <br/> |Windows-Autorisierungsdienst  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |St  <br/> |Microsoft 365-Anmeldedienst (OrgId)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |St  <br/> |Microsoft-Konto Anmeldedienst (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Microsoft Account Login Service Helper (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365-Anmelde Branding (OrgId)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Speicherverzeichnis für Dokumente und Orte  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Zuletzt verwendeter Dokumentdienst (MRU)  <br/> |
   
> [!NOTE]
> Für abonnementbasierte und Einzelhandelslizenzen aktiviert das Anmelden beide das Produkt und ermöglicht den Zugriff auf Cloud-Ressourcen wie OneDrive. Bei Volumenlizenz Installationen werden Benutzer weiterhin aufgefordert, sich anzumelden (standardmäßig), aber dies ist nur für den Zugriff auf Cloud-Ressourcen erforderlich, da das Produkt bereits aktiviert ist. 
  
 **Produktaktivierung**
  
Die folgenden Netzwerkendpunkte gelten für die Aktivierung von Microsoft 365-Abonnements und Einzelhandelslizenzen. Dies gilt insbesondere nicht für Volumenlizenz Installationen.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Office-Lizenzierungsdienst  <br/> |
   
 **Neuer Inhalt**
  
Die folgenden Netzwerkendpunkte gelten nur für das Microsoft 365-Abonnement.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |Neuer JSON-Seiteninhalt.  <br/> |
   
 **Recherche**
  
Die folgenden Netzwerkendpunkte gelten nur für das Microsoft 365-Abonnement.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Suchdienst  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Statischer Inhalt der Forscher  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |Researcher-Inhaltsanbieter  <br/> |
   
 **Intelligentes Nachschlagen**
  
Die folgenden Netzwerkendpunkte gelten sowohl für Microsoft 365-Abonnement-als auch für Einzelhandels-/Volumenlizenz Aktivierungen.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Insights-Webdienst  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |JQuery-Bibliothek  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Unterstützende JavaScript-Bibliothek  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Insights-Inhaltsanbieter  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Insights-Inhaltsanbieter  <br/> |
   
 **PowerPoint-Designer**
  
Die folgenden Netzwerkendpunkte gelten nur für das Microsoft 365-Abonnement.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint-Designer-Webdienst  <br/> |
   
 **PowerPoint-Schnellstarter**
  
Die folgenden Netzwerkendpunkte gelten nur für das Microsoft 365-Abonnement.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint Quick Start-Webdienst  <br/> |
   
 **Senden eines Lächelns/Stirnrunzeln**
  
Die folgenden Netzwerkendpunkte gelten sowohl für Microsoft 365-Abonnement-als auch für Einzelhandels-/Volumenlizenz Aktivierungen.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Senden eines smile-Diensts  <br/> |
   
 **Kontakt Support**
  
Die folgenden Netzwerkendpunkte gelten sowohl für Microsoft 365-Abonnement-als auch für Einzelhandels-/Volumenlizenz Aktivierungen.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Wenden Sie sich an den Support Dienst  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |In-App-Support Dienst  <br/> |
   
 **Als PDF speichern**
  
Die folgenden Netzwerkendpunkte gelten sowohl für Microsoft 365-Abonnement-als auch für Einzelhandels-/Volumenlizenz Aktivierungen.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Word Document Conversion Service (PDF)  <br/> |
   
 **Office-Apps (aka-Add-Ins)**
  
Die folgenden Netzwerkendpunkte gelten sowohl für Microsoft 365-Abonnement-als auch für Einzelhandels-/Volumenlizenz Aktivierungen, wenn Office-App-Add-ins vertrauenswürdig sind.
  
|**URL**|**Apps**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Konfiguration des Office-App-Shops  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-APP-Ressourcen  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Map-App-Ressourcen  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |Ressourcen für Personen Graph-apps  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office-Umleitungsdienst  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Office-JavaScript-Bibliotheken  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Telemetrie und Reporting Service für Office-Apps  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Microsoft AJAX-JavaScript-Bibliothek  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Microsoft AJAX-JavaScript-Bibliothek  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Office-JavaScript-Bibliotheken  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Support Ressourcen  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Support Ressourcen  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |Support Ressourcen  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |JavaScript-Bibliothek  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |Fehlerberichterstattung  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |Schriftressourcen  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |Telemetrie-Dienst  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Telemetrie-Berichterstellung  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Store-Objektbibliothek  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-Seitenressourcen  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-Medienressourcen  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-Sandbox-Frame  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |Kartenvorlagen  <br/> |
   
 **Sichere Links**
  
Der folgende Netzwerkendpunkt gilt nur für alle Office-Anwendungen für Microsoft 365-Abonnements.
  
|**URL**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Microsoft-Safe-Link-Dienst  <br/> |
   
 **Absturzbericht Erstellung**
  
Der folgende Netzwerkendpunkt gilt für alle Office-Anwendungen sowohl für Microsoft 365-Abonnement-als auch für Einzelhandels-/Volumenlizenz Aktivierungen. Wenn ein Prozess unerwartet abstürzt, wird ein Bericht generiert und an den Watson-Dienst gesendet.
  
|**URL**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |St  <br/> |Microsoft-Fehlerberichterstattungsdienst  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |St  <br/> |Office Collaborative Insights-Dienst  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Optionen für die Reduzierung von Netzwerkanforderungen und Datenverkehr

Die Standardkonfiguration von Office für Mac bietet eine optimale Benutzererfahrung, sowohl in Bezug auf die Funktionalität als auch auf dem neuesten Stand der Aktualisierung des Computers. In einigen Szenarien möchten Sie möglicherweise verhindern, dass Anwendungen an Netzwerkendpunkte wenden. In diesem Abschnitt werden die Optionen erläutert.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Deaktivieren der Cloud-Anmeldung und von Office-Add-ins
  
Kunden mit Volumenlizenzen haben möglicherweise strenge Richtlinien zum Speichern von Dokumenten im Cloud-basierten Speicher. Die folgende Einstellung pro Anwendung kann so eingestellt werden, dass die MSA/OrgId-Anmeldung deaktiviert wird und der Zugriff auf Office-Add-Ins möglich ist.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Wenn Benutzer versuchen, auf die Anmeldefunktion zuzugreifen, wird ein Fehler angezeigt, dass keine Netzwerkverbindung vorhanden ist. Da diese Einstellung auch die Online Produktaktivierung blockiert, sollte Sie nur für Volumenlizenz Installationen verwendet werden. Durch die Verwendung dieser Einstellung wird insbesondere verhindert, dass Office-Anwendungen auf die folgenden Endpunkte zugreifen:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Alle Endpunkte, die im Abschnitt "Anmelden" oben aufgeführt sind.
    
- Alle Endpunkte, die im Abschnitt "Smart Lookup" oben aufgeführt sind.
    
- Alle Endpunkte, die im Abschnitt "Produktaktivierung" aufgeführt sind.
    
- Alle Endpunkte, die im Abschnitt "Office-Apps (aka-Add-Ins)" aufgeführt sind.
    
Um die vollständige Funktionalität für den Benutzer wiederherzustellen, legen Sie die Einstellung auf "2" fest, oder entfernen Sie Sie.
  
> [!NOTE]
> Für diese Voreinstellung ist Office für Mac Build 15,25 [160726] oder höher erforderlich. 
  
### <a name="telemetry"></a>Telemetrie 
  
In regelmäßigen Abständen sendet Office für Mac Telemetrie-Informationen zurück an Microsoft. Daten werden in den Endpunkt "Nexus" hochgeladen. Die Telemetrie-Daten unterstützen das Entwicklungsteam bei der Bewertung der Integrität und der unerwarteten Verhaltensweisen der einzelnen Office-Apps. Es gibt zwei Kategorien von Telemetrie:
  
- **Heartbeat** enthält Versions-und Lizenzinformationen. Diese Daten werden sofort beim APP-Start gesendet. 
    
- Die **Verwendung** enthält Informationen zur Verwendung von apps und zu nicht schwerwiegenden Fehlern. Diese Daten werden alle 60 Minuten gesendet. 
    
Microsoft nimmt Ihre Privatsphäre sehr ernst. Weitere Informationen zur Datensammlungsrichtlinie von Microsoft finden Sie unter [https://privacy.microsoft.com](https://privacy.microsoft.com) . Um zu verhindern, dass Anwendungen "Usage"-Telemetrie senden, kann die **SendAllTelemetryEnabled** -Einstellung angepasst werden. Die Einstellung ist pro Anwendung und kann über macOS-Konfigurationsprofile oder manuell vom Terminal aus festgelegt werden: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

Takt Telemetrie wird immer gesendet und kann nicht deaktiviert werden.
  
### <a name="crash-reporting"></a>Absturzbericht Erstellung
  
Wenn ein schwerwiegender Anwendungsfehler auftritt, wird die Anwendung unerwartet beendet und lädt einen Absturzbericht in den "Watson"-Dienst hoch. Der Absturzbericht besteht aus einem Aufruf Stapel, der die Liste der Schritte ist, die von der Anwendung verarbeitet wurden, was zum Absturz führte. Diese Schritte helfen dem Entwicklungsteam, die genaue Funktion zu identifizieren, die fehlgeschlagen ist und warum.
  
In einigen Fällen führt der Inhalt eines Dokuments zum Absturz der Anwendung. Wenn die APP das Dokument als Ursache identifiziert, wird der Benutzer gefragt, ob es in Ordnung ist, das Dokument auch zusammen mit der Aufrufliste zu senden. Benutzer können eine fundierte Entscheidung für diese Frage treffen. IT-Administratoren haben möglicherweise strenge Anforderungen an die Übertragung von Dokumenten und treffen die Entscheidung im Namen des Benutzers, niemals Dokumente zu senden. Die folgende Einstellung kann festgelegt werden, um zu verhindern, dass Dokumente gesendet werden, und die Aufforderung an den Benutzer zu unterdrücken:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Wenn **SendAllTelemetryEnabled** auf **false**festgelegt ist, werden alle Absturzberichte für diesen Prozess deaktiviert. Zum Aktivieren der Absturzbericht Erstellung ohne Senden der Nutzungs Telemetrie kann die folgende Einstellung festgelegt werden: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Updates
  
Microsoft veröffentlicht Office für Mac Updates in regelmäßigen Abständen (in der Regel einmal im Monat). Wir empfehlen Benutzern und IT-Administratoren dringend, Computer auf dem neuesten Stand zu halten, um sicherzustellen, dass die neuesten Sicherheitsfixes installiert sind. In den Fällen, in denen IT-Administratoren Computer Updates genau steuern und verwalten möchten, kann die folgende Einstellung festgelegt werden, um zu verhindern, dass der AutoUpdate-Prozess automatisch Produktaktualisierungen erkennt und anbietet:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Blockieren von Anforderungen mit einer Firewall/einem Proxy
  
Wenn Ihre Organisation Anforderungen an URLs über eine Firewall oder einen Proxy Server blockiert, müssen Sie sicherstellen, dass die in diesem Dokument aufgeführten URLs entweder als zulässig oder als Block mit einer 40-d-Antwort (z. b. 403 oder 404) aufgeführt sind. Eine 40-Antwort ermöglicht es den Office-Anwendungen, die Unfähigkeit, auf die Ressource zuzugreifen, zu akzeptieren und eine schnellere Benutzeroberfläche zu bieten, als die Verbindung einfach abzubrechen, was wiederum dazu führt, dass der Client wiederholt wird.
  
Wenn Ihr Proxyserverauthentifizierung erfordert, wird eine 407-Antwort an den Client zurückgegeben. Um die beste Erfahrung zu erzielen, stellen Sie sicher, dass Sie Office für Mac Builds 15,27 oder höher verwenden, da Sie bestimmte Korrekturen für die Arbeit mit NTLM-und Kerberos-Servern beinhalten.
  
  
## <a name="see-also"></a>Siehe auch

[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)

