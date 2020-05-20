---
title: Datenüberlauf Szenario der eDiscovery-Lösungsreihe – Suche und Bereinigung
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Verwenden Sie eDiscovery-und Such Tools, um einen Vorfall zur Verschütten von Daten in Ihrer Organisation zu verwalten und zu reagieren.
ms.openlocfilehash: 4246460f2f7d7fdc41754fc2acd3125601bb5f79
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292451"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>eDiscovery-Lösungsreihe: Szenario mit Datenüberlauf-Suche und Bereinigung

 **Was ist Datenüberlauf und warum sollten Sie sich darum kümmern?** Das Verschütten von Daten erfolgt, wenn ein vertrauliches Dokument in einer nicht vertrauenswürdigen Umgebung freigegeben wird. Wenn ein Vorfall mit Datenüberlauf erkannt wird, ist es wichtig, die Größe und die Speicherorte des Verfalls schnell zu bewerten, Benutzeraktivitäten um ihn herum zu untersuchen und anschließend die verschütteten Daten endgültig aus dem System zu löschen. 
  
## <a name="data-spillage-scenario"></a>Szenario mit Datenüberlauf

Sie sind Lead Information Security Officer bei Contoso. Sie werden über eine Datenüberlauf Situation informiert, in der ein Mitarbeiter unwissentlich ein streng vertrauliches Dokument mit mehreren Personen per e-Mail freigegeben hat. Sie möchten schnell bewerten, wer dieses Dokument intern und extern erhalten hat. Sobald Sie identifiziert wurden, möchten Sie die Fall Ergebnisse mit anderen Ermittlern teilen, um Sie zu überprüfen und die Daten dann endgültig aus Office 365 zu entfernen. Nach Abschluss der Untersuchung möchten Sie einen Bericht mit dem Nachweis der permanenten Entfernung und anderer Fall Details für zukünftige Verweise generieren.
  
### <a name="scope-of-this-article"></a>Umfang dieses Artikels

Dieses Dokument enthält eine Liste mit Anweisungen zum endgültigen Entfernen einer Nachricht von Microsoft 365, sodass Sie nicht zugänglich oder nicht mehr verfügbar ist. Informationen zum Löschen einer Nachricht und zum Wiederherstellen bis zum Ablauf des Aufbewahrungszeitraums für gelöschte Elemente finden Sie unter [Suchen nach und Löschen von e-Mail-Nachrichten in Ihrer Organisation](search-for-and-delete-messages-in-your-organization.md).
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>Workflow für die Verwaltung von Ereignissen zur Verschütten von Daten

Hier erfahren Sie, wie Sie einen Vorfall mit Datenüberlauf verwalten:

![Der 8-stufige Workflow zum Verwalten von Ereignissen mit Verschütten von Daten](../media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[Optional Schritt 1: Verwalten der Benutzer, die auf den Fall zugreifen und Compliance-Grenzen festlegen können](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[Schritt 2: Erstellen eines eDiscovery-Falls](#step-2-create-an-ediscovery-case)<br/>
[Schritt 3: Suchen nach den verschütteten Daten](#step-3-search-for-the-spilled-data)<br/>
[Schritt 4: überprüfen und Überprüfen der Fall Ergebnisse](#step-4-review-and-validate-case-findings)<br/>
[Schritt 5: Nachrichtenablauf Verfolgungsprotokoll verwenden, um zu überprüfen, ob verschüttete Daten freigegeben wurden](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[Schritt 6: Vorbereiten der Postfächer](#step-6-prepare-the-mailboxes)<br/>
[Schritt 7: Dauerhaftes Löschen der verschütteten Daten](#step-7-permanently-delete-the-spilled-data)<br/>
[Schritt 8: überprüfen, stellen Sie einen Nachweis für die Löschung bereit, und überwachen](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>Dinge, die Sie kennen sollten, bevor Sie beginnen

- Wenn ein Postfach gespeichert ist, bleibt eine gelöschte Nachricht im Ordner "Wiederherstellbare Elemente", bis der Aufbewahrungszeitraum abläuft oder der Haltestatus aufgehoben wird. [Schritt 6](#step-6-prepare-the-mailboxes) enthält Informationen zum Entfernen von Haltestatus aus den Postfächern. Wenden Sie sich vor dem Entfernen des haltebereichs an Ihre Datensatzverwaltung oder Rechtsabteilungen. Ihre Organisation verfügt möglicherweise über eine Richtlinie, die definiert, ob ein aufbewahrtes Postfach oder ein Vorfall mit Datenüberlauf Vorrang hat. 
    
- Um zu steuern, welche Benutzerpostfächer ein Daten verschüttender Prüfer suchen und verwalten kann, wer auf den Fall zugreifen kann, können Sie Compliance-Grenzen einrichten und eine benutzerdefinierte Rollengruppe erstellen, die in [Schritt 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)beschrieben wird. Hierzu müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" sein oder der Rolle "Rollenverwaltung" zugewiesen sein. Wenn Sie oder der Administrator in Ihrer Organisation bereits Kompatibilitäts Grenzen festgelegt haben, können Sie Schritt 1 überspringen.
    
- Zum Erstellen eines Falles müssen Sie Mitglied der Rollengruppe "eDiscovery-Manager" sein oder Mitglied einer benutzerdefinierten Rollengruppe sein, der die Fall Verwaltungsrolle zugewiesen ist. Wenn Sie kein Mitglied sind, bitten Sie einen Microsoft 365-Administrator, [Sie der Rollengruppe "eDiscovery-Manager" hinzuzufügen](assign-ediscovery-permissions.md).
    
- Zum Erstellen und Ausführen einer Inhaltssuche müssen Sie Mitglied der Rollengruppe für eDiscovery-Manager sein, oder Ihnen muss die Compliancesuche-Verwaltungsrolle zugewiesen sein. Um Nachrichten löschen zu können, müssen Sie Mitglied der Rollengruppe „Organisationsverwaltung“ sein, oder Ihnen muss die Verwaltungsrolle zum Suchen und Löschen zugewiesen sein. Informationen zum Hinzufügen von Benutzern zu einer Rollengruppe finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).
    
- Um die eDiscovery-Aktivitäten des Überwachungsprotokolls in Schritt 8 durchsuchen zu können, muss die Überwachung für Ihre Organisation aktiviert werden. Sie können nach Aktivitäten suchen, die in den letzten 90 Tagen durchgeführt wurden. Weitere Informationen zum Aktivieren und Verwenden von Überwachung finden Sie im Abschnitt [Auditing the Data Spilling Investigation Process](#auditing-the-data-spillage-investigation-process) in Schritt 8. 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>Optional Schritt 1: Verwalten der Benutzer, die auf den Fall zugreifen und Compliance-Grenzen festlegen können

Je nach ihrer organisatorischen Vorgehensweise müssen Sie steuern, wer auf den eDiscovery-Fall zugreifen kann, der zur Untersuchung von Datenüberlauf Ereignissen und zum Einrichten von Compliance-Grenzen verwendet wird. Die einfachste Möglichkeit besteht darin, Ermittler als Mitglieder einer vorhandenen Rollengruppe im Security & Compliance Center hinzuzufügen und die Rollengruppe dann als Mitglied des eDiscovery-Falls hinzuzufügen. Informationen zu den integrierten eDiscovery-Rollengruppen und zum Hinzufügen von Mitgliedern zu einem eDiscovery-Fall finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).
  
Sie können auch eine neue Rollengruppe erstellen, die an Ihren organisatorischen Anforderungen ausgerichtet ist. Beispielsweise können Sie eine Gruppe von Daten verschüttenden Ermittlern in der Organisation für den Zugriff auf und die Zusammenarbeit bei allen Fällen von Daten verschütten möchten. Hierzu erstellen Sie eine Rollengruppe "Daten verschüttender Prüfer", indem Sie die entsprechenden Rollen zuweisen (exportieren, RMS-entschlüsseln, überprüfen, Vorschau, Konformitäts Suche und Fallverwaltung), die Datenüberlauf Prüfer zur Rollengruppe hinzufügen und dann die Rollengruppe als Mitglied des eDiscovery-Falls mit Datenüberlauf hinzufügen. Ausführliche Anweisungen zur Vorgehensweise finden Sie unter [Einrichten von Compliance-Grenzen für eDiscovery-Untersuchungen in Office 365](tagging-and-assessment-in-advanced-ediscovery.md) . 
  
## <a name="step-2-create-an-ediscovery-case"></a>Schritt 2: Erstellen eines eDiscovery-Falls

Ein eDiscovery-Fall stellt eine effektive Möglichkeit zum Verwalten der Untersuchung von Daten verschütteten dar. Sie können der Rollengruppe, die Sie in Schritt 1 erstellt haben, Mitglieder hinzufügen, die Rollengruppe als Mitglied eines neuen eDiscovery-Falls hinzufügen, iterative Suchvorgänge durchführen, um die verschütteten Daten zu finden, einen Bericht zur Freigabe exportieren, den Status der Anfrage nachverfolgen und dann bei Bedarf auf die Details des Falls zurückgreifen. Erstellen Sie eine Benennungskonvention für eDiscovery-Fälle, die für Datenüberlauf Ereignisse verwendet werden, und geben Sie so viele Informationen wie möglich in den Fall Namen und die Beschreibung ein, damit Sie in Zukunft bei Bedarf suchen und auf Sie zugreifen können.
  
Um einen neuen Fall zu erstellen, können Sie eDiscovery im Security and Compliance Center verwenden. Weitere Informationen finden Sie unter "Erstellen eines neuen Falls" in [eDiscovery-Fällen](ediscovery-cases.md#step-2-create-a-new-case).
  
## <a name="step-3-search-for-the-spilled-data"></a>Schritt 3: Suchen nach den verschütteten Daten

Nachdem Sie nun einen Fall und verwalteten Zugriff erstellt haben, können Sie den Fall verwenden, um iterativ nach den verschütteten Daten zu suchen und die Postfächer zu identifizieren, die die verschütteten Daten enthalten. Sie verwenden dieselbe Suchabfrage, die Sie zum Auffinden der e-Mail-Nachrichten verwendet haben, um die gleichen Nachrichten in [Schritt 7](#step-7-permanently-delete-the-spilled-data)zu löschen.
  
Informationen zum Erstellen einer Inhaltssuche, die einem eDiscovery-Fall zugeordnet ist, finden Sie unter "erstellen und Ausführen einer mit einem Fall verknüpften Inhaltssuche" in [eDiscovery-Fällen](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case).
  
 **Wichtig:** Die Schlüsselwörter, die Sie in der Suchabfrage verwenden, enthalten möglicherweise die tatsächlich verschütteten Daten, die Sie suchen. Wenn Sie beispielsweise nach Dokumenten suchen, die eine Sozialversicherungsnummer enthalten, und Sie das Schlüsselwort "IT as Search" verwenden, müssen Sie die Abfrage anschließend löschen, um weiteres ausschütten zu vermeiden. Weitere Informationen finden Sie unter [Löschen der Suchabfrage](#deleting-the-search-query) in Schritt 8. 
  
## <a name="step-4-review-and-validate-case-findings"></a>Schritt 4: überprüfen und Überprüfen der Fall Ergebnisse

Nachdem Sie eine Inhaltssuche erstellt haben, müssen Sie die Suchergebnisse überprüfen und überprüfen und sicherstellen, dass Sie nur aus den e-Mail-Nachrichten bestehen, die gelöscht werden müssen. Bei einer Inhaltssuche können Sie eine Vorschau einer Zufallsstichprobe von 1.000 e-Mail-Nachrichten anzeigen, ohne die Suchergebnisse zu exportieren, um weitere Datenüberlauf zu vermeiden. Weitere Informationen zu den Vorschau Beschränkungen finden Sie unter [Limits for Content Search](limits-for-content-search.md).
  
Wenn Sie mehr als 1.000 Postfächer oder mehr als 100 e-Mail-Nachrichten pro Postfach zur Überprüfung haben, können Sie die anfängliche Suche mithilfe zusätzlicher Stichwörter oder Bedingungen wie Datumsbereich oder Absender/Empfänger in mehrere Suchvorgänge unterteilen und die Ergebnisse jeder Suche einzeln überprüfen. Achten Sie darauf, alle Suchabfragen zu notieren, die beim Löschen von Nachrichten in [Schritt 7](#step-7-permanently-delete-the-spilled-data)verwendet werden sollen.

Wenn einer Depotbank oder einem Endbenutzer eine Office 365 E5-Lizenz zugewiesen ist, können Sie mit Advanced eDiscovery bis zu 10.000 Suchergebnisse gleichzeitig untersuchen. Wenn mehr als 10.000 e-Mail-Nachrichten zu überprüfen sind, können Sie die Suchabfrage nach Datumsbereich aufteilen und jedes Ergebnis einzeln überprüfen, da die Suchergebnisse nach Datum sortiert sind. In Advanced eDiscovery können Sie Suchergebnisse mit dem Feature **Bezeichnung als** im Vorschaufenster markieren und das Suchergebnis nach dem Tag filtern, mit dem Sie beschriftet haben. Dies ist hilfreich, wenn Sie mit einem sekundären Bearbeiter zusammenarbeiten. Durch die Verwendung zusätzlicher Analysetools in Advanced eDiscovery, wie der optischen Zeichenerkennung, des e-Mail-Threadings und der Vorhersage Codierung können Sie schnell Tausende von Nachrichten verarbeiten und überprüfen und Sie zur weiteren Überprüfung markieren. Siehe [Quick Setup für Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md).

Wenn Sie eine e-Mail-Nachricht finden, die verschüttete Daten enthält, überprüfen Sie die Empfänger der Nachricht, um festzustellen, ob Sie extern freigegeben wurde. Zur weiteren Ablaufverfolgung einer Nachricht können Sie Absenderinformationen und den Datumsbereich erfassen, sodass Sie die in [Schritt 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)beschriebenen Protokolle der Nachrichtenablaufverfolgung verwenden können.

Nachdem Sie die Suchergebnisse überprüft haben, möchten Sie möglicherweise Ihre Ergebnisse mit anderen Benutzern für eine sekundäre Überprüfung freigeben. Personen, die Sie dem Fall in Schritt 1 zugewiesen haben, können die Fall Inhalte sowohl in eDiscovery-als auch in Advanced eDiscovery-und genehmigenden Fall Ergebnissen überprüfen. Sie können auch einen Bericht generieren, ohne den tatsächlichen Inhalt zu exportieren. Sie können auch denselben Bericht als Lösch Nachweis verwenden, der in [Schritt 8](#step-8-verify-provide-a-proof-of-deletion-and-audit)beschrieben wird.
  
 **So generieren Sie einen statistischen Bericht:**
  
1. Wechseln Sie zur **Suchseite im** eDiscovery-Fall, und klicken Sie auf die Suche, für die Sie einen Bericht generieren möchten. 
    
2. Klicken Sie auf der Seite Flyout auf **Weitere > Bericht exportieren**.
 
      Die Seite Bericht exportieren wird angezeigt.

    ![Wählen Sie die Suche aus, und klicken Sie dann auf der Flyout-Seite auf Weitere > Bericht exportieren.](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. Wählen Sie **alle Elemente aus, einschließlich derer, die nicht erkanntes Format aufweisen, verschlüsselt sind oder aus anderen Gründen nicht indiziert** wurden, und klicken Sie dann auf **Bericht erstellen**.

4. Klicken Sie im Fall eDiscovery auf **exportieren** , um die Liste der Exportaufträge anzuzeigen. Möglicherweise müssen Sie auf **Aktualisieren** klicken, um die Liste zu aktualisieren, um den soeben erstellten Exportauftrag anzuzeigen.

5. Klicken Sie auf den Exportauftrag, und klicken Sie dann auf der Flyout-Seite auf Bericht **herunterladen** .
 
    ![Klicken Sie auf der Seite exportieren auf exportieren, und klicken Sie dann auf "Bericht herunterladen".](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

Der Bericht " **Zusammenfassung exportieren** " enthält die Anzahl der gefundenen Speicherorte mit Ergebnissen und der Größe der Suchergebnisse. Sie können dies verwenden, um mit dem Bericht zu vergleichen, der nach dem Löschen generiert wurde, und als Nachweis für die Löschung anzugeben. Der Bericht **Ergebnisse** enthält eine detailliertere Zusammenfassung der Suchergebnisse, einschließlich Betreff, Absender, Empfänger, wenn die e-Mail gelesen wurde, Daten und die Größe der einzelnen Nachrichten. Wenn eine der Details in diesem Bericht die tatsächlich verschütteten Daten enthält, müssen Sie die CSV-Datei "Results" nach Abschluss der Untersuchung endgültig löschen.

Weitere Informationen zum Exportieren von Berichten finden Sie unter [Exportieren eines Inhalts Suchberichts](export-a-content-search-report.md).
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>Schritt 5: Nachrichtenablauf Verfolgungsprotokoll verwenden, um zu überprüfen, ob verschüttete Daten freigegeben wurden

Um weiter zu untersuchen, ob e-Mails mit verschütteten Daten freigegeben wurden, können Sie optional die Nachrichtenablauf Verfolgungsprotokolle mit den Absenderinformationen und den Datumsbereichs Informationen Abfragen, die Sie in Schritt 4 gesammelt haben. Beachten Sie, dass der Aufbewahrungszeitraum für die Nachrichtenablaufverfolgung 30 Tage für Echtzeitdaten und 90 Tage für Verlaufsdaten beträgt.
  
Sie können die Nachrichtenablaufverfolgung im Security and Compliance Center verwenden oder die entsprechenden Cmdlets in Exchange Online PowerShell verwenden. Beachten Sie, dass die Nachrichtenablaufverfolgung nicht vollständige Garantien für die Vollständigkeit der zurückgegebenen Daten bietet. Weitere Informationen zur Verwendung der Nachrichtenablaufverfolgung finden Sie unter: 
  
- [Nachrichtenablaufverfolgung im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/message-trace-scc)
    
- [Neue Nachrichtenablaufverfolgung im Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>Schritt 6: Vorbereiten der Postfächer

Nachdem Sie überprüft und überprüft haben, dass die Suchergebnisse nur die zu löschenden Nachrichten enthalten, müssen Sie eine Liste der e-Mail-Adressen der betroffenen Postfächer sammeln, die in Schritt 7 verwendet werden, wenn Sie die verschütteten Daten löschen. Möglicherweise müssen Sie auch die Postfächer vorbereiten, bevor Sie e-Mail-Nachrichten dauerhaft löschen können, je nachdem, ob die Wiederherstellung einzelner Elemente in den Postfächern aktiviert ist, die die verschütteten Daten enthalten, oder ob sich diese Postfächer in der Warteschleife befinden.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>Abrufen einer Liste von Adressen von Postfächern mit verschütteten Daten

Es gibt zwei Möglichkeiten, eine Liste der e-Mail-Adressen von Postfächern mit verschütteten Daten zu sammeln.

**Option 1: Abrufen einer Liste von Adressen von Postfächern mit verschütteten Daten**

1. Öffnen Sie den eDiscovery-Fall, wechseln Sie zur Seite **Suche** , und wählen Sie die entsprechende Inhaltssuche aus. 
    
2. Klicken Sie auf der Seite Flyout auf **Ergebnisse anzeigen**.
    
3. Klicken Sie in der Dropdownliste **Einzelne Ergebnisse** auf **Suchstatistiken**.
    
4. Klicken Sie in der Dropdownliste **Typ** auf **obere Standorte**.
    
    ![Abrufen einer Liste von Postfächern, die Suchergebnisse auf der Seite "Top-Standorte" in den Suchstatistiken enthalten](../media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    Eine Liste mit Postfächern, die Suchergebnisse enthalten, wird angezeigt. Die Anzahl der Elemente in jedem Postfach, die mit der Suchabfrage übereinstimmen, wird ebenfalls angezeigt.
    
5. Kopieren Sie die Informationen in der Liste, speichern Sie Sie in einer Datei, oder klicken Sie auf **herunterladen** , um die Informationen in eine CSV-Datei herunterzuladen. 
    
**Option 2: Abrufen von Postfachspeicher Orten aus dem Exportbericht**

Öffnen Sie den Export Zusammenfassungsbericht, den Sie in [Schritt 4](#step-4-review-and-validate-case-findings)heruntergeladen haben. In der ersten Spalte des Berichts wird die e-Mail-Adresse jedes Postfachs unter **Standorte**aufgeführt.
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>Vorbereiten der Postfächer, sodass Sie die verschütteten Daten löschen können

Wenn die Wiederherstellung einzelner Elemente aktiviert ist oder ein Postfach aufbewahrt wird, wird im Ordner "Wiederherstellbare Elemente" eine endgültig gelöschte Nachricht (bereinigt) gespeichert. Bevor Sie also verschüttete Daten löschen können, müssen Sie die vorhandenen Postfachkonfigurationen überprüfen und die Wiederherstellung einzelner Elemente deaktivieren und alle halte-oder Aufbewahrungsrichtlinien entfernen. Beachten Sie, dass Sie ein Postfach gleichzeitig vorbereiten und dann denselben Befehl für verschiedene Postfächer ausführen oder ein PowerShell-Skript erstellen können, um mehrere Postfächer gleichzeitig vorzubereiten.

- Weitere Informationen zum Überprüfen, ob die Wiederherstellung einzelner Elemente aktiviert ist oder ob das Postfach in der Warteschleife oder einer Aufbewahrungsrichtlinie zugewiesen ist, finden Sie unter "Schritt 1: Erfassen von Informationen über das Postfach" unter [Löschen von Elementen im Ordner "Wiederherstellbare Elemente](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) " in der Warteschleife. 

- Anweisungen zum Deaktivieren der Wiederherstellung einzelner Elemente finden Sie unter "Schritt 2: Vorbereiten des Postfachs" unter [Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von cloudbasierten Postfächern in der Warteschleife](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) . 

- Weitere Informationen zum Entfernen einer Aufbewahrungs-oder Aufbewahrungsrichtlinie aus einem Postfach finden Sie unter "Schritt 3: Entfernen aller haltebereiche aus dem Postfach" unter " [Löschen von Elementen im Ordner" Wiederherstellbare Elemente "in der Warteschleife für Cloud-basierte Postfächer](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) . 

- Siehe "Schritt 4: Entfernen der Verzögerungszeit aus dem Postfach" unter [Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von cloudbasierten Postfächern in der Warteschleife](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) , um Anweisungen zum Entfernen des Verzögerungs Speichers zu erhalten, der auf das Postfach gesetzt wird, nachdem ein Aufbewahrungs entfernt wurde.

> [!IMPORTANT]
> Erkundigen Sie sich bei der Datensatzverwaltung oder den Rechtsabteilungen, bevor Sie eine Aufbewahrungsrichtlinie entfernen. Ihre Organisation verfügt möglicherweise über eine Richtlinie, die definiert, ob ein aufbewahrtes Postfach oder ein Vorfall mit Datenüberlauf Vorrang hat. 
  
Stellen Sie sicher, dass das Postfach auf frühere Konfigurationen zurückgesetzt wird, nachdem Sie sichergestellt haben, dass die verschütteten Daten endgültig gelöscht wurden. Weitere Informationen finden Sie in [Schritt 7](#step-7-permanently-delete-the-spilled-data).

## <a name="step-7-permanently-delete-the-spilled-data"></a>Schritt 7: Dauerhaftes Löschen der verschütteten Daten

Mithilfe der Postfachspeicher Orte, die Sie in Schritt 6 gesammelt und vorbereitet haben, und der in Schritt 3 erstellten und verfeinerten Suchabfrage zum Auffinden von e-Mail-Nachrichten, die die verschütteten Daten enthalten, können Sie nun die verschütteten Daten endgültig löschen.  Wie bereits erläutert, müssen Sie ein Mitglied der Rollengruppe Organisationsverwaltung sein oder der Rolle Search and Purge Management zugewiesen sein, um Nachrichten zu löschen. Informationen zum Hinzufügen von Benutzern zu einer Rollengruppe finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

Informationen zum Löschen der verschütteten Nachrichten finden Sie in den Schritten 2 & 3 unter [Suchen nach und Löschen von e-Mail-Nachrichten](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)

> [!IMPORTANT]
> E-Mail-Elemente in einem Überprüfungs Satz in einem erweiterten eDiscovery-Fall können nicht mithilfe der Verfahren in diesem Artikel gelöscht werden. Das liegt daran, dass Elemente in einem Überprüfungs Sätze Kopien von Elementen im Live-Dienst sind, die kopiert und an einem Azure-Speicherort gespeichert werden. Dies bedeutet, dass Sie nicht von einer Inhaltssuche zurückgegeben werden, die Sie in Schritt 3 erstellen. Um Elemente in einem Überprüfungs Satzes zu löschen, müssen Sie den erweiterten eDiscovery-Fall löschen, der die Überprüfungsgruppe enthält. Weitere Informationen finden Sie unter [Schließen oder Löschen eines erweiterten eDiscovery-Falls](close-or-delete-case.md).
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>Schritt 8: überprüfen, stellen Sie einen Nachweis für die Löschung bereit, und überwachen

Der letzte Schritt im Workflow zum Verwalten eines Daten verschüttenden Vorfalls besteht darin, zu überprüfen, ob die verschütteten Daten endgültig aus dem Postfach entfernt wurden, indem Sie zum eDiscovery-Fall wechseln und dieselbe Suchabfrage erneut ausführen, die zum Löschen dieser Daten verwendet wurde, um zu bestätigen, dass keine Ergebnisse zurückgegeben werden. Nachdem Sie sichergestellt haben, dass die verschütteten Daten endgültig entfernt wurden, können Sie einen Bericht exportieren und ihn (zusammen mit dem ursprünglichen Bericht) als Lösch Nachweis hinzufügen. Anschließend können Sie [den Fall schließen, der](ediscovery-cases.md#optional-step-9-close-a-case)es Ihnen ermöglicht, ihn erneut zu öffnen, wenn Sie in der Zukunft darauf verwiesen haben. Darüber hinaus können Sie Postfächer auch in ihren vorherigen Zustand zurücksetzen, die Suchabfrage löschen, die zum Auffinden der verschütteten Daten verwendet wurde, und nach Überwachungseinträgen von Vorgängen suchen, die bei der Verwaltung des Ereignisses zur Verschütten von Daten ausgeführt werden. 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>Zurücksetzen der Postfächer in ihren vorherigen Zustand

Wenn Sie in Schritt 6 eine Postfachkonfiguration geändert haben, um die Postfächer vorzubereiten, bevor die verschütteten Daten gelöscht wurden, müssen Sie Sie in ihren vorherigen Zustand zurücksetzen. Weitere Informationen finden Sie unter "Schritt 6: Zurücksetzen des Postfachs auf den vorherigen Status" unter [Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von cloudbasierten Postfächern in der Warteschleife](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state).
  
### <a name="deleting-the-search-query"></a>Löschen der Suchabfrage

Wenn die Schlüsselwörter in der Suchabfrage, die Sie in Schritt 3 erstellt und verwendet haben, einige der tatsächlichen verschütteten Daten enthalten, sollten Sie die Suchabfrage löschen, um zu verhindern, dass weitere Daten verschüttet werden.
  
1. Öffnen Sie im Security and Compliance Center den eDiscovery-Fall, wechseln Sie zur Seite **Suche** , und wählen Sie die entsprechende Inhaltssuche aus.
    
2. Klicken Sie auf der Seite Flyout auf **Löschen**.

    ![Wählen Sie die Suche aus, und klicken Sie dann auf der Flyout-Seite auf Löschen.](../media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>Überwachen des Ermittlungsprozesses für Datenüberlauf

Sie können das Überwachungsprotokoll nach den eDiscovery-Aktivitäten durchsuchen, die während der Untersuchung durchgeführt wurden. Sie können das Überwachungsprotokoll auch durchsuchen, um die Überwachungseinträge für den Befehl **New-ComplianceSearchAction-Purge** zurückzugeben, den Sie in Schritt 7 ausgeführt haben, um die verschütteten Daten zu löschen. Weitere Informationen finden Sie unter:

- [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md)

- [Suchen nach eDiscovery-Aktivitäten im Überwachungsprotokoll](search-for-ediscovery-activities-in-the-audit-log.md)
  
