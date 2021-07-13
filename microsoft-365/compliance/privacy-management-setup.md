---
title: Erste Schritte mit Microsoft Privacy Management (Vorschau)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie die Datenschutzverwaltung für Ihre Organisation einrichten, Rollen und Berechtigungen festlegen und wichtige Einstellungen konfigurieren.
ms.openlocfilehash: 5199cf96e9ede3287dc9ac33e26388c065189748
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378552"
---
# <a name="get-started-with-privacy-management-preview"></a>Erste Schritte mit der Datenschutzverwaltung (Vorschau)

In diesem Artikel erfahren Sie, wie Sie **den Zugriff auf die Datenschutzverwaltung** für Ihre Organisation einrichten, wie Sie mit der Auswertung Ihrer Daten **beginnen** und wie Wichtige **Einstellungen** behandelt werden.

## <a name="sign-up"></a>Registrieren

Die Datenschutzverwaltung wird im Microsoft 365 Compliance Center verfügbar sein. Die öffentliche Vorschau der Datenschutzverwaltung ist für Organisationen mit E1-, E3- und E5-Office 365 und Microsoft 365 Unternehmenslizenzen verfügbar. Bei der allgemeinen Verfügbarkeit der Datenschutzverwaltung müssen Organisationen eine neue Lizenz erhalten.

Beachten Sie, dass die öffentliche Vorschau der Datenschutzverwaltung für Kunden von US Government Community (GCC) Moderate, GCC High oder Department of Defense (DoD) nicht verfügbar ist.

Um mit der öffentlichen Vorschau zu beginnen, erhalten Sie das Vorschauabonnement im Admin Center. Wenn Sie bei der ersten Auswahl der Datenschutzverwaltung im Compliance Center noch nicht über die Lizenz verfügen, werden Sie zum Admin Center weitergeleitet, um loszulegen. Es wird empfohlen, dass sich der globale Administrator anmeldet und Benutzerberechtigungen wie unten beschrieben beim ersten Besuch der Datenschutzverwaltung festgelegt. Wenn Sie nicht über die erforderliche Rolle verfügen, um das Abonnement zu erhalten oder den Nutzungsbedingungen für die Datenverwaltung zuzustimmen, werden Sie aufgefordert, Sich an Ihren globalen Administrator zu wenden, um Unterstützung zu erhalten.

Die Bestätigung, dass Sie mit der Verwendung des Datenschutzmanagements beginnen möchten, signalisiert, dass Sie den Bedingungen und dem Prozess der Auswertung personenbezogener Daten zustimmen. Sie können die bereitgestellten Links vollständig überprüfen, bevor Sie fortfahren.

## <a name="set-user-permissions-and-assign-roles"></a>Festlegen von Benutzerberechtigungen und Zuweisen von Rollen

Die Datenschutzverwaltung verwendet ein rollenbasiertes Zugriffssteuerungsmodell (RBAC). Nur Benutzer, denen eine Rolle zugewiesen ist, können auf die Datenschutzverwaltung zugreifen, und die von jedem Benutzer zulässigen Aktionen sind je nach Rollentyp eingeschränkt.

Berechtigungen und Rollenzuweisungen für die Datenschutzverwaltung können innerhalb der Microsoft 365 Compliance Center wie folgt behandelt werden. Beachten Sie, dass Rollen, die für die Datenschutzverwaltung spezifisch sind, nicht in Azure Active Directory angezeigt werden.

### <a name="in-the-microsoft-365-compliance-center"></a>In der Microsoft 365 Compliance Center

- Wählen Sie im linken Navigationsbereich Berechtigungen aus.
- Erweitern Sie das Compliance Center, und wählen Sie "Rollen" aus. Die vollständige Liste der Rollengruppen wird angezeigt. 
- Scrollen Sie, um die Datenschutzverwaltungsgruppen zu finden, oder suchen Sie nach Schlüsselwörtern, z. B. "Datenschutz".
- Wählen Sie die relevante Rollengruppe aus, um eine Beschreibung, die zugewiesenen Rollen und eine Liste der Mitglieder anzuzeigen.
- Verwenden Sie den Link "Bearbeiten" neben diesen Abschnitten, um Benutzer hinzuzufügen oder zu ändern oder die Einstellungen zu bearbeiten.

