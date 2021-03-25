---
title: Behebung von Sicherheitsrisiken mit Bedrohungs- und Sicherheitsrisikoverwaltung
description: Beheben von Sicherheitslücken, die durch Sicherheitsempfehlungen entdeckt wurden, und bei Bedarf Ausnahmen bei der Bedrohungs- und Sicherheitsrisikoverwaltung.
keywords: microsoft defender atp tvm remediation, mdatp tvm, threat and vulnerability management, threat & vulnerability management, threat & vulnerability management remediation, tvm remediation intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0a0f70d81c3060f14f917cac49851af2e9dae210
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068687"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a>Behebung von Sicherheitsrisiken mit Bedrohungs- und Sicherheitsrisikoverwaltung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a>Anforderungsbehebung

Die Bedrohungs- und Sicherheitsrisikoverwaltungsfunktion in Microsoft Defender for Endpoint überbrückt die Lücke zwischen Sicherheits- und IT-Administratoren über den Workflow zur Behebungsanforderung. Sicherheitsadministratoren wie Sie können den IT-Administrator bitten, eine  Sicherheitslücke von den Sicherheitsempfehlungsseiten auf Intune zu be behebung.

### <a name="enable-microsoft-intune-connection"></a>Aktivieren der Microsoft Intune-Verbindung

Um diese Funktion zu verwenden, aktivieren Sie Ihre Microsoft Intune-Verbindungen. Navigieren Sie im Microsoft Defender Security Center zu **Einstellungen**  >  **Allgemeine erweiterte**  >  **Features**. Scrollen Sie nach unten, und suchen **Sie nach Microsoft Intune-Verbindung.** Standardmäßig ist der Umschalter deaktiviert. Schalten Sie **Ihre Microsoft Intune-Verbindung** **ein.**

**Hinweis:** Wenn Sie die Intune-Verbindung aktiviert haben, erhalten Sie eine Option zum Erstellen einer Intune-Sicherheitsaufgabe beim Erstellen einer Korrekturanforderung. Diese Option wird nicht angezeigt, wenn die Verbindung nicht festgelegt ist.

Weitere [Informationen finden Sie unter Verwenden](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) von Intune zur Behebung von von Microsoft Defender for Endpoint identifizierten Sicherheitsrisiken.

### <a name="remediation-request-steps"></a>Schritte zur Behebungsanforderung

1. Wechseln Sie zum Navigationsmenü zur Bedrohungs- und Sicherheitsrisikoverwaltung im Microsoft Defender Security Center, und wählen Sie [**Sicherheitsempfehlungen aus.**](tvm-security-recommendation.md)

2. Wählen Sie eine Sicherheitsempfehlung aus, für die Sie eine Korrektur anfordern möchten, und wählen Sie dann **Korrekturoptionen aus.**

3. Füllen Sie das Formular aus, einschließlich der Informationen, für die Sie eine Korrektur anfordern, anwendbare Gerätegruppen, Priorität, Fälligkeitsdatum und optionale Notizen.
    1. Wenn Sie die Option "Aufmerksamkeit erforderlich" auswählen, ist die Auswahl eines Fälligkeitsdatums nicht verfügbar, da keine bestimmte Aktion vorhanden ist.

4. Wählen **Sie Anforderung übermitteln aus.** Durch das Übermitteln einer Korrekturanforderung wird ein Problembehebungsaktivitätselement innerhalb der Bedrohungs- und Sicherheitsrisikoverwaltung erstellt, das zum Überwachen des Behebungsfortschritts für diese Empfehlung verwendet werden kann. Dadurch wird keine Korrektur ausgelöst oder Änderungen auf Geräten angewendet.

5. Benachrichtigen Sie Ihren IT-Administrator über die neue Anforderung, und lassen Sie sie sich bei Intune anmelden, um die Anforderung zu genehmigen oder abzulehnen und eine Paketbereitstellung zu starten.

6. Wechseln Sie zur [**Seite Korrektur,**](tvm-remediation.md) um den Status Ihrer Behebungsanforderung zu sehen.

Wenn Sie überprüfen möchten, wie das Ticket in Intune angezeigt wird, finden Sie weitere Informationen unter Verwenden von Intune zur Behebung von von [Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) identifizierten Sicherheitsrisiken.

