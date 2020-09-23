---
title: Erste Schritte mit dem Microsoft Compliance-Manager
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
description: Legen Sie die Benutzerberechtigungen und-Rollen von Microsoft Compliance Manager fest, und konfigurieren Sie automatisierte Tests von Aktionen. Verwalten Sie den Benutzerverlauf, und Filtern Sie die Dashboardansicht.
ms.openlocfilehash: ead4fe60a11bcf78a318601c1de6d72f2490c567
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204437"
---
# <a name="get-started-with-compliance-manager"></a>Erste Schritte mit Compliance-Manager

**In diesem Artikel:** Dieser Artikel unterstützt Sie beim Einrichten von Compliance-Manager. Erfahren Sie, wie Sie auf Compliance-Manager **zugreifen** , **Rollen und Berechtigungen festlegen**und **Automatische Tests von Verbesserungs Aktionen**konfigurieren. Navigieren Sie über das **Compliance-Manager-Dashboard** , und verstehen Sie die Hauptseiten: die Seite Verbesserungs Aktionen, die Seite Lösungen, die Seite "Bewertungen" und die Seite "Bewertungs Vorlagen".

## <a name="who-can-access-compliance-manager"></a>Wer auf den Compliance-Manager zugreifen kann

Compliance-Manager steht Organisationen mit Office 365-und Microsoft 365-Lizenzen zur Verfügung. Die Verfügbarkeit und die Verwaltungsfunktionen für die Bewertung hängen von Ihrem Lizenzvertrag ab.  [Anzeigen von Details zur Dienstbeschreibung](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="before-you-begin"></a>Bevor Sie beginnen

Der globale Administrator Microsoft 365 für Ihre Organisation ist wahrscheinlich der erste Benutzer, der auf den Compliance-Manager zugreift. Wenn Sie den Compliance-Manager zum ersten Mal besuchen, empfehlen wir die globale Administratoranmeldung und legen Benutzerberechtigungen fest, wie unten beschrieben.

## <a name="sign-in"></a>Anmelden

1. Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) , und **melden** Sie sich mit ihrem globalen Microsoft 365-Administratorkonto an.
2. Wählen Sie im linken Navigationsbereich **Compliance-Manager** aus. Sie gelangen zu Ihrem [Compliance-Manager-Dashboard](#understand-the-compliance-manger-dashboard).

Der direkte Link zum Zugriff auf Compliance-Manager ist [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Festlegen von Benutzerberechtigungen und Zuweisen von Rollen

Compliance-Manager verwendet ein RBAC-Berechtigungsmodell (Role-Based Access Control, rollenbasierte Zugriffssteuerung). Nur Benutzer, denen eine Rolle zugewiesen ist, können auf den Compliance-Manager zugreifen, und die von den einzelnen Benutzern zugelassenen Aktionen sind nach [Rollentyp](#role-types)eingeschränkt.

### <a name="where-to-set-permissions"></a>Festlegen von Berechtigungen

Die Person, die die globale Administratorrolle für Ihre Organisation innehat, kann Benutzerberechtigungen im Microsoft 365 Compliance Center sowie in Azure Active Directory (Azure AD) festlegen.

Führen Sie die folgenden Schritte aus, um Berechtigungen im Microsoft 365 Compliance Center festzulegen und Rollen zuzuweisen:

1. Wählen Sie **Berechtigungen** im linken Navigationsbereich von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie im oberen Bereich den Link **zum Anzeigen und Verwalten von Rollen in Office 365 aus, und klicken Sie hier.** Eine neue Registerkarte wird für das Office 365 Security & Compliance Center geöffnet (Informationen dazu,[warum Sie umgeleitet](microsoft-365-compliance-center.md#frequently-asked-questions)werden).

3. Suchen Sie nach der Rollengruppe, der Sie einen oder mehrere Benutzer hinzufügen möchten, und aktivieren Sie das Kontrollkästchen links neben dem Gruppennamen. (Weitere Informationen finden Sie unter der [Liste der Rollen und verwandten Funktionen](#role-types). Die Rollengruppen Namen imitieren den Rollennamen.)

4. Wählen Sie im Flyout-Bereich für diese Gruppe unter der Kopfzeile **Mitglieder** die Option **Bearbeiten** aus.

5. Wählen Sie **Mitglieder auswählen**aus. Ein weiteres Flyout-Fenster wird angezeigt.

6. Wählen Sie **+ Hinzufügen** aus, um einen oder mehrere Benutzer auszuwählen, die der Gruppe hinzugefügt werden sollen.

7. Aktivieren Sie das Kontrollkästchen neben den Namen, die Sie hinzufügen möchten, und klicken Sie dann unten auf die Schaltfläche **Hinzufügen** .

8. Wenn Sie mit dem Zuweisen von Benutzern fertig sind, wählen Sie **Fertig**aus, und klicken Sie dann auf **Speichern**und dann auf **Schließen**.

##### <a name="more-about-the-office-365-secruity--compliance-center"></a>Weitere Informationen zum Office 365 secruity & Compliance Center

Erfahren Sie mehr über [Berechtigungen im Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

Wenn Sie keinen Zugriff auf das Office 365 Security and Compliance Center haben oder auf die klassische Version von Compliance Manager im Microsoft Service Trust Portal zugreifen müssen, bietet die Administratoreinstellung im Dienst Vertrauensstellungs Portal eine weitere Möglichkeit zum Zuweisen von Rollen ([Anweisungen anzeigen](/meet-data-protection-and-regulatory-reqs-using-microsoft-cloud?view=o365-worldwide.md#assigning-compliance-manager-roles-to-users)). Beachten Sie, dass diese Rollen in ihrer Funktionalität geringer sind.

##### <a name="more-about-azure-ad"></a>Weitere Informationen zu Azure AD

Informationen zum Zuweisen von Rollen und Festlegen von Berechtigungen in Azure AD finden Sie unter [Zuweisen von Administrator-und nicht-Administratorrollen für Benutzer mit Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

Benutzer mit Azure AD Identitäten, die nicht über Office 365-oder Microsoft 365-Abonnements verfügen, können nicht auf den Compliance-Manager im Microsoft 365 Compliance Center zugreifen. Wenden Sie sich an [cmresearch@Microsoft.com](mailto:cmresearch@microsoft.com), um Unterstützung beim Zugriff auf den Compliance-Manager zu erhalten.

### <a name="role-types"></a>Rollentypen

In der folgenden Tabelle sind die Funktionen aufgeführt, die für die einzelnen Rollen im Compliance-Manager zulässig sind. In der Tabelle wird auch gezeigt, wie die einzelnen [Azure AD Rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) den Compliance-Manager Rollen zugeordnet werden. Benutzer benötigen mindestens die Compliance Manager-Leserrolle oder Azure AD globale Leserrolle, um auf den Compliance-Manager zuzugreifen.


| Benutzer kann Folgendes: | Compliance-Manager-Rolle | Azure AD Rolle | 
| :------------- | :-------------: | :------------: |
| **Lesen, aber nicht bearbeiten von Daten**| Compliance Manager Reader  | Azure AD globaler Leser, Sicherheits Leser | 
| **Bearbeiten von Daten**| Compliance-Manager-Beitrag | Complianceadministrator | 
| **Bearbeiten von Testergebnissen**| Compliance-Manager-Bewertung | Complianceadministrator | 
| **Verwalten von Bewertungen und Vorlagen-und Mandantendaten**| Compliance-Manager-Verwaltung | Compliance-Administrator, Compliance-Datenadministrator, Sicherheitsadministrator  | 
| **Zuweisen von Benutzern**| Globaler Administrator | Globaler Administrator | 

## <a name="settings-for-automated-testing-and-user-history"></a>Einstellungen für automatisierte Tests und Benutzerverlauf

Die Kompatibilitäts-Manager-Einstellungen im Microsoft 365 Compliance Center ermöglichen Ihnen das Aktivieren und Deaktivieren automatischer Tests von Verbesserungs Aktionen. Mit den Einstellungen können Sie auch die Daten von Benutzern verwalten, die Verbesserungs Aktionen zugeordnet sind, einschließlich der Möglichkeit, Verbesserungs Aktionen einem anderen Benutzer zuzuweisen.  Nur Personen mit globaler Administrator-oder Compliance-Manager-Administratorrolle können auf die Compliance-Manager-Einstellungen zugreifen.

### <a name="set-up-automated-testing"></a>Einrichten von automatisierten Tests

Einige Verbesserungs Aktionen im Compliance-Manager werden auch von [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)überwacht. Sie können automatisierte Tests für gemeinsam überwachte Aktionen einrichten, was bedeutet, dass beim Testen und Aktualisieren einer Aktion in "Secure Score" Diese Ergebnisse mit den gleichen Aktionen im Compliance-Manager synchronisiert werden und auf Ihre Konformitätsbewertung zählen.

Automatische Tests sind standardmäßig für Unternehmen mit Compliance-Manager neu aktiviert. Bei der ersten Bereitstellung von Microsoft 365 oder Office 365 dauert es ungefähr sieben Tage, bis Secure Score die Daten vollständig erfasst und Sie in ihrer Konformitätsbewertung berücksichtigt.  Wenn der automatisierte Test aktiviert ist, wird das Test Datum der Aktion nicht aktualisiert, aber der Teststatus wird aktualisiert. Wenn neue Bewertungen erstellt werden, enthalten Partituren automatisch Microsoft-Steuerpunkte und die Integration sicherer Bewertungen.

Der globale Administrator für Ihre Organisation kann die Einstellungen für automatisierte Tests zu einem beliebigen Zeitpunkt ändern. Sie können automatisierte Tests für allgemeine Verbesserungs Aktionen deaktivieren oder für einzelne Aktionen aktivieren. Befolgen Sie die Anweisungen unten, um die Einstellungen für automatisierte Tests zu ändern.

#### <a name="to-manage-your-automated-testing-settings"></a>So verwalten Sie die Einstellungen für automatisierte Tests:

1. Wählen Sie **Einstellungen** im linken Navigationsbereich von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie auf der Seite Einstellungen die Option **Compliance-Manager**aus.

3. Wählen Sie im linken Navigationsbereich die Option **automatisierte Tests** aus.

4. Wählen Sie die entsprechende Schaltfläche aus, um die automatischen Tests für alle Verbesserungs Aktionen zu aktivieren, für alle Aktionen auszuschalten oder durch eine einzelne Aktion einzuschalten.

5. Wenn Sie **pro Verbesserungs Aktion aktivieren**auswählen, werden in einer Liste alle verfügbaren Verbesserungs Aktionen angezeigt, aus denen Sie auswählen können.  Aktivieren Sie das Kontrollkästchen neben einer Aktion, die automatisch getestet werden soll.

6. Wählen Sie **Speichern** aus, um Ihre Einstellungen zu speichern. Am oberen Rand des Bildschirms wird eine Bestätigungsmeldung angezeigt, dass Ihre Auswahl gespeichert wurde. Wenn Sie eine Fehlermeldung erhalten, versuchen Sie es erneut.

**Hinweis:** Nur der globale Administrator kann automatische Updates für alle Aktionen aktivieren oder deaktivieren. Der Compliance-Manager-Administrator kann automatische Updates für einzelne Aktionen aktivieren, jedoch nicht für alle Aktionen Global.

### <a name="manage-user-history"></a>Verwalten des Benutzer Verlaufs

Mithilfe der Einstellungen zum **Verwalten von Benutzer Verlaufs** Informationen können Sie schnell erkennen, welche Benutzer mit Verbesserungs Aktionen in Compliance Manger gearbeitet haben. Zu den identifizierbaren Benutzerdaten im Zusammenhang mit den Verbesserungs Aktionen gehören alle ausgeführten Implementierungs-und Testaufgaben, hochgeladenen Dokumente und alle eingegebenen Notizen. Das Verständnis und das Abrufen dieser Art von Daten sind möglicherweise für die eigenen Compliance-Anforderungen Ihrer Organisation erforderlich.

Mithilfe der Einstellungen für den Benutzerverlauf können Sie auch alle Verbesserungs Aktionen von einem Benutzer zu einem anderen zuweisen.

**So finden Sie die Einstellungen für den Benutzerverlauf:**

1. Wählen Sie Einstellungen im linken Navigationsbereich von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie auf der Seite Einstellungen die Option **Compliance-Manager**aus.

3. Wählen Sie im linken Navigationsbereich die Option **Benutzerverlauf verwalten** aus.

Auf der Seite **Benutzerverlauf verwalten** wird eine Liste aller Benutzer anhand einer e-Mail-Adresse angezeigt, die einer Verbesserungs Aktion zugewiesen ist. Verwenden Sie die Schaltfläche **Suchen** , um schnell einen bestimmten Benutzer zu finden, indem Sie Ihre e-Mail-Adresse eingeben.

Rechts neben der e-Mail-Adresse jedes Benutzers stehen im Dropdownmenü **auswählen** Optionen zum Exportieren eines Berichts, zum erneuten Zuweisen von Verbesserungs Aktionen oder zum Löschen des Verlaufs zur Verfügung. Ausführliche Informationen zu den einzelnen Optionen finden Sie in den einzelnen Abschnitten.

#### <a name="export-a-report-of-user-history-data"></a>Exportieren eines Berichts über Benutzer Verlaufsdaten

Sie können eine Excel-Datei exportieren, die eine Liste der derzeit einem Benutzer zugewiesenen Verbesserungs Aktionen enthält.  Der Bericht listet auch alle Beweisdateien auf, die von diesem Benutzer hochgeladen wurden. Diese Informationen können Ihnen beim erneuten Zuweisen offener Verbesserungs Aktionen helfen.

Der Bericht gibt den Status der Verbesserungs Aktion zum Erstellungsdatum an. Es handelt sich nicht um einen Verlaufsbericht aller vorherigen Änderungen an seinem Status oder seiner Zuweisung (Informationen zum [Exportieren eines Berichts auf der Seite mit den Verbesserungs Aktionen](compliance-manager-improvement-actions.md#export-a-report)).

**Führen Sie die folgenden Schritte aus, um einen Bericht nach Benutzer zu exportieren:**

1. Wählen Sie **Einstellungen** im linken Navigationsbereich von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie auf der Seite Einstellungen die Option **Compliance-Manager**aus.

3. Wählen Sie in der Navigationsleiste links die Option **Benutzerverlauf verwalten** aus.

4. Suchen Sie den gewünschten Benutzer, indem Sie die Listen-e-Mail-Adressen durchsuchen oder die e-Mail-Adresse des **Benutzers auswählen.**

5. Wählen Sie im Dropdownmenü **auswählen** die Option **Bericht exportieren**aus.

6. Nachdem die Excel-Datei Ihres Berichts erstellt wurde, können Sie Sie öffnen und auf Ihrem lokalen Computer speichern.

#### <a name="reassign-improvement-actions-to-another-user"></a>Erneutes Zuweisen von Verbesserungs Aktionen zu einem anderen Benutzer

Sie können Verbesserungs Aktionen von einem Benutzer zu einem anderen zuweisen. Wenn Sie eine Aktion neu zuweisen, ändert sich der Dokumentupload-Verlauf nicht, aber der Name des Benutzers, der die Dokumentation ursprünglich hochgeladen hat, wird nicht mehr in der Verbesserungs Aktion angezeigt.

**Führen Sie die folgenden Schritte aus, um einem anderen Benutzer Verbesserungs Aktionen zuzuweisen:**

1. Wählen Sie **Einstellungen** im linken Navigationsbereich von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie auf der Seite Einstellungen die Option **Compliance-Manager**aus.

3. Wählen Sie in der Navigationsleiste links die Option **Benutzerverlauf verwalten** aus.

4. Suchen Sie nach einem Benutzer, indem Sie die Listen-e-Mail-Adressen **Durchsuchen oder** die e-Mail-Adresse des Benutzers eingeben.

5. Wählen Sie im Dropdownmenü **auswählen** die Option **Verbesserungs Aktionen zuordnen**aus. Der Flyout-Bereich **Verbesserungs Aktionen** werden erneut zuweisen angezeigt.

6. Geben Sie im Feld **Benutzer suchen** den Namen oder die e-Mail-Adresse des Benutzers *ein, dem*Sie die Verbesserungs Aktionen zuweisen möchten.

7. Wenn der Name des beabsichtigten Benutzers angezeigt wird, unter **Verbesserungs Aktionen werden zugewiesen**, wählen Sie den Benutzer aus, und wählen Sie dann **Aktionen zuweisen**aus.

8. Wenn die Neuzuweisung abgeschlossen ist, wird im Flyout-Bereich eine Bestätigungsmeldung angezeigt, in der bestätigt wird, dass alle Verbesserungs Aktionen des vorherigen Benutzers dem neuen Benutzer neu zugewiesen wurden. Wenn Sie eine Fehlermeldung zum erneuten Zuweisen erhalten, schließen Sie das Fenster, und versuchen Sie es erneut. Klicken Sie auf **Fertig**, um den Flyout-Bereich zu schließen.

Der neue Empfänger erhält eine e-Mail, der eine Verbesserungs Aktion zugewiesen wurde. Die e-Mail enthält einen direkten Link auf der Detailseite der Verbesserungs Aktion.
 
 > [!NOTE]
> Wenn Sie eine Aktion mit einer ausstehenden Aktualisierung erneut zuweisen, wird die direkte Verknüpfung mit der Aktion in der Neuzuweisungs-e-Mail unterbrochen, wenn die Aktualisierung nach der Neuzuweisung akzeptiert wird. Sie können dieses Problem beheben, indem Sie die Aktion dem Benutzer neu zuweisen, nachdem die Aktualisierung angenommen wurde. Erfahren Sie mehr über [Aktualisierungen von Verbesserungs Aktionen](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

#### <a name="delete-user-history"></a>Löschen des Benutzer Verlaufs

Wenn Sie den Verlauf eines Benutzers löschen, werden diese als Besitzer von Verbesserungs Aktionen entfernt, und Ihr Name wird aus allen anderen Feldern in Compliance Manger entfernt. Wenn Sie den Verlauf eines Benutzers löschen, werden die im Besitz befindlichen Verbesserungs Aktionen keinen **zugewiesenen** Wert anzeigen, bis ein neuer Benutzer zugewiesen wird. Alle Dokumente, die in die Verbesserungs Aktion hochgeladen wurden, zeigen Benutzer anstelle des Namens des gelöschten Benutzers **entfernt** an. Das Löschen des Benutzer Verlaufs ist dauerhaft.

Führen Sie die folgenden Schritte aus, um den Verlauf eines Benutzers zu löschen:

1. Wählen Sie **Einstellungen** im linken Navigationsbereich von einer beliebigen Stelle im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)aus.

2. Wählen Sie auf der Seite Einstellungen die Option **Compliance-Manager**aus.

3. Wählen Sie in der Navigationsleiste links die Option **Benutzerverlauf verwalten** aus.

4. Suchen Sie nach einem Benutzer, indem Sie die Listen-e-Mail-Adressen **Durchsuchen oder** die e-Mail-Adresse des Benutzers eingeben.

5. Wählen Sie im Dropdownmenü **auswählen** die Option **Verlauf löschen**aus.

6. Es wird ein Fenster angezeigt, in dem Sie aufgefordert werden, die dauerhafte Löschung des Benutzer Verlaufs zu bestätigen. Um den Löschvorgang fortzusetzen, wählen Sie **Verlauf löschen**aus. Wenn Sie das Protokoll verlassen möchten, ohne den Verlauf zu löschen, wählen Sie **Abbrechen**aus.

7. Sie gelangen wieder auf der Seite **Benutzerverlauf verwalten** mit einer Bestätigungsmeldung am oberen Rand, dass der Verlauf für den Benutzer gelöscht wurde.

## <a name="understand-the-compliance-manger-dashboard"></a>Grundlegendes zum Compliance-Manager-Dashboard

Das Compliance-Manager-Dashboard bietet Ihnen einen Überblick über Ihre aktuelle Compliance-Position.

![Compliance-Manager – Dashboard](../media/compliance-manager-dashboard.png "Compliance-Manager-Dashboard")

### <a name="overall-compliance-score"></a>Gesamtergebnis der Konformität

Ihr Konformitäts Bewertungspunkt wird oben im Vordergrund vorgestellt. Es zeigt einen Prozentsatz auf der Grundlage von Punkten, die für die Durchführung von Verbesserungs Aktionen zur Behandlung wichtiger Datenschutzstandards und-Vorschriften erreichbar sind. Punkte von [Microsoft-Aktionen](compliance-manager-assessments.md#microsoft-actions-tab), die mein Microsoft verwaltet haben, zählen ebenfalls zu Ihrem Konformitäts Bewertungsergebnis.

Wenn Sie den Compliance-Manager zum ersten Mal besuchen, basiert Ihr anfängliches Ergebnis auf der [Microsoft 365-Datenschutz Basis](compliance-manager-assessments.md#data-protection-baseline-default-assessment). Diese Basisbewertung, die allen Organisationen zur Verfügung steht, umfasst eine Reihe von Steuerelementen, die allgemeine Branchenvorschriften und-Standards umfassen. Compliance-Manager scannt Ihre vorhandenen Microsoft 365-Lösungen und gibt Ihnen eine erste Bewertung basierend auf Ihren aktuellen Datenschutz-und Sicherheitseinstellungen. Wenn Sie für Ihre Organisation relevante Bewertungen hinzufügen, wird Ihre Punktzahl für Sie aussagekräftiger.

**Weitere Informationen:** Grund [Legendes zur Berechnung der Konformitätsbewertung](compliance-score-calculation.md).

### <a name="key-improvement-actions"></a>Wichtige Verbesserungs Aktionen

In diesem Abschnitt werden die wichtigsten Verbesserungs Aktionen aufgelistet, die Sie im Moment durchführen können, um den größten positiven Einfluss auf Ihre gesamte Konformitätsbewertung zu nehmen. Wählen Sie **alle Verbesserungs Aktionen anzeigen** aus, um zur Seite Verbesserungs Aktionen zu wechseln.

### <a name="solutions-that-affect-your-score"></a>Lösungen, die Ihre Punktzahl beeinflussen

In diesem Abschnitt werden Lösungen aufgeführt, die Verbesserungs Aktionen enthalten, die sich positiv auf Ihre Bewertung auswirken können, sowie die Anzahl der ausstehenden Verbesserungs Aktionen in diesen Lösungen. Wählen Sie **alle Lösungen anzeigen** aus, um die Seite Lösungen zu besuchen.

### <a name="compliance-score-breakdown"></a>Aufschlüsselung der Konformitätsbewertung

In diesem Abschnitt erhalten Sie zwei verschiedene Möglichkeiten, um eine detailliertere Darstellung ihrer Ergebnisse zu erzielen:

- **Kategorien**: zeigt den Prozentsatz der Gesamtpunktzahl in Datenschutzkategorien an, beispielsweise "Informationen schützen" oder "Geräte verwalten".
- **Assessments**: zeigt den Prozentsatz Ihrer Fortschritte bei der Verwaltung von Bewertungen für bestimmte Compliance-und Datenschutzstandards, Verordnungen oder Gesetze wie dsgvo oder NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtern der Dashboardansicht

Sie können die Dashboardansicht filtern, um nur die Elemente anzuzeigen, die sich auf bestimmte Vorschriften und Standards, Lösungen, Aktionstypen, Bewertungsgruppen oder Datenschutzkategorien beziehen. Durch das Filtern der Ansicht auf diese Weise wird auch die Bewertung in Ihrem Dashboard gefiltert, und es wird angezeigt, wie viele Punkte Sie je nach den Filterkriterien aus insgesamt möglichen Punkten erzielt haben.

So wenden Sie Filter an:

1. Wählen Sie in der oberen rechten Ecke des Dashboards den **Filter** aus.
2. Wählen Sie Ihre Filterkriterien im Flyout- **Filter** Bereich aus, und wählen Sie dann **Apply**aus.

Nachdem Sie einen Filter angewendet haben, wird das Ergebnis in Echtzeit angepasst. Der Prozentsatz der Konformitätsbewertung und die Aufschlüsselung sowie die Verbesserungs Aktionen und-Lösungen beziehen sich jetzt nur auf Daten, die von Ihren Filterkriterien abgedeckt werden. Wenn Sie sich beim Compliance-Manager abmelden, bleibt die gefilterte Ansicht erhalten, wenn Sie sich wieder anmelden.

So entfernen Sie Filter:

- Wählen Sie auf der Überschrift " **angewendete Filter** " oberhalb der Konformitätsbewertung das **X** neben dem einzelnen Filter aus, den Sie entfernen möchten. oder
- Wählen Sie in der oberen rechten Ecke des Dashboards **Filter** aus, und wählen Sie dann **im Flyout-Bereich Filter die Option** Filter **Löschen**aus.

## <a name="improvement-actions-page"></a>Seite "Verbesserungs Aktionen"

[Verbesserungs Aktionen](compliance-manager-improvement-actions.md) sind Aktionen, die von Ihrer Organisation verwaltet werden. Die Arbeit mit Verbesserungs Aktionen hilft bei der Zentralisierung ihrer Compliance-Aktivitäten und der Anpassung an die Datenschutzbestimmungen und-Standards. Jede Verbesserungs Aktion enthält detaillierte Anleitungen zur Implementierung und einen Link, mit dem Sie die entsprechende Lösung starten können. Verbesserungs Aktionen können Benutzern in Ihrer Organisation zugewiesen werden, um Implementierungs-und Testaufgaben auszuführen. Sie können auch Dokumentation, Notizen und Datensatzstatus Aktualisierungen in der Verbesserungs Aktion speichern.

### <a name="view-your-improvement-actions"></a>Anzeigen von Verbesserungs Aktionen

Das Compliance-Manager-Dashboard zeigt Ihre **wichtigsten Verbesserungs Aktionen.** Um alle Ihre Verbesserungs Aktionen anzuzeigen, wählen Sie die Registerkarte Verbesserungs Aktionen in Ihrem Dashboard aus, die Sie zur Seite Verbesserungs Aktionen bringt. Sie können auch alle Verbesserungs Aktionen unterhalb der Liste der wichtigsten Verbesserungs Aktionen in Ihrem Dashboard anzeigen auswählen, um zur Seite mit den Verbesserungs Aktionen zu gelangen.

Auf der Seite Verbesserungs Aktionen werden alle Verbesserungs Aktionen angezeigt, die von Ihrer Organisation verwaltet werden. Aktionen, die von Microsoft verwaltet werden, können innerhalb jeder Bewertung angezeigt werden (Weitere Informationen zu [Microsoft-Aktionen](compliance-manager-assessments.md#microsoft-actions-tab)).

Wenn auf der Seite mit den Verbesserungs Aktionen eine lange Liste von Aktionen vorliegt, kann es hilfreich sein, die Ansicht zu filtern. Wählen Sie in der Liste Aktionen in der rechten oberen Ecke den **Filter** aus. Wenn der **Filter** Flyout-Bereich angezeigt wird, wählen Sie Ihre Kriterien basierend auf Regeln und Standards, Lösung und Gruppe aus. Sie können die Ansicht auch anpassen, indem Sie in der oberen rechten Ecke die Option **Gruppe** auswählen. Wählen Sie im Dropdownmenü die Option aus, um nach Gruppe, Lösung, Kategorie, Aktionstyp oder Status anzuzeigen.

In der Standardansicht für diese Seite werden keine Verbesserungs Aktionen mit dem Teststatus " **übergeben**" angezeigt. Zum Anzeigen von Aktionen, die Tests bestanden haben, aktivieren Sie das Kontrollkästchen **übergebenes** Feld im Dropdownbereich Filter. Nur Aktionen mit einem Teststatus der **übergebenen** Zählung zu Ihrer Partitur. Einige Aktionen zeigen möglicherweise eine **ausstehende Update Bezeichnung an.** Erfahren Sie mehr über [Aktualisierungen von Verbesserungs Aktionen](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

Auf der Seite Verbesserungs Aktionen werden die folgenden Datenpunkte für jede Verbesserungs Aktion angezeigt:

- **Erreichte Punkte**: die Anzahl der Punkte, die aus der Gesamtpunktzahl erzielt wurden, indem die Aktion abgeschlossen wurde.
- **Bestimmungen**: die Vorschriften oder Standards im Zusammenhang mit der Aktion
- **Gruppe**: die Gruppe, der Sie die Aktion zugewiesen haben
- **Lösungen**: die Lösung, mit der Sie zur Ausführung der Aktion wechseln können
- **Assessments**: die Bewertungen, die die Aktion enthalten
- **Kategorien**: die zugehörige Datenschutzkategorie (beispielsweise zum Schutz von Informationen, Verwalten von Geräten usw.)
- **Test Status**:
    - **None** – keine Statusaktualisierung aufgezeichnet
    - **Nicht bewertet** – Test wurde nicht gestartet
    - **Übergebene** Implementierung erfolgreich getestet
    - **Fehlgeschlagenes niedriges Risiko** – Testfehler, geringes Risiko
    - **Fehler bei mittlerem Risiko** – Testfehler, mittleres Risiko
    - Fehler **hafte hohe Risiko** Tests, hohes Risiko
    - **Außerhalb des Gültigkeitsbereichs** – die Aktion hat keinen Umfang für die Bewertung und wirkt sich nicht auf Ihre Punktzahl aus.
    - **Zu erkennen** : für manuellen Test wird angegeben, dass eine Aktion implementiert, aber nicht getestet wurde; für automatisierte Tests gibt an, dass eine Aktion auf das Automatisierungs Ergebnis wartet.
    - **Konnte nicht ermittelt werden** – automatischer Status kann nicht ermittelt werden
    - **Teilweise getestet** – automatisiertes Scoring zur Vergabe von Teil Punkten

**Weitere Informationen** [finden Sie unter zuweisen und Ausführen von Arbeiten zu Verbesserungs Aktionen](compliance-manager-improvement-actions.md).

## <a name="solutions-page"></a>Seite "Lösungen"

Auf der Seite Lösungen wird der Anteil der gesammelten und potenziellen Punkte wie in der Lösung organisiert dargestellt. Das Anzeigen der verbleibenden Punkte und Verbesserungs Aktionen in dieser Ansicht hilft Ihnen zu verstehen, welche Lösungen mehr sofortige Aufmerksamkeit benötigen.

Suchen Sie die Seite Lösungen, indem Sie auf der Registerkarte **Lösungen** im Compliance-Manager-Dashboard auswählen. Sie können auch im oberen rechten Bereich des Dashboards die Option **alle Lösungen** unterhalb von Lösungen anzeigen, die sich **auf Ihre Punktzahl auswirken** .

### <a name="filtering-your-solutions-view"></a>Filtern der Lösungs Ansicht

So filtern Sie die Ansicht von Lösungen:

1. Wählen Sie in der oberen linken Ecke der Liste Bewertungen die Option **Filter** aus.
2. Platzieren Sie im Flyout- **Filter** Bereich eine Überprüfung neben den gewünschten Kriterien (Normen und Verordnungen, Lösung, Aktionstyp, Compliance-Manager-Gruppe, Kategorie).
3. Klicken Sie auf die Schaltfläche über **nehmen** . Der Filterbereich wird geschlossen, und die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt oder Regulierung angezeigt werden, indem Sie den Typ der Gruppierung aus dem Dropdownmenü **Gruppieren** oberhalb Ihrer Bewertungsliste auswählen.

### <a name="taking-action-from-the-solution-page"></a>Ergreifen von Aktionen auf der Lösungsseite

Auf der Seite Lösungen werden die Lösungen Ihrer Organisation angezeigt, die mit Verbesserungs Aktionen verbunden sind. In der Tabelle werden die Beiträge der einzelnen Lösungen zu ihrer Gesamtpunktzahl, die erreichten und möglichen Punkte in dieser Lösung sowie die verbleibende Anzahl von Verbesserungs Aktionen, die in dieser Lösung gruppiert sind, aufgelistet, die Ihre Punktzahl verbessern kann.

Es gibt zwei Möglichkeiten, auf diesem Bildschirm Maßnahmen zu ergreifen:

1. Wählen Sie in der Zeile der gewünschten Lösung unter der Spalte **verbleibende Aktionen** die mit Hyperlinks verlinkte Nummer aus. Auf dem Bildschirm Verbesserungs Aktionen wird eine gefilterte Ansicht angezeigt, in der nicht getestete Verbesserungs Aktionen für diese Lösung angezeigt werden.

2. Wählen Sie in der Zeile der gewünschten Lösung unter der Spalte **Open Solution** die Option **Öffnen**aus. Sie sehen die Lösung oder den Standort im Sicherheits-und Compliance Center von Microsoft 365 und Office 365, in der Sie die empfohlene Aktion durchführen können.

## <a name="assessments-page"></a>Seite "Bewertungen"

Auf der Seite "Bewertungen" werden alle [Bewertungen](compliance-manager-assessments.md) aufgelistet, die Sie für Ihre Organisation eingerichtet haben. Der Nenner der Konformitätsbewertung wird durch alle nachverfolgten Bewertungen bestimmt. Wenn Sie weitere Bewertungen hinzufügen, werden auf der Seite Verbesserungs Aktionen weitere Verbesserungs Aktionen aufgeführt, und der Nenner der Konformitätsbewertung wird erhöht.

Auf der Seite "Bewertungen" werden wichtige Informationen zu den einzelnen Bewertungen zusammengefasst:

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
3. Klicken Sie auf die Schaltfläche über **nehmen** . Der Filterbereich wird geschlossen, und die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt oder Regulierung angezeigt werden, indem Sie den Typ der Gruppierung aus dem Dropdownmenü **Gruppieren** oberhalb Ihrer Bewertungsliste auswählen.

### <a name="default-assessment"></a>Standardbewertung

Standardmäßig sehen Sie die [Datenschutz-Basis](compliance-manager-assessments.md#data-protection-baseline-default-assessment) Bewertung auf der Seite "Bewertungen". Compliance-Manager bietet auch mehrere vorgefertigte [Vorlagen](compliance-manager-templates-list.md) zum Erstellen von Bewertungen.

## <a name="assessment-templates-page"></a>Seite "Bewertungs Vorlagen"

Eine Vorlage ist ein Framework zum Erstellen einer Bewertung im Compliance-Manager. Auf der Seite "Bewertungs Vorlagen" wird eine Liste der Vorlagen und Schlüssel Details angezeigt. Die Liste enthält Vorlagen, die vom Compliance-Manager bereitgestellt werden, sowie alle Vorlagen, die Ihre Organisation geändert oder erstellt hat. Sie können Filter anwenden, um eine Vorlage basierend auf Zertifizierung, Produktbereich, Land, Branche und der Person zu finden, die Sie erstellt hat.

Wählen Sie in der Zeile eine Vorlage aus, um die Details-Seite aufzurufen, die eine Beschreibung der Vorlage enthält, sowie weitere Informationen zu Zertifizierungs-, Bereichs-und Steuerelement Details. Auf dieser Seite können Sie die entsprechenden Schaltflächen auswählen, um eine Bewertung zu erstellen, die Vorlagendaten nach Excel zu exportieren oder die Vorlage zu ändern.

**Weitere Informationen:** [Lesen Sie, wie Sie mit Bewertungs Vorlagen arbeiten](compliance-manager-templates.md).

## <a name="next-step"></a>Nächster Schritt
Passen Sie Compliance-Manager an, indem [Sie Assessments einrichten](compliance-manager-assessments.md).