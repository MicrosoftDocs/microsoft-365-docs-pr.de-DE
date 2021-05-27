---
title: Filtern von Daten beim Importieren von PST-Dateien
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
ms.custom: seo-marvel-apr2020
description: Erfahren Sie, wie Sie Daten mithilfe des intelligenten Importfeatures im Office 365 importieren, wenn Sie PST-Dateien in Office 365.
ms.openlocfilehash: fb978332f70495044a457147d29d8cdcf1194264
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684053"
---
# <a name="filter-data-when-importing-pst-files"></a>Filtern von Daten beim Importieren von PST-Dateien

Verwenden Sie das neue Feature Intelligent Import im Office 365 Import service, um die Elemente in PST-Dateien zu filtern, die tatsächlich in die Zielpostfächer importiert werden. Funktionsweise:
  
- Nachdem Sie einen PST-Importauftrag erstellt und übermittelt haben, werden PST-Dateien in einen Azure-Speicherbereich in der Microsoft Cloud hochgeladen.
  
- Microsoft 365 analysiert die Daten in den PST-Dateien auf sichere Weise, indem das Alter der Postfachelemente und die verschiedenen Nachrichtentypen identifiziert werden, die in den PST-Dateien enthalten sind.
  
- Wenn die Analyse abgeschlossen ist und die Daten importiert werden können, haben Sie die Möglichkeit, alle Daten in den PST-Dateien so zu importieren, wie sie sind, oder die importierten Daten zu kürzen, indem Sie Filter festlegen, die steuern, welche Daten importiert werden. Sie können z. B. folgende Option auswählen:
  
  - Importieren Sie nur Elemente eines bestimmten Alters.
  
  - Importiert ausgewählte Nachrichtentypen.
  
  - Ausschließen von Nachrichten, die von bestimmten Personen gesendet oder empfangen wurden.
  
- Nachdem Sie die Filtereinstellungen konfiguriert haben, importiert Microsoft 365 nur die Daten, die die Filterkriterien erfüllen, in die im Importauftrag angegebenen Zielpostfächer.
  
In der folgenden Grafik wird der Intelligente Importprozess gezeigt, und es werden die von Ihnen ausgeführten Aufgaben und die von der Office 365.
  
