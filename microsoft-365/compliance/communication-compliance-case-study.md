---
title: Fallstudie – Contoso konfiguriert schnell eine Richtlinie für anstößige Sprache für Microsoft Teams-, Exchange- und Yammer-Kommunikation
description: Eine Fallstudie für Contoso und wie sie schnell eine Richtlinie zur Kommunikationscompliance konfigurieren, um in Microsoft Teams, Exchange Online und Yammer Kommunikation auf anstößige Sprache zu überwachen.
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
ms.openlocfilehash: b44977252b18c29a5f05a67f4ffbdb7dc85a8188
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256783"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>Fallstudie – Contoso konfiguriert schnell eine Richtlinie für anstößige Sprache für Microsoft Teams-, Exchange- und Yammer-Kommunikation

Die Kommunikationscompliance in Microsoft 365 trägt dazu bei, Kommunikationsrisiken zu minimieren, indem es Ihnen hilft, unangemessene Nachrichten in Ihrer Organisation zu erkennen, zu erfassen und darauf zu reagieren. Vordefinierte und benutzerdefinierte Richtlinien ermöglichen es Ihnen, die interne und externe Kommunikation auf Richtlinienübereinstimmungen zu überprüfen, damit sie von bestimmten Prüfern überprüft werden können. Prüfer können gescannte E-Mails, Microsoft Teams, Yammer oder Drittanbieterkommunikationen in Ihrer Organisation untersuchen und geeignete Korrekturmaßnahmen ergreifen, um sicherzustellen, dass sie den Nachrichtenstandards Ihrer Organisation entsprechen.

Die Contoso Corporation ist eine fiktive Organisation, die schnell eine Richtlinie zur Überwachung auf anstößige Sprache konfigurieren muss. Sie haben Microsoft 365 hauptsächlich für E-Mails, Microsoft Teams und Yammer Unterstützung für ihre Benutzer verwendet, haben aber neue Anforderungen, um Unternehmensrichtlinien im Zusammenhang mit Belästigung am Arbeitsplatz durchzusetzen. IT-Administratoren und Compliance-Spezialisten von Contoso verfügen über ein grundlegendes Verständnis der Grundlagen der Arbeit mit Microsoft 365 und suchen nach end-to-end-Anleitungen, wie Sie schnell mit der Kommunikationscompliance beginnen können.

In dieser Fallstudie werden die Grundlagen für die schnelle Konfiguration einer Richtlinie zur Kommunikationscompliance zur Überwachung der Kommunikation auf anstößige Sprache behandelt. Diese Anleitung enthält:

- Schritt 1 – Planen der Kommunikationscompliance
- Schritt 2 – Zugreifen auf die Kommunikationscompliance in Microsoft 365
- Schritt 3 – Konfigurieren von Voraussetzungen und Erstellen einer Richtlinie zur Kommunikationscompliance
- Schritt 4 – Untersuchung und Behebung von Warnungen

## <a name="step-1-planning-for-communication-compliance"></a>Schritt 1: Planen der Kommunikationscompliance

IT-Administratoren und Compliance-Spezialisten von Contoso besuchten Online-Webinare zu Compliancelösungen in Microsoft 365 und beschlossen, dass Richtlinien zur Kommunikationscompliance ihnen helfen, die aktualisierten Unternehmensrichtlinienanforderungen zur Verringerung von Belästigung am Arbeitsplatz zu erfüllen. Zusammen haben sie einen Plan entwickelt, um eine Richtlinie zur Kommunikationscompliance zu erstellen und zu aktivieren, die auf anstößige Sprache für Chats überwacht, die in Microsoft Teams, privaten Nachrichten und Community-Unterhaltungen in Yammer und in E-Mail-Nachrichten gesendet werden, die in Exchange Online gesendet werden. Ihr Plan umfasst die Identifizierung von:

- Die IT-Administratoren, die Zugriff auf Kommunikationscompliancefeatures benötigen.
- Die Compliance-Spezialisten, die Kommunikationsrichtlinien erstellen und verwalten müssen.
- Die Compliance-Spezialisten und andere Kollegen in anderen Abteilungen (Personalwesen, Recht usw.), die Warnungen zur Kommunikationscompliance untersuchen und beheben müssen.
- Die Benutzer, die für die Richtlinie für die Kommunikationscompliance anstößige Sprache gelten.

### <a name="licensing"></a>Lizenzierung

