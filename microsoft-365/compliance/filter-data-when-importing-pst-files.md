---
title: Filtern von Daten beim Importieren von PST-Dateien
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
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
description: In diesem Artikel erfahren Sie, wie Sie Daten mithilfe der intelligenten Importfunktion im Office 365 Import-Dienst filtern, wenn Sie PST-Dateien in Office 365 importieren.
ms.openlocfilehash: d511c1277104a27076116fafcb4b71bc851baaca
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817724"
---
# <a name="filter-data-when-importing-pst-files"></a>Filtern von Daten beim Importieren von PST-Dateien

Verwenden Sie die neue intelligente Importfunktion im Office 365 Import-Dienst, um die Elemente in PST-Dateien zu filtern, die tatsächlich in die Zielpostfächer importiert werden. So funktioniert es:
  
- Nachdem Sie einen PST-Importauftrag erstellt und gesendet haben, werden PST-Dateien in einen Azure-Speicherbereich in der Microsoft-Cloud hochgeladen.
    
- Microsoft 365 analysiert die Daten in den PST-Dateien auf sichere und sichere Weise, indem das Alter der Postfachelemente und die unterschiedlichen Nachrichtentypen identifiziert werden, die in den PST-Dateien enthalten sind.
    
- Wenn die Analyse abgeschlossen ist und die Daten importiert werden können, können Sie alle Daten in den PST-Dateien wie folgt importieren oder die importierten Daten kürzen, indem Sie Filter festlegen, mit denen gesteuert wird, welche Daten importiert werden. Sie können beispielsweise Folgendes auswählen:
    
  - Importieren Sie nur Elemente eines bestimmten Alters.
    
  - Importiert ausgewählte Nachrichtentypen.
    
  - Ausschließen von Nachrichten, die von bestimmten Personen gesendet oder empfangen wurden.
    
- Nachdem Sie die Filtereinstellungen konfiguriert haben, importiert Microsoft 365 nur die Daten, die die Filterkriterien erfüllen, in die Zielpostfächer, die im Importauftrag angegeben sind.
    
Die folgende Grafik zeigt den intelligenten Import Vorgang und hebt die Aufgaben hervor, die Sie ausführen, sowie die Aufgaben, die von Office 365 ausgeführt werden.
  