![Der intelligente Importprozess in Office 365](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a>Erstellen eines PST-Importauftrags

- Bei den Schritten in diesem Thema wird davon ausgegangen, dass Sie einen PST-Importauftrag im Office 365 Import service mithilfe von Netzwerkupload oder Laufwerkversand erstellt haben. Schrittweise Anweisungen finden Sie in einem der folgenden Themen:
    
  - [Verwenden des Netzwerkuploads zum Importieren von PST-Dateien in Office 365](use-network-upload-to-import-pst-files.md)
    
  - [Verwenden des Laufwerkversands zum Importieren von PST-Dateien in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- Nachdem Sie einen Importauftrag mithilfe des Netzwerkuploads erstellt haben, ist der Status für den Importauftrag auf der Seite Import im Security & Compliance Center auf **Analysis in progress** festgelegt, was bedeutet, dass Microsoft 365 die Daten in den hochgeladenen PST-Dateien analysiert. Klicken **Sie auf** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) Aktualisieren, um den Status des Importauftrags zu aktualisieren. 
    
- Bei Importaufträgen für den Laufwerkversand werden die Daten von Microsoft 365 analysiert, nachdem Mitarbeiter des Microsoft-Rechenzentrums Ihre Festplatte empfangen und die PST-Dateien in den Azure-Speicherbereich für Ihre Organisation hochgeladen haben.
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>Filtern von Daten, die in Postfächer importiert werden

Nachdem Sie einen PST-Importauftrag erstellt haben, führen Sie die folgenden Schritte aus, um die Daten zu filtern, bevor Sie ihn in Office 365.
  
1. Navigieren Sie zu <https://compliance.microsoft.com>, und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.
    
2. Klicken Sie im linken Bereich des Microsoft 365 Compliance Center auf **Information Governance** \> **Import**.
    
    Die Importaufträge für Ihre Organisation sind auf der Registerkarte **Importieren** aufgeführt. Der **Wert Analysis completed** in der Spalte **Status** gibt die Importaufträge an, die von Microsoft 365 analysiert wurden und zum Importieren bereit sind.
    
    ![Der vollständige Analysestatus gibt Microsoft 365 daten in PST-Dateien analysiert haben](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. Wählen Sie den Importauftrag aus, den Sie abschließen möchten, und klicken Sie **auf Import to Office 365**.
  
    Nun wird eine Flyout-Seite mit Informationen zu den PST-Dateien und anderen Informationen zur Importaufgabe angezeigt.

4. Klicken **Sie auf Importieren in Office 365**.
    
    Die Seite **Ihre Daten filtern** wird angezeigt. Sie enthält Dateneinblicke zu den Daten in den PST-Dateien für den Importauftrag, einschließlich Informationen zum Alter der Daten. 
    
    ![Die Seite Daten filtern zeigt Dateneinblicke der PST-Dateien für den Importauftrag an.](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. Gehen Sie basierend darauf, ob Sie die in Microsoft 365 importierten Daten kürzen möchten, unter Möchten Sie Ihre Daten **filtern?** eine der folgenden Schritte aus:
  
    a. Klicken **Sie auf Ja, ich möchte sie filtern,** bevor Sie importieren, um die importierten Daten zu kürzen, und klicken Sie dann auf **Weiter**.
  
    Die **Seite Daten in Office 365 importieren** wird mit detaillierten Dateneinblicken aus der Analyse angezeigt, die Microsoft 365 durchgeführt wurde. 
  
    ![Microsoft 365 zeigt detaillierte Dateneinblicke aus der Analyse der PST-Dateien an.](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    Das Diagramm auf dieser Seite zeigt die Datenmenge, die importiert wird. Informationen zu jedem Nachrichtentyp in den PST-Dateien werden im Diagramm angezeigt. Sie können mit dem Cursor auf jede Leiste zeigen, um bestimmte Informationen zu diesem Nachrichtentyp anzeigen zu können. Es gibt auch eine Dropdownliste mit unterschiedlichen Alterswerten, die auf der Analyse der PST-Dateien basieren. Wenn Sie ein Alter in der Dropdownliste auswählen, wird das Diagramm aktualisiert, um anzuzeigen, wie viele Daten für das ausgewählte Alter importiert werden. 
  
    b. Klicken Sie auf Weitere Filteroptionen, um Ergänzungsfilter zu konfigurieren, um die importierte **Datenmenge zu reduzieren.**
  
    ![Konfigurieren der Filter auf der Seite Weitere Optionen zum Kürzen der importierten Daten](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    Sie können die folgenden Filter konfigurieren:
  
      - **Alter** – Wählen Sie ein Alter aus, damit nur Elemente importiert werden, die höher als das angegebene Alter sind. Im Abschnitt [Weitere Informationen finden](#more-information) Sie eine Beschreibung, wie Microsoft 365 die Alterskübel für den **Altersfilter** bestimmt. 
  
      - **Typ** – Dieser Abschnitt zeigt alle Nachrichtentypen, die in den PST-Dateien für den Importauftrag gefunden wurden. Sie können ein Kontrollkästchen neben einem Nachrichtentyp deaktivieren, den Sie ausschließen möchten. Sie können den Anderen Nachrichtentyp nicht ausschließen. Im Abschnitt [Weitere Informationen finden](#more-information) Sie eine Liste der Postfachelemente, die in der Kategorie Andere enthalten sind.
  
      - **Benutzer** : Sie können Nachrichten ausschließen, die von bestimmten Personen gesendet oder empfangen werden. Klicken Sie auf Benutzer neben diesem Empfängertyp ausschließen, um Personen auszuschließen,  die im Feld Von:, An: oder im Feld Cc: von Nachrichten angezeigt werden. Geben Sie die E-Mail-Adresse (SMTP-Adresse) der Person ein, klicken Sie auf Neues Symbol hinzufügen, um sie der Liste der ausgeschlossenen Benutzer für diesen Empfängertyp hinzuzufügen, und klicken Sie dann auf Speichern, um die Liste der ausgeschlossenen Benutzer zu  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) speichern.  
  
        > [!NOTE]
        > Microsoft 365 zeigt keine Dateneinblicke an, die sich aus dem Festlegen des **Personenfilters** resulten. Wenn Sie diesen Filter jedoch so festlegen, dass Nachrichten ausgeschlossen werden, die von bestimmten Personen gesendet oder empfangen werden, werden diese Nachrichten während des tatsächlichen Importvorgangs ausgeschlossen. 
  
    c. Klicken **Sie auf** der **Fly-Out-Seite** Weitere Filteroptionen auf Übernehmen, um Die Filtereinstellungen zu speichern. 
  
    Die Dateneinblicke auf der Seite Daten in **Office 365** importieren werden basierend auf Ihren Filtereinstellungen aktualisiert, einschließlich der Gesamtmenge der Daten, die basierend auf den Filtereinstellungen importiert werden. Eine Zusammenfassung der Filtereinstellungen wird ebenfalls angezeigt. Sie können neben einem **Filter** auf Bearbeiten klicken, um die Einstellung bei Bedarf zu ändern. 
  
    ![Die Dateneinblicke werden basierend auf Ihren Filtereinstellungen aktualisiert.](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. Klicken Sie auf **Weiter**.
  
    Es wird eine Statusseite mit den Filtereinstellungen angezeigt. Auch hier können Sie alle Filtereinstellungen bearbeiten.
  
    e. Klicken **Sie auf Daten importieren,** um den Import zu starten. Die Gesamtanzahl der importierten Daten wird angezeigt. 
  
    Oder:
  
    a. Klicken **Sie auf Nein, ich möchte alles importieren,** um alle Daten in den PST-Dateien in Office 365 importieren, und klicken Sie dann auf **Weiter**.
  
    b. Klicken Sie **auf der Seite Daten Office 365** importieren auf Daten **importieren,** um den Import zu starten. Die Gesamtanzahl der importierten Daten wird angezeigt. 
  
6. Klicken Sie **auf der** Registerkarte Importieren auf **Aktualisieren** ![ aktualisieren ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) . Der Status des Importauftrags wird in der Spalte **Status** angezeigt.
  
7. Klicken Sie auf den Auftrag importieren, um ausführlichere Informationen wie den Status für jede PST-Datei und die von Ihnen konfigurierten Filtereinstellungen anzeigen zu können.

## <a name="more-information"></a>Weitere Informationen

- Wie bestimmt Microsoft 365 die Inkremente für den Altersfilter? Wenn Microsoft 365 eine PST-Datei analysiert, wird der gesendete oder empfangene Zeitstempel jedes Elements angezeigt (wenn ein Element sowohl einen gesendeten als auch einen empfangenen Zeitstempel besitzt, wird das älteste Datum ausgewählt). Anschließend Microsoft 365 den Jahreswert für diesen Zeitstempel und vergleicht ihn mit dem aktuellen Datum, um das Alter des Elements zu bestimmen. Diese Alter werden dann als Werte in der Dropdownliste für den Filter **Alter** verwendet. Wenn eine PST-Datei z. B. Nachrichten aus 2016, 2015 und 2014 enthält, sind die Werte im Filter Alter **1** Jahr, **2** Jahre und  **3 Jahre.**
  
- In der folgenden Tabelle sind die Nachrichtentypen aufgeführt, die  in der Kategorie **Andere** im Typfilter auf der Fly-Out-Seite Weitere Optionen enthalten sind (siehe Schritt 5b im vorherigen Verfahren).  Derzeit können Sie Elemente in der Kategorie "Andere" nicht ausschließen, wenn Sie PSTs in Office 365. 
  
    |**ID der Nachrichtenklasse**|**Postfachelemente, die diese Nachrichtenklasse verwenden**|
    |:-----|:-----|
    |IPM.Activity  <br/> |Journaleinträge  <br/> |
    |IPM.Document  <br/> |Dokumente und Dateien (nicht an eine E-Mail-Nachricht angefügt)  <br/> |
    |IPM. Datei  <br/> |(identisch mit IPM.DocUment)  <br/> |
    |IPM.Note.IMC.Notification  <br/> |Von Internet Mail Verbinden gesendete Berichte, das Exchange Server gateway to the Internet ist  <br/> |
    |IPM. Note.Microsoft.Fax  <br/> |Faxnachrichten  <br/> |
    |IPM. Note.Rules.Oof.Template.Microsoft  <br/> |Out-of-Office-Autoreply-Nachrichten  <br/> |
    |IPM.Note.Rules.ReplyTemplate.Microsoft  <br/> |Von einer Posteingangsregel gesendete Antworten  <br/> |
    |IPM.OLE.Class  <br/> |Ausnahmen für eine Serienserie  <br/> |
    |IPM.Recall.Report  <br/> |Berichte zum Nachrichtenrückruf  <br/> |
    |IPM.Remote  <br/> |Remote-E-Mail-Nachrichten  <br/> |
    |IPM.Report  <br/> |Artikelstatusberichte  <br/> |
