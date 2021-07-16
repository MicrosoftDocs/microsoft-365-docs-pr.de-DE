---
title: Erste Schritte mit Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
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
description: Legen Sie Benutzerberechtigungen und Rollen von Microsoft Compliance Manager fest, und konfigurieren Sie automatisierte Tests von Aktionen. Verwalten des Benutzerverlaufs und Filtern der Dashboardansicht.
ms.openlocfilehash: 4791948f6fe3ca6df620a0e93851dbf4e11edd98
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454017"
---
# <a name="get-started-with-compliance-manager"></a>Erste Schritte mit Compliance-Manager

**In diesem Artikel:** Dieser Artikel hilft Ihnen beim Einrichten des Compliance-Managers. Erfahren Sie, wie Sie auf compliance-Manager **zugreifen,** **Rollen und Berechtigungen festlegen** und automatische Tests von **Verbesserungsmaßnahmen** konfigurieren. Gehen Sie durch **Ihr Compliance-Manager-Dashboard,** und verstehen Sie die Hauptseiten: die Seite "Verbesserungsmaßnahmen", die Seite "Lösungen", die Seite "Bewertungen" und die Seite "Bewertungsvorlagen".

## <a name="who-can-access-compliance-manager"></a>Wer können auf den Compliance-Manager zugreifen

