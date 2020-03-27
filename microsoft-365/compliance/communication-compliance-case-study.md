---
title: 'Fallstudie: contoso konfiguriert eine Offensive Sprachrichtlinie schnell'
description: Eine Fallstudie für Contoso und ihre schnelle Konfiguration einer Kommunikations Konformitätsrichtlinie zur Überwachung der anstößigen Sprache in Microsoft Teams und Exchange Online Kommunikation
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
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 6b5ce3b9ca738ddf94edbb035daeb730f5e3f96a
ms.sourcegitcommit: 242f051c4cf3683f8c1a5da20ceca81bde212cfc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "42982353"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy"></a>Fallstudie: contoso konfiguriert eine Offensive Sprachrichtlinie schnell

Die Kommunikations Kompatibilität in Microsoft 365 hilft, Kommunikationsrisiken zu minimieren, indem Sie Sie bei der Erkennung, Erfassung und Durchführung von Korrekturaktionen für ungeeignete Nachrichten in Ihrer Organisation unterstützen. Mit vordefinierten und benutzerdefinierten Richtlinien können Sie interne und externe Kommunikationen nach Richtlinien Übereinstimmungen durchsuchen, damit Sie von bestimmten Prüfern geprüft werden können. Überprüfer können gescannte e-Mails, Microsoft Teams oder Drittanbieter Kommunikationen in Ihrer Organisation untersuchen und geeignete Korrekturaktionen durchführen, um sicherzustellen, dass diese mit den Nachrichtenstandards Ihrer Organisation konform sind.

Die Contoso Corporation ist eine fiktive Organisation, die eine Richtlinie zum Überwachen von anstößigen Sprachen schnell konfigurieren muss. Sie verwenden Microsoft 365 in erster Linie für e-Mail-und Microsoft Teams-Unterstützung für Ihre Mitarbeiter, haben aber neue Anforderungen für die Durchsetzung von Unternehmensrichtlinien im Hinblick auf Mobbing am Arbeitsplatz. IT-Administratoren und Compliance-Experten von Contoso verfügen über grundlegende Kenntnisse der Grundlagen der Zusammenarbeit mit Microsoft 365 und suchen nach einer End-to-End-Anleitung, wie Sie schnell mit der Kommunikation beginnen können.

In dieser Fallstudie werden die Grundlagen für die schnelle Konfiguration einer Kommunikations Konformitätsrichtlinie für die Überwachung der Kommunikation für anstößige Sprachen behandelt. Dieser Leitfaden umfasst Folgendes:

- Schritt 1: Planen der Kommunikation Compliance
- Schritt 2-Zugriff auf die Kommunikations Kompatibilität in Microsoft 365
- Schritt 3: Konfigurieren von Voraussetzungen und Erstellen einer Konformitätsrichtlinie für die Kommunikation
- Schritt 4 – untersuchen und Behebung von Warnungen

## <a name="step-1---planning-for-communication-compliance"></a>Schritt 1: Planen der Kommunikation Compliance

IT-Administratoren und Compliance-Experten von Contoso haben an Online-Webinaren zu Compliance-Lösungen in Microsoft 365 teilgenommen und entschieden, dass Compliance-Richtlinien für die Kommunikation Ihnen helfen, die aktualisierten Unternehmensrichtlinien Anforderungen für die Arbeitsplatz Reduzierung zu erfüllen Belästigung. Gemeinsam haben Sie einen Plan zum Erstellen und Aktivieren einer Kommunikations Konformitätsrichtlinie entwickelt, die die beleidigende Sprache für Chats überwacht, die in Microsoft Teams in e-Mail-Nachrichten gesendet werden, die in Exchange Online gesendet werden. Ihr Plan umfasst die Ermittlung:

