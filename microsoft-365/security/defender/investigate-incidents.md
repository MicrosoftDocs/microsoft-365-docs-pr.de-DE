---
title: Untersuchen von Vorfällen in Microsoft 365 Defender
description: Analysieren Sie Vorfälle in Bezug auf Geräte, Nutzer und Postfächer.
keywords: Vorfall, Vorfälle, Rechner, Geräte, Nutzer, Identitäten, Post, E-Mail, Postfach, Untersuchung, Graph, Beweise
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 99acc25c3949b758dab990a9c2e9104b9158accd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861875"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Untersuchen von Vorfällen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**

- Microsoft 365 Defender

Microsoft 365 Defender aggregiert alle zugehörigen Warnungen, Ressourcen, Untersuchungen und Nachweise aus Ihren Geräten, Benutzern und Postfächern in einem Vorfall, um Ihnen einen umfassenden Überblick über die gesamte Bandbreite eines Angriffs zu geben.

Innerhalb eines Vorfalls untersuchen Sie die Warnungen, die sich auf Ihr Netzwerk auswirken, verstehen, was sie bedeuten, und erstellen die Nachweise, damit Sie einen effektiven Korrekturplan entwickeln können.

## <a name="initial-investigation"></a>Erste Untersuchung

Bevor Sie in die Details eintauchen, sehen Sie sich die Eigenschaften und die Zusammenfassung des Vorfalls an.

Sie können beginnen, indem Sie den Vorfall in der Häkchenspalte auswählen. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Beispiel für die Auswahl eines Vorfalls aus der Häkchenspalte":::