>[!NOTE]
>Wenn Ihre Anforderung die Behebung von mehr als 10.000 Geräten umfasst, können wir nur 10.000 Geräte zur Behebung an Intune senden.

Nachdem die Cybersicherheitsschwächen Ihrer Organisation identifiziert und den Empfehlungen für umsetzbare Sicherheit zugeordnet [wurden,](tvm-security-recommendation.md)beginnen Sie mit dem Erstellen von Sicherheitsaufgaben. Sie können Aufgaben über die Integration mit Microsoft Intune erstellen, in der Wartungstickets erstellt werden.

Verringern Sie die Gefährdung Ihrer Organisation durch Sicherheitsrisiken, und erhöhen Sie Ihre Sicherheitskonfiguration, indem Sie die Sicherheitsempfehlungen abstellen.

## <a name="view-your-remediation-activities"></a>Anzeigen Ihrer Korrekturaktivitäten

Wenn Sie eine Behebungsanforderung von der Seite Sicherheitsempfehlungen übermitteln, wird eine Korrekturaktivität ins Jahr 2013 starten. Es wird eine Sicherheitsaufgabe erstellt, die auf der  Seite Zur Behebung von Bedrohungen und Sicherheitsrisiken nachverfolgt werden kann, und in Microsoft Intune wird ein Behebungsticket erstellt.

Wenn Sie die Option "Aufmerksamkeit erforderlich" ausgewählt haben, gibt es keine Statusanzeige, keinen Ticketstatus oder kein Fälligkeitsdatum, da es keine tatsächliche Aktion gibt, die wir überwachen können.

Sobald Sie sich auf der Seite Korrektur befinden, wählen Sie die Korrekturaktivität aus, die Sie anzeigen möchten. Sie können die Korrekturschritte ausführen, den Fortschritt nachverfolgen, die zugehörige Empfehlung anzeigen, in CSV exportieren oder als abgeschlossen markieren.
![Beispiel für die Seite "Korrektur" mit einer ausgewählten Korrekturaktivität und dem Flyout dieser Aktivität, in dem die Beschreibung, die IT-Dienst- und Geräteverwaltungstools sowie der Fortschritt der Gerätebehebung auflistet werden.](images/remediation_flyouteolsw.png)

>[!NOTE]
> Es gibt einen Aufbewahrungszeitraum von 180 Tage für abgeschlossene Korrekturaktivitäten. Damit die Korrekturseite optimal funktioniert, wird die Behebungsaktivität 6 Monate nach abschluss entfernt.

### <a name="completed-by-column"></a>Nach Spalte abgeschlossen

Verfolgen Sie, wer die Korrekturaktivität mit der Spalte "Abgeschlossen von" auf der Seite Korrektur geschlossen hat.

- **E-Mail-Adresse**: Die E-Mail der Person, die die Aufgabe manuell abgeschlossen hat
- **Systembestätigung**: Die Aufgabe wurde automatisch abgeschlossen (alle Geräte wurden behoben)
- **N/A**: Informationen sind nicht verfügbar, da wir nicht wissen, wie diese ältere Aufgabe abgeschlossen wurde.

![Erstellt von und wird von Spalten mit zwei Zeilen abgeschlossen. Eine Zeile für completed by hat ein Beispiel für eine E-Mail, die andere Zeile die Systembestätigung.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a>Die obersten Korrekturaktivitäten im Dashboard

Sehen **Sie sich im** Dashboard für die Verwaltung von Bedrohungen und Sicherheitslücken die aktivitäten zur Behebung von Bedrohungen und [Sicherheitslücken an.](tvm-dashboard-insights.md) Wählen Sie einen der Einträge aus, die zur Seite **Korrektur wechseln.** Sie können die Korrekturaktivität als abgeschlossen markieren, nachdem das IT-Administratorteam die Aufgabe behoben hat.

![Beispiel für die Karte "Top remediation activities" mit einer Tabelle, in der die top Aktivitäten aufgeführt sind, die aus Sicherheitsempfehlungen generiert wurden.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Sicherheitsempfehlungen](tvm-security-recommendation.md)