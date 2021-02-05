---
title: Fallstudie – Contoso konfiguriert schnell eine Richtlinie für anstößige Sprache für Microsoft Teams, Exchange und Yammer Kommunikation
description: Eine Fallstudie für Contoso und wie sie schnell eine Richtlinie zur Kommunikationskonformität konfigurieren, um in Microsoft Teams, Exchange Online und anderen Anwendungen auf anstößige Yammer überwachen.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 5925ad7641370b26d0a272968a13028b74b81ef4
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50109996"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>Fallstudie – Contoso konfiguriert schnell eine Richtlinie für anstößige Sprache für Microsoft Teams, Exchange und Yammer Kommunikation

Die Kommunikationskonformität in Microsoft 365 trägt dazu bei, Kommunikationsrisiken zu minimieren, indem Sie unangemessene Nachrichten in Ihrer Organisation erkennen, erfassen und auf diese weise agieren können. Mit vordefinierten und benutzerdefinierten Richtlinien können Sie die interne und externe Kommunikation auf Richtlinien übereinstimmungen überprüfen, damit sie von bestimmten Prüfern überprüft werden können. Prüfer können gescannte E-Mails, Microsoft Teams, Yammer oder Drittanbieterkommunikationen in Ihrer Organisation untersuchen und geeignete Abhilfemaßnahmen ergreifen, um sicherzustellen, dass sie den Nachrichtenstandards Ihrer Organisation entsprechen.

Die Contoso Corporation ist eine fiktive Organisation, die schnell eine Richtlinie zur Überwachung auf anstößige Sprache konfigurieren muss. Sie haben Microsoft 365 in erster Linie für E-Mail, Microsoft Teams und Yammer für ihre Benutzer verwendet, haben jedoch neue Anforderungen, um Unternehmensrichtlinien in Der Umgebung von Belästigungen am Arbeitsplatz durchzusetzen. Contoso-IT-Administratoren und Compliancespezialisten verfügen über grundlegende Kenntnisse der Grundlagen der Arbeit mit Microsoft 365 und suchen nach end-to-end-Anleitungen für den schnellen Einstieg in die Kommunikationskonformität.

In dieser Fallstudie werden die Grundlagen für die schnelle Konfiguration einer Richtlinie zur Kommunikationscompliance zur Überwachung der Kommunikation auf anstößige Sprache behandelt. Diese Anleitung enthält:

- Schritt 1 – Planen der Kommunikationscompliance
- Schritt 2 – Zugreifen auf die Kommunikationscompliance in Microsoft 365
- Schritt 3 – Konfigurieren von Voraussetzungen und Erstellen einer Richtlinie zur Kommunikationscompliance
- Schritt 4 – Untersuchung und Behebung von Warnungen

## <a name="step-1-planning-for-communication-compliance"></a>Schritt 1: Planen der Kommunikationskonformität

Contoso-IT-Administratoren und Compliancespezialisten teilnahmen an Online-Webinaren zu Compliancelösungen in Microsoft 365 und entschieden, dass Richtlinien zur Kommunikationskonformität ihnen helfen, die aktualisierten Unternehmensrichtlinienanforderungen zur Verringerung von Belästigungen am Arbeitsplatz zu erfüllen. Zusammen haben sie einen Plan zum Erstellen und Aktivieren einer Kommunikationskonformitätsrichtlinie entwickelt, die auf anstößige Sprache für Chats überwacht, die in Microsoft Teams gesendet werden, private Nachrichten und Communityunterhaltungen in Yammer und in E-Mail-Nachrichten, die in Exchange Online gesendet werden. Ihr Plan umfasst die Identifizierung von:

- Die IT-Administratoren, die Zugriff auf kommunikationskonformitätsfeatures benötigen.
- Die Compliancespezialisten, die Kommunikationsrichtlinien erstellen und verwalten müssen.
- Die Compliancespezialisten und andere Kollegen in anderen Abteilungen (Personalwesen, Rechtsabteilung usw.), die Warnungen zur Kommunikationskonformität untersuchen und begleichen müssen.
- Die Benutzer, die für die Richtlinie für anstößige Sprachrichtlinien zur Kommunikationskonformität im Bereich sind.

### <a name="licensing"></a>Lizenzierung

Der erste Schritt besteht in der Bestätigung, dass die Microsoft 365-Lizenzierung von Contoso Unterstützung für die Kommunikationskonformitätslösung umfasst. Um auf die Kommunikationskonformität zugreifen und diese verwenden zu können, müssen contoso-IT-Administratoren überprüfen, ob Contoso über eine der folgenden Optionen verfügt:

