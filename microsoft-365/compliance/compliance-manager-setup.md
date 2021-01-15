---
title: Erste Schritte mit Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Festlegen von Microsoft Compliance -Manager-Benutzerberechtigungen und -rollen und Konfigurieren automatisierter Tests von Aktionen. Verwalten des Benutzerverlaufs und Filtern der Dashboardansicht
ms.openlocfilehash: e130fc3438fc8b4674b752e25fc473ee0dd55ae4
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870910"
---
# <a name="get-started-with-compliance-manager"></a>Erste Schritte mit Compliance-Manager

**In diesem Artikel:** Dieser Artikel hilft Ihnen beim Einrichten des Compliance-Managers. Erfahren Sie, **wie Sie auf den** Compliance-Manager zugreifen, Rollen **und** Berechtigungen festlegen und automatische Tests **von Verbesserungsmaßnahmen konfigurieren.** Gehen Sie **durch Ihr Compliance-Manager-Dashboard,** und verstehen Sie die Hauptseiten: die Seite "Verbesserungsmaßnahmen", die Lösungsseite, die Bewertungsseite und die Seite mit den Bewertungsvorlagen.

## <a name="who-can-access-compliance-manager"></a>Wer auf den Compliance Manager zugreifen kann

Der Compliance Manager ist für Organisationen mit Office 365- und Microsoft 365-Lizenzen sowie für Kunden der US Government Community Cloud (GCC) Moderate und GCC High verfügbar. Verfügbarkeits- und Verwaltungsfunktionen der Bewertung hängen von Ihrem Lizenzvertrag ab.  [Anzeigen von Dienstbeschreibungsdetails.](https://go.microsoft.com/fwlink/?linkid=2132371)

## <a name="before-you-begin"></a>Vorabinformationen

Der globale Microsoft 365-Administrator für Ihre Organisation ist wahrscheinlich der erste Benutzer, der auf den Compliance Manager zu zugegriffen hat. Wir empfehlen, dass sich der globale Administrator anmeldet und Benutzerberechtigungen wie unten beschrieben beim ersten Besuch des Compliance-Managers festlegen.

## <a name="sign-in"></a>Anmelden

1. Wechseln Sie zum [Microsoft 365 Compliance Center,](https://compliance.microsoft.com/) und **melden** Sie sich mit Ihrem globalen Microsoft 365-Administratorkonto an.
2. Wählen **Sie im linken Navigationsbereich** den Compliance-Manager aus. Sie gelangen zu Ihrem [Compliance-Manager-Dashboard.](#understand-the-compliance-manager-dashboard)

Der direkte Link zum Zugriff auf den Compliance-Manager ist [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Festlegen von Benutzerberechtigungen und Zuweisen von Rollen

Der Compliance-Manager verwendet ein rollenbasiertes Berechtigungsmodell für die Zugriffssteuerung (RBAC). Nur Benutzer, denen eine Rolle zugewiesen ist, können auf den Compliance-Manager zugreifen, und die von jedem Benutzer zugelassenen Aktionen werden nach [Rollentyp eingeschränkt.](#role-types)

### <a name="where-to-set-permissions"></a>Festlegen von Berechtigungen

Die Person, die die globale Administratorrolle für Ihre Organisation hat, kann Benutzerberechtigungen für den #A0 festlegen. Berechtigungen können im Office 365 Security & Compliance Center sowie in Azure Active Directory (Azure AD) festgelegt werden.

> [!NOTE]
> Kunden in einer hohen Umgebung der US Government Community (GCC) können nur Benutzerberechtigungen und Rollen für den Compliance Manager in Azure AD festlegen. Weitere Informationen zu Azure AD-Anweisungen und Rollentypdefinitionen finden Sie weiter unten.

Führen Sie zum Festlegen von Berechtigungen und Zuweisen von Rollen im Office 365 Security & Compliance Center die folgenden Schritte aus:

1. Wechseln Sie zum [Office 365 Security & Compliance Center,](https://protection.office.com/) und **wählen** Sie im linken Navigationsbereich "Berechtigungen" aus.

2. Suchen Sie die Rollengruppe, der Sie einen oder mehrere Benutzer hinzufügen möchten, und aktivieren Sie das Kontrollkästchen links vom Gruppennamen. (Weitere Informationen finden [Sie in der Liste der Rollen und zugehörigen Funktionen weiter unten.](#role-types) Die Rollengruppennamen imitieren den Rollennamen.)

3. Wählen Sie im Flyoutbereich für diese Gruppe unter der **Kopfzeile** "Mitglieder" die Option **"Bearbeiten"** aus.

4. Wählen Sie **Mitglieder auswählen aus.** Ein weiteres Flyoutfenster wird angezeigt.

5. Wählen **Sie +Hinzufügen** aus, um einen oder mehrere Benutzer auszuwählen, die der Gruppe hinzugefügt werden.

6. Aktivieren Sie das Kontrollkästchen neben den Namen, die  Sie hinzufügen möchten, und wählen Sie dann unten die Schaltfläche "Hinzufügen" aus.

7. Wenn Sie mit der Zuweisung von Benutzern fertig sind, wählen Sie **"Fertig"** und dann **"Speichern"** und dann **"Schließen" aus.**

##### <a name="more-about-the-office-365-security--compliance-center"></a>Weitere Informationen zum Office 365 Security & Compliance Center

Weitere Informationen zu [Berechtigungen finden Sie im Office 365 Security & Compliance Center.](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

Wenn Sie keinen Zugriff auf das Office 365 Security and Compliance Center haben oder wenn Sie auf die klassische Version von Compliance Manager im Microsoft Service Trust Portal zugreifen müssen, bieten die Administratoreinstellungen im Service Trust Portal eine weitere Möglichkeit zum Zuweisen von Rollen[(](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)Anweisungen anzeigen). Beachten Sie, dass diese Rollen in ihrer Funktionalität eingeschränkter sind.

##### <a name="more-about-azure-ad"></a>Weitere Informationen zu Azure AD

Informationen zum Zuweisen von Rollen und Festlegen von Berechtigungen in Azure AD finden Sie unter Zuweisen von Administrator- und [Nichtadministratorrollen zu](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)Benutzern mit Azure Active Directory.

Benutzer mit Azure AD-Identitäten, die nicht über Office 365- oder Microsoft 365-Abonnements verfügen, können im Microsoft 365 Compliance Center nicht auf den Compliance Manager zugreifen. Um Unterstützung beim Zugriff auf den Compliance Manager zu erhalten, wenden Sie sich [an cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).

### <a name="role-types"></a>Rollentypen

In der folgenden Tabelle sind die Funktionen aufgeführt, die von den einzelnen Rollen im Compliance-Manager zulässig sind. Die Tabelle zeigt auch, wie jede [Azure AD-Rolle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) Compliance-Manager-Rollen zu ordnet. Benutzer benötigen mindestens die Compliance-Manager-Leserolle oder die globale Azure AD-Leserolle, um auf den Compliance-Manager zu zugreifen.


| Der Benutzer kann: | Rolle "Compliance-Manager" | Azure AD-Rolle | 
| :------------- | :-------------: | :------------: |
| **Lesen, aber nicht bearbeiten von Daten**| Compliance-Manager-Leser  | Globaler Azure AD-Reader, Sicherheitsleseprogramm | 
| **Bearbeiten von Daten**| Compliance-Manager-Beitrag | Complianceadministrator | 
| **Bearbeiten von Testergebnissen**| Compliance-Manager-Bewertung | Complianceadministrator | 
| **Verwalten von Bewertungen sowie Vorlagen- und Mandantendaten**| Verwaltung des Compliance-Managers | Kompatibilitätsadministrator, Kompatibilitätsdatenadministrator, Sicherheitsadministrator  | 
| **Zuweisen von Benutzern**| Globaler Administrator | Globaler Administrator | 

## <a name="settings-for-automated-testing-and-user-history"></a>Einstellungen für automatisierte Tests und Benutzerverlauf

Mit den Compliance-Manager-Einstellungen im Microsoft 365 Compliance Center können Sie automatische Tests von Verbesserungsmaßnahmen aktivieren und deaktivieren. Mit den Einstellungen können Sie auch die Daten von Benutzern verwalten, die Verbesserungsmaßnahmen zugeordnet sind, einschließlich der Möglichkeit, Verbesserungsmaßnahmen einem anderen Benutzer neu zuzuweisen.  Nur Personen mit einer globalen Administrator- oder Compliance-Manager-Administratorrolle können auf die Compliance-Manager-Einstellungen zugreifen.

> [!NOTE]
> Das Feature für automatisierte Tests ist für Kunden in GCC High Umgebungen nicht verfügbar, da die Sicherheitsprüfung in diesen Umgebungen nicht verfügbar ist. GCC High-Kunden müssen ihre Verbesserungsmaßnahmen manuell implementieren und testen.

### <a name="set-up-automated-testing"></a>Einrichten von automatisierten Tests

Einige Verbesserungsmaßnahmen im Compliance Manager werden auch von [der Microsoft Secure Score überwacht.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) Sie können automatisierte Tests von Aktionen einrichten, die gemeinsam überwacht werden, was bedeutet, dass beim Testen und Aktualisieren einer Aktion in der Sicherheitswertung diese Ergebnisse mit denselben Aktionen im Compliance-Manager synchronisiert werden und auf Ihre Compliance-Bewertung angezählt werden.

Automatische Tests sind für Organisationen, die im Compliance Manager neu sind, standardmäßig aktiviert. Wenn Sie Microsoft 365 oder Office 365 zum ersten Mal bereitstellen, dauert es ungefähr sieben Tage, bis die Sicherheitswertung Daten vollständig erfasst und in Ihre Compliance-Bewertung einbe berücksichtigt hat.  Wenn automatisierte Tests aktiviert sind, wird das Testdatum der Aktion nicht aktualisiert, aber der Teststatus wird aktualisiert. Wenn neue Bewertungen erstellt werden, enthalten Bewertungen automatisch Microsoft-Steuerelementbewertungen und die Integration der Sicherheitsbewertung.

Der globale Administrator für Ihre Organisation kann die Einstellungen für automatisierte Tests jederzeit ändern. Sie können automatisierte Tests auf allgemeine Verbesserungsmaßnahmen deaktivieren oder für einzelne Aktionen aktivieren. Befolgen Sie die nachstehenden Anweisungen, um Ihre Einstellungen für automatisierte Tests zu ändern.

#### <a name="to-manage-your-automated-testing-settings"></a>So verwalten Sie die Einstellungen für automatisierte Tests:

1. Wählen **Sie** im Microsoft 365 Compliance Center von einer beliebigen Stelle im [Microsoft 365 Compliance Center die Option "Einstellungen" im linken Navigationsbereich aus.](https://compliance.microsoft.com/)

2. Wählen Sie auf der Einstellungsseite den **Compliance-Manager aus.**

3. Wählen Sie **automatisierte Tests** im linken Navigationsbereich aus.

4. Wählen Sie die entsprechende Schaltfläche aus, um automatische Tests für alle Verbesserungsmaßnahmen zu aktivieren, sie für alle Aktionen zu deaktivieren oder durch einzelne Aktion zu aktivieren.

5. Wenn Sie **"Pro Verbesserungsaktion** aktivieren" auswählen, werden in einer Liste alle verfügbaren Verbesserungsmaßnahmen zur Auswahl angezeigt.  Aktivieren Sie das Kontrollkästchen neben jeder Aktion, die automatisch getestet werden soll.

6. Wählen **Sie "Speichern"** aus, um Ihre Einstellungen zu speichern. Am oberen Rand des Bildschirms wird eine Bestätigungsmeldung angezeigt, dass Ihre Auswahl gespeichert wurde. Wenn Sie eine Fehlerbenachrichtigung erhalten, versuchen Sie es erneut.

**Hinweis:** Nur der globale Administrator kann automatische Updates für alle Aktionen aktivieren oder deaktivieren. Der Compliance-Manager-Administrator kann automatische Updates für einzelne Aktionen aktivieren, jedoch nicht für alle Aktionen global.

### <a name="manage-user-history"></a>Verwalten des Benutzerverlaufs

Mithilfe **der Einstellungen für die Verwaltung des** Benutzerverlaufs können Sie schnell erkennen, welche Benutzer mit Verbesserungsmaßnahmen im Compliance-Manager gearbeitet haben. Die identifizierbaren Benutzerdaten im Zusammenhang mit Verbesserungsmaßnahmen umfassen alle durchgeführten Implementierungs- und Testarbeiten, hochgeladene Dokumente und alle von ihnen eingegebenen Notizen. Möglicherweise müssen Sie diese Art von Daten verstehen und abrufen, um die Complianceanforderungen Ihrer Organisation zu erfüllen.

Mit den Einstellungen für den Benutzerverlauf können Sie auch alle Verbesserungsmaßnahmen von einem Benutzer an einen anderen zuweisen.

**So suchen Sie die Einstellungen für den Benutzerverlauf:**

1. Wählen Sie im Microsoft 365 Compliance Center von einer beliebigen Stelle im [Microsoft 365 Compliance Center die Option "Einstellungen" im linken Navigationsbereich aus.](https://compliance.microsoft.com/)

2. Wählen Sie auf der Einstellungsseite den **Compliance-Manager aus.**

3. Wählen **Sie im linken Navigationsbereich "Benutzerverlauf** verwalten" aus.

Auf **der Seite "Benutzerverlauf verwalten"** wird eine Liste aller Benutzer nach E-Mail-Adresse angezeigt, die einer Verbesserungsaktion zugewiesen sind. Verwenden Sie die **Schaltfläche "Suchen",** um einen bestimmten Benutzer schnell zu finden, indem Sie seine E-Mail-Adresse eingeben.

Rechts neben der E-Mail-Adresse  jedes Benutzers enthält das Dropdownmenü "Auswählen" Optionen zum Exportieren eines Berichts, zum erneuten Zuweisen von Verbesserungsmaßnahmen oder zum Löschen des Verlaufs. Details zu den einzelnen Optionen finden Sie in den einzelnen Abschnitten weiter unten.

#### <a name="export-a-report-of-user-history-data"></a>Exportieren eines Berichts mit Benutzerverlaufsdaten

Sie können eine Excel-Datei exportieren, die eine Liste der Verbesserungsmaßnahmen enthält, die derzeit einem Benutzer zugewiesen sind.  Der Bericht enthält auch alle Nachweisdateien, die von diesem Benutzer hochgeladen wurden. Diese Informationen können Ihnen helfen, offene Verbesserungsmaßnahmen neu zuzuweisen.

Der Bericht gibt den Status der Verbesserungsaktion ab dem Erstellungsdatum wieder. Es ist kein verlaufshistorischen Bericht über alle vorherigen Änderungen am Status oder der Zuweisung (erfahren Sie, wie Sie einen Bericht von Ihrer Seite mit [Verbesserungsmaßnahmen exportieren).](compliance-manager-improvement-actions.md#export-a-report)

**Führen Sie die folgenden Schritte aus, um einen Bericht nach Benutzer zu exportieren:**

1. Wählen **Sie** im Microsoft 365 Compliance Center von einer beliebigen Stelle im [Microsoft 365 Compliance Center die Option "Einstellungen" im linken Navigationsbereich aus.](https://compliance.microsoft.com/)

2. Wählen Sie auf der Einstellungsseite den **Compliance-Manager aus.**

3. Wählen **Sie in der Navigation links die** Option "Benutzerverlauf verwalten" aus.

4. Suchen Sie den beabsichtigten Benutzer, indem  Sie die E-Mail-Adressen der Liste durchsuchen oder indem Sie "Suchen" auswählen und die E-Mail-Adresse des Benutzers eingeben.

5. Wählen Sie **im Dropdownmenü** "Auswählen" die Option **"Bericht exportieren" aus.**

6. Nachdem die Excel-Datei Ihres Berichts generiert wurde, können Sie sie öffnen und auf Ihrem lokalen Computer speichern.

#### <a name="reassign-improvement-actions-to-another-user"></a>Erneutes Zuweisen von Verbesserungsmaßnahmen zu einem anderen Benutzer

Sie können Verbesserungsmaßnahmen von einem Benutzer zu einem anderen zuweisen. Wenn Sie eine Aktion erneut zuweisen, ändert sich der Uploadverlauf des Dokuments nicht, aber der Name des Benutzers, der die Dokumentation ursprünglich hochgeladen hat, wird in der Verbesserungsaktion nicht mehr angezeigt.

**Führen Sie die folgenden Schritte aus, um Verbesserungsmaßnahmen einem anderen Benutzer neu zuzuweisen:**

1. Wählen **Sie** im Microsoft 365 Compliance Center von einer beliebigen Stelle im [Microsoft 365 Compliance Center die Option "Einstellungen" im linken Navigationsbereich aus.](https://compliance.microsoft.com/)

2. Wählen Sie auf der Einstellungsseite den **Compliance-Manager aus.**

3. Wählen **Sie in der Navigation links die** Option "Benutzerverlauf verwalten" aus.

4. Suchen Sie einen Benutzer, indem Sie  die E-Mail-Adressen der Liste durchsuchen oder indem Sie "Suchen" auswählen und die E-Mail-Adresse dieses Benutzers eingeben.

5. Wählen Sie **im Dropdownmenü** "Auswählen" die Option **"Verbesserungsmaßnahmen neu zuweisen" aus.** Der **Flyoutbereich "Verbesserungsmaßnahmen** neu zuweisen" wird angezeigt.

6. Geben Sie **im Feld Benutzer suchen** den Namen oder die E-Mail-Adresse des Benutzers ein, dem Sie die Verbesserungsmaßnahmen zuweisen *möchten.*

7. Wenn der Name des beabsichtigten Benutzers unter Verbesserungsmaßnahmen zugewiesen **wird,** wählen Sie den Benutzer aus, und wählen Sie dann **"Aktionen zuweisen" aus.**

8. Nach Abschluss der Neuzuweisung wird im Flyoutbereich eine Bestätigungsmeldung angezeigt, die bestätigt, dass alle Verbesserungsmaßnahmen des vorherigen Benutzers dem neuen Benutzer neu zugewiesen wurden. Wenn Sie eine Benachrichtigung über einen Fehler bei der Neuzuweisung erhalten, schließen Sie das Fenster, und versuchen Sie es erneut. Um den Flyoutbereich zu schließen, wählen Sie **"Fertig"** aus.

Der neue Zugewiesene erhält eine E-Mail, dass er einer Verbesserungsaktion zugewiesen wurde. Die E-Mail enthält einen direkten Link zur Detailseite der Verbesserungsaktion.
 
 > [!NOTE]
> Wenn Sie eine Aktion mit einer ausstehenden Aktualisierung erneut zuweisen, wird der direkte Link zu der Aktion in der E-Mail zur Neuzuweisung nicht mehr aktualisiert, wenn das Update nach der neu zugewiesenen Aktualisierung akzeptiert wird. Sie können dieses Problem beheben, indem Sie die Aktion dem Benutzer erneut zuweisen, nachdem das Update akzeptiert wurde. Erfahren Sie mehr über [Updates für Verbesserungsmaßnahmen.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

#### <a name="delete-user-history"></a>Löschen des Benutzerverlaufs

Durch das Löschen des Verlaufs eines Benutzers wird der Benutzer als Besitzer von Verbesserungsmaßnahmen entfernt, und sein Name wird aus allen anderen Feldern im Compliance-Manager entfernt. Wenn Sie den Verlauf eines Benutzers löschen, wird für die Verbesserungsmaßnahmen, die er im Besitz hat, erst ein Wert vom Wert **"Zugewiesen zu"** angezeigt, wenn ein neuer Benutzer zugewiesen wurde. Alle Dokumente, die in die Verbesserungsaktion hochgeladen wurden, zeigen den entfernten Benutzer **an** stelle des Namens des gelöschten Benutzers an. Das Löschen des Benutzerverlaufs ist dauerhaft.

Führen Sie die folgenden Schritte aus, um den Verlauf eines Benutzers zu löschen:

1. Wählen **Sie** im Microsoft 365 Compliance Center von einer beliebigen Stelle im [Microsoft 365 Compliance Center die Option "Einstellungen" im linken Navigationsbereich aus.](https://compliance.microsoft.com/)

2. Wählen Sie auf der Einstellungsseite den **Compliance-Manager aus.**

3. Wählen **Sie in der Navigation links die** Option "Benutzerverlauf verwalten" aus.

4. Suchen Sie einen Benutzer, indem Sie  die E-Mail-Adressen der Liste durchsuchen oder indem Sie "Suchen" auswählen und die E-Mail-Adresse dieses Benutzers eingeben.

5. Wählen Sie **im Dropdownmenü** "Auswählen" die Option **"Verlauf löschen" aus.**

6. In einem Fenster werden Sie aufgefordert, die dauerhafte Löschung des Verlaufs des Benutzers zu bestätigen. Um mit dem Löschen fortzufahren, wählen Sie **"Verlauf löschen" aus.** Um den Verlauf zu verlassen, ohne den Verlauf zu löschen, wählen Sie **Abbrechen** aus.

7. Sie gelangen zurück zur  Seite "Benutzerverlauf verwalten" mit einer Bestätigungsmeldung oben, dass der Verlauf für den Benutzer gelöscht wurde.

## <a name="understand-the-compliance-manager-dashboard"></a>Verstehen des Compliance-Manager-Dashboards

Das Compliance-Manager-Dashboard bietet Ihnen einen Überblick über Ihren aktuellen Compliance-Status.

![Compliance-Manager – Dashboard](../media/compliance-manager-dashboard.png "Compliance-Manager-Dashboard")

### <a name="overall-compliance-score"></a>Compliance-Gesamtergebnis

Ihre Compliance-Bewertung wird oben deutlich präsentiert. Sie zeigt einen Prozentsatz an, der auf Punkten basiert, die zur Durchführung von Verbesserungsmaßnahmen erreicht werden können, die wichtige Datenschutzstandards und -vorschriften erfüllen. Punkte aus [Microsoft-Aktionen,](compliance-manager-assessments.md#microsoft-actions-tab)die von Microsoft verwaltet werden, zählen auch auf Ihre Compliance-Bewertung.

Wenn Sie zum ersten Mal zum Compliance-Manager kommen, basiert Ihre anfängliche Bewertung auf der [Microsoft 365-Datenschutzgrundlinie.](compliance-manager-assessments.md#data-protection-baseline-default-assessment) Bei dieser grundlegenden Bewertung, die für alle Organisationen verfügbar ist, handelt es sich um eine Reihe von Kontrollen, die allgemeine branchenübliche Vorschriften und Standards umfassen. Der Compliance-Manager überprüft Ihre vorhandenen Microsoft 365-Lösungen und erstellt eine erste Bewertung basierend auf Ihren aktuellen Datenschutz- und Sicherheitseinstellungen. Wenn Sie Bewertungen hinzufügen, die für Ihre Organisation relevant sind, wird Ihre Bewertung für Sie aussagekräftiger.

**Weitere Informationen: Verstehen** [Sie, wie Ihre Compliance-Bewertung berechnet wird.](compliance-score-calculation.md)

### <a name="key-improvement-actions"></a>Wichtige Verbesserungsmaßnahmen

In diesem Abschnitt werden die besten Verbesserungsmaßnahmen aufgeführt, die Sie zur zeit ergreifen können, um die größten positiven Auswirkungen auf die Gesamt-Compliance-Bewertung zu erzielen. Wählen **Sie "Alle Verbesserungsmaßnahmen anzeigen"** aus, um zur Seite mit den Verbesserungsmaßnahmen zu wechseln.

### <a name="solutions-that-affect-your-score"></a>Lösungen, die sich auf Ihre Bewertung auswirken

In diesem Abschnitt werden Lösungen mit Verbesserungsmaßnahmen beschrieben, die sich positiv auf Ihre Bewertung auswirken können, sowie die Anzahl der ausstehenden Verbesserungsmaßnahmen in diesen Lösungen. Wählen **Sie "Alle Lösungen anzeigen"** aus, um ihre Lösungsseite zu besuchen.

### <a name="compliance-score-breakdown"></a>Aufschlüsselung der Compliance-Bewertung

In diesem Abschnitt erhalten Sie eine detailliertere Ansicht Ihrer Bewertung auf zwei verschiedene Arten:

- **Kategorien:** Zeigt den Prozentsatz Ihrer Gesamtpunktzahl innerhalb von Datenschutzkategorien an, z. B. "Informationen schützen" oder "Geräte verwalten".
- **Bewertungen:** Zeigt den Prozentsatz Ihres Fortschritts bei der Verwaltung von Bewertungen für bestimmte Compliance- und Datenschutzstandards, Vorschriften oder Gesetze wie DSGVO oder NIST 800-53 an.

### <a name="filtering-your-dashboard-view"></a>Filtern der Dashboardansicht

Sie können Ihre Dashboardansicht filtern, um nur die Elemente im Zusammenhang mit bestimmten Vorschriften und Standards, Lösungen, Aktionstypen, Bewertungsgruppen oder Datenschutzkategorien anzuzeigen. Wenn Sie Ihre Ansicht auf diese Weise filtern, wird auch die Bewertung auf Ihrem Dashboard gefiltert, die zeigt, wie viele Punkte Sie anhand Ihrer Filterkriterien aus den insgesamt möglichen Punkten erzielt haben.

So wenden Sie Filter an:

1. Wählen **Sie oben** rechts im Dashboard "Filter" aus.
2. Wählen Sie im  Flyoutbereich "Filter" die Filterkriterien aus, und wählen Sie dann **"Übernehmen" aus.**

Nachdem Sie einen Filter angewendet haben, wird Ihre Bewertung in Echtzeit angepasst. Der Prozentsatz und die Aufschlüsselung der Compliance-Bewertung sowie die Verbesserungsmaßnahmen und -lösungen gelten jetzt nur noch für Daten, die von Ihren Filterkriterien abgedeckt werden. Wenn Sie sich vom Compliance Manager abmelden, bleibt die gefilterte Ansicht erhalten, wenn Sie sich wieder anmelden.

So entfernen Sie Filter:

- Wählen Sie **in der Überschrift "Angewendete** Filter" oberhalb ihrer Compliance-Bewertung das **X** neben dem einzelnen Filter aus, den Sie entfernen möchten. oder
- Wählen **Sie** oben rechts im Dashboard "Filter"  und dann im Flyoutbereich "Filter **löschen" aus.**

## <a name="improvement-actions-page"></a>Seite "Verbesserungsmaßnahmen"

[Verbesserungsmaßnahmen](compliance-manager-improvement-actions.md) sind Aktionen, die von Ihrer Organisation verwaltet werden. Die Arbeit mit Verbesserungsmaßnahmen trägt dazu bei, Ihre Complianceaktivitäten zu zentralisieren und sich an den Datenschutzbestimmungen und -standards auszurichten. Jede Verbesserungsaktion enthält detaillierte Implementierungsanleitungen und einen Link, um Sie in die entsprechende Lösung zu starten. Verbesserungsmaßnahmen können Benutzern in Ihrer Organisation zugewiesen werden, um Implementierungs- und Testarbeiten durchzuführen. Sie können auch Dokumentationen, Notizen und Statusaktualisierungen innerhalb der Verbesserungsaktion speichern.

### <a name="view-your-improvement-actions"></a>Anzeigen Ihrer Verbesserungsmaßnahmen

Das Compliance-Manager-Dashboard zeigt Ihre **wichtigsten Verbesserungsmaßnahmen.** Um alle Verbesserungsmaßnahmen anzuzeigen, wählen Sie die Registerkarte "Verbesserungsmaßnahmen" auf Ihrem Dashboard aus, die Sie zu Ihrer Seite mit Verbesserungsmaßnahmen führt. Sie können auch alle Verbesserungsmaßnahmen unter der Liste der wichtigsten Verbesserungsmaßnahmen auf Ihrem Dashboard anzeigen auswählen, um zu Ihrer Seite mit Verbesserungsmaßnahmen zu gelangen.

Auf der Seite "Verbesserungsmaßnahmen" werden alle Verbesserungsmaßnahmen angezeigt, die von Ihrer Organisation verwaltet werden. Aktionen, die von Microsoft verwaltet werden, können in jeder Bewertung angezeigt werden (erfahren Sie mehr über [Microsoft-Aktionen).](compliance-manager-assessments.md#microsoft-actions-tab)

Wenn Ihre Seite mit Verbesserungsmaßnahmen eine lange Liste von Aktionen enthält, kann es hilfreich sein, Ihre Ansicht zu filtern. Wählen **Sie "Filter"** in der oberen rechten Ecke der Aktionsliste aus. Wenn der **Flyoutbereich** "Filter" angezeigt wird, wählen Sie Ihre Kriterien basierend auf Vorschriften und Standards, Lösung und Gruppe aus. Sie können Ihre Ansicht auch anpassen, indem **Sie** in der oberen rechten Ecke "Gruppe" auswählen. Wählen Sie im Dropdownmenü die Option aus, um sie nach Gruppe, Lösung, Kategorie, Aktionstyp oder Status anzuzeigen.

In der Standardansicht für diese Seite werden keine Verbesserungsmaßnahmen mit dem Teststatus **"Passed" angezeigt.** Zum Anzeigen von Aktionen, die die Tests bestanden haben, aktivieren Sie das Kontrollkästchen **"Übergeben"** im Flyoutbereich "Filter". Nur Aktionen mit dem Teststatus **"Bestanden"** werden in Richtung Ihrer Bewertung gezählt. Einige Aktionen zeigen möglicherweise eine **ausstehende Aktualisierungsbezeichnung an.** Erfahren Sie mehr über [Updates für Verbesserungsmaßnahmen.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

Auf der Seite "Verbesserungsmaßnahmen" werden die folgenden Datenpunkte für jede Verbesserungsaktion angezeigt:

- **Punkte erreicht:** die Anzahl der Punkte, die aus der Gesamtzahl der verfügbaren Punkte durch Abschluss der Aktion erzielt wurden.
- **Vorschriften:** die Vorschriften oder Standards im Zusammenhang mit der Aktion
- **Gruppe**: die Gruppe, der Sie die Aktion zugewiesen haben
- **Lösungen:** die Lösung, in der Sie die Aktion ausführen können
- **Bewertungen:** die Bewertungen, die die Aktion enthalten
- **Kategorien:** die zugehörige Datenschutzkategorie (z. B. Schützen von Informationen, Verwalten von Geräten usw.)
- **Teststatus:**
    - **Keine** – keine Statusaktualisierung aufgezeichnet
    - **Nicht bewertet** – Tests wurden noch nicht gestartet
    - **Übergeben** – Implementierung erfolgreich getestet
    - **Fehlgeschlagenes niedriges Risiko** – Test fehlgeschlagen, niedriges Risiko
    - **Mittleres Risiko fehlgeschlagen** – Test fehlgeschlagen, mittleres Risiko
    - **Fehlgeschlagenes hohes Risiko** – Test fehlgeschlagen, hohes Risiko
    - **Nicht im Bereich –** die Aktion befindet sich nicht im Bereich der Bewertung und hat keine Auswirkungen auf Ihre Bewertung.
    - **Zu erkennen –** gibt für den manuellen Test an, dass eine Aktion implementiert, aber nicht getestet wurde. für automatisierte Tests, gibt an, dass eine Aktion auf automatisierungsergebnis wartet
    - **Nicht erkannt –** automatisierter Status kann nicht ermittelt werden
    - **Teilweise getestet –** automatisierte Bewertung, die Teilpunkte ausgibt

**Weitere Informationen:** [Hier erfahren Sie, wie Sie Verbesserungsmaßnahmen zuweisen und arbeiten.](compliance-manager-improvement-actions.md)

## <a name="solutions-page"></a>Lösungsseite

Auf der Seite "Lösungen" wird der Anteil der gewonnenen und potenziellen Punkte nach Lösung organisiert angezeigt. Wenn Sie die verbleibenden Punkte und Verbesserungsmaßnahmen aus dieser Ansicht anzeigen, können Sie verstehen, welche Lösungen eine sofortigere Aufmerksamkeit erfordern.

Suchen Sie die Lösungsseite, indem Sie **die** Registerkarte "Lösungen" im Compliance-Manager-Dashboard auswählen. Sie können auch **alle** Lösungen  unter "Lösungen" anzeigen auswählen, die sich auf Ihre Bewertung im oberen rechten Bereich Des Dashboards auswirken.

### <a name="filtering-your-solutions-view"></a>Filtern der Lösungsansicht

So filtern Sie die Ansicht von Lösungen:

1. Wählen **Sie in** der oberen linken Ecke der Bewertungsliste "Filter" aus.
2. Platzieren Sie **im Flyoutbereich** "Filter" eine Prüfung neben den gewünschten Kriterien (Standards und Vorschriften, Lösung, Aktionstyp, Compliance-Manager-Gruppe, Kategorie).
3. Wählen Sie die **Schaltfläche "Übernehmen"** aus. Der Filterbereich wird geschlossen, und Die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt  oder Vorschrift angezeigt werden, indem Sie den Gruppierungstyp im Dropdownmenü "Gruppe" oberhalb Ihrer Bewertungsliste auswählen.

### <a name="taking-action-from-the-solution-page"></a>Ergreifen von Aktionen auf der Lösungsseite

Auf der Seite "Lösungen" werden die Lösungen Ihrer Organisation angezeigt, die mit Verbesserungsmaßnahmen verbunden sind. In der Tabelle sind der Beitrag jeder Lösung zu Ihrer Gesamtpunktzahl, die in dieser Lösung erzielten und möglichen Punkte und die verbleibende Anzahl von Verbesserungsmaßnahmen in dieser Lösung aufgeführt, die Ihre Bewertung erhöhen können.

Es gibt zwei Möglichkeiten, wie Sie auf diesem Bildschirm Maßnahmen ergreifen können:

1. Wählen Sie in der Zeile der vorgesehenen Lösung unter der Spalte **"Verbleibende** Aktionen" die Nummer mit dem Hyperlink aus. Es wird eine gefilterte Ansicht des Bildschirms mit Verbesserungsmaßnahmen mit nicht getesteten Verbesserungsmaßnahmen für diese Lösung angezeigt.

2. Wählen Sie in der Zeile der vorgesehenen Lösung unter der **Spalte** Projektmappe öffnen die Option **Öffnen aus.** Sie sehen die Lösung oder den Speicherort im Microsoft 365- und Office 365 Security and Compliance Center, wo Sie die empfohlene Aktion ergreifen können.

## <a name="assessments-page"></a>Bewertungsseite

Auf der Seite "Bewertungen" werden alle [Bewertungen aufgeführt,](compliance-manager-assessments.md) die Sie für Ihre Organisation eingerichtet haben. Ihr Compliancebewertungs denominator wird durch alle Ihre nachverfolgten Bewertungen bestimmt. Wenn Sie weitere Bewertungen hinzufügen, werden weitere Verbesserungsmaßnahmen auf Ihrer Seite mit Verbesserungsmaßnahmen aufgeführt, und Ihr Nenner der Compliancebewertung nimmt zu.

Auf der Bewertungsseite werden die wichtigsten Informationen zu den einzelnen Bewertungen zusammengefasst:

- **Bewertung:** Name der Bewertung
- **Status:**
    - **Vollständig** – alle Steuerelemente haben den Status "übergeben", oder mindestens ein Steuerelement wird übergeben, und die restlichen Steuerelemente liegen "nicht im Gültigkeitsbereich".
    - **Unvollständig** – mindestens ein Steuerelement hat den Status "fehlgeschlagen".
    - **Keine** – alle Steuerelemente wurden noch nicht getestet
    - **In Bearbeitung** – Verbesserungsmaßnahmen haben einen anderen Status, z. B. "In Bearbeitung", "Teilweise Gutschrift" oder "Nicht erkannt"
- **Bewertungsfortschritt:** Der Prozentsatz der Arbeit, die in Richtung des Abschlusses ausgeführt wurde, gemessen durch die Anzahl der erfolgreich getesteten Steuerelemente.
- **Ihre Verbesserungsmaßnahmen:** die Anzahl der abgeschlossenen Aktionen, um die Implementierung Ihrer Steuerelemente zu erfüllen
- **Microsoft-Aktionen:** Die Anzahl der abgeschlossenen Aktionen zur Erfüllung der Implementierung von Microsoft-Steuerelementen.
- **Gruppe:** Name der Gruppe, zu der die Bewertung gehört
- **Produkt**: zugeordneter Microsoft 365-Dienst
- **Verordnung:** der regulatorische Standard, die Richtlinie oder das Recht, das für die Bewertung gilt

### <a name="filtering-your-assessments-view"></a>Filtern der Bewertungsansicht

So filtern Sie die Ansicht der Bewertungen:

1. Wählen **Sie in** der oberen linken Ecke der Bewertungsliste "Filter" aus.
2. Überprüfen Sie **im Flyoutbereich** "Filter" die gewünschten Kriterien.
3. Wählen Sie die **Schaltfläche "Übernehmen"** aus. Der Filterbereich wird geschlossen, und die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt  oder Vorschrift angezeigt werden, indem Sie den Gruppierungstyp im Dropdownmenü "Gruppe" oberhalb Ihrer Bewertungsliste auswählen.

### <a name="default-assessment"></a>Standardbewertung

Standardmäßig wird die Bewertung [](compliance-manager-assessments.md#data-protection-baseline-default-assessment) der Datenschutzgrundwerte auf der Bewertungsseite angezeigt. Der Compliance-Manager stellt außerdem mehrere vordefinierte Vorlagen [für die](compliance-manager-templates-list.md) Gebäudebewertung bereit.

## <a name="assessment-templates-page"></a>Seite "Bewertungsvorlagen"

Eine Vorlage ist ein Framework zum Erstellen einer Bewertung im Compliance-Manager. Auf der Seite mit den Bewertungsvorlagen wird eine Liste mit Vorlagen und wichtigen Details angezeigt. Die Liste enthält Vorlagen, die vom Compliance Manager bereitgestellt werden, sowie alle Vorlagen, die Ihre Organisation geändert oder erstellt hat. Sie können Filter anwenden, um eine Vorlage basierend auf Zertifizierung, Produktbereich, Land, Branche und dem Benutzer zu finden, der sie erstellt hat.

Wählen Sie in der Zeile eine Vorlage aus, um die Detailseite anzuzeigen, die eine Beschreibung der Vorlage sowie weitere Informationen zu Zertifizierung, Bereich und Steuerelementdetails enthält. Auf dieser Seite können Sie die entsprechenden Schaltflächen auswählen, um eine Bewertung zu erstellen, die Vorlagendaten nach Excel zu exportieren oder die Vorlage zu ändern.

**Weitere Informationen:** [Lesen Sie, wie Sie mit Bewertungsvorlagen arbeiten.](compliance-manager-templates.md)

## <a name="next-step"></a>Nächster Schritt
Passen Sie den Compliance-Manager an, [indem Sie Bewertungen einrichten.](compliance-manager-assessments.md)
