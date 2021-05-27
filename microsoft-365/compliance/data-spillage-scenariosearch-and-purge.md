---
title: eDiscovery-Lösungsreihe Datenleckszenario – Suchen und Löschen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Verwenden Sie eDiscovery und Suchtools, um einen Datenlecksvorfall in Ihrer Organisation zu verwalten und darauf zu reagieren.
ms.openlocfilehash: f92887018a7ab1cec35526c2a36cce4b0889172e
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683775"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>eDiscovery-Lösungsreihe: Datenleckszenario – Suchen und Löschen

 **Was ist Datenleck, und warum sollten Sie sich darum kümmern?** Datenleck ist, wenn ein vertrauliches Dokument in einer nicht vertrauenswürdigen Umgebung freigegeben wird. Wenn ein Datenlecksvorfall erkannt wird, ist es wichtig, die Größe und Die Standorte des Spillages schnell zu bewerten, benutzeraktivitäten zu untersuchen und die ausgelaufenen Daten endgültig aus dem System zu löschen. 
  
## <a name="data-spillage-scenario"></a>Datenleckszenario

Sie sind lead information security officer bei Contoso. Sie werden über eine Datenlecksituation informiert, bei der ein Mitarbeiter unwissentlich ein streng vertrauliches Dokument mit mehreren Personen per E-Mail geteilt hat. Sie möchten schnell bewerten, wer dieses Dokument intern und extern erhalten hat. Sobald sie identifiziert wurden, möchten Sie Fallbefunde mit anderen Ermittlern teilen, um sie zu überprüfen, und dann die Daten endgültig aus dem Office 365. Nachdem die Untersuchung abgeschlossen ist, möchten Sie einen Bericht mit den Nachweisen der endgültigen Entfernung und anderen Falldetails für jeden zukünftigen Verweis generieren.
  
### <a name="scope-of-this-article"></a>Umfang dieses Artikels

Dieses Dokument enthält eine Liste der Anweisungen zum dauerhaften Entfernen einer Nachricht aus Microsoft 365, sodass sie nicht zugänglich oder wiederherstellbar ist. Informationen zum Löschen einer Nachricht und zur Wiederherstellung bis zum Ablauf des Aufbewahrungszeitraums für gelöschte Elemente finden Sie unter Suchen und Löschen von E-Mail-Nachrichten [in Ihrer Organisation.](search-for-and-delete-messages-in-your-organization.md)
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>Workflow zum Verwalten von Datenlecksvorfällen

Hier erfahren Sie, wie Sie einen Datenleckvorfall verwalten:

