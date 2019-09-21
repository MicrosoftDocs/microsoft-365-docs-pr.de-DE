---
title: Erstellen und Anwenden von Informationsverwaltungsrichtlinien
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
description: Mithilfe von Informationsverwaltungsrichtlinien kann Ihre Organisation steuern, wie lange Inhalt aufbewahrt werden soll, um zu überwachen, was Benutzer mit Inhalten tun, und um einem dokumentbarcodes oder Beschriftungen hinzuzufügen. Eine Richtlinie kann dazu beitragen, die Einhaltung gesetzlicher und behördlicher Vorschriften oder interner Geschäftsprozesse zu erzwingen. Als Administrator können Sie eine Richtlinie einrichten, um zu steuern, wie Dokumente überwacht werden und wie lange Dokumente aufbewahrt werden sollen.
ms.openlocfilehash: 85113393f534a6b17f75962d02518a5a8c65dd8b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37080886"
---
# <a name="create-and-apply-information-management-policies"></a>Erstellen und Anwenden von Informationsverwaltungsrichtlinien

Mithilfe von Informationsverwaltungsrichtlinien kann Ihre Organisation steuern, wie lange Inhalt aufbewahrt werden soll, um zu überwachen, was Benutzer mit Inhalten tun, und um einem dokumentbarcodes oder Beschriftungen hinzuzufügen. Eine Richtlinie kann dazu beitragen, die Einhaltung gesetzlicher und behördlicher Vorschriften oder interner Geschäftsprozesse zu erzwingen. Als Administrator können Sie eine Richtlinie einrichten, um zu steuern, wie Dokumente überwacht werden und wie lange Dokumente aufbewahrt werden sollen.
  
Sie können eine Informationsverwaltungsrichtlinie erstellen, die an drei verschiedenen Orten in der Websitehierarchie, vom weitesten bis zum engsten, möglich ist:
  
- Erstellen Sie eine Richtlinie, die für mehrere Inhaltstypen in einer Websitesammlung verwendet werden soll.
    
- Erstellen Sie eine Richtlinie für einen Websiteinhaltstyp.
    
- Erstellen Sie eine Richtlinie für eine Liste oder Bibliothek.
    
Weitere Informationen finden Sie unter [Einführung in Informationsverwaltungsrichtlinien](intro-to-info-mgmt-policies.md).
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>Erstellen einer Richtlinie für mehrere Inhaltstypen in einer Websitesammlung
<a name="__toc261001590"> </a>

Um sicherzustellen, dass eine Informationsrichtlinie auf alle Dokumente eines bestimmten Typs in einer Websitesammlung angewendet wird, sollten Sie die Richtlinie auf Websitesammlungsebene erstellen und die Richtlinie später auf Inhaltstypen anwenden. Diese werden als Websitesammlungsrichtlinien bezeichnet. 
  
