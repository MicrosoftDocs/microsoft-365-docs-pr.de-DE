---
title: Übersicht über die automatische Untersuchung und Reaktion (Luft)
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
- m365-initiative-defender-office365
keywords: Automatische Vorfall Antwort, Untersuchung, Behebung, Bedrohungsschutz
ms.date: 09/29/2020
description: Erhalten Sie einen Überblick über die automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Defender für Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 850291966c2f2da51782d8e70de23ff4f06d6136
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413962"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Eine Übersicht über die automatisierte Untersuchung und Antwort (Air) in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wenn Sicherheitswarnungen ausgelöst werden, liegt es an Ihrem Sicherheits Betriebsteam, diese Warnungen zu untersuchen und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen. Manchmal können sich Sicherheits Operations Teams von der Menge der ausgelösten Warnungen überfordert fühlen. Die Funktionen für die automatische Untersuchung und Reaktion (Air) in Microsoft Defender für Office 365 können helfen. 

Mit Air kann Ihr Security Operations-Team effizienter und effektiver arbeiten. Air-Funktionen umfassen automatisierte Ermittlungsprozesse als Reaktion auf bekannte Bedrohungen, die heute vorhanden sind. Geeignete Korrekturaktionen warten auf die Genehmigung, sodass Ihr Sicherheits Betriebsteam auf erkannte Bedrohungen reagieren kann. 

Dieser Artikel bietet eine Übersicht über Air. Wenn Sie mit der Verwendung von Air beginnen möchten, finden Sie weitere Informationen unter [Automatisches untersuchen und reagieren auf Bedrohungen](office-365-air.md).

## <a name="at-a-high-level"></a>Auf einer hohen Ebene

