---
title: Erstellen und Anwenden von Informationsverwaltungsrichtlinien
f1.keywords:
- NOCSH
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
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie eine Informationsverwaltungsrichtlinie einrichten, um zu steuern, wie lange Informationen aufbewahrt werden und wer die Informationen verwendet.
ms.openlocfilehash: 2519f039e7495d01a828aee564ce1a6caf41342d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817994"
---
# <a name="create-and-apply-information-management-policies"></a>Erstellen und Anwenden von Informationsverwaltungsrichtlinien

Informationsverwaltungsrichtlinien ermöglichen Es Ihrer Organisation, zu steuern, wie lange Inhalte beibehalten werden sollen, um zu überwachen, was Personen mit Inhalten tun, und Barcodes oder Bezeichnungen zu Dokumenten hinzuzufügen. Eine Richtlinie kann dazu beitragen, die Einhaltung gesetzlicher und behördlicher Bestimmungen oder interner Geschäftsprozesse durchzusetzen. Als Administrator können Sie eine Richtlinie einrichten, um zu steuern, wie Dokumente nachverfolgt werden und wie lange Dokumente beibehalten werden.
  
Sie können eine Informationsverwaltungsrichtlinie an drei verschiedenen Speicherorten in der Websitehierarchie erstellen, von der breitesten bis zur schmalsten:
  
- Erstellen Sie eine Richtlinie, die für mehrere Inhaltstypen in einer Websitesammlung verwendet werden soll.
    
- Erstellen Sie eine Richtlinie für einen Websiteinhaltstyp.
    
- Erstellen Sie eine Richtlinie für eine Liste oder Bibliothek.
    
Weitere Informationen finden Sie unter [Einführung in Informationsverwaltungsrichtlinien](intro-to-info-mgmt-policies.md).
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>Erstellen einer Richtlinie für mehrere Inhaltstypen in einer Websitesammlung
<a name="__toc261001590"> </a>

Um sicherzustellen, dass eine Informationsrichtlinie auf alle Dokumente eines bestimmten Typs in einer Websitesammlung angewendet wird, sollten Sie die Richtlinie auf Websitesammlungsebene erstellen und die Richtlinie später auf Inhaltstypen anwenden. Diese werden als Websitesammlungsrichtlinien bezeichnet. 
  
