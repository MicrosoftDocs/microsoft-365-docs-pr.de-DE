---
title: Untersuchen von Vorfällen in Microsoft 365 Defender
description: Untersuchen sie Vorfälle im Zusammenhang mit Geräten, Benutzern und Postfächern.
keywords: Incident, incidents, analyze, response, machines, devices, users, identities, mail, email, mailbox, investigation, graph, evidence
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fdfc065aea3549e99de72c968c0fa19412f9e246
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105356"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Untersuchen von Vorfällen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

Microsoft 365 Defender aggregiert alle zugehörigen Warnungen, Ressourcen, Untersuchungen und Nachweise aus Ihren Geräten, Benutzern und Postfächern zu einem Vorfall, um Ihnen einen umfassenden Überblick über die gesamte Breite eines Angriffs zu geben.

Innerhalb eines Vorfalls analysieren Sie die Warnungen, die sich auf Ihr Netzwerk auswirken, verstehen, was sie bedeuten, und sortieren die Nachweise, damit Sie einen effektiven Korrekturplan erstellen können.

## <a name="initial-investigation"></a>Anfängliche Untersuchung

Bevor Sie sich mit den Details befassen, sehen Sie sich die Eigenschaften und die Zusammenfassung des Vorfalls an.

Sie können beginnen, indem Sie den Vorfall in der Häkchenspalte auswählen. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Beispiel für die Auswahl eines Vorfalls in der Häkchenspalte":::

