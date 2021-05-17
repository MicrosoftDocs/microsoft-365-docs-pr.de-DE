---
title: Funktionsweise der automatisierten Untersuchung und Reaktion in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: automatisierte Reaktion auf Vorfälle, Untersuchung, Behebung, Bedrohungsschutz
ms.date: 01/29/2021
description: Erfahren Sie, wie automatisierte Untersuchungs- und Reaktionsfunktionen in Microsoft Defender for Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a8d33804e8c1405093843709e06250beb7f10512
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269636"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Funktionsweise der automatisierten Untersuchung und Reaktion in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wenn Sicherheitswarnungen ausgelöst werden, ist es an Ihrem Sicherheitsbetriebsteam, diese Warnungen zu betrachten und Schritte zum Schutz Ihrer Organisation zu ergreifen. Manchmal können sich Sicherheitsteams von der Menge der ausgelösten Warnungen überfordert fühlen. Automatisierte Untersuchungs- und Reaktionsfunktionen (AIR) in Microsoft Defender for Office 365 können helfen.

AIR ermöglicht Es Ihrem Sicherheitsteam, effizienter und effektiver zu arbeiten. Zu den AIR-Funktionen gehören automatisierte Untersuchungsprozesse als Reaktion auf bekannte Bedrohungen, die heute vorhanden sind. Geeignete Korrekturmaßnahmen warten auf die Genehmigung, sodass Ihr Sicherheitsteam auf erkannte Bedrohungen reagieren kann.

In diesem Artikel wird die Funktionsweise von AIR anhand mehrerer Beispiele beschrieben. Wenn Sie bereit sind, mit AIR zu beginnen, lesen [Sie Automatisch untersuchen und auf Bedrohungen reagieren.](office-365-air.md)

