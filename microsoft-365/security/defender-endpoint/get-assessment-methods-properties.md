---
title: Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät
description: Stellt Informationen zu den APIs bereit, die "Bedrohungs- und Sicherheitsrisikomanagement"-Daten abrufen. Es gibt verschiedene API-Aufrufe, um unterschiedliche Arten von Daten abzurufen. Im Allgemeinen enthält jeder API-Aufruf die erforderlichen Daten für Geräte in Ihrer Organisation. Da die Datenmenge groß sein kann, gibt es zwei Möglichkeiten, sie abzurufen.
keywords: API, APIs, Exportbewertung, pro Gerätebewertung, pro Computerbewertung, Bericht zur Bewertung von Sicherheitsrisiken, Bewertung der Sicherheitslücken des Geräts, Bericht über Sicherheitsrisiko, Bewertung der sicheren Konfiguration, Bericht über sichere Konfiguration, Bewertung von Software-Sicherheitsrisiken, Bericht über Sicherheitsrisiken nach Computer,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: ace9f55b0b083faaeeb620700a43a1216c4451c2
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984868"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>API-Beschreibung

Stellt Methoden und Eigenschaftendetails zu den APIs bereit, die Bedrohungs- und Sicherheitsrisikomanagement Daten pro Gerät abrufen. Es gibt verschiedene API-Aufrufe, um unterschiedliche Arten von Daten abzurufen. Im Allgemeinen enthält jeder API-Aufruf die erforderlichen Daten für Geräte in Ihrer Organisation.

> [!Note]
>
> Sofern nicht anders angegeben, sind alle aufgeführten Exportbewertungsmethoden **_vollständige Exporte_** und **_nach Gerät_** (auch als **_pro Gerät_** bezeichnet).

Sie können die Exportbewertungs-APIs verwenden, um verschiedene Arten von Informationen abzurufen (zu exportieren):

