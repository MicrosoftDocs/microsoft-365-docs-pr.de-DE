---
title: Funktionsweise der automatisierten Untersuchung und Reaktion in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
keywords: Automatisierte Reaktion auf Vorfälle, Untersuchung, Problembehebung, Bedrohungsschutz
ms.date: 01/29/2021
description: Erfahren Sie, wie automatisierte Untersuchungs- und Reaktionsfunktionen in Microsoft Defender für Office 365 funktionieren
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b187c5fee560e1ebf5463e889fff874aca05212d
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175823"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Funktionsweise der automatisierten Untersuchung und Reaktion in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Wenn Sicherheitswarnungen ausgelöst werden, ist es an Ihrem Sicherheitsteam, diese Warnungen zu betrachten und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen. Manchmal können sich Sicherheitsteams überfordert fühlen, wenn die Anzahl der ausgelösten Warnungen zu groß ist. Automatisierte Untersuchungs- und Reaktionsfunktionen (AIR) in Microsoft Defender für Office 365 können hilfreich sein.

AIR ermöglicht Es Ihrem Sicherheitsteam, effizienter und effektiver zu arbeiten. Die Funktionen von AIR umfassen automatisierte Untersuchungsprozesse als Reaktion auf bekannte Bedrohungen, die heute vorhanden sind. Geeignete Abhilfemaßnahmen warten auf Genehmigung, sodass Ihr Sicherheitsteam auf erkannte Bedrohungen reagieren kann.

In diesem Artikel wird die Funktionsweise von AIR anhand mehrerer Beispiele beschrieben. Wenn Sie bereit sind, mit AIR zu beginnen, lesen Sie "Automatische Untersuchung und [Reaktion auf Bedrohungen".](office-365-air.md)