### <a name="learn-about-role-groups-and-roles"></a>Informationen zu Rollengruppen und Rollen

In diesem Abschnitt werden die Rollengruppen und Rollen beschrieben, die für die Datenschutzverwaltung relevant sind. Mitglieder sollten Rollengruppen vom Administrator auf oberster Ebene zugewiesen werden, je nachdem, welche Aufgaben sie ausführen müssen und welche Ebene des Dateizugriffs geeignet ist. Jede Rollengruppe enthält eine oder mehrere Rollen. Diese Rollen können bestimmte Datenschutzverwaltungsaufgaben betreffen oder wichtigen Funktionen entsprechen, die für die Mitglieder dieser Gruppe aktiviert oder eingeschränkt sind.

Rollengruppen können bei Bedarf angepasst werden. Um versehentlichen Verlust des Zugriffs zu vermeiden, empfehlen wir, eine Kopie der vorhandenen Rollengruppe zu erstellen, die Sie anpassen möchten, der Kopie einen identifizierbaren Namen zu geben, Ihre Änderungen an der neuen Gruppe vorzunehmen und zu überprüfen und ihr Personen je nach Bedarf zuzuweisen.

**Datenschutzverwaltung:** Diese Gruppe enthält alle Berechtigungsrollen für die Datenschutzverwaltung in einer einzigen Gruppe. Dies ist die einfachste Möglichkeit, schnell mit der Datenschutzverwaltung zu beginnen und die Zugriffssteuerung für andere Gruppen zu verwalten, die die Datenschutzverwaltung verwenden. Es eignet sich auch gut für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind.

**Datenschutzverwaltungsadministratoren:** Mitglieder dieser Rollengruppe konzentrieren sich auf Konfigurations- und Verwaltungsaufgaben und haben breiten Zugriff auf Datenschutzverwaltungsfunktionen, einschließlich erstellung, Lesen, Aktualisieren und Löschen von Datenschutzverwaltungsrichtlinien, Anträgen auf Rechte betroffener Personen, Datenschutzverwaltungsberechtigungen und Datenschutzverwaltungseinstellungen.

**Datenverwaltungsanalysten:** Mitglieder dieser Rollengruppe fungieren als Fallanalysten für das Datenschutzmanagement. Sie können Richtlinienüberstimmungen untersuchen, Dateimetadaten anzeigen und Korrekturmaßnahmen ergreifen. Diese Gruppe kann nicht über den Inhalts-Explorer auf vollständige Dateien zugreifen.

**Datenschutzverwaltungsermittler:** Mitglieder dieser Gruppe fungieren als Datenermittler für die Datenverwaltung. Sie können Richtlinienüberstimmungen untersuchen, den zugehörigen Dateiinhalt anzeigen und Korrekturmaßnahmen ergreifen. Diese Gruppe kann über den Inhalts-Explorer auf Dateien zugreifen.

**Datenschutzverwaltungs-Viewer:** Mitglieder dieser Gruppe können analysebasierte Informationen in der Datenschutzverwaltung anzeigen, z. B. die Übersicht, das Datenprofil und die Berichte zu Antragstelleranfragen.

**Antragstellerrechte-Anforderungsadministratoren:** Mitglieder dieser Gruppe haben vollzugriff auf die Verwaltung und Erstellung von Anträgen auf Antragstellerrechte.

**Mitwirkende im Datenschutzmanagement:** Mitglieder dieser Gruppe haben Zugriff auf Anträge von Antragstellerrechten.

Die spezifischen Rollen, die in den einzelnen Rollengruppen enthalten sind, finden Sie in der folgenden Tabelle.

