---
title: Anwenden oder Entfernen einer Dokumentlöschrichtlinie für eine Website
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Unternehmen unterliegen häufig compliancebezogenen, rechtlichen oder anderen Vorschriften, nach denen sie Dokumente eine bestimmte Zeit lang aufbewahren müssen. Werden Dokumente jedoch länger als erforderlich aufbewahrt, kann dies für das Unternehmen ein rechtliches Risiko darstellen. Daher hat Ihr Unternehmen für Ihre Website möglicherweise eine Dokumentlöschrichtlinie erstellt, nach der z. B. allgemeine Geschäftsdokumente fünf Jahre nach Erstellung gelöscht werden müssen.
ms.openlocfilehash: f04b693a68da36b37524fe5c1fd2e00fab6c2bc6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079842"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Anwenden oder Entfernen einer Dokumentlöschrichtlinie für eine Website

Unternehmen unterliegen häufig compliancebezogenen, rechtlichen oder anderen Vorschriften, nach denen sie Dokumente eine bestimmte Zeit lang aufbewahren müssen. Werden Dokumente jedoch länger als erforderlich aufbewahrt, kann dies für das Unternehmen ein rechtliches Risiko darstellen. Aus diesem Grund hat Ihre Organisation möglicherweise eine Richtlinie zum Löschen von Dokumenten&mdash;für Ihre Website erstellt. beispielsweise können allgemeine Geschäftsdokumente fünf Jahre nach ihrer Erstellung gelöscht werden.
  
Abhängig von Ihrem Unternehmen kann eine Dokumentlöschrichtlinie eine der folgenden Eigenschaften aufweisen:
  
- **Obligatorisch** Ein Websitebesitzer kann keine obligatorische Richtlinie deaktivieren, die automatisch auf die Website angewendet wird. 
    
- **Standardmäßig** Eine Standardrichtlinie wird automatisch auf eine Website angewendet. Ein Websiteeigentümer hat jedoch folgende Möglichkeiten: 
    
  - Auswählen einer anderen Richtlinie, sofern verfügbar.
    
  - Deaktivieren Sie die Richtlinie vollständig, wenn Sie für den Inhalt der Website nicht relevant ist.
    
- **Weder verpflichtend noch standardmäßig** In diesem Fall wird auf die Website keine Richtlinie automatisch angewendet, und der Websiteeigentümer muss Maßnahmen ergreifen, um eine Richtlinie anzuwenden. 
    
Eine Richtlinie zum Löschen von Dokumenten enthält möglicherweise mehrere Regeln&mdash;, beispielsweise kann eine Regel sagen, Löschen von Dokumenten ein Jahr nach ihrer Erstellung, aber eine andere Regel könnte sagen, Löschen von Dokumenten ein Jahr nach ihrer letzten Änderung. Wenn eine Richtlinie mehr als eine Regel enthält, können Sie die Regel auswählen, die am besten für Ihre Website gilt. Die Delete-Regel wird auf alle Bibliotheken innerhalb der Website angewendet. In einer Website kann jeweils immer nur eine Richtlinie und eine Regel aktiv sein. Wie eine Richtlinie kann eine Regel als Standard festgelegt werden, sodass Sie automatisch angewendet wird, wenn die Richtlinie angewendet wird.
  
Außerdem werden Dokumentlöschrichtlinien vererbt. Wenn Sie eine Richtlinie oder Regel für Ihre Website auswählen, wird diese Auswahl von allen Unterwebsites geerbt. Der Besitzer einer Website kann die Vererbung allerdings durch Auswahl einer anderen Richtlinie oder Regel unterbrechen. Berücksichtigen Sie bei der Auswahl einer Richtlinie oder Regel die Inhalte aller Unterwebsites unterhalb Ihrer Website.
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a>Anzeigen der in einer Websitesammlung verfügbaren Dokumentlöschrichtlinien

