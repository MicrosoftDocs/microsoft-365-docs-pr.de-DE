---
title: Microsoft Defender Security Center Security Operations Dashboard
description: Verwenden Sie das Dashboard, um gefährdete Geräte zu identifizieren, den Status des Diensts zu verfolgen und Statistiken und Informationen zu Geräten und Warnungen anzuzeigen.
keywords: Dashboard, Warnungen, neu, in Bearbeitung, aufgelöst, Risiko, Gefährdete Geräte, Infektionen, Berichterstellung, Statistiken, Diagramme, Diagramme, Gesundheit, aktive Schadsoftwareerkennungen, Bedrohungskategorie, Kategorien, Kennwortdiebstahl, Ransomware, Exploit, Bedrohung, niedriger Schweregrad, aktive Schadsoftware
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064912"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a>Microsoft Defender Security Center Security Operations Dashboard

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

Im **Dashboard für Sicherheitsvorgänge** werden die Erkennungs- und Reaktionsfunktionen für Endpunkte angezeigt. Es bietet einen umfassenden Überblick darüber, wo Erkennungen angezeigt wurden, und hervorhebt, wo Reaktionsaktionen erforderlich sind. 

Das Dashboard zeigt eine Momentaufnahme von:

- Aktive Warnungen
- Gefährdete Geräte
- Sensorinte health
- Dienststatus
- Tägliche Geräteberichte
- Aktive automatisierte Untersuchungen
- Statistiken zu automatisierten Untersuchungen
- Gefährdete Benutzer
- Verdächtige Aktivitäten


![Abbildung des Dashboards für Sicherheitsvorgänge](images/atp-sec-ops-dashboard.png)

Sie können Warnungen und Geräte erkunden und untersuchen, um schnell zu ermitteln, ob, wo und wann verdächtige Aktivitäten in Ihrem Netzwerk aufgetreten sind, um den Kontext zu verstehen, in dem sie aufgetreten sind.

Im **Dashboard für Sicherheitsvorgänge** werden aggregierte Ereignisse angezeigt, um die Identifizierung wichtiger Ereignisse oder Verhaltensweisen auf einem Gerät zu erleichtern. Sie können auch detaillierte Informationen zu detaillierten Ereignissen und Indikatoren auf niedriger Ebene anzeigen.

Es verfügt auch über klickbare Kacheln, die visuelle Hinweise auf den allgemeinen Integritätsstatus Ihrer Organisation geben. Jede Kachel öffnet eine detaillierte Ansicht der entsprechenden Übersicht.

## <a name="active-alerts"></a>Aktive Warnungen
Sie können die Gesamtzahl der aktiven Warnungen aus den letzten 30 Tagen in Ihrem Netzwerk über die Kachel anzeigen. Warnungen werden in **Neu und** In **Bearbeitung gruppieren.**

![Klicken Sie auf jeden Datenschnitt oder Schweregrad, um eine Liste der Warnungen aus den letzten 30 Tagen anzuzeigen.](images/active-alerts-tile.png)

Jede Gruppe wird in die entsprechenden Warnungsschweregrade unter kategorisiert. Klicken Sie auf die Anzahl der Warnungen in den einzelnen Warnungsringen, um eine sortierte Ansicht der Warteschlange dieser Kategorie anzuzeigen (**Neu** oder **In Bearbeitung**).

Weitere Informationen finden Sie unter [Alerts overview](alerts-queue.md).

Jede Zeile enthält eine Kategorie für den Warnungsschweregrad und eine kurze Beschreibung der Warnung. Sie können auf eine Warnung klicken, um die detaillierte Ansicht zu sehen. Weitere Informationen finden Sie unter  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and Alerts [overview](alerts-queue.md).


## <a name="devices-at-risk"></a>Gefährdete Geräte
Diese Kachel zeigt eine Liste der Geräte mit der höchsten Anzahl aktiver Warnungen. Die Gesamtanzahl der Warnungen für jedes Gerät wird in einem Kreis neben dem Gerätenamen angezeigt und dann weiter nach Schweregraden am ende der Kachel kategorisiert (zeigen Sie auf jeden Schweregradbalken, um dessen Bezeichnung anzuzeigen).

![Die Kachel Geräte mit Risiken zeigt eine Liste der Geräte mit der höchsten Anzahl von Warnungen und eine Aufschlüsselung des Schweregrads der Warnungen an.](images/devices-at-risk-tile.png)

Klicken Sie auf den Namen des Geräts, um Details zu diesem Gerät anzuzeigen. Weitere Informationen finden Sie unter [Untersuchen von Geräten in der Liste Microsoft Defender for Endpoint Devices](investigate-machines.md).

Sie können auch oben auf **der** Kachel auf Geräteliste klicken, um direkt zur Geräteliste **zu** wechseln, sortiert nach der Anzahl der aktiven Warnungen. Weitere Informationen finden Sie unter [Untersuchen von Geräten in der Liste Microsoft Defender for Endpoint Devices](investigate-machines.md).

