---
title: Beheben von Sicherheitsrisiken mit Bedrohungs- und Sicherheitsrisikomanagement
description: Beheben Von Sicherheitsschwächen, die durch Sicherheitsempfehlungen erkannt werden, und Erstellen von Ausnahmen bei Bedarf in Bedrohungs- und Sicherheitsrisikomanagement.
keywords: Microsoft Defender für Endpunkt-TVM-Wartung, Microsoft Defender für Endpunkt-TVM, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs-& Sicherheitsrisikomanagement, Bedrohungs-& Sicherheitsrisikomanagement-Wartung, TVM-Wartungs-Intune, TVM-Korrektur sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 602a38d8ad27505e81628db265681ac89218e593
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840911"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a>Beheben von Sicherheitsrisiken mit Bedrohungs- und Sicherheitsrisikomanagement

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohung und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a>Korrektur anfordern

Die Bedrohungs- und Sicherheitsrisikomanagement-Funktion in Microsoft Defender für Endpunkt schließt die Lücke zwischen Sicherheits- und IT-Administratoren über den Korrekturanforderungsworkflow. Sicherheitsadministratoren wie Sie können anfordern, dass der IT-Administrator eine Sicherheitslücke von den **Sicherheitsempfehlungen** an Intune behebt.

### <a name="enable-microsoft-intune-connection"></a>Aktivieren Microsoft Intune Verbindung

Um diese Funktion zu verwenden, aktivieren Sie Ihre Microsoft Intune Verbindungen. Navigieren Sie im Microsoft Defender Security Center zu **Einstellungen**  >  **Allgemeinen**  >  **erweiterten Features.** Scrollen Sie nach unten, und suchen Sie **nach Microsoft Intune Verbindung.** Standardmäßig ist die Umschaltfläche deaktiviert. Schalten Sie die **Microsoft Intune Verbindungsschaltfläche** **ein.**

**Hinweis:** Wenn Sie die Intune-Verbindung aktiviert haben, erhalten Sie eine Option zum Erstellen einer Intune-Sicherheitsaufgabe beim Erstellen einer Wartungsanforderung. Diese Option wird nicht angezeigt, wenn die Verbindung nicht festgelegt ist.

Weitere Informationen finden Sie unter ["Verwenden von Intune zum Beheben von Von Microsoft Defender für Endpunkt identifizierten Sicherheitsrisiken".](/intune/atp-manage-vulnerabilities)

### <a name="remediation-request-steps"></a>Schritte zur Korrekturanforderung

1. Wechseln Sie im Microsoft Defender Security Center zum navigationsmenü Bedrohungs- und Sicherheitsrisikomanagement, und wählen Sie [**Sicherheitsempfehlungen aus.**](tvm-security-recommendation.md)

2. Wählen Sie eine Sicherheitsempfehlung aus, für die Sie eine Korrektur anfordern möchten, und wählen Sie dann **Korrekturoptionen** aus.

3. Füllen Sie das Formular aus, einschließlich der Informationen, für die Sie eine Korrektur anfordern, zutreffender Gerätegruppen, Priorität, Fälligkeitsdatum und optionaler Hinweise.
    1. Wenn Sie die Korrekturoption "Achtung erforderlich" auswählen, ist die Auswahl eines Fälligkeitsdatums nicht verfügbar, da keine bestimmte Aktion vorhanden ist.

4. Wählen Sie **"Anforderung senden"** aus. Durch das Senden einer Korrekturanforderung wird innerhalb Bedrohungs- und Sicherheitsrisikomanagement ein Wartungsaktivitätselement erstellt, das zum Überwachen des Wartungsfortschritts für diese Empfehlung verwendet werden kann. Dies löst keine Korrektur aus oder wendet keine Änderungen auf Geräte an.

5. Benachrichtigen Sie Ihren IT-Administrator über die neue Anforderung, und lassen Sie ihn sich bei Intune anmelden, um die Anforderung zu genehmigen oder abzulehnen und eine Paketbereitstellung zu starten.

6. Wechseln Sie zur Seite [**"Korrektur",**](tvm-remediation.md) um den Status Ihrer Korrekturanfrage anzuzeigen.