Ihr Unternehmen kann unterschiedlichen Websitesammlungen unterschiedliche Richtlinien zuweisen. Auf Ebene der Websitesammlung kann der Besitzer einer Websitesammlung alle Dokumentlöschrichtlinien anzeigen, die für diese Websitesammlung verfügbar sind. Die Richtlinien wurden möglicherweise für die Websitesammlungsvorlage (und somit für alle mit dieser Vorlage erstellten Websitesammlungen) oder für diese bestimmte Websitesammlung verfügbar gemacht.
  
1. Wählen Sie auf der Website auf oberster Ebene in der Websitesammlung in der oberen rechten Ecke **Einstellungen** [Zahnradsymbol] \> **Websiteeinstellungen**aus.
    
2. **Dokument Löschungsrichtlinien**unter **Websitesammlungsverwaltung** \> .
    
    > [!NOTE]
    > Der Link **Dokument Löschungsrichtlinien** wird nur angezeigt, wenn der Websitesammlung Richtlinien zugewiesen wurden. Außerdem wird der Link nicht unmittelbar nach dem Zuweisen von Richtlinien zur Website angezeigt – es kann bis zu 24 Stunden dauern, bis die Richtlinien zugewiesen sind, wenn der Link **Dokument Löschungsrichtlinien** angezeigt wird. 
  
3. Auf dieser Seite können Sie Folgendes anzeigen:
    
  - Die aktuell zugewiesenen Richtlinien und die zugehörigen Regeln. Wählen Sie eine Richtlinie aus, um die Regeln im rechten Fenster anzuzeigen.
    
  - Bei der Standardrichtlinie, falls vorhanden, steht in der Spalte **Standard****Ja**. 
    
  - Unterhalb der Liste wird eine Meldung angezeigt, wenn die Richtlinie als **Verpflichtend** zugewiesen wurde.
    
Diese Liste ist schreibgeschützt und dient dem Websitesiteeigentümer dazu, alle verfügbaren Richtlinien und Regeln anzuzeigen. Informationen zum Anwenden einer Richtlinie finden Sie im nächsten Abschnitt.
  
