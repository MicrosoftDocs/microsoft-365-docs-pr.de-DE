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
ms.openlocfilehash: 626549401f463ca7a28a0cdd8948f710a5128f08
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287515"
---
# <a name="create-and-apply-information-management-policies"></a>Erstellen und Anwenden von Informationsverwaltungsrichtlinien

Informationsverwaltungsrichtlinien ermöglichen Es Ihrer Organisation, zu steuern, wie lange Inhalte aufbewahrt werden sollen, um zu überwachen, was Personen mit Inhalten tun, und Strichcodes oder Bezeichnungen zu Dokumenten hinzuzufügen. Eine Richtlinie kann dazu beitragen, die Einhaltung gesetzlicher und behördlicher Vorschriften oder interner Geschäftsprozesse zu erzwingen. Als Administrator können Sie eine Richtlinie einrichten, um zu steuern, wie Dokumente nachverfolgt und wie lange Dokumente aufbewahrt werden.

Sie können eine Informationsverwaltungsrichtlinie an drei verschiedenen Speicherorten in der Websitehierarchie erstellen, von der breitesten bis zur engsten:

- Erstellen Sie eine Richtlinie, die für mehrere Inhaltstypen in einer Websitesammlung verwendet werden soll.
- Erstellen Sie eine Richtlinie für einen Websiteinhaltstyp.
- Erstellen Sie eine Richtlinie für eine Liste oder Bibliothek.

Weitere Informationen finden Sie unter ["Einführung in Informationsverwaltungsrichtlinien".](intro-to-info-mgmt-policies.md)

## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>Erstellen einer Richtlinie für mehrere Inhaltstypen in einer Websitesammlung
<a name="__toc261001590"> </a>

Um sicherzustellen, dass eine Informationsrichtlinie auf alle Dokumente eines bestimmten Typs innerhalb einer Websitesammlung angewendet wird, sollten Sie die Richtlinie auf Websitesammlungsebene erstellen und die Richtlinie später auf Inhaltstypen anwenden. Diese werden als Websitesammlungsrichtlinien bezeichnet.

