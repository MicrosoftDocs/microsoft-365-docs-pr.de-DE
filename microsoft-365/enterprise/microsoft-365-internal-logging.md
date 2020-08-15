---
title: Microsoft 365-interne Protokollierung für Microsoft 365 Engineering
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie eine Erläuterung der Funktionsweise der internen Protokollierung für Microsoft 365-Entwicklungsteams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b4c4b1db876a6b68ec852adbbd51afe7386a1855
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695991"
---
# <a name="internal-logging-for-microsoft-365-engineering"></a>Interne Protokollierung für Microsoft 365 Engineering

Zusätzlich zu den für Kunden verfügbaren Ereignissen und Protokolldaten gibt es auch ein internes Protokoll Datenerfassungssystem, das Microsoft 365-Ingenieuren bei Microsoft zur Verfügung steht. Viele verschiedene Typen von Protokolldaten werden von Microsoft 365-Servern in einen internen, großen Daten Datenverarbeitungsdienst mit dem Namen Cosmos hochgeladen. Jedes Service Team lädt Überwachungsprotokolle von den jeweiligen Servern in die Cosmos-Datenbank für Aggregation und Analyse hoch. Diese Datenübertragung erfolgt über eine FIPS 140-2-validierte TLS-Verbindung auf speziell genehmigten Ports und Protokollen mithilfe eines proprietären Automatisierungstools namens Office Data Loader (ODL). Die in Microsoft 365 zum Erfassen und Verarbeiten von Überwachungsdatensätzen verwendeten Tools ermöglichen keine permanenten oder irreversiblen Änderungen am ursprünglichen Inhalt oder der Zeitreihenfolge des Überwachungseintrags.

Service Teams verwenden Cosmos als zentrales Repository, um eine Analyse der Anwendungsnutzung, zur Messung der System-und Betriebsleistung und zur Ermittlung von Anomalien und Mustern zu suchen, die auf Probleme oder Sicherheitsprobleme hindeuten können. Jedes Dienst Team lädt eine Baseline von Protokollen in Cosmos, je nachdem, was Sie analysieren möchten, die häufig Folgendes umfassen:

- Ereignisprotokolle
- AppLocker-Protokolle
- Leistungsdaten
- System Center-Daten
- Anruf Detaildatensätze
- Quality of Experience-Daten
- IIS-Webserverprotokolle
- SQL Server Protokolle
- Syslog-Daten
- Sicherheitsüberwachungsprotokolle

Vor dem Hochladen von Daten in Cosmos verwendet die ODL-Anwendung einen Scrubbing-Dienst, um alle Felder zu verbergen, die Kundendaten enthalten, beispielsweise Mandanteninformationen und benutzerbezogene Informationen, und diese Felder durch einen Hashwert ersetzen. Die anonymisierten und gehashten Protokolle werden umgeschrieben und dann in Cosmos hochgeladen. Dienst Teams führen bereichsbezogene Abfragen mit Ihren Daten in Cosmos für Korrelation, Warnungen und Berichterstellung aus. Der Zeitraum für die Aufbewahrung von Überwachungsprotokolldaten in Cosmos wird von den Service Teams bestimmt. die meisten Überwachungsprotokolldaten werden für 90 Tage oder länger aufbewahrt, um Sicherheitsvorfälle zu unterstützen und behördliche Aufbewahrungsanforderungen zu erfüllen.

Der Zugriff auf Microsoft 365-Daten, die in Cosmos gespeichert sind, ist auf autorisiertes Personal beschränkt. Microsoft schränkt die Verwaltung der Überwachungsfunktionen auf die beschränkte Teilmenge der Dienst Teammitglieder ein, die für die Überwachungsfunktionen zuständig sind. Diese Teammitglieder haben nicht die Möglichkeit, Daten aus dem Kosmos zu ändern oder zu löschen, und alle Änderungen an den Protokollierungsmechanismen für Cosmos werden aufgezeichnet und überwacht.

Jedes Dienst Team greift zur Analyse auf seine Protokolldaten zu, indem es bestimmte Anwendungen zum Durchführen einer bestimmten Analyse autorisiert. Beispielsweise verwendet das Microsoft 365-Sicherheitsteam Daten aus dem Kosmos über einen proprietären Ereignisprotokoll Parser zum korrelieren, warnen und Generieren von Berichten mit Aktionen für mögliche verdächtige Aktivitäten in der Microsoft 365-Produktionsumgebung. Die Berichte aus diesen Daten werden verwendet, um Sicherheitsrisiken zu beheben und die Gesamtleistung des Diensts zu verbessern. Wenn für eine bestimmte Warnung oder einen bestimmten Bericht weitere Untersuchungen erforderlich sind, können Dienstmitarbeiter anfordern, dass die Daten wieder in den Microsoft 365-Dienst importiert werden. Da das spezifische Protokoll, das aus Cosmos importiert wird, verschlüsselt ist und Servicemitarbeiter keinen Zugriff auf Entschlüsselungsschlüssel haben, wird das Zielprotokoll programmgesteuert über einen Entschlüsselungs Dienst übergeben, der bereichsbezogene Ergebnisse an die autorisierten Dienstmitarbeiter zurückgibt. Alle Sicherheitsanfälligkeiten aus dieser Übung werden mithilfe der standardmäßigen Management Kanäle für Sicherheitsvorfälle von Microsoft gemeldet und eskaliert.