- [Beispiel 1: Eine vom Benutzer gemeldete Phishingnachricht startet ein Untersuchungsspielbuch](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Beispiel 2: Ein Sicherheitsadministrator löst eine Untersuchung aus dem Bedrohungs-Explorer aus.](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Beispiel 3: Ein Sicherheitsbetriebsteam integriert AIR mithilfe der Office 365 Management Activity API in ihr SIEM](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Beispiel: Eine vom Benutzer gemeldete Phishingnachricht startet ein Untersuchungsspielbuch

Angenommen, ein Benutzer in Ihrer Organisation empfängt eine E-Mail, die er für einen Phishingversuch hält. Der Benutzer, der für die Meldung solcher Nachrichten geschult ist, verwendet das [Add-In](enable-the-report-message-add-in.md) "Nachricht melden" oder das [Phishing-Add-In](enable-the-report-phish-add-in.md) melden, um es zur Analyse an Microsoft zu senden. Die Übermittlung wird auch an Ihr System gesendet und im Explorer in der **Übermittlungsansicht** angezeigt (früher als vom Benutzer **gemeldete** Ansicht bezeichnet). Darüber hinaus löst die vom Benutzer gemeldete Nachricht nun eine systembasierte Informationswarnung aus, die automatisch das Untersuchungsspielbuch startet.

Während der Stammuntersuchungsphase werden verschiedene Aspekte der E-Mail bewertet. Zu diesen Aspekten gehören:

- Eine Bestimmung darüber, um welche Art von Bedrohung es sich handeln kann.
- Wer gesendet;
- Woher die E-Mail gesendet wurde (sendende Infrastruktur);
- Gibt an, ob andere Instanzen der E-Mail zugestellt oder blockiert wurden;
- Eine Bewertung unserer Analysten;
- Gibt an, ob die E-Mail bekannten Kampagnen zugeordnet ist.
- und vieles mehr.

Nachdem die Stammuntersuchung abgeschlossen ist, enthält das Playbook eine Liste der empfohlenen Aktionen für die ursprüngliche E-Mail und die zugehörigen Entitäten.

Als Nächstes werden mehrere Schritte zur Bedrohungsuntersuchung und -suche ausgeführt:

- Ähnliche E-Mail-Nachrichten werden über E-Mail-Clustersuchen identifiziert.
- Das Signal wird für andere Plattformen freigegeben, z. B. [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- Es wird bestimmt, ob Benutzer auf schädliche Links in verdächtigen E-Mail-Nachrichten geklickt haben.
- Eine Überprüfung erfolgt Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) und ([Microsoft Defender für Office 365](defender-for-office-365.md)), um zu überprüfen, ob andere ähnliche Nachrichten von Benutzern gemeldet wurden.
- Es wird überprüft, ob ein Benutzer gefährdet wurde. Bei dieser Überprüfung werden Signale Office 365, [Microsoft Cloud App Security](/cloud-app-security)und Azure Active Directory [verwendet,](/azure/active-directory)die alle zugehörigen Anomalien der Benutzeraktivität korrelieren.

Während der Suche werden Risiken und Bedrohungen verschiedenen Jagdschritten zugewiesen.

Die Korrektur ist die letzte Phase des Spielbuchs. In dieser Phase werden Korrekturschritte basierend auf den Untersuchungs- und Nachschlagephasen unternommen.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Beispiel: Ein Sicherheitsadministrator löst eine Untersuchung aus dem Bedrohungs-Explorer aus.

Zusätzlich zu automatisierten Untersuchungen, die durch eine Warnung ausgelöst werden, kann das Sicherheitsteam Ihrer Organisation eine automatisierte Untersuchung aus einer Ansicht im [Bedrohungs-Explorer auslösen.](threat-explorer.md)  Diese Untersuchung erstellt auch eine Warnung, damit Microsoft Defender Incidents und externe SIEM-Tools erkennen können, dass diese Untersuchung ausgelöst wurde.

Angenommen, Sie verwenden die **Schadsoftwareansicht** im Explorer. Auf den Registerkarten unterhalb des Diagramms wählen Sie die Registerkarte **E-Mail** aus. Wenn Sie ein oder mehrere Elemente in der Liste auswählen, wird die **Schaltfläche + Aktionen** aktiviert.

![Explorer mit ausgewählten Nachrichten](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Im Menü **Aktionen** können Sie Untersuchung **auslösen auswählen.**

![Menü "Aktionen" für ausgewählte Nachrichten](../../media/explorer-malwareview-selectedemails-actions.jpg)

Ähnlich wie bei Playbooks, die durch eine Warnung ausgelöst werden, umfassen automatische Untersuchungen, die von einer Ansicht in Explorer ausgelöst werden, eine Stammuntersuchung, Schritte zum Identifizieren und Korrelieren von Bedrohungen sowie empfohlene Maßnahmen zur Minderung dieser Bedrohungen.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Beispiel: Ein Sicherheitsbetriebsteam integriert AIR mithilfe der Office 365 Management Activity API in ihr SIEM

Zu den AIR-Funktionen in Microsoft Defender for Office 365 gehören Berichte [&,](air-view-investigation-results.md) die Sicherheitsbetriebsteams zum Überwachen und Reagieren von Bedrohungen verwenden können. Sie können die FUNKTIONEN von AIR jedoch auch in andere Lösungen integrieren. Beispiele sind ein Sicherheitsinformations- und Ereignisverwaltungssystem (SIEM), ein Fallverwaltungssystem oder eine benutzerdefinierte Berichtslösung. Diese Arten von Integrationen können mithilfe der Office 365 [Management Activity API durchgeführt werden.](/office/office-365-management-api/office-365-management-activity-api-reference)

Beispielsweise hat eine Organisation kürzlich eine Möglichkeit für ihr Sicherheitsteam eingerichtet, um von Benutzern gemeldete Phishingwarnungen anzuzeigen, die bereits von AIR verarbeitet wurden. Ihre Lösung integriert relevante Warnungen in den SIEM-Server der Organisation und das Fallverwaltungssystem der Organisation. Die Lösung reduziert die Anzahl falsch positiver Ergebnisse erheblich, sodass das Sicherheitsteam seine Zeit und seinen Aufwand auf echte Bedrohungen konzentrieren kann. Weitere Informationen zu dieser benutzerdefinierten Lösung finden Sie unter [Tech Community blog: Improve the Effectiveness of your SOC with Microsoft Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-steps"></a>Nächste Schritte

- [Erste Schritte mit AIR](office-365-air.md)
- [Anzeigen ausstehender oder abgeschlossener Korrekturaktionen](air-review-approve-pending-completed-actions.md)