Wenn Sie überprüfen möchten, wie das Ticket in Intune angezeigt wird, finden Sie weitere Informationen unter [Verwenden von Intune zum Beheben von Sicherheitsrisiken,](/intune/atp-manage-vulnerabilities) die von Microsoft Defender für Endpunkt identifiziert wurden.

>[!NOTE]
>Wenn Ihre Anforderung die Behebung von mehr als 10.000 Geräten umfasst, können wir nur 10.000 Geräte zur Behebung an Intune senden.

Nachdem die Cybersicherheitsschwächen Ihrer Organisation identifiziert und umsetzbaren [Sicherheitsempfehlungen](tvm-security-recommendation.md)zugeordnet wurden, beginnen Sie mit der Erstellung von Sicherheitsaufgaben. Sie können Aufgaben durch die Integration in Microsoft Intune erstellen, in denen Wartungstickets erstellt werden.

Verringern Sie die Gefährdung Ihrer Organisation durch Sicherheitsrisiken, und erhöhen Sie Ihre Sicherheitskonfiguration, indem Sie die Sicherheitsempfehlungen korrigieren.

## <a name="view-your-remediation-activities"></a>Anzeigen Ihrer Korrekturaktivitäten

Wenn Sie eine Korrekturanforderung von der Seite "Sicherheitsempfehlungen" übermitteln, wird eine Korrekturaktivität gestartet. Eine Sicherheitsaufgabe wird erstellt, die auf der Seite Bedrohungs- und Sicherheitsrisikomanagement **Korrektur** nachverfolgt werden kann, und ein Wartungsticket wird in Microsoft Intune erstellt.

Wenn Sie die Korrekturoption "Aufmerksamkeit erforderlich" ausgewählt haben, gibt es keine Statusanzeige, keinen Ticketstatus oder kein Fälligkeitsdatum, da keine tatsächliche Aktion vorhanden ist, die wir überwachen können.

Sobald Sie sich auf der Seite "Korrektur" befinden, wählen Sie die Korrekturaktivität aus, die Sie anzeigen möchten. Sie können die Korrekturschritte ausführen, den Fortschritt nachverfolgen, die zugehörige Empfehlung anzeigen, in CSV exportieren oder als abgeschlossen markieren.
![Beispiel für die Seite "Korrektur" mit einer ausgewählten Korrekturaktivität und dem Flyout dieser Aktivität, in dem die Beschreibung, IT-Dienst- und Geräteverwaltungstools sowie der Fortschritt der Gerätebehebung aufgeführt sind.](images/remediation_flyouteolsw.png)

>[!NOTE]
> Es gibt einen Aufbewahrungszeitraum von 180 Tagen für abgeschlossene Korrekturaktivitäten. Damit die Seite "Korrektur" optimal ausgeführt wird, wird die Korrekturaktivität 6 Monate nach abschluss entfernt.

### <a name="completed-by-column"></a>Abgeschlossen nach Spalte

Verfolgen Sie, wer die Korrekturaktivität mit der Spalte "Abgeschlossen von" auf der Seite "Korrektur" geschlossen hat.

- **E-Mail-Adresse:** Die E-Mail-Adresse der Person, die die Aufgabe manuell abgeschlossen hat
- **Systembestätigung:** Die Aufgabe wurde automatisch abgeschlossen (alle Geräte behoben)
- **Nicht** verfügbar: Informationen sind nicht verfügbar, da wir nicht wissen, wie diese ältere Aufgabe abgeschlossen wurde

![Wird von Spalten mit zwei Zeilen erstellt und abgeschlossen. Eine Zeile für "Abgeschlossen durch" weist ein Beispiel für eine E-Mail auf, die andere Zeile gibt die Systembestätigung an.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a>Wichtigste Wartungsaktivitäten im Dashboard

Zeigen Sie die **wichtigsten Wartungsaktivitäten** im [Bedrohungs- und Sicherheitsrisikomanagement-Dashboard](tvm-dashboard-insights.md)an. Wählen Sie einen der Einträge aus, um zur Seite **"Korrektur"** zu wechseln. Sie können die Korrekturaktivität als abgeschlossen markieren, nachdem das IT-Administratorteam die Aufgabe behoben hat.

![Beispiel für karte top remediation activities with a table that lists top activities that were generated from security recommendations.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Bedrohungen und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Sicherheitsempfehlungen](tvm-security-recommendation.md)