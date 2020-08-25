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
ms.collection: M365-security-compliance
ms.date: 08/21/2020
description: Hier erhalten Sie einen Überblick über die automatisierten Ermittlungs-und Antwortfunktionen in Office 365 Advanced Threat Protection-Plan 2.
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: 27a2330d5f1ff339aabf6a0fccb94a15dec30852
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860721"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a>Eine Übersicht über die automatische Untersuchung und Reaktion (Air) in Microsoft 365

Wenn Sicherheitswarnungen ausgelöst werden, liegt es an Ihrem Sicherheits Betriebsteam, diese Warnungen zu untersuchen und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen. Manchmal können sich Sicherheits Operations Teams von der Menge der ausgelösten Warnungen überfordert fühlen. Die Funktionen für die automatische Untersuchung und Reaktion (Air) in Office 365 Advanced Threat Protection (Office 365 ATP) können helfen. 

Mit Air kann Ihr Security Operations-Team effizienter und effektiver arbeiten. Air-Funktionen umfassen automatisierte Ermittlungsprozesse als Reaktion auf bekannte Bedrohungen, die heute vorhanden sind. Geeignete Korrekturaktionen warten auf die Genehmigung, sodass Ihr Sicherheits Betriebsteam auf erkannte Bedrohungen reagieren kann. 

Dieser Artikel bietet eine Übersicht über Air. Wenn Sie mit der Verwendung von Air beginnen möchten, finden Sie weitere Informationen unter [Automatisches untersuchen und reagieren auf Bedrohungen](office-365-air.md).

## <a name="at-a-high-level"></a>Auf einer hohen Ebene

