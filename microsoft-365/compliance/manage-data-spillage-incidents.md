---
title: Verwalten eines Ereignisses zur Verschütten von Daten in Microsoft 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 'In diesem Artikel wird beschrieben, wie Sie mithilfe des Tools für die neue Daten Untersuchung (Preview) im Security #a0 Compliance Center einen Vorfall mit Datenüberlauf verwalten.'
ms.openlocfilehash: 53193d3bd915562037a6409766e9be9d42d272c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081622"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a>Verwalten eines Ereignisses zur Verschütten von Daten in Microsoft 365

Das Verschütten von Daten erfolgt, wenn ein Dokument mit vertraulichen, vertraulichen oder bösartigen Informationen in einer nicht vertrauenswürdigen Umgebung veröffentlicht wird. Wenn ein Vorfall mit Datenüberlauf erkannt wird, ist es wichtig, dass die Umgebung schnell enthalten ist, die Größe und die Standorte des Verfalls bewertet, die Benutzeraktivitäten um Sie herum überprüft und dann die verschütteten Daten aus dem Dienst gelöscht werden. Mithilfe des Tools zur Datenermittlung (Preview) können Sie nach vertraulichen, böswilligen oder veralteten Daten in Office 365 suchen, um herauszufinden, was passiert ist, und dann entsprechende Aktionen durchführen.  

## <a name="scope-of-this-article"></a>Umfang dieses Artikels

Dieser Artikel enthält eine Liste mit Anweisungen zum endgültigen Löschen von Elementen aus Office 365 Postfächern, damit Sie nicht mehr zugänglich sind oder von Benutzern oder Administratoren wiederhergestellt werden können. 

> [!NOTE]
> Wenn Sie Elemente löschen, die sich in einer SharePoint-oder OneDrive für Unternehmen-Website befinden, werden Sie für 93 Tage ab dem Zeitpunkt aufbewahrt, zu dem Sie Sie aus Ihrem ursprünglichen Speicherort löschen.

## <a name="scenario"></a>Szenario

Sie werden über einen Vorfall mit Datenüberlauf informiert, bei dem ein Mitarbeiter unwissentlich ein streng vertrauliches Dokument mit mehreren Personen per e-Mail freigegeben hat. Sie möchten schnell beurteilen, wer dieses Dokument empfangen hat, sowohl innerhalb als auch außerhalb Ihrer Organisation. Nachdem Sie den Vorfall untersucht haben, planen Sie, ihre Ergebnisse mit anderen Ermittlern zu überprüfen und die verschütteten Daten dann endgültig aus Ihrer Office 365 Organisation zu entfernen. Nach Abschluss der Untersuchung möchten Sie alle Beweise entfernen. 

> [!IMPORTANT]
> Während Sie die verschütteten Daten in ihrer eigenen Organisation dauerhaft entfernen können, können alle Daten, die außerhalb Ihrer Organisation verschüttet werden, mit diesen Funktionen nicht entfernt werden.

## <a name="workflow"></a>Workflow

Im folgenden finden Sie den Workflow für die Verwendung von Daten Untersuchungen (Preview) zum Verwalten eines Ereignisses zur Verschütten von Daten:

1.  Erstellen Sie eine Daten Untersuchung.

2.  Suchen Sie nach vertraulichen, böswilligen oder verlegten Daten, und sammeln Sie Sie als Beweis.

3.  Überprüfen und untersuchen Sie die Beweise.

4.  Löschen Sie die verschütteten Daten endgültig.

5.  Schließen oder löschen Sie die Untersuchung.


## <a name="before-you-begin"></a>Bevor Sie beginnen

- Um eine Datenermittlung durchführen, nach Inhalten suchen und verschüttete Daten löschen zu können, müssen Sie Mitglied der Rollengruppe "Daten Ermittler" im Security #a0 Compliance Center sein.

- Um zu steuern, welche Benutzerpostfächer und OneDrive-Konten ein Prüfer durchsuchen kann, kann Ihre Organisation Compliance-Grenzen einrichten. Weitere Informationen erhalten Sie, indem [Sie Compliance-Grenzen für eDiscovery-Untersuchungen einrichten](tagging-and-assessment-in-advanced-ediscovery.md). 

## <a name="step-1-create-a-data-investigation"></a>Schritt 1: Erstellen einer Daten Untersuchung

So erstellen Sie eine Untersuchung im Tool zur Datenanalyse (Vorschau):

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich bei Office 365 mit einem Konto an, das Mitglied der Rollengruppe "Data Investigator" ist.
    
3. Klicken Sie im Security and Compliance Center auf **Daten Untersuchungen**.
 
4. Klicken Sie auf der Seite **Daten Ermittlungen (Vorschau)** auf **neue Untersuchung erstellen**.
    