## <a name="devices-with-sensor-issues"></a>Geräte mit Sensorproblemen
Die **Kachel Geräte mit Sensorproblemen** enthält Informationen zur Fähigkeit des einzelnen Geräts, Sensordaten für den Microsoft Defender for Endpoint-Dienst zur Verfügung zu stellen. Es berichtet, wie viele Geräte Aufmerksamkeit erfordern und hilft Ihnen, problematische Geräte zu identifizieren.

![Geräte mit Einer Kachel mit Sensorproblemen](images/atp-tile-sensor-health.png)

Es gibt zwei Statusindikatoren, die Informationen zur Anzahl der Geräte bereitstellen, die dem Dienst nicht ordnungsgemäß melden:
- **Falsch konfiguriert –** Diese Geräte melden möglicherweise teilweise Sensordaten an den Microsoft Defender for Endpoint-Dienst und können Konfigurationsfehler haben, die korrigiert werden müssen.
- **Inaktiv** – Geräte, die die Berichterstellung an den Microsoft Defender for Endpoint-Dienst im letzten Monat für mehr als sieben Tage beendet haben.

Wenn Sie auf eine der Gruppen klicken, werden Sie zu der Geräteliste geleitet, die nach Ihrer Wahl gefiltert wird. Weitere Informationen finden Sie unter [Überprüfen des Sensorstatus und](check-sensor-status.md) Untersuchen von [Geräten](investigate-machines.md).

## <a name="service-health"></a>Dienststatus
Die **Kachel Dienstintehzustand** informiert Sie, ob der Dienst aktiv ist oder probleme auftreten.

![Die Kachel Dienstintehzustand zeigt einen allgemeinen Indikator des Diensts an.](images/status-tile.png)

Weitere Informationen zum Dienstzustand finden Sie unter [Überprüfen der Integrität des Microsoft Defender for Endpoint-Diensts](service-status.md).


## <a name="daily-devices-reporting"></a>Tägliche Geräteberichte
Die **Kachel Tägliche Gerätebericht** zeigt ein Balkendiagramm, das die Anzahl der Täglichen Berichte in den letzten 30 Tagen darstellt. Zeigen Sie auf einzelne Balken im Diagramm, um die genaue Anzahl der Geräte anzuzeigen, die jeden Tag berichten.

![Abbildung der Kachel für tägliche Geräteberichte](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a>Aktive automatisierte Untersuchungen
Sie können die Gesamtzahl der automatisierten Untersuchungen aus den letzten 30 Tagen in Ihrem Netzwerk auf der **Kachel Aktive automatisierte Untersuchungen** anzeigen. Untersuchungen werden in **ausstehende** Aktion, **Warten auf Gerät** und Ausführen **gruppieren.**

![Inmage von aktiven automatisierten Untersuchungen](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a>Statistiken zu automatisierten Untersuchungen
Diese Kachel zeigt Statistiken zu automatisierten Untersuchungen in den letzten sieben Tagen. Sie zeigt die Anzahl der abgeschlossenen Untersuchungen, die Anzahl der erfolgreich behobenen Untersuchungen, die durchschnittliche Ausstehendzeit für die Untersuchung, die durchschnittliche Zeit für die Behebung einer Warnung, die Anzahl der untersuchten Warnungen und die Anzahl der Stunden automatisierung, die bei einer typischen manuellen Untersuchung gespeichert wurden. 

![Abbildung der Statistiken zu automatisierten Untersuchungen](images/atp-automated-investigations-statistics.png)

Sie können auf **Automatisierte** **Untersuchungen,** Nachgefilterte Untersuchungen und  **untersuchte Warnungen** klicken, um zur Seite Untersuchungen zu navigieren, gefiltert nach der entsprechenden Kategorie. Auf diese Weise können Sie eine detaillierte Aufschlüsselung der Untersuchungen im Kontext sehen.

## <a name="users-at-risk"></a>Gefährdete Benutzer
Die Kachel zeigt eine Liste der Benutzerkonten mit den aktivsten Warnungen und der Anzahl der Warnungen, die bei hohen, mittleren oder niedrigen Warnungen angezeigt werden. 

![Die Kachel "Risikokonten" zeigt eine Liste der Benutzerkonten mit der höchsten Anzahl von Warnungen und eine Aufschlüsselung des Schweregrads der Warnungen an.](images/atp-users-at-risk.png)

Klicken Sie auf das Benutzerkonto, um Details zum Benutzerkonto anzuzeigen. Weitere Informationen finden Sie [unter Untersuchen eines Benutzerkontos](investigate-user.md).

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a>Verwandte Themen
- [Verstehen des Microsoft Defender for Endpoint-Portals](use.md)
- [Portalübersicht](portal-overview.md)
- [Anzeigen des Dashboards & Bedrohungsrisikoverwaltung](tvm-dashboard-insights.md)
- [Anzeigen des Dashboards für die Bedrohungsanalyse und Ergreifen empfohlener Gegenmaßnahmen](threat-analytics.md)