In diesem Fall wird ein Zusammenfassungsbereich mit wichtigen Informationen zum Vorfall geöffnet, z. B. schweregrad, wem er zugewiesen ist, und die [MITRE ATT-&&trade; CK-Kategorien](https://attack.mitre.org/) für den Vorfall. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Beispiel für den Zusammenfassungsbereich für einen Vorfall":::

Hier können Sie die Seite **"Vorfall öffnen" auswählen.** Dadurch wird die Hauptseite für den Vorfall geöffnet, auf der Sie weitere Zusammenfassungsinformationen und Registerkarten für Warnungen, Geräte, Benutzer, Untersuchungen und Nachweise finden.

Sie können auch die Hauptseite für einen Vorfall öffnen, indem Sie den Vorfallnamen aus der Vorfallwarteschlange auswählen.

## <a name="summary"></a>Zusammenfassung

Auf **der** Seite Zusammenfassung finden Sie einen Überblick über die wichtigsten Dinge, die Sie über den Vorfall bemerken können.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Beispiel für die Zusammenfassungsseite für einen Vorfall im Microsoft 365 Security Center":::

Die Angriffskategorien bieten Ihnen eine visuelle und numerische Ansicht, wie weit der Angriff gegenüber der Kill Chain fortgeschritten ist. Wie bei anderen Microsoft-Sicherheitsprodukten ist Microsoft 365 Defender am [MITRE &trade; ATT-&CK-Framework](https://attack.mitre.org/) ausgerichtet.

Der Bereich enthält eine Liste der am häufigsten betroffenen Assets, die Teil dieses Vorfalls sind. Wenn es spezifische Informationen zu diesem Asset gibt, wie z. B. Risikograd, Untersuchungspriorität sowie eine Kennzeichnung des Assets, wird dies ebenfalls in diesem Abschnitt angezeigt.

Die Zeitachse für Warnungen bietet einen Einblick in die chronologische Reihenfolge, in der die Warnungen aufgetreten sind, sowie die Gründe, warum diese Warnungen mit diesem Vorfall verknüpft sind.

Und last – der Abschnitt "Evidence" enthält eine Zusammenfassung der Anzahl der verschiedenen Artefakte, die in den Vorfall einbezogen wurden, und deren Behebungsstatus, damit Sie sofort erkennen können, ob eine Aktion von Ihnen erforderlich ist.

Diese Übersicht kann bei der anfänglichen Triage des Vorfalls helfen, indem sie Einen Einblick in die wichtigsten Merkmale des Vorfalls bietet, die Sie beachten sollten.

## <a name="alerts"></a>Warnungen

Auf der **Registerkarte Warnung** können Sie die Warnwarteschlange für Warnungen im Zusammenhang mit dem Vorfall und andere Informationen zu diesem Ereignis anzeigen, z. B.:

- Schweregrad.
- Die Entitäten, die an der Warnung beteiligt waren.
- Die Quelle der Warnungen (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender für Office 365).
- Der Grund, warum sie miteinander verknüpft wurden.

Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Beispiel für eine Warnungsseite für einen Vorfall":::

Standardmäßig werden die Warnungen chronologisch geordnet, damit Sie sehen können, wie sich der Vorfall im Laufe der Zeit abgespielt hat. Wenn Sie jede Warnung auswählen, gelangen Sie zur Hauptseite der Warnung, auf der Sie eine eingehende Untersuchung dieser Warnung durchführen können. 

Informationen zur Verwendung der Warnungswarteschlange und der Warnungsseiten unter [Warnungen untersuchen](investigate-alerts.md)

## <a name="devices"></a>Geräte

Auf **der** Registerkarte Geräte werden alle Geräte im Zusammenhang mit dem Vorfall aufgeführt. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Beispiel für eine Geräteseite für einen Vorfall":::

Sie können das Häkchen für ein Gerät aktivieren, um Details zu Gerät, Verzeichnisdaten, aktiven Warnungen und angemeldeten Benutzern anzuzeigen. Wählen Sie den Namen des Geräts aus, um Gerätedetails im Microsoft Defender for Endpoints-Gerätebestand anzuzeigen.

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Beispiel für eine Geräteseite für Microsoft Defender for Endpoints":::

Auf der Geräteseite können Sie zusätzliche Informationen zum Gerät sammeln, z. B. alle Warnungen, eine Zeitachse und Sicherheitsempfehlungen. Auf der Registerkarte  Zeitachse können Sie beispielsweise einen Bildlauf durch die Zeitachse des Computers durchführen und alle auf dem Computer beobachteten Ereignisse und Verhaltensweisen in chronologischer Reihenfolge anzeigen, die durch die ausgelösten Warnungen durchgezogen sind.

> [!TIP]
> Sie können Bedarfsscans auf einer Geräteseite durchführen. Wählen Sie im Microsoft 365 Security Center **Endpunkte > Gerätebestand aus.** Wählen Sie ein Gerät mit Warnungen aus, und führen Sie dann eine Antivirenscan aus. Aktionen, z. B. Antivirenscans, werden nachverfolgt und sind auf der Seite **Geräteinventar** sichtbar. Weitere Informationen finden Sie unter [Ausführen der Microsoft Defender Antivirus-Überprüfung auf Geräten](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).

## <a name="users"></a>Benutzer

Auf **der** Registerkarte Benutzer werden alle Benutzer aufgeführt, die als Teil oder im Zusammenhang mit dem Vorfall identifiziert wurden. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Beispiel einer Benutzerseite für einen Vorfall":::

Sie können das Häkchen für einen Benutzer aktivieren, um Details zur Bedrohung, Belichtung und Kontaktinformationen des Benutzerkontos anzuzeigen. Wählen Sie den Benutzernamen aus, um weitere Benutzerkontodetails anzuzeigen.

## <a name="mailboxes"></a>Postfächer

Auf **der Registerkarte** Postfächer werden alle Postfächer aufgeführt, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Beispiel einer Postfachseite für einen Vorfall":::

Sie können das Häkchen für ein Postfach aktivieren, um eine Liste aktiver Warnungen anzuzeigen. Wählen Sie den Postfachnamen aus, um zusätzliche Postfachdetails auf der Explorer-Seite für Microsoft Defender für Office 365 anzuzeigen.

## <a name="investigations"></a>Untersuchungen

Auf **der Registerkarte** Untersuchungen sind alle automatisierten Untersuchungen aufgeführt, die durch Warnungen in diesem Vorfall ausgelöst wurden. Die Untersuchungen führen Korrekturmaßnahmen durch oder warten auf die Genehmigung von Aktionen durch Analysten, je nachdem, wie Sie Ihre automatisierten Untersuchungen für die Ausführung in Microsoft Defender for Endpoint und Defender für Office 365 konfiguriert haben.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Beispiel für eine Seite &quot;Untersuchungen&quot; für einen Vorfall":::

Wählen Sie eine Untersuchung aus, um zur Seite mit den Untersuchungsdetails zu navigieren und vollständige Informationen zum Untersuchungs- und Behebungsstatus zu erhalten. Wenn im Rahmen der Untersuchung Aktionen zur Genehmigung ausstehen, werden sie auf der Registerkarte Ausstehende Aktionen angezeigt. Ergreifen Sie Maßnahmen im Rahmen der Vorfallbehebung.

## <a name="evidence-and-response"></a>Nachweis und Antwort

Auf **der Registerkarte Nachweis und Antwort** werden alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen im Vorfall angezeigt. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Beispiel für eine Evidenz- und Reaktionsseite für einen Vorfall":::

Microsoft 365 Defender untersucht automatisch alle von Vorfällen unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen und stellt Ihnen Informationen zu wichtigen E-Mails, Dateien, Prozessen, Diensten, IP-Adressen und mehr zur Verfügung. Auf diese Weise können Sie potenzielle Bedrohungen in dem Vorfall schnell erkennen und blockieren.

Jede der analysierten Entitäten ist mit einem Urteil (Bösartig, Verdächtig, Clean) und einem Behebungsstatus gekennzeichnet. Auf diese Weise können Sie den Behebungsstatus des gesamten Vorfalls und die nächsten Schritte verstehen.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Vorfälle](incidents-overview.md)
- [Priorisieren von Vorfällen](incident-queue.md)
- [Verwalten von Vorfällen](manage-incidents.md)