Wenn Warnungen ausgelöst werden, treten Sicherheits-Textbuch in Kraft. Je nach Situation kann ein [automatischer Ermittlungsprozess](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) beginnen. Während und nach einer automatischen Untersuchung werden [Korrekturaktionen](air-remediation-actions.md) empfohlen. In Microsoft Defender werden für Office 365 keine Aktionen automatisch ausgeführt. Ihr Security Operations-Team überprüft, und [genehmigt oder lehnt dann jede Korrekturaktion](air-review-approve-pending-completed-actions.md)ab. Wenn alle nach einer Untersuchung durchgeführten Aktionen genehmigt oder abgelehnt werden, wird die Untersuchung abgeschlossen. Alle diese Aktivitäten werden im Microsoft 365 Security Center () nachverfolgt und angezeigt [https://security.microsoft.com](https://security.microsoft.com) . (Weitere Informationen finden Sie unter [Details zu einer Untersuchung anzeigen](air-view-investigation-results.md#view-details-of-an-investigation)).

Die folgenden Abschnitte enthalten weitere Informationen zu Warnungen, Sicherheits handschreibungen und Beispiele für Luft in Aktion.

## <a name="alerts"></a>Warnungen

[Warnungen](../../compliance/alert-policies.md#viewing-alerts) stellen Auslöser für Sicherheitsvorgänge-Team Workflows für die Vorfall Antwort dar. Priorisieren des richtigen Warnungs Satzes für die Untersuchung, wobei sichergestellt wird, dass keine Bedrohungen unbehandelt sind, ist eine Herausforderung. Wenn Untersuchungen zu Warnungen manuell durchgeführt werden, müssen Sicherheits Betriebsteams Entitäten (beispielsweise Inhalte, Geräte und Benutzer), die von Bedrohungen bedroht sind, jagen und korrelieren. Solche Aufgaben und Workflows können sehr zeitaufwendig sein und umfassen mehrere Tools und Systeme. Mit Air werden Untersuchung und Reaktion für Sicherheitsereignisse automatisiert, indem wichtige Sicherheits-und Bedrohungsmanagement-Warnungen automatisch Sicherheitsantwort-Textbuch auslösen. 

Derzeit werden Warnungen, die aus den folgenden Arten von Warnungsrichtlinien generiert werden, automatisch untersucht:  

- Ein potenziell böswilliger URL-Klick wurde erkannt.
- Vom Benutzer als Phishing gemeldete e-Mail`*`
- E-Mail-Nachrichten mit Schadsoftware nach der Zustellung entfernt`*`
- E-Mail-Nachrichten mit Phishing-URLs nach der Zustellung entfernt`*`
- Erkannte verdächtige e-Mail-Sende Muster
- Benutzer vom Senden von e-Mails eingeschränkt
- Manuelles untersuchen von e-Mails durch den Administrator ausgelöst`*`

> [!NOTE]
> Die mit einem Sternchen () markierten Warnungen `*` werden in den jeweiligen Warnungsrichtlinien im Microsoft 365 Security Center mit einem *Informations* Schweregrad versehen, wobei e-Mail-Benachrichtigungen deaktiviert sind. E-Mail-Benachrichtigungen können über die [Warnungsrichtlinien Konfiguration](../../compliance/alert-policies.md#alert-policy-settings)aktiviert werden. 

Um Warnungen anzuzeigen, wählen Sie im Security & Compliance **Center Benachrichtigungen**  >  **anzeigen Warnungen**aus. Wählen Sie eine Warnung aus, um die Details anzuzeigen, und verwenden Sie dann den Link **Untersuchung anzeigen** , um zur entsprechenden [Untersuchung](air-view-investigation-results.md#investigation-graph)zu gelangen.  

> [!NOTE]
> Informationswarnungen werden standardmäßig in der Warnungsansicht ausgeblendet. Um diese anzuzeigen, ändern Sie die Warnungsfilterung so, dass Sie Informationswarnungen einschließt.

Wenn Ihre Organisation ihre Sicherheitswarnungen über ein Warnungsverwaltungssystem, ein Dienst Verwaltungssystem oder ein System für die Verwaltung von Sicherheitsinformationen und Ereignisverwaltung verwaltet, können Sie Warnungen entweder per e-Mail-Benachrichtigung oder über die [Office 365 Verwaltungs Aktivitäts-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)an dieses System senden. Die Untersuchung von Benachrichtigungs Benachrichtigungen per e-Mail oder API enthält Links für den Zugriff auf die Warnungen im Microsoft 365 Security Center, sodass der zugewiesene Sicherheitsadministrator schnell zu der Untersuchung navigieren kann.

![Warnungen, die mit Untersuchungen verknüpft sind](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Sicherheits-Manuskripte

Sicherheits-Textbuch sind Back-End-Richtlinien, die im Mittelpunkt der Automatisierung in Microsoft Defender für Office 365 und Microsoft Threat Protection stehen. Die in Air bereitgestellten Sicherheits-Textbuch basieren auf gängigen realen Sicherheitsszenarien und werden auf der Grundlage von Feedback aus Sicherheits Betriebsteams entwickelt. Ein Sicherheits Textbuch wird automatisch gestartet, wenn in Ihrer Organisation bestimmte Warnungen ausgelöst werden. Sobald die Warnung ausgelöst wird, wird das zugehörige Textbuch durch das automatisierte Ermittlungs-und Antwortsystem ausgeführt. Die Untersuchung erfolgt durch eine Analyse der Warnung basierend auf dem Textbuch der jeweiligen Warnung, wobei alle zugehörigen Metadaten (einschließlich e-Mail-Nachrichten, Benutzer, Subjekte, Absender usw.) untersucht werden. Basierend auf den Ergebnissen der Untersuchung des Textbuch empfiehlt Air eine Reihe von Aktionen, die das Sicherheitsteam Ihrer Organisation ausführen kann, um die Bedrohung zu steuern und zu mindern. 

Die Sicherheits-Textbuch-Dokumente, die Sie mit Air erhalten, wurden entwickelt, um die häufigsten Bedrohungen zu bewältigen, mit denen Organisationen heute mit e-Mails konfrontiert sind. Sie basieren auf Eingaben aus Sicherheits-und Vorfall Reaktions Teams, einschließlich Personen, die zur Verteidigung von Microsoft und den Ressourcen unserer Kunden beitragen.

- Vom Benutzer gemeldete Phishing-Nachricht
- Änderung des URL-Klick-Urteils
- Erkannte Schadsoftware nach der Zustellung (Malware zap)
- Phishing-Erkennung nach der Zustellung zap (Phishing zap)
- Benutzer als kompromittiert gemeldet 
- Manuelle e-Mail-Untersuchung (ausgelöst vom Administrator aus dem Explorer-Malware, Phishing oder alle e-Mail-Ansicht)

Weitere Textbuch-und Textbuch-Updates werden als abgeschlossen veröffentlicht. Besuchen Sie die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap) , um zu sehen, was noch geplant ist und demnächst verfügbar ist.

### <a name="playbooks-include-investigation-and-recommendations"></a>Manuskripte umfassen Untersuchungen und Empfehlungen

In der Luft umfasst jedes Sicherheits-Textbuch Folgendes: 

- eine Stamm Untersuchung der Entitäten einer e-Mail (beispielsweise Dateien, URLs, Empfänger, IP-Adressen und mehr)
- Weitere Jagd auf ähnliche e-Mails, die von der Organisation empfangen werden 
- Schritte zum Identifizieren und korrelieren anderer potenzieller Bedrohungen und 
- Empfohlene Aktionen zur Behebung von Bedrohungen.

Jeder allgemeine Schritt enthält eine Reihe von unterschritten, die ausgeführt werden, um eine Tiefe, detaillierte und erschöpfende Antwort auf Bedrohungen bereitzustellen.

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
- Eine Überprüfung erfolgt über Exchange Online Protection ([EoP](exchange-online-protection-overview.md)) und Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)), um zu sehen, ob andere ähnliche Nachrichten von Benutzern gemeldet werden.
- Eine Überprüfung wird durchgeführt, um festzustellen, ob ein Benutzer kompromittiert wurde. Bei dieser Überprüfung werden Signale in Bezug auf Office 365, [Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security)und [Azure-Active Directory](https://docs.microsoft.com/azure/active-directory)verwendet, sodass alle zugehörigen Anomalien bei Benutzeraktivitäten korreliert werden.

Während der Jagd Phase werden Risiken und Bedrohungen verschiedenen Jagd Schritten zugeordnet. 

Die Korrektur ist die letzte Phase des Textbuch. In dieser Phase werden korrekturschritte basierend auf den Ermittlungs-und Jagd Phasen durchgeführt. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Beispiel: ein Sicherheitsadministrator löst eine Untersuchung mit Threat Explorer aus.

Zusätzlich zu den automatisierten Untersuchungen, die durch eine Warnung ausgelöst werden, kann das Sicherheits Betriebsteam Ihrer Organisation eine automatisierte Untersuchung aus einer Ansicht in [Threat Explorer](threat-explorer.md)auslösen.  Diese Untersuchung erstellt auch eine Warnung, sodass Microsoft Defender-Vorfälle und externe Siem-Tools erkennen können, dass diese Untersuchung ausgelöst wurde. 

Nehmen wir beispielsweise an, dass Sie die **Malware** Ansicht im Explorer verwenden. Mithilfe der Registerkarten unter dem Diagramm Wählen Sie die Registerkarte **e-Mail** aus. Wenn Sie ein oder mehrere Elemente in der Liste auswählen, wird die Schaltfläche **+ Aktionen** aktiviert. 

![Explorer mit ausgewählten Nachrichten](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Über das Menü **Aktionen** können Sie **Untersuchung auslösen**auswählen.

![Menü "Aktionen" für ausgewählte Nachrichten](../../media/explorer-malwareview-selectedemails-actions.jpg)

Ähnlich wie Textbuch, die durch eine Warnung ausgelöst werden, umfassen automatische Untersuchungen, die aus einer Ansicht im Explorer ausgelöst werden, eine Stamm Ermittlung, Schritte zum Identifizieren und Korrelieren von Bedrohungen sowie Empfohlene Aktionen zur Minderung dieser Bedrohungen.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Beispiel: ein Security Operations-Team integriert Air mit ihren Siem-Funktionen mithilfe der Office 365-Verwaltungs Aktivitäts-API

Air-Funktionen in Microsoft Defender für Office 365 enthalten [Berichte & Details](air-view-investigation-results.md) , die Sicherheits Operations Teams zum Überwachen und adressieren von Bedrohungen verwenden können. Sie können aber auch Air-Funktionen in andere Lösungen integrieren. Beispiele hierfür sind ein System für Sicherheitsinformationen und Ereignisverwaltung (SIEM), ein Fallverwaltungssystem oder eine benutzerdefinierte Berichtslösung. Diese Arten von Integrationen können mithilfe der API für die [Office 365-Verwaltungsaktivität](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)ausgeführt werden. 

Beispielsweise hat eine Organisation kürzlich eine Möglichkeit für Ihr Sicherheits Betriebsteam eingerichtet, Benutzer gemeldete Phishing-Benachrichtigungen anzuzeigen, die bereits von Air verarbeitet wurden. Ihre Lösung integriert relevante Warnungen in den Siem-Server der Organisation und Ihr Fallverwaltungssystem. Die Lösung reduziert erheblich die Anzahl falsch positiver Ergebnisse, sodass Ihr Sicherheits Betriebsteam sich Zeit und Aufwand auf reale Bedrohungen konzentrieren kann. Weitere Informationen zu dieser benutzerdefinierten Lösung finden Sie unter [Tech Community Blog: verbessern der Effektivität ihrer SoC mit Office 365 ATP und der O365-Verwaltungs-API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-steps"></a>Nächste Schritte

- [Erste Schritte mit Air](office-365-air.md)

- [Besuchen Sie die Microsoft 365-Roadmap, um zu sehen, was in Kürze geplant und veröffentlicht wurde.](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Informationen zu zusätzlichen automatischen Ermittlungs-und Antwortfunktionen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