| **Rollengruppe**      | **Enthaltene Rollen**                        |
|:-- |:--|
| Datenschutzverwaltung  | Fallverwaltung                           |
|                     | Inhaltsanzeige für Datenklassifizierung        |
|                     | Datenklassifizierungslistenanzeige           |
|                     | Datenschutzverwaltungsadministrator                  |
|                     | Analyse des Datenschutzmanagements               |
|                     | Untersuchung des Datenschutzmanagements          |
|                     | Permanenter Beitrag zum Datenschutzmanagement |
|                     | Temporärer Beitrag zur Datenschutzverwaltung |
|                     | Privacy Management Viewer                 |
|                     | Administrator für Antragstellerrechteanforderung              |
|                     | View-Only Fall                            |
| Datenschutzverwaltungsadministrator | Fallverwaltung                      |
|                          | Datenschutzverwaltungsadministrator             |
|                          | View-Only Fall                       |
| Datenverwaltungsanalysten | Fallverwaltung                   |
|                             | Datenklassifizierungslistenanzeige   |
|                             | Analyse des Datenschutzmanagements       |
|                             | View-Only Fall                    |
| Ermittler des Datenschutzmanagements | Fallverwaltung              |
|                                  | Inhaltsanzeige für Datenklassifizierung |
|                                  | Datenklassifizierungslistenanzeige    |
|                                  | Untersuchung des Datenschutzmanagements   |
|                                  | View-Only Fall                     |
| Privacy Management Viewer        | Privacy Management Viewer          |
| Administrator für Antragstellerrechteanforderung | Administrator für Antragstellerrechteanforderung   |
|Mitwirkende im Datenschutzmanagement       | Temporärer Beitrag zur Datenschutzverwaltung |
|                                      | Permanenter Beitrag zum Datenschutzmanagement |

## <a name="configure-settings"></a>Konfigurieren von Einstellungen

Auf die Einstellungen Seite kann über das Zahnrad in der oberen rechten Ecke der Hauptseiten der Datenschutzverwaltung zugegriffen werden. Sie ermöglicht Es Datenschutzverwaltungsadministratoren, wichtige Eigenschaften für die Datenschutzverwaltung zu konfigurieren. Folgende Optionen sind verfügbar.

### <a name="anonymization"></a>Anonymisierung

Mit diesem Feature können Sie anonymisierte Versionen von Benutzernamen innerhalb von Datenschutzverwaltungsfeatures für Benutzer in bestimmten Rollen anzeigen. Dadurch werden identifizierbare Anzeigenamen wie "Grace Grace" durch eine generische Bezeichnung wie "AnonyIS8-988" ersetzt, um die Identitäten Ihrer Benutzer beim Überprüfen vertraulicher Daten zu maskieren. Diese Option gilt nicht für das Anforderungsmodul für Betreffrechte.

### <a name="user-notification-emails"></a>Benutzerbenachrichtigungs-E-Mails

Wenn wir eine Übereinstimmung mit Ihren Datenverarbeitungsrichtlinien erkennen, kann die Datenschutzverwaltung eine E-Mail an die betroffenen Benutzer mit Korrekturmaßnahmen und einem Link zu Datenschutzschulungen senden. In Einstellungen können Sie die E-Mail-Benachrichtigungsfunktion der Datenschutzverwaltung als Ganzes aktivieren oder deaktivieren. Sie können einzelne Benachrichtigungen aktivieren, die E-Mail-Häufigkeit festlegen und beim Erstellen oder Bearbeiten einer Richtlinie eine Schulungs-URL angeben. Wenn die Benachrichtigungsfunktion in Einstellungen deaktiviert ist, wird jede Konfiguration auf Richtlinienebene für bestimmte Benachrichtigungs-E-Mails deaktiviert. Weitere Informationen zu Richtlinien finden Sie unter [Erstellen und Verwalten von Richtlinien.](privacy-management-policies.md)

### <a name="teams-collaboration"></a>Zusammenarbeit in Teams

Integrieren Sie Microsoft Teams Funktionen in das Datenschutzmanagement, um die Zusammenarbeit mit den Beteiligten zu verbessern. Jedes Mal, wenn eine Antragstellerberechtigungsanforderung erstellt wird, wird ein zugeordnetes Team erstellt. Benutzer können einem Team über die Registerkarte "Mitarbeiter" der Anforderung hinzugefügt werden. Weitere Informationen zu Anträgen auf Rechte von Antragstellern finden Sie unter [Verwalten von Anträgen auf Rechte betroffener Personen.](privacy-management-subject-rights-requests.md)