- Die IT-Administratoren, die Zugriff auf die Kommunikationsrichtlinien Features benötigen.
- Die Compliance-Experten, die Kommunikationsrichtlinien erstellen und verwalten müssen.
- Die Compliance-Experten und andere Kollegen in anderen Abteilungen (Personal, Legal, etc.), die Benachrichtigungen zur Kommunikations Konformität untersuchen und beheben müssen.
- Die Benutzer, die für die Kommunikationsrichtlinien Compliance-Offensive-Sprachrichtlinie in der Reichweite sind.

### <a name="licensing"></a>Lizenzierung

Der erste Schritt besteht darin zu bestätigen, dass die Microsoft 365-Lizenzierung von Contoso Unterstützung für die Kommunikations kompatibilitätslösung enthält. Für den Zugriff auf und die Verwendung der Kommunikations Konformität müssen die IT-Administratoren von Contoso überprüfen, ob contoso über eine der folgenden Optionen verfügt:

- Microsoft 365 E5-Abonnement (kostenpflichtige oder Testversion)
- Office 365 Enterprise E3-Lizenz mit dem Advanced Compliance-Add-on
- Office 365 Enterprise E5-Abonnement (kostenpflichtige oder Testversion)

Sie müssen außerdem sicherstellen, dass Benutzer, die in Kommunikations Konformitätsrichtlinien enthalten sind, einer der oben aufgeführten Lizenzen zugewiesen werden müssen.

IT-Administratoren von Contoso führen Sie die folgenden Schritte aus, um die Lizenzierungsunterstützung für contoso zu überprüfen:

1. IT-Administratoren melden sich beim **Microsoft 365 Admin Center** [anhttps://admin.microsoft.com) (](https://admin.microsoft.com) und wechseln zu **Microsoft 365 Admin Center** > -**Abrechnungs** > **Lizenzen**.

2. Hier bestätigen Sie, dass Sie über eine der [Lizenzoptionen](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin) verfügen, die Unterstützung für die Kommunikations Kompatibilität beinhalten.

![Kommunikation Compliance-Lizenzierung](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Berechtigungen für die Kommunikations Konformität

Standardmäßig haben globale Administratoren keinen Zugriff auf Features für die Kommunikations Kompatibilität. [Berechtigungen müssen so konfiguriert werden](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#step-1-required-enable-permissions-for-communication-compliance) , dass Administratoren von Contoso und Compliance-Experten Zugriff auf die Kommunikations Konformität haben.

1. Contoso-IT-Administratoren melden sich auf der Seite Berechtigungen für das **Office 365 Security and Compliance Center** an [(https://protection.office.com/permissions) ](https://protection.office.com/permissions) Verwenden von Anmeldeinformationen für ein globales Administratorkonto und auswählen des Links zum Anzeigen und Verwalten von Rollen in Office 365.
2. Nachdem Sie **Create**ausgewählt haben, weisen Sie der neuen Rollengruppe den Anzeigenamen "*Communication Compliance*" zu und wählen **dann weiter**aus.
3. Wählen Sie **Rollen auswählen** aus, und wählen Sie dann **Hinzufügen**aus. Sie fügen die erforderlichen Rollen hinzu, indem Sie das Kontrollkästchen für *Aufsichts Überprüfungs Administrator*, *Fallverwaltung*, *Kompatibilitäts Administrator*und *Überprüfung*aktivieren und dann **Hinzufügen**, **Fertig** und **weiter**auswählen.

![Kommunikation Compliance Roles](../media/communication-compliance-case-roles.png)

4. Als nächstes wählen die IT-Administratoren **"Mitglieder** auswählen" und dann " **Hinzufügen**" aus. Das Kontrollkästchen für alle Benutzer und Gruppen aktivieren, für die Sie Richtlinien erstellen und Nachrichten mit Richtlinien Übereinstimmungen verwalten möchten. Sie fügen die IT-Administratoren, Compliance-Experten und andere Kollegen in der Personalabteilung und den Rechtsabteilungen hinzu, die Sie in der anfänglichen Planung identifiziert haben, und wählen dann **Hinzufügen**, **Fertig**und **weiter**aus.
5. Um die Berechtigungen abzuschließen, wählen die IT-Administratoren die Option **Create Role Group** to Finish aus. Es dauert etwa 30 Minuten, bis die Rollen im Microsoft 365-Dienst von Contoso wirksam werden.

![Überprüfung der Kommunikations Konformität](../media/communication-compliance-case-review.png)

## <a name="step-2---accessing-communication-compliance-in-microsoft-365"></a>Schritt 2-Zugriff auf die Kommunikations Kompatibilität in Microsoft 365

Nach dem Konfigurieren der Berechtigungen für die Kommunikations Konformität können die in der neuen Rollengruppe definierten IT-Administratoren und Compliance-Experten von Contoso auf die Lösung für die Kommunikations Kompatibilität in Microsoft 365 zugreifen. IT-Administratoren und Compliance-Experten von Contoso haben verschiedene Möglichkeiten für den Zugriff auf die Kommunikations Konformität und erste Schritte beim Erstellen einer neuen Richtlinie:

- Direktes Starten von der Kommunikations kompatibilitätslösung
- Ausgehend vom Microsoft 365 Compliance Center
- Ausgehend vom Microsoft 365-Lösungskatalog
- Ausgehend vom Microsoft 365 Admin Center

### <a name="starting-directly-from-the-communication-compliance-solution"></a>Direktes Starten von der Kommunikations kompatibilitätslösung

Die schnellste Möglichkeit für den Zugriff auf die Lösung ist die direkte Anmeldung bei der **Communication Compliance** (<https://compliance.microsoft.com/supervisoryreview>)-Lösung. Mithilfe dieses Links werden die Experten von Contoso IT-Administratoren und Compliance-Spezialisten an das Dashboard zur Kommunikation-Compliance-Übersicht weitergeleitet, in dem Sie schnell den Status von Warnungen überprüfen und neue Richtlinien aus den vordefinierten Vorlagen erstellen können.

![Übersicht über die Kommunikations Kompatibilität](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>Ausgehend vom Microsoft 365 Compliance Center

Eine weitere einfache Möglichkeit für IT-Administratoren und Compliance-Experten von Contoso, auf die Lösung für die Kommunikations Konformität zuzugreifen, ist die direkte Anmeldung beim **Microsoft 365 Compliance Center** [(https://compliance.microsoft.com)](https://compliance.microsoft.com). Nachdem Sie sich angemeldet haben, müssen Benutzer einfach das Steuerelement **Alle anzeigen** auswählen, um alle Kompatibilitätslösungen anzuzeigen, und dann die Lösung für die **Kommunikations Kompatibilität** für die ersten Schritte auswählen.

![Compliance Center](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>Ausgehend vom Microsoft 365-Lösungskatalog

Contoso-IT-Administratoren und Compliance-Experten können sich auch für den Zugriff auf die Kommunikations kompatibilitätslösung entscheiden, indem Sie den Microsoft 365-Lösungskatalog auswählen. Wenn Sie im Abschnitt " **catalog** in **Solutions** " im linken Navigationsbereich im **Microsoft 365 Compliance Center**auswählen, können Sie den Lösungskatalog öffnen, in dem alle Microsoft 365-Kompatibilitätslösungen aufgelistet sind. Wenn Sie einen Bildlauf nach unten zum Abschnitt **Insider Risk Management** durchführen, können Contoso-IT-Administratoren die Kommunikations Kompatibilität für erste Schritte auswählen. Contoso-IT-Administratoren entscheiden sich außerdem für die Verwendung der Anzeige im Navigationssteuerelement, um die Lösung für die Kommunikations Konformität im linken Navigationsbereich für einen schnelleren Zugriff zu fixieren, wenn Sie sich in Zukunft anmelden.

![Lösungskatalog](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>Ausgehend vom Microsoft 365 Admin Center

Für den Zugriff auf die Kommunikations Kompatibilität beim Start vom Microsoft 365 Admin Center melden sich Contoso IT-Administratoren und Compliance-Experten beim Microsoft 365 Admin Center an [(https://admin.microsoft.com) ](https://admin.microsoft.com) und navigieren Sie zu **Microsoft 365 Admin Center** > **Compliance**.

![Kommunikations Kompatibilitätslink](../media/communication-compliance-case-compliance-link.png)

Dadurch wird das **Office 365 Security and Compliance Center**geöffnet, und Sie müssen den Link zum **Microsoft 365 Compliance Center** auswählen, der im Banner oben auf der Seite bereitgestellt wird.

![Office 365 Security and Compliance Center](../media/communication-compliance-case-scc.png)

Sobald Sie sich im **Microsoft 365 Compliance Center**befinden, wählen Sie " **Alle anzeigen** " aus, um die vollständige Liste der Kompatibilitätslösungen anzuzeigen.

![Menü "Kommunikations Kompatibilität"](../media/communication-compliance-case-show-all.png)

Nachdem Sie **Alle anzeigen**ausgewählt haben, können die IT-Administratoren von Contoso auf die Lösung für die Kommunikations Konformität zugreifen.

![Übersicht über die Kommunikations Kompatibilität](../media/communication-compliance-case-overview.png)

## <a name="step-3---configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Schritt 3: Konfigurieren von Voraussetzungen und Erstellen einer Konformitätsrichtlinie für die Kommunikation

Für den Einstieg in eine Kommunikations Konformitätsrichtlinie gibt es mehrere Voraussetzungen, die von Contoso-IT-Administratoren konfiguriert werden müssen, bevor die neue Richtlinie für die Überwachung auf anstößige Sprache eingerichtet wird. Nachdem diese Voraussetzungen erfüllt sind, können Contoso-IT-Administratoren und Compliance-Experten die neuen Richtlinien und Compliance-Experten konfigurieren, die mit der Untersuchung beginnen und alle generierten Warnungen remediationieren.

### <a name="enabling-auditing-in-office-365"></a>Aktivieren der Überwachung in Office 365

Für die Kommunikations Kompatibilität müssen Überwachungsprotokolle Warnungen anzeigen und von den Prüfern vorgenommene Korrekturaktionen nachverfolgen. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten, die einer definierten Organisationsrichtlinie zugeordnet sind, oder wenn es eine Änderung an einer Kommunikations Konformitätsrichtlinie gibt.

Contoso IT-Administratoren überprüfen und vervollständigen die [schrittweisen Anweisungen](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) zum Aktivieren der Überwachung. Nachdem Sie die Überwachung aktiviert haben, wird eine Meldung angezeigt, die besagt, dass das Überwachungsprotokoll vorbereitet wird und dass Sie eine Suche in einigen Stunden nach Abschluss der Vorbereitung ausführen können. Die IT-Administratoren von Contoso müssen diese Aktion nur einmal durchführen.

### <a name="setting-up-a-group-for-in-scope-users"></a>Einrichten einer Gruppe für Benutzer in einem Bereich

Contoso Compliance Specialists möchten alle Mitarbeiter der Kommunikationsrichtlinie hinzufügen, die die anstößige Sprache überwacht. Sie können beschließen, jedes Employee-Benutzerkonto separat zur Richtlinie hinzuzufügen, aber Sie haben beschlossen, dass es viel einfacher ist, und sparen viel Zeit, um eine **gesamte Mitarbeiter** -Verteilergruppe für die Benutzer dieser Richtlinie zu verwenden.

Sie müssen eine neue Gruppe erstellen, um alle Contoso-Mitarbeiter einzuschließen, sodass Sie die folgenden Schritte ausführen:

1. Contoso IT-Administratoren melden Sie sich beim **Microsoft 365 Admin Center** [anhttps://admin.microsoft.com) (](https://admin.microsoft.com) und navigieren Sie zu **Microsoft 365 Admin Center** > **Groups** > **Groups**.
2. Sie wählen **Hinzufügen einer Gruppe** und schließen den Assistenten aus, um eine neue *Office 365 Gruppe* oder *Verteilergruppe*zu erstellen.

![Gruppen](../media/communication-compliance-case-all-employees.png)

3. Nachdem die neue Gruppe erstellt wurde, müssen Sie alle Contoso-Benutzer zur neuen Gruppe hinzufügen. Sie öffnen das **Exchange Admin Center** [(https://outlook.office365.com/ecp) ](https://outlook.office365.com/ecp) und wechseln zu **Exchange Admin Center** > **Recipients** > **Groups**. Die IT-Administratoren von Contoso wählen den Mitgliedschaftsbereich und die neue Gruppe *alle Mitarbeiter* aus, die Sie erstellt haben, und wählen das **Bearbeitungs** Steuerelement aus, um alle Contoso-Mitarbeiter der neuen Gruppe im Assistenten hinzuzufügen.

![Exchange Admin Center](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>Erstellen der zu überwachenden Richtlinie für anstößige Sprachen

Nachdem alle erforderlichen Voraussetzungen erfüllt sind, sind die IT-Administratoren und die Compliance-Spezialisten für Contoso für die Konfiguration der Kommunikations Konformitätsrichtlinie zur Überwachung der anstößigen Sprache gerüstet. Bei Verwendung der neuen Richtlinienvorlage für anstößige Sprachen ist das Konfigurieren dieser Richtlinie einfach und schnell.

1. Die Spezialisten von Contoso für IT-Administratoren und Compliance-Experten melden sich beim **Microsoft 365 Compliance Center** an und wählen im linken Navigationsbereich die Option " **Kommunikations Kompatibilität** " aus. Mit dieser Aktion wird das Übersichts **Dashboard geöffnet, das über Quick** Links für Kommunikationsrichtlinien Vorlagen für Konformitätsrichtlinien verfügt. Sie wählen die Vorlage **Monitor für anstößige Sprachen** aus, indem Sie **Erste Schritte** für die Vorlage auswählen.

![Communication Compliance anstößige Sprachvorlage](../media/communication-compliance-case-template.png)

2. Im Assistenten für Richtlinienvorlagen arbeiten die Spezialisten von Contoso für IT-Administratoren und Compliance-Experten zusammen, um die drei erforderlichen Felder abzuschließen: **Richtlinienname**, **Benutzer oder zu überwachende Gruppen**und **Prüfer**.
3. Da der Richtlinien-Assistent bereits einen Namen für die Richtlinie vorgeschlagen hat, beschließen die IT-Administratoren und Compliance-Experten, den vorgeschlagenen Namen beizubehalten und sich auf die verbleibenden Felder zu konzentrieren. Sie wählen die Gruppe *alle Mitarbeiter* für die **zu überwachenden Benutzer oder Gruppen** aus und wählen die Kompatibilitäts Experten aus, die Richtlinienwarnungen für das Feld **Bearbeiter** untersuchen und korrigieren sollten. Der letzte Schritt zum Konfigurieren der Richtlinie und zum Starten der Erfassung von Warnungsinformationen besteht in der Auswahl von **Create Policy**.

![Assistent für Kommunikationsrichtlinien Treue-anstößige Sprachen](../media/communication-compliance-case-wizard.png)

## <a name="step-4--investigate-and-remediate-alerts"></a>Schritt 4 – untersuchen und Beheben von Warnungen

Nachdem die Kommunikations Konformitätsrichtlinie für die Überwachung anstößiger Sprachen konfiguriert wurde, besteht der nächste Schritt für die Contoso-Compliance-Experten darin, alle Warnungen zu untersuchen und zu korrigieren, die von der Richtlinie generiert werden. Es dauert bis zu 24 Stunden, bis die Richtlinie die Kommunikationen in allen Kommunikations Quellkanälen vollständig verarbeitet und Warnungen im **Benachrichtigungs Dashboard**angezeigt wird.

Nachdem Warnungen generiert wurden, befolgen die Contoso-Compliance-Experten die [Workflowanweisungen](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate) , um anstößige Sprachprobleme zu untersuchen und zu beheben.
