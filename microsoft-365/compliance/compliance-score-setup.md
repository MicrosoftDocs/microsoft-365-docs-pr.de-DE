---
title: Setup der Microsoft-Kompatibilitätsbewertung (Vorschau)
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: In diesem Artikel erfahren Sie, wie Sie die Microsoft-Kompatibilitätsbewertung einrichten und verwenden, um Risikobewertungen zu vereinfachen und zu automatisieren.
ms.openlocfilehash: f7a501d0ede0d7635e20581774ce51a599dde65b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016190"
---
# <a name="compliance-score-preview-setup"></a>Setup für Kompatibilitätsbewertung (Vorschau)

**In diesem Artikel:** Hier erfahren Sie, wie Sie auf das Kompatibilitäts Ergebnis **zugreifen** , **Rollen und Berechtigungen**festlegen und **Automatische Bewertungen für sichere Gäste**konfigurieren. In diesem Artikel werden auch die wichtigsten Seiten für die Konformitätsbewertung erläutert: **Ihr Dashboard**, die Seite Verbesserungs Aktionen, die Seite Lösungen und die Seite Bewertungen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Der globale Administrator von Microsoft 365 für Ihre Organisation ist wahrscheinlich der erste Benutzer, der auf das Kompatibilitäts Ergebnis zugreift. Wenn Sie das Kompatibilitäts Ergebnis zum ersten Mal besuchen, empfehlen wir die globale Administratoranmeldung, und legen Sie die Benutzerberechtigungen fest, wie unten beschrieben.

## <a name="sign-in"></a>Anmelden

1. Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) , und **melden** Sie sich mit ihrem globalen Microsoft 365-Administratorkonto an.
2. Wählen Sie **Kompatibilitätsbewertung** im linken Navigationsbereich aus. Das [Dashboard für die Konformitätsbewertung sollte dann mit ihrer Bewertung](#understand-the-compliance-score-dashboard)angezeigt werden.

Der direkte Link zum Zugriff auf die Konformitätsbewertung ist [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore) .

## <a name="set-user-permissions-and-assign-roles"></a>Festlegen von Benutzerberechtigungen und Zuweisen von Rollen

Bei der Kompatibilitätsbewertung wird ein RBAC-Berechtigungsmodell (Role-Based Access Control, rollenbasierte Zugriffssteuerung) verwendet. Nur Benutzer, denen eine Rolle zugewiesen ist, können auf die Konformitätsbewertung zugreifen, und die von den einzelnen Benutzern zugelassenen Aktionen sind nach Rollentyp eingeschränkt.

### <a name="where-to-set-permissions"></a>Festlegen von Berechtigungen

Die Person, die die globale Administratorrolle für Ihre Organisation innehat, kann Benutzerberechtigungen in [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) oder im [Compliance-Manager](compliance-manager-overview.md#permissions)festlegen. Sobald die Rollen an beiden Speicherorten festgelegt wurden, können Benutzer auf die Konformitätsbewertung und den Compliance-Manager zugreifen.

### <a name="role-types"></a>Rollentypen

In der folgenden Tabelle wird gezeigt, wie jede [Azure AD Rolle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) vorhandenen Compliance-Manager-Rollen zugeordnet ist und welche Funktionen für welche Rolle zulässig sind. Benutzer benötigen mindestens die Azure AD globale Leserrolle, um auf das Kompatibilitäts Ergebnis zuzugreifen.


| Benutzer kann Folgendes: | Azure AD Rolle | Compliance-Manager-Rolle | 
| :------------- | :-------------: | :------------: |
| **Lesen, aber nicht bearbeiten von Daten**| Azure AD globaler Leser  | Azure AD globaler Leser | 
| **Lesen, aber nicht bearbeiten von Daten**| Benutzer mit Leseberechtigung für Sicherheitsfunktionen | Compliance-Manager-Leser  | 
| **Bearbeiten von Daten**| Compliance-Administrator | Compliance-Manager-Mitwirkender | 
| **Bearbeiten von Testergebnissen**| Compliance-Administrator | Auditor für Compliance-Manager | 
| **Verwalten von Bewertungen und Vorlagen-und Mandantendaten**| Compliance-Administrator<br>Compliancedatenadministrator<br>Sicherheitsadministrator | Compliance-Manager-Administrator | 
| **Zuweisen von Benutzern**| Globaler Administrator | Portal Administrator | 

> [!NOTE]
> Wenn Sie von der Kompatibilitätsbewertung zum Compliance-Manager wechseln, um eine Aufgabe während der öffentlichen Vorschau abzuschließen, öffnet Ihr Browser eine neue Registerkarte, und ein Dialogfeld wird angezeigt. Im oberen Abschnitt mit dem Header "bereits Microsoft Cloud Services-Kunde? Melden Sie sich bei Ihrem Konto an, "wählen Sie **Anmelden** bei Access Compliance Manager aus. Sie müssen Ihre Anmeldeinformationen nicht erneut eingeben.

## <a name="configure-automatic-secure-score-updates"></a>Konfigurieren automatischer Updates für sichere Bewertungen

Standardmäßig haben alle neuen Mandanten die Option Automatische Updates für [sichere Bewertungen](../security/mtp/microsoft-secure-score-new.md) aktiviert. Alle Aktionen, die von Secure Score überwacht werden, aktualisieren den Status für dieselbe Aktion automatisch in der Kompatibilitätsbewertung.

Ihr globaler Administrator kann diese Einstellung verwalten, um automatische Updates für alle Aktionen zu deaktivieren oder Aktualisierungen für Aktionen einzeln festzulegen.

Während der öffentlichen Vorschau müssen Sie zum Microsoft Service Trust Portal (wo sich Compliance Manger befindet) wechseln, um sichere Bewertungs Aktualisierungen zu verwalten.

Führen Sie die folgenden Schritte aus, um automatische Bewertungen für sichere Gäste zu verwalten:

1. Melden Sie sich mit ihrem globalen Administratorkonto beim [Dienst Vertrauensstellungs Portal](https://servicetrust.microsoft.com) an.

2. Wählen Sie in der oberen Menüleiste des Dienst Vertrauensstellungs Portals unter **Weitere**die Option **Administrator** aus, und wählen Sie dann **Einstellungen**aus.

3. Wählen Sie auf der Registerkarte **sichere Punktzahl** die entsprechende Schaltfläche aus, um **für alle Aktionen**aktiviert, **für alle Aktionen**oder **pro Aktion festlegen** zu deaktivieren.

Wenn Sie die Option **pro Aktion festlegen auswählen,** führen Sie die folgenden zusätzlichen Schritte aus, um für einzelne Aktionen sichere Bewertungs Aktualisierungen zu aktivieren:

4. Wählen Sie im oberen Menü den Eintrag **Compliance-Manager** aus (Wählen Sie nicht "Compliance-Manager (klassisch)") aus.

5. Wählen Sie in der oberen rechten Ecke des Bildschirms **Mandantenverwaltung** aus.

6. Suchen Sie im Bereich **Kundenaktionen** die gewünschte Aktion mit einem Auslassungszeichen (**..**.) unter der Spalte **betroffene Aktionen** . Klicken Sie auf die Ellipsen, und wählen Sie **Bearbeiten aus.**

7. Wechseln Sie zur Option **Secure Score Continuous Update** Toggle to **on.**

8. Wählen Sie **Speichern aus.** Secure Score die kontinuierliche Überwachung ist nun für diese Aktion aktiviert.

**Hinweis:** Nur der globale Administrator kann automatische Updates für alle Aktionen aktivieren oder deaktivieren. Der Compliance-Manager-Administrator kann automatische Updates für einzelne Aktionen aktivieren, jedoch nicht für alle Aktionen Global.

#### <a name="learn-more"></a>Weitere Informationen

[Hier finden Sie Informationen zur Verwaltung sicherer Score-Updates](compliance-manager-release-notes.md#secure-score).

## <a name="understand-the-compliance-score-dashboard"></a>Grundlegendes zum Kompatibilitäts Bewertungs Dashboard

Das Compliance Score-Dashboard bietet Ihnen einen Überblick über Ihre aktuelle Compliance-Position.

![Compliance Score-Dashboard](../media/compliance-score-dashboard.png "Konformitäts Bewertungs Dashboard")

### <a name="overall-compliance-score"></a>Gesamtergebnis der Konformität

Ihr Konformitäts Bewertungspunkt wird oben im Vordergrund vorgestellt. Es zeigt einen Prozentsatz auf der Grundlage von Punkten, die für die Durchführung von Verbesserungs Aktionen zur Behandlung wichtiger Datenschutzstandards und-Vorschriften erreichbar sind.

Wenn Sie zum ersten Mal auf die Konformitätsbewertung stoßen, basiert Ihr anfängliches Ergebnis auf der integrierten [Microsoft 365-Datenschutz Basislinie](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)– einer Reihe von Steuerelementen, die allgemeine Branchenvorschriften und-Standards umfassen. Compliance Score scannt Ihre vorhandenen Microsoft 365-Lösungen und gibt Ihnen eine erste Bewertung basierend auf Ihren aktuellen Datenschutz-und Sicherheitseinstellungen. Wenn Sie für Ihre Organisation relevante Bewertungen hinzufügen, wird Ihre Punktzahl für Sie aussagekräftiger.

#### <a name="learn-more"></a>Weitere Informationen
Grund [Legendes zur Berechnung der Konformitätsbewertung](compliance-score-methodology.md)

### <a name="key-improvement-actions"></a>Wichtige Verbesserungs Aktionen

In diesem Abschnitt werden die wichtigsten Verbesserungs Aktionen aufgelistet, die Sie im Moment durchführen können, um den größten positiven Einfluss auf Ihre gesamte Konformitätsbewertung zu nehmen.

### <a name="solutions-that-affect-your-score"></a>Lösungen, die Ihre Punktzahl beeinflussen

In diesem Abschnitt werden Lösungen mit Aktionen gezeigt, die die beste Möglichkeit haben, Ihre Punktzahl positiv zu beeinflussen, sowie die Anzahl der ausstehenden Verbesserungs Aktionen in jeder Lösung.

### <a name="compliance-score-breakdown"></a>Aufschlüsselung der Konformitätsbewertung

In diesem Abschnitt erhalten Sie zwei verschiedene Möglichkeiten, um eine detailliertere Darstellung ihrer Ergebnisse zu erzielen:

- **Kategorien**: zeigt den Prozentsatz der Gesamtpunktzahl in Datenschutzkategorien an, beispielsweise "Informationen schützen" oder "Geräte verwalten".
- **Assessments**: zeigt den Prozentsatz Ihrer Fortschritte bei der Verwaltung von Bewertungen für bestimmte Compliance-und Datenschutzstandards, Verordnungen oder Gesetze wie dsgvo oder NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtern der Dashboardansicht

Sie können die Dashboardansicht filtern, um nur die Elemente anzuzeigen, die sich auf bestimmte Vorschriften und Standards, Lösungen, Aktionstypen, Bewertungsgruppen oder Datenschutzkategorien beziehen. Durch das Filtern der Ansicht auf diese Weise wird auch die Bewertung in Ihrem Dashboard gefiltert, und es wird angezeigt, wie viele Punkte Sie je nach den Filterkriterien aus insgesamt möglichen Punkten erzielt haben.

So wenden Sie Filter an:

1. Wählen Sie in der oberen rechten Ecke des Dashboards den **Filter** aus.
2. Wählen Sie Ihre Filterkriterien im Flyout- **Filter** Bereich aus, und wählen Sie dann **Apply**aus.

Nachdem Sie einen Filter angewendet haben, wird das Ergebnis in Echtzeit angepasst. Der Prozentsatz der Konformitätsbewertung und die Aufschlüsselung sowie die Verbesserungs Aktionen und-Lösungen beziehen sich jetzt nur auf Daten, die von Ihren Filterkriterien abgedeckt werden. Wenn Sie sich bei der Konformitätsbewertung abmelden, bleibt die gefilterte Ansicht erhalten, wenn Sie sich wieder anmelden.

So entfernen Sie Filter:

- Wählen Sie auf der Überschrift " **angewendete Filter** " oberhalb der Konformitätsbewertung das **X** neben dem einzelnen Filter aus, den Sie entfernen möchten. oder
- Wählen Sie in der oberen rechten Ecke des Dashboards **Filter** aus, und wählen Sie dann **Filter löschen**aus.

## <a name="improvement-actions-page"></a>Seite "Verbesserungs Aktionen"

[Verbesserungs Aktionen](compliance-score-improvement-actions.md) zentralisieren Sie Ihre Compliance-Aktivitäten und unterstützen Sie bei der Anpassung an Datenschutzbestimmungen und-Standards. Jede Verbesserungs Aktion enthält detaillierte Anleitungen zur Implementierung und einen Link, mit dem Sie die entsprechende Lösung starten können. Aktionen können Benutzern in Ihrer Organisation zugewiesen werden, um Implementierungs-und Testaufgaben auszuführen. Sie können auch Dokumentation, Notizen und Datensatzstatus Aktualisierungen in der Verbesserungs Aktion speichern.

### <a name="view-your-improvement-actions"></a>Anzeigen von Verbesserungs Aktionen

Das Konformitäts Bewertungs Dashboard zeigt die wichtigsten **Verbesserungs Aktionen**an, bei denen es sich um die am besten verfügbaren Punkte handelt, die die wichtigsten Probleme behandeln.

Wenn Sie alle Verbesserungs Aktionen anzeigen möchten, wählen Sie die Registerkarte **Verbesserungs Aktionen** in Ihrem Dashboard aus. Oder wählen Sie **alle Verbesserungs Aktionen** unterhalb der Liste der wichtigsten Verbesserungs Aktionen in Ihrem Dashboard anzeigen aus.

Wenn Sie eine lange Liste von Aktionen haben, ist es möglicherweise hilfreich, Ihre Ansicht zu filtern. Wählen Sie in der Liste Aktionen in der rechten oberen Ecke den **Filter** aus. Wenn der **Filter** Flyout-Bereich angezeigt wird, wählen Sie Ihre Kriterien basierend auf Regeln und Standards, Lösung und Gruppe aus. Sie können die Ansicht auch anpassen, indem Sie in der oberen rechten Ecke die Option **Gruppe** auswählen. Wählen Sie im Dropdownmenü die Option aus, um nach Gruppe, Lösung, Kategorie, Aktionstyp oder Status anzuzeigen.

In der Standardansicht für diese Seite werden keine Verbesserungs Aktionen mit dem Teststatus " **übergeben**" angezeigt. Zum Anzeigen von Aktionen, die Tests bestanden haben, aktivieren Sie das Kontrollkästchen **übergebenes** Feld im Dropdownbereich Filter. Nur Aktionen mit einem Teststatus der **übergebenen** Zählung zu Ihrer Partitur.

Auf der Seite Verbesserungs Aktionen werden die folgenden Datenpunkte für jede Verbesserungs Aktion angezeigt:

- **Ergebnisauswirkung**: die Punkte, um die sich die Gesamtpunktzahl beim Abschließen der Aktion erhöht
- **Bestimmungen**: die Richtlinie oder Norm im Zusammenhang mit der Aktion
- **Gruppe**: die Gruppe, der Sie die Aktion zugewiesen haben
- **Lösungen**: die Lösung, mit der Sie zur Ausführung der Aktion wechseln können
- **Assessments**: die Bewertung (die Steuerelemente zur Erfüllung eines bestimmten Compliance-Ziels organisiert), in dem sich die Aktion befindet
- **Kategorien**: die zugehörige Datenschutzkategorie (beispielsweise zum Schutz von Informationen, Verwalten von Geräten usw.)
- **Test Status**:
    - **None** – keine Statusaktualisierung aufgezeichnet
    - **Nicht bewertet** – Test wurde nicht gestartet
    - **Übergebene** Implementierung erfolgreich getestet
    - **Fehlgeschlagenes niedriges Risiko** – Testfehler, geringes Risiko
    - **Fehler bei mittlerem Risiko** – Testfehler, mittleres Risiko
    - Fehler **hafte hohe Risiko** Tests, hohes Risiko
    - **Nicht im Bereich** – die Aktion hat keinen Umfang für die Bewertung und wirkt sich nicht auf Ihre Punktzahl aus.
    - **Zu erkennen** : für manuellen Test wird angegeben, dass eine Aktion implementiert, aber nicht getestet wurde; für automatisierte Tests gibt an, dass eine Aktion auf das Automatisierungs Ergebnis wartet.
    - **Konnte nicht ermittelt werden** – automatischer Status kann nicht ermittelt werden
    - **Teilweise getestet** – automatisiertes Scoring zur Vergabe von Teil Punkten
- **Erreichte Punkte**: Anzahl der Punkte, die aus der maximal möglichen Höhe verdient wurden

#### <a name="learn-more"></a>Weitere Informationen
[Siehe Vorgehensweise zuweisen und Ausführen von Arbeiten an Verbesserungs Aktionen](compliance-score-improvement-actions.md).

## <a name="solutions-page"></a>Seite "Lösungen"

Auf der Seite Lösungen wird der Anteil der gesammelten und potenziellen Punkte wie in der Lösung organisiert dargestellt. Das Anzeigen der verbleibenden Punkte und Verbesserungs Aktionen in dieser Ansicht hilft Ihnen zu verstehen, welche Lösungen mehr sofortige Aufmerksamkeit benötigen.

Suchen Sie die Seite Lösungen, indem Sie auf der Registerkarte **Lösungen** im Dashboard für die Konformitätsbewertung auswählen. Sie können auch im oberen rechten Bereich des Dashboards die Option **alle Lösungen** unterhalb von Lösungen anzeigen, die sich **auf Ihre Punktzahl auswirken** .

### <a name="filtering-your-solutions-view"></a>Filtern der Lösungs Ansicht

So filtern Sie die Ansicht von Lösungen:

1. Wählen Sie in der oberen linken Ecke der Liste Bewertungen die Option **Filter** aus.
2. Platzieren Sie im Flyout- **Filter** Bereich eine Überprüfung neben den gewünschten Kriterien (Normen und Verordnungen, Lösung, Aktionstyp, Compliance-Manager-Gruppe, Kategorie).
3. Klicken Sie auf die Schaltfläche über **nehmen** . Der Filterbereich wird geschlossen, und die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt oder Regulierung angezeigt werden, indem Sie den Typ der Gruppierung aus dem Dropdownmenü **Gruppieren** oberhalb Ihrer Bewertungsliste auswählen.

### <a name="taking-actions-from-the-solution-page"></a>Ergreifen von Aktionen auf der Lösungsseite

Auf der Seite Lösungen werden die Lösungen Ihrer Organisation angezeigt, die mit Verbesserungs Aktionen verbunden sind. In der Tabelle sind die Beiträge der einzelnen Lösungen zu ihrer Gesamtpunktzahl, die erzielten Punkte Verbesserungen und mögliche Ergebnisse in dieser Lösung sowie die verbleibende Anzahl von Verbesserungs Aktionen, die in dieser Lösung gruppiert sind, aufgeführt, die Ihre Punktzahl erhöhen können.

Es gibt zwei Möglichkeiten, auf diesem Bildschirm Maßnahmen zu ergreifen:

1. Wählen Sie in der Zeile der gewünschten Lösung unter der Spalte **verbleibende Aktionen** die mit Hyperlinks verlinkte Nummer aus. Auf dem Bildschirm Verbesserungs Aktionen wird eine gefilterte Ansicht angezeigt, in der nicht getestete Verbesserungs Aktionen für diese Lösung angezeigt werden.

2. Wählen Sie in der Zeile der gewünschten Lösung unter der Spalte **Open Solution** die Option **Öffnen**aus. Sie sehen die Lösung oder den Standort im Sicherheits-und Compliance Center von Microsoft 365 und Office 365, in der Sie die empfohlene Aktion durchführen können.

## <a name="assessments-page"></a>Seite "Bewertungen"

Auf der Seite "Bewertungen" werden alle [Bewertungen](compliance-score-assessments.md) aufgelistet, die Sie für Ihre Organisation eingerichtet haben. Der Nenner der Konformitätsbewertung wird durch alle nachverfolgten Bewertungen bestimmt. Je mehr Bewertungen Sie hinzufügen, desto mehr Verbesserungs Aktionen sehen Sie auf der Seite Verbesserungs Aktionen und desto höher ist Ihr Ergebnis Nenner.

Auf dieser Seite werden wichtige Informationen zu den einzelnen Bewertungen zusammengefasst:

- **Bewertung**: Name der Bewertung
- **Status**:
    - **Complete** -alle Steuerelemente haben den Status "übergeben" oder mindestens eine wird übergeben, und der Rest ist "außerhalb des Bereichs".
    - **Unvollständig** – mindestens ein Steuerelement hat den Status "Fehler".
    - **None** -alle Steuerelemente wurden nicht getestet
    - **In Progress** -Improvement Aktionen haben einen anderen Status, einschließlich "in Progress", "teilweiser Kredit" oder "unentdeckt
- **Bewertungs Fortschritt**: der Prozentsatz der Arbeit bis zum Abschluss, gemessen an der Anzahl der erfolgreich getesteten Steuerelemente.
- **Ihre Verbesserungs Aktionen**: die Anzahl der abgeschlossenen Aktionen zur Erfüllung der Implementierung Ihrer Steuerelemente
- **Microsoft-Aktionen**: die Anzahl der abgeschlossenen Aktionen zur Erfüllung der Implementierung von Microsoft-Steuerelementen
- **Group**: Name der Gruppe, zu der die Bewertung gehört
- **Produkt**: zugeordneter Microsoft 365-Dienst
- **Verordnung**: Regulierungsstandard, Richtlinie oder Recht für die Bewertung

### <a name="filtering-your-assessments-view"></a>Filtern der Ansicht "Bewertungen"

So filtern Sie die Ansicht von Bewertungen:

1. Wählen Sie in der oberen linken Ecke der Liste Bewertungen die Option **Filter** aus.
2. Überprüfen Sie im Flyout- **Filter** Bereich die gewünschten Kriterien.
3. Klicken Sie auf die Schaltfläche übernehmen. Der Filterbereich wird geschlossen, und die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt oder Regulierung angezeigt werden, indem Sie den Typ der Gruppierung aus dem Dropdownmenü **Gruppieren** oberhalb Ihrer Bewertungsliste auswählen.

### <a name="default-assessment"></a>Standardbewertung

Standardmäßig wird die [Microsoft 365-Datenschutz-Basis](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline) Bewertung auf der Seite "Bewertungen" angezeigt. Compliance Score bietet auch mehrere vorgefertigte [Vorlagen](compliance-score-templates.md) , aus denen Sie Assessments erstellen können.

## <a name="next-step"></a>Nächster Schritt
Passen Sie die Konformitätsbewertung an, indem [Sie Assessments einrichten](compliance-score-assessments.md).