Der erste Schritt besteht darin, zu bestätigen, dass die Microsoft 365 Lizenzierung von Contoso Unterstützung für die Kommunikationscompliancelösung umfasst. Um auf die Kommunikationscompliance zuzugreifen und diese zu verwenden, müssen IT-Administratoren von Contoso überprüfen, ob Contoso über eine der folgenden Optionen verfügt:

- Microsoft 365 E5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 E3 Abonnement + das Microsoft 365 E5 Compliance-Add-On
- Microsoft 365 E3 Abonnement und das Add-On Microsoft 365 E5 Insider-Risikomanagement
- Microsoft 365 A5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 A3 Abonnement und das Microsoft 365 A5 Compliance-Add-On
- Microsoft 365 A3 Abonnement und das Add-On Microsoft 365 A5 Insider-Risikomanagement
- Microsoft 365 G5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 G5-Abonnement + das Microsoft 365 G5 Compliance-Add-On
- Microsoft 365 G5-Abonnement + das add-on Microsoft 365 G5 Insider Risk Management
- Office 365 Enterprise E5-Abonnement (kostenpflichtige version oder Testversion)
- Office 365 Enterprise E3-Abonnement + das Office 365 Advanced Compliance-Add-On (für neue Abonnements nicht mehr verfügbar, siehe Hinweis)

Sie müssen außerdem bestätigen, dass Benutzern, die in Richtlinien zur Kommunikationscompliance enthalten sind, eine der oben genannten Lizenzen zugewiesen werden muss.

> [!IMPORTANT]
> Office 365 Advanced Compliance wird nicht mehr als eigenständiges Abonnement verkauft. Wenn aktuelle Abonnements ablaufen, sollten Kunden auf eines der oben genannten Abonnements umsteigen, die die gleichen oder zusätzlichen Compliancefeatures enthalten.

It-Administratoren von Contoso führen die folgenden Schritte aus, um die Lizenzierungsunterstützung für Contoso zu überprüfen:

1. IT-Administratoren melden sich beim **Microsoft 365 Admin Center** an <https://admin.microsoft.com> und navigieren zu **Microsoft 365 Admin Center**  >  **Abrechnungslizenzen.**  >  

