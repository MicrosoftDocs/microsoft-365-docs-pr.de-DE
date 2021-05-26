---
title: Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät
description: Stellt Informationen zu den APIs zur Verfügung, die "Bedrohungs- und Sicherheitsrisikomanagement" ziehen. Es gibt verschiedene API-Aufrufe, um verschiedene Datentypen zu erhalten. Im Allgemeinen enthält jeder API-Aufruf die erforderlichen Daten für Geräte in Ihrer Organisation. Da die Datenmenge sehr groß sein kann, gibt es zwei Möglichkeiten, sie abzurufen.
keywords: api, apis, export assessment, per device assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilites assessment, software vulnerability report, vulnerability report by machine,
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
ms.openlocfilehash: 851c792265375e5905c0c427bfc77a2366bc962d
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653658"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="api-description"></a>API-Beschreibung

Stellt Methoden und Eigenschaftendetails zu den APIs zur Verfügung, Bedrohungs- und Sicherheitsrisikomanagement Daten auf Gerätebasis ziehen. Es gibt verschiedene API-Aufrufe, um verschiedene Datentypen zu erhalten. Im Allgemeinen enthält jeder API-Aufruf die erforderlichen Daten für Geräte in Ihrer Organisation.

> [!Note]
>
> Sofern nicht anders angegeben, sind **** alle aufgeführten Exportbewertungsmethoden der vollständige Export und nach Gerät **_(auch_** als pro **_Gerät bezeichnet)._**

Es gibt verschiedene API-Aufrufe, um verschiedene Datentypen zu erhalten. Da die Datenmenge groß sein kann, gibt es zwei Möglichkeiten, sie abzurufen:

- **OData**  Die API verwendet alle Daten in Ihrer Organisation als Json-Antworten nach dem OData-Protokoll. Diese Methode ist am besten für _kleine Organisationen mit weniger als 100K-Geräten._ Die Antwort wird paginiert, sodass Sie das odata.nextLink-Feld aus der Antwort verwenden können, \@ um die nächsten Ergebnisse zu erhalten.

- **über Dateien** Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100K-Geräten empfohlen. Diese API verwendet alle Daten in Ihrer Organisation als Downloaddateien. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:

  - Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten zu erhalten.

  - Laden Sie alle Dateien mithilfe der URLs zum Herunterladen herunter, und verarbeiten Sie die Daten nach Ben.

Die erfassten Daten (für _OData_ oder über Dateien _)_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten. Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.

Sofern nicht anders angegeben, sind **** alle aufgeführten Exportbewertungsmethoden der vollständige Export und nach Gerät **_(auch_** als pro **_Gerät bezeichnet)._**

## <a name="1-export-secure-configurations-assessment"></a>1. Bewertung sicherer Konfigurationen exportieren

Gibt alle Konfigurationen und deren Status auf Gerätebasis zurück.

### <a name="11-methods"></a>1.1-Methoden