Wenn Warnungen ausgelöst werden, treten Sicherheits-Textbuch in Kraft. Je nach Situation kann ein [automatischer Ermittlungsprozess](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) beginnen. Während und nach einer automatischen Untersuchung werden [Korrekturaktionen](air-remediation-actions.md) empfohlen. In Office 365 Advanced Threat Protection werden keine Aktionen automatisch durchgeführt. Ihr Security Operations-Team überprüft, und [genehmigt oder lehnt dann jede Korrekturaktion](air-review-approve-pending-completed-actions.md)ab. Wenn alle nach einer Untersuchung durchgeführten Aktionen genehmigt oder abgelehnt werden, wird die Untersuchung abgeschlossen. Alle diese Aktivitäten werden im Security & Compliance Center nachverfolgt und angezeigt (Weitere Informationen finden Sie unter [Details einer Untersuchung anzeigen](air-view-investigation-results.md#view-details-of-an-investigation)).

Die folgenden Abschnitte enthalten weitere Informationen zu Warnungen, Sicherheits handschreibungen und Beispiele für Luft in Aktion.

## <a name="alerts"></a>Warnungen

[Warnungen](../../compliance/alert-policies.md#viewing-alerts) stellen Auslöser für Sicherheitsvorgänge-Team Workflows für die Vorfall Antwort dar. Priorisieren des richtigen Warnungs Satzes für die Untersuchung, wobei sichergestellt wird, dass keine Bedrohungen unbehandelt sind, ist eine Herausforderung. Wenn Untersuchungen zu Warnungen manuell durchgeführt werden, müssen Sicherheits Betriebsteams Entitäten (beispielsweise Inhalte, Geräte und Benutzer), die von Bedrohungen bedroht sind, jagen und korrelieren. Solche Aufgaben und Workflows können sehr zeitaufwendig sein und umfassen mehrere Tools und Systeme. Mit Air werden Untersuchung und Reaktion für Sicherheitsereignisse automatisiert, indem wichtige Sicherheits-und Bedrohungsmanagement-Warnungen automatisch Sicherheitsantwort-Textbuch auslösen. 

Derzeit werden Warnungen, die aus den folgenden Arten von Warnungsrichtlinien generiert werden, automatisch untersucht:  

- Ein potenziell böswilliger URL-Klick wurde erkannt.
- Vom Benutzer als Phishing gemeldete e-Mail`*`
- E-Mail-Nachrichten mit Schadsoftware nach der Zustellung entfernt`*`
- E-Mail-Nachrichten mit Phishing-URLs nach der Zustellung entfernt`*`
- Erkannte verdächtige e-Mail-Sende Muster`#`
- Benutzer vom Senden von e-Mails eingeschränkt`#`

> [!NOTE]
> Die mit einem Sternchen () markierten Warnungen `*` werden in den jeweiligen Warnungsrichtlinien im Security & Compliance Center mit einem *Informations* Schweregrad versehen, wobei e-Mail-Benachrichtigungen deaktiviert sind. E-Mail-Benachrichtigungen können über die [Warnungsrichtlinien Konfiguration](../../compliance/alert-policies.md#alert-policy-settings)aktiviert werden. Mit einem Hash () gekennzeichnete Warnungen `#` sind allgemein verfügbare Warnungen für öffentliche Vorschau-Textbuch.

Um Warnungen anzuzeigen, wählen Sie im Security & Compliance **Center Benachrichtigungen**  >  **anzeigen Warnungen**aus. Wählen Sie eine Warnung aus, um die Details anzuzeigen, und verwenden Sie dann den Link **Untersuchung anzeigen** , um zur entsprechenden [Untersuchung](air-view-investigation-results.md#investigation-graph)zu gelangen.  

> [!NOTE]
> Informationswarnungen werden standardmäßig in der Warnungsansicht ausgeblendet. Um diese anzuzeigen, ändern Sie die Warnungsfilterung so, dass Sie Informationswarnungen einschließt.

Wenn Ihre Organisation ihre Sicherheitswarnungen über ein Warnungsverwaltungssystem, ein Dienst Verwaltungssystem oder ein System für die Verwaltung von Sicherheitsinformationen und Ereignisverwaltung verwaltet, können Sie Warnungen entweder per e-Mail-Benachrichtigung oder über die [Office 365 Verwaltungs Aktivitäts-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)an dieses System senden. Die Untersuchung von Benachrichtigungs Benachrichtigungen per e-Mail oder API enthält Links für den Zugriff auf die Warnungen im Security & Compliance Center, sodass der zugewiesene Sicherheitsadministrator schnell zu der Untersuchung navigieren kann.

![Warnungen, die mit Untersuchungen verknüpft sind](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Sicherheits-Manuskripte

Sicherheits-Textbuch sind Back-End-Richtlinien, die im Mittelpunkt der Automatisierung in Office Advanced Threat Protection und Microsoft Threat Protection stehen. Die in Air bereitgestellten Sicherheits-Textbuch basieren auf gängigen realen Sicherheitsszenarien und werden auf der Grundlage von Feedback aus Sicherheits Betriebsteams entwickelt. Ein Sicherheits Textbuch wird automatisch gestartet, wenn in Ihrer Organisation bestimmte Warnungen ausgelöst werden. Sobald die Warnung ausgelöst wird, wird das zugehörige Textbuch vom System für die automatische Untersuchung und Reaktion (Air) ausgeführt. Die Untersuchung erfolgt durch eine Analyse der Warnung basierend auf dem Textbuch der jeweiligen Warnung, wobei alle zugehörigen Metadaten (einschließlich e-Mail-Nachrichten, Benutzer, Subjekte, Absender usw.) untersucht werden. Basierend auf den Ergebnissen der Untersuchung des Textbuch empfiehlt Air eine Reihe von Aktionen, die das Sicherheitsteam Ihrer Organisation ausführen kann, um die Bedrohung zu steuern und zu mindern. 

Die Sicherheits-Textbuch-Dokumente, die Sie mit Air erhalten, wurden entwickelt, um die häufigsten Bedrohungen zu bewältigen, mit denen Organisationen heute mit e-Mails konfrontiert sind. Sie basieren auf Eingaben aus Sicherheits-und Vorfall Reaktions Teams, einschließlich Personen, die zur Verteidigung von Microsoft und den Ressourcen unserer Kunden beitragen.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Sicherheits-Textbuch-Rollen in Phasen

Im Rahmen von Air werden Sicherheits-Textbuch in Phasen ausgerollt. Phase 1 ist jetzt allgemein verfügbar und enthält mehrere Textbuch, die Empfehlungen für Aktionen enthalten, die Sicherheitsadministratoren überprüfen und genehmigen können:

- Vom Benutzer gemeldete Phishing-Nachricht
- Änderung des URL-Klick-Urteils
- Erkannte Schadsoftware nach der Zustellung (Malware zap)
- Phishing-Erkennung nach der Zustellung zap (Phishing zap)

Phase 1 enthält auch Unterstützung für von Administratoren ausgelöste e-Mail-Untersuchungen (mithilfe von [Threat Explorer](threat-explorer.md)).

Phase 2 ist jetzt mit den folgenden Textbuch in der **öffentlichen Vorschau**fortgeschritten, bietet Empfehlungen für Aktionen und unterstützt Sicherheitsadministratoren bei der Untersuchung von Problemen:

- Als kompromittiert gemeldeter Benutzer (öffentliche Vorschau)

Weitere Textbuch werden als abgeschlossen veröffentlicht. Besuchen Sie die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap) , um zu sehen, was noch geplant ist und demnächst verfügbar ist.

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
- Das Signal wird für andere Plattformen wie [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)freigegeben.
- Es wird festgestellt, ob Benutzer in verdächtigen e-Mail-Nachrichten auf böswillige Links geklickt haben.
- Eine Überprüfung erfolgt über Exchange Online Protection ([EoP](exchange-online-protection-overview.md)) und Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)), um zu sehen, ob andere ähnliche Nachrichten von Benutzern gemeldet werden.
- Eine Überprüfung wird durchgeführt, um festzustellen, ob ein Benutzer kompromittiert wurde. Bei dieser Überprüfung werden Signale in Bezug auf Office 365, [Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security)und [Azure-Active Directory](https://docs.microsoft.com/azure/active-directory)verwendet, sodass alle zugehörigen Anomalien bei Benutzeraktivitäten korreliert werden.

Während der Jagd Phase werden Risiken und Bedrohungen verschiedenen Jagd Schritten zugeordnet. 

Die Korrektur ist die letzte Phase des Textbuch. In dieser Phase werden korrekturschritte basierend auf den Ermittlungs-und Jagd Phasen durchgeführt. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Beispiel: ein Sicherheitsadministrator löst eine Untersuchung mit Threat Explorer aus.

Zusätzlich zu den automatisierten Untersuchungen, die durch eine Warnung ausgelöst werden, kann das Sicherheits Betriebsteam Ihrer Organisation eine automatisierte Untersuchung aus einer Ansicht in [Threat Explorer](threat-explorer.md)auslösen.

Nehmen wir beispielsweise an, dass Sie die **Malware** Ansicht im Threat Explorer verwenden. Mithilfe der Registerkarten unter dem Diagramm Wählen Sie die Registerkarte **e-Mail** aus. Wenn Sie ein oder mehrere Elemente in der Liste auswählen, wird die Schaltfläche **+ Aktionen** aktiviert. 

![Explorer mit ausgewählten Nachrichten](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Über das Menü **Aktionen** können Sie **Untersuchung auslösen**auswählen.

![Menü "Aktionen" für ausgewählte Nachrichten](../../media/explorer-malwareview-selectedemails-actions.jpg)

Ähnlich wie Textbuch, die durch eine Warnung ausgelöst werden, umfassen automatische Untersuchungen, die aus einer Ansicht im Explorer ausgelöst werden, eine Stamm Ermittlung, Schritte zum Identifizieren und Korrelieren von Bedrohungen sowie Empfohlene Aktionen zur Minderung dieser Bedrohungen.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Beispiel: ein Security Operations-Team integriert Air mit ihren Siem-Funktionen mithilfe der Office 365-Verwaltungs Aktivitäts-API

Zu den Air-Funktionen in Office 365 ATP gehören [Berichte & Details](air-view-investigation-results.md) , mit denen Sicherheitsaufgaben-Teams Bedrohungen überwachen und adressieren können. Sie können aber auch Air-Funktionen in andere Lösungen integrieren. Beispiele hierfür sind ein System für Sicherheitsinformationen und Ereignisverwaltung (SIEM), ein Fallverwaltungssystem oder eine benutzerdefinierte Berichtslösung. Diese Art der Integration kann mithilfe der [Office 365-Verwaltungs Aktivitäts-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)erfolgen. 

Beispielsweise hat eine Organisation kürzlich eine Möglichkeit für Ihr Sicherheits Betriebsteam eingerichtet, Benutzer gemeldete Phishing-Benachrichtigungen anzuzeigen, die bereits von Air verarbeitet wurden. Ihre Lösung integriert relevante Warnungen in den Siem-Server der Organisation und Ihr Fallverwaltungssystem. Die Lösung reduziert erheblich die Anzahl falsch positiver Ergebnisse, sodass Ihr Sicherheits Betriebsteam sich Zeit und Aufwand auf reale Bedrohungen konzentrieren kann. Weitere Informationen zu dieser benutzerdefinierten Lösung finden Sie unter [Tech Community Blog: verbessern der Effektivität ihrer SoC mit Office 365 ATP und der O365-Verwaltungs-API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-step"></a>Nächster Schritt

- [Erste Schritte mit Air](office-365-air.md)

## <a name="see-also"></a>Weitere Artikel

- [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide)