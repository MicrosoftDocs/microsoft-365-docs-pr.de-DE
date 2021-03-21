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
description: Festlegen von Microsoft Compliance Manager-Benutzerberechtigungen und -rollen und Konfigurieren automatisierter Tests von Aktionen. Verwalten Sie den Benutzerverlauf, und filtern Sie Ihre Dashboardansicht.
ms.openlocfilehash: d8eb1d7d8245aa31cb5429452128cedc0adf4684
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925703"
---
# <a name="get-started-with-compliance-manager"></a>Erste Schritte mit Compliance-Manager

**In diesem Artikel:** Dieser Artikel hilft Ihnen beim Einrichten von Compliance Manager. Erfahren Sie, **wie Sie auf Compliance-Manager** zugreifen, Rollen und Berechtigungen **festlegen** und automatische Tests **von Verbesserungsmaßnahmen konfigurieren.** Gehen Sie **durch Ihr Compliance -Manager-Dashboard,** und verstehen Sie die Hauptseiten: die Seite "Verbesserungsmaßnahmen", die Lösungsseite, die Bewertungsseite und die Seite "Bewertungsvorlagen".

## <a name="who-can-access-compliance-manager"></a>Wer auf compliance-Manager zugreifen kann

Compliance Manager ist für Organisationen mit Office 365- und Microsoft 365-Lizenzen sowie für Moderate und GCC High-Kunden der US Government Community Cloud (GCC) verfügbar. Bewertungsverfügbarkeit und Verwaltungsfunktionen hängen von Ihrem Lizenzvertrag ab.  [Anzeigen von Dienstbeschreibungsdetails](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="before-you-begin"></a>Bevor Sie beginnen

Der globale Microsoft 365-Administrator für Ihre Organisation ist wahrscheinlich der erste Benutzer, der auf den Compliance-Manager zu zugegriffen hat. Es wird empfohlen, dass sich der globale Administrator anmeldet und Benutzerberechtigungen wie unten beschrieben festlegen, wenn er den Compliance-Manager zum ersten Mal besucht.

## <a name="sign-in"></a>Anmelden

1. Wechseln Sie zum [Microsoft 365 Compliance Center,](https://compliance.microsoft.com/) und melden Sie **sich mit** Ihrem globalen Microsoft 365-Administratorkonto an.
2. Wählen Sie im linken Navigationsbereich den **Compliance-Manager** aus. Sie gelangen zu Ihrem [Compliance -Manager-Dashboard.](#understand-the-compliance-manager-dashboard)

Der direkte Link zum Zugriff auf den Compliance-Manager ist [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Festlegen von Benutzerberechtigungen und Zuweisen von Rollen

Der Compliance-Manager verwendet ein rollenbasiertes Zugriffssteuerungsmodell (RBAC). Nur Benutzer, denen eine Rolle zugewiesen ist, können auf den Compliance-Manager zugreifen, und die von jedem Benutzer zulässigen Aktionen werden durch den [Rollentyp eingeschränkt.](#role-types)

### <a name="where-to-set-permissions"></a>Festlegen von Berechtigungen

Die Person, die die globale Administratorrolle für Ihre Organisation übernimmt, kann Benutzerberechtigungen für den Compliance-Manager festlegen. Berechtigungen können im Office 365 Security & Compliance Center sowie in Azure Active Directory (Azure AD) festgelegt werden.

> [!NOTE]
> Kunden in der US Government Community (GCC) Hohe Umgebungen können nur Benutzerberechtigungen und Rollen für Compliance Manager in Azure AD festlegen. Weitere Informationen zu Azure AD-Anweisungen und Rollentypdefinitionen finden Sie unten.

Führen Sie zum Festlegen von Berechtigungen und Zuweisen von Rollen im Office 365 Security & Compliance Center die folgenden Schritte aus:

1. Wechseln Sie zum [Office 365 Security & Compliance Center,](https://protection.office.com/) und wählen Sie **berechtigungen** auf der linken Navigation aus.

2. Suchen Sie die Rollengruppe, der Sie einen oder mehrere Benutzer hinzufügen möchten, und aktivieren Sie das Kontrollkästchen links vom Gruppennamen. (Weitere Informationen [finden Sie in der Liste der Rollen und zugehörigen Funktionen weiter unten.](#role-types) Die Rollengruppennamen imitieren den Rollennamen.)

3. Wählen Sie im Flyoutbereich für diese Gruppe **unter der Kopfzeile** **Mitglieder** bearbeiten aus.

4. Wählen **Sie Mitglieder auswählen aus.** Ein weiteres Flyoutfenster wird angezeigt.

5. Wählen **Sie + Hinzufügen** aus, um einen oder mehrere Benutzer auszuwählen, die der Gruppe hinzugefügt werden.

6. Aktivieren Sie das Kontrollkästchen neben den Namen, die  Sie hinzufügen möchten, und wählen Sie dann unten die Schaltfläche Hinzufügen aus.

7. Wenn Sie mit dem Zuweisen von Benutzern fertig sind, wählen Sie **Fertig** aus, und wählen Sie **dann Speichern** und dann **Schließen aus.**

##### <a name="more-about-the-office-365-security--compliance-center"></a>Weitere Informationen zum Office 365 Security & Compliance Center

Weitere Informationen zu [Berechtigungen finden Sie im Office 365 Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

Wenn Sie keinen Zugriff auf das Office 365 Security and Compliance Center haben oder auf die klassische Version von Compliance Manager im Microsoft Service Trust Portal zugreifen müssen, bieten die Administratoreinstellungen im Dienstvertrauensportal eine weitere Möglichkeit zum Zuweisen von Rollen ([Ansichtsanweisungen](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)). Beachten Sie, dass diese Rollen in ihrer Funktionalität eingeschränkter sind.

##### <a name="more-about-azure-ad"></a>Weitere Informationen zu Azure AD

Informationen zum Zuweisen von Rollen und Festlegen von Berechtigungen in Azure AD finden Sie unter [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

Benutzer mit Azure AD-Identitäten, die nicht über Office 365- oder Microsoft 365-Abonnements verfügen, können im Microsoft 365 Compliance Center nicht auf den Compliance Manager zugreifen. Wenden Sie sich an cmresearch@microsoft.com, um Hilfe beim Zugriff [auf den Compliance-Manager cmresearch@microsoft.com.](mailto:cmresearch@microsoft.com)

### <a name="role-types"></a>Rollentypen

In der folgenden Tabelle sind die Funktionen aufgeführt, die von den einzelnen Rollen im Compliance-Manager zulässig sind. In der Tabelle wird außerdem gezeigt, wie [jede Azure AD-Rolle](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) den Rollen des Compliance-Managers zugewiesen wird. Benutzer benötigen mindestens die Leserolle des Compliance-Managers oder die globale Azure AD-Leserrolle, um auf den Compliance-Manager zu zugreifen.


| Der Benutzer kann: | Rolle "Compliance-Manager" | Azure AD-Rolle | 
| :------------- | :-------------: | :------------: |
| **Daten lesen, aber nicht bearbeiten**| Compliance-Manager-Leser  | Azure AD Global Reader, Security Reader | 
| **Bearbeiten von Daten**| Compliance-Manager-Beitrag | Complianceadministrator | 
| **Bearbeiten von Testergebnissen**| Compliance-Manager-Bewertung | Complianceadministrator | 
| **Verwalten von Bewertungen sowie Vorlagen- und Mandantendaten**| Verwaltung des Compliance-Managers | Complianceadministrator, Compliancedatenadministrator, Sicherheitsadministrator  | 
| **Zuweisen von Benutzern**| Globaler Administrator | Globaler Administrator | 

## <a name="settings-for-automated-testing-and-user-history"></a>Einstellungen für automatisierte Tests und Benutzerverlauf

Mit den Einstellungen des Compliance-Managers im Microsoft 365 Compliance Center können Sie automatische Tests von Verbesserungsmaßnahmen aktivieren und deaktivieren. Mit den Einstellungen können Sie auch die Daten von Benutzern verwalten, die Verbesserungsmaßnahmen zugeordnet sind, einschließlich der Möglichkeit, Verbesserungsmaßnahmen einem anderen Benutzer erneut zuzuweisen.  Nur Personen mit einer globalen Administrator- oder Compliance-Manager-Administratorrolle können auf die Compliance-Manager-Einstellungen zugreifen.

> [!NOTE]
> Das Feature für automatisierte Tests steht Kunden in GCC High-Umgebungen nicht zur Verfügung, da secure score in diesen Umgebungen nicht verfügbar ist. GCC Hohe Kunden müssen ihre Verbesserungsmaßnahmen manuell implementieren und testen.

### <a name="set-up-automated-testing"></a>Einrichten automatisierter Tests

Einige Verbesserungsmaßnahmen im Compliance Manager werden auch von [Microsoft Secure Score überwacht.](../security/mtp/microsoft-secure-score.md) Sie können automatisierte Tests von Aktionen einrichten, die gemeinsam überwacht werden, d. h., wenn eine Aktion in Secure Score getestet und aktualisiert wird, synchronisieren sich diese Ergebnisse mit denselben Aktionen im Compliance-Manager und zählen auf Ihre Compliance-Bewertung.

Automatische Tests sind standardmäßig für Organisationen aktiviert, die im Compliance Manager neu sind. Wenn Sie Microsoft 365 oder Office 365 zum ersten Mal bereitstellen, dauert es ungefähr sieben Tage, bis Secure Score Daten vollständig erfasst und in Ihre Compliance-Bewertung einbe berücksichtigt hat.  Wenn automatisierte Tests aktiviert sind, wird das Testdatum der Aktion nicht aktualisiert, aber der Teststatus wird aktualisiert. Wenn neue Bewertungen erstellt werden, enthalten Bewertungen automatisch Microsoft-Kontrollergebnisse und Secure Score-Integration.

Der globale Administrator für Ihre Organisation kann die Einstellungen für automatisierte Tests jederzeit ändern. Sie können automatisierte Tests für allgemeine Verbesserungsmaßnahmen deaktivieren oder für einzelne Aktionen aktivieren. Befolgen Sie die folgenden Anweisungen, um Die Einstellungen für automatisierte Tests zu ändern.

#### <a name="to-manage-your-automated-testing-settings"></a>So verwalten Sie Ihre automatischen Testeinstellungen:

1. Wählen **Sie** einstellungen auf der linken Navigation von einer beliebigen Stelle im [Microsoft 365 Compliance Center aus.](https://compliance.microsoft.com/)

2. Wählen Sie auf der Seite Einstellungen die Option **Compliance-Manager aus.**

3. Wählen **Sie automatisierte Tests** in der linken Navigation aus.

4. Wählen Sie die entsprechende Schaltfläche aus, um automatische Tests für alle Verbesserungsaktionen zu aktivieren, sie für alle Aktionen zu deaktivieren oder durch einzelne Aktion zu aktivieren.

5. Wenn Sie Pro **Verbesserungsaktion** aktivieren auswählen, werden in einer Liste alle verfügbaren Verbesserungsmaßnahmen angezeigt, aus der Sie auswählen können.  Aktivieren Sie das Kontrollkästchen neben jeder Aktion, die automatisch getestet werden soll.

6. Wählen **Sie Speichern** aus, um Ihre Einstellungen zu speichern. Sie erhalten am oberen Rand des Bildschirms eine Bestätigungsnachricht, dass Ihre Auswahl gespeichert wurde. Wenn Sie eine Fehlerbenachrichtigung erhalten, versuchen Sie es erneut.

**Hinweis:** Nur der globale Administrator kann automatische Updates für alle Aktionen aktivieren oder deaktivieren. Der Compliance-Manager-Administrator kann automatische Updates für einzelne Aktionen aktivieren, jedoch nicht für alle Aktionen global.

### <a name="manage-user-history"></a>Verwalten des Benutzerverlaufs

Mithilfe **der Einstellungen für den** Benutzerverlauf verwalten können Sie schnell ermitteln, welche Benutzer mit Verbesserungsmaßnahmen im Compliance-Manager gearbeitet haben. Die identifizierbaren Benutzerdaten, die Verbesserungsmaßnahmen zugeordnet sind, umfassen alle durchgeführten Implementierungs- und Testarbeiten, hochgeladene Dokumente und alle von ihnen eingegebenen Notizen. Das Verständnis und Abrufen dieser Art von Daten kann für die eigenen Complianceanforderungen Ihrer Organisation erforderlich sein.

Mit den Einstellungen für den Benutzerverlauf können Sie auch alle Verbesserungsaktionen von einem Benutzer zu einem anderen neu zuweisen.

**So suchen Sie die Einstellungen für den Benutzerverlauf:**

1. Wählen Sie einstellungen auf der linken Navigation von einer beliebigen Stelle im [Microsoft 365 Compliance Center aus.](https://compliance.microsoft.com/)

2. Wählen Sie auf der Seite Einstellungen die Option **Compliance-Manager aus.**

3. Wählen **Sie im linken Navigationsbereich** Benutzerverlauf verwalten aus.

Auf **der Seite Benutzerverlauf verwalten** wird eine Liste aller Benutzer nach E-Mail-Adresse angezeigt, denen eine Verbesserungsaktion zugewiesen ist. Verwenden Sie die **Schaltfläche** Suchen, um schnell einen bestimmten Benutzer zu finden, indem Sie ihre E-Mail-Adresse eingeben.

Rechts neben der E-Mail-Adresse  jedes Benutzers bietet das Dropdownmenü Select Optionen zum Exportieren eines Berichts, zum Erneuten Zuweisen von Verbesserungsmaßnahmen oder zum Löschen des Verlaufs. Weitere Informationen zu den einzelnen Optionen finden Sie in den einzelnen Abschnitten unten.

#### <a name="export-a-report-of-user-history-data"></a>Exportieren eines Berichts mit Benutzerverlaufsdaten

Sie können eine Excel-Datei exportieren, die eine Liste der Verbesserungsmaßnahmen enthält, die derzeit einem Benutzer zugewiesen sind.  Der Bericht listet auch alle von diesem Benutzer hochgeladenen Nachweisdateien auf. Diese Informationen können Ihnen dabei helfen, offene Verbesserungsmaßnahmen neu zuzuweisen.

Der Bericht spiegelt den Status der Verbesserungsaktion ab dem Erstellungsdatum wider. Es ist kein verlaufshistorischer Bericht aller vorherigen Änderungen am Status oder der Zuordnung (Informationen zum Exportieren eines Berichts von der Seite [verbesserungsaktionen](compliance-manager-improvement-actions.md#export-a-report)).

**Führen Sie die folgenden Schritte aus, um einen Bericht nach Benutzer zu exportieren:**

1. Wählen **Sie** einstellungen auf der linken Navigation von einer beliebigen Stelle im [Microsoft 365 Compliance Center aus.](https://compliance.microsoft.com/)

2. Wählen Sie auf der Seite Einstellungen die Option **Compliance-Manager aus.**

3. Wählen **Sie In der Navigation links** die Option Benutzerverlauf verwalten aus.

4. Suchen Sie ihren beabsichtigten Benutzer, indem  Sie die E-Mail-Adressen der Liste durchsuchen oder suchen auswählen und die E-Mail-Adresse des Benutzers eingeben.

5. Wählen Sie **im Dropdownmenü** Select die Option **Bericht exportieren aus.**

6. Sobald die Excel-Datei Ihres Berichts generiert wurde, können Sie sie öffnen und auf Ihrem lokalen Computer speichern.

#### <a name="reassign-improvement-actions-to-another-user"></a>Erneutes Zuweisen von Verbesserungsmaßnahmen zu einem anderen Benutzer

Sie können Verbesserungsaktionen von einem Benutzer zu einem anderen neu zuweisen. Wenn Sie eine Aktion erneut zuweisen, ändert sich der Dokumentuploadverlauf nicht, aber der Name des Benutzers, der die Dokumentation ursprünglich hochgeladen hat, wird nicht mehr innerhalb der Verbesserungsaktion angezeigt.

**Führen Sie die folgenden Schritte aus, um Verbesserungsmaßnahmen einem anderen Benutzer zuzuweisen:**

1. Wählen **Sie** einstellungen auf der linken Navigation von einer beliebigen Stelle im [Microsoft 365 Compliance Center aus.](https://compliance.microsoft.com/)

2. Wählen Sie auf der Seite Einstellungen die Option **Compliance-Manager aus.**

3. Wählen **Sie In der Navigation links** die Option Benutzerverlauf verwalten aus.

4. Suchen Sie einen Benutzer, indem Sie  die E-Mail-Adressen der Liste durchsuchen oder suchen auswählen und die E-Mail-Adresse dieses Benutzers eingeben.

5. Wählen Sie **im Dropdownmenü** Auswählen die Option **Verbesserungsaktionen neu zuweisen aus.** Der **Flyoutbereich "Verbesserungsaktionen** neu zuweisen" wird angezeigt.

6. Geben Sie **im Feld** Benutzer suchen den Namen oder die E-Mail-Adresse des Benutzers ein, dem Sie die Verbesserungsmaßnahmen *zuweisen möchten.*

7. Wenn der Name Des beabsichtigten Benutzers unter Verbesserungsaktionen zugewiesen **wird,** wählen Sie den Benutzer aus, und wählen Sie **Dann Aktionen zuweisen aus.**

8. Nach Abschluss der Neuzuweisung wird im Flyoutbereich eine Bestätigungsmeldung angezeigt, in der bestätigt wird, dass alle Verbesserungsaktionen des vorherigen Benutzers dem neuen Benutzer neu zugewiesen wurden. Wenn Sie eine Erneutes Zuweisenfehlerbenachrichtigung erhalten, schließen Sie das Fenster, und versuchen Sie es erneut. Wählen Sie Fertig aus, um den Flyoutbereich **zu schließen.**

Der neue Zuordnende erhält eine E-Mail, dass er einer Verbesserungsaktion zugewiesen wurde. Die E-Mail enthält einen direkten Link zur Detailseite der Verbesserungsaktion.
 
 > [!NOTE]
> Wenn Sie eine Aktion mit einer ausstehenden Aktualisierung erneut zuweisen, wird der direkte Link zur Aktion in der E-Mail für die neu zugewiesene E-Mail nicht mehr aktiv, wenn das Update nach der neu zugewiesenen Aktualisierung akzeptiert wird. Sie können dies beheben, indem Sie die Aktion dem Benutzer erneut zuweisen, nachdem das Update akzeptiert wurde. Erfahren Sie mehr über [Updates für Verbesserungsmaßnahmen](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

#### <a name="delete-user-history"></a>Löschen des Benutzerverlaufs

Durch löschen des Verlaufs eines Benutzers werden sie als Besitzer von Verbesserungsmaßnahmen entfernt und ihr Name aus allen anderen Feldern im Compliance-Manager entfernt. Wenn Sie den Verlauf eines Benutzers löschen, werden die Verbesserungsaktionen, die sie besaßen, erst dann einen **Wert zugewiesen,** wenn einem neuen Benutzer zugewiesen wurde. Alle Dokumente, die in die Verbesserungsaktion hochgeladen wurden, zeigen benutzer entfernt **an** stelle des Namens des gelöschten Benutzers an. Das Löschen des Benutzerverlaufs ist dauerhaft.

Führen Sie die folgenden Schritte aus, um den Verlauf eines Benutzers zu löschen:

1. Wählen **Sie** einstellungen auf der linken Navigation von einer beliebigen Stelle im [Microsoft 365 Compliance Center aus.](https://compliance.microsoft.com/)

2. Wählen Sie auf der Seite Einstellungen die Option **Compliance-Manager aus.**

3. Wählen **Sie In der Navigation links** die Option Benutzerverlauf verwalten aus.

4. Suchen Sie einen Benutzer, indem Sie  die E-Mail-Adressen der Liste durchsuchen oder suchen auswählen und die E-Mail-Adresse dieses Benutzers eingeben.

5. Wählen Sie **im Dropdownmenü** Select die Option Verlauf **löschen aus.**

6. Es wird ein Fenster angezeigt, in dem Sie aufgefordert werden, den endgültigen Löschvorgang des Benutzerverlaufs zu bestätigen. Um mit dem Löschen fortzufahren, wählen Sie **Verlauf löschen aus.** Wählen Sie Abbrechen aus, um den Verlauf zu verlassen, ohne den Verlauf **zu löschen.**

7. Sie gelangen zur Seite  Benutzerverlauf verwalten mit einer Bestätigungsmeldung oben, dass der Verlauf für den Benutzer gelöscht wurde.

## <a name="understand-the-compliance-manager-dashboard"></a>Verstehen des Compliance -Manager-Dashboards

Das Compliance -Manager-Dashboard bietet Ihnen eine Übersicht über Ihre aktuelle Compliance-Position.

![Compliance-Manager – Dashboard](../media/compliance-manager-dashboard.png "Compliance-Manager-Dashboard")

### <a name="overall-compliance-score"></a>Gesamter Compliance-Wert

Ihre Compliance-Bewertung wird ganz oben vorgestellt. Es zeigt einen Prozentsatz basierend auf punkten, die für die Durchführung von Verbesserungsmaßnahmen erreichbar sind, die wichtige Datenschutzstandards und -vorschriften erfüllen. Punkte aus [Microsoft-Aktionen](compliance-manager-assessments.md#microsoft-actions-tab), die meinem Microsoft verwaltet werden, zählen auch auf Ihre Compliance-Bewertung.

Wenn Sie zum ersten Mal zum Compliance-Manager kommen, basiert Ihre anfängliche Bewertung auf der [Microsoft 365-Datenschutzgrundlinie](compliance-manager-assessments.md#data-protection-baseline-default-assessment). Bei dieser Basisbewertung, die für alle Organisationen verfügbar ist, handelt es sich um eine Reihe von Steuerelementen, die allgemeine Branchenbestimmungen und -standards enthalten. Compliance Manager überprüft Ihre vorhandenen Microsoft 365-Lösungen und bietet Ihnen eine erste Bewertung basierend auf Ihren aktuellen Datenschutz- und Sicherheitseinstellungen. Wenn Sie Bewertungen hinzufügen, die für Ihre Organisation relevant sind, wird Ihre Bewertung für Sie aussagekräftiger.

**Weitere Informationen:** [Erfahren Sie, wie Ihre Compliance-Bewertung berechnet wird.](compliance-score-calculation.md)

### <a name="key-improvement-actions"></a>Wichtige Verbesserungsmaßnahmen

In diesem Abschnitt werden die besten Verbesserungsmaßnahmen aufgeführt, die Sie jetzt ergreifen können, um die größten positiven Auswirkungen auf die Gesamt-Compliance-Bewertung zu erzielen. Wählen **Sie Alle Verbesserungsmaßnahmen anzeigen aus,** um zur Seite Verbesserungsmaßnahmen zu wechseln.

### <a name="solutions-that-affect-your-score"></a>Lösungen, die sich auf Ihre Bewertung auswirken

In diesem Abschnitt werden Lösungen mit Verbesserungsmaßnahmen beschrieben, die sich positiv auf Ihre Bewertung auswirken können, sowie die Anzahl ausstehender Verbesserungsmaßnahmen in diesen Lösungen. Wählen **Sie Alle Lösungen anzeigen aus,** um ihre Lösungsseite zu besuchen.

### <a name="compliance-score-breakdown"></a>Aufschlüsselung der Compliance-Bewertung

In diesem Abschnitt erhalten Sie eine detailliertere Ansicht Ihrer Bewertung auf zwei verschiedene Arten:

- **Kategorien**: zeigt den Prozentsatz Ihrer Gesamtpunktzahl in Datenschutzkategorien an, z. B. "Informationen schützen" oder "Geräte verwalten".
- **Bewertungen**: zeigt den Prozentsatz Ihrer Fortschritte bei der Verwaltung von Bewertungen für bestimmte Compliance- und Datenschutzstandards, -vorschriften oder -gesetze wie DSGVO oder NIST 800-53 an.

### <a name="filtering-your-dashboard-view"></a>Filtern der Dashboardansicht

Sie können Ihre Dashboardansicht filtern, um nur die Elemente im Zusammenhang mit bestimmten Vorschriften und Standards, Lösungen, Aktionstyp, Bewertungsgruppen oder Datenschutzkategorien anzuzeigen. Wenn Sie Ihre Ansicht auf diese Weise filtern, wird auch die Bewertung auf Ihrem Dashboard gefiltert, und es wird angezeigt, wie viele Punkte Sie anhand ihrer Filterkriterien aus den insgesamt möglichen Punkten erzielt haben.

So wenden Sie Filter an:

1. Wählen **Sie auf** der oberen rechten Seite des Dashboards Filter aus.
2. Wählen Sie ihre Filterkriterien aus dem **Flyoutbereich** Filter aus, und wählen Sie dann **Übernehmen aus.**

Nachdem Sie einen Filter angewendet haben, wird Ihre Bewertung in Echtzeit angepasst. Der Prozentsatz der Compliance-Bewertung und die Aufschlüsselungsinformationen sowie die Verbesserungsmaßnahmen und -lösungen betreffen jetzt nur die Daten, die von Ihren Filterkriterien abgedeckt werden. Wenn Sie sich vom Compliance Manager abmelden, bleibt ihre gefilterte Ansicht erhalten, wenn Sie sich wieder anmelden.

So entfernen Sie Filter:

- Wählen Sie **auf der Überschrift** Angewendete Filter über Ihrer Compliance-Bewertung das **X** neben dem einzelnen Filter aus, den Sie entfernen möchten. oder
- Wählen **Sie oben** rechts im Dashboard Filter aus,  und wählen Sie dann im Flyoutbereich Filter **löschen aus.**

## <a name="improvement-actions-page"></a>Seite "Verbesserungsmaßnahmen"

[Verbesserungsmaßnahmen](compliance-manager-improvement-actions.md) sind Aktionen, die von Ihrer Organisation verwaltet werden. Das Arbeiten mit Verbesserungsmaßnahmen trägt dazu bei, Ihre Complianceaktivitäten zu zentralisieren und sich an Datenschutzbestimmungen und -standards zu halten. Jede Verbesserungsaktion enthält detaillierte Implementierungsanleitungen und einen Link, um Sie in die entsprechende Lösung zu starten. Verbesserungsmaßnahmen können Benutzern in Ihrer Organisation zugewiesen werden, um Implementierungs- und Testarbeiten durchzuführen. Sie können dokumentations-, notizen- und datensatzstatusupdates auch innerhalb der Verbesserungsaktion speichern.

### <a name="view-your-improvement-actions"></a>Anzeigen Ihrer Verbesserungsmaßnahmen

Das Compliance-Manager-Dashboard zeigt Ihre **wichtigsten Verbesserungsmaßnahmen.** Um alle Verbesserungsmaßnahmen anzuzeigen, wählen Sie die Registerkarte Verbesserungsaktionen auf Ihrem Dashboard aus, die Sie zu Ihrer Seite verbesserungsaktionen führt. Sie können auch alle Verbesserungsaktionen unter der Liste der wichtigsten Verbesserungsmaßnahmen auf Ihrem Dashboard anzeigen auswählen, um zu Ihrer Seite verbesserungsaktionen zu gelangen.

Auf der Seite Verbesserungsmaßnahmen werden alle Verbesserungsmaßnahmen angezeigt, die von Ihrer Organisation verwaltet werden. Aktionen, die von Microsoft verwaltet werden, können in jeder Bewertung angezeigt werden (weitere Informationen zu [Microsoft-Aktionen).](compliance-manager-assessments.md#microsoft-actions-tab)

Wenn Sie über eine lange Liste von Aktionen auf der Seite verbesserungsaktionen verfügen, kann es hilfreich sein, Ihre Ansicht zu filtern. Wählen **Sie filter** in der oberen rechten Ecke der Aktionsliste aus. Wenn der **Flyoutbereich** Filter angezeigt wird, wählen Sie Ihre Kriterien basierend auf Vorschriften und Standards, Lösung und Gruppe aus. Sie können ihre Ansicht auch anpassen, indem **Sie** in der oberen rechten Ecke Gruppe auswählen. Wählen Sie im Dropdownmenü die Option aus, um nach Gruppe, Lösung, Kategorie, Aktionstyp oder Status anzuzeigen.

Die Standardansicht für diese Seite zeigt keine Verbesserungsaktionen mit dem Teststatus **Passed an.** Zum Anzeigen von Aktionen, die tests bestanden haben, aktivieren Sie das Kontrollkästchen **Übergeben** im Flyoutbereich Filter. Nur Aktionen mit dem Teststatus **"Bestanden"** zählen für Ihre Bewertung. Einige Aktionen zeigen möglicherweise eine **ausstehende Aktualisierungsbezeichnung an.** Erfahren Sie mehr über [Updates für Verbesserungsmaßnahmen](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

Die Seite Verbesserungsmaßnahmen zeigt die folgenden Datenpunkte für jede Verbesserungsaktion:

- **Punkte erreicht:** Die Anzahl der Punkte, die aus der Gesamtzahl der verfügbaren Punkte erzielt wurden, indem Sie die Aktion abschließen.
- **Vorschriften**: die Vorschriften oder Standards im Zusammenhang mit der Aktion
- **Gruppe**: die Gruppe, der Sie die Aktion zugewiesen haben
- **Lösungen**: die Lösung, in der Sie die Aktion ausführen können
- **Bewertungen**: die Bewertungen, die die Aktion enthalten
- **Kategorien**: die zugehörige Datenschutzkategorie (z. B. Schützen von Informationen, Verwalten von Geräten usw.)
- **Teststatus**:
    - **Keine** – keine Statusaktualisierung aufgezeichnet
    - **Nicht bewertet** – tests hasn't started
    - **Bestanden** – Implementierung erfolgreich getestet
    - **Fehlgeschlagenes niedriges Risiko** – Tests fehlgeschlagen, geringes Risiko
    - **Fehlgeschlagenes mittleres Risiko** – Test fehlgeschlagen, mittleres Risiko
    - **Fehlgeschlagenes hohes Risiko** – Tests fehlgeschlagen, hohes Risiko
    - **Nicht im Bereich** – die Aktion hat keinen Umfang für die Bewertung und hat keine Auswirkungen auf Ihre Bewertung.
    - **Zu erkennen –** gibt für den manuellen Test an, dass eine Aktion implementiert, aber nicht getestet wurde. für automatisierten Test, gibt an, dass eine Aktion auf automatisierungsergebnis wartet
    - **Konnte nicht erkannt werden** – automatisierter Status kann nicht bestimmt werden
    - **Teilweise getestet –** automatisierte Bewertung, die Teilpunkte zugibt

**Weitere Informationen:** [Erfahren Sie, wie Sie Verbesserungsmaßnahmen zuweisen](compliance-manager-improvement-actions.md)und durchführen.

## <a name="solutions-page"></a>Seite "Lösungen"

Auf der Seite Lösungen wird der Anteil der verdienten und potenziellen Punkte nach Lösung organisiert angezeigt. Wenn Sie ihre verbleibenden Punkte und Verbesserungsmaßnahmen in dieser Ansicht anzeigen, erfahren Sie, welche Lösungen unmittelbarere Aufmerksamkeit benötigen.

Suchen Sie die Lösungsseite, indem Sie die Registerkarte **Lösungen** im Compliance -Manager-Dashboard auswählen. Sie können auch alle Lösungen  unter Lösungen **anzeigen** auswählen, die sich auf Ihre Bewertung auswirken, im oberen rechten Abschnitt Ihres Dashboards.

### <a name="filtering-your-solutions-view"></a>Filtern der Lösungsansicht

So filtern Sie ihre Ansicht von Lösungen:

1. Wählen **Sie in** der oberen linken Ecke der Bewertungsliste Filter aus.
2. Platzieren Sie **im Flyoutbereich** Filter eine Prüfung neben den gewünschten Kriterien (Standards und Vorschriften, Lösung, Aktionstyp, Gruppe "Compliance-Manager", Kategorie).
3. Wählen Sie die **Schaltfläche Anwenden** aus. Der Filterbereich wird geschlossen, und Die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt  oder Verordnung angezeigt werden, indem Sie den Typ der Gruppierung im Dropdownmenü Gruppe über Ihrer Bewertungsliste auswählen.

### <a name="taking-action-from-the-solution-page"></a>Ergreifen von Aktionen auf der Lösungsseite

Auf der Seite Lösungen werden die Lösungen Ihrer Organisation angezeigt, die mit Verbesserungsmaßnahmen verbunden sind. In der Tabelle sind der Beitrag der einzelnen Lösungen zu Ihrer Gesamtpunktzahl, die in dieser Lösung erzielten und möglichen Punkte sowie die verbleibende Anzahl von Verbesserungsmaßnahmen aufgeführt, die in dieser Lösung aufgeführt sind und ihre Bewertung erhöhen können.

Es gibt zwei Möglichkeiten, wie Sie auf diesem Bildschirm Aktionen ergreifen können:

1. Wählen Sie in der Zeile der beabsichtigten Lösung unter der Spalte **Verbleibende Aktionen** die Nummer mit Hyperlinks aus. Es wird eine gefilterte Ansicht des Bildschirms für Verbesserungsmaßnahmen angezeigt, in der nicht getestete Verbesserungsmaßnahmen für diese Lösung angezeigt werden.

2. Wählen Sie in der Zeile Der beabsichtigten Lösung unter der Spalte **Lösung öffnen** die Option **Öffnen aus.** Sie sehen die Lösung oder den Speicherort in den Microsoft 365- und Office 365-Sicherheits- und Compliancecentern, in denen Sie die empfohlene Aktion ergreifen können.

## <a name="assessments-page"></a>Bewertungsseite

Auf der Bewertungsseite sind alle [Bewertungen aufgeführt,](compliance-manager-assessments.md) die Sie für Ihre Organisation eingerichtet haben. Ihr Konformitätsbewertungs-Nenner wird durch alle Ihre nachverfolgten Bewertungen bestimmt. Wenn Sie weitere Bewertungen hinzufügen, werden auf der Seite Verbesserungsmaßnahmen weitere Verbesserungsmaßnahmen aufgeführt, und der Nenner der Compliancebewertung wird erhöht.

Der **Indikator aktivierter** Vorlagen am oberen Rand der Seite zeigt die Anzahl der aktiven Bewertungsvorlagen an, die derzeit verwendet werden, aus der Gesamtzahl der Vorlagen, die für Ihre Organisation verfügbar sind. Weitere [Informationen finden Sie unter Vorlagentyp.](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive)

Auf der Bewertungsseite werden die wichtigsten Informationen zu den einzelnen Bewertungen zusammengefasst:

- **Bewertung**: Name der Bewertung
- **Status**:
    - **Abgeschlossen** – alle Steuerelemente haben den Status "übergeben", oder mindestens ein Steuerelement wird übergeben, und der Rest ist "nicht mehr im Bereich"
    - **Unvollständig** – mindestens ein Steuerelement hat den Status "fehlgeschlagen"
    - **Keine** – alle Steuerelemente wurden nicht getestet
    - **In Bearbeitung** – Verbesserungsmaßnahmen haben einen anderen Status, z. B. "in Bearbeitung", "Teilguthaben" oder "unentdeckt"
- **Bewertungsfortschritt:** Der Prozentsatz der Arbeit, die bis zum Abschluss ausgeführt wurde, gemessen an der Anzahl der erfolgreich getesteten Steuerelemente
- **Ihre Verbesserungsmaßnahmen**: Die Anzahl der abgeschlossenen Aktionen, um die Implementierung Ihrer Steuerelemente zu erfüllen
- **Microsoft-Aktionen**: Die Anzahl abgeschlossener Aktionen zur Erfüllung der Implementierung von Microsoft-Steuerelementen
- **Gruppe**: Name der Gruppe, zu der die Bewertung gehört
- **Produkt**: zugeordneter Microsoft 365-Dienst
- **Verordnung**: der rechtliche Standard, die Richtlinie oder das Recht, das für die Bewertung gilt

### <a name="filtering-your-assessments-view"></a>Filtern der Bewertungsansicht

So filtern Sie die Ansicht von Bewertungen:

1. Wählen **Sie in** der oberen linken Ecke der Bewertungsliste Filter aus.
2. Überprüfen Sie **im Flyoutbereich** Filter die gewünschten Kriterien.
3. Wählen Sie die **Schaltfläche Anwenden** aus. Der Filterbereich wird geschlossen, und Die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt  oder Verordnung angezeigt werden, indem Sie den Typ der Gruppierung im Dropdownmenü Gruppe über Ihrer Bewertungsliste auswählen.

### <a name="default-assessment"></a>Standardbewertung

Standardmäßig wird die Datenschutzgrundlinienbewertung [auf](compliance-manager-assessments.md#data-protection-baseline-default-assessment) der Bewertungsseite angezeigt. Der Compliance-Manager stellt außerdem mehrere vordefinierte Vorlagen [für Gebäudebewertungen](compliance-manager-templates-list.md) bereit.

## <a name="assessment-templates-page"></a>Seite "Bewertungsvorlagen"

Eine Vorlage ist ein Framework zum Erstellen einer Bewertung im Compliance-Manager. Auf der Seite Bewertungsvorlagen wird eine Liste mit Vorlagen und Schlüsseldetails angezeigt. Die Liste enthält Vorlagen, die vom Compliance Manager bereitgestellt werden, sowie alle Vorlagen, die Ihre Organisation geändert oder erstellt hat. Sie können Filter anwenden, um eine Vorlage basierend auf Zertifizierung, Produktbereich, Land, Branche und derEntifizierung zu finden.

Der **Indikator aktivierter** Vorlagen am oberen Rand der Seite zeigt die Anzahl der aktiven Bewertungsvorlagen an, die derzeit verwendet werden, aus der Gesamtzahl der Vorlagen, die für Ihre Organisation verfügbar sind. Weitere [Informationen finden Sie unter Vorlagentyp.](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive)

Wählen Sie eine Vorlage aus der Zeile aus, um die Detailseite anzuzeigen, die eine Beschreibung der Vorlage sowie weitere Informationen zu Zertifizierung, Bereich und Steuerelementdetails enthält. Auf dieser Seite können Sie die entsprechenden Schaltflächen auswählen, um eine Bewertung zu erstellen, die Vorlagendaten nach Excel zu exportieren oder die Vorlage zu ändern.

**Weitere Informationen:** [Lesen Sie, wie Sie mit Bewertungsvorlagen arbeiten.](compliance-manager-templates.md)

## <a name="next-step"></a>Nächster Schritt
Passen Sie den Compliance-Manager an, [indem Sie Bewertungen einrichten.](compliance-manager-assessments.md)