![Ansicht der einer Websitesammlung zugewiesenen Dokument Löschungsrichtlinien](../media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Anwenden oder Entfernen einer Dokumentlöschrichtlinie für eine Website

Für Sie als Besitzer einer Website oder Websitesammlung gibt es in Ihrem Unternehmen möglicherweise Richtlinien, die Sie auf Ihre Website anwenden oder komplett abwählen können.
  
1. Wählen Sie in der oberen rechten Ecke **Einstellungen** [Zahnradsymbol] \> **Websiteeinstellungen**aus.
    
2. **Dokument Löschungsrichtlinien**unter **Websiteverwaltung** \> .
    
    > [!NOTE]
    > Der Link **Dokument Löschungsrichtlinien** wird nur angezeigt, wenn der Websitesammlung Richtlinien zugewiesen wurden. Außerdem wird der Link nicht unmittelbar nach dem Zuweisen von Richtlinien zur Website angezeigt – es kann bis zu 24 Stunden dauern, bis die Richtlinien zugewiesen sind, wenn der Link **Dokument Löschungsrichtlinien** angezeigt wird. 
  
3. Führen Sie einen der folgenden Schritte aus:
    
  - **So wenden Sie eine Richtlinie an** Wählen Sie eine \> Richtlinie aus wählen Sie eine \> Regel in dieser Richtlinie **Speichern**aus.
    
    In einer Website kann jeweils immer nur eine Richtlinie und eine Regel aktiv sein. Ihr Unternehmen stellt möglicherweise mehrere Richtlinien und Regeln zur Auswahl oder nur eine Richtlinie oder Regel bereit.
    
    ![Option "Richtlinie auswählen"](../media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - **So deaktivieren Sie eine Richtlinie** Wählen Sie **Opt-out: Do Note DELETE** \> **Save**.
    
    Als Websitebesitzer können Sie eine Richtlinie für das Löschen von Dokumenten deaktivieren, wenn Sie feststellen, dass die Richtlinie nicht für den Inhalt Ihrer Website gilt. Sie können jedoch keine Richtlinie deaktivieren, die als **obligatorisch**gekennzeichnet wurde.
    
    ![Opt-out-Option](../media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a>Dokumentlöschrichtlinien haben Vorrang vor anderen Richtlinien

Eine Website verwendet möglicherweise andere Richtlinie für die Aufbewahrung und Löschung von Inhalten:
  
- Inhaltstyprichtlinien für die Websitesammlung.
    
- Informationsverwaltungsrichtlinien für eine Liste oder Bibliothek.
    
Wenn Sie eine Dokumentlöschrichtlinie auf eine Website anwenden, die für eine Liste oder Bibliothek bereits Inhaltstyp- oder Informationsverwaltungsrichtlinien verwendet, werden diese Richtlinien ignoriert, während die Dokumentlöschrichtlinie angewendet wird. Wenn andere Richtlinien ignoriert werden, wird die Meldung "Inhalt auf dieser Website verwendet Dokument Löschungsrichtlinien" angezeigt.
  
Das bedeutet, dass Sie für eine Website nur Richtlinien verwenden sollten, die für strukturierte Inhalte (Informationsverwaltungs- und Inhaltstyprichtlinien) oder unstrukturierte Inhalte (Dokumentlöschungsrichtlinien) gedacht sind, und nicht beide Arten von Richtlinien. Wenn Sie eine Richtlinie für das Löschen von Dokumenten ablehnen, wird die Warnung nicht angezeigt, und andere Richtlinientypen funktionieren weiterhin.
  
Websiterichtlinien sind von Dokumentlöschungsrichtlinien nicht betroffen.
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a>Prüfen, ob Inhaltstyprichtlinien ignoriert werden

Wenn Ihre Website Inhaltstyprichtlinien verwendet hat und nun diese Meldung angezeigt wird, werden diese Richtlinien nicht mehr angewendet. Wenn Sie die Richtlinien für den Inhaltstyp wiederherstellen möchten, können Sie die Richtlinie für das Löschen von Dokumenten aus Ihrer Website entfernen (siehe oben beschrieben), wenn eine Opt-out-Option zur Verfügung steht. Wenn keine Option zum Deaktivieren vorhanden ist, ist die Richtlinie für das Löschen von Dokumenten zwingend erforderlich, und Sie müssen sich an den Compliance Officer in Ihrer Organisation wenden.
  
1. Wählen Sie in der oberen rechten Ecke **Einstellungen** [Zahnradsymbol] \> **Websiteeinstellungen**aus.
    
2. Unter **Inhaltstyp Richtlinienvorlagen**für **Websiteverwaltung** \> .
    
    ![Warnung vor der Website, dass Dokument Löschungsrichtlinien verwendet werden](../media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a>Prüfen, ob Informationsverwaltungsrichtlinien ignoriert werden

Wenn Ihre Website Informationsverwaltungsrichtlinien verwendet hat und nun diese Meldung angezeigt wird, werden diese Richtlinien nicht mehr angewendet. Um die Richtlinien für die Informationsverwaltung wiederherzustellen, können Sie die Dokument Löschungs Richtlinie wie oben beschrieben aus Ihrer Website entfernen, wenn eine Opt-out-Option zur Verfügung steht. Wenn keine Option zum Deaktivieren vorhanden ist, ist die Richtlinie für das Löschen von Dokumenten zwingend erforderlich, und Sie müssen sich an den Compliance Officer in Ihrer Organisation wenden.
  
- Für eine Liste oder Bibliothek auf der Registerkarte \> **** \> **Bibliothekseinstellungen** \> der Menü Bandbibliothek unter **Berechtigungen und Verwaltungs** \> **Informationsverwaltungsrichtlinien Einstellungen**.
    
    ![Warnung vor der Website, dass Dokument Löschungsrichtlinien verwendet werden](../media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a>Siehe auch

[Übersicht über Dokumentlöschrichtlinien](document-deletion-policies.md)
  
[Erstellen einer Dokumentlöschrichtlinie](create-a-document-deletion-policy.md)