In diesem Fall wird ein Zusammenfassungsbereich mit wichtigen Informationen zu dem Vorfall geöffnet, z. B. dem Schweregrad, dem er zugewiesen ist, und dem [MITRE ATT&&trade; CK-Kategorien](https://attack.mitre.org/) für den Vorfall. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Beispiel für den Zusammenfassungsbereich für einen Vorfall":::

Von hier aus können Sie die **Seite "Vorfall öffnen"** auswählen. Dadurch wird die Hauptseite für den Vorfall geöffnet, auf der Sie weitere zusammenfassende Informationen und Registerkarten für Warnungen, Geräte, Benutzer, Untersuchungen und Nachweise finden.

Sie können auch die Hauptseite für einen Vorfall öffnen, indem Sie den Namen des Vorfalls aus der Vorfallwarteschlange auswählen.

## <a name="summary"></a>Zusammenfassung

Auf der **Zusammenfassungsseite** erhalten Sie einen Momentaufnahme-Blick auf die wichtigsten Punkte, die Sie über den Vorfall feststellen können.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Beispiel für die Seite &quot;Zusammenfassung&quot; für einen Vorfall im Microsoft 365 Security Center":::

Die Angriffskategorien geben Ihnen eine visuelle und numerische Übersicht darüber, wie fortgeschritten der Angriff gegen die Kill Chain fortgeschritten ist. Wie bei anderen Microsoft-Sicherheitsprodukten ist Microsoft 365 Defender auf das [MITRE ATT &trade;&CK-Framework](https://attack.mitre.org/) ausgerichtet.

Der Bereich enthält eine Liste der am häufigsten betroffenen Assets, die Teil dieses Vorfalls sind. Wenn es spezifische Informationen zu diesem Asset gibt, wie z. B. Risikograd, Untersuchungspriorität sowie eine Kennzeichnung des Assets, wird dies ebenfalls in diesem Abschnitt angezeigt.

Die Warnungszeitachse bietet einen kurzen Einblick in die chronologische Reihenfolge, in der die Warnungen aufgetreten sind, sowie die Gründe, warum diese Warnungen mit diesem Vorfall verknüpft sind.

Und schließlich – der Nachweisabschnitt enthält eine Zusammenfassung der Anzahl der verschiedenen Artefakte, die in den Vorfall einbezogen wurden, und deren Behebungsstatus, sodass Sie sofort erkennen können, ob eine Aktion von Ihnen erforderlich ist.

Diese Übersicht kann Ihnen bei der anfänglichen Triage des Vorfalls helfen, indem sie Einblicke in die wichtigsten Merkmale des Vorfalls bietet, die Sie kennen sollten.

## <a name="alerts"></a>Warnungen

Auf der Registerkarte **"Warnung"** können Sie die Warnungswarteschlange für Warnungen im Zusammenhang mit dem Vorfall und andere Informationen zu diesen anzeigen, z. B.:

- Schweregrad.
- Die Entitäten, die an der Warnung beteiligt waren.
- Die Quelle der Warnungen (Microsoft Defender for Identity, Microsoft Defender für Endpunkt, Microsoft Defender für Office 365).
- Der Grund, warum sie miteinander verknüpft wurden.

Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Beispiel für eine Seite &quot;Warnungen&quot; für einen Vorfall":::

Standardmäßig sind die Warnungen chronologisch sortiert, damit Sie sehen können, wie der Vorfall im Laufe der Zeit ausgespielt wurde. Wenn Sie eine Warnung innerhalb eines Vorfalls auswählen, zeigt Microsoft 365 Defender die spezifischen Warnungsinformationen für den Kontext des Gesamtvorfalls an. 

Sie können die Ereignisse der Warnung sehen, durch die andere ausgelöste Warnungen die aktuelle Warnung verursacht haben, sowie alle betroffenen Entitäten und Aktivitäten, die an dem Angriff beteiligt sind, einschließlich Dateien, Benutzern und Postfächern.

Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Beispiel für eine Seite mit Warnungsdetails innerhalb eines Vorfalls":::

Diese Vorfallwarnungsseite besteht aus den folgenden Abschnitten:

- Warnungsartikel, der eine Zusammenfassung der Ereignisse enthält
- Verwandte Ereignisse und Warnungen
- Zusammenfassungsdetails

Erfahren Sie, wie Sie die Warnungswarteschlange und die Warnungsseiten verwenden, um Warnungen zu [untersuchen.](investigate-alerts.md)

## <a name="devices"></a>Geräte

Auf der Registerkarte **"Geräte"** werden alle Geräte aufgelistet, die sich auf den Vorfall beziehen. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Beispiel für eine Seite &quot;Geräte&quot; für einen Vorfall":::

Sie können das Häkchen für ein Gerät aktivieren, um Details zu Gerät, Verzeichnisdaten, aktiven Warnungen und angemeldeten Benutzern anzuzeigen. Wählen Sie den Namen des Geräts aus, um Gerätedetails im Microsoft Defender für Endpunkte-Gerätebestand anzuzeigen.

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Beispiel für eine Geräteseite für Microsoft Defender für Endpunkte":::

Auf der Geräteseite können Sie zusätzliche Informationen über das Gerät sammeln, z. B. alle Warnungen, eine Zeitachse und Sicherheitsempfehlungen. Beispielsweise können Sie auf der Registerkarte **"Zeitachse"** einen Bildlauf durch die Computerzeitachse durchführen und alle auf dem Computer beobachteten Ereignisse und Verhaltensweisen in chronologischer Reihenfolge anzeigen, durchsetzt mit den ausgelösten Warnungen.

> [!TIP]
> Sie können Scans bei Bedarf auf einer Geräteseite durchführen. Wählen Sie im Microsoft 365 Security Center **Endpunkte > Gerätebestand** aus. Wählen Sie ein Gerät mit Warnungen aus, und führen Sie dann einen Antivirenscan aus. Aktionen, z. B. Antivirenscans, werden nachverfolgt und auf der **Gerätebestandsseite** angezeigt. Weitere Informationen finden Sie unter [Ausführen Microsoft Defender Antivirus Überprüfung auf Geräten.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)

## <a name="users"></a>Benutzer

Auf der Registerkarte **"Benutzer"** sind alle Benutzer aufgeführt, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Beispiel für eine Seite &quot;Benutzer&quot; für einen Vorfall":::

Sie können das Häkchen für einen Benutzer aktivieren, um Details zu Bedrohung, Gefährdung und Kontaktinformationen des Benutzerkontos anzuzeigen. Wählen Sie den Benutzernamen aus, um weitere Benutzerkontodetails anzuzeigen.

Erfahren Sie, wie Sie zusätzliche Benutzerinformationen anzeigen und die Benutzer eines Vorfalls bei der Untersuchung von [Benutzern](investigate-users.md)verwalten.


## <a name="mailboxes"></a>Postfächer

Auf der Registerkarte **"Postfächer"** werden alle Postfächer aufgelistet, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Beispiel für eine Seite &quot;Postfächer&quot; für einen Vorfall":::

Sie können das Häkchen für ein Postfach aktivieren, um eine Liste aktiver Warnungen anzuzeigen. Wählen Sie den Postfachnamen aus, um zusätzliche Postfachdetails auf der Explorer-Seite für Microsoft Defender für Office 365 anzuzeigen.

## <a name="investigations"></a>Untersuchungen

Die Registerkarte **"Untersuchungen"** listet alle [automatisierten Untersuchungen auf,](m365d-autoir.md) die durch Warnungen in diesem Vorfall ausgelöst werden. Die Untersuchungen führen Korrekturmaßnahmen aus oder warten auf die Genehmigung von Aktionen durch den Analysten, je nachdem, wie Sie Ihre automatisierten Untersuchungen so konfiguriert haben, dass sie in Microsoft Defender für Endpunkt und Defender für Office 365 ausgeführt werden.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Beispiel für eine Seite &quot;Untersuchungen&quot; für einen Vorfall":::

Wählen Sie eine Untersuchung aus, um zur Detailseite zu navigieren, um vollständige Informationen zum Untersuchungs- und Wartungsstatus zu erhalten. Wenn im Rahmen der Untersuchung Aktionen zur Genehmigung ausstehen, werden sie auf der Registerkarte **"Verlauf ausstehender Aktionen"** angezeigt. Ergreifen sie Maßnahmen im Rahmen der Vorfallbehebung.

Es gibt auch eine Registerkarte **"Untersuchungsdiagramm",** die Zeigt:

- Die Verbindung von Warnungen zu den betroffenen Ressourcen in Ihrer Organisation.
- Welche Entitäten mit welchen Warnungen zusammenhängen und wie sie Teil der Geschichte des Angriffs sind.
- Die Warnungen für den Vorfall.

Das Untersuchungsdiagramm hilft Ihnen, den gesamten Umfang des Angriffs schnell zu verstehen, indem die verschiedenen verdächtigen Entitäten, die Teil des Angriffs sind, mit ihren verwandten Ressourcen wie Benutzern, Geräten und Postfächern verbunden werden. 

Weitere Informationen finden Sie [unter "Automatisierte Untersuchung und Reaktion" in Microsoft 365 Defender.](m365d-autoir.md)

## <a name="evidence-and-response"></a>Nachweise und Antworten

Auf der Registerkarte **"Nachweise und Reaktion"** werden alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen des Vorfalls angezeigt. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Beispiel für eine Seite &quot;Nachweis und Reaktion&quot; für einen Vorfall":::

Microsoft 365 Defender untersucht automatisch alle von den Vorfällen unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen und stellt Ihnen Informationen zu wichtigen E-Mails, Dateien, Prozessen, Diensten, IP-Adressen und mehr bereit. Auf diese Weise können Sie potenzielle Bedrohungen im Vorfall schnell erkennen und blockieren.

Jede der analysierten Entitäten ist mit einem Bewertungsstatus (bösartig, verdächtig, sauber) und einem Korrekturstatus gekennzeichnet. Dies hilft Ihnen, den Wartungsstatus des gesamten Vorfalls zu verstehen und zu verstehen, welche nächsten Schritte ausgeführt werden können.

## <a name="next-steps"></a>Nächste Schritte

Bei Bedarf:

- [Untersuchen der Warnungen eines Vorfalls](investigate-alerts.md)
- [Untersuchen der Benutzer eines Vorfalls](investigate-users.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Priorisieren von Vorfällen](incident-queue.md)
- [Verwalten von Vorfällen](manage-incidents.md)