1. Klicken Sie auf der Homepage der \> **Websitesammlung Einstellungen** ![ SharePoint 2016 Einstellungen auf der Titelleiste.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Websiteeinstellungen**.
    
    Klicken Sie SharePoint mit einer Gruppe verbundenen Website auf **Einstellungen**, klicken Sie auf Websiteinhalte, und klicken Sie dann auf Website **Einstellungen**. 
    
2. Auf der Seite Website Einstellungen unter **Websitesammlungsverwaltung** \> **Inhaltstyprichtlinienvorlagen**. 
  
![Link zur Inhaltstyprichtlinie auf Einstellungen Seite](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Erstellen Sie auf der Seite \> **Richtlinien**. 
    
4. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein, und schreiben Sie dann eine kurze Richtlinienrichtlinie, in der den Benutzern erklärt wird, wofür die Richtlinie dient.
    
5. Im nächsten Abschnitt zum Erstellen von Richtlinien für einen Websiteinhaltstyp erfahren Sie, wie Sie die Features einrichten, die Sie der Richtlinie zuordnen möchten. 
    
6. Wählen Sie **OK** aus.
    
## <a name="create-a-policy-for-a-site-content-type"></a>Erstellen einer Richtlinie für einen Websiteinhaltstyp
<a name="__create_a_policy"> </a>

Das Hinzufügen einer Informationsverwaltungsrichtlinie zu einem Inhaltstyp erleichtert das Zuordnen von Richtlinienfeatures zu mehreren Listen oder Bibliotheken. Sie können eine vorhandene Informationsverwaltungsrichtlinie zu einem Inhaltstyp hinzufügen oder eine eindeutige Richtlinie erstellen, die für einen einzelnen Inhaltstyp spezifisch ist.
  
 Sie können auch eine Informationsverwaltungsrichtlinie zu einem Inhaltstyp hinzufügen, der für Listen spezifisch ist. Dies hat den Effekt, dass die Richtlinie nur auf Elemente in dieser Liste angewendet wird, die den Inhaltstyp verwenden. 
  
1. Klicken Sie auf der Homepage der \> **Websitesammlung Einstellungen** ![ SharePoint 2016 Einstellungen auf der Titelleiste.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Websiteeinstellungen**.
    
    Klicken Sie SharePoint mit einer Gruppe verbundenen Website auf **Einstellungen**, klicken Sie auf Websiteinhalte, und klicken Sie dann auf Website **Einstellungen**. 
    
2. Auf der Seite Website Einstellungen unter **Web Designer Galleries** \> **Websiteinhaltstypen**.
  
![Link zu Websiteinhaltstypen auf Einstellungen Seite](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. Wählen Sie auf Einstellungen Seite Websiteinhaltstyp den Inhaltstyp aus, dem Sie eine Richtlinie hinzufügen möchten.
    
4. Klicken Sie auf der Seite **Websiteinhaltstyp unter Einstellungen** \> **Richtlinieneinstellungen für die Informationsverwaltung**.
    
5. Geben Sie auf der Seite Richtlinie bearbeiten einen Namen und eine Beschreibung für die Richtlinie ein, und schreiben Sie dann eine kurze Beschreibung, in der den Benutzern erklärt wird, wofür die Richtlinie dient.
    
6. Wählen Sie in den nächsten Abschnitten die einzelnen Richtlinienfeatures aus, die Sie Ihrer Informationsverwaltungsrichtlinie hinzufügen möchten. 
  
![Typen von Inhaltsrichtlinien](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. Wenn Sie einen Aufbewahrungszeitraum für Dokumente und Elemente angeben möchten, die dieser Richtlinie unterliegen, wählen Sie Aufbewahrung aktivieren **aus,** und geben Sie dann den Aufbewahrungszeitraum und die Aktionen an, die beim Ablauf der Elemente erfolgen sollen.
    
    So geben Sie einen Aufbewahrungszeitraum an
    
||||||**1.**|**Choose **Add a retention stage for records...****|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> | Wählen Sie eine Aufbewahrungszeitraumoption aus, um anzugeben, wann Dokumente oder Elemente auf Ablauf festgelegt sind. Führen Sie einen der folgenden Schritte aus:  <br/>  Wenn Sie das Ablaufdatum basierend auf einer Date-Eigenschaft festlegen möchten, wählen Sie unter **Ereignis** Diese Phase basiert auf einer Date-Eigenschaft für das Element, und wählen Sie dann die Dokument- oder Elementaktion (z. B. Erstellt oder Geändert) und die Zeit nach dieser Aktion (z. B. die Anzahl der Tage, Monate oder Jahre) aus, wenn das Element ablaufen \> soll.  <br/>  Wenn Sie eine benutzerdefinierte Aufbewahrungsformel zum Bestimmen des Ablaufs verwenden möchten, wählen Sie Auf diesem Server installierte benutzerdefinierte **Aufbewahrungsformel festlegen aus.**  <br/> > [!NOTE]> Diese Option ist nur verfügbar, wenn ihr Administrator eine benutzerdefinierte Formel eingerichtet hat.           |
||||||3.  <br/> |Die **Option Workflow starten** ist nur verfügbar, wenn Sie eine Richtlinie für eine Liste, Bibliothek oder einen Inhaltstyp definieren, der bereits ein Workflow zugeordnet ist. Anschließend erhalten Sie eine Auswahl an Workflows zur Auswahl.  <br/> |
||||||4.  <br/> |Wählen Sie **im Abschnitt Serien** die Option Aktion dieser Phase wiederholen **aus...** und geben Sie ein, wie oft die Aktion erneut geschehen soll.  <br/> > [!NOTE]> Diese Option ist nur verfügbar, wenn die ausgewählte Aktion wiederholt werden kann. Sie können z. B. keine Serienserie für die Aktion **Dauerhaft löschen festlegen.**           |
||||||5.  <br/> |Wählen Sie **OK** aus.  <br/> |
   
1. Um die Überwachung für die Dokumente und Elemente zu aktivieren, die dieser Richtlinie unterliegen, wählen Sie Überwachung aktivieren **aus,** und geben Sie dann die Ereignisse an, die Überwacht werden sollen.
    
    So aktivieren Sie die Überwachung
    
||||||1.****|Klicken Sie auf der Seite Richtlinie bearbeiten** **unter**  Überwachung Überwachung aktivieren **, und aktivieren Sie dann die Kontrollkästchen neben den Ereignissen, für die Sie einen Überwachungspfad **\>**  behalten möchten.****|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |**Wenn Sie Benutzer zum Einfügen dieser Barcodes in Dokumente**  anfordern möchten, wählen Sie Benutzer zum Einfügen eines Strichcodes vor dem Speichern oder **Drucken an.**  <br/> |
||||||**3.** <br/> |**Wählen Sie** **OK** ** aus, um das Überwachungsfeature auf die Richtlinie anzuwenden. ** <br/> |
|||||||Mit dem Feature Überwachungsrichtlinien können Organisationen Überwachungsprotokolle für Dokumente erstellen und analysieren und Elemente wie Aufgabenlisten, Problemlisten, Diskussionsgruppen und Kalender auflisten. Mit diesem Richtlinienfeature wird ein Überwachungsprotokoll bereitgestellt, das Ereignisse wie beispielsweise, wenn Inhalt angezeigt, bearbeitet oder gelöscht wird, aufzeichnet.  <br/> |
|||||||Wenn die Überwachung als Teil einer Informationsverwaltungsrichtlinie aktiviert ist, können Administratoren die Überwachungsdaten in Richtlinienverwendungsberichten anzeigen, die in Microsoft Excel und die aktuelle Verwendung zusammenfassen. Administratoren können mithilfe dieser Berichte feststellen, wie Informationen innerhalb der Organisation verwendet werden. Diese Berichte können Organisationen auch dabei helfen, die Einhaltung gesetzlicher Vorschriften zu überprüfen und zu dokumentieren oder potenzielle Bedenken zu untersuchen.  <br/> |
|||||||Im Überwachungsprotokoll werden folgende Informationen aufgezeichnet: Ereignisname, Datum und Uhrzeit des Ereignisses sowie der Systemname des Benutzers, der die Aktion ausgeführt hat.  <br/> |
   
1. Wenn Barcodes als Teil einer Richtlinie aktiviert sind, werden sie dokumenteigenschaften hinzugefügt und im Kopfzeilenbereich des Dokuments angezeigt, auf das der Strichcode angewendet wird. Strichcodes können wie Bezeichnungen auch manuell aus einem Dokument entfernt werden. Sie können angeben, ob Benutzer aufgefordert werden sollen, den Strichcode beim Drucken oder  Speichern eines Elements anzugeben, oder ob der Strichcode manuell mithilfe der Registerkarte Einfügen in 2010 Office eingefügt werden soll. 
    
    So aktivieren Sie Barcodes
    
||||||1.****|**Klicken Sie auf der Seite Richtlinie bearbeiten unter **Barcodes** \> **Barcodes aktivieren**.**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |Wenn Sie Benutzer zum Einfügen dieser Barcodes in Dokumente anfordern möchten, wählen Sie Benutzer zum Einfügen eines Strichcodes vor dem Speichern **oder Drucken an.**  <br/> |
||||||**3.** <br/> |Wählen **Sie OK** aus, um das Strichcodefeature auf die Richtlinie anzuwenden.  <br/> |
|||||||
 Die Barcoderichtlinie generiert Code 39-Standardcodecodes. Jedes Strichcodebild enthält Text unter dem Strichcodesymbol, das den Strichcodewert darstellt. Dadurch können die Strichcodedaten auch dann verwendet werden, wenn keine Scanhardware verfügbar ist. Benutzer können die Strichcodenummer manuell in das Suchfeld eingeben, um das Element auf einer Website zu finden.  <br/> |
   
1. Wenn Sie festlegen möchten, dass Dokumente, die dieser Richtlinie unterliegen, Bezeichnungen haben, wählen Sie Bezeichnungen aktivieren **aus,** und geben Sie dann die Einstellungen für die Bezeichnungen an.
    
    So aktivieren Sie Bezeichnungen
    
||||||**1.**|**Wenn Benutzer eine Bezeichnung zu einem Dokument hinzufügen müssen, wählen Sie Benutzer zum Einfügen einer Bezeichnung vor dem Speichern oder **Drucken anforderen aus.**  <br/> > [!NOTE]> Wenn Bezeichnungen optional sein sollen, aktivieren Sie dieses Kontrollkästchen nicht.        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> |Um eine Bezeichnung so zu sperren, dass sie nach dem Einfügen nicht geändert werden kann, wählen Sie Änderungen an Bezeichnungen verhindern aus, **nachdem sie hinzugefügt wurden.**  <br/>  Diese Einstellung verhindert, dass der Beschriftungstext aktualisiert wird, sobald die Bezeichnung in ein Element in einer Clientanwendung wie Word, Excel oder PowerPoint. Aktivieren Sie dieses Kontrollkästchen nicht, falls die Bezeichnung aktualisiert werden soll, wenn die Eigenschaften für dieses Dokument oder Element aktualisiert werden.  <br/> |
||||||3.  <br/> |Geben Sie im Feld Bezeichnungsformat den Text für die Bezeichnung so ein, wie sie angezeigt werden soll. Bezeichnungen können bis zu 10 Spaltenverweise enthalten, von denen jede bis zu 255 Zeichen lang sein kann. Gehen Sie wie folgt vor, um das Format für Ihre Bezeichnung zu erstellen:  <br/> Geben Sie die Namen der Spalten ein, die in der Bezeichnung in der Reihenfolge enthalten sein sollen, in der sie angezeigt werden sollen. Schließen Sie die Spaltennamen in geschweifte Klammern ( ) ein, wie im Beispiel auf der Seite {} Richtlinie bearbeiten gezeigt.  <br/> Geben Sie Wörter ein, um die Spalten außerhalb der Klammern zu identifizieren, wie im Beispiel auf der Seite Richtlinie bearbeiten gezeigt.  <br/> |
||||||4.  <br/> |Um einen Zeilenbruch hinzuzufügen, geben Sie **\n** ein, an dem der Zeilenbruch angezeigt werden soll.  <br/> |
||||||5.  <br/> |Wählen Sie den Schriftgrad und die Formatvorlage aus, und geben Sie an, ob die Beschriftung links, zentriert oder rechts im Dokument positioniert werden soll.  <br/>  Wählen Sie eine Schriftart und ein Format aus, die auf den Benutzercomputern verfügbar sind. Es hängt vom Schriftgrad ab, wie viel Text auf der Bezeichnung angezeigt werden kann.  <br/> |
||||||6.  <br/> |Geben Sie die Höhe und Breite der Beschriftung ein. Die Beschriftungshöhe kann zwischen 25 und 20 Zoll liegen, und die Beschriftungsbreite kann zwischen 25 und 20 Zoll liegen. Bezeichnungstext ist immer vertikal zentriert innerhalb des Beschriftungsbilds.  <br/> |
||||||7.  <br/> |Wählen **Sie Aktualisieren** aus, um eine Vorschau des Beschriftungsinhalts anzuzeigen.  <br/> |
   
1. Wählen Sie **OK** aus.
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>Erstellen einer Richtlinie für eine Liste, Bibliothek oder einen Ordner (standortbasierte Aufbewahrungsrichtlinie)
<a name="__create_a_policy"> </a>

Sie können eine Aufbewahrungsrichtlinie definieren, die nur für eine bestimmte Liste, Bibliothek oder einen bestimmten Ordner gilt. Wenn Sie jedoch eine Aufbewahrungsrichtlinie auf diese Weise erstellen, können Sie diese Richtlinie nicht in anderen Listen, Bibliotheken, Ordnern oder Websites wiederverwenden und eine Websitesammlungsrichtlinie nicht auf eine standortbasierte Richtlinie anwenden.
  
Wenn Sie eine einzelne Aufbewahrungsrichtlinie auf alle Inhaltstypen an einem einzigen Speicherort anwenden möchten, sollten Sie höchstwahrscheinlich die standortbasierte Aufbewahrung verwenden. In den meisten anderen Fällen sollten Sie überprüfen, ob für alle Inhaltstypen eine Aufbewahrungsrichtlinie angegeben ist.
  
 Jeder Unterordner erbt die Aufbewahrungsrichtlinie des übergeordneten Elements, es sei denn, Sie möchten die Vererbung brechen und eine neue Aufbewahrungsrichtlinie auf untergeordneter Ebene definieren. 
  
Wenn Sie eine andere Informationsverwaltungsrichtlinie als die Aufbewahrung für eine Liste oder Bibliothek definieren möchten, müssen Sie eine Informationsverwaltungsrichtlinie für jeden einzelnen Listeninhaltstyp definieren, der dieser Liste oder Bibliothek zugeordnet ist.
  
 Wenn Sie zu einem beliebigen Zeitpunkt entscheiden, von Inhaltstyp zu standortbasierten Richtlinien für eine Liste oder Bibliothek zu wechseln, wird nur die Aufbewahrungsrichtlinie als standortbasierte Richtlinie verwendet. Alle anderen Verwaltungsrichtlinien (Audits, Barcodes und Barcodes) werden von den zugeordneten Inhaltstypen geerbt. 
  
 Standortbasierte Richtlinien können für eine Websitesammlung deaktiviert werden, indem das Feature Bibliothek und ordnerbasierte Aufbewahrung deaktiviert wird. Auf diese Weise können Websitesammlungsadministratoren sicherstellen, dass ihre Inhaltstyprichtlinien nicht von den standortbasierten Richtlinien eines Listenadministrators überschrieben werden. 
  
Sie benötigen mindestens die Berechtigung Listen verwalten, um die Richtlinieneinstellungen für die Informationsverwaltung für eine Liste oder Bibliothek zu ändern.
  
1. Navigieren Sie zu der Liste oder Bibliothek, für die Sie eine Informationsverwaltungsrichtlinie angeben möchten. 
    
2. Wählen Sie auf dem Menüband die Registerkarte **Bibliothek** **oder** \> **Listenbibliothek Einstellungen** oder Listen **Einstellungen**.
    
    Klicken SharePoint Online auf **Einstellungen** und dann auf **Listeneinstellungen** oder **Bibliothekseinstellungen**. 
    
3. Unter **Richtlinieneinstellungen für Berechtigungen und** Verwaltung von \> **Informationsverwaltung**.
  
![Link zu Informationsverwaltungsrichtlinien auf der Einstellungsseite für die Dokumentbibliothek](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Stellen Sie auf Einstellungen Seite Informationsverwaltungsrichtlinie sicher, dass die Aufbewahrungsquelle für die Liste oder Bibliothek auf Bibliothek und Ordner festgelegt ist. 
  
Wenn **Inhaltstyp** als Quelle angezeigt wird, klicken Sie auf **Quelle** ändern, und klicken Sie dann auf Bibliothek **und Ordner**. Sie werden darauf aufmerksam, dass Aufbewahrungsrichtlinien für Inhaltstypen ignoriert werden. Wählen Sie **OK** aus. 
    
5. Geben Sie auf der Seite Richtlinie bearbeiten unter Bibliotheksbasierter Aufbewahrungszeitplan eine kurze Beschreibung für die Richtlinie ein, die Sie erstellen. 
    
6. Wählen **Sie Aufbewahrungsphase hinzufügen aus...**
    
     Beachten Sie, dass Sie unter Datensätze verschiedene Aufbewahrungsrichtlinien für Datensätze definieren können, indem Sie die Option Verschiedene Aufbewahrungsphasen für Datensätze definieren auswählen. 
    
7. Wählen Sie im Dialogfeld Stage-Eigenschaften die Option Aufbewahrungszeitraum aus, um anzugeben, wann Dokumente oder Elemente auf Ablauf festgelegt sind. Führen Sie einen der folgenden Schritte aus:
    
  - Wenn Sie das Ablaufdatum basierend auf einer Date-Eigenschaft festlegen möchten, wählen Sie unter **Ereignis** Diese Phase basiert auf einer Date-Eigenschaft für das Element, und wählen Sie dann die Dokument- oder Elementaktion (z. B. Erstellt oder Geändert) und die Zeit nach dieser Aktion (z. B. die Anzahl der Tage, Monate oder Jahre) aus, wenn das Element ablaufen \> soll. 
    
  - Wenn Sie eine benutzerdefinierte Aufbewahrungsformel zum Bestimmen des Ablaufs verwenden möchten, wählen Sie Auf diesem Server installierte benutzerdefinierte **Aufbewahrungsformel festlegen aus.** 
    
    > [!NOTE]
    >  Diese Option ist nur verfügbar, wenn ihr Administrator eine benutzerdefinierte Formel eingerichtet hat. 
  
  - Geben Sie unter **Aktion** an, was geschehen soll, wenn das Dokument oder Element abläuft. Wählen Sie eine Aktion aus der Liste aus, um eine bestimmte Aktion für das Dokument oder Element (z. B. löschen) zu aktivieren. 
    
8. Die **Option Workflow starten** ist nur verfügbar, wenn Sie eine Richtlinie für eine Liste, Bibliothek oder einen Inhaltstyp definieren, der bereits ein Workflow zugeordnet ist. Anschließend erhalten Sie eine Auswahl an Workflows zur Auswahl. 
    
9. Wählen **Sie unter Serien** die Option Aktion dieser Phase wiederholen **aus...** und geben Sie ein, wie oft die Aktion erneut geschehen soll. 
    
    > [!NOTE]
    >  Diese Option ist nur verfügbar, wenn die ausgewählte Aktion wiederholt werden kann. Sie können z. B. keine Serienserie für die Aktion **Dauerhaft löschen festlegen.** 
  
10. Wählen Sie **OK** aus.
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a>Anwenden einer Websitesammlungsrichtlinie auf einen Inhaltstyp
<a name="__apply_a_site"> </a>

Wenn für Ihre Website bereits Informationsverwaltungsrichtlinien als Websitesammlungsrichtlinien erstellt wurden, können Sie eine der Richtlinien auf einen Inhaltstyp anwenden. Auf diese Weise können Sie dieselbe Richtlinie auf mehrere Inhaltstypen in einer Websitesammlung anwenden, die nicht denselben übergeordneten Inhaltstyp verwenden.
  
 Wenn Sie Richtlinien auf mehrere Inhaltstypen in einer Websitesammlung anwenden möchten und einen verwalteten Metadatendienst konfiguriert haben, können Sie die Inhaltstypveröffentlichung verwenden, um Richtlinien für die Informationsverwaltung in mehreren Websitesammlungen zu veröffentlichen. Weitere Informationen finden Sie im Abschnitt [Anwenden einer Richtlinie in Websitesammlungen.](#apply-a-policy-across-site-collections) 
  
1. Navigieren Sie zu der Liste oder Bibliothek, die den Inhaltstyp enthält, auf den Sie eine Richtlinie anwenden möchten.
    
2. Wählen Sie auf dem Menüband die Registerkarte **Bibliothek** **oder** \> **Listenbibliothek Einstellungen** oder Listen **Einstellungen**.
    
    Klicken SharePoint Online auf **Einstellungen** und dann auf **Listeneinstellungen** oder **Bibliothekseinstellungen**. 
    
3. Unter **Richtlinieneinstellungen für Berechtigungen und** Verwaltung von \> **Informationsverwaltung**.
  
![Link zu Informationsverwaltungsrichtlinien auf der Einstellungsseite für die Dokumentbibliothek](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Stellen Sie sicher, dass die Richtlinienquelle  auf Inhaltstypen festgelegt **ist,** und wählen Sie unter Inhaltstyprichtlinien den Inhaltstyp aus, auf den Sie die Richtlinie anwenden möchten. 
    
5. Wählen **Sie unter Richtlinie Festlegen der** Richtlinie \> **Websitesammlungsrichtlinie verwenden** aus der Liste aus, und wählen Sie dann die Richtlinie aus, die Sie anwenden möchten. 
    
    > [!NOTE]
    >  Wenn die **Option Websitesammlungsrichtlinie** verwenden nicht verfügbar ist, wurden keine Websitesammlungsrichtlinien für die Websitesammlung definiert. 
  
6. Wählen Sie **OK** aus.
    
     Wenn die Liste oder Bibliothek, mit der Sie arbeiten, die Verwaltung mehrerer Inhaltstypen unterstützt, können Sie unter Inhaltstypen den Inhaltstyp auswählen, für den Sie eine Informationsverwaltungsrichtlinie angeben möchten.  Dies wird Sie direkt zu Schritt 5 oben. 
    
## <a name="apply-a-policy-across-site-collections"></a>Anwenden einer Richtlinie auf Websitesammlungen
<a name="__toc260646789"> </a>

Freigeben von Inhaltstypen in Websitesammlungen mithilfe einer Dienstanwendung für verwaltete Metadaten zum Einrichten der Inhaltstypveröffentlichung. Die Inhaltstypveröffentlichung hilft Ihnen, Inhalte und Metadaten auf Ihren Websites konsistent zu verwalten, da Inhaltstypen zentral erstellt und aktualisiert werden können und Updates in mehreren abonnierenden Websitesammlungen oder Webanwendungen veröffentlicht werden können.
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>Erstellen einer Vorlage aus einer vorhandenen Richtlinie, die websiteübergreifend verwendet werden soll
<a name="__toc262125409"> </a>

Sie können eine Informationsverwaltungsrichtlinie definieren und anschließend eine Vorlage erstellen, die bei Bedarf in mehreren Websitesammlungen verwendet werden soll. Diese Methode kann verwendet werden, wenn Sie über eine Sicherung Ihrer Informationsrichtlinien verfügen möchten, oder sie kann auch als alternative Methode zur Verwendung der Inhaltstypveröffentlichung zum Anwenden einer Richtlinie in Websitesammlungen verwendet werden. Sie erstellen eine Vorlage oder Sicherung der Richtlinie, indem Sie die Richtlinie aus einer Websitesammlung exportieren und dann an einen gespeicherten Speicherort oder in eine andere Websitesammlung importieren.
  
> [!IMPORTANT]
>  Wenn Sie das Export/Import-Feature zum Erstellen einer Reihe von Richtlinienvorlagen verwenden, beachten Sie, dass in der Richtliniendatei .xml ist. Aus diesem Grund können Sie diese Richtlinie nicht mehr als einmal in eine Website importieren, ohne diesen eindeutigen Bezeichner zu ändern. 
  
### <a name="export-a-policy"></a>Exportieren einer Richtlinie
<a name="__toc260646790"> </a>

1. Wählen Sie auf der **Homepage** der Websitesammlung die Option Einstellungen Einstellungen zahnrad aus, das an die Stelle der ![ Websitesammlung Einstellungen. ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Website Einstellungen**.
    
    Klicken Sie SharePoint mit einer Gruppe verbundenen Website auf **Einstellungen**, klicken Sie auf Websiteinhalte, und klicken Sie dann auf Website **Einstellungen**. 
    
2. Auf der Seite Website Einstellungen unter **Websitesammlungsverwaltung** \> **Inhaltstyprichtlinienvorlagen**. 
  
![Link zur Inhaltstyprichtlinie auf Einstellungen Seite](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Wählen Sie die Richtlinie aus, die Sie exportieren \> möchten, und führen Sie den Bildlauf zum unteren Export \> **aus.**
    
4. Wählen Sie an der Eingabeaufforderung zum Speichern oder Öffnen der Datei **Speichern** aus, und wählen Sie dann einen Speicherort aus, an dem die Datei gespeichert werden soll. Achten Sie darauf, einen Speicherort auszuwählen, der für die Websitesammlungen verfügbar ist, die die Richtlinie importieren.
    
5. Wenn das Dialogfeld Download abgeschlossen angezeigt wird, wählen Sie **Schließen aus.**
    
### <a name="import-a-policy-to-a-different-site-collection"></a>Importieren einer Richtlinie in eine andere Websitesammlung
<a name="__toc260646791"> </a>

Durch das Importieren einer Informationsverwaltungsrichtlinie können Sie sie auf mehrere Inhaltstypen auf Website- oder Listenebene innerhalb einer bestimmten Websitesammlung anwenden. Dies bietet zwei Vorteile: Sie müssen die Richtlinie nicht neu definieren und auf jeden Inhaltstyp anwenden, und Sie können Richtlinienänderungen einfacher verwalten, indem Sie Änderungen an der Richtlinie an nur einem Ort vornehmen.
  
1. Wählen Sie auf der Startseite der Websitesammlung, auf die Sie die Richtlinie anwenden möchten, **Einstellungen** Kleines Einstellungen-Zahnrad aus, das an die Stelle von ![ Site Einstellungen. Site Einstellungen ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **.**
    
    Klicken Sie SharePoint mit einer Gruppe verbundenen Website auf **Einstellungen**, klicken Sie auf Websiteinhalte, und klicken Sie dann auf Website **Einstellungen**. 
    
2. Auf der Seite Website Einstellungen unter **Websitesammlungsverwaltung** \> **Inhaltstyprichtlinienvorlagen**.
    
3. Suchen Sie auf der \> **Seite Richtlinien** \> **durchsuchen,** um die XML-Datei für die Richtlinie zu finden. 
    
4. Wählen Sie die XML-Datei aus, in der die Richtlinie gespeichert wurde \> **Open**. 
    
5. Klicken Sie auf der Seite Websitesammlungsrichtlinie \> **importieren,** um die Richtlinie der Websitesammlung hinzuzufügen. 
    
Ihre importierte Richtlinie kann jetzt auf einen oder mehrere Inhaltstypen auf Website- oder Listenebene angewendet werden. 
  
Informationsverwaltungsrichtlinien ermöglichen Es Ihrer Organisation, zu steuern, wie lange Inhalte beibehalten werden sollen, um zu überwachen, was Personen mit Inhalten tun, und Barcodes oder Bezeichnungen zu Dokumenten hinzuzufügen. Eine Richtlinie kann dazu beitragen, die Einhaltung gesetzlicher und behördlicher Bestimmungen oder interner Geschäftsprozesse durchzusetzen. Als Administrator können Sie eine Richtlinie einrichten, um zu steuern, wie Dokumente nachverfolgt werden und wie lange Dokumente beibehalten werden.

Sie können eine Informationsverwaltungsrichtlinie an drei verschiedenen Speicherorten in der Websitehierarchie erstellen, von der breitesten bis zur schmalsten:
- Erstellen Sie eine Richtlinie, die für mehrere Inhaltstypen in einer Websitesammlung verwendet werden soll.
- Erstellen Sie eine Richtlinie für einen Websiteinhaltstyp.
- Erstellen Sie eine Richtlinie für eine Liste oder Bibliothek.

Weitere Informationen finden Sie unter [Einführung in Informationsverwaltungsrichtlinien](intro-to-info-mgmt-policies.md).
  

