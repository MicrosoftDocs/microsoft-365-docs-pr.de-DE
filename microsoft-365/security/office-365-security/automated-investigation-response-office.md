---
title: Funktionsweise von automatisierten Untersuchungen und Antworten in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: Automatische Vorfall Antwort, Untersuchung, Behebung, Bedrohungsschutz
ms.date: 11/05/2020
description: Erfahren Sie, wie automatisierte unter Such-und Antwortfunktionen in Microsoft Defender für Office 365 funktionieren.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: b901585f0a25c51c377e974c56faffe560eab5f3
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357671"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Funktionsweise von automatisierten Untersuchungen und Antworten in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Wenn Sicherheitswarnungen ausgelöst werden, liegt es an Ihrem Sicherheits Betriebsteam, diese Warnungen zu untersuchen und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen. Manchmal können sich Sicherheits Operations Teams von der Menge der ausgelösten Warnungen überfordert fühlen. Die Funktionen für die automatische Untersuchung und Reaktion (Air) in Microsoft Defender für Office 365 können helfen.

Mit Air kann Ihr Security Operations-Team effizienter und effektiver arbeiten. Air-Funktionen umfassen automatisierte Ermittlungsprozesse als Reaktion auf bekannte Bedrohungen, die heute vorhanden sind. Geeignete Korrekturaktionen warten auf die Genehmigung, sodass Ihr Sicherheits Betriebsteam auf erkannte Bedrohungen reagieren kann.

In diesem Artikel wird die Funktionsweise von Air anhand verschiedener Beispiele beschrieben. Wenn Sie mit der Verwendung von Air beginnen möchten, finden Sie weitere Informationen unter [Automatisches untersuchen und reagieren auf Bedrohungen](office-365-air.md).

- [Beispiel 1: eine von einem Benutzer gemeldete Phishing-Nachricht startet eine Untersuchung des Manuskripts](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Beispiel 2: ein Sicherheitsadministrator löst eine Untersuchung von Threat Explorer aus](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Beispiel 3: ein Security Operations-Team integriert Air mit ihren Siem-Funktionen mithilfe der Office 365-Verwaltungs Aktivitäts-API](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)


## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Beispiel: eine von einem Benutzer gemeldete Phishing-Nachricht startet eine Untersuchung des Manuskripts

