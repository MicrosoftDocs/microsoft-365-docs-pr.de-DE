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
ms.openlocfilehash: e820875a3350761824c3e4e67311e55507a9cb6f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778352"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="api-description"></a>API-Beschreibung

Stellt Methoden und Eigenschaftendetails zu den APIs bereit, die Bedrohungs- und Sicherheitsrisikomanagement Daten pro Gerät abrufen. Es gibt verschiedene API-Aufrufe, um unterschiedliche Arten von Daten abzurufen. Im Allgemeinen enthält jeder API-Aufruf die erforderlichen Daten für Geräte in Ihrer Organisation.

> [!Note]
>
> Sofern nicht anders angegeben, sind alle aufgeführten Exportbewertungsmethoden **_vollständige Exporte_** und **_nach Gerät_** (auch als **_pro Gerät_** bezeichnet).

Es gibt drei API-Methoden, die Sie zum Abrufen (Exportieren) verschiedener Informationstypen verwenden können:

1. Exportieren der Bewertung sicherer Konfigurationen

2. Exportieren der Bewertung des Softwarebestands

3. Exportieren der Bewertung von Sicherheitsrisiken

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
Deviceid | Zeichenfolge | Eindeutiger Bezeichner für das Gerät im Dienst.
DeviceName | Zeichenfolge | Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.
IsApplicable | bool | Gibt an, ob die Konfiguration oder Richtlinie anwendbar ist.
IsCompliant | bool | Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist
IsExpectedUserImpact | bool | Gibt an, ob es Auswirkungen auf den Benutzer gibt, wenn die Konfiguration angewendet wird.
OSPlatform | Zeichenfolge | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.
RbacGroupName | Zeichenfolge | Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen". Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".
RecommendationReference | Zeichenfolge | Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.
Zeitstempel | Zeichenfolge | Zeitpunkt, zu dem die Konfiguration zuletzt auf dem Gerät angezeigt wurde

### <a name="13-properties-via-files"></a>1.3 Eigenschaften (über Dateien)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\] | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.
GeneratedTime | Zeichenfolge | Die Zeit, zu der der Export generiert wurde.

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
Deviceid | Zeichenfolge | Eindeutiger Bezeichner für das Gerät im Dienst.
DeviceName | Zeichenfolge | Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.
DiskPaths | Array[string]  | Datenträgernachweis, dass das Produkt auf dem Gerät installiert ist.
EndOfSupportDate | Zeichenfolge | Das Datum, an dem die Unterstützung für diese Software endet oder endet.
EndOfSupportStatus | Zeichenfolge | Ende des Supportstatus. Kann diese möglichen Werte enthalten: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.
Id | string | Eindeutiger Bezeichner für den Datensatz.
NumberOfWeaknesses | int|Anzahl der Schwachstellen dieser Software auf diesem Gerät
OSPlatform | Zeichenfolge | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.
RbacGroupName | Zeichenfolge | Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen". Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".
RegistryPaths | Array[string] | Registrierungsnachweis, dass das Produkt auf dem Gerät installiert ist.
SoftwareFirstSeenTimestamp | Zeichenfolge | Diese Software wurde zum ersten Mal auf dem Gerät angezeigt.
SoftwareName | Zeichenfolge | Name des Softwareprodukts.
SoftwareVendor | Zeichenfolge | Name des Softwareanbieters.
SoftwareVersion | Zeichenfolge | Versionsnummer des Softwareprodukts.

### <a name="23-properties-via-files"></a>2.3 Eigenschaften (über Dateien)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\] | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.
GeneratedTime | Zeichenfolge | Die Zeit, zu der der Export generiert wurde.

## <a name="3-export-software-vulnerabilities-assessment"></a>3. Bewertung von Software-Sicherheitsrisiken exportieren

Gibt alle bekannten Sicherheitsrisiken auf einem Gerät und deren Details für alle Geräte zurück.

### <a name="31-methods"></a>3.1 Methoden

