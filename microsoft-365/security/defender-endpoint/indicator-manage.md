---
title: Indikatoren verwalten
ms.reviewer: ''
description: 'Verwalten von Indikatoren für einen Dateihash, eine #A0, URLs oder Domänen, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.'
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185945"
---
# <a name="manage-indicators"></a>Indikatoren verwalten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Indikatoren aus.**

2. Wählen Sie die Registerkarte des Entitätstyps aus, den Sie verwalten möchten.  

3. Aktualisieren Sie die Details des Indikators, und klicken Sie auf **Speichern** oder klicken Sie auf die Schaltfläche Löschen, wenn Sie die Entität aus der Liste entfernen möchten. 

## <a name="import-a-list-of-iocs"></a>Importieren einer Liste von IoCs

Sie können auch eine CSV-Datei hochladen, die die Attribute von Indikatoren, die zu ergreifende Aktion und andere Details definiert.

Laden Sie die Beispiel-CSV herunter, um die unterstützten Spaltenattribute zu kennen.

1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Indikatoren aus.**

2. Wählen Sie die Registerkarte des Entitätstyps aus, für den Sie Indikatoren importieren möchten.

3. Wählen **Sie Datei** importieren  >  **aus.** 

4. Wählen Sie **Importieren** aus. Tun Sie dies für alle Dateien, die Sie importieren möchten. 

5. Wählen Sie **Fertig** aus.

In der folgenden Tabelle sind die unterstützten Parameter aufgeführt.

Parameter | Typ    |   Beschreibung
:---|:---|:---
indicatorType | Enum | Typ des Indikators. Mögliche Werte sind: "FileSha1", "FileSha256", "IpAddress", "DomainName" und "Url". **Required**
indicatorValue | String | Identität der [Indicator-Entität.](ti-indicator.md) **Required**
Aktion | Enum | Die Aktion, die ergriffen wird, wenn der Indikator in der Organisation ermittelt wird. Mögliche Werte sind: "Alert", "AlertAndBlock" und "Allowed". **Required**
title | String | Titel der Warnung des Indikators. **Required**
description | String |  Beschreibung des Indikators. **Required**
expirationTime | DateTimeOffset | Die Ablaufzeit des Indikators im folgenden Format YYYY-MM-DDTHH:MM:SS.0Z. **Optional**
Schweregrad | Enum | Der Schweregrad des Indikators. Mögliche Werte sind: "Informational", "Low", "Medium" und "High". **Optional**
recommendedActions | String | Empfohlene Aktionen zur Warnung des TI-Indikators. **Optional**
rbacGroupNames | String | Durch Kommas getrennte Liste der RBAC-Gruppennamen, auf die der Indikator angewendet werden soll. **Optional**
category | String | Die Kategorie der Warnung. Beispiele: Ausführung und Zugriff auf Anmeldeinformationen. **Optional**
mitretechniques| String | CODE/ID der MITRE-Techniken (durch Komma getrennt). Weitere Informationen finden Sie unter [Enterprise Taktik](https://attack.mitre.org/tactics/enterprise/). **Optional** Es wird empfohlen, bei einer MITRE-Technik einen Wert in der Kategorie hinzuzufügen.

Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).


## <a name="see-also"></a>Siehe auch
- [Indikatoren erstellen](manage-indicators.md)
- [Erstellen von Indikatoren für Dateien](indicator-file.md)
- [Erstellen von Indikatoren für IPs und URLs/Domänen](indicator-ip-domain.md)
- [Erstellen von Indikatoren basierend auf Zertifikaten](indicator-certificates.md)