Angenommen, ein Benutzer in Ihrer Organisation erhält eine e-Mail, die er für einen Phishing-Versuch halte. Der Benutzer, der zum Melden solcher Nachrichten ausgebildet wurde, verwendet das [Add-in "Berichtsnachricht](enable-the-report-message-add-in.md) ", um ihn zur Analyse an Microsoft zu senden. Die Übermittlung wird auch an Ihr System gesendet und im Explorer in der Ansicht " **Einsendungen** " (zuvor als vom **Benutzer gemeldete** Ansicht bezeichnet) angezeigt. Darüber hinaus wird von der vom Benutzer gemeldeten Nachricht nun eine System basierte Informationswarnung ausgelöst, die das unter suchbuch automatisch startet.

Während der Stamm Untersuchungsphase werden verschiedene Aspekte der e-Mail bewertet. Diese Aspekte umfassen:

- Eine Bestimmung darüber, welche Art von Bedrohung es sein könnte;
- Absender
- Woher die e-Mail gesendet wurde (sendende Infrastruktur);
- Gibt an, ob andere Instanzen der e-Mail zugestellt oder blockiert wurden;
- Eine Bewertung durch unsere Analysten;
- Gibt an, ob die e-Mail bekannten Kampagnen zugeordnet ist;
- und vieles mehr.

Nachdem die Stamm Untersuchung abgeschlossen ist, enthält das Textbuch eine Liste der empfohlenen Aktionen, die für die ursprünglichen e-Mail-Objekte und zugehörigen Entitäten übernommen werden sollen.
  
Im nächsten Schritt werden mehrere Schritte zur Ermittlung und Jagd von Bedrohungen ausgeführt:

- Ähnliche e-Mail-Nachrichten werden über e-Mail-Cluster Suchvorgänge identifiziert.
- Das Signal wird für andere Plattformen freigegeben, wie [zum Beispiel Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- Es wird festgestellt, ob Benutzer in verdächtigen e-Mail-Nachrichten auf böswillige Links geklickt haben.
- Eine Überprüfung erfolgt über Exchange Online Schutz ([EoP](exchange-online-protection-overview.md)) und ([Microsoft Defender für Office 365](office-365-atp.md)), um zu sehen, ob es andere ähnliche Nachrichten gibt, die von Benutzern gemeldet werden.
- Eine Überprüfung wird durchgeführt, um festzustellen, ob ein Benutzer kompromittiert wurde. Bei dieser Überprüfung werden Signale in Bezug auf Office 365, [Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security)und [Azure-Active Directory](https://docs.microsoft.com/azure/active-directory)verwendet, sodass alle zugehörigen Anomalien bei Benutzeraktivitäten korreliert werden.

Während der Jagd Phase werden Risiken und Bedrohungen verschiedenen Jagd Schritten zugeordnet. 

Die Korrektur ist die letzte Phase des Textbuch. In dieser Phase werden korrekturschritte basierend auf den Ermittlungs-und Jagd Phasen durchgeführt. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Beispiel: ein Sicherheitsadministrator löst eine Untersuchung mit Threat Explorer aus.

Zusätzlich zu den automatisierten Untersuchungen, die durch eine Warnung ausgelöst werden, kann das Sicherheits Betriebsteam Ihrer Organisation eine automatisierte Untersuchung aus einer Ansicht in [Threat Explorer](threat-explorer.md)auslösen.  Diese Untersuchung erstellt auch eine Warnung, sodass Microsoft Defender-Vorfälle und externe Siem-Tools erkennen können, dass diese Untersuchung ausgelöst wurde. 

Nehmen wir beispielsweise an, dass Sie die **Malware** Ansicht im Explorer verwenden. Mithilfe der Registerkarten unter dem Diagramm Wählen Sie die Registerkarte **e-Mail** aus. Wenn Sie ein oder mehrere Elemente in der Liste auswählen, wird die Schaltfläche **+ Aktionen** aktiviert. 

![Explorer mit ausgewählten Nachrichten](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Über das Menü **Aktionen** können Sie **Untersuchung auslösen** auswählen.

![Menü "Aktionen" für ausgewählte Nachrichten](../../media/explorer-malwareview-selectedemails-actions.jpg)

Ähnlich wie Textbuch, die durch eine Warnung ausgelöst werden, umfassen automatische Untersuchungen, die aus einer Ansicht im Explorer ausgelöst werden, eine Stamm Ermittlung, Schritte zum Identifizieren und Korrelieren von Bedrohungen sowie Empfohlene Aktionen zur Minderung dieser Bedrohungen.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Beispiel: ein Security Operations-Team integriert Air mit ihren Siem-Funktionen mithilfe der Office 365-Verwaltungs Aktivitäts-API

Air-Funktionen in Microsoft Defender für Office 365 enthalten [Berichte & Details](air-view-investigation-results.md) , die Sicherheits Operations Teams zum Überwachen und adressieren von Bedrohungen verwenden können. Sie können aber auch Air-Funktionen in andere Lösungen integrieren. Beispiele hierfür sind ein System für Sicherheitsinformationen und Ereignisverwaltung (SIEM), ein Fallverwaltungssystem oder eine benutzerdefinierte Berichtslösung. Diese Arten von Integrationen können mithilfe der API für die [Office 365-Verwaltungsaktivität](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)ausgeführt werden. 

Beispielsweise hat eine Organisation kürzlich eine Möglichkeit für Ihr Sicherheits Betriebsteam eingerichtet, Benutzer gemeldete Phishing-Benachrichtigungen anzuzeigen, die bereits von Air verarbeitet wurden. Ihre Lösung integriert relevante Warnungen in den Siem-Server der Organisation und Ihr Fallverwaltungssystem. Die Lösung reduziert erheblich die Anzahl falsch positiver Ergebnisse, sodass Ihr Sicherheits Betriebsteam sich Zeit und Aufwand auf reale Bedrohungen konzentrieren kann. Weitere Informationen zu dieser benutzerdefinierten Lösung finden Sie unter [Tech Community Blog: verbessern der Effektivität ihrer SoC mit Microsoft Defender für Office 365 und der O365-Verwaltungs-API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-steps"></a>Nächste Schritte

- [Erste Schritte mit Air](office-365-air.md)

- [Besuchen Sie die Microsoft 365-Roadmap, um zu sehen, was in Kürze geplant und veröffentlicht wurde.](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Informationen zu automatisierten Ermittlungs-und Antwortfunktionen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