Methode | Datentyp | Beschreibung
:---|:---|:---
Bewertung von Software-Sicherheitsrisiken **exportieren (OData)** | Untersuchungssammlung Siehe: [3.2 Eigenschaften (OData)](#32-properties-odata) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId zurück. Die API ruft alle Daten in Ihrer Organisation als JSON-Antworten nach dem OData-Protokoll ab. Diese Methode eignet sich am besten für kleine Organisationen mit weniger als 100-K-Geräten. Die Antwort ist paginiert, sodass Sie das Feld @odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.
Bewertung von Software-Sicherheitsrisiken **exportieren (über Dateien)** | Untersuchungsentität Siehe: [3.3 Eigenschaften (über Dateien)](#33-properties-via-files) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId zurück. Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100-K-Geräten empfohlen. Diese API ruft alle Daten in Ihrer Organisation als Downloaddateien ab. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen: 1.  Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten abzurufen. 2.  Laden Sie alle Dateien mithilfe der Download-URLs herunter, und verarbeiten Sie die Daten nach Bedarf.

### <a name="32-properties-odata"></a>3.2-Eigenschaften (OData)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
CveId | Zeichenfolge | Eindeutiger Bezeichner, der dem Sicherheitsrisiko unter dem System für allgemeine Sicherheitsrisiken und Sicherheitsrisiken (CVE) zugewiesen ist.
CvssScore | Zeichenfolge | Die CVSS-Bewertung des CVE.
Deviceid | Zeichenfolge | Eindeutiger Bezeichner für das Gerät im Dienst.
DeviceName | Zeichenfolge | Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.
DiskPaths | \[Arrayzeichenfolge\] | Datenträgernachweis, dass das Produkt auf dem Gerät installiert ist.
ExploitabilityLevel | Zeichenfolge | Die Ausnutzbarkeitsstufe dieser Sicherheitsanfälligkeit (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | Zeichenfolge | Die CVE dieses Produkts wurde zum ersten Mal auf dem Gerät angezeigt.
Id | string | Eindeutiger Bezeichner für den Datensatz.
LastSeenTimestamp | Zeichenfolge | Das letzte Mal, als das CVE auf dem Gerät angezeigt wurde.
OSPlatform | Zeichenfolge | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.
RbacGroupName | Zeichenfolge | Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen". Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".
RecommendationReference | Zeichenfolge | Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.
RecommendedSecurityUpdate | Zeichenfolge | Name oder Beschreibung des sicherheitsrelevanten Updates, das vom Softwareanbieter bereitgestellt wurde, um die Sicherheitsanfälligkeit zu beheben.
RecommendedSecurityUpdateId | Zeichenfolge | Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel
Arrayzeichenfolge für Registrierungspfade \[\] | Registrierungsnachweis, dass das Produkt auf dem Gerät installiert ist.
SoftwareName | Zeichenfolge | Name des Softwareprodukts.
SoftwareVendor | Zeichenfolge | Name des Softwareanbieters.
SoftwareVersion | Zeichenfolge | Versionsnummer des Softwareprodukts.
VulnerabilitySeverityLevel | Zeichenfolge | Schweregrad, der dem Sicherheitsrisiko zugewiesen ist, basierend auf der CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden.

### <a name="33-properties-via-files"></a>3.3 Eigenschaften (über Dateien)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\]  | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.
GeneratedTime | Zeichenfolge | Die Zeit, zu der der Export generiert wurde.

## <a name="see-also"></a>Siehe auch

- [Exportieren der Bewertung der sicheren Konfiguration pro Gerät](get-assessmnt-secure-cfg.md)

- [Exportieren der Softwareinventarisierungsbewertung pro Gerät](get-assessmnt-software-inventory.md)

- [Exportieren der Bewertung von Software-Sicherheitsrisiken pro Gerät](get-assessmnt-software-vulnerabilities.md)

Andere verwandte

- [Risikobasierte Bedrohungs-& Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