5. Geben Sie auf der Seite **neue Daten Ermittlungs** Flyout der Untersuchung einen Namen (erforderlich), und geben Sie dann eine optionale unter Suchnummer und eine Beschreibung ein. Der Name muss in Ihrer Organisation eindeutig sein.

6. Führen **Sie unter möchten Sie zusätzliche Einstellungen nach dem Erstellen dieser Untersuchung konfigurieren?** eine der folgenden Aktionen aus:

    - Klicken Sie auf **Ja** , um die Untersuchung zu erstellen, und zeigen Sie die Seite **Einstellungen** im neuen Fall an. Auf diese Weise können Sie der Untersuchung Mitglieder hinzufügen.
    
    - Klicken Sie auf **Nein** , um die Untersuchung zu erstellen und in der Liste der Fälle auf der Seite **Daten Ermittlungen (Vorschau)** anzuzeigen. Wenn Sie diese Option auswählen, werden Sie als einziges Mitglied der Untersuchung hinzugefügt, und die Standardeinstellungen für Suche und Analyse werden verwendet. Sie können Mitglieder hinzufügen oder Einstellungen jederzeit ändern, nachdem die Untersuchung erstellt wurde.

7. Klicken Sie auf **Speichern** , um die Untersuchung zu erstellen.

    Die neue Untersuchung wird in der Liste auf der Seite **Daten Ermittlungen (Vorschau)** angezeigt. 

8. Klicken Sie zum Öffnen einer Untersuchung auf den Namen der Untersuchung. 

    Die Registerkarte **Start** für die Untersuchung wird angezeigt. 

> [!TIP]
> Erstellen Sie eine Benennungskonvention für Untersuchungen, und geben Sie so viele Informationen wie möglich in den Namen und die Beschreibung ein, damit Sie Sie in Zukunft gegebenenfalls finden und darauf Bezug nehmen können.
 
## <a name="step-2-search-for-the-spilled-data"></a>Schritt 2: Suchen nach den verschütteten Daten 
 
Wenn Sie wissen, welche Benutzer Sie nach verschütteten Daten durchsuchen möchten, können Sie diese als interessante Personen hinzufügen, um Ihre Datenquellen der Untersuchung zuzuordnen und Ihr Postfach und Ihr OneDrive-Konto schnell zu durchsuchen. Klicken Sie zum Hinzufügen von Personen, die für die Untersuchung interessant sind, auf **interessante**Personen, und klicken Sie dann auf interessante Personen **Hinzufügen**. Weitere Informationen finden Sie unter [Verwalten von Personen mit Interesse](manage-people-of-interest.md).

Auf der Registerkarte **Suchen** können Sie Suchvorgänge erstellen, um die verschütteten Daten zu finden. Weitere Informationen zum Erstellen von Suchvorgängen finden Sie unter [Suchen nach Daten in einer Untersuchung](search-for-data.md).

