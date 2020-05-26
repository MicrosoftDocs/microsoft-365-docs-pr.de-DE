---
title: Informationen zu Aufbewahrungsbezeichnungen
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie mithilfe von Aufbewahrungsbezeichnungen Daten organisationsweit für die Governance klassifizieren und Aufbewahrungsregeln basierend auf dieser Klassifizierung durchsetzen können. Sie können Aufbewahrungsbezeichnungen auch verwenden, um eine Lösung zur Datensatzverwaltung für Microsoft 365 zu implementieren.
ms.openlocfilehash: 54691f996f1b2e0759c4d8758df0044a32b9ffa9
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327903"
---
# <a name="learn-about-retention-labels"></a>Informationen zu Aufbewahrungsbezeichnungen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

In Ihrer Organisation verwenden Sie wahrscheinlich verschiedene Arten von Inhalten, für die unterschiedliche Aktionen ausgeführt werden müssen, um branchenspezifische Vorschriften und interne Richtlinien einzuhalten. Dies kann zum Beispiel die folgenden Inhalte umfassen:
  
- Steuerformulare, die für einen bestimmten Zeitraum **aufbewahrt** werden müssen. 
    
- Pressematerialien, die nach dem Erreichen eines bestimmten Alters **dauerhaft gelöscht** werden müssen. 
    
- Im Wettbewerb stehende Forschungen, die sowohl **aufbewahrt** als auch anschließend **dauerhaft gelöscht** werden müssen. 
    
- Arbeitsvisa, die **als Datensatz gekennzeichnet** werden müssen, damit sie nicht bearbeitet oder gelöscht werden. 
    
In all diesen Fällen können Aufbewahrungsbezeichnungen Ihnen dabei helfen, die richtigen Maßnahmen für die entsprechenden Inhalte zu treffen. Mit Aufbewahrungsbezeichnungen können Sie Daten organisationsweit für Governance klassifizieren und Aufbewahrungsregeln basierend auf dieser Klassifizierung durchsetzen.
  
Mit Aufbewahrungsbezeichnungen können Sie Folgendes:
  
- **Es Personen in Ihrer Organisation ermöglichen, eine Aufbewahrungsbezeichnung manuell** auf einen Inhalt in Outlook im Web, Outlook 2010 und höher, OneDrive, SharePoint und Microsoft 365-Gruppen anzuwenden. Benutzer wissen oft am besten, mit welcher Art von Inhalt sie arbeiten. Deshalb können sie den Inhalt klassifizieren und die entsprechende Richtlinie darauf anwenden lassen. 
    
- **Sie können Aufbewahrungsbezeichnungen automatisch** auf Inhalt anwenden, wenn er bestimmten Bedingungen entspricht: 
    
    - Der Inhalt enthält bestimmte vertrauliche Informationen.
    
    - Der Inhalt enthält bestimmte Stichwörter, die einer von Ihnen erstellten Abfrage entsprechen.
    
    - Musterübereinstimmungen für eine trainierbare Klassifizierung.
    
  Die Möglichkeit, Aufbewahrungsbezeichnungen automatisch auf Inhalte anzuwenden, ist aus den folgenden Gründen wichtig:
    
     - Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.
    
     - Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.
    
   - Benutzer müssen nicht mehr über Governance-Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.

- **Wenden Sie eine Standardaufbewahrungsbezeichnung auf eine Dokumentbibliothek, einen Ordner oder eine Dokumentenmappe** in SharePoint an, sodass alle an diesem Speicherort gespeicherten Dokumente mit der Standardaufbewahrungsbezeichnung versehen werden.

Aufbewahrungsbezeichnungen unterstützen darüber hinaus die [Datensatzverwaltung](records-management.md) für E-Mails und Dokumente in Microsoft 365-Apps und -Diensten. Sie können Aufbewahrungsbezeichnungen verwenden, um Inhalte als Datensätze zu kennzeichnen. Wenn dies geschieht, kann die Bezeichnung nicht geändert oder entfernt und die Inhalte können nicht bearbeitet oder gelöscht werden. 

Für die Anzahl der Aufbewahrungsbezeichnungen, die für einen Mandanten unterstützt werden, gibt es keine Beschränkung. Es werden jedoch maximal 10.000 Richtlinien für einen Mandanten unterstützt. Dazu gehören die Richtlinien, mit denen die Bezeichnungen angewendet werden (Aufbewahrungsbezeichnungsrichtlinien und automatische Aufbewahrungsrichtlinien), sowie Aufbewahrungsrichtlinien.

## <a name="how-retention-labels-work-with-retention-label-policies"></a>Funktionsweise von Aufbewahrungsbezeichnungen bei Aufbewahrungsbezeichnungsrichtlinien

Der Vorgang, mit dem Personen in Ihrer Organisation Aufbewahrungsbezeichnungen zur Verfügung gestellt werden, damit sie Inhalte klassifizieren können, besteht aus zwei Schritten: 

1. Erstellen der Aufbewahrungsbezeichnungen

2. Veröffentlichen der Aufbewahrungsbezeichnungen mithilfe einer Aufbewahrungsbezeichnungsrichtlinie
  
