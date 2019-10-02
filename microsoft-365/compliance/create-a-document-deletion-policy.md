---
title: Erstellen einer Dokumentlöschrichtlinie
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: Organisationen müssen häufig Dokumente aufgrund von Konformitäts-, rechtlicher und anderer Bestimmungen für einen bestimmten Zeitraum aufbewahren. Wenn Dokumente aber länger als nötig aufbewahrt werden, kann dies für die Organisation rechtliche Folgen haben.
ms.openlocfilehash: 00b10e1c86160917c96ed1062f0638acf56ef56e
ms.sourcegitcommit: 1eecd7b127462585c35b0c96a179d37db45f6013
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "37342978"
---
# <a name="create-a-document-deletion-policy"></a>Erstellen einer Dokumentlöschrichtlinie

> [!IMPORTANT]
> Wir empfehlen die Verwendung einer Aufbewahrungsrichtlinie oder von Aufbewahrungs Bezeichnungen, die im Microsoft 365 Compliance Center, im Microsoft 365 Security Center oder im Office 365 Security &amp; Compliance Center anstelle einer Dokument Löschungs Richtlinie erstellt wurden. Dokument Löschungsrichtlinien funktionieren weiterhin nebeneinander mit Aufbewahrungsrichtlinien, wenn Sie jedoch Inhalte an einer beliebigen Stelle in Office 365 beibehalten oder löschen müssen, wird empfohlen, eine Aufbewahrungsrichtlinie zu verwenden. Weitere Informationen finden Sie unter [Verwenden einer Aufbewahrungsrichtlinie anstelle dieser Features](retention-policies.md#use-a-retention-policy-instead-of-these-features). 
  
Organisationen müssen häufig Dokumente aufgrund von Konformitäts-, rechtlicher und anderer Bestimmungen für einen bestimmten Zeitraum aufbewahren. Wenn Dokumente aber länger als nötig aufbewahrt werden, kann dies für die Organisation rechtliche Folgen haben.
  
Mit einer Richtlinie zum Löschen von Dokumenten können Sie das Risiko proaktiv verringern, indem Sie Dokumente in einer Website nach einem bestimmten Zeitraum löschen (beispielsweise können Sie fünf Jahre nach dem Erstellen der Dokumente die OneDrive für Unternehmen Websites von Benutzern löschen. 
  
Nach dem Erstellen einer Dokumentlöschrichtlinie können Sie sie einer Vorlage für Websitesammlung zuweisen, damit die Richtlinie für alle Websitesammlungen, die aus dieser Vorlage erstellt werden, verfügbar ist. Sie können außerdem einer bestimmten Websitesammlung eine Richtlinie zuweisen, die alle Richtlinien, die der Vorlage für diese Websitesammlung möglicherweise schon zugewiesen wurden, außer Kraft setzt.
  
![Startseite des Dokument Löschrichtlinien Centers](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a>Richtlinienvorlagen

Sie können eine Dokumentlöschrichtlinie von Grund auf neu erstellen oder eine unserer Beispielrichtlinien verwenden. Im Compliance Policy Center finden Sie Beispielrichtlinien, die Sie entweder sofort verwenden oder als Ausgangsbasis verwenden und umbenennen oder ändern können.
  
![Beispiele für Dokument Löschungsrichtlinien](media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a>Beispiele

Einer Websitesammlung oder einer websitesammlungsvorlage kann eine weitere Richtlinie zugewiesen sein, und jede dieser Richtlinien kann eine oder mehrere Regeln haben. Es kann jedoch nur eine Richtlinie pro Standort aktiv sein, und es kann immer nur eine Löschregel für die Bibliotheken innerhalb der Website aktiv sein.
  
![Diagramm mit Beziehung zwischen Richtlinien](media/IP-Two-policies-four-rules.png)
  
Außerdem können Sie eine Richtlinie als obligatorisch oder Standard und eine Löschregel als Standardregel auswählen: 
  
- **Verbindliche Richtlinie** Wenn eine Richtlinie als obligatorisch gekennzeichnet ist, kann der Websitesammlung oder Vorlage nur eine Richtlinie zugewiesen werden. Die Richtlinie muss als Standard gekennzeichnet sein und wird auf alle Websites angewendet. Websitebesitzer können die Richtlinie nicht abwählen.
    
- **Standardrichtlinie** Wenn eine Richtlinie als Standard festgelegt ist, ist die Richtlinie automatisch in allen Websites aktiv, denen Sie zugewiesen ist, ohne dass der Websitebesitzer eine Aktion benötigt.
    
- **Standardregel** Wenn eine Löschregel als Standard festgelegt ist, wird Sie automatisch auf alle Bibliotheken in den Websites angewendet, in denen die Richtlinie verwendet wird.
    
Die folgenden Beispiele erläutern, wann Sie möglicherweise eine obligatorische Richtlinie oder Standardrichtlinien und -regeln verwenden sollten.
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a>Beispiel 1: Anwenden einer einzelnen Richtlinie mit einer einzelnen Regel auf eine Vorlage für Websitesammlung

Angenommen, Sie möchten eine Dokumentlöschrichtlinie für eine vielfältige Reihe von unstrukturierten Inhalten erzwingen, z. B. alle Websites von OneDrive for Business oder alle Teamwebsites. Wenn Sie sicherstellen möchten, dass eine einzelne Dokumentlöschrichtlinie auf allen Websites aktiv ist, die von einer Vorlage für Websitesammlung erstellt wurde, können Sie wie folgt vorgehen:
  
1. Erstellen Sie eine einzelne Richtlinie mit einer einzelnen Standardlöschregel.
    
2. Legen Sie die Richtlinie als obligatorisch und Standard fest.
    
3. Weisen Sie die Richtlinie einer Vorlage für Websitesammlung zu.
    
In diesem Beispiel wird die Standardlöschregel auf alle Bibliotheken in allen Websitesammlungen angewendet, die aufgrund der Vorlage erstellt wurden, und die Websitebesitzer können die Richtlinie nicht abwählen. Dies ist die einfachste Möglichkeit, um eine Dokumentlöschrichtlinie umfassend und strikt zu erzwingen.
  
![Diagramm mit einer einzelnen verbindlichen Richtlinie](media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a>Beispiel 2: Anwenden einer einzelnen Richtlinie mit mehreren Regeln auf eine websitesammlungsvorlage

Websitebesitzer wissen oft am besten, welche Art von Inhalten ihre Website enthält, sodass Sie Websitebesitzern die Auswahl der für ihre Website am besten geeigneten Löschregel ermöglichen können. Sie können auch zulassen, dass Websitebesitzer die Richtlinie ganz abwählen.
  
Auch dann können Sie die Richtlinien noch zentral erstellen und verwalten. Sie können auch eine Richtlinie und Regel als den Standard auswählen, sodass eine Richtlinie so lange aktiv ist, bis der Websitebesitzer eine andere auswählt oder die Richtlinie abwählt. Wenn Sie Websitebesitzern diese Flexibilität bieten möchten, können Sie wie folgt vorgehen:
  
1. Erstellen Sie eine einzelne Richtlinie mit mehreren Löschregeln, und legen Sie eine Regel als den Standard fest.
    
2. Legen Sie die Richtlinie als die Standardrichtlinie fest.
    
3. Weisen Sie die Richtlinie einer Vorlage für Websitesammlung zu.
    
Websitebesitzer können eine der alternativen Löschregeln auswählen, die Richtlinie abwählen oder nichts unternehmen und die Standardrichtlinie und -regel übernehmen.
  
![Diagramm, das eine Richtlinie mit vielen Regeln zeigt](media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a>Beispiel 3: Anwenden mehrerer Richtlinien mit mindestens einer Regel auf eine Websitesammlung

In diesem Beispiel haben Websitebesitzer die höchste Flexibilität, weil sie aus mehreren Richtlinien auswählen und nach der Auswahl einer Richtlinie oft aus mehreren Regeln auswählen können. Eine Richtlinie und eine Regel sind als der Standard festgelegt, sodass eine Richtlinie so lange aktiv ist, bis der Websitebesitzer eine andere auswählt oder die Richtlinie abwählt. Beachten Sie Folgendes: Wenn Sie keine Richtlinie und Regel als Standard festlegen, sind auf der Website keine Richtlinien oder Regeln für die Dokumentbibliotheken aktiv, bis der Websitebesitzer eine Aktion durchführt, um sie auszuwählen und anzuwenden.
  
Im Unterschied zu den vorherigen beiden Beispielen werden diese Richtlinien einer bestimmten Websitesammlung zugewiesen, nicht der Vorlage für Websitesammlung. Die Richtlinien können also gezielter für den Inhalt in einer bestimmten Websitesammlung angepasst werden.
  
Richtlinien und Regeln werden vererbt. Websitebesitzer können für ihre Website eine Richtlinie und Regel auswählen, und alle Unterwebsites erben die Richtlinie von der übergeordneten Website. Ein Besitzer einer Unterwebsite kann aber die Vererbung aufheben, indem er eine andere Richtlinie und Regel auswählt, die wiederum für alle Unterwebsites gilt, bis die Vererbung wieder aufgehoben wird.
  
Um dieses Szenario einzurichten, können Sie wie folgt vorgehen:
  
1. Erstellen Sie mehrere Richtlinien, die jeweils mindestens eine Regel enthalten.
    
2. Legen Sie eine Richtlinie und Regel als den Standard fest.
    
3. Weisen Sie die Richtlinien einer bestimmten Websitesammlung zu.
    
Außerdem werden die Richtlinien und Regeln für eine bestimmte Websitesammlung angepasst, bei der die Websitebesitzer die Vererbung aufheben können, indem sie die Richtlinie und Regel auswählen, die sich am besten für ihre Website eignet.
  
![Diagramm mit vielen Richtlinien und Regeln](media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a>Erstellen einer Dokumentlöschrichtlinie

1. Navigieren Sie im Office &amp; 365Security Compliance Center zur **Aufbewahrung**der **Datenverwaltung** \> . Klicken Sie unter **Löschen**auf **Dokument Löschrichtlinien für SharePoint Online und OneDrive für Unternehmen verwalten**. Das Document Deletion Policy Center wird auf einer neuen Registerkarte im Browser geöffnet.
    
    Wenn Sie zum ersten Mal vom Security &amp; Compliance Center zum Dokument Löschrichtlinien Center navigieren, wird das Richtlinien Center automatisch erstellt. Alternativ können Sie das Richtlinien Center manuell erstellen, indem Sie [die Websitesammlung erstellen](http://go.microsoft.com/fwlink/p/?LinkID=404342) und auf der Registerkarte **Enterprise** die Option **Compliance Policy Center** auswählen. 
    
2. Wählen Sie **Löschrichtlinien**aus.
    
    ![Löschrichtlinien (Option)](media/IP-Deletion-Policies-option.png)
  
3. Wählen Sie **Neues Element** aus.
    
4. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein. Websitebesitzer wählen eine Richtlinie möglicherweise aufgrund ihres Namens und ihrer Beschreibung aus. Geben Sie daher ausreichende Informationen an, damit sie die richtige Richtlinie auswählen können.
    
5. Um eine Regel zu erstellen, wählen Sie **Neu** aus.
    
6. Geben Sie einen Namen ein, und wählen Sie die folgenden Optionen aus:
    
  - Wählen Sie aus, ob die Regel Dokumente dauerhaft oder in den Papierkorb löschen soll. Der Papierkorb bietet ein Sicherheitsnetz der zweiten Stufe, bevor ein Element permanent von einer Website gelöscht wird. Weitere Informationen zum Papierkorb finden Sie unter [leeren des Papierkorbs oder Wiederherstellen Ihrer Dateien](http://go.microsoft.com/fwlink/p/?LinkID=404348).
    
  - Wählen Sie aus, ob das Löschdatum ab dem Datum der Dokumenterstellung oder der letzten Dokumentänderung berechnet werden soll.
    
  - Geben Sie die Anzahl der Tage, Monate oder Jahre als Zeitraum ein, nach dem das Dokument gelöscht werden soll.
    
  - Wählen Sie, ob die Regel eine Standardregel ist. Die erste Regel, die Sie erstellen, wird automatisch als die Standardregel festgelegt. Eine Standardregel wird automatisch auf alle Bibliotheken auf den Websites angewendet, die die Richtlinie verwenden.
    
![Seite "neue Löschregel"](media/IP-New-deletion-rule.png)
  
7. Klicken Sie auf **Speichern**.
    
8. Erstellen Sie zusätzliche Regeln, wenn Sie zulassen möchten, dass Websitebesitzer andere Regeln auswählen und auf ihre Website anwenden können. Falls vorhanden wird die Standardregel angewendet, wenn der Websitebesitzer keine Aktion durchführt.
    
9. Um eine Regel aus einer Richtlinie zu entfernen, wählen Sie die Regel aus, klicken Sie auf **Löschen**, und klicken Sie dann auf **OK**.
    
    > [!NOTE]
    > Wenn Sie eine Regel löschen und die Richtlinie keine Standardregel enthält, wird für diese Richtlinie keine Regel angewendet, d. h., es werden keine Dokumente gelöscht. 
  
![Bestätigen, dass die Regel aus der Richtlinien Meldung entfernt wird](media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a>Zuweisen der Dokumentlöschrichtlinie zu einer Vorlage für Websitesammlung

Durch das Zuweisen einer Richtlinie zu einer Vorlage für Websitesammlung machen Sie die Richtlinie für alle Websitesammlungen verfügbar, die aufgrund dieser Vorlage erstellt werden, einschließlich bereits vorhandener und künftiger Websitesammlungen.
  
Beachten Sie, dass es sich bei dem für eine Dokument Löschrichtlinie angegebenen Zeitraum um die Zeit seit dem Erstellen oder Ändern des Dokuments und nicht um die Zeit seit der Zuweisung der Richtlinie handelt. Wenn Sie die Richtlinie zum ersten Mal zuweisen, werden alle Dokumente auf der Website ausgewertet und, falls sie die Kriterien erfüllen, gelöscht. Dies trifft auf alle vorhandenen Dokumente zu, nicht nur auf neue Dokumente, die seit der Zuweisung der Richtlinie erstellt wurden.
  
1. Navigieren Sie im &amp; Security Compliance Center zur **Aufbewahrung**der **Datenverwaltung** \> . Klicken Sie unter **Löschen**auf **Dokument Löschrichtlinien für SharePoint Online und OneDrive für Unternehmen verwalten**. Das Document Deletion Policy Center wird auf einer neuen Registerkarte im Browser geöffnet.
    
2. Wählen Sie **Richtlinienzuweisungen für Vorlagen**.
    
    ![Option "Richtlinienzuweisungen für Vorlagen"](media/IP-Policy-Assignments-for-Templates-option.png)
  
3. Wählen Sie **Neues Element** aus.
    
4. Führen Sie einen der folgenden Schritte aus:
    
  - Um die Richtlinie einer Vorlage für Websitesammlung wie die Teamwebsitevorlage zuzuweisen, wählen Sie **Vorlage für Websitesammlung zuweisen** aus, und wählen Sie die Vorlage für Websitesammlung.
    
  - Wenn Sie die Richtlinie Benutzern ein Laufwerk für Unternehmen zuweisen möchten, wählen Sie **OneDrive für Unternehmen Vorlage zuweisen**aus, die unten hervorgehoben ist.
    
    > [!NOTE]
    > Wenn Sie eine Richtlinie zu einer Vorlage für Websitesammlung zuweisen, wird die Richtlinie für bereits vorhandene Websitesammlungen, die aufgrund dieser Vorlage erstellt wurden, und für künftige Websitesammlungen verfügbar gemacht. 
  
![Auswählen einer Vorlagenseite mit OneDrive-Option](media/IP-Choose-a-template.png)
  
5. Klicken Sie auf **Speichern**.
    
    > [!NOTE]
    > Jeder Vorlage kann immer nur ein Satz von Richtlinien zugewiesen werden. Wenn ein Fehler angezeigt wird, der besagt, dass dieser Vorlage bereits Richtlinien zugewiesen wurden **,** \> wählen Sie in der linken Navigations \> Leiste **zuweisen zur Websitesammlung** auswählen aus wählen Sie eine Websitesammlung aus, um die Gruppe von Richtlinien anzuzeigen und zu verwalten, die bereits zugewiesen. 
  
6. Wählen Sie **Zugewiesene Richtlinien verwalten** und die zuzuweisenden Richtlinien aus, und legen Sie dann fest, ob eine Richtlinie die Standardrichtlinie sein soll. Wenn Sie eine Standardrichtlinie festlegen, wird die Richtlinie für alle Websites, die der Richtlinie zugewiesen wurden, automatisch aktiv, ohne dass der Websitebesitzer eine Aktion durchführen muss.
    
    ![Seite "Richtlinien hinzufügen und verwalten"](media/IP-Add-and-manage-policies-page.png)
  
7. Klicken Sie auf **Speichern**.
    
8. Wenn Sie die Richtlinie auf allen Websites erzwingen möchten, ohne zuzulassen, dass Websitebesitzer sie abwählen können, wählen Sie **Richtlinie als obligatorisch kennzeichnen** aus. Wenn Sie eine Richtlinie als obligatorisch kennzeichnen, kann einer Vorlage für Websitesammlung nur diese einzelne Richtlinie zugewiesen werden. Die Richtlinie muss außerdem als Standard gekennzeichnet werden.
    
    Wenn diese Option ausgegraut ist, wählen Sie **Zugewiesene Richtlinien verwalten** aus, und stellen Sie sicher, dass mindestens eine Richtlinie zugewiesen und als Standard festgelegt ist. 
    
9. Klicken Sie auf **Speichern**.
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a>Zuweisen der Dokumentlöschrichtlinie zu einer Websitesammlung

Durch das Zuweisen einer Richtlinie zu einer bestimmten Websitesammlung machen Sie die Richtlinie nur für diese Websitesammlung verfügbar. Sie können also Richtlinien näher an den Inhalt in der Websitesammlung anpassen. Außerdem setzen Richtlinien, die einer bestimmten Websitesammlung zugewiesen werden, alle Richtlinien, die der Vorlage für diese Websitesammlung zugewiesen sind, außer Kraft. Zum Beispiel setzt eine Richtlinie, die der (aus der Teamwebsitevorlage erstellten) Websitesammlung Vertriebsabteilung zugewiesen ist, alle Richtlinien außer Kraft, die der Teamwebsitevorlage zugewiesen sind.
  
Beachten Sie, dass es sich bei dem für eine Dokument Löschrichtlinie angegebenen Zeitraum um die Zeit seit dem Erstellen oder Ändern des Dokuments und nicht um die Zeit seit der Zuweisung der Richtlinie handelt. Wenn Sie die Richtlinie zum ersten Mal zuweisen, werden alle Dokumente auf der Website ausgewertet und, falls sie die Kriterien erfüllen, gelöscht. Dies trifft auf alle vorhandenen Dokumente zu, nicht nur auf neue Dokumente, die seit der Zuweisung der Richtlinie erstellt wurden.
  
1. Navigieren Sie im &amp; Security Compliance Center zur **Aufbewahrung**der **Datenverwaltung** \> . Wählen Sie unter **Löschen**die Option **Dokument Löschrichtlinien für SharePoint Online und OneDrive für Unternehmen verwalten**aus. Das Document Deletion Policy Center wird auf einer neuen Registerkarte im Browser geöffnet.
    
2. Wählen Sie **Richtlinienzuweisungen für Websitesammlungen**.
    
    ![Richtlinienzuweisungen für Websitesammlungen (Option)](media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. Wählen Sie **Neues Element** aus.
    
4. Wählen Sie **Websitesammlung auswählen**aus. Suchen Sie nach der Websitesammlung anhand des Namens oder der URL, wählen Sie die Websitesammlung aus, und klicken Sie auf **Speichern**.
    
    > [!NOTE]
    > Jeder Websitesammlung kann immer nur ein Satz von Richtlinien zugewiesen werden. Wenn ein Fehler angezeigt wird, der besagt, dass dieser Websitesammlung bereits Richtlinien zugewiesen wurden, wählen Sie **"** \> der **Websitesammlung zuweisen** " aus, und wählen Sie eine Websitesammlung aus, um den bereits zugewiesenen Satz von Richtlinien anzuzeigen und zu verwalten. 
  
![Auswählen einer Website Sammlungsseite](media/IP-Choose-a-site-collection-page.png)
  
5. Wählen Sie **Zugewiesene Richtlinien verwalten** und die zuzuweisenden Richtlinien aus, und legen Sie dann fest, ob eine Richtlinie die Standardrichtlinie sein soll. Wenn Sie eine Standardrichtlinie festlegen, wird die Richtlinie für alle Websites, die der Richtlinie zugewiesen wurden, automatisch aktiv, ohne dass der Websitebesitzer eine Aktion durchführen muss.
    
    ![Seite "Richtlinien hinzufügen und verwalten"](media/IP-Add-and-manage-policies-page.png)
  
6. Klicken Sie auf **Speichern**.
    
7. Wenn Sie die Richtlinie auf allen Websites erzwingen möchten, ohne zuzulassen, dass Websitebesitzer sie abwählen können, wählen Sie **Richtlinie als obligatorisch kennzeichnen** aus. Wenn Sie eine Richtlinie als obligatorisch kennzeichnen, kann einer Websitesammlung nur diese einzelne Richtlinie zugewiesen werden. Die Richtlinie muss außerdem als Standard gekennzeichnet werden.
    
    Wenn diese Option ausgegraut ist, wählen Sie **Zugewiesene Richtlinien verwalten** aus, und stellen Sie sicher, dass mindestens eine Richtlinie zugewiesen und als Standard festgelegt ist. 
    
8. Klicken Sie auf **Speichern**.
    
## <a name="delete-a-policy-assignment"></a>Löschen einer Richtlinienzuweisung

Wenn Sie eine Zuweisung löschen, werden die zugewiesenen Richtlinien nicht mehr auf die Websites in der Websitesammlung oder Vorlage für Websitesammlung angewendet.
  
1. Navigieren Sie im &amp; Security Compliance Center zur **Aufbewahrung**der **Datenverwaltung** \> . Wählen Sie unter **Löschen**die Option **Dokument Löschrichtlinien für SharePoint Online und OneDrive für Unternehmen verwalten**aus. Das Document Deletion Policy Center wird auf einer neuen Registerkarte im Browser geöffnet.
    
2. Wählen Sie entweder **Richtlinienzuweisungen für Vorlagen ** oder **Richtlinienzuweisungen für Websitesammlungen**.
    
3. Wählen Sie das Zuordnungselement aus, und klicken Sie auf **Element löschen**.
    
    ![Befehl "Element löschen" für Richtlinienzuweisung](media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a>Löschen einer Richtlinie

Eine verwendete Richtlinie kann nicht gelöscht werden. Bevor Sie eine Richtlinie löschen können, müssen Sie zunächst alle Zuordnungen zu Websitesammlungen und Websitesammlungsvorlagen löschen, die diese Richtlinie enthalten – siehe den vorherigen Abschnitt.
  
1. Wählen Sie im &amp; Security Compliance \> Center in der linken Navigation \> unter Manage Document **Delete** \> \> Policies for SharePoint Online and OneDrive die Option **Data Management** **Retention** aus. ** für Unternehmen**. Das Document Deletion Policy Center wird auf einer neuen Registerkarte im Browser geöffnet.
    
2. Wählen Sie * * Löschrichtlinien * * aus.
    
    ![Löschrichtlinien (Option)](media/IP-Deletion-Policies-option.png)
  
3. Wählen Sie die Richtlinie aus.
    
4. Entfernen Sie auf \> der Register \> Karte Menü Band **Elemente** die **Richtlinie**.
    
    ![Schaltfläche ' Richtlinie entfernen ' auf dem Menüband](media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. Wenn die Richtlinie verwendet wird, werden Sie gefragt, ob Sie die Richtlinie aus allen Websitesammlungen entfernen möchten, in denen Sie verwendet wird. Wenn Sie sich sicher sind, wählen Sie **OK**.
    
    ![Bestätigungsnachricht für die Richtlinie löschen](media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a>Siehe auch

[Übersicht über Dokumentlöschrichtlinien](document-deletion-policies.md)

[Anwenden oder Entfernen einer Dokumentlöschrichtlinie für eine Website](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