- [Beispiel 1: Eine vom Benutzer gemeldete Phishingnachricht startet ein Playbook für die Untersuchung](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Beispiel 2: Ein Sicherheitsadministrator löst eine Untersuchung von Threat Explorer aus](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Beispiel 3: Ein Sicherheitsteam integriert AIR mithilfe der Office 365-Verwaltungsaktivitäts-API in ihr SIEM.](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Beispiel: Eine vom Benutzer gemeldete Phishingnachricht startet ein Playbook zur Untersuchung

Angenommen, ein Benutzer in Ihrer Organisation empfängt eine E-Mail, die seiner Meinung nach ein Phishingversuch ist. Der Benutzer, der zum Melden solcher Nachrichten geschult ist, verwendet das [Add-In](enable-the-report-message-add-in.md) "Nachricht melden" oder das [Phishing-Add-In](enable-the-report-phish-add-in.md) "Melden", um es zur Analyse an Microsoft zu senden. Die Übermittlung wird auch an Ihr System gesendet  und im Explorer in der Ansicht "Übermittlungen" angezeigt (früher als Vom Benutzer **gemeldete** Ansicht bezeichnet). Darüber hinaus löst die vom Benutzer gemeldete Nachricht jetzt eine systembasierte Informationswarnung aus, die automatisch das Playbook für die Untersuchung startet.

Während der Stammuntersuchungsphase werden verschiedene Aspekte der E-Mail bewertet. Zu diesen Aspekten gehören:

- Eine Entscheidung darüber, um welche Art von Bedrohung es sich handeln kann;
- Wer hat es gesendet?
- Woher die E-Mail gesendet wurde (Sendende Infrastruktur);
- Gibt an, ob andere Instanzen der E-Mail zugestellt oder blockiert wurden.
- Eine Bewertung unserer Analysten;
- Gibt an, ob die E-Mail bekannten Kampagnen zugeordnet ist.
- und vieles mehr.

Nach Abschluss der Stammuntersuchung bietet das Playbook eine Liste der empfohlenen Aktionen für die ursprüngliche E-Mail und die damit verbundenen Entitäten.

Als Nächstes werden mehrere Schritte zur Bedrohungsuntersuchung und -suche ausgeführt:

- Ähnliche E-Mail-Nachrichten werden über E-Mail-Clustersuchen identifiziert.
- Das Signal wird mit anderen Plattformen geteilt, z. B. [Microsoft Defender für Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- Es wird bestimmt, ob Benutzer auf bösartige Links in verdächtigen E-Mail-Nachrichten geklickt haben.
- Eine Überprüfung erfolgt in Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) und ([Microsoft Defender für Office 365](office-365-atp.md)), um zu überprüfen, ob andere ähnliche Nachrichten von Benutzern gemeldet wurden.
- Es wird überprüft, ob ein Benutzer gefährdet wurde. Diese Überprüfung nutzt Signale in Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)und Azure Active [Directory,](https://docs.microsoft.com/azure/active-directory)und korreliert alle verwandten Benutzeraktivitätsanomalien.

Während der Suche werden Risiken und Bedrohungen verschiedenen Schritten für die Suche zugewiesen.

Die Korrektur ist die letzte Phase des Playbooks. Während dieser Phase werden Korrekturschritte basierend auf den Untersuchungs- und Nachschlagephasen unternommen.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Beispiel: Ein Sicherheitsadministrator löst eine Untersuchung vom Bedrohungs-Explorer aus

Zusätzlich zu automatisierten Untersuchungen, die durch eine Warnung ausgelöst werden, kann das Sicherheitsteam Ihrer Organisation eine automatisierte Untersuchung aus einer Ansicht im [Threat Explorer auslösen.](threat-explorer.md)  Diese Untersuchung erstellt auch eine Warnung, damit Microsoft Defender Incidents und externe SIEM-Tools sehen können, dass diese Untersuchung ausgelöst wurde.

Angenommen, Sie verwenden die Ansicht **"Schadsoftware"** im Explorer. Auf den Registerkarten unterhalb des Diagramms wählen Sie die Registerkarte **"E-Mail"** aus. Wenn Sie ein oder mehrere Elemente in der Liste auswählen, wird die Schaltfläche **+Aktionen** aktiviert.

![Explorer mit ausgewählten Nachrichten](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Im Menü **"Aktionen"** können Sie "Untersuchung **auslösen" auswählen.**

![Menü "Aktionen" für ausgewählte Nachrichten](../../media/explorer-malwareview-selectedemails-actions.jpg)

Ähnlich wie durch eine Warnung ausgelöste Playbooks umfassen automatische Untersuchungen, die von einer Ansicht im Explorer ausgelöst werden, eine Stammuntersuchung, Schritte zum Identifizieren und Korrelieren von Bedrohungen sowie empfohlene Maßnahmen zur Minderung dieser Bedrohungen.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Beispiel: Ein Sicherheitsteam integriert AIR mithilfe der Office 365-Verwaltungsaktivitäts-API in ihr SIEM

Die Funktionen von AIR in Microsoft Defender für Office 365 umfassen Berichte [&](air-view-investigation-results.md) Details, die Sicherheitsteams zum Überwachen und Reagieren auf Bedrohungen verwenden können. Sie können jedoch auch die Funktionen von AIR in andere Lösungen integrieren. Beispiele hierfür sind ein Sicherheitsinformations- und Ereignisverwaltungssystem (SIEM), ein Fallverwaltungssystem oder eine benutzerdefinierte Berichterstellungslösung. Diese Arten von Integrationen können mithilfe der [Office 365-Verwaltungsaktivitäts-API durchgeführt werden.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

Vor kurzem hat eine Organisation beispielsweise eine Möglichkeit für ihr Sicherheitsteam eingerichtet, um von Benutzern gemeldete Phishingwarnungen anzuzeigen, die bereits von AIR verarbeitet wurden. Ihre Lösung integriert relevante Warnungen in den SIEM-Server und das Fallverwaltungssystem der Organisation. Die Lösung reduziert die Anzahl falsch positiver Ergebnisse erheblich, damit ihr Sicherheitsteam seine Zeit und Mühe auf echte Bedrohungen konzentrieren kann. Weitere Informationen zu dieser benutzerdefinierten Lösung finden Sie im Tech Community-Blog: Verbessern der Effektivität Ihres SOC mit Microsoft Defender für Office 365 und der [O365-Verwaltungs-API.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

## <a name="next-steps"></a>Nächste Schritte

- [Erste Schritte mit AIR](office-365-air.md)
- [Anzeigen ausstehender oder abgeschlossener Wartungsaktionen](air-review-approve-pending-completed-actions.md)