Compliance-Manager ist für Organisationen mit Office 365- und Microsoft 365-Lizenzen sowie für Us-Government Community Cloud (GCC) moderate, GCC High- und Department of Defense (DoD)-Kunden verfügbar. Die Bewertungsverfügbarkeit und Verwaltungsfunktionen hängen von Ihrem Lizenzvertrag ab.  [Anzeigen von Dienstbeschreibungsdetails.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="before-you-begin"></a>Bevor Sie beginnen

Der Microsoft 365 globale Administrator für Ihre Organisation wird wahrscheinlich der erste Benutzer sein, der auf compliance-Manager zugreift. Es wird empfohlen, dass sich der globale Administrator anmeldet und die Benutzerberechtigungen wie unten beschrieben beim ersten Besuch des Compliance-Managers festlegen.

## <a name="sign-in"></a>Anmelden

1. Wechseln Sie zum [Microsoft 365 Compliance Center,](https://compliance.microsoft.com/) und **melden Sie sich** mit Ihrem Microsoft 365 globalen Administratorkonto an.
2. Wählen Sie im linken Navigationsbereich **den Compliance-Manager** aus. Sie gelangen zu Ihrem [Compliance-Manager-Dashboard.](#understand-the-compliance-manager-dashboard)

Der direkte Link für den Zugriff auf compliance-Manager lautet [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Festlegen von Benutzerberechtigungen und Zuweisen von Rollen

Compliance-Manager verwendet ein rollenbasiertes Zugriffssteuerungsmodell (RBAC). Nur Benutzer, denen eine Rolle zugewiesen ist, können auf den Compliance-Manager zugreifen, und die von jedem Benutzer zulässigen Aktionen sind durch [den Rollentyp](#role-types)eingeschränkt.

### <a name="where-to-set-permissions"></a>Festlegen von Berechtigungen

Die Person, die die globale Administratorrolle für Ihre Organisation hat, kann Benutzerberechtigungen für Compliance-Manager festlegen. Berechtigungen können sowohl im Microsoft 365 Compliance Center als auch in Azure Active Directory (Azure AD) festgelegt werden.

> [!NOTE]
> Kunden in den Umgebungen "High" und "Department of Defense" (DoD) von US Government Community (GCC) können nur Benutzerberechtigungen und -rollen für Compliance-Manager in Azure AD festlegen. Azure AD-Anweisungen und Rollentypdefinitionen finden Sie unten.

Führen Sie die folgenden Schritte aus, um Berechtigungen festzulegen und Rollen im Microsoft 365 Compliance Center zuzuweisen:

1. Wechseln Sie zum [Microsoft 365 Compliance Center,](https://compliance.microsoft.com/compliancemanager) und wählen Sie im linken Navigationsbereich **"Berechtigungen"** aus.

2. Wählen Sie im Compliance **Center-Dropdown** die Option **"Rollen"** aus. 

3. Suchen Sie die Rollengruppe, der Sie einen oder mehrere Benutzer hinzufügen möchten, und aktivieren Sie das Kontrollkästchen links neben dem Gruppennamen. (Siehe [liste der Rollen und zugehörigen Funktionen unten](#role-types). Die Rollengruppennamen imitieren den Rollennamen.)

4. Wählen Sie im Flyoutbereich für diese Gruppe unter der Kopfzeile **"Mitglieder"** die Option **"Bearbeiten"** aus.

5. Wählen Sie **"Mitglieder auswählen" aus.** Ein weiteres Flyoutfenster wird angezeigt.

6. Wählen Sie **+Hinzufügen aus,** um einen oder mehrere Benutzer auszuwählen, die der Gruppe hinzugefügt werden sollen.

7. Aktivieren Sie das Kontrollkästchen neben den Namen, die Sie hinzufügen möchten, und klicken Sie dann unten auf die Schaltfläche **"Hinzufügen".**

8. Wenn Sie mit dem Zuweisen von Benutzern fertig sind, wählen Sie **"Fertig"** und dann **"Speichern"** und dann **"Schließen"** aus.

Wenn Sie im Microsoft Service Trust Portal auf die klassische Version des Compliance-Managers zugreifen müssen, bieten die Administratoreinstellungen im Service Trust Portal eine weitere Möglichkeit zum Zuweisen von Rollen[(Anweisungen anzeigen).](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users) Beachten Sie, dass solche Rollen in ihrer Funktionalität eingeschränkt sind.

##### <a name="more-about-azure-ad"></a>Weitere Informationen zu Azure AD

Informationen zum Zuweisen von Rollen und Festlegen von Berechtigungen in Azure AD finden Sie unter [Zuweisen von Administrator- und Nicht-Administratorrollen zu Benutzern mit Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

Benutzer mit Azure AD-Identitäten, die nicht über Office 365 oder Microsoft 365 Abonnements verfügen, können im Microsoft 365 Compliance Center nicht auf den Compliance-Manager zugreifen. Wenden Sie sich an [cmresearch@microsoft.com,](mailto:cmresearch@microsoft.com)um Unterstützung beim Zugriff auf Compliance-Manager zu erhalten.

### <a name="role-types"></a>Rollentypen

In der folgenden Tabelle sind die Funktionen aufgeführt, die von den einzelnen Rollen im Compliance-Manager zulässig sind. Die Tabelle zeigt auch, wie jede [Azure AD-Rolle](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) Compliance-Manager-Rollen zugeordnet wird. Benutzer benötigen mindestens die Compliance-Manager-Leserrolle oder die globale Azure AD-Leserrolle, um auf den Compliance-Manager zuzugreifen.


| Der Benutzer kann: | Rolle "Compliance-Manager" | Azure AD-Rolle | 
| :------------- | :-------------: | :------------: |
| **Daten lesen, aber nicht bearbeiten**| Compliance-Manager-Leser  | Azure AD Global Reader, Security Reader | 
| **Daten bearbeiten**| Compliance-Manager-Beitrag | Complianceadministrator | 
| **Bearbeiten von Testergebnissen**| Compliance-Manager-Sachverständiger | Complianceadministrator | 
| **Verwalten von Bewertungen sowie Vorlagen- und Mandantendaten**| Compliance-Manager-Verwaltung | Complianceadministrator, Compliance-Datenadministrator, Sicherheitsadministrator  | 
| **Zuweisen von Benutzern**| Globaler Administrator | Globaler Administrator | 

## <a name="settings-for-automated-testing-and-user-history"></a>Einstellungen für automatisierte Tests und den Benutzerverlauf

Mit den Compliance-Manager-Einstellungen im Microsoft 365 Compliance Center können Sie das automatische Testen von Verbesserungsmaßnahmen aktivieren und deaktivieren. Mit den Einstellungen können Sie auch die Daten von Benutzern verwalten, die verbesserungsaktionen zugeordnet sind, einschließlich der Möglichkeit, Verbesserungsmaßnahmen einem anderen Benutzer neu zuzuweisen.  Nur Personen mit einer globalen Administrator- oder Compliance-Manager-Administratorrolle können auf die Compliance-Manager-Einstellungen zugreifen.

> [!NOTE]
> Das Feature für automatisierte Tests ist für Kunden in GCC High- und DoD-Umgebungen nicht verfügbar, da die Sicherheitsbewertung in diesen Umgebungen nicht verfügbar ist. GCC High- und DoD-Kunden müssen ihre Verbesserungsmaßnahmen manuell implementieren und testen.

### <a name="set-up-automated-testing"></a>Einrichten automatisierter Tests

Einige Verbesserungsmaßnahmen im Compliance-Manager werden auch von [Microsoft Secure Score](../security/defender/microsoft-secure-score.md)überwacht. Sie können automatisierte Tests von Aktionen einrichten, die gemeinsam überwacht werden. Dies bedeutet, dass beim Testen und Aktualisieren einer Aktion in der Sicherheitsbewertung diese Ergebnisse mit den gleichen Aktionen im Compliance-Manager synchronisiert und auf Ihre Compliancebewertung gezählt werden.

Automatische Tests sind standardmäßig für Organisationen aktiviert, die neu im Compliance-Manager sind. Wenn Sie Microsoft 365 oder Office 365 zum ersten Mal bereitstellen, dauert es ungefähr sieben Tage, bis die Sicherheitsbewertung Daten vollständig erfasst und in Ihre Compliancebewertung einfügt.  Wenn automatisierte Tests aktiviert sind, wird das Testdatum der Aktion nicht aktualisiert, aber der Teststatus wird aktualisiert. Wenn neue Bewertungen erstellt werden, umfassen die Bewertungen automatisch Microsoft-Kontrollergebnisse und die Integration der Sicherheitsbewertung.

Der globale Administrator Für Ihre Organisation kann die Einstellungen für automatisierte Tests jederzeit ändern. Sie können automatisierte Tests für allgemeine Verbesserungsmaßnahmen deaktivieren oder für einzelne Aktionen aktivieren. Befolgen Sie die nachstehenden Anweisungen, um Ihre Einstellungen für automatisierte Tests zu ändern.

#### <a name="to-manage-your-automated-testing-settings"></a>So verwalten Sie Ihre Einstellungen für automatisierte Tests:

1. Wählen Sie **Einstellungen** in der linken Navigationsleiste von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie auf der Einstellungsseite **Compliance-Manager** aus.

3. Wählen Sie im linken Navigationsbereich **"Automatisierte Tests"** aus.

4. Wählen Sie die entsprechende Schaltfläche aus, um automatische Tests für alle Verbesserungsmaßnahmen zu aktivieren, sie für alle Aktionen zu deaktivieren oder nach einzelner Aktion zu aktivieren.

5. Wenn Sie **"Pro Verbesserungsmaßnahme aktivieren"** auswählen, werden in einer Liste alle verfügbaren Verbesserungsmaßnahmen angezeigt.  Aktivieren Sie das Kontrollkästchen neben allen Aktionen, die Automatisch getestet werden sollen.

6. Wählen Sie **"Speichern"** aus, um Ihre Einstellungen zu speichern. Sie erhalten oben auf dem Bildschirm eine Bestätigungsmeldung, dass Ihre Auswahl gespeichert wurde. Wenn Sie einen Fehlerhinweis erhalten, versuchen Sie es erneut.

**Hinweis:** Nur der globale Administrator kann automatische Updates für alle Aktionen aktivieren oder deaktivieren. Der Compliance-Manager-Administrator kann automatische Updates für einzelne Aktionen aktivieren, jedoch nicht für alle Aktionen global.

### <a name="manage-user-history"></a>Verwalten des Benutzerverlaufs

Die Einstellungen zum Verwalten des **Benutzerverlaufs** helfen Ihnen, schnell zu erkennen, welche Benutzer mit Verbesserungsmaßnahmen im Compliance-Manager gearbeitet haben. Die identifizierbaren Benutzerdaten im Zusammenhang mit Verbesserungsmaßnahmen umfassen alle durchgeführten Implementierungs- und Testarbeiten, hochgeladene Dokumente und alle eingegebenen Notizen. Das Verständnis und abrufen dieser Art von Daten kann für die Complianceanforderungen Ihrer Organisation erforderlich sein.

Mit den Einstellungen für den Benutzerverlauf können Sie auch alle Verbesserungsmaßnahmen von einem Benutzer zu einem anderen neu zuweisen.

**So finden Sie die Einstellungen für den Benutzerverlauf:**

1. Wählen Sie Einstellungen in der linken Navigationsleiste von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie auf der Einstellungsseite **Compliance-Manager** aus.

3. Wählen Sie im linken Navigationsbereich **"Benutzerverlauf verwalten"** aus.

Auf der Seite **"Benutzerverlauf verwalten"** wird eine Liste aller Benutzer nach E-Mail-Adresse angezeigt, die einer Verbesserungsmaßnahme zugewiesen sind. Verwenden Sie die **Schaltfläche "Suchen",** um einen bestimmten Benutzer schnell zu finden, indem Sie seine E-Mail-Adresse eingeben.

Rechts neben der E-Mail-Adresse jedes Benutzers bietet das Dropdownmenü **"Auswählen"** Optionen zum Exportieren eines Berichts, zum Neuzuweisen von Verbesserungsmaßnahmen oder zum Löschen des Verlaufs. Details zu den einzelnen Optionen finden Sie unten in den einzelnen Abschnitten.

#### <a name="export-a-report-of-user-history-data"></a>Exportieren eines Berichts mit Benutzerverlaufsdaten

Sie können eine Excel Datei exportieren, die eine Liste der Verbesserungsmaßnahmen enthält, die einem Benutzer derzeit zugewiesen sind.  Der Bericht listet auch alle Nachweisdateien auf, die von diesem Benutzer hochgeladen wurden. Diese Informationen können Ihnen helfen, offene Verbesserungsmaßnahmen neu zuzuweisen.

Der Bericht gibt den Status der Verbesserungsmaßnahme ab dem Erstellungsdatum wieder. Es handelt sich nicht um einen Verlaufsbericht aller vorherigen Änderungen am Status oder der Zuweisung (erfahren Sie, wie Sie [einen Bericht von Ihrer Seite für Verbesserungsmaßnahmen exportieren).](compliance-manager-improvement-actions.md#export-a-report)

**Führen Sie die folgenden Schritte aus, um einen Bericht nach Benutzer zu exportieren:**

1. Wählen Sie **Einstellungen** auf der linken Navigationsleiste von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie auf der Einstellungsseite **Compliance-Manager** aus.

3. Wählen Sie in der Navigation auf der linken Seite **"Benutzerverlauf verwalten"** aus.

4. Suchen Sie den gewünschten Benutzer, indem Sie die E-Mail-Adressen der Liste durchsuchen oder die **Suche** auswählen und die E-Mail-Adresse des Benutzers eingeben.

5. Wählen Sie im Dropdownmenü **"Auswählen"** die Option **"Bericht exportieren"** aus.

6. Nachdem die Excel-Datei Ihres Berichts generiert wurde, können Sie sie öffnen und auf Ihrem lokalen Computer speichern.

#### <a name="reassign-improvement-actions-to-another-user"></a>Erneutes Zuweisen von Verbesserungsmaßnahmen zu einem anderen Benutzer

Sie können Verbesserungsmaßnahmen von einem Benutzer zu einem anderen zuweisen. Wenn Sie eine Aktion neu zuweisen, ändert sich der Dokumentuploadverlauf nicht, aber der Name des Benutzers, der die Dokumentation ursprünglich hochgeladen hat, wird nicht mehr in der Verbesserungsmaßnahme angezeigt.

**Führen Sie die folgenden Schritte aus, um Verbesserungsmaßnahmen einem anderen Benutzer neu zuzuweisen:**

1. Wählen Sie **Einstellungen** auf der linken Navigationsleiste von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie auf der Einstellungsseite **Compliance-Manager** aus.

3. Wählen Sie in der Navigation auf der linken Seite **"Benutzerverlauf verwalten"** aus.

4. Suchen Sie einen Benutzer, indem Sie die E-Mail-Adressen der Liste durchsuchen oder die **Suche** auswählen und die E-Mail-Adresse dieses Benutzers eingeben.

5. Wählen Sie im Dropdownmenü **"Auswählen"** die Option **"Verbesserungsmaßnahmen neu zuweisen"** aus. Der Flyoutbereich **"Verbesserungsmaßnahmen** neu zuweisen" wird angezeigt.

6. Geben Sie im Feld **"Benutzer suchen"** den Namen oder die E-Mail-Adresse des Benutzers ein, dem Sie die *Verbesserungsmaßnahmen* zuweisen möchten.

7. Wenn der Name des gewünschten Benutzers unter **Verbesserungsmaßnahmen angezeigt wird,** wählen Sie den Benutzer aus, und wählen Sie dann **Aktionen zuweisen** aus.

8. Wenn die Neuzuweisung abgeschlossen ist, wird im Flyoutbereich eine Bestätigungsmeldung angezeigt, die bestätigt, dass alle Verbesserungsmaßnahmen des vorherigen Benutzers dem neuen Benutzer neu zugewiesen wurden. Wenn Sie einen Fehler bei der Neuzuweisung erhalten, schließen Sie das Fenster, und versuchen Sie es erneut. Wählen Sie zum Schließen des Flyoutbereichs **"Fertig"** aus.

Der neue Zugewiesene erhält eine E-Mail, dass er einer Verbesserungsmaßnahme zugewiesen wurde. Die E-Mail enthält einen direkten Link zur Detailseite der Verbesserungsmaßnahme.

 > [!NOTE]
> Wenn Sie eine Aktion mit einer ausstehenden Aktualisierung neu zuweisen, wird der direkte Link zu der Aktion in der Neuzuweisungs-E-Mail unterbrochen, wenn das Update nach der erneuten Zuweisung akzeptiert wird. Sie können dies beheben, indem Sie die Aktion dem Benutzer erneut zuweisen, nachdem das Update akzeptiert wurde. Erfahren Sie mehr über [Updates für Verbesserungsmaßnahmen.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

#### <a name="delete-user-history"></a>Löschen des Benutzerverlaufs

Wenn Sie den Verlauf eines Benutzers löschen, werden sie als Besitzer von Verbesserungsmaßnahmen entfernt, und der Name wird aus allen anderen Feldern im Compliance-Manager entfernt. Wenn Sie den Verlauf eines Benutzers löschen, werden die Verbesserungsmaßnahmen, die ihm gehörten, erst dann als Wert **zugewiesen** angezeigt, wenn ein neuer Benutzer zugewiesen wurde. Alle Dokumente, die in die Verbesserungsmaßnahme hochgeladen wurden, zeigen den Benutzer anstelle des Namens des gelöschten Benutzers **an.** Das Löschen des Benutzerverlaufs ist dauerhaft.

Führen Sie die folgenden Schritte aus, um den Verlauf eines Benutzers zu löschen:

1. Wählen Sie **Einstellungen** auf der linken Navigationsleiste von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie auf der Einstellungsseite **Compliance-Manager** aus.

3. Wählen Sie in der Navigation auf der linken Seite **"Benutzerverlauf verwalten"** aus.

4. Suchen Sie einen Benutzer, indem Sie die E-Mail-Adressen der Liste durchsuchen oder die **Suche** auswählen und die E-Mail-Adresse dieses Benutzers eingeben.

5. Wählen Sie im Dropdownmenü **"Select"** die Option **"Verlauf löschen"** aus.

6. Es wird ein Fenster angezeigt, in dem Sie aufgefordert werden, die dauerhafte Löschung des Benutzerverlaufs zu bestätigen. Um mit dem Löschen fortzufahren, wählen Sie **"Verlauf löschen"** aus. Wenn Sie den Verlauf verlassen möchten, ohne den Verlauf zu löschen, wählen Sie **Abbrechen** aus.

7. Sie gelangen zurück zur Seite **"Benutzerverlauf verwalten"** mit einer Bestätigungsmeldung oben, dass der Verlauf für den Benutzer gelöscht wurde.

## <a name="understand-the-compliance-manager-dashboard"></a>Grundlegendes zum Compliance-Manager-Dashboard

Das Compliance-Manager-Dashboard bietet Ihnen einen Überblick über Ihren aktuellen Compliancestatus.

:::image type="content" alt-text="Compliance-Manager – Dashboard." source="../media/compliance-manager-dashboard.png" lightbox="../media/compliance-manager-dashboard.png":::

### <a name="overall-compliance-score"></a>Compliancebewertung gesamt

Ihre Compliancebewertung wird an oberster Stelle hervorgehoben. Es zeigt einen Prozentsatz basierend auf Punkten, die zur Durchführung von Verbesserungsmaßnahmen, die wichtige Datenschutzstandards und -vorschriften erfüllen, erreichbar sind. Punkte aus [Microsoft-Aktionen,](compliance-manager-assessments.md#microsoft-actions-tab)die von Microsoft verwaltet werden, zählen auch für Ihre Compliancebewertung.

Wenn Sie zum ersten Mal zum Compliance-Manager kommen, basiert Ihr anfängliches Ergebnis auf der [Microsoft 365 Datenschutzgrundlinie.](compliance-manager-assessments.md#data-protection-baseline-default-assessment) Diese baseline assessment, which is available to all organizations, is a set of controls that includes common industry regulations and standards. Compliance-Manager überprüft Ihre vorhandenen Microsoft 365 Lösungen und bietet Ihnen eine erste Bewertung basierend auf Ihren aktuellen Datenschutz- und Sicherheitseinstellungen. Wenn Sie Bewertungen hinzufügen, die für Ihre Organisation relevant sind, wird Ihre Bewertung für Sie aussagekräftiger.

**Weitere Informationen:** [Erfahren Sie, wie Ihre Compliancebewertung berechnet wird.](compliance-score-calculation.md)

### <a name="key-improvement-actions"></a>Hauptverbesserungsaktionen

In diesem Abschnitt werden die wichtigsten Verbesserungsmaßnahmen aufgeführt, die Sie derzeit ergreifen können, um die größten positiven Auswirkungen auf Ihre Compliancebewertung insgesamt zu erzielen. Wählen Sie **"Alle Verbesserungsmaßnahmen anzeigen"** aus, um zur Seite "Verbesserungsmaßnahmen" zu gelangen.

### <a name="solutions-that-affect-your-score"></a>Lösungen, die sich auf Ihre Bewertung auswirken

In diesem Abschnitt werden Lösungen mit Verbesserungsmaßnahmen, die sich positiv auf Ihre Bewertung auswirken können, und die Anzahl ausstehender Verbesserungsmaßnahmen in diesen Lösungen beschrieben. Wählen Sie **"Alle Lösungen anzeigen"** aus, um ihre Lösungsseite zu besuchen.

### <a name="compliance-score-breakdown"></a>Aufschlüsselung der Compliancebewertung

In diesem Abschnitt erhalten Sie einen detaillierteren Überblick über Ihre Bewertung auf zwei verschiedene Arten:

- **Kategorien:** zeigt den Prozentsatz Ihrer Gesamtbewertung innerhalb von Datenschutzkategorien an, z. B. "Informationen schützen" oder "Geräte verwalten".
- **Bewertungen:** Zeigt den Prozentsatz Ihres Fortschritts bei der Verwaltung von Bewertungen für bestimmte Compliance- und Datenschutzstandards, Vorschriften oder Gesetze wie DSGVO oder NIST 800-53 an.

### <a name="filtering-your-dashboard-view"></a>Filtern der Dashboardansicht

Sie können Ihre Dashboardansicht filtern, um nur die Elemente im Zusammenhang mit bestimmten Vorschriften und Standards, Lösungen, Aktionstyp, Bewertungsgruppen oder Datenschutzkategorien anzuzeigen. Wenn Sie Ihre Ansicht auf diese Weise filtern, wird auch die Bewertung auf Ihrem Dashboard gefiltert, wobei angezeigt wird, wie viele Punkte Sie basierend auf Ihren Filterkriterien erreicht haben.

So wenden Sie Filter an:

1. Wählen  Sie auf der oberen rechten Seite des Dashboards Filtern aus.
2. Wählen Sie ihre Filterkriterien im Flyoutbereich **Filter** aus, und wählen Sie dann **übernehmen** aus.

Nachdem Sie einen Filter angewendet haben, wird Ihr Ergebnis in Echtzeit angepasst. Der Prozentsatz der Compliancebewertung und die Aufschlüsselungsinformationen sowie die Verbesserungsmaßnahmen und -lösungen beziehen sich jetzt nur auf Daten, die von Ihren Filterkriterien abgedeckt werden. Wenn Sie sich vom Compliance-Manager abmelden, bleibt Ihre gefilterte Ansicht erhalten, wenn Sie sich wieder anmelden.

So entfernen Sie Filter:

- Wählen Sie in der **Überschrift "Angewendete Filter"** oberhalb Ihrer Compliancebewertung das **X** neben dem einzelnen Filter aus, den Sie entfernen möchten. Oder
- Wählen  Sie auf der oberen rechten Seite des Dashboards Filter und dann im Flyoutbereich **Filter** die Option **Filter** löschen aus.

## <a name="improvement-actions-page"></a>Seite "Verbesserungsmaßnahmen"

[Verbesserungsmaßnahmen](compliance-manager-improvement-actions.md) sind Aktionen, die von Ihrer Organisation verwaltet werden. Die Arbeit mit Verbesserungsmaßnahmen trägt dazu bei, Ihre Complianceaktivitäten zu zentralisieren und sich an Datenschutzbestimmungen und -standards zu orientieren. Jede Verbesserungsmaßnahme bietet detaillierte Implementierungsanleitungen und einen Link, um Sie in die entsprechende Lösung zu starten. Verbesserungsmaßnahmen können Benutzern in Ihrer Organisation zugewiesen werden, um Implementierungs- und Testarbeiten durchzuführen. Sie können auch Dokumentationen, Notizen und Statusaktualisierungen im Rahmen der Verbesserungsmaßnahme speichern.

### <a name="view-your-improvement-actions"></a>Anzeigen Ihrer Verbesserungsmaßnahmen

Das Compliance-Manager-Dashboard zeigt Ihre **wichtigsten Verbesserungsmaßnahmen.** Um alle Ihre Verbesserungsmaßnahmen anzuzeigen, wählen Sie die Registerkarte "Verbesserungsmaßnahmen" in Ihrem Dashboard aus, die Sie zur Seite "Verbesserungsmaßnahmen" führt. Sie können auch alle Verbesserungsmaßnahmen unter der Liste der wichtigsten Verbesserungsmaßnahmen auf Ihrem Dashboard anzeigen auswählen, um zu Ihrer Seite für Verbesserungsmaßnahmen zu gelangen.

Auf der Seite "Verbesserungsmaßnahmen" werden alle Verbesserungsmaßnahmen angezeigt, die von Ihrer Organisation verwaltet werden. Von Microsoft verwaltete Aktionen können in jeder Bewertung angezeigt werden (weitere Informationen zu [Microsoft-Aktionen).](compliance-manager-assessments.md#microsoft-actions-tab)

Wenn Sie eine lange Liste von Aktionen auf der Seite "Verbesserungsmaßnahmen" haben, kann es hilfreich sein, Ihre Ansicht zu filtern. Wählen Sie **in** der oberen rechten Ecke der Aktionsliste Filtern aus. Wenn der Flyoutbereich **Filter** angezeigt wird, wählen Sie Ihre Kriterien basierend auf Vorschriften und Standards, Lösung und Gruppe aus. Sie können Ihre Ansicht auch anpassen, indem Sie in der oberen rechten Ecke **"Gruppe"** auswählen. Wählen Sie im Dropdownmenü die Option aus, um nach Gruppe, Lösung, Kategorie, Aktionstyp oder Status anzuzeigen.

In der Standardansicht für diese Seite werden keine Verbesserungsmaßnahmen mit dem Teststatus **"Erfolgreich" angezeigt.** Aktivieren Sie zum Anzeigen von Aktionen, die die Tests bestanden haben, das Kontrollkästchen **"Übergeben"** im Flyoutbereich "Filter". Nur Aktionen mit dem Teststatus **"Anzahl bestanden"** in Richtung Ihres Punktestands. Einige Aktionen zeigen möglicherweise eine **ausstehende Aktualisierungsbezeichnung an.** Erfahren Sie mehr über [Updates für Verbesserungsmaßnahmen.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

Auf der Seite "Verbesserungsmaßnahmen" werden die folgenden Datenpunkte für jede Verbesserungsmaßnahme angezeigt:

- **Erreichte Punkte:** die Anzahl der Punkte, die von der verfügbaren Gesamtmenge erreicht werden, indem die Aktion abgeschlossen wird.
- **Bestimmungen:** die Bestimmungen oder Standards, die sich auf die Aktion beziehen
- **Gruppe:** die Gruppe, der Sie die Aktion zugewiesen haben
- **Lösungen:** die Lösung, in der Sie die Aktion ausführen können
- **Bewertungen:** die Bewertungen, die die Aktion enthalten
- **Kategorien:** die zugehörige Datenschutzkategorie (z. B. Schützen von Informationen, Verwalten von Geräten usw.)
- **Teststatus:**
    - **Keine** – keine Statusaktualisierung aufgezeichnet
    - **Nicht bewertet** – Tests wurden nicht gestartet
    - **Erfolgreich bestanden** – Implementierung erfolgreich getestet
    - **Niedriges Risiko fehlgeschlagen** – Fehler beim Testen, geringes Risiko
    - **Mittleres Risiko fehlgeschlagen** – Fehler beim Testen, mittleres Risiko
    - **Hohes Risiko fehlgeschlagen** – Fehler bei Tests, hohes Risiko
    - **Außerhalb des Gültigkeitsbereichs** – die Aktion ist nicht für die Bewertung vorgesehen und wirkt sich nicht auf Ihre Bewertung aus.
    - **Zu erkennen** – gibt für manuelle Tests an, dass eine Aktion implementiert, aber nicht getestet wurde; gibt für automatisierte Tests an, dass eine Aktion auf das Automatisierungsergebnis wartet
    - **Konnte nicht erkannt werden** – automatisierter Status kann nicht ermittelt werden
    - **Teilweise getestet** – automatisierte Bewertung, die Teilpunkte zurückgibt

**Weitere Informationen:** [Erfahren Sie, wie Sie Verbesserungsmaßnahmen zuweisen und durchführen.](compliance-manager-improvement-actions.md)

## <a name="solutions-page"></a>Seite "Lösungen"

Die Lösungsseite zeigt den Anteil der erzielten und potenziellen Punkte nach Lösung. Wenn Sie ihre verbleibenden Punkte und Verbesserungsmaßnahmen aus dieser Sicht betrachten, können Sie verstehen, welche Lösungen sofortiger beachtet werden müssen.

Suchen Sie die Lösungsseite, indem Sie die Registerkarte **"Lösungen"** im Compliance-Manager-Dashboard auswählen. Sie können auch alle Lösungen unter **"Lösungen** **anzeigen", die sich auf Ihre Bewertung auswirken,** im oberen rechten Bereich Ihres Dashboards auswählen.

### <a name="filtering-your-solutions-view"></a>Filtern der Lösungsansicht

So filtern Sie die Ansicht von Lösungen:

1. Wählen  Sie in der oberen linken Ecke der Bewertungsliste Filtern aus.
2. Platzieren Sie im Flyoutbereich **"Filter"** neben den gewünschten Kriterien eine Überprüfung (Standards und Vorschriften, Lösung, Aktionstyp, Compliance-Manager-Gruppe, Kategorie).
3. Wählen Sie die Schaltfläche **"Übernehmen"** aus. Der Filterbereich wird geschlossen, und Die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt oder Verordnung angezeigt werden, indem Sie den Typ der Gruppierung im Dropdownmenü **"Gruppe"** über Ihrer Bewertungsliste auswählen.

### <a name="taking-action-from-the-solution-page"></a>Ergreifen von Maßnahmen auf der Lösungsseite

Auf der Lösungsseite werden die Lösungen Ihrer Organisation angezeigt, die mit Verbesserungsmaßnahmen verbunden sind. In der Tabelle sind der Beitrag jeder Lösung zu Ihrer Gesamtbewertung, die erzielten und möglichen Punkte innerhalb dieser Lösung sowie die verbleibende Anzahl von Verbesserungsmaßnahmen aufgeführt, die in dieser Lösung gruppiert sind und ihre Bewertung erhöhen können.

Auf diesem Bildschirm gibt es zwei Möglichkeiten, maßnahmen zu ergreifen:

1. Wählen Sie in der Zeile der gewünschten Lösung unter der Spalte **"Verbleibenden Aktionen"** die Nummer des Hyperlinks aus. Sie sehen eine gefilterte Ansicht des Bildschirms "Verbesserungsmaßnahmen" mit nicht getesteten Verbesserungsmaßnahmen für diese Lösung.

2. Wählen Sie in der Zeile der gewünschten Lösung unter der Spalte **"Projektmappe öffnen"** die Option **"Öffnen"** aus. Sie sehen die Lösung oder den Speicherort im Microsoft 365 und Office 365 Security and Compliance Center, in denen Sie die empfohlenen Maßnahmen ergreifen können.

## <a name="assessments-page"></a>Bewertungsseite

Auf der Bewertungsseite sind alle [Bewertungen aufgeführt,](compliance-manager-assessments.md) die Sie für Ihre Organisation eingerichtet haben. Der Nenner der Compliancebewertung wird von allen Erfassten Bewertungen bestimmt. Wenn Sie weitere Bewertungen hinzufügen, werden auf der Seite "Verbesserungsmaßnahmen" weitere Verbesserungsmaßnahmen aufgeführt, und ihr Nenner für die Compliancebewertung nimmt zu.

Der **aktivierte Vorlagenzähler** am oberen Rand der Seite zeigt die Anzahl der aktiven Bewertungsvorlagen an, die derzeit verwendet werden, von der Gesamtzahl der Vorlagen, die für Ihre Organisation zur Verfügung stehen. Weitere Informationen finden Sie unter [Verfügbarkeit und Lizenzierung](compliance-manager-templates.md#template-availability-and-licensing) von Vorlagen.

Auf der Bewertungsseite werden die wichtigsten Informationen zu den einzelnen Bewertungen zusammengefasst:

- **Bewertung:** Name der Bewertung
- **Status**:
    - **Vollständig** – alle Steuerelemente haben den Status "übergeben", oder mindestens ein Steuerelement wird übergeben, und die restlichen Steuerelemente liegen außerhalb des Gültigkeitsbereichs.
    - **Unvollständig** – mindestens ein Steuerelement hat den Status "fehlgeschlagen"
    - **Keine -** alle Steuerelemente wurden nicht getestet
    - **In Bearbeitung** – Verbesserungsmaßnahmen haben einen anderen Status, einschließlich "in Bearbeitung", "Teilgutschrift" oder "nicht erkannt"
- **Bewertungsfortschritt:** Der Prozentsatz der abgeschlossenen Arbeit, gemessen an der Anzahl der erfolgreich getesteten Steuerelemente.
- **Ihre Verbesserungsmaßnahmen:** die Anzahl abgeschlossener Aktionen, um die Implementierung Ihrer Steuerelemente zu erfüllen
- **Microsoft-Aktionen:** Die Anzahl abgeschlossener Aktionen, um die Implementierung von Microsoft-Steuerelementen zu erfüllen
- **Gruppe**: Name der Gruppe, zu der die Bewertung gehört
- **Produkt:** zugeordneter Microsoft 365-Dienst
- **Verordnung:** der regulatorische Standard, die Richtlinie oder das Recht, das für die Bewertung gilt

### <a name="filtering-your-assessments-view"></a>Filtern der Bewertungsansicht

So filtern Sie die Ansicht der Bewertungen:

1. Wählen  Sie in der oberen linken Ecke der Bewertungsliste Filtern aus.
2. Überprüfen Sie im Flyoutbereich **"Filter"** die gewünschten Kriterien.
3. Wählen Sie die Schaltfläche **"Übernehmen"** aus. Der Filterbereich wird geschlossen, und Die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt oder Verordnung angezeigt werden, indem Sie den Typ der Gruppierung im Dropdownmenü **"Gruppe"** über Ihrer Bewertungsliste auswählen.

### <a name="default-assessment"></a>Standardbewertung

Standardmäßig wird die Bewertung der [Datenschutzgrundwerte](compliance-manager-assessments.md#data-protection-baseline-default-assessment) auf der Bewertungsseite angezeigt. Compliance-Manager bietet auch mehrere vordefinierte [Vorlagen](compliance-manager-templates-list.md) für die Erstellung von Bewertungen.

## <a name="assessment-templates-page"></a>Seite „Bewertungsvorlagen“

Eine Vorlage ist ein Framework zum Erstellen einer Bewertung im Compliance-Manager. Auf der Seite „Bewertungsvorlagen“ wird eine Liste mit Vorlagen und wichtigen Details angezeigt. Die Liste enthält Vorlagen, die vom Compliance-Manager bereitgestellt werden, sowie alle Vorlagen, die Ihre Organisation geändert oder erstellt hat. Sie können Filter anwenden, um eine Vorlage basierend auf Zertifizierung, Produktbereich, Land, Branche und der Person zu finden, die sie erstellt hat.

Der **aktivierte Vorlagenzähler** am oberen Rand der Seite zeigt die Anzahl der aktiven Bewertungsvorlagen an, die derzeit verwendet werden, von der Gesamtzahl der Vorlagen, die für Ihre Organisation zur Verfügung stehen. Weitere Informationen finden Sie unter [Verfügbarkeit und Lizenzierung](compliance-manager-templates.md#template-availability-and-licensing) von Vorlagen.

Wählen Sie eine Vorlage aus der Zeile aus, um die Detailseite aufzurufen, die eine Beschreibung der Vorlage sowie weitere Informationen zu Zertifizierungs-, Bereichs- und Steuerelementdetails enthält. Auf dieser Seite können Sie die entsprechenden Schaltflächen auswählen, um eine Bewertung zu erstellen, die Vorlagendaten in Excel zu exportieren oder die Vorlage zu ändern.

**Weitere Informationen:** [Lesen Sie, wie Sie mit Bewertungsvorlagen arbeiten.](compliance-manager-templates.md)

## <a name="next-step"></a>Nächster Schritt
Passen Sie Compliance-Manager durch Einrichten von [Bewertungen](compliance-manager-assessments.md)an.