![Diagramm der Rollen und Aufgaben für Bezeichnungen](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
Aufbewahrungsbezeichnungen sind unabhängige, wiederverwendbare Bausteine, die in einer oder mehreren Aufbewahrungsbezeichnungsrichtlinien enthalten sind. Der Hauptzweck der Aufbewahrungsbezeichnungsrichtlinie besteht darin, eine Reihe von Aufbewahrungsbezeichnungen zu gruppieren und die Orte anzugeben, an denen die Bezeichnungen angezeigt werden sollen.
  
![Diagramm der Bezeichnungen, Bezeichnungsrichtlinien und Speicherorte](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. Wenn Sie Aufbewahrungsbezeichnungen veröffentlichen, werden sie in eine Aufbewahrungsbezeichnungsrichtlinie einbezogen. Die Namen von Aufbewahrungsbezeichnungen sind unveränderlich, das bedeutet, sie können nach ihrer Erstellung nicht mehr bearbeitet werden.

2. Eine einzelne Aufbewahrungsbezeichnung kann in mehrere Aufbewahrungsbezeichnungsrichtlinien einbezogen werden.

3. Ein einzelner Ort kann auch in viele Aufbewahrungsbezeichnungsrichtlinien einbezogen werden.
    
3. Aufbewahrungsbezeichnungsrichtlinien geben die Speicherorte zum Veröffentlichen der Aufbewahrungsbezeichnungen an.
    
## <a name="only-one-retention-label-at-a-time"></a>Jeweils nur eine Aufbewahrungsbezeichnung

Es ist wichtig zu wissen, dass ein Inhalt wie eine E-Mail-Nachricht oder ein Dokument jeweils nur über eine Aufbewahrungsbezeichnung verfügen kann:
  
- Aufbewahrungsbezeichnungen, die von den Endbenutzern manuell zugewiesen wurden, können entfernt oder geändert werden.
    
- Wenn eine Bezeichnung einem Inhalt automatisch zugewiesen wurde, kann diese automatisch zugewiesene Aufbewahrungsbezeichnung durch eine vom Endbenutzer manuell zugewiesene Bezeichnung ersetzt werden.
    
- Wenn einem Inhalt eine Aufbewahrungsbezeichnung manuell von einem Endbenutzer zugewiesen wurde, kann diese manuell zugewiesene Aufbewahrungsbezeichnung nicht durch eine automatisch zugewiesene Bezeichnung ersetzt werden.
    
- Wenn es mehrere Regeln gibt, durch die eine Bezeichnung automatisch zugewiesen wird, und ein Inhalt die Bedingungen verschiedener Regeln erfüllt, wird die Aufbewahrungsbezeichnung für die älteste Regel angewendet.
    
Um zu verstehen, wie und warum eine Aufbewahrungsbezeichnung und nicht eine andere angewendet wird, ist es hilfreich, den Unterschied zwischen der expliziten und der impliziten Zuweisung einer Bezeichnung nachzuvollziehen:

- Manuell zugewiesene Bezeichnungen sind explizit zugewiesen.
- Automatisch angewendete Bezeichnungen sind implizit zugewiesen.

Eine explizit zugewiesene Aufbewahrungsbezeichnung hat Vorrang vor einer implizit zugewiesenen. Weitere Informationen finden Sie im Abschnitt [Die Grundsätze der Aufbewahrung, oder was hat Vorrang?](#the-principles-of-retention-or-what-takes-precedence) auf dieser Seite.

In den Ergebnissen zeigt die Eigenschaft `ELCLastSuccessTimeStamp` (UTC), wann das System zuletzt Ihr Postfach verarbeitet hat. Wenn dies seit dem Zeitpunkt der Richtlinienerstellung nicht geschehen ist, werden die Bezeichnungen nicht angezeigt. Um die Verarbeitung zu erzwingen, führen Sie `Start-ManagedFolderAssistant -Identity <user>` aus.
    
Wenn die Bezeichnungen nicht in Outlook im Web angezeigt werden und Sie denken, dass sie angezeigt werden sollten, müssen Sie den Cache des Browsers leeren (STRG + F5).
    
## <a name="retention-label-policies-and-locations"></a>Aufbewahrungsbezeichnungsrichtlinien und Speicherorte

Verschiedene Arten von Aufbewahrungsbezeichnungen können an verschiedenen Speicherorten veröffentlicht werden, je nach Funktion der Aufbewahrungsbezeichnung.
  
|**Wenn für die Aufbewahrungsbezeichnung Folgendes gilt:**|**So kann die Bezeichnungsrichtlinie angewendet werden auf...**|
|:-----|:-----|
|für Endbenutzer veröffentlicht  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365-Gruppen  <br/> |
|basierend auf Typen vertraulicher Informationen automatisch angewendet  <br/> |Exchange (nur alle Postfächer), SharePoint, OneDrive  <br/> |
|basieren auf einer Abfrage automatisch angewendet  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365-Gruppen  <br/> |
   
In Exchange werden automatisch angewendete Bezeichnungen (sowohl für Abfragen als auch für vertrauliche Informationstypen) nur auf neu gesendete Nachrichten (in Übertragung begriffene Daten) angewendet, und nicht auf alle Elemente, die sich derzeit im Postfach befinden (ruhende Daten). Außerdem können automatisch angewendete Aufbewahrungsbezeichnungen für vertrauliche Informationstypen nur auf alle Postfächer angewendet werden; Sie können keine bestimmten Postfächer dafür auswählen.
  
Öffentliche Ordner in Exchange und Skype unterstützen keine Aufbewahrungsbezeichnungen.

## <a name="how-retention-labels-enforce-retention"></a>So erzwingen Aufbewahrungsbezeichnungen die Aufbewahrung

Aufbewahrungsbezeichnungen können die gleichen Aufbewahrungsaktionen wie eine Aufbewahrungsrichtlinie erzwingen: aufbewahren und dann löschen, nur aufbewahren oder nur löschen. Mithilfe von Aufbewahrungsbezeichnungen können Sie einen komplexen Inhaltsplan (oder Dateiplan) implementieren. Näheres über die Aufbewahrung erfahren Sie unter [Informationen zu Aufbewahrungsrichtlinien](retention-policies.md).
  
Darüber hinaus hat eine Aufbewahrungsbezeichnung zwei Aufbewahrungsoptionen, die nur für eine Aufbewahrungsbezeichnung und nicht in einer Aufbewahrungsrichtlinie verfügbar sind. Aufbewahrungsbezeichnungen bieten Ihnen die folgenden Möglichkeiten:
  
- Auslösen einer Löschungsprüfung am Ende des Aufbewahrungszeitraums, damit SharePoint- und OneDrive-Dokumente überprüft werden müssen, bevor sie gelöscht werden können. Weitere Informationen finden Sie unter [Löschungsprüfungen](disposition.md#disposition-reviews).
    
- Beginnen des Aufbewahrungszeitraums zu dem Zeitpunkt, an dem der Inhalt mit der Bezeichnung versehen wurde, und nicht ausgehend vom Alter des Inhalts oder dem Zeitpunkt, zu dem er zuletzt geändert wurde. Diese Option gilt nur für Inhalte auf SharePoint-Websites und in OneDrive-Konten. Bei Exchange-E-Mails basiert der Aufbewahrungszeitraum immer auf dem Datum, an dem die Nachricht gesendet oder empfangen wurde, und zwar unabhängig davon, welche Option Sie hier auswählen.
    
![Aufbewahrungseinstellungen mit Optionen speziell für Bezeichnungen](../media/c49118c9-6279-4661-94db-deffa76e27ac.png)

## <a name="where-published-retention-labels-can-appear-to-end-users"></a>Wo veröffentlichte Aufbewahrungsbezeichnungen Endbenutzern verfügbar gemacht werden können

Wenn Endbenutzer Aufbewahrungsbezeichnungen auf Inhalte anwenden, können Sie die Bezeichnungen an den folgenden Speicherorten veröffentlichen:
  
- Outlook und Outlook im Web
    
- OneDrive
    
- SharePoint
    
- Microsoft 365-Gruppen (sowohl die Gruppenwebsite als auch das Gruppenpostfach in Outlook im Web)
    
In den folgenden Abschnitten wird erläutert, wie Bezeichnungen den Endbenutzern in Ihrer Organisation in verschiedenen Apps angezeigt werden.
  

### <a name="outlook"></a>Outlook

Wenn Sie ein Element im Outlook-Desktop-Client beschriften möchten, wählen Sie es zunächst aus. Klicken Sie im Menüband auf der Registerkarte **Start** auf **Richtlinie zuweisen**, und wählen Sie dann die gewünschte Aufbewahrungsbezeichnung aus. 
  
![Schaltfläche „Richtlinie zuweisen“](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
Sie können auch mit der rechten Maustaste auf ein Element klicken, im Kontextmenü auf **Richtlinie zuweisen** klicken, und dann die gewünschte Aufbewahrungsbezeichnung auswählen. 

Nachdem die Aufbewahrungsbezeichnung angewendet wurde, können Sie sie zusammen mit der von ihr ausgeführten Aktion über dem Element anzeigen. Wenn einer E-Mail eine Aufbewahrungsbezeichnung und damit verbunden ein Aufbewahrungszeitraum zugeordnet wurde, können Sie auf einen Blick sehen, wann die E-Mail abläuft.
  
Sie können Aufbewahrungsbezeichnungen auch auf Ordner anwenden. Hierbei gilt Folgendes:
  
- Alle Elemente im Ordner erhalten automatisch dieselbe Aufbewahrungsbezeichnung, **mit Ausnahme von Elementen**, auf die eine Aufbewahrungsbezeichnung explizit angewendet wurde. Explizit bezeichnete Elemente behalten die bestehende Aufbewahrungsbezeichnung bei. Weitere Informationen finden Sie im Abschnitt [Die Grundsätze der Aufbewahrung, oder was hat Vorrang?](#the-principles-of-retention-or-what-takes-precedence) auf dieser Seite. 
    
- Wenn Sie die Standardaufbewahrungsbezeichnung eines Ordners ändern oder entfernen, wird die Aufbewahrungsbezeichnung ebenfalls für alle Elemente in dem Ordner geändert oder entfernt, **mit Ausnahme von** Elementen, die über explizit zugewiesene Aufbewahrungsbezeichnungen verfügen. 
    
- Wenn Sie ein Element mit einer Standardaufbewahrungsbezeichnung von einem Ordner in einen anderen Ordner mit einer anderen Standardaufbewahrungsbezeichnung verschieben, erhält das Element die neue Standardaufbewahrungsbezeichnung.
    
- Wenn Sie ein Element mit einer Standardaufbewahrungsbezeichnung von einem Ordner in einen anderen Ordner ohne Standardaufbewahrungsbezeichnung verschieben, wird die alte Standardaufbewahrungsbezeichnung entfernt.

### <a name="outlook-on-the-web"></a>Outlook im Web

Um ein Element in Outlook im Web mit einer Bezeichnung zu versehen: Mit der rechten Maustaste auf das Element klicken \> **Richtlinie zuweisen** \> Aufbewahrungsbezeichnung auswählen. 
  
![Menü „Richtlinie zuweisen“ in Outlook im Web](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
Nachdem die Aufbewahrungsbezeichnung zugewiesen wurde, können Sie oben im Element diese Aufbewahrungsbezeichnung anzeigen und sehen, welche Aktion sie durchführt. Wenn eine E-Mail klassifiziert ist, der ein Aufbewahrungszeitraum zugeordnet wurde, sehen Sie auf einen Blick, wann die E-Mail abläuft.
  
![Bezeichnung, die einer E-Mail in Outlook im Web zugewiesen wurde](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
Wie bei Outlook im Web können Sie Aufbewahrungsbezeichnungen auch auf Ordner anwenden. 

### <a name="onedrive-and-sharepoint"></a>OneDrive und SharePoint

Um in OneDrive oder SharePoint ein Dokument mit einer Bezeichnung zu versehen (einschließlich OneNote-Dateien), wählen Sie das entsprechende Element \> in der oberen rechten Ecke aus, wählen Sie **Detailfenster öffnen**![Symbol des Informationsbereichs](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Aufbewahrungsbezeichnung anwenden** \> Aufbewahrungsbezeichnung auswählen. 
  
Sie können eine Aufbewahrungsbezeichnung auch auf einen Ordner- oder Dokumentensatz anwenden sowie eine [Standardaufbewahrungsbezeichnung für eine Dokumentbibliothek](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) festlegen.
  
![Bezeichnungsliste auf ein Element in SharePoint anwenden](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
Nachdem eine Aufbewahrungsbezeichnung auf ein Element angewendet wurde, wird sie im Detailbereich angezeigt, wenn das Element ausgewählt wird.
  
![Angewendete Bezeichnung im Detailbereich](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
Für SharePoint, aber nicht OneDrive, können Sie eine Bibliotheksansicht erstellen, die die Spalten **Bezeichnungen** oder **Element ist ein Datensatz** enthält. In dieser Ansicht sehen Sie auf einen Blick die Aufbewahrungsbezeichnungen, die allen Elementen zugeordnet sind, und bei welchen Elementen es sich um Datensätze handelt. Beachten Sie jedoch, dass Sie die Ansicht nicht nach der Spalte **Element ist ein Datensatz** filtern können. Anweisungen zum Hinzufügen von Spalten finden Sie unter [Ein- oder Ausblenden von Spalten in einer Liste oder Bibliothek](https://support.microsoft.com/de-DE/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2).
  

### <a name="microsoft-365-groups"></a>Microsoft 365-Gruppen

Wenn Sie Aufbewahrungsbezeichnungen für Microsoft 365-Gruppen ([vormals Office 365-Gruppen](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) veröffentlichen, werden diese sowohl auf der Gruppen-Website als auch im Gruppenpostfach in Outlook im Web angezeigt. Die Vorgehensweise zum Anwenden einer Aufbewahrungsbezeichnung auf Inhalte ist mit der für E-Mails und Dokumente identisch.

Wenn Sie Inhalte für eine Microsoft 365-Gruppe aufbewahren möchten, verwenden Sie den **Office 365-Gruppen**-Speicherort. Obwohl eine Microsoft 365-Gruppe über ein Exchange-Postfach verfügt, bezieht eine Aufbewahrungsrichtlinie, die den gesamten Exchange-Speicherort umfasst, keine Inhalte in Microsoft 365-Gruppenpostfächern mit ein.

Außerdem ist es nicht möglich, den Exchange-Speicherort für den Ein- oder Ausschluss eines bestimmten Gruppenpostfachs zu verwenden. Obwohl der Exchange-Speicherort zunächst die Auswahl eines Gruppenpostfachs zulässt, erhalten Sie beim Versuch, die Aufbewahrungsrichtlinie zu speichern, die Fehlermeldung, dass "RemoteGroupMailbox" keine gültige Auswahl für den Exchange-Speicherort ist.
  
Erstellen und konfigurieren Sie zunächst die Vertraulichkeitsbezeichnungen, die Sie für Apps und andere Dienste zur Verfügung stellen möchten, zum Beispiel die Bezeichnungen, die Benutzer in Office-Apps sehen und anwenden sollen. 

Erstellen Sie dann eine oder mehrere Bezeichnungsrichtlinien mit den von Ihnen konfigurierten Bezeichnungen und Richtlinieneinstellungen. Es ist die Bezeichnungsrichtlinie, die die Bezeichnungen und Einstellungen für die von Ihnen ausgewählten Benutzer und Standorte veröffentlicht.

## <a name="applying-a-retention-label-automatically-based-on-conditions"></a>Automatisches Zuweisen einer Aufbewahrungsbezeichnung basierend auf Bedingungen

Eines der leistungsstärksten Features von Aufbewahrungsbezeichnungen ist die Möglichkeit, sie automatisch auf Inhalte anzuwenden, die bestimmte Bedingungen erfüllen. In diesem Fall müssen die Personen in Ihrer Organisation die Bezeichnungen nicht selber anwenden. Das wird von Microsoft 365 erledigt.
  
![Diagramm der Rollen und Aufgaben für automatisch angewendete Bezeichnungen](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
Das automatische Anwenden von Aufbewahrungsbezeichnungen ist aus den folgenden Gründen besonders effektiv:
  
- Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.
    
- Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.
    
- Benutzer müssen nicht mehr über Governance-Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.
    
Sie können Aufbewahrungsbezeichnungen automatisch auf Inhalte anwenden, wenn diese folgende Bedingungen erfüllen:
  
- [Der Inhalt enthält bestimmte vertrauliche Informationen.](create-retention-labels.md#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [Der Inhalt enthält bestimmte Stichwörter, die einer von Ihnen erstellten Abfrage entsprechen.](create-retention-labels.md#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [Eine Übereinstimmung für trainierbare Klassifizierungen](create-retention-labels.md#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![Seite "Bedingung auswählen" für automatisch angewendete Bezeichnungen](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

> [!TIP]
> Unter [Verwalten des Lebenszyklus von SharePoint-Dokumenten mithilfe von Aufbewahrungsbezeichnungen](auto-apply-retention-labels-scenario.md)finden Sie ein detailliertes Szenario zur Verwendung von verwalteten Eigenschaften in SharePoint, um Aufbewahrungsbezeichnungen automatisch anzuwenden und die ereignisgesteuerte Aufbewahrung zu implementieren.

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a>Anwenden einer Standardaufbewahrungsbezeichnung auf alle Inhalte in einer SharePoint-Bibliothek, einem Ordner oder einer Dokumentenmappe

Sie können es Personen nicht nur ermöglichen, eine Aufbewahrungsbezeichnung auf einzelne Dokumente anzuwenden, sondern Sie können eine Standardaufbewahrungsbezeichnung auf eine SharePoint-Bibliothek, einen Ordner oder eine Dokumentenmappe anwenden, sodass alle Dokumente in diesem Speicherort diese Standardaufbewahrungsbezeichnung erhalten.
  
Bei einer Dokumentbibliothek geschieht das auf der Seite **Bibliothekseinstellungen**. Wenn Sie die standardmäßige Aufbewahrungsbezeichnung auswählen, können Sie auch auswählen, dass sie auf vorhandene Elemente in der Bibliothek angewendet werden soll. 
  
Wenn Sie zum Beispiel über ein Tag für Marketingmaterial verfügen und wissen, dass eine bestimmte Dokumentenbibliothek nur diese Art von Inhalt enthält, können Sie das Marketingmaterial-Tag als Standard für alle Dokumente in dieser Bibliothek festlegen.
  
![Option „Bezeichnung anwenden“ auf der Seite mit den Bibliothekeinstellungen](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
Wenn Sie eine Standardaufbewahrungsbezeichnung auf vorhandene Elemente in der Bibliothek, im Ordner oder in der Dokumentenmappe anwenden:
  
- Alle Elemente in der Bibliothek, dem Ordner oder der Dokumentenmappe erhalten automatisch dieselbe Aufbewahrungsbezeichnung, **mit Ausnahme von Elementen**, auf die eine Aufbewahrungsbezeichnung explizit angewendet wurde (z. B. Datensätze). Explizit bezeichnete Elemente behalten diese Bezeichnung bei. Weitere Informationen finden Sie weiter unten im Abschnitt [Die Grundsätze der Aufbewahrung, oder was hat Vorrang?](#the-principles-of-retention-or-what-takes-precedence)
    
- Wenn Sie die Standardaufbewahrungsbezeichnung einer Bibliothek, eines Ordners oder einer Dokumentenmappe ändern oder entfernen, wird die Aufbewahrungsbezeichnung ebenfalls für alle Elemente in der Bibliothek, im Ordner oder in der Dokumentenmappe geändert oder entfernt, **mit Ausnahme von** Elementen, die über explizit zugewiesene Aufbewahrungsbezeichnungen verfügen (z. B. Datensätze).
    
- Wenn Sie ein Element mit einer Standardaufbewahrungsbezeichnung aus einer Sitesammlung, Bibliothek, einem Ordner oder einer Dokumentenmappe in eine andere Sitesammlung, Bibliothek, einen Ordner oder eine Dokumentenmappe verschieben, behält das Element die vorhandene Standardaufbewahrungsbezeichnung auch dann, wenn der neue Speicherort eine andere Standardaufbewahrungsbezeichnung hat. Wenn das Element vor dem Verschieben nicht mit einer Bezeichnung versehen ist, nimmt es die Standardaufbewahrungsbezeichnung des neuen Speicherorts an.

**Einträge:** Wenn Sie eine Standarddatensatzbezeichnung auf eine Bibliothek, einen Ordner oder eine Dokumentenmappe anwenden, wird eine Datensatzbezeichnung auf jedes einzelne Element innerhalb dieser Speicherorte angewendet. Wenn Sie ein neues Element an einen Speicherort mit einer Datensatzbezeichnung verschieben, erhält dieses Element eine Bezeichnung als Datensatz. Wenn Sie die Standardaufbewahrungsbezeichnung jedoch in eine Bezeichnung ändern, die Inhalt nicht als Datensatz deklariert, wird die Datensatzbezeichnung durch diese Aktion nicht von den einzelnen Elementen entfernt, und die einzelnen Elemente behalten ihre Datensatzbezeichnung. Nur ein Websitesammlungsadministrator kann die Aufbewahrungsbezeichnung von Datensatzelementen explizit entfernen oder ändern.

Weitere Informationen zu Aufbewahrungsbezeichnungen, die Inhalte als Datensatz deklarieren, finden Sie unter [Informationen zu Datensätzen](records.md).

## <a name="applying-a-retention-label-to-email-by-using-rules"></a>Anwenden einer Aufbewahrungsbezeichnung auf E-Mails mithilfe von Regeln

In Outlook können Sie Regeln zum Anwenden einer Aufbewahrungsbezeichnung oder Aufbewahrungsrichtlinie erstellen.
  
Sie können zum Beispiel eine Regel erstellen, die eine bestimmte Aufbewahrungsbezeichnung auf alle Nachrichten anwendet, die an eine oder von einer bestimmten Verteilergruppe gesendet werden.
  
So erstellen Sie eine Regel: Rechtsklick auf ein Element \> **Regeln** \> **Regel erstellen** \> **Erweiterte Optionen** \> **Regel-Assistent** \> **Aufbewahrungsrichtlinie anwenden**.
  
![Regel-Assistent mit Option zum Anwenden von Aufbewahrungsrichtlinien](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a>Klassifizieren von Inhalten ohne Anwendung von Aktionen

Sie können eine Aufbewahrungsbezeichnung erstellen, ohne eine Aufbewahrungsaktion oder sonstige Aktionen aktivieren zu müssen. In diesem Fall können Sie eine Aufbewahrungsbezeichnung einfach als Beschriftung verwenden, ohne irgendwelche Aktionen zu erzwingen.
  
Sie können beispielsweise die Aufbewahrungsbezeichnung „Später überprüfen“ ohne Aktionen erstellen und diese Aufbewahrungsbezeichnung dann automatisch auf Inhalte mit vertraulichen Informationen oder auf abgefragte Inhalte anwenden.
  
![Seite „Bezeichnungseinstellungen“ mit deaktivierter Aufbewahrung](../media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-retention-labels-for-records-management"></a>Verwenden von Aufbewahrungsbezeichnungen für die Datensatzverwaltung
    
Sie können Aufbewahrungsbezeichnungen verwenden, um Inhalte als Datensätze zu klassifizieren. Auf diese Weise können Sie eine einzige, einheitliche Strategie zur Datensatzverwaltung in Microsoft 365 einrichten. Weitere Informationen finden Sie unter [Übersicht über Datensätze](records.md).
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>Verwenden einer Aufbewahrungsbezeichnung als Bedingung in einer DLP-Richtlinie

Eine Aufbewahrungsbezeichnung kann Aufbewahrungsaktionen für Inhalte erzwingen. Darüber hinaus können Sie eine Aufbewahrungsbezeichnung als Bedingung in einer Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) verwenden. Dies bedeutet, dass die DLP-Richtlinie weitere Aktionen für Inhalte, die eine bestimmte Bezeichnung haben, erzwingen kann, wie zum Beispiel das Einschränken des Zugriffs. 
  
Weitere Informationen finden Sie unter [Verwenden einer Aufbewahrungsbezeichnung als Bedingung in einer DLP-Richtlinie](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).
  

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Die Grundsätze der Aufbewahrung, oder was hat Vorrang?

Es ist möglich oder sogar wahrscheinlich, dass auf Inhalte mehrere Aufbewahrungsrichtlinien angewendet werden, die jeweils mit einer anderen Aktion (aufbewahren, löschen oder beides) und einem anderen Aufbewahrungszeitraum verbunden sind. Was hat Vorrang? Ganz allgemein sei gesagt, dass Sie sich sicher sein können, dass Inhalte, die aufgrund einer Richtlinie aufbewahrt werden müssen, nicht von einer anderen Richtlinie dauerhaft gelöscht werden können.
  
![Diagramm der Grundsätze der Aufbewahrung](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Um zu verstehen, wie verschiedene Bezeichnungen mit Aufbewahrungsrichtlinien auf Inhalte angewendet werden, sollten Sie diese Grundsätze der Aufbewahrung beachten:
  
1. **Aufbewahrung hat Vorrang vor Löschung. ** Angenommen, eine Aufbewahrungsrichtlinie gibt vor, dass Exchange-E-Mails nach drei Jahren gelöscht werden sollen, eine andere Aufbewahrungsrichtlinie jedoch besagt, dass Exchange-E-Mails fünf Jahre lang aufbewahrt und dann gelöscht werden müssen. Alle Inhalte, die drei Jahre alt sind, werden gelöscht und aus der Ansicht der Benutzer ausgeblendet, aber immer noch im Ordner "Wiederherstellbare Elemente" aufbewahrt, bis sie fünf Jahre alt sind und endgültig gelöscht werden. 
    
2. **Der längste Aufbewahrungszeitraum hat Vorrang. ** Wenn Inhalte mehreren Aufbewahrungsrichtlinien, nach denen Inhalte aufbewahrt werden, unterliegen, werden sie bis zum Ende des längsten Aufbewahrungszeitraums aufbewahrt. 
    
3. **Explizite Einbindung hat Vorrang vor impliziter Einbindung.** Dies bedeutet: 
    
    1. Wenn eine Aufbewahrungsbezeichnung mit Einstellungen für die Aufbewahrung von einem Benutzer manuell einem Element, z. B. einer Exchange-E-Mail oder einem OneDrive-Dokument, zugewiesen wird, hat diese Aufbewahrungsbezeichnung sowohl Vorrang vor einer Richtlinie, die auf Website- oder Postfachebene zugewiesen wurde, als auch vor einer Standard-Aufbewahrungsbezeichnung, die von der Dokumentbibliothek zugewiesen wurde. Wenn beispielsweise die explizite Aufbewahrungsbezeichnung eine Aufbewahrung über zehn Jahre angibt, die der Website zugewiesene Aufbewahrungsrichtlinie hingegen eine Aufbewahrung über nur fünf Jahre, hat die Aufbewahrungsbezeichnung Vorrang. Automatisch zugewiesene Aufbewahrungsbezeichnungen werden als implizit und nicht explizit angesehen, da sie von Microsoft 365 automatisch angewendet werden.
    
    2. Wenn eine Aufbewahrungsrichtlinie einen bestimmten Speicherort wie das Postfach oder OneDrive-Konto eines bestimmten Benutzers umfasst, hat diese Richtlinie Vorrang vor einer anderen Aufbewahrungsrichtlinie, die für alle Postfächer oder OneDrive-Konten von Benutzern gilt, aber nicht das Postfach dieses Benutzers speziell einschließt.
    
4. **Der kürzeste Löschzeitraum hat Vorrang. ** Ebenso gilt, dass wenn Inhalte mehreren Aufbewahrungsrichtlinien zur Löschung (ohne Aufbewahrung) unterliegen, sie am Ende des kürzesten Aufbewahrungszeitraums gelöscht werden. 
    
Beachten Sie: Wenn die Regeln, die von allen Richtlinien oder Kennzeichnungen angewendet werden, auf einer Ebene identisch sind, bewegt sich der Fluss nach unten zur nächsten Ebene, wo entschieden wird, welche Regel Vorrang hat.
  
Inhalt, der für eDiscovery gesperrt ist, kann nicht dauerhaft aufgrund einer Aufbewahrungsrichtlinie oder -bezeichnung gelöscht werden. Wenn die Sperre aufgehoben wird, ist der Inhalt wieder für den oben beschriebenen Bereinigungsprozess verfügbar.

### <a name="precedence-for-auto-labeling-with-trainable-classifiers"></a>Vorrang für das automatische Bezeichnen mit trainierbaren Klassifizierungsmerkmalen

Alle Aufbewahrungsbezeichnungen, die für trainierbare Klassifizierungsmerkmale konfiguriert sind, werden gleichzeitig ausgewertet. Wird ein Element von mehr als einem trainierbaren Klassifizierungsmerkmal erkannt, wird anhand der folgenden Kriterien bestimmt, welche Aufbewahrungsbezeichnungen anzuwenden ist:

1. Aufbewahrungsbezeichnungen, die für "nur aufbewahren" oder "aufbewahren und anschließend löschen" konfiguriert sind, haben Vorrang vor Aufbewahrungsbezeichnungen, die für "nur löschen" konfiguriert sind.

2. Bei Aufbewahrungsbezeichnungen, die für "nur aufbewahren" oder "aufbewahren und anschließend löschen" konfiguriert sind, gilt die Aufbewahrungsbezeichnung, die für die längste Aufbewahrung konfiguriert ist.

3. Bei Aufbewahrungsbezeichnungen, die für "nur löschen" konfiguriert sind, gilt die Aufbewahrungsbezeichnung, die für den kürzesten Zeitraum konfiguriert ist.

4. Aufbewahrungsbezeichnungen mit derselben Aktion und dem gleichen Zeitraum führen zu einer nicht deterministischen Auswahl der Aufbewahrungsbezeichnung.

## <a name="monitor-retention-labels"></a>Aufbewahrungsbezeichnungen überwachen

Nachdem Sie Ihre Aufbewahrungsbezeichnungen veröffentlicht oder automatisch angewendet haben, sollten Sie überprüfen, ob sie auf Inhalte wie gewünscht angewendet werden. So überwachen Sie Ihre Aufbewahrungsbezeichnungen:
  
- **Der Bezeichnungsaktivitäten-Explorer**. Mit dem Explorer (Beispiel im Bild unten) können Sie Aktivitäten von Aufbewahrungsbezeichnungen für alle Inhalte in SharePoint und OneDrive während der letzten 30 Tage schnell suchen und anzeigen. Weitere Informationen finden Sie unter [Bezeichnungaktivitäten für Dokumente anzeigen](view-label-activity-for-documents.md).

- Seite zur **Analyse von Bezeichnungen**. Im Microsoft 365 Compliance Center und Microsoft 365 Security Center können Sie schnell sehen, welche Aufbewahrungsbezeichnungen am häufigsten verwendet werden und wo sie angewendet werden. Außerdem können Sie alle Inhalte mit einer bestimmten Aufbewahrungsbezeichnung anzeigen. Weitere Informationen finden Sie unter [Anzeigen der Bezeichnungsnutzung mit der Analyse der Bezeichnungen](label-analytics.md).
    
- **Daten-Governance-Berichte**. Mit diesem Berichten können Sie Trends und Aktivitäten von Aufbewahrungsbezeichnungen für alle Inhalte in Exchange, SharePoint und OneDrive während der letzten 90 Tage schnell anzeigen. Weitere Informationen finden Sie unter [Anzeigen der Daten-Governance-Berichte](view-the-data-governance-reports.md).
    
![Bezeichnungsaktivitäten-Explorer](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)

## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a>Verwenden der Inhaltssuche zum Suchen des gesamten Inhalts, auf den eine bestimmte Aufbewahrungsbezeichnung angewendet wurde

Nachdem die Aufbewahrungsbezeichnungen den Inhalten entweder von Benutzern oder automatisch zugewiesen wurden, können Sie mit der Inhaltssuche alle Inhalte finden, die mit einer bestimmten Aufbewahrungsbezeichnung klassifiziert sind.
  
Wählen Sie beim Erstellen einer Inhaltssuche die Bedingung **Compliancetag** aus, und geben Sie den Namen der Aufbewahrungsbezeichnung vollständig oder teilweise (mit einem Platzhalter) ein. Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
![Compliancetag-Bedingung](../media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="use-retention-labels-instead-of-older-features"></a>Verwenden von Aufbewahrungsbezeichnungen anstelle älterer Features

Aufbewahrungsbezeichnungen können auf einfache Weise der gesamten Organisation und deren Inhalten überall in Microsoft 365 – einschließlich Exchange, SharePoint, OneDrive und Microsoft 365-Gruppen – zur Verfügung gestellt werden. Wenn Sie an einer beliebigen Stelle in Microsoft 365 Inhalte aufbewahren oder löschen oder Datensätze verwalten müssen, empfiehlt sich die Verwendung von Aufbewahrungsbezeichnungen.
  
Es gibt mehrere andere Features, die zuvor zum Aufbewahren oder Löschen von Inhalten oder zum Verwalten von Datensätzen in Microsoft 365 verwendet wurden. Diese Features funktionieren weiterhin Seite an Seite mit Aufbewahrungsbezeichnungen. Es gibt zwar Fälle, in denen sich die Implementierung von Aufbewahrungsbezeichnungen von früheren Features unterscheidet, die Entwicklung von Aufbewahrungsbezeichnungen wird jedoch die Zukunft der Datensatzverwaltung in Microsoft 365 bestimmen. Daher wird im Hinblick auf Datengovernance auf lange Sicht empfohlen, Aufbewahrungsbezeichnungen anstelle der nachfolgend aufgeführten älteren Features zu verwenden.
  
### <a name="exchange-online"></a>Exchange Online

- [Aufbewahrungstags und Aufbewahrungsrichtlinien](https://go.microsoft.com/fwlink/?linkid=846125), auch bekannt als [Messaging-Datensatzverwaltung](https://go.microsoft.com/fwlink/?linkid=846126) (Nur Löschen) 
    
### <a name="sharepoint-and-onedrive"></a>SharePoint und OneDrive

- [Konfiguration der direkten Datensatzverwaltung](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (Aufbewahrung) 
    
- [Einführung in das Datenarchiv](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (Aufbewahrung) 
    
- [Richtlinien zur Informationsverwaltung](intro-to-info-mgmt-policies.md) (Nur Löschen) 
    