![Der intelligente Import Vorgang in Office 365](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a>Erstellen eines PST-importauftrags

- In den Schritten in diesem Thema wird davon ausgegangen, dass Sie einen PST-Importauftrag im Office 365 Import-Dienst mithilfe des Netzwerk-Uploads oder des Laufwerk Versands erstellt haben. Eine Schritt-für-Schritt-Anleitung finden Sie unter einem der folgenden Themen:
    
  - [Verwenden des Netzwerkuploads zum Importieren von PST-Dateien in Office 365](use-network-upload-to-import-pst-files.md)
    
  - [Verwenden des Laufwerkversands zum Importieren von PST-Dateien in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- Nachdem Sie einen Importauftrag mithilfe des Netzwerk Uploads erstellt haben, wird der Status für den Importauftrag auf der Seite importieren im Security & Compliance Center auf **Analysis in Progress**festgelegt, was bedeutet, dass Microsoft 365 die Daten in den PST-Dateien analysiert, die Sie hochgeladen haben. Klicken **Sie auf Aktualisierung aktualisieren** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) , um den Status für den Importauftrag zu aktualisieren. 
    
- Für Importaufträge für den Laufwerk Versand werden die Daten von Microsoft 365 analysiert, nachdem Microsoft Datacenter-Mitarbeiter Ihre Festplatte erhalten und die PST-Dateien in den Azure-Speicherbereich für Ihre Organisation hochgeladen haben.
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>Filtern von Daten, die in Postfächer importiert werden

Nachdem Sie einen PST-Importauftrag erstellt haben, führen Sie die folgenden Schritte aus, um die Daten zu filtern, bevor Sie Sie in Office 365 importieren.
  
1. Navigieren Sie zu [https://protection.office.com/](https://protection.office.com/), und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an. 
    
2. Klicken Sie auf **Information Governance** \> **Import** \> **Import PST Files**.
    
    Die Importaufträge für Ihre Organisation werden auf der Seite **PST-Dateien importieren** aufgeführt. Beachten Sie, dass der Wert **Analyse abgeschlossen** in der Spalte **Status** die Importaufträge angibt, die von Microsoft 365 analysiert wurden und für den Import bereit sind. 
    
    ![Analysis Complete Status gibt an, dass Microsoft 365 die Daten in PST-Dateien analysiert hat.](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. Klicken Sie auf **Ready to Import to Office 365** für den Importauftrag, den Sie abschließen möchten. 
    
    Nun wird eine Flyout-Seite mit Informationen zu den PST-Dateien und anderen Informationen zur Importaufgabe angezeigt.
    
4. Klicken Sie auf **Importieren in Office 365**.
    
    Die Seite **Ihre Daten filtern** wird angezeigt. Sie enthält Daten Einblicke in die Daten in den PST-Dateien für den Importauftrag, einschließlich Informationen zum Alter der Daten. 
    
    ![Auf der Seite Daten filtern werden Daten Einblicke in die PST-Dateien für den Importauftrag angezeigt.](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. Je nachdem, ob Sie die Daten, die in Microsoft 365 importiert wurden, kürzen möchten, führen **Sie unter möchten Sie Ihre Daten filtern**aus einen der folgenden Schritte aus:
    
    a. Klicken Sie auf **Ja, ich möchte ihn vor dem Importieren Filtern** , um die importierten Daten zu trimmen, und klicken Sie dann auf **weiter**.
    
    Die Seite **Daten in Office 365 Seite importieren** wird mit detaillierten Daten Einblicken aus der Analyse angezeigt, die von Microsoft 365 ausgeführt wurde. 
    
    ![Microsoft 365 zeigt detaillierte Daten Einblicke aus der Analyse der PST-Dateien an.](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    Im Diagramm auf dieser Seite wird die Menge der Daten angezeigt, die importiert werden. Informationen zu den einzelnen Nachrichtentypen, die in den PST-Dateien gefunden werden, werden im Diagramm angezeigt. Sie können den Mauszeiger über die einzelnen Balken bewegen, um bestimmte Informationen zu diesem Nachrichtentyp anzuzeigen. Es gibt auch eine Dropdownliste mit unterschiedlichen Alters Werten, die auf der Analyse der PST-Dateien basiert. Wenn Sie in der Dropdownliste ein Alter auswählen, wird das Diagramm so aktualisiert, dass angezeigt wird, wie viele Daten für das ausgewählte Alter importiert werden. 
    
    b. Klicken Sie auf **Weitere Filteroptionen**, um zusätzliche Filter zu konfigurieren, um die Menge der importierten Daten zu reduzieren.
    
    ![Konfigurieren Sie die Filter auf der Seite Weitere Optionen, um die importierten Daten zu kürzen.](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    Sie können diese Filter konfigurieren:
    
      - **Alter** – wählen Sie ein Alter aus, sodass nur Elemente importiert werden, die jünger als das angegebene Alter sind. Im Abschnitt [Weitere Informationen](#more-information) finden Sie eine Beschreibung dazu, wie Microsoft 365 die Alters Eimer für den **Alters** Filter ermittelt. 
    
      - **Type** – in diesem Abschnitt werden alle Nachrichtentypen angezeigt, die in den PST-Dateien für den Importauftrag gefunden wurden. Sie können ein Kontrollkästchen neben einem Nachrichtentyp deaktivieren, den Sie ausschließen möchten. Beachten Sie, dass Sie den anderen Nachrichtentyp nicht ausschließen können. Im Abschnitt [Weitere Informationen](#more-information) finden Sie eine Liste der Postfachelemente, die in der anderen Kategorie enthalten sind. 
    
      - **Benutzer** – Sie können Nachrichten ausschließen, die von bestimmten Personen gesendet oder empfangen werden. Wenn Sie Personen ausschließen möchten, die im Feld von: Feld, an: oder im Feld CC: von Nachrichten angezeigt werden, klicken Sie neben diesem Empfängertyp auf **Benutzer ausschließen** . Geben Sie die e-Mail-Adresse (SMTP-Adresse) der Person ein, klicken Sie auf neues Symbol **Hinzufügen**, um ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) Sie der Liste der ausgeschlossenen Benutzer dieses Empfängertyps hinzuzufügen, und klicken Sie dann auf **Speichern** , um die Liste der ausgeschlossenen Benutzer zu speichern. 
    
        > [!NOTE]
        > In Microsoft 365 werden keine Daten Einblicke angezeigt, die sich aus dem Festlegen des **Personen** Filters ergeben. Wenn Sie diesen Filter jedoch so festlegen, dass Nachrichten, die von bestimmten Personen gesendet oder empfangen werden, ausgeschlossen werden, werden diese Nachrichten während des tatsächlichen Importvorgangs ausgeschlossen. 
  
    c. Klicken Sie auf der Seite **Weitere Filteroptionen** auf über **nehmen** , um die Filtereinstellungen zu speichern. 
    
    Die Daten Insights auf der Seite **Daten in Office 365 importieren** werden basierend auf Ihren Filtereinstellungen aktualisiert, einschließlich der Gesamtmenge der Daten, die basierend auf den Filtereinstellungen importiert werden. Beachten Sie, dass auch eine Zusammenfassung der Filtereinstellungen angezeigt wird. Sie können neben einem Filter auf **Bearbeiten** klicken, um die Einstellung bei Bedarf zu ändern. 
    
    ![Die Daten Einblicke werden basierend auf Ihren Filtereinstellungen aktualisiert.](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. Klicken Sie auf **Weiter**.
    
    Eine Statusseite mit den Filtereinstellungen wird angezeigt. Sie können auch eine beliebige Filtereinstellung bearbeiten.
    
    e. Klicken Sie auf **Daten importieren** , um den Import zu starten. Beachten Sie, dass die Gesamtmenge der importierten Daten angezeigt wird. 
    
    Oder
    
    a. Klicken Sie auf **Nein, ich möchte alles importieren** , um alle Daten in die PST-Dateien in Office 365 zu importieren, und klicken Sie dann auf **weiter**.
    
    b. Klicken Sie auf der Seite **Daten in Office 365 importieren** auf **Daten importieren** , um den Import zu starten. Beachten Sie, dass die Gesamtmenge der importierten Daten angezeigt wird. 
    
6. Klicken Sie auf der Seite **PST-Dateien importieren** **auf Aktualisierung aktualisieren** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) . Der Status des importauftrags wird in der Spalte **Status** angezeigt. 
    
7. Klicken Sie auf den Auftrag importieren, um detailliertere Informationen anzuzeigen, beispielsweise den Status für jede PST-Datei und die von Ihnen konfigurierten Filtereinstellungen.

  
## <a name="more-information"></a>Weitere Informationen

- Wie ermittelt Microsoft 365 die Inkremente für den Altersfilter? Wenn Microsoft 365 eine PST-Datei analysiert, sieht es den gesendeten oder empfangenen Zeitstempel jedes Elements an (wenn ein Element über einen gesendeten und empfangenen Zeitstempel verfügt, wird das älteste Datum ausgewählt). Anschließend sucht Microsoft 365 den Jahreswert für diesen Zeitstempel und vergleicht ihn mit dem aktuellen Datum, um das Alter des Elements zu bestimmen. Diese Altersgruppen werden dann als Werte in der Dropdownliste für den **Alters** Filter verwendet. Wenn beispielsweise eine PST-Datei Nachrichten von 2016, 2015 und 2014 enthält, sind die Werte im **Alters** Filter **1 Jahr**, **2 Jahre**und **3 Jahre**.
    
- In der folgenden Tabelle sind die Nachrichtentypen aufgeführt, die in der Kategorie " **andere** " im Feld " **Typ** " auf der Seite " **Weitere Optionen** ausfliegen" enthalten sind (siehe Schritt 5B im vorherigen Verfahren). Derzeit können Sie keine Elemente in der Kategorie "Others" ausschließen, wenn Sie PST in Office 365 importieren. 
    
    |**ID der Nachrichtenklasse**|**Postfachelemente, die diese Nachrichtenklasse verwenden**|
    |:-----|:-----|
    |IPM.Activity  <br/> |Journaleinträge  <br/> |
    |IPM.Document  <br/> |Dokumente und Dateien (nicht an eine e-Mail-Nachricht angefügt)  <br/> |
    |IPM. Datei  <br/> |(identisch mit IPM.Document)  <br/> |
    |IPM.Note.IMC.Notification  <br/> |Von Internet Mail Connect gesendete Berichte, die Exchange Server Gateway zum Internet  <br/> |
    |IPM. Hinweis. Microsoft. Fax  <br/> |Faxnachrichten  <br/> |
    |IPM. Note. Rules. OOF. Template. Microsoft  <br/> |Abwesenheitsnachrichten, die automatisch beantwortet werden  <br/> |
    |IPM.Note.Rules.ReplyTemplate.Microsoft  <br/> |Von einer Posteingangsregel gesendete Antworten  <br/> |
    |IPM.OLE.Class  <br/> |Ausnahmen für eine wiederkehrende Reihe  <br/> |
    |IPM.Recall.Report  <br/> |Berichte zum Nachrichtenrückruf  <br/> |
    |IPM.Remote  <br/> |Remote-e-Mail-Nachrichten  <br/> |
    |IPM.Report  <br/> |Elementstatus Berichte  <br/> |