- Microsoft 365 E5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 E3-Abonnement + das Microsoft 365 E5 Compliance-Add-On
- Microsoft 365 E3-Abonnement + das Microsoft 365 E5 Insider Risk Management-Add-On
- Microsoft 365 A5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 A3-Abonnement + das Microsoft 365 A5 Compliance-Add-On
- Microsoft 365 A3-Abonnement + das Microsoft 365 A5 Insider Risk Management-Add-On
- Microsoft 365 -G5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 -G5-Abonnement + das Microsoft 365 G5 Compliance-Add-On
- Microsoft 365 -G5-Abonnement + das Microsoft 365 G5-Add-On "Insider Risk Management"
- Office 365 Enterprise E5-Abonnement (kostenpflichtig oder Testversion)
- Office 365 Enterprise E3-Abonnement + das Office 365 Advanced Compliance-Add-On (nicht mehr verfügbar für neue Abonnements, siehe Hinweis)

Außerdem müssen sie bestätigen, dass Benutzern, die in Richtlinien zur Kommunikationskonformität enthalten sind, eine der oben genannten Lizenzen zugewiesen werden muss.

>[!IMPORTANT]
>Office 365 Advanced Compliance wird nicht mehr als eigenständiges Abonnement verkauft. Wenn aktuelle Abonnements ablaufen, sollten Kunden zu einem der oben genannten Abonnements überwechseln, das dieselben oder zusätzliche Compliancefeatures enthält.

Contoso-IT-Administratoren gehen wie folgt vor, um die Lizenzierungsunterstützung für Contoso zu überprüfen:

