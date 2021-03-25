---
title: Anzeigen und Organisieren der Microsoft Defender ATP-Geräteliste
description: Erfahren Sie mehr über die verfügbaren Features, die Sie in der Liste Geräte verwenden können, z. B. Sortieren, Filtern und Exportieren der Liste, um Untersuchungen zu verbessern.
keywords: sort, filter, export, csv, device name, domain, last seen, internal IP, health state, active alerts, active malware detections, threat category, review alerts, network, connection, malware, type, password stealer, ransomware, exploit, threat, general malware, unwanted software
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
ms.openlocfilehash: 9068983b5f61305b1f3da4d076e99e71974e8df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185671"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a>Anzeigen und Organisieren der Microsoft Defender for Endpoint Devices-Liste

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


Die **Liste Geräte** enthält eine Liste der Geräte in Ihrem Netzwerk, auf denen Warnungen generiert wurden. Standardmäßig werden in der Warteschlange Geräte angezeigt, die in den letzten 30 Tagen angezeigt wurden.  

Auf einen Blick werden Informationen wie Domäne, Risikostufe, Betriebssystemplattform und andere Details zur einfachen Identifizierung der am stärksten gefährdeten Geräte angezeigt.

Es stehen mehrere Optionen zur Verfügung, um die Gerätelistenansicht anzupassen. Im oberen Navigationsbereich können Sie:

- Hinzufügen oder Entfernen von Spalten
- Exportieren der gesamten Liste im CSV-Format
- Auswählen der Anzahl der Elemente, die pro Seite angezeigt werden soll
- Anwenden von Filtern

Während des Onboardingprozesses wird die **Liste Geräte** schrittweise mit Geräten aufgefüllt, wenn sie beginnen, Sensordaten zu melden. Verwenden Sie diese Ansicht, um Ihre integrierten Endpunkte zu verfolgen, während sie online sind, oder laden Sie die vollständige Endpunktliste als CSV-Datei für die Offlineanalyse herunter.

>[!NOTE]
> Wenn Sie die Geräteliste exportieren, enthält sie jedes Gerät in Ihrer Organisation. Je nachdem, wie groß Ihre Organisation ist, kann es sehr viel Zeit zum Herunterladen dauern. Beim Exportieren der Liste im CSV-Format werden die Daten ungefiltert angezeigt. Die CSV-Datei enthält alle Geräte in der Organisation, unabhängig davon, ob die Filterung in der Ansicht selbst angewendet wird.

![Abbildung der Geräteliste mit Liste der Geräte](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a>Sortieren und Filtern der Geräteliste

Sie können die folgenden Filter anwenden, um die Liste der Warnungen zu beschränken und eine fokussierte Ansicht zu erhalten.

### <a name="risk-level"></a>Risikostufe

Die Risikostufe spiegelt die allgemeine Risikobewertung des Geräts basierend auf einer Kombination von Faktoren wider, einschließlich der Typen und des Schweregrads aktiver Warnungen auf dem Gerät. Das Auflösen aktiver Warnungen, das Genehmigen von Korrekturaktivitäten und das Unterdrücken nachfolgender Warnungen können die Risikostufe senken.

### <a name="exposure-level"></a>Belichtungsstufe

Die Belichtungsstufe spiegelt die aktuelle Belichtung des Geräts basierend auf den kumulativen Auswirkungen der ausstehenden Sicherheitsempfehlungen wider. Die möglichen Ebenen sind niedrig, mittel und hoch. Niedrige Belichtung bedeutet, dass Ihre Geräte weniger anfällig für die Nutzung sind.

Wenn die Risikostufe "Keine Daten verfügbar" ausdingt, gibt es einige Gründe, warum dies der Fall sein kann:

- Gerät hat die Berichterstellung für mehr als 30 Tage beendet – in diesem Fall gilt es als inaktiv, und die Belichtung wird nicht berechnet.
- Gerätebetriebssystem nicht unterstützt – siehe [Mindestanforderungen für Microsoft Defender for Endpoint](minimum-requirements.md)
- Gerät mit veralteten Agents (sehr unwahrscheinlich)

### <a name="os-platform"></a>Betriebssystemplattform

Wählen Sie nur die Betriebssystemplattformen aus, die Sie untersuchen möchten.

### <a name="health-state"></a>Integritätsstatus

Filtern sie nach den folgenden Geräteintehzustandszuständen:

- **Aktiv** – Geräte, die aktiv Sensordaten an den Dienst melden.
- **Inaktiv** – Geräte, die das Senden von Signalen für mehr als 7 Tage vollständig beendet haben.
- **Falsch konfiguriert –** Geräte, die die Kommunikation mit dem Dienst beeinträchtigt haben oder keine Sensordaten senden können. Falsch konfigurierte Geräte können weiter wie folgt klassifiziert werden:
  - Keine Sensordaten
  - Beeinträchtigte Kommunikation

  Weitere Informationen zum Beheben von Problemen auf falsch konfigurierten Geräten finden Sie unter [Fix unhealthy sensors](fix-unhealthy-sensors.md).

### <a name="antivirus-status"></a>Antivirusstatus

Filtern Von Geräten nach Antivirusstatus. Gilt nur für aktive Windows 10-Geräte.

- **Deaktiviert** – & Schutz vor Bedrohungen ist deaktiviert.
- **Keine Berichterstellung** – Virenschutz & wird nicht berichtet.
- **Nicht aktualisiert** – Virenschutz & bedrohungsschutz ist nicht auf dem neuesten Stand.

Weitere Informationen finden Sie unter [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).

### <a name="threat-mitigation-status"></a>Status der Bedrohungsminderung

Um Geräte anzuzeigen, die möglicherweise von einer bestimmten Bedrohung betroffen sind, wählen Sie die Bedrohung im Dropdownmenü aus, und wählen Sie dann aus, welcher Sicherheitsrisikoaspekt abgemildert werden muss.

Weitere Informationen zu bestimmten Bedrohungen finden Sie unter [Threat analytics](threat-analytics.md). Informationen zur Risikominderung finden Sie unter [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).

### <a name="windows-10-version"></a>Windows 10-Version

Wählen Sie nur die Windows 10-Versionen aus, die Sie untersuchen möchten.

### <a name="tags--groups"></a>Tags & Gruppen

Filtern Sie die Liste basierend auf der Gruppierung und Kennzeichnung, die Sie einzelnen Geräten hinzugefügt haben. Weitere [Informationen finden Sie unter Erstellen und Verwalten von Gerätetags](machine-tags.md) und Erstellen und Verwalten von [Gerätegruppen.](machine-groups.md)

## <a name="related-topics"></a>Verwandte Themen

- [Untersuchen von Geräten in der Microsoft Defender for Endpoint Devices-Liste](investigate-machines.md)