![Der 8-Schritt-Workflow zum Verwalten von Datenleckvorfällen](../media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[(Optional) Schritt 1: Verwalten, wer auf den Fall zugreifen kann, und Festlegen von Compliancegrenzen](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[Schritt 2: Erstellen eines eDiscovery-Falls](#step-2-create-an-ediscovery-case)<br/>
[Schritt 3: Suchen nach den übergelaufenen Daten](#step-3-search-for-the-spilled-data)<br/>
[Schritt 4: Überprüfen und Überprüfen von Fallbefunden](#step-4-review-and-validate-case-findings)<br/>
[Schritt 5: Verwenden des Nachrichtenverfolgungsprotokolls, um zu überprüfen, wie datenlecks freigegeben wurden](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[Schritt 6: Vorbereiten der Postfächer](#step-6-prepare-the-mailboxes)<br/>
[Schritt 7: Endgültiges Löschen der übergelaufenen Daten](#step-7-permanently-delete-the-spilled-data)<br/>
[Schritt 8: Überprüfen, Bereitstellen eines Löschnachweises und Überwachung](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>Dinge, die Sie wissen sollten, bevor Sie beginnen

- Wenn sich ein Postfach im Haltezeitraum befindet, verbleibt eine gelöschte Nachricht im Ordner "Wiederherstellbare Elemente", bis der Aufbewahrungszeitraum abläuft oder die Aufbewahrungszeit freigegeben wird. [In Schritt 6](#step-6-prepare-the-mailboxes) wird beschrieben, wie der Halteraum aus den Postfächern entfernt wird. Informieren Sie sich vor dem Entfernen des Halteraums bei Der Datensatzverwaltung oder den Rechtsabteilungen. Ihre Organisation kann über eine Richtlinie verfügen, die definiert, ob ein Postfach im Archiv oder ein Datenlecksvorfall Vorrang hat. 
    
- Um zu steuern, welche Benutzerpostfächer ein Ermittler für Datenlecks durchsuchen und verwalten kann, wer auf den Fall zugreifen kann, können Sie Compliancegrenzen einrichten und eine benutzerdefinierte Rollengruppe erstellen, die in [Schritt 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)beschrieben wird. Dazu müssen Sie Mitglied der Rollengruppe Organisationsverwaltung sein oder der Rollenverwaltungsrolle zugewiesen werden. Wenn Sie oder ein Administrator in Ihrer Organisation bereits Compliancegrenzen festgelegt haben, können Sie Schritt 1 überspringen.
    
- Zum Erstellen eines Falls müssen Sie Mitglied der Rollengruppe eDiscovery Manager oder Mitglied einer benutzerdefinierten Rollengruppe sein, der die Rolle Fallverwaltung zugewiesen ist. Wenn Sie kein Mitglied sind, bitten Sie einen Microsoft 365, Sie der [Rollengruppe des eDiscovery-Managers hinzuzufügen.](assign-ediscovery-permissions.md)
    
- Zum Erstellen und Ausführen einer Inhaltssuche müssen Sie Mitglied der Rollengruppe für eDiscovery-Manager sein, oder Ihnen muss die Compliancesuche-Verwaltungsrolle zugewiesen sein. Um Nachrichten löschen zu können, müssen Sie Mitglied der Rollengruppe „Organisationsverwaltung“ sein, oder Ihnen muss die Verwaltungsrolle zum Suchen und Löschen zugewiesen sein. Informationen zum Hinzufügen von Benutzern zu einer Rollengruppe finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center](./assign-ediscovery-permissions.md).
    
- Zum Durchsuchen der eDiscovery-Aktivitäten des Überwachungsprotokolls in Schritt 8 muss die Überwachung für Ihre Organisation aktiviert sein. Sie können nach Aktivitäten suchen, die innerhalb der letzten 90 Tage ausgeführt wurden. Weitere Informationen zum Aktivieren und Verwenden der Überwachung finden Sie im Abschnitt [Auditing the data spillage investigation process](#auditing-the-data-spillage-investigation-process) in Schritt 8. 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>(Optional) Schritt 1: Verwalten, wer auf den Fall zugreifen kann, und Festlegen von Compliancegrenzen

Je nach Organisationspraxis müssen Sie steuern, wer auf den eDiscovery-Fall zugreifen kann, der zum Untersuchen eines Datenleckvorfalls und zum Einrichten von Compliancegrenzen verwendet wird. Die einfachste Möglichkeit besteht in dem Hinzufügen von Ermittlern als Mitglieder einer vorhandenen Rollengruppe im Security & Compliance Center und anschließend dem Hinzufügen der Rollengruppe als Mitglied des eDiscovery-Falls. Informationen zu den integrierten eDiscovery-Rollengruppen und zum Hinzufügen von Mitgliedern zu einem eDiscovery-Fall finden Sie unter [Assign eDiscovery permissions](assign-ediscovery-permissions.md).
  
Sie können auch eine neue Rollengruppe erstellen, die ihren organisatorischen Anforderungen entspricht. Beispielsweise möchten Sie, dass eine Gruppe von Ermittlern für Datenlecks in der Organisation auf alle Fälle von Datenlecks zugreifen und zusammenarbeiten kann. Dazu erstellen Sie eine Rollengruppe "Datenleck-Ermittler", weisen die entsprechenden Rollen (Export, RMS Decrypt, Review, Preview, Compliance Search und Case Management) zu, fügen die Ermittler für Datenlecks zur Rollengruppe hinzu und fügen dann die Rollengruppe als Mitglied des eDiscovery-Falls für Datenlecks hinzu. Ausführliche Anweisungen dazu finden Sie unter Set [up compliance boundaries for eDiscovery investigations in Office 365.](set-up-compliance-boundaries.md) 
  
## <a name="step-2-create-an-ediscovery-case"></a>Schritt 2: Erstellen eines eDiscovery-Falls

Ein eDiscovery-Fall bietet eine effektive Möglichkeit zum Verwalten Ihrer Datenleckuntersuchung. Sie können der Rollengruppe, die Sie in Schritt 1 erstellt haben, Mitglieder hinzufügen, die Rollengruppe als Mitglied eines neuen eDiscovery-Falls hinzufügen, iterative Suchen durchführen, um die übergelaufenen Daten zu finden, einen Bericht zur Freigabe exportieren, den Status des Falls nachverfolgen und dann bei Bedarf auf die Details des Falls verweisen. Erwägen Sie, eine Benennungskonvention für eDiscovery-Fälle zu erstellen, die für Datenlecksvorfälle verwendet werden, und stellen Sie so viele Informationen wie möglich im Fallnamen und der Beschreibung zur Verfügung, damit Sie bei Bedarf in Zukunft suchen und auf diese verweisen können.
  
Um einen neuen Fall zu erstellen, können Sie eDiscovery im Security and Compliance Center verwenden. Weitere Informationen finden Sie unter "Erstellen eines neuen Falls" unter [Erste Schritte mit Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).
  
## <a name="step-3-search-for-the-spilled-data"></a>Schritt 3: Suchen nach den übergelaufenen Daten

Nachdem Sie nun einen Fall und verwalteten Zugriff erstellt haben, können Sie den Fall verwenden, um iterativ nach den übergelaufenen Daten zu suchen und die Postfächer zu identifizieren, die die übergelaufenen Daten enthalten. Sie verwenden dieselbe Suchabfrage, mit der Sie die E-Mail-Nachrichten gefunden haben, um dieselben Nachrichten in [Schritt 7 zu löschen.](#step-7-permanently-delete-the-spilled-data)
  
Informationen zum Erstellen einer Inhaltssuche, die einem eDiscovery-Fall zugeordnet ist, finden Sie unter Suchen nach Inhalt [in einem Core eDiscovery-Fall](search-for-content-in-core-ediscovery.md).
  
> [!IMPORTANT]
> Die Schlüsselwörter, die Sie in der Suchabfrage verwenden, enthalten möglicherweise die tatsächlichen überlaufenen Daten, nach der Sie suchen. Wenn Sie z. B. nach Dokumenten suchen, die eine Sozialversicherungsnummer enthalten, und sie als Suchschlüsselwort verwenden, müssen Sie die Abfrage anschließend löschen, um ein weiteres Überlaufen zu vermeiden. Weitere [Informationen finden Sie unter Löschen der Suchabfrage](#deleting-the-search-query) in Schritt 8.
  
## <a name="step-4-review-and-validate-case-findings"></a>Schritt 4: Überprüfen und Überprüfen von Fallbefunden

Nachdem Sie eine Inhaltssuche erstellt haben, müssen Sie überprüfen und überprüfen, ob die Suchergebnisse nur aus den E-Mail-Nachrichten bestehen, die gelöscht werden müssen. Bei einer Inhaltssuche können Sie eine Vorschau einer zufälligen Stichprobe von 1.000 E-Mail-Nachrichten anzeigen, ohne die Suchergebnisse zu exportieren, um weitere Datenlecks zu vermeiden. Weitere Informationen zu den Vorschaueinschränkungen finden Sie unter [Limits for Content Search](limits-for-content-search.md).
  
Wenn Sie mehr als 1.000 Postfächer oder mehr als 100 E-Mail-Nachrichten pro Postfach überprüfen müssen, können Sie die anfängliche Suche in mehrere Suchen unterteilen, indem Sie zusätzliche Schlüsselwörter oder Bedingungen wie Datumsbereich oder Absender/Empfänger verwenden und die Ergebnisse jeder Suche einzeln überprüfen. Notieren Sie sich alle Suchabfragen, die beim Löschen von Nachrichten in [Schritt 7 verwendet werden sollen.](#step-7-permanently-delete-the-spilled-data)

Wenn einem Verwahrer oder Endbenutzer eine Office 365 E5-Lizenz zugewiesen ist, können Sie bis zu 10.000 Suchergebnisse gleichzeitig mithilfe von Advanced eDiscovery. Wenn mehr als 10.000 E-Mail-Nachrichten überprüft werden müssen, können Sie die Suchabfrage nach Datumsbereich teilen und jedes Ergebnis einzeln überprüfen, da die Suchergebnisse nach Datum sortiert sind. In Advanced eDiscovery können Sie Suchergebnisse mit dem **Feature Bezeichnung** als Feature im Vorschaubereich markieren und das Suchergebnis nach dem gekennzeichneten Tag filtern. Dies ist hilfreich, wenn Sie mit einem sekundären Prüfer zusammenarbeiten. Mithilfe zusätzlicher Analysetools in Advanced eDiscovery, z. B. optische Zeichenerkennung, E-Mail-Threading und Vorhersagecodierung, können Sie Tausende von Nachrichten schnell verarbeiten und überprüfen und zur weiteren Überprüfung kennzeichnen. Weitere Informationen finden Sie unter [Quick setup for Advanced eDiscovery](./get-started-with-advanced-ediscovery.md).

Wenn Sie eine E-Mail-Nachricht mit überlaufenen Daten finden, überprüfen Sie die Empfänger der Nachricht, um zu ermitteln, ob sie extern freigegeben wurde. Um eine Nachricht weiter zu verfolgen, können Sie Absenderinformationen und Datumsbereiche erfassen, damit Sie die Nachrichtenverfolgungsprotokolle verwenden können. Dieser Vorgang wird in [Schritt 5 beschrieben.](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)

Nachdem Sie die Suchergebnisse überprüft haben, können Sie Ihre Ergebnisse für eine sekundäre Überprüfung mit anderen teilen. Personen, die Sie dem Fall in Schritt 1 zugewiesen haben, können den Fallinhalt sowohl in eDiscovery als auch in Advanced eDiscovery überprüfen und Fallbefunde genehmigen. Sie können auch einen Bericht generieren, ohne den tatsächlichen Inhalt zu exportieren. Sie können diesen Bericht auch als Löschnachweis verwenden, der in [Schritt 8 beschrieben wird.](#step-8-verify-provide-a-proof-of-deletion-and-audit)
  
 **So generieren Sie einen statistischen Bericht:**
  
1. Wechseln Sie **im** Fall eDiscovery zur Seite Suchen, und klicken Sie auf die Suche, für die Sie einen Bericht generieren möchten. 
    
2. Klicken Sie auf der Flyoutseite auf **Weitere > Export report**.
 
      Die Seite Bericht exportieren wird angezeigt.

    ![Wählen Sie die Suche aus, und klicken Sie dann > auf der Flyoutseite auf Weitere Informationen zum Exportbericht.](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. Wählen **Sie Alle Elemente aus,** einschließlich der Elemente, die ein unbekanntes Format haben, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden, und klicken Sie dann auf Bericht **generieren.**

4. Klicken Sie im Fall eDiscovery auf **Exportieren,** um die Liste der Exportaufträge anzeigen zu können. Möglicherweise müssen Sie auf **Aktualisieren klicken,** um die Liste zu aktualisieren, um den von Ihnen erstellten Exportauftrag anzeigen zu können.

5. Klicken Sie auf den Exportauftrag, und klicken Sie dann auf **der** Flyoutseite auf Bericht herunterladen.
 
    ![Klicken Sie auf der Seite Exportieren auf den Export, und klicken Sie dann auf "Bericht herunterladen"](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

Der **Bericht "Zusammenfassung** exportieren" enthält die Anzahl der Speicherorte, die mit Ergebnissen gefunden wurden, und die Größe der Suchergebnisse. Sie können dies verwenden, um den nach dem Löschen generierten Bericht zu vergleichen und einen Löschnachweis zu liefern. Der **Ergebnisbericht** enthält eine ausführlichere Zusammenfassung der Suchergebnisse, einschließlich Betreff, Absender, Empfänger, wenn die E-Mail gelesen wurde, Datum und Größe der einzelnen Nachrichten. Wenn eines der Details in diesem Bericht diese tatsächlich übergelaufenen Daten enthält, müssen Sie die Datei Results.csv nach Abschluss der Untersuchung endgültig löschen.

Weitere Informationen zum Exportieren von Berichten finden Sie unter [Export a Content Search report](export-a-content-search-report.md).
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>Schritt 5: Verwenden des Nachrichtenverfolgungsprotokolls, um zu überprüfen, wie datenlecks freigegeben wurden

Um weiter zu untersuchen, ob E-Mails mit überlaufenen Daten freigegeben wurden, können Sie optional die Nachrichtenverfolgungsprotokolle mit den Absenderinformationen und den Datumsbereichsinformationen abfragen, die Sie in Schritt 4 gesammelt haben. Der Aufbewahrungszeitraum für die Nachrichtenverfolgung beträgt 30 Tage für Echtzeitdaten und 90 Tage für Verlaufsdaten.
  
Sie können die Nachrichtenverfolgung im Security and Compliance Center oder die entsprechenden Cmdlets in Exchange Online PowerShell verwenden. Beachten Sie, dass die Nachrichtenablaufverfolgung keine vollständigen Garantien für die Vollständigkeit der zurückgegebenen Daten bietet. Weitere Informationen zur Verwendung der Nachrichtenverfolgung finden Sie unter: 
  
- [Nachrichtenablaufverfolgung im Security & Compliance Center](../security/office-365-security/message-trace-scc.md)
    
- [Neue Nachrichtenverfolgung im Security & Compliance Center](https://techcommunity.microsoft.com/t5/exchange-team-blog/new-message-trace-in-office-365-security-038-compliance-center/ba-p/607893)
    
## <a name="step-6-prepare-the-mailboxes"></a>Schritt 6: Vorbereiten der Postfächer

Nachdem Sie überprüft und überprüft haben, ob die Suchergebnisse nur die Nachrichten enthalten, die gelöscht werden müssen, müssen Sie eine Liste der E-Mail-Adressen der betroffen postfächer erfassen, die in Schritt 7 verwendet werden sollen, wenn Sie die überlaufenen Daten löschen. Möglicherweise müssen Sie auch die Postfächer vorbereiten, bevor Sie E-Mail-Nachrichten dauerhaft löschen können, je nachdem, ob die Wiederherstellung einzelner Elemente für die Postfächer aktiviert ist, die die überlaufenen Daten enthalten, oder ob sich eines dieser Postfächer im Haltezustand befindet.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>Eine Liste der Adressen von Postfächern mit überlaufenen Daten

Es gibt zwei Möglichkeiten, eine Liste von E-Mail-Adressen von Postfächern mit überlaufenen Daten zu erfassen.

**Option 1: Eine Liste der Adressen von Postfächern mit überlaufenen Daten erhalten**

1. Öffnen Sie den eDiscovery-Fall, wechseln Sie zur Seite **Suchen,** und wählen Sie die entsprechende Inhaltssuche aus. 
    
2. Klicken Sie auf der Flyoutseite auf **Ergebnisse anzeigen.**
    
3. Klicken Sie in der Dropdownliste **Einzelne Ergebnisse** auf **Suchstatistiken**.
    
4. Klicken Sie **in** der Dropdownliste Typ auf **Top locations**.
    
    ![Eine Liste der Postfächer mit Suchergebnissen auf der Seite "Top locations" in der Suchstatistik](../media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    Eine Liste der Postfächer, die Suchergebnisse enthalten, wird angezeigt. Die Anzahl der Elemente in jedem Postfach, die mit der Suchabfrage übereinstimmen, wird ebenfalls angezeigt.
    
5. Kopieren Sie die Informationen in der Liste, und speichern Sie sie in einer Datei, oder klicken Sie auf **Herunterladen,** um die Informationen in eine CSV-Datei herunterzuladen. 
    
**Option 2: Postfachspeicherorte aus dem Exportbericht erhalten**

Öffnen Sie den Zusammenfassenden Exportbericht, den Sie in [Schritt 4 heruntergeladen haben.](#step-4-review-and-validate-case-findings) In der ersten Spalte des Berichts wird die E-Mail-Adresse jedes Postfachs unter **Speicherorte aufgeführt.**
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>Vorbereiten der Postfächer, damit Sie die überlaufenen Daten löschen können

Wenn die Wiederherstellung einzelner Elemente aktiviert ist oder ein Postfach in der Warteschleife platziert wird, wird eine endgültig gelöschte (gelöschte) Nachricht im Ordner "Wiederherstellbare Elemente" aufbewahrt. Bevor Sie ausgelaufene Daten löschen können, müssen Sie die vorhandenen Postfachkonfigurationen überprüfen und die Wiederherstellung einzelner Elemente deaktivieren und alle Aufbewahrungs- oder Aufbewahrungsrichtlinien entfernen. Denken Sie daran, dass Sie ein Postfach gleichzeitig vorbereiten und dann denselben Befehl für verschiedene Postfächer ausführen oder ein PowerShell-Skript erstellen können, um mehrere Postfächer gleichzeitig vorzubereiten.

- Unter "Schritt 1: Sammeln von Informationen über das Postfach" finden Sie unter Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von [cloudbasierten](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) Postfächern, die im Archiv gespeichert sind, Anweisungen zum Überprüfen, ob die Wiederherstellung einzelner Elemente aktiviert ist oder ob das Postfach in der Aufbewahrungsaufbewahrung oder einer Aufbewahrungsrichtlinie zugewiesen ist. 

- Anweisungen zum Deaktivieren der Wiederherstellung einzelner Elemente finden Sie unter "Schritt 2: Vorbereiten des Postfachs" unter Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von [cloudbasierten](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) Postfächern im Archiv. 

- Anweisungen zum Entfernen einer Aufbewahrungs- oder Aufbewahrungsrichtlinie aus einem Postfach finden Sie unter "Schritt 3: Entfernen aller Haltepunkte aus dem Postfach" unter Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von [cloudbasierten](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) Postfächern im Archiv. 

- Unter "Schritt 4: Entfernen des Verzögerungsspeichers aus dem Postfach" finden Sie unter Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von [cloudbasierten](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) Postfächern, die in der Warteschleife gespeichert sind, Anweisungen zum Entfernen des Verzögerungsspeichers, der für das Postfach nach dem Entfernen eines beliebigen Haltetyps platziert wird.

> [!IMPORTANT]
> Informieren Sie sich vor dem Entfernen einer Aufbewahrungs- oder Aufbewahrungsrichtlinie bei Ihren Datensatzverwaltungs- oder Rechtsabteilungen. Ihre Organisation kann über eine Richtlinie verfügen, die definiert, ob ein Postfach im Archiv oder ein Datenlecksvorfall Vorrang hat. 
  
Stellen Sie sicher, dass das Postfach auf frühere Konfigurationen zurückgesetzt wird, nachdem Sie sichergestellt haben, dass die übergelaufenen Daten endgültig gelöscht wurden. Weitere Informationen finden Sie in [Schritt 7](#step-7-permanently-delete-the-spilled-data).

## <a name="step-7-permanently-delete-the-spilled-data"></a>Schritt 7: Endgültiges Löschen der übergelaufenen Daten

Mithilfe der Postfachspeicherorte, die Sie in Schritt 6 gesammelt und vorbereitet haben, und der Suchabfrage, die in Schritt 3 erstellt und verfeinert wurde, um E-Mail-Nachrichten zu finden, die die übergelaufenen Daten enthalten, können Sie die überlaufenen Daten nun endgültig löschen.  Wie bereits erläutert, müssen Sie zum Löschen von Nachrichten Mitglied der Rollengruppe Organisationsverwaltung sein oder der Verwaltungsrolle Suchen und Löschen zugewiesen werden. Informationen zum Hinzufügen von Benutzern zu einer Rollengruppe finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center](./assign-ediscovery-permissions.md).

Informationen zum Löschen der überlaufenen Nachrichten finden Sie unter [Suchen nach und Löschen von E-Mail-Nachrichten.](search-for-and-delete-messages-in-your-organization.md)

Beachten Sie beim Löschen von übergelaufenen Daten die folgenden Grenzwerte:

- Die maximale Anzahl von Postfächern in einer Suche, die Sie zum Löschen von Elementen verwenden können, indem Sie eine Such- und Bereinigungsaktion tun, beträgt 50.000. Wenn bei der in Schritt 3 erstellten Suche mehr als 50.000 Postfächer durchsucht werden, tritt bei der Bereinigungsaktion ein Fehler auf. Zum Durchsuchen von mehr als 50.000 Postfächern in einer einzigen Suche kann es typischerweise kommen, wenn Sie die Suche so konfigurieren, dass alle Postfächer in Ihrer Organisation durchsucht werden. Diese Einschränkung gilt auch dann, wenn weniger als 50.000 Postfächer Elemente enthalten, die der Suchabfrage entsprechen.

- Aus jedem Postfach können maximal 10 Elemente gleichzeitig entfernt werden. Da die Funktion zum Suchen und Entfernen von Nachrichten ein Tool zur Reaktion auf Vorfälle sein soll, stellt dieser Höchstwert sicher, dass Nachrichten schnell aus Postfächern entfernt werden können. Das Feature ist nicht zum Bereinigen von Benutzerpostfächern vorgesehen.

> [!IMPORTANT]
> E-Mail-Elemente in einer Überprüfung in einem erweiterten eDiscovery-Fall können nicht mithilfe der in diesem Artikel beschriebenen Verfahren gelöscht werden. Das liegt daran, dass Elemente in einem Überprüfungssatz Kopien von Elementen im Livedienst sind, die kopiert und an einem speicherort Azure Storage werden. Dies bedeutet, dass sie nicht von einer Inhaltssuche zurückgegeben werden, die Sie in Schritt 3 erstellen. Wenn Sie Elemente in einem Überprüfungssatz löschen möchten, müssen Sie den erweiterten eDiscovery-Fall löschen, der den Überprüfungssatz enthält. Weitere Informationen finden Sie unter [Schließen oder Löschen eines erweiterten eDiscovery-Falls](close-or-delete-case.md).
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>Schritt 8: Überprüfen, Bereitstellen eines Löschnachweises und Überwachung

Der letzte Schritt im Workflow zum Verwalten eines Datenleckvorfalls besteht in der Überprüfung, ob die übergelaufenen Daten dauerhaft aus dem Postfach entfernt wurden, indem Sie zum eDiscovery-Fall gehen und dieselbe Suchabfrage erneut ausführen, mit der diese Daten gelöscht wurden, um zu bestätigen, dass keine Ergebnisse zurückgegeben werden. Nachdem Sie bestätigt haben, dass die übergelaufenen Daten endgültig entfernt wurden, können Sie einen Bericht exportieren und ihn (zusammen mit dem ursprünglichen Bericht) als Löschnachweis verwenden. Anschließend können Sie [den Fall schließen,](close-reopen-delete-core-ediscovery-cases.md) damit Sie ihn erneut öffnen können, wenn Sie in Zukunft auf ihn verweisen müssen. Darüber hinaus können Sie Postfächer auch auf ihren vorherigen Status zurücksetzen, die Suchabfrage löschen, mit der die übergelaufenen Daten gefunden werden, und nach Überwachungsdatensätzen von Aufgaben suchen, die beim Verwalten des Datenleckvorfalls ausgeführt wurden.
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>Zurücksetzen der Postfächer auf den vorherigen Status

Wenn Sie eine Postfachkonfiguration in Schritt 6 geändert haben, um die Postfächer vorzubereiten, bevor die übergelaufenen Daten gelöscht wurden, müssen Sie sie in den vorherigen Zustand zurücksetzen. Weitere Informationen finden Sie unter "Schritt 6: Zurücksetzen des Postfachs auf den vorherigen Status" unter Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von [cloudbasierten Postfächern](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)im Archiv .
  
### <a name="deleting-the-search-query"></a>Löschen der Suchabfrage

Wenn die Schlüsselwörter in der Suchabfrage, die Sie in Schritt 3 erstellt und verwendet haben, einige der tatsächlichen übergelaufenen Daten enthalten, sollten Sie die Suchabfrage löschen, um weitere Datenlecks zu verhindern.
  
1. Öffnen Sie im Security and Compliance Center den eDiscovery-Fall, wechseln Sie zur Seite Suchen, und wählen Sie die entsprechende Inhaltssuche aus. 

2. Klicken Sie auf der Flyoutseite auf **Löschen**.

    ![Wählen Sie die Suche aus, und klicken Sie dann auf der Flyoutseite auf Löschen.](../media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)

### <a name="auditing-the-data-spillage-investigation-process"></a>Überwachen des Datenleckuntersuchungsprozesses

Sie können das Überwachungsprotokoll nach den eDiscovery-Aktivitäten durchsuchen, die während der Untersuchung ausgeführt wurden. Sie können auch das Überwachungsprotokoll durchsuchen, um die Überwachungsdatensätze für den **Befehl New-ComplianceSearchAction -Purge** zurückzukehren, den Sie in Schritt 7 ausgeführt haben, um die übergelaufenen Daten zu löschen. Weitere Informationen finden Sie unter:

- [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md)

- [Suchen nach eDiscovery-Aktivitäten im Überwachungsprotokoll](search-for-ediscovery-activities-in-the-audit-log.md)