1. It administrators sign in to the **Microsoft 365 admin center** [( https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center**  >  **Billing**  >  **Licenses**.

2. Hier bestätigen sie, dass sie über eine der [Lizenzoptionen verfügen,](communication-compliance-configure.md#subscriptions-and-licensing) die Unterstützung für die Kommunikationskonformität umfassen.

![Lizenzierung der Kommunikationskonformität](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Berechtigungen für die Kommunikationskonformität

Es gibt fünf Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Kommunikationskonformitätsfeatures verwendet werden. Um  die Kommunikationskonformität als Menüoption im Microsoft 365 Compliance Center verfügbar zu machen und mit diesen Konfigurationsschritten fortzufahren, wird den Administratoren von Contoso die Administratorrolle *"Kommunikationskonformität"* zugewiesen.

Contoso entscheidet sich  für die Verwendung der Rollengruppe "Kommunikationskonformität", um der Gruppe alle Kommunikationskonformitätsadministratoren, Analysten, Ermittler und Betrachter zuzuordnen. Dies erleichtert Contoso den schnellen Einstieg und erfüllt die Complianceverwaltungsanforderungen am besten.

|**Rolle**|**Rollenberechtigungen**|
|:-----|:-----|
| **Kommunikationskonformität** | Verwenden Sie diese Rollengruppe, um die Kommunikationskonformität für Ihre Organisation in einer einzigen Gruppe zu verwalten. Durch Hinzufügen aller Benutzerkonten für designierte Administratoren, Analysten, Ermittler und Betrachter können Sie Berechtigungen zur Kommunikationskonformität in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für die Kommunikationskonformität. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit der Kommunikationskonformität zu beginnen, und ist gut geeignet für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. |
| **Kommunikationskonformitätsadministrator** | Verwenden Sie diese Rollengruppe, um zunächst die Kommunikationskonformität zu konfigurieren und später Administratoren für die Kommunikationskonformität in eine definierte Gruppe zu untergtrennen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien zur Kommunikationskonformität, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. Benutzer, die dieser Rollengruppe zugewiesen sind, können keine Benachrichtigungen anzeigen. |
| **Communication Compliance Analyst** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die als Kommunikations-Compliance-Analysten fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien anzeigen, in denen sie als Prüfer zugewiesen sind, Nachrichtenmetadaten (keine Nachrichteninhalte) anzeigen, an zusätzliche Prüfer eskalieren oder Benachrichtigungen an Benutzer senden. Analysten können ausstehende Warnungen nicht beheben. |
| **Kommunikations-Compliance-Ermittler** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die als Ermittler der Kommunikationskonformität fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Nachrichtenmetadaten und -inhalte anzeigen, an weitere Prüfer eskalieren, zu einem Advanced eDiscovery-Fall eskalieren, Benachrichtigungen an Benutzer senden und die Warnung auflösen. |
| **Communication Compliance Viewer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die Kommunikationsberichte verwalten. Benutzer, die dieser Rollengruppe zugewiesen sind, können auf der Startseite für die Kommunikationskonformität auf alle Berichts widgets zugreifen und alle Berichte zur Kommunikationskonformität anzeigen. |

1. Contoso-IT-Administratoren melden sich auf der Berechtigungsseite des **Office 365 Security & Compliance Centers** an [(verwenden https://protection.office.com/permissions)](https://protection.office.com/permissions) Die Anmeldeinformationen für ein globales Administratorkonto verwenden und den Link zum Anzeigen und Verwalten von Rollen in Microsoft 365 auswählen.
2. Im **Security & Compliance Center** wechseln sie  zu "Berechtigungen" und wählen den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.
3. Die Administratoren  wählen die Rollengruppe "Kommunikationskonformität" und dann **"Rollengruppe bearbeiten" aus.**
4. Die Administratoren wählen **im linken Navigationsbereich** "Mitglieder auswählen" und dann "Bearbeiten" **aus.**
5. Sie wählen **"Hinzufügen"** aus und aktivieren dann das Kontrollkästchen für alle Contoso-Benutzer, die die Kommunikationskonformität verwalten, Warnungen untersuchen und überprüfen.
6. Die Administratoren wählen **"Hinzufügen"** und dann **"Fertig" aus.**
7. Sie wählen **"Speichern"** aus, um der Rollengruppe Benutzer von Contoso hinzuzufügen. Sie wählen **"Schließen"** aus, um die Schritte ausführen zu können.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>Schritt 2: Zugreifen auf Kommunikationskonformität in Microsoft 365

Nach dem Konfigurieren der Berechtigungen für die Kommunikationskonformität können contoso-IT-Administratoren und Compliance-Experten, die der Rollengruppe "Kommunikationskonformität" zugewiesen sind, auf die Kommunikationskonformitätslösung in Microsoft 365 zugreifen. Contoso-IT-Administratoren und Compliancespezialisten haben mehrere Möglichkeiten, auf die Kommunikationskonformität zu zugreifen und mit dem Erstellen einer neuen Richtlinie zu beginnen:

- Direkt von der Kommunikationskonformitätslösung ausgehend
- Beginnend mit dem Microsoft 365 Compliance Center
- Beginnend mit dem Microsoft 365-Lösungskatalog
- Beginnend mit dem Microsoft 365 Admin Center

### <a name="starting-directly-from-the-communication-compliance-solution"></a>Direkt von der Kommunikationskonformitätslösung ausgehend

Die schnellste Möglichkeit, auf die Lösung zu  zugreifen, besteht in der direkten Anmeldung bei der Kommunikationskonformitätslösung ( <https://compliance.microsoft.com/supervisoryreview> ). Über diesen Link werden Contoso-IT-Administratoren und Compliancespezialisten an das Übersichtsdashboard zur Kommunikationskonformität geleitet, wo Sie den Status von Warnungen schnell überprüfen und neue Richtlinien aus den vordefinierten Vorlagen erstellen können.

![Übersicht der Kommunikationscompliance](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>Beginnend mit dem Microsoft 365 Compliance Center

Eine weitere einfache Möglichkeit für Contoso-IT-Administratoren und Compliancespezialisten, auf die Kommunikationskonformitätslösung zu zugreifen, besteht in der direkten Anmeldung beim **Microsoft 365 Compliance Center** [( https://compliance.microsoft.com)](https://compliance.microsoft.com). Nach der Anmeldung müssen die Benutzer lediglich das Steuerelement **Alle anzeigen** auswählen, um alle Compliance-Lösungen anzuzeigen, und dann die Lösung **Kommunikationscompliance** auswählen, um zu beginnen.

![Compliance Center](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>Beginnend mit dem Microsoft 365-Lösungskatalog

Contoso-IT-Administratoren und Compliancespezialisten können auch auf die Kommunikationskonformitätslösung zugreifen, indem Sie den Microsoft 365-Lösungskatalog auswählen. Durch Auswählen  **des** Abschnitts "Katalog" im Abschnitt "Lösungen" im linken Navigationsbereich im **Microsoft 365 Compliance Center** können sie den Lösungskatalog mit allen Microsoft 365-Compliancelösungen öffnen. Beim Scrollen nach unten zum **Abschnitt "Insider-Risikomanagement"** können Contoso-IT-Administratoren die Kommunikationskonformität für die ersten Schritte auswählen. Contoso-IT-Administratoren entscheiden sich auch für die Verwendung des Steuerelements "In Navigation anzeigen", um die Kommunikationskonformitätslösung für den schnelleren Zugriff an den linken Navigationsbereich zu anheften, wenn sie sich in Zukunft anmelden.

![Lösungskatalog](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>Beginnend mit dem Microsoft 365 Admin Center

Um beim Starten vom Microsoft 365 Admin Center aus auf die Kommunikationskonformität zu zugreifen, melden sich contoso-IT-Administratoren und Compliancespezialisten beim Microsoft 365 Admin Center [an https://admin.microsoft.com) (](https://admin.microsoft.com) und navigieren Sie zu Microsoft **365 Admin Center**  >  **Compliance**.

![Link zur Kommunikationskonformität](../media/communication-compliance-case-compliance-link.png)

Diese Aktion öffnet das **Office 365 Security and Compliance Center** und muss den Link zum Microsoft **365 Compliance Center** auswählen, der im Banner oben auf der Seite bereitgestellt wird.

![Office 365 Security and Compliance Center](../media/communication-compliance-case-scc.png)

Im **Microsoft 365 Compliance Center** wählen Contoso -IT-Administratoren "Alle anzeigen" aus, um die vollständige Liste der Compliancelösungen anzeigen. 

![Menü "Kommunikationskonformität"](../media/communication-compliance-case-show-all.png)

Nachdem Sie **"Alle anzeigen"** ausgewählt haben, können die Contoso-IT-Administratoren auf die Kommunikationskonformitätslösung zugreifen.

![Übersicht der Kommunikationscompliance](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Schritt 3: Konfigurieren der Voraussetzungen und Erstellen einer Richtlinie zur Kommunikationskonformität

Um mit einer Richtlinie zur Kommunikationscompliance zu beginnen, müssen IT-Administratoren von Contoso mehrere Voraussetzungen konfigurieren, bevor sie die neue Richtlinie zur Überwachung auf anstößige Sprache einrichten können. Nachdem diese Voraussetzungen erfüllt sind, können die IT-Administratoren und Compliance-Spezialisten von Contoso die neue Richtlinie konfigurieren, und die Compliance-Spezialisten können mit der Untersuchung und Behebung aller generierten Warnungen beginnen.

### <a name="enabling-auditing-in-microsoft-365"></a>Aktivieren der Überwachung in Microsoft 365

Für die Kommunikationscompliance sind Überwachungsprotokolle erforderlich, um Warnungen anzuzeigen und die von den Prüfern ergriffenen Abhilfemaßnahmen zu verfolgen. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten im Zusammenhang mit einer definierten Organisationsrichtlinie oder immer dann, wenn es eine Änderung einer Richtlinie zur Kommunikationscompliance gibt.

Die IT-Administratoren von Contoso überprüfen und vervollständigen die [Schritt-für-Schritt-Anweisungen](turn-audit-log-search-on-or-off.md) zum Aktivieren der Überwachung. Daraufhin teilt ihnen eine Meldung mit, dass das Überwachungsprotokoll vorbereitet wird und sie in ein paar Stunden nach Abschluss der Vorbereitung eine Suche durchführen können. Die IT-Administratoren von Contoso müssen diese Aktion nur einmal ausführen.

### <a name="configuring-yammer-tenant-for-native-mode"></a>Konfigurieren Yammer Mandanten für den nativen Modus

Die Kommunikationskonformität setzt voraus, dass Yammer Mandanten für eine Organisation sich im nativen Modus befindet, um in privaten Nachrichten und öffentlichen Communityunterhaltungen auf anstößige Sprache zu überwachen.

Contoso-IT-Administratoren stellen sicher, dass sie die Informationen im Artikel "Übersicht über den Yammer nativen Modus [in Microsoft 365"](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) lesen und die Schritte zum Ausführen des Migrationstools im Artikel "Konfigurieren ihres Yammer-Netzwerks für den nativen Modus für [Microsoft 365"](/yammer/configure-your-yammer-network/native-mode) ausführen.

### <a name="setting-up-a-group-for-in-scope-users"></a>Einrichten einer Gruppe für Benutzer im Bereich

Die Compliancespezialisten von Contoso möchten alle Benutzer zur Kommunikationsrichtlinie hinzufügen, die auf anstößige Sprache überwacht wird. Sie könnten jedes Benutzerkonto separat zur Richtlinie hinzufügen, haben sich jedoch entschieden, dass es  viel einfacher ist und Zeit für die Verwendung einer Verteilergruppe "Alle Benutzer" für die Benutzer für diese Richtlinie gespart wird.

Sie müssen eine neue Gruppe erstellen, die alle Benutzer von Contoso enthält, damit sie die folgenden Schritte ausführen:

1. Contoso IT Administrators IT sign in to the **Microsoft 365 admin center** [ https://admin.microsoft.com) (](https://admin.microsoft.com) and navigate to Microsoft **365 admin center**  >  **Groups**  >  .
2. Sie wählen **"Gruppe hinzufügen"** aus und schließen den Assistenten ab, um eine neue *Microsoft 365-Gruppe* oder *Verteilergruppe zu erstellen.*

    ![Gruppen](../media/communication-compliance-case-all-employees.png)

3. Nachdem die neue Gruppe erstellt wurde, müssen alle Contoso-Benutzer zu der neuen Gruppe hinzugefügt werden. Sie öffnen das **Exchange Admin Center** [( https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) und navigieren zu **Empfängergruppen im Exchange Admin**  >    >  **Center.** Die Contoso-IT-Administratoren wählen den  Mitgliedschaftsbereich und die  neue Gruppe "Alle Mitarbeiter" aus, die sie erstellt haben, und wählen das Steuerelement "Bearbeiten" aus, um alle Benutzer von Contoso zur neuen Gruppe im Assistenten hinzuzufügen.

    ![Exchange Admin-Center](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>Erstellung der Richtlinie zur Überwachung auf anstößige Sprache

Wenn alle Voraussetzungen erfüllt sind, sind die IT-Administratoren und die Compliance-Spezialisten von Contoso bereit, die Richtlinien für die Kommunikationscompliance zur Überwachung auf anstößige Sprache zu konfigurieren. Mit der neuen Richtlinienvorlage für anstößige Sprache ist die Konfiguration dieser Richtlinie einfach und schnell.

1. Die IT-Administratoren und Compliance-Spezialisten von Contoso melden sich beim **Microsoft 365 Compliance Center** an und wählen im linken Navigationsbereich die Option **Kommunikationscompliance** aus. Mit dieser Aktion wird das Dashboard **Übersicht** geöffnet, das Schnellverknüpfungen für Richtlinienvorlagen zur Kommunikationscompliance enthält. Sie wählen die Vorlage **Überwachung auf anstößige Sprache**, indem sie für die Vorlage **Erste Schritte** wählen.

    ![Vorlage für anstößige Sprache der Kommunikationskonformität](../media/communication-compliance-case-template.png)

2. Im Assistenten für Richtlinienvorlagen arbeiten die IT-Administratoren und Compliance-Spezialisten von Contoso zusammen, um die drei erforderlichen Felder auszufüllen: **Richtliniennamen**, **Zu beaufsichtigende Benutzer oder Gruppen** und **Prüfer**.
3. Da der Assistent für Richtlinien bereits einen Namen für die Richtlinie vorgeschlagen hat, beschließen die IT-Administratoren und Compliance-Spezialisten, den vorgeschlagenen Namen beizubehalten und sich auf die übrigen Bereiche zu konzentrieren. Sie wählen die Gruppe  *"Alle* Benutzer" für die Zu überwachenden Benutzer oder Gruppen und die Compliancespezialisten aus, die Richtlinienwarnungen für das Feld "Prüfer" untersuchen und **beaufsichtigen** sollen. Der letzte Schritt zum Konfigurieren der Richtlinie und zum Sammeln von Warnungsinformationen besteht in der Auswahl von **"Richtlinie erstellen".**

    ![Assistent für kommunikationskonforme anstößige Sprache](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>Schritt 4: Untersuchen und Behebung von Warnungen

Nun, da die Richtlinie zur Überwachung der Kommunikationscompliance auf anstößige Sprache konfiguriert ist, besteht der nächste Schritt für die Compliance-Spezialisten von Contoso darin, alle durch die Richtlinie erzeugten Warnungen zu untersuchen und zu beheben. Es wird bis zu 24 Stunden dauern, bis die Richtlinie die Kommunikationen in allen Kommunikationskanälen vollständig verarbeitet hat und die Warnungen im **Dashboard „Warnung“** angezeigt werden.

Nachdem Warnungen generiert wurden, folgen die Compliancespezialisten von Contoso den [Workflowanweisungen,](communication-compliance-investigate-remediate.md) um Probleme mit anstößigen Sprachen zu untersuchen und zu beheben.