- [1. Exportieren der Bewertung sicherer Konfigurationen](#1-export-secure-configurations-assessment)

- [2. Exportieren der Softwareinventarisierungsbewertung](#2-export-software-inventory-assessment)

- [3. Bewertung von Software-Sicherheitsrisiken exportieren](#3-export-software-vulnerabilities-assessment)

Die APIs, die den Exportinformationstypen entsprechen, werden in den Abschnitten 1, 2 und 3 beschrieben.

Für jede Methode gibt es unterschiedliche API-Aufrufe, um unterschiedliche Datentypen abzurufen. Da die Datenmenge groß sein kann, gibt es zwei Möglichkeiten, sie abzurufen:

- **OData**  Die API ruft alle Daten in Ihrer Organisation als JSON-Antworten nach dem OData-Protokoll ab. Diese Methode eignet sich am besten für _kleine Organisationen mit weniger als 100-K-Geräten._ Die Antwort ist paginiert, sodass Sie das \@ Feld odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.

- **über Dateien** Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100-K-Geräten empfohlen. Diese API ruft alle Daten in Ihrer Organisation als Downloaddateien ab. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:

  - Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten abzurufen.

  - Laden Sie alle Dateien mithilfe der Download-URLs herunter, und verarbeiten Sie die Daten nach Bedarf.

Daten, die gesammelt werden (entweder mit _OData_ oder _über Dateien),_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten. Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.

## <a name="1-export-secure-configurations-assessment"></a>1. Exportieren der Bewertung sicherer Konfigurationen

Gibt alle Konfigurationen und deren Status pro Gerät zurück.

### <a name="11-methods"></a>1.1 Methoden

Methode | Datentyp | Beschreibung
:---|:---|:---
Exportieren der Bewertung der sicheren Konfiguration **(OData)** | Sichere Konfiguration nach Gerätesammlung. Siehe: [1.2-Eigenschaften (OData)](#12-properties-odata) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, ConfigurationId, zurück. Die API ruft alle Daten in Ihrer Organisation als JSON-Antworten nach dem OData-Protokoll ab. Diese Methode eignet sich am besten für kleine Organisationen mit weniger als 100-K-Geräten. Die Antwort ist paginiert, sodass Sie das Feld @odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.
Exportieren der Bewertung der sicheren Konfiguration **(über Dateien)** | Sichere Konfiguration nach Gerätesammlung. Siehe: [1.2-Eigenschaften (OData)](#12-properties-odata) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, ConfigurationId, zurück. Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100-K-Geräten empfohlen. Diese API ruft alle Daten in Ihrer Organisation als Downloaddateien ab. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen: 1.  Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten abzurufen. 2.  Laden Sie alle Dateien mithilfe der Download-URLs herunter, und verarbeiten Sie die Daten nach Bedarf.

### <a name="12-properties-odata"></a>1.2-Eigenschaften (OData)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
ConfigurationCategory | string | Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen
ConfigurationId | string | Eindeutiger Bezeichner für eine bestimmte Konfiguration
ConfigurationImpact | string | Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)
ConfigurationName | string | Anzeigename der Konfiguration
ConfigurationSubcategory | string | Unterkategorie oder Untergruppe, zu der die Konfiguration gehört. In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.
Deviceid | string | Eindeutiger Bezeichner für das Gerät im Dienst.
DeviceName | string | Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.
IsApplicable | bool | Gibt an, ob die Konfiguration oder Richtlinie anwendbar ist.
IsCompliant | bool | Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist
IsExpectedUserImpact | bool | Gibt an, ob es Auswirkungen auf den Benutzer gibt, wenn die Konfiguration angewendet wird.
OSPlatform | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.
RbacGroupName | string | Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen". Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".
RecommendationReference | string | Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.
Zeitstempel | string | Zeitpunkt, zu dem die Konfiguration zuletzt auf dem Gerät angezeigt wurde

### <a name="13-properties-via-files"></a>1.3 Eigenschaften (über Dateien)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\] | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.
GeneratedTime | string | Die Zeit, zu der der Export generiert wurde.

## <a name="2-export-software-inventory-assessment"></a>2. Exportieren der Softwareinventarisierungsbewertung

Gibt alle installierten Software und deren Details auf jedem Gerät zurück.

### <a name="21-methods"></a>2.1 Methoden

Methode | Datentyp | Beschreibung
:---|:---|:---
Exportieren der Softwareinventarbewertung **(OData)** | Softwareinventarisierung nach Gerätesammlung. Siehe: [2.2-Eigenschaften (OData)](#22-properties-odata) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück. Die API ruft alle Daten in Ihrer Organisation als JSON-Antworten nach dem OData-Protokoll ab. Diese Methode eignet sich am besten für kleine Organisationen mit weniger als 100-K-Geräten. Die Antwort ist paginiert, sodass Sie das Feld @odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.
Exportieren der Softwareinventarisierungsbewertung **(über Dateien)** | Softwareinventarisierung nach Gerätedateien. Siehe: [2.3 Eigenschaften (über Dateien)](#23-properties-via-files) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück. Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100-K-Geräten empfohlen. Diese API ruft alle Daten in Ihrer Organisation als Downloaddateien ab. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen: 1.  Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten abzurufen. 2.  Laden Sie alle Dateien mithilfe der Download-URLs herunter, und verarbeiten Sie die Daten nach Bedarf.

### <a name="22-properties-odata"></a>2.2-Eigenschaften (OData)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
Deviceid | string | Eindeutiger Bezeichner für das Gerät im Dienst.
DeviceName | string | Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.
DiskPaths | Array[string]  | Datenträgernachweis, dass das Produkt auf dem Gerät installiert ist.
EndOfSupportDate | string | Das Datum, an dem die Unterstützung für diese Software endet oder endet.
EndOfSupportStatus | string | Ende des Supportstatus. Kann diese möglichen Werte enthalten: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.
Id | string | Eindeutiger Bezeichner für den Datensatz.
NumberOfWeaknesses | int|Anzahl der Schwachstellen dieser Software auf diesem Gerät
OSPlatform | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.
RbacGroupName | string | Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen". Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".
RegistryPaths | Array[string] | Registrierungsnachweis, dass das Produkt auf dem Gerät installiert ist.
SoftwareFirstSeenTimestamp | string | Diese Software wurde zum ersten Mal auf dem Gerät angezeigt.
SoftwareName | string | Name des Softwareprodukts.
SoftwareVendor | string | Name des Softwareanbieters.
SoftwareVersion | string | Versionsnummer des Softwareprodukts.

### <a name="23-properties-via-files"></a>2.3 Eigenschaften (über Dateien)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\] | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.
GeneratedTime | string | Die Zeit, zu der der Export generiert wurde.

## <a name="3-export-software-vulnerabilities-assessment"></a>3. Bewertung von Software-Sicherheitsrisiken exportieren

Gibt alle bekannten Sicherheitsrisiken auf einem Gerät und deren Details für alle Geräte zurück.

### <a name="31-methods"></a>3.1 Methoden

Methode | Datentyp | Beschreibung
:---|:---|:---
Bewertung von Software-Sicherheitsrisiken **exportieren (OData)** | Untersuchungssammlung Siehe: [3.2 Eigenschaften (OData)](#32-properties-odata) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId zurück. Die API ruft alle Daten in Ihrer Organisation als JSON-Antworten nach dem OData-Protokoll ab. Diese Methode eignet sich am besten für kleine Organisationen mit weniger als 100-K-Geräten. Die Antwort ist paginiert, sodass Sie das Feld @odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.
Bewertung von Software-Sicherheitsrisiken **exportieren (über Dateien)** | Untersuchungsentität Siehe: [3.3 Eigenschaften (über Dateien)](#33-properties-via-files) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId zurück. Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100-K-Geräten empfohlen. Diese API ruft alle Daten in Ihrer Organisation als Downloaddateien ab. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen: 1.  Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten abzurufen. 2.  Laden Sie alle Dateien mithilfe der Download-URLs herunter, und verarbeiten Sie die Daten nach Bedarf.
Bewertung von Software-Sicherheitsrisiken im **Delta-Export** **(OData)** | Untersuchungssammlung Siehe: [3.4 Eigenschaften Delta Export OData)](#34-properties-delta-export-odata) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination von: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId und EventTimestamp zurück. <br><br> Die API ruft Daten in Ihrer Organisation als JSON-Antworten nach dem OData-Protokoll ab. Die Antwort ist paginiert, sodass Sie das Feld @odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen. Im Gegensatz zur vollständigen Bewertung von Softwareschwachstellen (OData), die verwendet wird, um eine vollständige Momentaufnahme der Bewertung der Software-Sicherheitsrisiken Ihrer Organisation nach Gerät zu erhalten, wird der Deltaexport-OData-API-Aufruf verwendet, um nur die Änderungen abzurufen, die zwischen einem ausgewählten Datum und dem aktuellen Datum (dem "Delta"-API-Aufruf) aufgetreten sind. Anstatt jedes Mal einen vollständigen Export mit einer großen Datenmenge zu erhalten, erhalten Sie nur spezifische Informationen zu neuen, festen und aktualisierten Sicherheitsrisiken. Der Delta-Export-OData-API-Aufruf kann auch verwendet werden, um verschiedene KPIs zu berechnen, z. B. "wie viele Sicherheitsrisiken wurden behoben?" oder "wie viele neue Sicherheitsrisiken wurden zu meiner Organisation hinzugefügt?"  <br><br> Da der Delta-Export-OData-API-Aufruf für Softwarerisiken nur Daten für einen Zieldatumsbereich zurückgibt, wird er nicht als _vollständiger Export_ betrachtet.

### <a name="32-properties-odata"></a>3.2-Eigenschaften (OData)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
CveId | string | Eindeutiger Bezeichner, der dem Sicherheitsrisiko unter dem System für allgemeine Sicherheitsrisiken und Sicherheitsrisiken (CVE) zugewiesen ist.
CvssScore | string | Die CVSS-Bewertung des CVE.
Deviceid | string | Eindeutiger Bezeichner für das Gerät im Dienst.
DeviceName | string | Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.
DiskPaths | \[Arrayzeichenfolge\] | Datenträgernachweis, dass das Produkt auf dem Gerät installiert ist.
ExploitabilityLevel | string | Die Ausnutzbarkeitsstufe dieser Sicherheitsanfälligkeit (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | string | Die CVE dieses Produkts wurde zum ersten Mal auf dem Gerät angezeigt.
Id | string | Eindeutiger Bezeichner für den Datensatz.
LastSeenTimestamp | string | Das letzte Mal, als das CVE auf dem Gerät angezeigt wurde.
OSPlatform | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.
RbacGroupName | string | Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen". Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".
RecommendationReference | string | Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.
RecommendedSecurityUpdate | string | Name oder Beschreibung des sicherheitsrelevanten Updates, das vom Softwareanbieter bereitgestellt wurde, um die Sicherheitsanfälligkeit zu beheben.
RecommendedSecurityUpdateId | string | Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel
Arrayzeichenfolge für Registrierungspfade \[\] | Registrierungsnachweis, dass das Produkt auf dem Gerät installiert ist.
SoftwareName | string | Name des Softwareprodukts.
SoftwareVendor | string | Name des Softwareanbieters.
SoftwareVersion | string | Versionsnummer des Softwareprodukts.
VulnerabilitySeverityLevel | string | Schweregrad, der dem Sicherheitsrisiko zugewiesen ist, basierend auf der CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden.

### <a name="33-properties-via-files"></a>3.3 Eigenschaften (über Dateien)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\]  | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.
GeneratedTime | string | Die Zeit, zu der der Export generiert wurde.

### <a name="34-properties-delta-export-odata"></a>3.4 Eigenschaften (Deltaexport OData)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
CveId | string | Eindeutiger Bezeichner, der dem Sicherheitsrisiko unter dem System für allgemeine Sicherheitsrisiken und Sicherheitsrisiken (CVE) zugewiesen ist.
CvssScore | string | Die CVSS-Bewertung des CVE.
Deviceid | string | Eindeutiger Bezeichner für das Gerät im Dienst.
DeviceName | string | Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.
DiskPaths | Array[string] | Datenträgernachweis, dass das Produkt auf dem Gerät installiert ist.
EventTimestamp | Zeichenfolge | Die Zeit, zu der dieses Delta-Ereignis gefunden wurde.
ExploitabilityLevel | string | Die Ausnutzbarkeitsstufe dieser Sicherheitsanfälligkeit (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | string | Die CVE dieses Produkts wurde zum ersten Mal auf dem Gerät angezeigt.
Id | string | Eindeutiger Bezeichner für den Datensatz.  
LastSeenTimestamp | string | Das letzte Mal, als das CVE auf dem Gerät angezeigt wurde.
OSPlatform | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.
RbacGroupName | string | Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen". Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".
RecommendationReference | string | Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.
RecommendedSecurityUpdate  | string | Name oder Beschreibung des sicherheitsrelevanten Updates, das vom Softwareanbieter bereitgestellt wurde, um die Sicherheitsanfälligkeit zu beheben.
RecommendedSecurityUpdateId  | string | Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel
RegistryPaths  | Array[string] | Registrierungsnachweis, dass das Produkt auf dem Gerät installiert ist.
SoftwareName | string | Name des Softwareprodukts.
SoftwareVendor | string | Name des Softwareanbieters.
SoftwareVersion | string | Versionsnummer des Softwareprodukts.
Status | Zeichenfolge | **Neu**   (für eine neue Sicherheitslücke, die auf einem Gerät eingeführt wurde).  **Behoben**   (für eine Sicherheitslücke, die auf dem Gerät nicht mehr vorhanden ist, was bedeutet, dass sie behoben wurde). **Aktualisiert**   (für eine Sicherheitslücke auf einem Gerät, das sich geändert hat. Die möglichen Änderungen sind: CVSS-Bewertung, Ausnutzbarkeitsgrad, Schweregrad, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).
VulnerabilitySeverityLevel | string | Schweregrad, der dem Sicherheitsrisiko zugewiesen ist, basierend auf der CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden.

## <a name="see-also"></a>Siehe auch

- [Exportieren der Bewertung der sicheren Konfiguration pro Gerät](get-assessment-secure-config.md)

- [Exportieren der Softwareinventarisierungsbewertung pro Gerät](get-assessment-software-inventory.md)

- [Exportieren der Bewertung von Software-Sicherheitsrisiken pro Gerät](get-assessment-software-vulnerabilities.md)

Andere verwandte

- [Risikobasierte bedrohungsbasierte & Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