1. Klicken Sie auf der \> **Seite Einstellungen für die**![SharePoint 2016-Startseite auf der Titelleiste auf die Schaltfläche Websitesammlung.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Websiteeinstellungen**.
    
    Klicken Sie auf einer mit SharePoint-Gruppe verbundenen Website auf **Einstellungen**, klicken Sie auf **Websiteinhalte**, und klicken Sie dann auf **Websiteeinstellungen**. 
    
2. Geben Sie auf der Seite Websiteeinstellungen unter **Inhaltstyp Richtlinienvorlagen**für die **Websitesammlungsverwaltung** \> . 
  
![Link zur Richtlinienvorlage "Inhaltstyp" auf der Seite "Websiteeinstellungen"](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. \> **Erstellen**Sie auf der Seite Richtlinien die. 
    
4. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein, und schreiben Sie dann eine kurze Richtlinienanweisung, die den Benutzern erklärt, wofür die Richtlinie verwendet wird.
    
5. Weitere Informationen zum Einrichten der Features, die Sie der Richtlinie zuordnen möchten, finden Sie im nächsten Abschnitt Erstellen von Richtlinien für einen Websiteinhaltstyp. 
    
6. Wählen Sie **OK** aus.
    
## <a name="create-a-policy-for-a-site-content-type"></a>Erstellen einer Richtlinie für einen Websiteinhaltstyp
<a name="__create_a_policy"> </a>

Durch das Hinzufügen einer Informationsverwaltungsrichtlinie zu einem Inhaltstyp ist es einfach, Richtlinienfeatures mehreren Listen oder Bibliotheken zuzuordnen. Sie können eine vorhandene Informationsverwaltungsrichtlinie zu einem Inhaltstyp hinzufügen oder eine eindeutige Richtlinie erstellen, die für einen einzelnen Inhaltstyp spezifisch ist.
  
 Sie können auch eine Informationsverwaltungsrichtlinie zu einem für Listenspezifischen Inhaltstyp hinzufügen. Dies hat den Effekt, dass die Richtlinie nur auf Elemente in dieser Liste angewendet wird, die den Inhaltstyp verwenden. 
  
1. Klicken Sie auf der \> **Seite Einstellungen für die**![SharePoint 2016-Startseite auf der Titelleiste auf die Schaltfläche Websitesammlung.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Websiteeinstellungen**.
    
    Klicken Sie auf einer mit SharePoint-Gruppe verbundenen Website auf **Einstellungen**, klicken Sie auf **Websiteinhalte**, und klicken Sie dann auf **Websiteeinstellungen**. 
    
2. Klicken Sie auf der Seite Websiteeinstellungen unter **Web-Designer-Kataloge** \> auf **Websiteinhaltstypen**.
  
![Link "Websiteinhaltstypen" auf der Seite "Websiteeinstellungen"](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. Wählen Sie auf der Seite Einstellungen des Websiteinhaltstyps den Inhaltstyp aus, dem Sie eine Richtlinie hinzufügen möchten.
    
4. Klicken Sie auf der Seite Websiteinhaltstyp unter **Einstellungen** \> für die **Richtlinieneinstellungen für die Informationsverwaltung**.
    
5. Geben Sie auf der Seite Richtlinie bearbeiten einen Namen und eine Beschreibung für die Richtlinie ein, und schreiben Sie dann eine kurze Beschreibung, die den Benutzern erklärt, wofür die Richtlinie gilt.
    
6. Wählen Sie in den nächsten Abschnitten die einzelnen Richtlinienfeatures aus, die Sie zu ihrer Informationsverwaltungsrichtlinie hinzufügen möchten. 
  
![Arten von Inhaltsrichtlinien](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. Wählen Sie zum Angeben eines Aufbewahrungszeitraums für Dokumente und Elemente, die dieser Richtlinie unterliegen, die **Option Aufbewahrung aktivieren**aus, und geben Sie dann den Aufbewahrungszeitraum und die Aktionen an, die beim Ablauf der Elemente ausgeführt werden sollen.
    
    So geben Sie einen Aufbewahrungszeitraum an
    
||||||**1.**|* * Wählen Sie * * eine Aufbewahrungsphase für Datensätze hinzufügen... * * * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> | Wählen Sie eine Beibehaltungsdauer Option aus, um anzugeben, wann Dokumente oder Elemente auf Ablauf festgelegt werden. Führen Sie einen der folgenden Schritte aus:  <br/>  Um das Ablaufdatum basierend auf einer Date-Eigenschaft festzulegen, unter dem **Ereignis** \> **Diese Stufe basiert auf einer Date-Eigenschaft für das Element**, und wählen Sie dann die Dokument-oder Elementaktion (beispielsweise erstellt oder geändert) und das Inkrement der Zeit nach dieser Aktion ( beispielsweise die Anzahl der Tage, Monate oder Jahre), wenn das Element ablaufen soll.  <br/>  Wenn Sie eine benutzerdefinierte Aufbewahrungs Formel zum Bestimmen des Ablaufs verwenden möchten, wählen Sie **durch eine auf diesem Server installierte benutzerdefinierte Aufbewahrungs Formel festlegen**aus.  <br/> > [!NOTE]> diese Option ist nur verfügbar, wenn eine benutzerdefinierte Formel vom Administrator eingerichtet wurde.           |
||||||3.  <br/> |Die Option **Workflow starten** ist nur verfügbar, wenn Sie eine Richtlinie für eine Liste, Bibliothek oder einen Inhaltstyp definieren, dem bereits ein Workflow zugeordnet ist. Sie erhalten dann eine Auswahl von Workflows zur Auswahl.  <br/> |
||||||4.  <br/> |Wählen Sie im Abschnitt **Serie** die Option **Aktion dieser Stufe wiederholen aus...** und geben Sie ein, wie oft die Aktion wieder aufgetreten werden soll.  <br/> > [!NOTE]> diese Option ist nur verfügbar, wenn die Aktion, die Sie ausgewählt haben, wiederholt werden kann. Beispielsweise können Sie die Serie für die Aktion nicht **dauerhaft löschen**festlegen.           |
||||||5.  <br/> |Wählen Sie **OK**aus.  <br/> |
   
1. Wählen Sie zum Aktivieren der Überwachung für die Dokumente und Elemente, die dieser Richtlinie unterliegen, die **Option Überwachung aktivieren**aus, und geben Sie dann die Ereignisse an, die Sie überwachen möchten.
    
    So aktivieren Sie die Überwachung
    
||||||1. * * * *|Klicken Sie auf der Seite Richtlinie bearbeiten * * **unter** **Auditing** **\>** **enable Auditing** * *, und aktivieren Sie dann die Kontrollkästchen neben den Ereignissen, für die Sie einen Überwachungspfad beibehalten möchten. * * * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |**Um Benutzer aufzufordern, diese Barcodes in Dokumente einzufügen,** **Wählen Sie** **Benutzer auffordern, vor dem Speichern oder Drucken einen Barcode einzufügen** **.** <br/> |
||||||**3.** <br/> |**Wählen Sie** **OK** * *, um das Überwachungsfeature auf die Richtlinie anzuwenden. ** <br/> |
|||||||Mit dem Überwachungsrichtlinienfeature können Organisationen Überwachungspfade für Dokumente erstellen und analysieren sowie Elemente wie Aufgabenlisten, Problemlisten, Diskussionsgruppen und Kalender auflisten. Mit diesem Richtlinienfeature wird ein Überwachungsprotokoll bereitgestellt, das Ereignisse wie beispielsweise, wenn Inhalt angezeigt, bearbeitet oder gelöscht wird, aufzeichnet.  <br/> |
|||||||Wenn die Überwachung als Teil einer Informationsverwaltungsrichtlinie aktiviert ist, können Administratoren die Überwachungsdaten in Berichten zur Richtlinienverwendung anzeigen, die in Microsoft Excel basieren und die aktuelle Verwendung zusammenfassen. Administratoren können mithilfe dieser Berichte feststellen, wie Informationen innerhalb der Organisation verwendet werden. Diese Berichte können Organisationen auch helfen, ihre behördlichen Vorschriften zu überprüfen und zu dokumentieren oder potenzielle Probleme zu untersuchen.  <br/> |
|||||||Im Überwachungsprotokoll werden folgende Informationen aufgezeichnet: Ereignisname, Datum und Uhrzeit des Ereignisses sowie der Systemname des Benutzers, der die Aktion ausgeführt hat.  <br/> |
   
1. Wenn Barcodes als Teil einer Richtlinie aktiviert werden, werden Sie den Dokumenteigenschaften hinzugefügt und im Kopfbereich des Dokuments angezeigt, auf das der Barcode angewendet wird. Wie Beschriftungen können auch Barcodes manuell aus einem Dokument entfernt werden. Sie können angeben, ob Benutzer aufgefordert werden sollen, den Barcode beim Drucken oder Speichern eines Elements einzuschließen, oder ob der Barcode manuell mithilfe der Registerkarte **Einfügen** in 2010-Office Release-Programmen eingefügt werden soll. 
    
    So aktivieren Sie Barcodes
    
||||||1. * * * *|**Aktivieren Sie auf der Seite Richtlinie bearbeiten unter **Barcodes** \> die **Option Barcodes**.**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |Um Benutzer aufzufordern, diese Barcodes in Dokumente einzufügen, wählen Sie **Benutzer auffordern, vor dem Speichern oder Drucken einen Barcode einzufügen**.  <br/> |
||||||**3.** <br/> |Wählen Sie **OK** aus, um das Barcode-Feature auf die Richtlinie anzuwenden.  <br/> |
|||||||
 Die Barcode-Richtlinie generiert Code 39 Standard-Barcodes. Jedes Barcode Bild enthält Text unterhalb des Strichcode Symbols, das den Barcode Wert darstellt. Auf diese Weise können die Barcodedaten auch dann verwendet werden, wenn die Scan Hardware nicht verfügbar ist. Benutzer können die Barcodenummer manuell in das Suchfeld eingeben, um das Element auf einer Website zu suchen.  <br/> |
   
1. Um zu verlangen, dass Dokumente, die dieser Richtlinie unterliegen, Beschriftungen aufweisen, wählen Sie **Bezeichnungen aktivieren**aus, und geben Sie dann die gewünschten Einstellungen für die Beschriftungen an.
    
    So aktivieren Sie Beschriftungen
    
||||||**1.**|* * Wenn Sie festlegen möchten, dass Benutzer einem Dokument eine Bezeichnung hinzufügen möchten, wählen Sie **Benutzer zum Einfügen einer Bezeichnung vor dem Speichern oder Drucken auffordern**aus.  <br/> > [!NOTE]> wenn Beschriftungen optional sein sollen, aktivieren Sie dieses Kontrollkästchen nicht.        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> |Wenn Sie eine Beschriftung so sperren möchten, dass Sie nach dem Einfügen nicht mehr geändert werden kann, wählen Sie **nach dem Hinzufügen Änderungen an Beschriftungen verhindern**aus.  <br/>  Mit dieser Einstellung wird verhindert, dass der Bezeichnungstext aktualisiert wird, nachdem die Bezeichnung in ein Element in einer Clientanwendung wie Word, Excel oder PowerPoint eingefügt wurde. Aktivieren Sie dieses Kontrollkästchen nicht, falls die Bezeichnung aktualisiert werden soll, wenn die Eigenschaften für dieses Dokument oder Element aktualisiert werden.  <br/> |
||||||3.  <br/> |Geben Sie im Feld Bezeichnungsformat den Text für die Beschriftung so ein, wie er angezeigt werden soll. Beschriftungen können bis zu 10 Spaltenbezüge enthalten, von denen jede bis zu 255 Zeichen lang sein kann. Führen Sie die folgenden Schritte aus, um das Format für ihre Bezeichnung zu erstellen:  <br/> Geben Sie die Namen der Spalten ein, die Sie in die Bezeichnung einschließen möchten, in der Reihenfolge, in der Sie angezeigt werden sollen. Schließen Sie die Spaltennamen in geschweifte Klammern ({}) ein, wie im Beispiel auf der Seite Richtlinie bearbeiten dargestellt.  <br/> Geben Sie Wörter ein, um die Spalten außerhalb der Klammern zu identifizieren, wie im Beispiel auf der Seite Richtlinie bearbeiten dargestellt.  <br/> |
||||||4.  <br/> |Geben Sie zum Hinzufügen eines Positions Umbruchs **\n** an der Stelle ein, an der der Positions Umbruch angezeigt werden soll.  <br/> |
||||||5.  <br/> |Wählen Sie den gewünschten Schriftgrad und die gewünschte Formatvorlage aus, und geben Sie an, ob die Beschriftung links, zentriert oder rechts im Dokument positioniert werden soll.  <br/>  Wählen Sie eine Schriftart und ein Format aus, die auf den Benutzercomputern verfügbar sind. Es hängt vom Schriftgrad ab, wie viel Text auf der Bezeichnung angezeigt werden kann.  <br/> |
||||||6.  <br/> |Geben Sie die Höhe und Breite der Beschriftung ein. Die Bezeichnungshöhe kann zwischen .25 Zoll und 20 Zoll liegen, und die Breite der Beschriftung reicht von .25 Zoll bis 20 Zoll. Bezeichnungstext ist immer vertikal innerhalb des Bezeichnungs Bilds zentriert.  <br/> |
||||||7.  <br/> |Wählen Sie **Aktualisieren** aus, um eine Vorschau des Bezeichnungs Inhalts anzuzeigen.  <br/> |
   
1. Wählen Sie **OK** aus.
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>Erstellen einer Richtlinie für eine Liste, Bibliothek oder einen Ordner (standortbasierte Aufbewahrungsrichtlinie)
<a name="__create_a_policy"> </a>

Sie können eine Aufbewahrungsrichtlinie definieren, die nur für eine bestimmte Liste, Bibliothek oder einen bestimmten Ordner gilt. Wenn Sie jedoch auf diese Weise eine Aufbewahrungsrichtlinie erstellen, können Sie diese Richtlinie nicht für andere Listen, Bibliotheken, Ordner oder Websites wieder verwenden, und Sie können eine Websitesammlungsrichtlinie nicht auf eine standortbasierte Richtlinie anwenden.
  
Wenn Sie eine einzelne Aufbewahrungsrichtlinie auf alle Arten von Inhalten an einem einzelnen Speicherort anwenden möchten, werden Sie wahrscheinlich die standortbasierte Aufbewahrung verwenden möchten. In den meisten anderen Fällen sollten Sie überprüfen, ob eine Aufbewahrungsrichtlinie für alle Inhaltstypen angegeben ist.
  
 Jeder Unterordner erbt die Aufbewahrungsrichtlinie seines übergeordneten Elements, es sei denn, Sie brechen die Vererbung auf und definieren eine neue Aufbewahrungsrichtlinie auf der untergeordneten Ebene. 
  
Wenn Sie eine Informationsverwaltungsrichtlinie außer Aufbewahrung in einer Liste oder Bibliothek definieren möchten, müssen Sie eine Informationsverwaltungsrichtlinie für jeden einzelnen Listeninhaltstyp definieren, der dieser Liste oder Bibliothek zugeordnet ist.
  
 Wenn Sie sich an einem beliebigen Punkt für eine Liste oder Bibliothek vom Inhaltstyp zu standortbasierten Richtlinien umschalten, wird nur die Aufbewahrungsrichtlinie als standortbasierte Richtlinie verwendet. Alle anderen Verwaltungsrichtlinien (Überwachungen, Barcodes und Barcodes) werden von den zugeordneten Inhaltstypen geerbt. 
  
 Speicherortbasierte Richtlinien können für eine Websitesammlung deaktiviert werden, indem Sie die Bibliothek und die ordnerbasierte Aufbewahrungsfunktion deaktivieren. Dadurch können Websitesammlungsadministratoren sicherstellen, dass Ihre Inhaltstyp Richtlinien nicht von den standortbasierten Richtlinien eines Listenadministrators außer Kraft gesetzt werden. 
  
Sie benötigen mindestens die Berechtigung Listen verwalten, um die Einstellungen für die Informationsverwaltungsrichtlinie für eine Liste oder Bibliothek zu ändern.
  
1. Navigieren Sie zu der Liste oder Bibliothek, für die Sie eine Informationsverwaltungsrichtlinie angeben möchten. 
    
2. Wählen Sie im Menüband die Bibliotheks **Einstellungen** oder Listen \> **Einstellungen** **für Bibliotheks** -oder **Listen** Registerkarten aus.
    
    Klicken Sie in SharePoint Online auf **Einstellungen** , und klicken Sie dann auf **Listeneinstellungen** oder **Bibliothekseinstellungen**. 
    
3. Unter **Berechtigungen und Verwaltungs** \> **Informationsverwaltungsrichtlinien Einstellungen**.
  
![Link "Informationsverwaltungsrichtlinien" auf der Seite "Einstellungen" für Dokumentbibliothek](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Stellen Sie auf der Seite Einstellungen für die Informationsverwaltungsrichtlinie sicher, dass die Aufbewahrungs Quelle für die Liste oder Bibliothek auf Bibliothek und Ordner festgelegt ist. 
  
Wenn **Inhaltstyp** als Quelle angezeigt wird, klicken Sie auf **Quelle ändern**, und klicken Sie dann auf **Bibliothek und Ordner**. Sie werden gewarnt, dass Inhaltstyp Aufbewahrungsrichtlinien ignoriert werden. Wählen Sie **OK** aus. 
    
5. Geben Sie auf der Seite Richtlinie bearbeiten unter **Bibliotheks basierter aufbewahrungszeitplan**eine kurze Beschreibung für die Richtlinie ein, die Sie erstellen. 
    
6. Wählen Sie **Add a Retention Stage** aus...
    
     Beachten Sie, dass Sie Unterdatensätze auswählen können, unterschiedliche Aufbewahrungsrichtlinien für Datensätze zu definieren, indem Sie die Option unterschiedliche Aufbewahrungs Phasen für Datensätze definieren auswählen. 
    
7. Wählen Sie im Dialogfeld Bühneneigenschaften eine Option für den Aufbewahrungszeitraum aus, um anzugeben, wann Dokumente oder Elemente auf Ablauf festgelegt werden. Führen Sie einen der folgenden Schritte aus:
    
  - Um das Ablaufdatum basierend auf einer Date-Eigenschaft festzulegen, unter dem **Ereignis** \> **Diese Stufe basiert auf einer Date-Eigenschaft für das Element**, und wählen Sie dann die Dokument-oder Elementaktion (beispielsweise erstellt oder geändert) und das Inkrement der Zeit nach dieser Aktion ( beispielsweise die Anzahl der Tage, Monate oder Jahre), wenn das Element ablaufen soll. 
    
  - Wenn Sie eine benutzerdefinierte Aufbewahrungs Formel zum Bestimmen des Ablaufs verwenden möchten, wählen Sie **durch eine auf diesem Server installierte benutzerdefinierte Aufbewahrungs Formel festlegen**aus. 
    
    > [!NOTE]
    >  Diese Option ist nur verfügbar, wenn eine benutzerdefinierte Formel vom Administrator eingerichtet wurde. 
  
  - Geben Sie unter **Aktion**an, was geschehen soll, wenn das Dokument oder Element abläuft. Um zu ermöglichen, dass eine bestimmte Aktion mit dem Dokument oder Element (beispielsweise Löschung) geschieht, wählen Sie eine Aktion aus der Liste aus. 
    
8. Die Option **Workflow starten** ist nur verfügbar, wenn Sie eine Richtlinie für eine Liste, Bibliothek oder einen Inhaltstyp definieren, dem bereits ein Workflow zugeordnet ist. Sie erhalten dann eine Auswahl von Workflows zur Auswahl. 
    
9. Wählen **** Sie unter Serie **die Aktion diese Phase wiederholen...** und geben Sie ein, wie oft die Aktion wieder aufgetreten werden soll. 
    
    > [!NOTE]
    >  Diese Option ist nur verfügbar, wenn die Aktion, die Sie ausgewählt haben, wiederholt werden kann. Beispielsweise können Sie die Serie für die Aktion nicht **dauerhaft löschen**festlegen. 
  
10. Wählen Sie **OK** aus.
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a>Anwenden einer Websitesammlungsrichtlinie auf einen Inhaltstyp
<a name="__apply_a_site"> </a>

Wenn für Ihre Website bereits Informationsverwaltungsrichtlinien als Websitesammlungsrichtlinien erstellt wurden, können Sie eine der Richtlinien auf einen Inhaltstyp anwenden. Auf diese Weise können Sie dieselbe Richtlinie auf mehrere Inhaltstypen in einer Websitesammlung anwenden, die nicht den gleichen übergeordneten Inhaltstyp aufweisen.
  
 Wenn Sie Richtlinien auf mehrere Inhaltstypen in einer Websitesammlung anwenden möchten und ein verwalteter Metadatendienst konfiguriert ist, können Sie die inhaltstypveröffentlichung verwenden, um Informationsverwaltungsrichtlinien in mehreren Websitesammlungen zu veröffentlichen. Weitere Informationen finden Sie im Abschnitt [Anwenden einer Richtlinie auf Websitesammlungen](#apply-a-policy-across-site-collections) . 
  
1. Navigieren Sie zu der Liste oder Bibliothek, die den Inhaltstyp enthält, auf den Sie eine Richtlinie anwenden möchten.
    
2. Wählen Sie im Menüband die Bibliotheks **Einstellungen** oder Listen \> **Einstellungen** **für Bibliotheks** -oder **Listen** Registerkarten aus.
    
    Klicken Sie in SharePoint Online auf **Einstellungen** , und klicken Sie dann auf **Listeneinstellungen** oder **Bibliothekseinstellungen**. 
    
3. Unter **Berechtigungen und Verwaltungs** \> **Informationsverwaltungsrichtlinien Einstellungen**.
  
![Link "Informationsverwaltungsrichtlinien" auf der Seite "Einstellungen" für Dokumentbibliothek](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Stellen Sie sicher, dass die Richtlinienquelle auf **Inhaltstypen**festgelegt ist, und wählen Sie unter **Inhaltstyp Richtlinien** den Inhaltstyp aus, auf den die Richtlinie angewendet werden soll. 
    
5. Wählen Sie unter **Geben Sie die Richtlinie** \> **verwenden eine Websitesammlungsrichtlinie**aus, und wählen Sie dann die Richtlinie aus der Liste aus, die Sie anwenden möchten. 
    
    > [!NOTE]
    >  Wenn die Option **Websitesammlungsrichtlinie verwenden** nicht verfügbar ist, wurden keine Websitesammlungsrichtlinien für die Websitesammlung definiert. 
  
6. Wählen Sie **OK** aus.
    
     Wenn die Liste oder Bibliothek, mit der Sie arbeiten, die Verwaltung mehrerer Inhaltstypen unterstützt, können Sie unter **Inhaltstypen** den Inhaltstyp auswählen, für den Sie eine Informationsverwaltungsrichtlinie angeben möchten. Dadurch gelangen Sie direkt zu Schritt 5 weiter oben. 
    
## <a name="apply-a-policy-across-site-collections"></a>Anwenden einer Richtlinie auf Websitesammlungen
<a name="__toc260646789"> </a>

Freigeben von Inhaltstypen für Websitesammlungen mithilfe einer Dienstanwendung für verwaltete Metadaten zum Einrichten der Veröffentlichung von Inhaltstypen. Die inhaltstypveröffentlichung unterstützt Sie bei der konsistenten Verwaltung von Inhalten und Metadaten auf ihren Websites, da Inhaltstypen zentral erstellt und aktualisiert werden können und Updates in mehreren Abonnement-Websitesammlungen oder Webanwendungen veröffentlicht werden können.
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>Erstellen einer Vorlage aus einer vorhandenen Richtlinie für die Verwendung in Websitesammlungen
<a name="__toc262125409"> </a>

Sie können eine Informationsverwaltungsrichtlinie definieren und anschließend eine Vorlage daraus erstellen, die bei Bedarf in mehreren Websitesammlungen verwendet wird. Diese Methode kann verwendet werden, wenn Sie eine Sicherung ihrer Informationsrichtlinien verwenden möchten, oder Sie kann auch als alternative Methode für die Verwendung der inhaltstypveröffentlichung zum Anwenden einer Richtlinie auf Websitesammlungen verwendet werden. Sie erstellen eine Vorlage oder Sicherung der Richtlinie, indem Sie die Richtlinie aus einer Websitesammlung exportieren und anschließend an einen gespeicherten Speicherort oder eine andere Websitesammlung importieren.
  
> [!IMPORTANT]
>  Wenn Sie das Feature exportieren/importieren als Möglichkeit zum Erstellen einer Reihe von Richtlinienvorlagen verwenden, sollten Sie beachten, dass in der Datei Policy. XML ein eindeutiger Bezeichner vorhanden ist. Aus diesem Grund können Sie diese Richtlinie nicht mehr als einmal in eine Website importieren, ohne diesen eindeutigen Bezeichner zu ändern. 
  
### <a name="export-a-policy"></a>Exportieren einer Richtlinie
<a name="__toc260646790"> </a>

1. Wählen Sie auf der Homepage der Websitesammlung **Einstellungen**![für kleine Einstellungen aus, die als Standort für Websiteeinstellungen eintraten. ](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) **** Website \> Einstellungen.
    
    Klicken Sie auf einer mit SharePoint-Gruppe verbundenen Website auf **Einstellungen**, klicken Sie auf **Websiteinhalte**, und klicken Sie dann auf **Websiteeinstellungen**. 
    
2. Geben Sie auf der Seite Websiteeinstellungen unter **Inhaltstyp Richtlinienvorlagen**für die **Websitesammlungsverwaltung** \> . 
  
![Link zur Richtlinienvorlage "Inhaltstyp" auf der Seite "Websiteeinstellungen"](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Wählen Sie die Richtlinie aus, \> die Sie exportieren möchten \> , Scrollen Sie zum unteren **Export**.
    
4. Wählen Sie an der Eingabeaufforderung zum Speichern oder Öffnen der Datei **Speichern**aus, und wählen Sie dann einen Speicherort aus, in dem die Datei gespeichert werden soll. Stellen Sie sicher, dass Sie einen Speicherort auswählen, der für die Websitesammlungen zur Verfügung steht, die die Richtlinie importieren.
    
5. Wenn das Dialogfeld zum Herunterladen abgeschlossen angezeigt wird, wählen Sie **Schließen**aus.
    
### <a name="import-a-policy-to-a-different-site-collection"></a>Importieren einer Richtlinie in eine andere Websitesammlung
<a name="__toc260646791"> </a>

Wenn Sie eine Informationsverwaltungsrichtlinie importieren, können Sie Sie auf der Website-oder Listenebene innerhalb einer bestimmten Websitesammlung auf mehrere Inhaltstypen anwenden. Die Vorteile dieser Vorgehensweise liegen auf zweierlei Weise: Sie müssen die Richtlinie nicht für jeden Inhaltstyp neu definieren und anwenden, und Sie können Richtlinienänderungen einfacher verwalten, indem Sie Änderungen an der Richtlinie an nur einer Stelle vornehmen.
  
1. Wählen Sie auf der Homepage der Websitesammlung, auf die Sie die Richtlinie anwenden möchten, die Option **Einstellungen**![für kleine Einstellungen aus, die den Ort der Websiteeinstellungen übernahm. ](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) **** Website \> Einstellungen.
    
    Klicken Sie auf einer mit SharePoint-Gruppe verbundenen Website auf **Einstellungen**, klicken Sie auf **Websiteinhalte**, und klicken Sie dann auf **Websiteeinstellungen**. 
    
2. Geben Sie auf der Seite Websiteeinstellungen unter **Inhaltstyp Richtlinienvorlagen**für die **Websitesammlungsverwaltung** \> .
    
3. Suchen Sie auf der \> Seite Richtlinien **importieren** \> **nach der** XML-Datei für die Richtlinie. 
    
4. Wählen Sie die XML-Datei aus, in der die \> Richtlinie **geöffnet**gespeichert wurde. 
    
5. Klicken Sie auf der Seite \> Importieren einer Websitesammlungsrichtlinie auf **importieren** , um die Richtlinie der Websitesammlung hinzuzufügen. 
    
Die importierte Richtlinie kann nun auf einen oder mehrere Inhaltstypen auf Website-oder Listenebene angewendet werden. 
  
Mithilfe von Informationsverwaltungsrichtlinien kann Ihre Organisation steuern, wie lange Inhalt aufbewahrt werden soll, um zu überwachen, was Benutzer mit Inhalten tun, und um einem dokumentbarcodes oder Beschriftungen hinzuzufügen. Eine Richtlinie kann dazu beitragen, die Einhaltung gesetzlicher und behördlicher Vorschriften oder interner Geschäftsprozesse zu erzwingen. Als Administrator können Sie eine Richtlinie einrichten, um zu steuern, wie Dokumente überwacht werden und wie lange Dokumente aufbewahrt werden sollen.

Sie können eine Informationsverwaltungsrichtlinie erstellen, die an drei verschiedenen Orten in der Websitehierarchie, vom weitesten bis zum engsten, möglich ist:
- Erstellen Sie eine Richtlinie, die für mehrere Inhaltstypen in einer Websitesammlung verwendet werden soll.
- Erstellen Sie eine Richtlinie für einen Websiteinhaltstyp.
- Erstellen Sie eine Richtlinie für eine Liste oder Bibliothek.

Weitere Informationen finden Sie unter [Einführung in Informationsverwaltungsrichtlinien](intro-to-info-mgmt-policies.md).
  