1. Auf der Homepage der Websitesammlung \> **Einstellungen** ![ SharePoint 2016 Einstellungen Schaltfläche in der Titelleiste.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Websiteeinstellungen**.

    Klicken Sie in einer SharePoint mit einer Gruppe verbundenen Website auf **Einstellungen,** klicken Sie auf **"Websiteinhalte"** und dann auf **"Website Einstellungen".**

2. Auf der Seite "Website Einstellungen" unter "Inhaltstyprichtlinienvorlagen für **die Websitesammlungsverwaltung".** \> 

   ![Link "Inhaltstyprichtlinienvorlage" auf der Seite "Website Einstellungen"](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)

3. Auf der Seite \> **"Richtlinien" erstellen**.

4. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein, und schreiben Sie dann eine kurze Richtlinienanweisung, in der den Benutzern erläutert wird, wofür die Richtlinie gilt.

5. Im nächsten Abschnitt zum Erstellen von Richtlinien für einen Websiteinhaltstyp erfahren Sie, wie Sie die Features einrichten, die Sie der Richtlinie zuordnen möchten.

6. Wählen Sie **OK** aus.

## <a name="create-a-policy-for-a-site-content-type"></a>Erstellen einer Richtlinie für einen Websiteinhaltstyp
<a name="__create_a_policy"> </a>

Das Hinzufügen einer Informationsverwaltungsrichtlinie zu einem Inhaltstyp erleichtert das Zuordnen von Richtlinienfeatures zu mehreren Listen oder Bibliotheken. Sie können eine vorhandene Informationsverwaltungsrichtlinie zu einem Inhaltstyp hinzufügen oder eine eindeutige Richtlinie erstellen, die für einen einzelnen Inhaltstyp spezifisch ist.

 Sie können auch eine Informationsverwaltungsrichtlinie zu einem Inhaltstyp hinzufügen, der für Listen spezifisch ist. Dies hat zur Auswirkung, dass die Richtlinie nur auf Elemente in dieser Liste angewendet wird, die den Inhaltstyp verwenden.

1. Auf der Homepage der Websitesammlung \> **Einstellungen** ![ SharePoint 2016 Einstellungen Schaltfläche in der Titelleiste.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Websiteeinstellungen**.

    Klicken Sie in einer SharePoint mit einer Gruppe verbundenen Website auf **Einstellungen,** klicken Sie auf **"Websiteinhalte"** und dann auf **"Website Einstellungen".**

2. On the Site Einstellungen page, under **Web Designer Galleries** Site content \> **types**.

   ![Link zu Websiteinhaltstypen auf website Einstellungen Seite](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)

3. Wählen Sie auf der Seite "Websiteinhaltstyp Einstellungen" den Inhaltstyp aus, dem Sie eine Richtlinie hinzufügen möchten.

4. Auf der Seite "Websiteinhaltstyp" unter **Einstellungen** \> **Richtlinieneinstellungen für die Informationsverwaltung.**

5. Geben Sie auf der Seite "Richtlinie bearbeiten" einen Namen und eine Beschreibung für die Richtlinie ein, und schreiben Sie dann eine kurze Beschreibung, in der den Benutzern erläutert wird, wofür die Richtlinie vorgesehen ist.

6. Wählen Sie in den nächsten Abschnitten die einzelnen Richtlinienfeatures aus, die Sie Ihrer Informationsverwaltungsrichtlinie hinzufügen möchten.

   ![Typen von Inhaltsrichtlinien](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)

7. Um einen Aufbewahrungszeitraum für Dokumente und Elemente anzugeben, die dieser Richtlinie unterliegen, wählen Sie **"Aufbewahrung aktivieren"** aus, und geben Sie dann den Aufbewahrungszeitraum und die Aktionen an, die ausgeführt werden sollen, wenn die Elemente ablaufen.

   So geben Sie einen Aufbewahrungszeitraum an:

   1. Wählen **Sie "Aufbewahrungsphase für Datensätze hinzufügen" aus.**

   2. Wählen Sie eine Option für den Aufbewahrungszeitraum aus, um anzugeben, wann Dokumente oder Elemente ablaufen sollen. Führen Sie einen der folgenden Schritte aus:
      - To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item,** and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.
      - Wenn Sie eine benutzerdefinierte Aufbewahrungsformel verwenden möchten, um den Ablauf zu bestimmen, wählen Sie **"Festlegen durch eine benutzerdefinierte Aufbewahrungsformel" aus, die auf diesem Server installiert ist.**

        > [!NOTE]
        > Diese Option ist nur verfügbar, wenn vom Administrator eine benutzerdefinierte Formel eingerichtet wurde.

   3. Die **Option "Workflow starten"** ist nur verfügbar, wenn Sie eine Richtlinie für eine Liste, Bibliothek oder einen Inhaltstyp definieren, der bereits ein Workflow zugeordnet ist. Sie erhalten dann eine Auswahl von Workflows zur Auswahl.

   4. Wählen Sie im Abschnitt **"Serie"** die **Option "Aktion dieser Phase wiederholen" aus...** und geben Sie an, wie oft die Aktion wiederholt werden soll.

      > [!NOTE]
      >  Diese Option ist nur verfügbar, wenn die ausgewählte Aktion wiederholt werden kann. Sie können z. B. keine Serie für die Aktion **"Endgültig löschen"** festlegen.

   5. Ok ausgewählt.

8. Um die Überwachung für die Dokumente und Elemente zu aktivieren, die dieser Richtlinie unterliegen, wählen Sie Überwachung **aktivieren** aus, und geben Sie dann die Ereignisse an, die Sie überwachen möchten.

   So aktivieren Sie die Überwachung:

   1. Wählen Sie auf der Seite "Richtlinie bearbeiten" unter **"Überwachung"** die Option **"Überwachung aktivieren"** aus, und aktivieren Sie dann die Kontrollkästchen neben den Ereignissen, für die Sie einen Überwachungspfad beibehalten möchten.

   2. Um Benutzer aufzufordern, diese Barcodes in Dokumente einzufügen, wählen Sie **"Benutzer auffordern" aus, vor dem Speichern oder Drucken einen Strichcode einzufügen.**

   3. Wählen Sie **"OK"** aus, um das Überwachungsfeature auf die Richtlinie anzuwenden.

   Mit dem Feature "Überwachungsrichtlinie" können Organisationen Überwachungsprotokolle für Dokumente und Listenelemente wie Aufgabenlisten, Problemlisten, Diskussionsgruppen und Kalender erstellen und analysieren. Mit diesem Richtlinienfeature wird ein Überwachungsprotokoll bereitgestellt, das Ereignisse wie beispielsweise, wenn Inhalt angezeigt, bearbeitet oder gelöscht wird, aufzeichnet.

   Wenn die Überwachung als Teil einer Informationsverwaltungsrichtlinie aktiviert ist, können Administratoren die Überwachungsdaten in Richtliniennutzungsberichten anzeigen, die auf Microsoft Excel basieren und die die aktuelle Nutzung zusammenfassen. Administratoren können mithilfe dieser Berichte feststellen, wie Informationen innerhalb der Organisation verwendet werden. Diese Berichte können Organisationen auch dabei helfen, die Einhaltung gesetzlicher Vorschriften zu überprüfen und zu dokumentieren oder potenzielle Bedenken zu untersuchen.

   Im Überwachungsprotokoll werden folgende Informationen aufgezeichnet: Ereignisname, Datum und Uhrzeit des Ereignisses sowie der Systemname des Benutzers, der die Aktion ausgeführt hat.

9. Wenn Barcodes als Teil einer Richtlinie aktiviert sind, werden sie dokumenteigenschaften hinzugefügt und im Kopfbereich des Dokuments angezeigt, auf das der Strichcode angewendet wird. Wie Bezeichnungen können Barcodes auch manuell aus einem Dokument entfernt werden. Sie können angeben, ob Benutzer aufgefordert werden sollen, den Strichcode beim Drucken oder Speichern eines Elements einzuschließen, oder ob der Barcode manuell mithilfe der Registerkarte **"Einfügen"** in 2010 Office Releaseprogrammen eingefügt werden soll.

   So aktivieren Sie Barcodes:

   1. Wählen Sie auf der Seite **"Richtlinie bearbeiten"** unter **"Barcodes"** die Option **"Barcodes aktivieren" aus.**

   2. Um Benutzer aufzufordern, diese Barcodes in Dokumente einzufügen, wählen Sie **"Benutzer auffordern" aus, vor dem Speichern oder Drucken einen Strichcode einzufügen.**

   3. Wählen Sie **"OK"** aus, um die Strichcodefunktion auf die Richtlinie anzuwenden.

   Die Strichcoderichtlinie generiert Code 39-Standardstrichcodes. Jedes Strichcodebild enthält Text unterhalb des Strichcodesymbols, das den Strichcodewert darstellt. Dadurch können die Strichcodedaten auch dann verwendet werden, wenn die Überprüfung der Hardware nicht verfügbar ist. Benutzer können die Strichcodenummer manuell in das Suchfeld eingeben, um das Element auf einer Website zu suchen.  <br/> |

10. Um festzulegen, dass Dokumente, die dieser Richtlinie unterliegen, Bezeichnungen aufweisen, wählen Sie **Bezeichnungen aktivieren** aus, und geben Sie dann die gewünschten Einstellungen für die Bezeichnungen an.

    So aktivieren Sie Bezeichnungen:

    1. Um festzulegen, dass Benutzer einem Dokument eine Bezeichnung hinzufügen müssen, wählen Sie **"Benutzer auffordern" aus, vor dem Speichern oder Drucken eine Bezeichnung einzufügen.**

       > [!NOTE]
       > Aktivieren Sie dieses Kontrollkästchen nicht, wenn Bezeichnungen optional sein sollen. 

    2. Wenn Sie eine Bezeichnung sperren möchten, damit sie nach dem Einfügen nicht mehr geändert werden kann, wählen Sie **"Änderungen an Bezeichnungen verhindern" aus, nachdem sie hinzugefügt wurden.**

       Diese Einstellung verhindert, dass der Bezeichnungstext aktualisiert wird, sobald die Bezeichnung in ein Element in einer Clientanwendung wie Word, Excel oder PowerPoint eingefügt wurde. Aktivieren Sie dieses Kontrollkästchen nicht, falls die Bezeichnung aktualisiert werden soll, wenn die Eigenschaften für dieses Dokument oder Element aktualisiert werden.

    3. Geben Sie im Feld "Bezeichnungsformat" den Text für die Beschriftung so ein, wie sie angezeigt werden soll. Beschriftungen können bis zu 10 Spaltenbezüge enthalten, von denen jedes bis zu 255 Zeichen lang sein kann. Führen Sie die folgenden Schritte aus, um das Format für Ihre Bezeichnung zu erstellen:
       - Geben Sie die Namen der Spalten, die Sie in die Beschriftung einschließen möchten, in der Reihenfolge ein, in der sie angezeigt werden sollen. Schließen Sie die Spaltennamen in geschweifte Klammern ( ) ein, {} wie im Beispiel auf der Seite "Richtlinie bearbeiten" dargestellt.
       - Geben Sie Wörter ein, um die Spalten außerhalb der Klammern zu identifizieren, wie im Beispiel auf der Seite "Richtlinie bearbeiten" dargestellt.

    4. Um einen Zeilenumbruch hinzuzufügen, geben Sie **\n** ein, an der der Zeilenumbruch angezeigt werden soll.

    5. Wählen Sie den gewünschten Schriftgrad und -stil aus, und geben Sie an, ob die Beschriftung links, zentriert oder rechts im Dokument positioniert werden soll.

       Wählen Sie eine Schriftart und ein Format aus, die auf den Benutzercomputern verfügbar sind. Es hängt vom Schriftgrad ab, wie viel Text auf der Bezeichnung angezeigt werden kann.

    6. Geben Sie die Höhe und Breite der Beschriftung ein. Die Höhe der Bezeichnungen kann zwischen 0,25 und 20 Zoll liegen, und die Beschriftungsbreite kann zwischen 0,25 und 20 Zoll liegen. Beschriftungstext wird im Bezeichnungsbild immer vertikal zentriert.

    7. Wählen Sie **"Aktualisieren"** aus, um eine Vorschau des Bezeichnungsinhalts anzuzeigen.

11. Wählen Sie **OK** aus.

## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>Erstellen einer Richtlinie für eine Liste, Bibliothek oder einen Ordner (standortbasierte Aufbewahrungsrichtlinie)
<a name="__create_a_policy"> </a>

Sie können eine Aufbewahrungsrichtlinie definieren, die nur für eine bestimmte Liste, Bibliothek oder einen bestimmten Ordner gilt. Wenn Sie jedoch eine Aufbewahrungsrichtlinie auf diese Weise erstellen, können Sie diese Richtlinie nicht für andere Listen, Bibliotheken, Ordner oder Websites wiederverwenden und keine Websitesammlungsrichtlinie auf eine standortbasierte Richtlinie anwenden.

Wenn Sie eine einzelne Aufbewahrungsrichtlinie auf alle Arten von Inhalten an einem einzigen Speicherort anwenden möchten, sollten Sie höchstwahrscheinlich die standortbasierte Aufbewahrung verwenden. In den meisten anderen Fällen sollten Sie überprüfen, ob eine Aufbewahrungsrichtlinie für alle Inhaltstypen angegeben ist.

Jeder Unterordner erbt die Aufbewahrungsrichtlinie des übergeordneten Elements, es sei denn, Sie möchten die Vererbung unterbrechen und eine neue Aufbewahrungsrichtlinie auf untergeordneter Ebene definieren.

Wenn Sie eine andere Informationsverwaltungsrichtlinie als die Aufbewahrung in einer Liste oder Bibliothek definieren möchten, müssen Sie eine Informationsverwaltungsrichtlinie für jeden einzelnen Listeninhaltstyp definieren, der dieser Liste oder Bibliothek zugeordnet ist.

Wenn Sie zu einem beliebigen Zeitpunkt von einem Inhaltstyp zu standortbasierten Richtlinien für eine Liste oder Bibliothek wechseln möchten, wird nur die Aufbewahrungsrichtlinie als standortbasierte Richtlinie verwendet. Alle anderen Verwaltungsrichtlinien (Audits, Barcodes und Barcodes) werden von den zugeordneten Inhaltstypen geerbt.

Standortbasierte Richtlinien können für eine Websitesammlung deaktiviert werden, indem das Feature "Bibliotheks- und ordnerbasierte Aufbewahrung" deaktiviert wird. Dadurch können Websitesammlungsadministratoren sicherstellen, dass ihre Inhaltstyprichtlinien nicht von den standortbasierten Richtlinien eines Listenadministrators überschrieben werden.

Sie benötigen mindestens die Berechtigung "Listen verwalten", um die Richtlinieneinstellungen für die Informationsverwaltung für eine Liste oder Bibliothek zu ändern.

1. Navigieren Sie zu der Liste oder Bibliothek, für die Sie eine Informationsverwaltungsrichtlinie angeben möchten.

2. Wählen Sie im Menüband **die** Registerkarte Bibliotheks- oder **Listenregisterkarte** \> **Bibliothek Einstellungen** oder **Liste Einstellungen** aus.

   Klicken Sie in SharePoint Online auf **Einstellungen** und dann auf **Listeneinstellungen** oder **Bibliothekseinstellungen.**

3. Unter **Berechtigungen und Richtlinieneinstellungen** für \> **die Verwaltung von Verwaltungsinformationen.**

   ![Link zu Informationsverwaltungsrichtlinien auf der Einstellungsseite für die Dokumentbibliothek](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)

4. Stellen Sie auf der Seite "Informationsverwaltungsrichtlinie Einstellungen" sicher, dass die Quelle der Aufbewahrung für die Liste oder Bibliothek auf "Bibliothek und Ordner" festgelegt ist.

   Wenn **der Inhaltstyp** als Quelle angezeigt wird, klicken Sie auf **"Quelle ändern"** und dann auf **"Bibliothek und Ordner".** Sie werden benachrichtigt, dass Aufbewahrungsrichtlinien für Inhaltstypen ignoriert werden. Wählen Sie **OK** aus.

5. Geben Sie auf der Seite "Richtlinie bearbeiten" unter **"Bibliotheksbasierter Aufbewahrungszeitplan"** eine kurze Beschreibung für die Richtlinie ein, die Sie erstellen.

6. Wählen Sie **"Aufbewahrungsphase hinzufügen" aus...**

   Beachten Sie, dass Sie unter "Datensätze" unterschiedliche Aufbewahrungsrichtlinien für Datensätze definieren können, indem Sie die Option "Verschiedene Aufbewahrungsphasen für Datensätze definieren" auswählen.

7. Wählen Sie im Dialogfeld "Phaseneigenschaften" eine Option für den Aufbewahrungszeitraum aus, um anzugeben, wann Dokumente oder Elemente ablaufen sollen. Führen Sie einen der folgenden Schritte aus:

   - To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item,** and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.

   - Wenn Sie eine benutzerdefinierte Aufbewahrungsformel verwenden möchten, um den Ablauf zu bestimmen, wählen Sie **"Festlegen durch eine benutzerdefinierte Aufbewahrungsformel" aus, die auf diesem Server installiert ist.**

     > [!NOTE]
     >  Diese Option ist nur verfügbar, wenn vom Administrator eine benutzerdefinierte Formel eingerichtet wurde.

   - Geben Sie unter **"Aktion"** an, was passieren soll, wenn das Dokument oder Element abläuft. Um eine bestimmte Aktion für das Dokument oder Element (z. B. löschen) zu aktivieren, wählen Sie eine Aktion aus der Liste aus.

8. Die **Option "Workflow starten"** ist nur verfügbar, wenn Sie eine Richtlinie für eine Liste, Bibliothek oder einen Inhaltstyp definieren, der bereits ein Workflow zugeordnet ist. Sie erhalten dann eine Auswahl von Workflows zur Auswahl.

9. Wählen Sie unter **"Serie"** **die Option "Aktion dieser Phase wiederholen" aus...** und geben Sie an, wie oft die Aktion wiederholt werden soll.

   > [!NOTE]
   >  Diese Option ist nur verfügbar, wenn die ausgewählte Aktion wiederholt werden kann. Sie können z. B. keine Serie für die Aktion **"Endgültig löschen"** festlegen.

10. Wählen Sie **OK** aus.

## <a name="apply-a-site-collection-policy-to-a-content-type"></a>Anwenden einer Websitesammlungsrichtlinie auf einen Inhaltstyp
<a name="__apply_a_site"> </a>

Wenn Informationsverwaltungsrichtlinien für Ihre Website bereits als Websitesammlungsrichtlinien erstellt wurden, können Sie eine der Richtlinien auf einen Inhaltstyp anwenden. Auf diese Weise können Sie dieselbe Richtlinie auf mehrere Inhaltstypen in einer Websitesammlung anwenden, die nicht denselben übergeordneten Inhaltstyp gemeinsam verwenden.

 Wenn Sie Richtlinien auf mehrere Inhaltstypen in einer Websitesammlung anwenden möchten und ein verwalteter Metadatendienst konfiguriert ist, können Sie die Inhaltstypveröffentlichung verwenden, um Informationsverwaltungsrichtlinien in mehreren Websitesammlungen zu veröffentlichen. Weitere Informationen finden Sie im Abschnitt ["Anwenden einer Richtlinie in allen Websitesammlungen".](#apply-a-policy-across-site-collections)

1. Navigieren Sie zu der Liste oder Bibliothek, die den Inhaltstyp enthält, auf den Sie eine Richtlinie anwenden möchten.

2. Wählen Sie im Menüband **die** Registerkarte Bibliotheks- oder **Listenregisterkarte** \> **Bibliothek Einstellungen** oder **Liste Einstellungen** aus.

   Klicken Sie in SharePoint Online auf **Einstellungen** und dann auf **Listeneinstellungen** oder **Bibliothekseinstellungen.**

3. Unter **Berechtigungen und Richtlinieneinstellungen** für \> **die Verwaltung von Verwaltungsinformationen.**

   ![Link zu Informationsverwaltungsrichtlinien auf der Einstellungsseite für die Dokumentbibliothek](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)

4. Stellen Sie sicher, dass die Richtlinienquelle auf **Inhaltstypen** festgelegt ist, und wählen Sie unter **"Inhaltstyprichtlinien"** den Inhaltstyp aus, auf den Sie die Richtlinie anwenden möchten.

5. Under **Specify the Policy** Use a site collection \> **policy**, and then select the policy that you want to apply from the list.

   > [!NOTE]
   >  Wenn die Option **"Websitesammlungsrichtlinie verwenden"** nicht verfügbar ist, wurden keine Websitesammlungsrichtlinien für die Websitesammlung definiert.

6. Wählen Sie **OK** aus.

   Wenn die Liste oder Bibliothek, mit der Sie arbeiten, die Verwaltung mehrerer Inhaltstypen unterstützt, können Sie unter **"Inhaltstypen"** den Inhaltstyp auswählen, für den Sie eine Informationsverwaltungsrichtlinie angeben möchten. Dadurch gelangen Sie direkt zu Schritt 5 oben.

## <a name="apply-a-policy-across-site-collections"></a>Anwenden einer Richtlinie in allen Websitesammlungen
<a name="__toc260646789"> </a>

Freigeben von Inhaltstypen in allen Websitesammlungen mithilfe einer Dienstanwendung für verwaltete Metadaten zum Einrichten der Inhaltstypveröffentlichung. Die Inhaltstypveröffentlichung hilft Ihnen bei der konsistenten Verwaltung von Inhalten und Metadaten auf allen Websites, da Inhaltstypen zentral erstellt und aktualisiert werden können und Updates für mehrere abonnierende Websitesammlungen oder Webanwendungen veröffentlicht werden können.

## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>Erstellen einer Vorlage aus einer vorhandenen Richtlinie zur Verwendung in allen Websitesammlungen
<a name="__toc262125409"> </a>

Sie können eine Informationsverwaltungsrichtlinie definieren und dann eine Vorlage erstellen, die nach Bedarf in mehreren Websitesammlungen verwendet werden kann. Diese Methode kann verwendet werden, wenn Sie eine Sicherung Ihrer Informationsrichtlinien wünschen, oder sie kann auch als alternative Methode für die Verwendung der Inhaltstypveröffentlichung zum Anwenden einer Richtlinie in allen Websitesammlungen verwendet werden. Sie erstellen eine Vorlage oder Sicherung der Richtlinie, indem Sie die Richtlinie aus einer Websitesammlung exportieren und sie dann an einen gespeicherten Speicherort oder in eine andere Websitesammlung importieren.

> [!IMPORTANT]
> Wenn Sie das Export-/Importfeature zum Erstellen eines Satzes von Richtlinienvorlagen verwenden, beachten Sie, dass in der Richtlinie .xml Datei ein eindeutiger Bezeichner vorhanden ist. Aus diesem Grund können Sie diese Richtlinie nicht mehrmals in eine Website importieren, ohne diesen eindeutigen Bezeichner zu ändern.

### <a name="export-a-policy"></a>Exportieren einer Richtlinie
<a name="__toc260646790"> </a>

1. Wählen Sie auf der Startseite der Websitesammlung **Einstellungen** Kleine Einstellungen Zahnrad aus, ![ das anstelle von Site Einstellungen wurde. ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Website Einstellungen**.

   Klicken Sie in einer SharePoint mit einer Gruppe verbundenen Website auf **Einstellungen,** klicken Sie auf **"Websiteinhalte"** und dann auf **"Website Einstellungen".**

2. Auf der Seite "Website Einstellungen" unter "Inhaltstyprichtlinienvorlagen für **die Websitesammlungsverwaltung".** \> 

   ![Link "Inhaltstyprichtlinienvorlage" auf der Seite "Website Einstellungen"](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)

3. Wählen Sie die Richtlinie aus, die Sie exportieren \> möchten, scrollen Sie nach \> **unten.**

4. Wählen Sie an der Eingabeaufforderung zum Speichern oder Öffnen der Datei **"Speichern"** aus, und wählen Sie dann einen Speicherort aus, an dem die Datei gespeichert werden soll. Achten Sie darauf, einen Speicherort auszuwählen, der für die Websitesammlungen verfügbar ist, die die Richtlinie importieren.

5. Wenn das Dialogfeld "Vollständig herunterladen" angezeigt wird, wählen Sie **"Schließen"** aus.

### <a name="import-a-policy-to-a-different-site-collection"></a>Importieren einer Richtlinie in eine andere Websitesammlung
<a name="__toc260646791"> </a>

Mit dem Importieren einer Informationsverwaltungsrichtlinie können Sie sie auf mehrere Inhaltstypen auf Website- oder Listenebene innerhalb einer bestimmten Websitesammlung anwenden. Die Vorteile dieser Vorgehensweise sind zwei: Sie müssen die Richtlinie nicht neu definieren und auf jeden Inhaltstyp anwenden, und Sie können Richtlinienänderungen einfacher verwalten, indem Sie Änderungen an der Richtlinie an nur einem Ort vornehmen.

1. Wählen Sie auf der Startseite der Websitesammlung, auf die Sie die Richtlinie anwenden möchten, **Einstellungen** Kleine Einstellungen Zahnrad aus, ![ das anstelle der Website Einstellungen wurde. ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Website Einstellungen**.

   Klicken Sie in einer SharePoint mit einer Gruppe verbundenen Website auf **Einstellungen,** klicken Sie auf **"Websiteinhalte"** und dann auf **"Website Einstellungen".**

2. Auf der Seite "Website Einstellungen" unter "Inhaltstyprichtlinienvorlagen für **die Websitesammlungsverwaltung".** \> 

3. Suchen Sie auf der Seite \> **"Richtlinien"** \> **"Durchsuchen",** um die XML-Datei für die Richtlinie zu finden.

4. Wählen Sie die XML-Datei aus, in der die Richtlinie gespeichert \> **wurde. Öffnen**.

5. Fügen Sie auf der Seite "Websitesammlungsrichtlinie importieren" \>  die Richtlinie der Websitesammlung hinzu.

Ihre importierte Richtlinie kann jetzt auf einen oder viele Inhaltstypen auf Website- oder Listenebene angewendet werden.

Informationsverwaltungsrichtlinien ermöglichen Es Ihrer Organisation, zu steuern, wie lange Inhalte aufbewahrt werden sollen, um zu überwachen, was Personen mit Inhalten tun, und Strichcodes oder Bezeichnungen zu Dokumenten hinzuzufügen. Eine Richtlinie kann dazu beitragen, die Einhaltung gesetzlicher und behördlicher Vorschriften oder interner Geschäftsprozesse zu erzwingen. Als Administrator können Sie eine Richtlinie einrichten, um zu steuern, wie Dokumente nachverfolgt und wie lange Dokumente aufbewahrt werden.

Sie können eine Informationsverwaltungsrichtlinie an drei verschiedenen Speicherorten in der Websitehierarchie erstellen, von der breitesten bis zur engsten:

- Erstellen Sie eine Richtlinie, die für mehrere Inhaltstypen in einer Websitesammlung verwendet werden soll.
- Erstellen Sie eine Richtlinie für einen Websiteinhaltstyp.
- Erstellen Sie eine Richtlinie für eine Liste oder Bibliothek.

Weitere Informationen finden Sie unter ["Einführung in Informationsverwaltungsrichtlinien".](intro-to-info-mgmt-policies.md)