Methode | Datentyp | Beschreibung
:---|:---|:---
[Export secure configuration assessment (OData)](get-assessmnt-secure-cfg.md#1-export-secure-configuration-assessment-odata) | Sichere Konfiguration nach Gerätesammlung. Siehe: [1.2 Properties (OData)](#12-properties-odata) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination von DeviceId, ConfigurationId zurück. Die erfassten Daten (für _OData_ oder über Dateien _)_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten. Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.
[Exportieren einer sicheren Konfigurationsbewertung (über Dateien)](get-assessmnt-secure-cfg.md#2-export-secure-configuration-assessment-via-files) | sichere Konfiguration nach Gerätedateien. Siehe: [1.3 Eigenschaften (über Dateien)](#13-properties-via-files) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination von DeviceId, ConfigurationId zurück. Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100K-Geräten empfohlen. Diese API verwendet alle Daten in Ihrer Organisation als Downloaddateien. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen: 1.  Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten zu erhalten. 2.  Laden Sie alle Dateien mithilfe der URLs zum Herunterladen herunter, und verarbeiten Sie die Daten nach Ben.

### <a name="12-properties-odata"></a>1.2 Properties (OData)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
ConfigurationCategory | string | Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen
ConfigurationId | string | Eindeutiger Bezeichner für eine bestimmte Konfiguration
ConfigurationImpact | string | Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)
ConfigurationName | string | Anzeigename der Konfiguration
ConfigurationSubcategory | string | Unterkategorie oder Untergruppe, zu der die Konfiguration gehört. In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.
DeviceId | string | Eindeutige ID für das Gerät im Dienst.
DeviceName | string | Vollqualifizierter Domänenname (FQDN) des Geräts.
IsApplicable | bool | Gibt an, ob die Konfiguration oder Richtlinie anwendbar ist
IsCompliant | bool | Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist
IsExpectedUserImpact | bool | Gibt an, ob sich benutzer auswirken wird, wenn die Konfiguration angewendet wird.
OSPlatform | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Weitere Informationen finden Sie unter tvm supported operating systems and platforms.
RbacGroupName | string | Die rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keinem RBAC-Gruppen zugewiesen ist, wird der Wert "Nicht zugewiesen" angezeigt. Wenn die Organisation keine RBAC-Gruppen enthält, ist der Wert "None".
RecommendationReference | string | Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.
Zeitstempel | string | Das letzte Mal, als die Konfiguration auf dem Gerät angezeigt wurde

### <a name="13-properties-via-files"></a>1.3 Eigenschaften (über Dateien)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\] | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.
GeneratedTime | string | Der Zeitpunkt, zu dem der Export generiert wurde.

## <a name="2-export-software-inventory-assessment"></a>2. Exportieren der Softwareinventarbewertung

Gibt alle installierten Software und deren Details auf jedem Gerät zurück.

### <a name="21-methods"></a>2.1-Methoden

Methode | Datentyp | Beschreibung
:---|:---|:---
[Export software inventory assessment (OData)](get-assessmnt-software-inventory.md#1-export-software-inventory-assessment-odata) | Softwareinventar nach Gerätesammlung. Siehe: [2.2 Properties (OData)](#22-properties-odata) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück. Die erfassten Daten (für _OData_ oder über Dateien _)_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten. Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.
[Exportieren der Softwareinventarbewertung (über Dateien)](get-assessmnt-software-inventory.md#2-export-software-inventory-assessment-via-files) | Softwareinventar nach Gerätedateien. Siehe: [2.3 Eigenschaften (über Dateien)](#23-properties-via-files) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück. Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100K-Geräten empfohlen. Diese API verwendet alle Daten in Ihrer Organisation als Downloaddateien. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen: 1.  Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten zu erhalten. 2.  Laden Sie alle Dateien mithilfe der URLs zum Herunterladen herunter, und verarbeiten Sie die Daten nach Ben.

### <a name="22-properties-odata"></a>2.2 Properties (OData)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
DeviceId | string | Eindeutige ID für das Gerät im Dienst.
DeviceName | string | Vollqualifizierter Domänenname (FQDN) des Geräts.
DiskPaths | Array[string]  | Datenträgerbeweis, dass das Produkt auf dem Gerät installiert ist.
EndOfSupportDate | string | Das Datum, an dem die Unterstützung für diese Software endet.
EndOfSupportStatus | string | Ende des Supportstatus. Kann die folgenden möglichen Werte enthalten: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.
Id | string | Eindeutige ID für den Datensatz.
NumberOfWeaknesses | int|Anzahl der Schwachstellen dieser Software auf diesem Gerät
OSPlatform | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Weitere Informationen finden Sie unter tvm supported operating systems and platforms.
RbacGroupName | string | Die rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keinem RBAC-Gruppen zugewiesen ist, wird der Wert "Nicht zugewiesen" angezeigt. Wenn die Organisation keine RBAC-Gruppen enthält, ist der Wert "None".
RegistryPaths | Array[string] | Registrierungsbeweis, dass das Produkt auf dem Gerät installiert ist.
SoftwareFirstSeenTimestamp | string | Das erste Mal, dass diese Software auf dem Gerät angezeigt wurde.
SoftwareName | string | Name des Softwareprodukts.
SoftwareVendor | string | Name des Softwareanbieters.
SoftwareVersion | string | Versionsnummer des Softwareprodukts.

### <a name="23-properties-via-files"></a>2.3 Eigenschaften (über Dateien)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\] | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.
GeneratedTime | string | Der Zeitpunkt, zu dem der Export generiert wurde.

## <a name="3-export-software-vulnerabilities-assessment-per-device"></a>3. Export software vulnerabilities assessment per device

Gibt alle bekannten Sicherheitsrisiken auf einem Gerät und deren Details für alle Geräte zurück.

### <a name="31-methods"></a>3.1-Methoden

Methode | Datentyp | Beschreibung
:---|:---|:---
[Export software vulnerabilities assessment (OData)](get-assessmnt-software-vulnerabilities.md#1-export-software-vulnerabilities-assessment-odata) | Untersuchungssammlung Siehe: [3.2 Properties (OData)](#32-properties-odata) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId zurück. Die erfassten Daten (für _OData_ oder über Dateien _)_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten. Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.
[Export software vulnerabilities assessment (via files)](get-assessmnt-software-vulnerabilities.md#2-export-software-vulnerabilities-assessment-via-files) | Untersuchungsentität Siehe: [3.3 Eigenschaften (über Dateien)](#33-properties-via-files) | Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId zurück. Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100K-Geräten empfohlen. Diese API verwendet alle Daten in Ihrer Organisation als Downloaddateien. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen: 1.  Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten zu erhalten. 2.  Laden Sie alle Dateien mithilfe der URLs zum Herunterladen herunter, und verarbeiten Sie die Daten nach Ben.

### <a name="32-properties-odata"></a>3.2 Properties (OData)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
CveId | string | Eindeutige ID, die der Sicherheitslücke unter dem System für häufige Sicherheitsrisiken und -risiken (Common Vulnerabilities and Exposures, CVE) zugewiesen ist.
CvssScore | string | Die CVSS-Bewertung des CVE.
DeviceId | string | Eindeutige ID für das Gerät im Dienst.
DeviceName | string | Vollqualifizierter Domänenname (FQDN) des Geräts.
DiskPaths | \[Arrayzeichenfolge\] | Datenträgerbeweis, dass das Produkt auf dem Gerät installiert ist.
ExploitabilityLevel | string | Die Ausnutzungsebene dieser Sicherheitsanfälligkeit (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | string | Das erste Mal, dass der CVE dieses Produkts auf dem Gerät angezeigt wurde.
Id | string | Eindeutige ID für den Datensatz.
LastSeenTimestamp | string | Das letzte Mal, dass der CVE auf dem Gerät angezeigt wurde.
OSPlatform | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Weitere Informationen finden Sie unter tvm supported operating systems and platforms.
RbacGroupName | string | Die rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keinem RBAC-Gruppen zugewiesen ist, wird der Wert "Nicht zugewiesen" angezeigt. Wenn die Organisation keine RBAC-Gruppen enthält, ist der Wert "None".
RecommendationReference | string | Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.
RecommendedSecurityUpdate | string | Name oder Beschreibung des Sicherheitsupdates, das vom Softwareanbieter bereitgestellt wird, um die Sicherheitslücke zu bean standen.
RecommendedSecurityUpdateId | string | Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel
Arrayzeichenfolge für \[ Registrierungspfade\] | Registrierungsbeweis, dass das Produkt auf dem Gerät installiert ist.
SoftwareName | string | Name des Softwareprodukts.
SoftwareVendor | string | Name des Softwareanbieters.
SoftwareVersion | string | Versionsnummer des Softwareprodukts.
VulnerabilitySeverityLevel | string | Schweregrad, der der Sicherheitslücke zugewiesen ist, basierend auf der CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden.

### <a name="33-properties-via-files"></a>3.3 Eigenschaften (über Dateien)

Eigenschaft (ID) | Datentyp | Beschreibung
:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\]  | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.
GeneratedTime | string | Der Zeitpunkt, zu dem der Export generiert wurde.

## <a name="see-also"></a>Siehe auch

- [Exportieren einer sicheren Konfigurationsbewertung pro Gerät](get-assessmnt-secure-cfg.md)

- [Exportieren der Softwareinventarbewertung pro Gerät](get-assessmnt-software-inventory.md)

- [Exportieren der Bewertung von Softwarerisiken pro Gerät](get-assessmnt-software-vulnerabilities.md)

Andere verwandte

- [Risikobasierte Bedrohungsrisiken & Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