Nachdem Sie die Suche ausgeführt haben, können Sie eine Vorschau der Suchergebnisse anzeigen und Suchstatistiken anzeigen, um die Effektivität Ihrer Suchabfrage auszuwerten. Nachdem Sie die Elemente identifiziert haben, die Sie aus Office 365 löschen möchten, können Sie die Suchergebnisse einem Beweissatz hinzufügen. Klicken Sie dazu auf die Suche, die Sie untersuchen möchten. Klicken Sie auf der Seite Flyout auf **Ergebnisse zu Beweismitteln hinzufügen** , und befolgen Sie die Anweisungen. Anschließend können Sie in den Beweis Sätzen einzelne Dokumente überprüfen, ermitteln, wer Zugriff auf Dokumente hat, und die Dokumente exportieren. Wenn Sie die Dokumente (oder eine Teilmenge von Dokumenten) löschen möchten, statt sie zu überprüfen, fahren Sie mit [Schritt 4](#step-4-delete-the-spilled-data)fort. 

> [!IMPORTANT]
> Die Schlüsselwörter, die Sie in der Suchabfrage verwenden, enthalten möglicherweise die tatsächlich verschütteten Daten, die Sie suchen. Wenn Sie beispielsweise nach Dokumenten suchen, die eine Sozialversicherungsnummer enthalten, und Sie Sie als Stichwort in der Suchabfrage verwenden, müssen Sie die Abfrage anschließend löschen, um weiteres auslaufen zu vermeiden. Sie können die Suche löschen oder die gesamte Untersuchung in [Schritt 5](#step-5-close-or-delete-the-investigation)löschen. 

## <a name="step-3-review-and-investigate"></a>Schritt 3: überprüfen und untersuchen 

Wechseln Sie in der Untersuchung zur Registerkarte **Beweise** , und klicken Sie auf den Beweissatz, den Sie im vorherigen Schritt erstellt haben. Nachdem der Verarbeitungsauftrag abgeschlossen wurde und die Suchergebnisse dem Beweis hinzugefügt wurden, können Sie einzelne Dokumente in ihrem systemeigenen Format, im Text Format oder im nahezu systemeigenen Format überprüfen. Sie können zusätzliche Abfragen erstellen, um die Liste der Dokumente einzuschränken und Dokumente zu markieren, um die Ergebnisse ihrer Untersuchung anzugeben. Weitere Informationen finden Sie unter [Überprüfen von Daten in Evidence](review-data-in-evidence.md) .

Klicken Sie auf **Beweise verwalten**, um Dokumente zu gruppieren und weitere Unterstützung für Ihre Überprüfung zu erhalten. Klicken Sie in der **Analyse** Kachel auf **analysieren**. Dadurch werden erweiterte Analysen wie doppelte Erkennung, e-Mail-Threading und Design Analyse ausgeführt. Weitere Informationen finden Sie unter:

- [Durchführen von Analysen zur schnelleren Untersuchung](run-analytics-to-investigate-faster.md)
- [Erkennen von Quasiduplikaten](near-duplicates.md)
- [E-Mail-Threading](email-threading.md)
- [Designs](themes.md)

Um zu ermitteln, welche Benutzer am Datenüberlauf beteiligt sind, können Sie eine Abfrage im Beweissatz erstellen und dann die Bedingungen Absender/Autor und Empfänger verwenden. Dadurch wird eine Liste aller Absender, Empfänger und Autoren erstellt, die in gesammelten Daten gefunden wurden, die dem Beweis hinzugefügt wurden. Stellen Sie sicher, dass Sie die Liste untersuchen, um festzustellen, ob externe Benutzer vorhanden sind. Weitere Informationen zum Einschränken von Suchergebnissen mithilfe von Bedingungen finden Sie unter [Suchbedingungen](keyword-queries-and-search-conditions.md#search-conditions).

## <a name="step-4-delete-the-spilled-data"></a>Schritt 4: Löschen der verschütteten Daten

Mithilfe des Tools zur Datenermittlung können Sie Elemente aus ihren ursprünglichen Speicherorten löschen. Sie können beispielsweise Elemente aus Postfächern, SharePoint-Websites und OneDrive-Konten in Ihrer Organisation löschen. Beachten Sie, dass Sie, da Sie Elemente als Beweismaterial gesammelt haben (indem Sie die Suchergebnisse dem in Schritt 2 festgelegten Nachweis hinzugefügt haben), Kopien der Elemente im Evidence-Satzes haben, um Sie weiter zu untersuchen oder beizubehalten.

So löschen Sie Elemente aus ihren ursprünglichen Speicherorten:

1. Wählen Sie in der Gruppe Beweise die Elemente aus, die Sie löschen möchten. Wenn Sie Elemente auswählen, die einer e-Mail-Nachricht zugeordnet sind, wird die übergeordnete e-Mail-Nachricht ebenfalls ausgewählt und gelöscht. 
 
2. Klicken Sie auf **Aktion** und dann auf **Elemente aus ursprünglichen Speicherorten löschen**.

   ![Klicken Sie auf Aktion und dann auf Elemente aus ursprünglichen Speicherorten löschen.](media/DataInvestigationsDeleteItems1.png)

3. Überprüfen Sie auf der Seite Flyout die Anzahl der Elemente und zugehörigen untergeordneten Dokumente, die gelöscht werden sollen, und klicken Sie dann auf **Löschen**.

Wenn Sie jetzt Elemente aus Ihrem ursprünglichen Speicherort löschen, werden die Elemente vorläufig gelöscht. Dies bedeutet, dass die gelöschten Elemente beibehalten werden, bis der Wiederherstellungszeitraum für gelöschte Elemente für das Element abläuft. Dies bedeutet auch, dass Benutzer diese Elemente wiederherstellen können. Weitere Informationen dazu, was geschieht, wenn Elemente aus Postfächern und Websites gelöscht werden, finden Sie unter [Löschen von Elementen von Ihrem ursprünglichen Speicherort](delete-items-from-original-locations.md).

## <a name="step-5-close-or-delete-the-investigation"></a>Schritt 5: schließen oder Löschen der Untersuchung

Nachdem Sie Dokumente in den Quellinhalts Speicherorten (Postfächern oder Websites) im Live-Dienst gelöscht haben, verfügen Sie weiterhin über Kopien dieser Dokumente, die Sie im Rahmen der Untersuchung zum Beweis hinzugefügt haben. Um weitere Datenüberlauf zu vermeiden, sollten Sie das Löschen der Untersuchung selbst in Betracht ziehen.

So löschen Sie eine Untersuchung:

1. Klicken Sie auf der Registerkarte **Einstellungen** auf **Ermittlungsinformationen**.

2. Klicken Sie auf **Untersuchung löschen**. 

Wenn Sie die Untersuchung nicht löschen müssen oder wenn Sie die Informationen speichern möchten, die Sie während der Untersuchung gesammelt haben, können Sie auf **Fall schließen**klicken. Später können Sie abgeschlossene Untersuchungen erneut öffnen.