### <a name="power-automate-flows"></a>Power Automate Flüsse

Verwenden Sie Power Automate Flüsse, um datenschutzbezogene Prozesse und Aufgaben automatisch zu verwalten. Sie können Flüsse im Einstellungen Abschnitt mithilfe integrierter Vorlagen für die Datenschutzverwaltung erstellen oder die Power Automate-Konsole verwenden, um benutzerdefinierte Flüsse zu erstellen. Weitere Informationen zu Power Automate finden Sie in der [Power Automate](/power-automate/) Dokumentation.

### <a name="data-matching"></a>Datenabgleich

Verwenden Sie diesen Abschnitt, um Datenschemas hochzuladen, die Attribute Ihrer betroffenen Personen beschreiben, wodurch die richtige betroffene Person bei der Suche nach personenbezogenen Daten in Ihrer Microsoft 365 Umgebung identifiziert wird. Schemas und Regelpakete werden im XML-Format erstellt und hochgeladen. Unter "Hochladen personenbezogener Daten" können Sie auch personenbezogene Daten übermitteln, die einem bereitgestellten Schema entsprechen. Sie können Eine eigene Datei erstellen und hochladen oder persönliche Daten aus Azure hochladen. Weitere Informationen zu Anträgen auf Rechte von Antragstellern finden Sie unter [Verwalten von Anträgen auf Rechte betroffener Personen.](privacy-management-subject-rights-requests.md)

### <a name="data-retention-periods"></a>Datenaufbewahrungszeiträume

Wählen Sie für Anträge auf Betreffrechte aus, wie lange Sie die endgültigen Daten aufbewahren möchten, die nach dem Schließen einer Anforderung gesammelt und gemeldet werden sollen. Sie können zwischen 30 und 90 Tagen auswählen. Weitere Informationen zu Anträgen auf Rechte von Antragstellern finden Sie unter [Verwalten von Anträgen auf Rechte betroffener Personen.](privacy-management-subject-rights-requests.md)

### <a name="data-review-tags"></a>Tags für die Datenüberprüfung

Verwalten Sie die Tags, die Sie verwenden, um Dateien zu markieren, die in einer Anforderung für Betreffrechte abgerufen wurden. In diesem Abschnitt können Sie die Namen und Beschreibungen für benutzerdefinierte Tags bearbeiten. Sie können auch Tagbeschreibungen für die integrierten Tags bearbeiten, die vom System bereitgestellt werden. Namen für Systemtags können nicht geändert werden. Weitere Informationen zu Anträgen auf Rechte von Antragstellern finden Sie unter [Verwalten von Anträgen auf Rechte betroffener Personen.](privacy-management-subject-rights-requests.md)

## <a name="get-initial-data-insights"></a>Abrufen anfänglicher Datenerkenntnisse

Nachdem Sie sich bei der Datenschutzverwaltung angemeldet haben, gelangen Sie zur **Seite "Übersicht".** Diese Seite bietet dynamische Einblicke in die personenbezogenen Daten, die in Ihrer Microsoft 365-Umgebung gespeichert sind, um Ihnen zu helfen, Probleme schnell zu erkennen, Risikoindikatoren zu identifizieren und Maßnahmen zur Behebung von Problemen zu ergreifen. Ihre Übersicht sollte innerhalb der ersten 24 Stunden nach der Registrierung mit ersten Erkenntnissen aufgefüllt werden. Während Sie die Datenschutzverwaltung weiterhin verwenden, wird die Übersichtsseite aktualisiert, um weiterhin aktuelle Informationen bereitzustellen.

Für weitere Einblicke in Ihre Daten im Laufe der Zeit bietet Ihre **Datenprofilseite** mehr Visualisierungen und Analysen und bietet Ihnen eine allgemeine Übersicht über die Daten Ihrer Organisation nach geografischem Standort und nach Microsoft 365 Dienst.

Weitere Informationen zu diesen Seiten finden Sie unter [Suchen und Visualisieren Ihrer Daten.](privacy-management-data-profile.md)