2. Hier bestätigen sie, dass sie über eine der [Lizenzoptionen](communication-compliance-configure.md#subscriptions-and-licensing) verfügen, die Unterstützung für die Kommunikationscompliance umfasst.

![Lizenzierung der Kommunikationscompliance](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Berechtigungen für die Kommunikationscompliance

Es gibt fünf Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Kommunikationscompliancefeatures verwendet werden. Um **die Kommunikationscompliance** in Microsoft 365 Compliance Center als Menüoption verfügbar zu machen und mit diesen Konfigurationsschritten fortzufahren, wird Contoso-Administratoren die Administratorrolle *"Kommunikationscompliance"* zugewiesen.

Contoso beschließt, die Rollengruppe *"Kommunikationscompliance"* zu verwenden, um der Gruppe alle Kommunikationscomplianceadministratoren, Analysten, Ermittler und Betrachter zuzuweisen. Dadurch ist es für Contoso einfacher, schnell zu beginnen und die Compliance-Verwaltungsanforderungen am besten zu erfüllen.

|**Rolle**|**Rollenberechtigungen**|
|:-----|:-----|
| **Kommunikationscompliance** | Verwenden Sie diese Rollengruppe, um die Kommunikationscompliance für Ihre Organisation in einer einzigen Gruppe zu verwalten. Indem Sie alle Benutzerkonten für bestimmte Administratoren, Analysten, Ermittler und Betrachter hinzufügen, können Sie Kommunikationscomplianceberechtigungen in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für die Kommunikationscompliance. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit der Kommunikationscompliance zu beginnen, und eignet sich gut für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. |
| **Kommunikationscompliance-Administrator** | Verwenden Sie diese Rollengruppe, um zunächst die Kommunikationscompliance zu konfigurieren und später die Administratoren der Kommunikationscompliance in eine definierte Gruppe zu unterteilen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien zur Kommunikationscompliance, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. Benutzer, die dieser Rollengruppe zugewiesen sind, können keine Meldungswarnungen anzeigen. |
| **Kommunikationscompliance-Analyst** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Kommunikationscomplianceanalysten fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien anzeigen, denen sie als Prüfer zugewiesen sind, Nachrichtenmetadaten anzeigen (nicht Nachrichteninhalte), an zusätzliche Prüfer eskalieren oder Benachrichtigungen an Benutzer senden. Analysten können ausstehende Warnungen nicht auflösen. |
| **Kommunikationscompliance-Ermittler** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Ermittler für die Kommunikationscompliance fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Nachrichtenmetadaten und Inhalte anzeigen, an zusätzliche Prüfer eskalieren, zu einem Advanced eDiscovery Fall eskalieren, Benachrichtigungen an Benutzer senden und die Warnung auflösen. |
| **Kommunikationscompliance-Anzeigender** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die Kommunikationsberichte verwalten. Benutzer, die dieser Rollengruppe zugewiesen sind, können auf der Startseite zur Kommunikationscompliance auf alle Berichterstellungs-Widgets zugreifen und alle Kommunikationscomplianceberichte anzeigen. |

1. It-Administratoren von Contoso melden sich bei der Berechtigungsseite **Office 365 Security & Compliance Center** an [( https://compliance.microsoft.com/permissions)](https://compliance.microsoft.com/permissions) verwenden Sie anmeldeinformationen für ein globales Administratorkonto, und wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Microsoft 365 aus.
2. Im **Security & Compliance Center** wechseln sie zu **"Berechtigungen",** und wählen den Link aus, um Rollen in Office 365 anzuzeigen und zu verwalten.
3. Die Administratoren wählen die Rollengruppe *"Kommunikationscompliance"* und dann die **Rollengruppe "Bearbeiten"** aus.
4. Die Administratoren wählen **Mitglieder** aus dem linken Navigationsbereich und dann **bearbeiten** aus.
5. Sie wählen **"Hinzufügen"** und dann das Kontrollkästchen für alle Contoso-Benutzer aus, die die Kommunikationscompliance verwalten, Warnungen untersuchen und überprüfen.
6. Die Administratoren wählen **"Hinzufügen"** und dann **"Fertig"** aus.
7. Sie wählen **"Speichern"** aus, um contoso-Benutzer zur Rollengruppe hinzuzufügen. Sie wählen **"Schließen"** aus, um die Schritte abzuschließen.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>Schritt 2: Zugreifen auf kommunikationscompliance in Microsoft 365

Nach dem Konfigurieren der Berechtigungen für die Kommunikationscompliance können IT-Administratoren und Compliance-Spezialisten von Contoso, die der Rollengruppe "Kommunikationscompliance" zugewiesen sind, auf die Kommunikationscompliancelösung in Microsoft 365 zugreifen. It-Administratoren und Compliance-Spezialisten von Contoso haben mehrere Möglichkeiten, auf Kommunikationscompliance zuzugreifen und mit dem Erstellen einer neuen Richtlinie zu beginnen:

- Direkt von der Kommunikationscompliancelösung aus
- Ab dem Microsoft 365 Compliance Center
- Ab dem Microsoft 365 Lösungskatalog
- Ab der Microsoft 365 Admin Center

### <a name="starting-directly-from-the-communication-compliance-solution"></a>Direkt von der Kommunikationscompliancelösung aus

Die schnellste Möglichkeit, auf die Lösung zuzugreifen, besteht darin, sich direkt bei der Lösung für **kommunikationscompliance** ( <https://compliance.microsoft.com/supervisoryreview> ) anzumelden. Über diesen Link werden IT-Administratoren und Compliance-Spezialisten von Contoso zum Dashboard "Übersicht über die Kommunikationscompliance" weitergeleitet, in dem Sie schnell den Status von Warnungen überprüfen und neue Richtlinien aus den vordefinierten Vorlagen erstellen können.

![Übersicht der Kommunikationscompliance](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>Ab dem Microsoft 365 Compliance Center

Eine weitere einfache Möglichkeit für IT-Administratoren und Compliance-Spezialisten von Contoso, auf die Lösung zur Kommunikationscompliance zuzugreifen, ist die direkte Anmeldung beim **Microsoft 365 Compliance Center** [( https://compliance.microsoft.com)](https://compliance.microsoft.com). Nach der Anmeldung müssen die Benutzer lediglich das Steuerelement **Alle anzeigen** auswählen, um alle Compliance-Lösungen anzuzeigen, und dann die Lösung **Kommunikationscompliance** auswählen, um zu beginnen.

![Compliance Center](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>Ab dem Microsoft 365 Lösungskatalog

IT-Administratoren und Compliance-Spezialisten von Contoso können auch auf die Kommunikationscompliancelösung zugreifen, indem sie den Microsoft 365 Lösungskatalog auswählen. Durch Auswahl des Abschnitts **"Katalog"** im Abschnitt **"Lösungen"** der linken Navigationsleiste im **Microsoft 365 Compliance Center** können sie den Lösungskatalog öffnen, in dem alle Microsoft 365 Compliancelösungen aufgeführt sind. Wenn Sie nach unten zum Abschnitt **"Insider-Risikomanagement"** scrollen, können IT-Administratoren von Contoso kommunikationscompliance auswählen, um zu beginnen. It-Administratoren von Contoso entscheiden sich auch für die Verwendung des Steuerelements "Im Navigation anzeigen", um die Kommunikationscompliancelösung an den linken Navigationsbereich zu anheften, damit sie sich in Zukunft schneller anmelden können.

![Lösungskatalog](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>Ab der Microsoft 365 Admin Center

Um auf die Kommunikationscompliance zuzugreifen, wenn Sie von der Microsoft 365 Admin Center aus beginnen, melden sich IT-Administratoren und Compliance-Spezialisten von Contoso beim Microsoft 365 Admin Center [an ( https://admin.microsoft.com)](https://admin.microsoft.com) und navigieren Sie zu **Microsoft 365 Admin Center**  >  **Compliance**.

![Link zur Kommunikationscompliance](../media/communication-compliance-case-compliance-link.png)

Mit dieser Aktion wird das **Office 365 Security and Compliance Center** geöffnet, und sie müssen den Link zu den **Microsoft 365 Compliance Center** auswählen, die im Banner oben auf der Seite angegeben sind.

![Office 365 Security and Compliance Center](../media/communication-compliance-case-scc.png)

Im **Microsoft 365 Compliance Center** wählen CONTOSO-IT-Administratoren **"Alle** anzeigen" aus, um die vollständige Liste der Compliancelösungen anzuzeigen.

![Menü "Kommunikationscompliance"](../media/communication-compliance-case-show-all.png)

Nachdem sie **"Alle anzeigen"** ausgewählt haben, können die IT-Administratoren von Contoso auf die Kommunikationscompliancelösung zugreifen.

![Übersicht der Kommunikationscompliance](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Schritt 3: Konfigurieren von Voraussetzungen und Erstellen einer Kommunikationscompliancerichtlinie

Um mit einer Richtlinie zur Kommunikationscompliance zu beginnen, müssen IT-Administratoren von Contoso mehrere Voraussetzungen konfigurieren, bevor sie die neue Richtlinie zur Überwachung auf anstößige Sprache einrichten können. Nachdem diese Voraussetzungen erfüllt sind, können die IT-Administratoren und Compliance-Spezialisten von Contoso die neue Richtlinie konfigurieren, und die Compliance-Spezialisten können mit der Untersuchung und Behebung aller generierten Warnungen beginnen.

### <a name="enabling-auditing-in-microsoft-365"></a>Aktivieren der Überwachung in Microsoft 365

Für die Kommunikationscompliance sind Überwachungsprotokolle erforderlich, um Warnungen anzuzeigen und die von den Prüfern ergriffenen Abhilfemaßnahmen zu verfolgen. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten im Zusammenhang mit einer definierten Organisationsrichtlinie oder immer dann, wenn es eine Änderung einer Richtlinie zur Kommunikationscompliance gibt.

Die IT-Administratoren von Contoso überprüfen und vervollständigen die [Schritt-für-Schritt-Anweisungen](turn-audit-log-search-on-or-off.md) zum Aktivieren der Überwachung. Daraufhin teilt ihnen eine Meldung mit, dass das Überwachungsprotokoll vorbereitet wird und sie in ein paar Stunden nach Abschluss der Vorbereitung eine Suche durchführen können. Die IT-Administratoren von Contoso müssen diese Aktion nur einmal ausführen.

### <a name="configuring-yammer-tenant-for-native-mode"></a>Konfigurieren Yammer Mandanten für den nativen Modus

Kommunikationscompliance erfordert, dass sich der Yammer Mandant für eine Organisation im nativen Modus befindet, um in privaten Nachrichten und öffentlichen Community-Unterhaltungen auf anstößige Sprache zu überwachen.

It-Administratoren von Contoso stellen sicher, dass sie die Informationen in der [Übersicht über Yammer nativen Modus in Microsoft 365 Artikel](/yammer/configure-your-yammer-network/overview-native-mode) überprüfen und die Schritte zum Ausführen des Migrationstool im Artikel "Konfigurieren Ihres Yammer Netzwerks für den [nativen Modus für Microsoft 365"](/yammer/configure-your-yammer-network/native-mode) ausführen.

### <a name="setting-up-a-group-for-in-scope-users"></a>Einrichten einer Gruppe für Benutzer im Bereich

Compliance-Spezialisten von Contoso möchten alle Benutzer zur Kommunikationsrichtlinie hinzufügen, die auf anstößige Sprache überwacht wird. Sie könnten sich entscheiden, jedes Benutzerkonto separat zur Richtlinie hinzuzufügen, aber sie haben beschlossen, dass es viel einfacher ist und zeitsparend ist, eine Verteilergruppe **"Alle Benutzer"** für die Benutzer für diese Richtlinie zu verwenden.

Sie müssen eine neue Gruppe erstellen, um alle Contoso-Benutzer einzuschließen, damit sie die folgenden Schritte ausführen:

1. Die IT-Administratoren von Contoso melden sich beim **Microsoft 365 Admin Center** [an ( https://admin.microsoft.com)](https://admin.microsoft.com) und navigieren zu **Microsoft 365 Admin Center**  >    >  **Gruppengruppen.**
2. Sie wählen **eine Gruppe hinzufügen** aus, und schließen den Assistenten ab, um eine neue Microsoft 365 *Gruppe* oder *Verteilergruppe* zu erstellen.

    ![Gruppen](../media/communication-compliance-case-all-employees.png)

3. Nachdem die neue Gruppe erstellt wurde, müssen alle Contoso-Benutzer zu der neuen Gruppe hinzugefügt werden. Sie öffnen das **Exchange Admin Center** [( https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) und navigieren zu Exchange Admin **Center-Empfängergruppen.**  >    >   The Contoso IT administrators select the Membership area and the new *All Employees* group they created and select the **Edit** control to add all Contoso users to the new group in the wizard.

    ![Exchange Admin-Center](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>Erstellung der Richtlinie zur Überwachung auf anstößige Sprache

Wenn alle Voraussetzungen erfüllt sind, sind die IT-Administratoren und die Compliance-Spezialisten von Contoso bereit, die Richtlinien für die Kommunikationscompliance zur Überwachung auf anstößige Sprache zu konfigurieren. Mit der neuen Richtlinienvorlage für anstößige Sprache ist die Konfiguration dieser Richtlinie einfach und schnell.

1. Die IT-Administratoren und Compliance-Spezialisten von Contoso melden sich beim **Microsoft 365 Compliance Center** an und wählen im linken Navigationsbereich die Option **Kommunikationscompliance** aus. Mit dieser Aktion wird das Dashboard **Übersicht** geöffnet, das Schnellverknüpfungen für Richtlinienvorlagen zur Kommunikationscompliance enthält. Sie wählen die Vorlage **Überwachung auf anstößige Sprache**, indem sie für die Vorlage **Erste Schritte** wählen.

    ![Vorlage für kommunikationscompliance anstößige Sprache](../media/communication-compliance-case-template.png)

2. Im Assistenten für Richtlinienvorlagen arbeiten die IT-Administratoren und Compliance-Spezialisten von Contoso zusammen, um die drei erforderlichen Felder auszufüllen: **Richtliniennamen**, **Zu beaufsichtigende Benutzer oder Gruppen** und **Prüfer**.
3. Da der Assistent für Richtlinien bereits einen Namen für die Richtlinie vorgeschlagen hat, beschließen die IT-Administratoren und Compliance-Spezialisten, den vorgeschlagenen Namen beizubehalten und sich auf die übrigen Bereiche zu konzentrieren. Sie wählen die Gruppe *"Alle Benutzer"* für die **Benutzer oder Gruppen aus, um** das Feld zu überwachen, und wählen die Compliance-Spezialisten aus, die Richtlinienwarnungen für das Feld **"Prüfer"** untersuchen und beheben sollten. The last step to configure the policy and start gathering alert information is to select **Create policy**.

    ![Assistent für kommunikationscompliance anstößige Sprache](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>Schritt 4: Untersuchen und Beheben von Warnungen

Nun, da die Richtlinie zur Überwachung der Kommunikationscompliance auf anstößige Sprache konfiguriert ist, besteht der nächste Schritt für die Compliance-Spezialisten von Contoso darin, alle durch die Richtlinie erzeugten Warnungen zu untersuchen und zu beheben. Es wird bis zu 24 Stunden dauern, bis die Richtlinie die Kommunikationen in allen Kommunikationskanälen vollständig verarbeitet hat und die Warnungen im **Dashboard „Warnung“** angezeigt werden.

Nachdem Warnungen generiert wurden, folgen die Compliance-Spezialisten von Contoso den [Workflowanweisungen,](communication-compliance-investigate-remediate.md) um Probleme mit anstößigen Sprachen zu untersuchen und zu beheben.