---
title: Arbeiten mit Bewertungsvorlagen im Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informationen zum Verwenden und Verwalten von Vorlagen zum Erstellen von Bewertungen in Microsoft Compliance Manager. Erstellen und Ändern von Vorlagen mithilfe einer formatierten Excel-Datei.
ms.openlocfilehash: 2d95aa4172d80a81e8c635edb01ab56579513c53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922785"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Arbeiten mit Bewertungsvorlagen im Compliance-Manager

**In diesem Artikel:** Erfahren **Sie, wie Vorlagen funktionieren** und wie Sie sie **auf** ihrer Bewertungsvorlagenseite verwalten. Erhalten Sie Anweisungen **zum Erstellen** neuer Vorlagen, **zum Ändern** vorhandener Vorlagen, zum Formatieren der **Vorlagendaten mit Excel** und zum Exportieren von **Vorlagenberichten.**

> [!IMPORTANT]
> Die Bewertungsvorlagen, die Für Ihre Organisation verfügbar sind, hängen von Ihrem Lizenzvertrag ab. [Überprüfen Sie die Details](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="templates-overview"></a>Übersicht über Vorlagen

Eine Vorlage ist ein Framework von Steuerelementen zum Erstellen einer Bewertung im Compliance-Manager. Unser umfassender Vorlagensatz kann Ihre Organisation dabei unterstützen, nationale, regionale und branchenspezifische Anforderungen für die Erfassung und Verwendung von Daten zu erfüllen. Wir verweisen auf Vorlagen mit demselben Namen wie die zugrunde liegende Zertifizierung oder Verordnung, z. B. die DSGVO-Vorlage der EU und die ISO 27001:2013-Vorlage.

 Zeigen Sie [die vollständige Liste der Vorlagen an.](compliance-manager-templates-list.md)

## <a name="template-types-included-and-premium-active-and-inactive"></a>Vorlagentypen: eingeschlossen und premium, aktiv und inaktiv

#### <a name="included-and-premium-templates"></a>Enthaltene und Premium-Vorlagen

Die verfügbaren Vorlagen basieren auf dem Lizenzvertrag Ihrer Organisation ([Anzeigen von Lizenzierungsdetails](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)). Es gibt zwei Kategorien von Vorlagen: enthalten und Premium.

1. **Enthaltene** Vorlagen können im Rahmen des Lizenzvertrags Ihrer Organisation verwendet werden.
2. **Premiumvorlagen** müssen erworben werden, um Bewertungen von diesen zu erstellen. Nach dem Kauf können Sie aus einer Vorlage nach Bedarf so viele Bewertungen erstellen.

#### <a name="active-and-inactive-templates"></a>Aktive und inaktive Vorlagen

Vorlagen zeigen den Aktivierungsstatus entweder als aktiv oder inaktiv an:

- Eine Vorlage wird als **aktiv betrachtet,** nachdem Sie eine Bewertung aus dieser Vorlage erstellt haben.
- Eine Vorlage wird als **inaktiv** betrachtet, wenn Ihre Organisation sie nicht als Framework für eine Bewertung verwendet.

Wenn Sie eine Premiumvorlage erwerben und eine Bewertung aus dieser erstellen, ist diese Vorlage ein Jahr aktiv. Ihr Kauf wird automatisch verlängert, es sei denn, Sie kündigen die Verlängerung.

**Zähler für aktivierte Vorlagen**

Ihre Bewertungsseite und Bewertungsvorlagenseite verfügen über einen **aktivierten Vorlagenzähler** ganz oben. Der Indikator zeigt die Anzahl der verwendeten Vorlagen aus der Anzahl an, die gemäß Ihrem Lizenzvertrag verwendet werden kann.

Wenn Ihr Indikator beispielsweise 2/5 zeigt, bedeutet dies, dass Ihre Organisation zwei der fünf verfügbaren Vorlagen aktiviert hat.

Wenn Ihr Indikator 5/2 zeigt, bedeutet dies, dass Ihre Organisation ihre Grenzen überschreitet und 3 der verwendeten Premiumvorlagen erwerben muss.

Weitere [Informationen finden Sie unter Compliance Manager Licensing Guidance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Anzeigen und Verwalten von Vorlagen auf der Seite "Bewertungsvorlagen"

Auf der Seite Bewertungsvorlagen im Compliance-Manager wird eine Liste mit Vorlagen und wichtigen Details angezeigt. Die Liste enthält Vorlagen, die vom Compliance Manager bereitgestellt werden, sowie alle Vorlagen, die Ihre Organisation geändert oder erstellt hat. Sie können Filter anwenden, um eine Vorlage basierend auf zertifizierung, Produktbereich, Land, Branche, wer sie erstellt hat und ob die Vorlage für die Erstellung von Bewertung aktiviert ist.

Wählen Sie eine Vorlage aus der Zeile aus, um die Detailseite anzuzeigen. Diese Seite enthält eine Beschreibung der Vorlage und weitere Informationen zu Zertifizierung, Umfang und Steuerelementdetails. Auf dieser Seite können Sie die entsprechenden Schaltflächen auswählen, um eine Bewertung zu erstellen, die Vorlagendaten nach Excel zu exportieren oder die Vorlage zu ändern.

## <a name="creating-and-modifying-templates-overview"></a>Übersicht über das Erstellen und Ändern von Vorlagen

Um eine vorhandene Vorlage zu ändern oder eine eigene neue Vorlage zu erstellen, verwenden Sie eine speziell formatierte Excel-Kalkulationstabelle[(Beispiel](https://go.microsoft.com/fwlink/?linkid=2124865)herunterladen), um die erforderlichen Steuerelementdaten zusammenstellen zu können. Nachdem Sie die Tabelle abgeschlossen haben, importieren Sie sie während des Erstellens oder Änderns einer Vorlage in den Compliance-Manager.

> [!NOTE]
> Die Kalkulationstabelle verfügt über ein bestimmtes Format und Schema, das verwendet werden muss, oder sie wird nicht ordnungsgemäß in den Compliance-Manager importiert. Die [Formatierungsanweisungen](#formatting-your-template-data-with-excel) sind unten aufgeführt.

**Erforderliche Rollen**

Nur Benutzer, die über eine Rolle "Globaler Administrator" oder "Compliance-Manager"-Verwaltungsrolle enthalten, können Vorlagen erstellen und ändern. Erfahren Sie mehr über [Rollen und Berechtigungen](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

## <a name="create-a-new-template"></a>Erstellen einer neuen Vorlage

Führen Sie die folgenden Schritte aus, um eine eigene neue Vorlage zu erstellen (die zum Erstellen benutzerdefinierter Bewertungen verwendet wird).

1. Wechseln Sie zur **Seite Bewertungsvorlagen** im Compliance-Manager.
2. Wählen **Sie Neue Vorlage erstellen aus.** Ein Vorlagenerstellungs-Assistent wird geöffnet.
3. Wählen Sie den Typ der Vorlage aus, die Sie erstellen möchten. Wählen Sie in diesem Fall **Erstellen einer benutzerdefinierten Vorlage** aus, und wählen Sie dann Weiter **aus.**
4. Wählen Sie auf dem  Bildschirm **Datei** hochladen die Option Durchsuchen aus, um die formatierte Excel-Datei mit allen erforderlichen Vorlagendaten zu suchen und hochzuladen (siehe Anweisungen zum ordnungsgemäßen [Formatieren Der Datei).](#formatting-your-template-data-with-excel)
5. Wenn keine Probleme mit ihrer Datei auftreten, wird der Name der hochgeladenen Datei angezeigt. Wählen **Sie Weiter aus,** um fortzufahren. (Wenn Sie die Datei ändern müssen, wählen Sie **Hochladen einer anderen Datei aus).**
    - Wenn eine Datei einen Fehler enthält, wird in einer Fehlermeldung oben erklärt, was falsch ist. Sie müssen Ihre Datei korrigieren und erneut hochladen. Fehler resultieren, wenn Ihre Kalkulationstabelle nicht ordnungsgemäß formatiert ist oder wenn in bestimmten Feldern ungültige Informationen enthalten sind (weitere Informationen finden Sie in den [Formatierungsanweisungen](#formatting-your-template-data-with-excel)).  
    
6. Der **Bildschirm Überprüfen und Fertig** stellen zeigt die Anzahl der Verbesserungsaktionen und -steuerelemente sowie die maximale Bewertung für die Vorlage an. Wenn Sie zur Genehmigung bereit sind, wählen Sie **Vorlage erstellen aus.** (Wenn Sie Änderungen vornehmen müssen, wählen Sie **Zurück** aus.)
7. Der letzte Bildschirm bestätigt, dass eine neue Vorlage erstellt wurde. Wählen **Sie Fertig** aus, um den Assistenten zu beenden.
8. Sie gelangen zur Detailseite Ihrer neuen Vorlage, auf der Sie [Ihre Bewertung erstellen können.](compliance-manager-assessments.md#create-your-own-custom-assessment)

## <a name="formatting-your-template-data-with-excel"></a>Formatieren der Vorlagendaten mit Excel

Die zum Erstellen von Vorlagen verwendete Excel-Kalkulationstabelle enthält vier Registerkarten, von denen drei erforderlich sind:

1. [Vorlage](#template-tab) (erforderlich)
2. [ControlFamily](#controlfamily-tab) (erforderlich)
3. [Aktionen](#actions-tab) (erforderlich)
4. [Dimensionen](#dimensions-tab) (optional)

Wenn Sie Ihre  **Kalkulationstabelle** mit Vorlagendaten ausfüllen, muss die Tabelle die Registerkarten in der oben aufgeführten Reihenfolge enthalten, andernfalls werden Ihre Daten nicht erfolgreich in eine Vorlage importiert.

##### <a name="template-tab"></a>Registerkarte "Vorlage"

Die **Registerkarte Vorlage** ist erforderlich. Die Informationen auf dieser Registerkarte enthalten Metadaten zur Vorlage. Es sind vier Spalten erforderlich. Die Spalten müssen die Reihenfolge auf dem Excel-Blatt beibehalten, wie unten aufgeführt. Sie können eine eigene Spalte nach **den** vier Spalten hinzufügen, um Eigene Dimensionen zu bieten. Wenn Sie dies tun, stellen  Sie sicher, dass Sie sie mithilfe der folgenden Anweisungen zur Registerkarte Dimensionen [hinzufügen.](#dimensions-tab)

- **title**: Dies ist der Titel für Ihre Vorlage, der eindeutig sein muss. Es kann keinen Namen für eine andere Vorlage freigeben, die Sie im Compliance Manager haben, einschließlich Ihrer eigenen Vorlagen oder einer Compliance-Manager-Vorlage.

- **product**: Dies ist eine erforderliche Dimension. Listet das Produkt auf, das der Vorlage zugeordnet ist.

- **zertifizierung**: Dies ist die Verordnung, die Sie für die Vorlage verwenden.

- **inScopeServices**: Dies sind die Dienste innerhalb des Produkts, das diese Bewertung adressiert (wenn Sie beispielsweise Office 365 als Produkt aufgelistet haben, könnte Microsoft Teams ein In-Scope-Dienst sein). Sie können mehrere Dienste durch zwei Semikolon getrennt auflisten.

> [!NOTE]
> Die Daten, die Sie  in die **Produkt-** und Zertifizierungszellen einfügen, können nach dem Importieren der Kalkulationstabelle zum Erstellen oder Anpassen einer Vorlage nicht bearbeitet werden. Außerdem kann eine Gruppe nicht zwei Bewertungen enthalten, die dieselbe **Produkt-/Zertifizierungskombination** haben. Sie können mehrere Vorlagen mit derselben Produkt-/Zertifizierungskombination verwenden.

##### <a name="controlfamily-tab"></a>Registerkarte "ControlFamily"

Die **Registerkarte ControlFamily** ist erforderlich.  Die erforderlichen Spalten auf dieser Registerkarte, die der in der Beispielkalkulationstabelle angegebenen Reihenfolge folgen müssen, sind:

- **controlName**: Dies ist der Steuerelementname aus der Zertifizierung, dem Standard oder der Vorschrift, die in der Regel eine Art von ID ist. Steuerelementnamen müssen innerhalb einer Vorlage eindeutig sein. In der Kalkulationstabelle können nicht mehrere Steuerelemente mit demselben Namen verwendet werden.

- **controlFamily**: Geben Sie ein Wort oder einen Ausdruck für controlFamily an, das eine breite Gruppierung von Steuerelementen identifiziert. Ein controlFamily muss nicht eindeutig sein. sie kann mehr als einmal in einer Kalkulationstabelle aufgeführt werden. Das gleiche controlFamily kann auch in mehreren Vorlagen aufgeführt werden, hat jedoch keinen Bezug zueinander. Jedes controlFamily-Steuerelement muss mindestens einem Steuerelement zugeordnet sein.

- **controlTitle**: Geben Sie einen Titel für das Steuerelement an. Während controlName ein Referenzcode ist, ist der Titel ein Rich-Text-Format, das in der Regel in den Bestimmungen zu sehen ist.

- **controlDescription**: Geben Sie eine Beschreibung des Steuerelements an.

- **controlActionTitle**: Dies ist der Titel einer Aktion, die Sie mit diesem Steuerelement in Beziehung bringen möchten. Sie können mehrere Aktionen hinzufügen, indem Sie durch zwei Semikolons ohne Leerzeichen dazwischen trennen. Jedes steuerelement, das Sie auflisten, muss mindestens eine Aktion enthalten, und die Aktion  muss vorhanden sein (d. h. Sie können eine Aktion auf der Registerkarte Aktionen derselben Tabelle auflisten, eine Aktion, die in einer anderen Vorlage vorhanden ist, oder eine von Microsoft erstellte Aktion). Unterschiedliche Steuerelemente können auf dieselbe Aktion verweisen.

##### <a name="actions-tab"></a>Registerkarte "Aktionen"

Die **Registerkarte Aktionen** ist erforderlich.  Er bestimmt Verbesserungsmaßnahmen, die von Ihrer Organisation verwaltet werden, und nicht die von Microsoft, die bereits im Compliance Manager vorhanden sind. Die erforderlichen Spalten für diese Registerkarte, die der in der Beispielkalkulationstabelle angegebenen Reihenfolge folgen müssen, sind:

- **actionTitle**: Dies ist der Titel ihrer Aktion und ein erforderliches Feld. Der von Ihnen zur Verfügung stellende Titel muss eindeutig sein. **Wichtig:** Wenn Sie auf eine Aktion verweisen, die bereits vorhanden ist (z. B. in einer anderen Vorlage), und Sie eines der Elemente in den nachfolgenden Spalten ändern, werden diese Änderungen in anderen Vorlagen an dieselbe Aktion weiter gegeben.

- **implementationType**: In diesem erforderlichen Feld müssen Sie einen der drei folgenden Implementierungstypen auflisten:
    - **Betriebsbereit** – Von Personen und Prozessen implementierte Aktionen zum Schutz der Vertraulichkeit, Integrität und Verfügbarkeit von Organisationssystemen, Ressourcen, Daten und Personal (Beispiel: Sicherheitsbewusstsein und Schulung)
    - **Technical** – Aktionen, die durch die Verwendung von Technologien und Mechanismen in den Hardware-, Software- oder Firmwarekomponenten des Informationssystems abgeschlossen wurden, um die Vertraulichkeit, Integrität und Verfügbarkeit von Organisationssystemen und Daten zu schützen (Beispiel: mehrstufige Authentifizierung)
    - **Dokumentation** – Aktionen, die durch dokumentierte Richtlinien und Verfahren implementiert werden, um die zum Schutz der Vertraulichkeit, Integrität und Verfügbarkeit von Organisationssystemen, Ressourcen, Daten und Personal erforderlichen Kontrollen zu erstellen und zu definieren (Beispiel: eine Informationssicherheitsrichtlinie)

- **actionScore**: Geben Sie in diesem erforderlichen Feld einen numerischen Bewertungswert für Ihre Aktion an. Es muss eine ganze Zahl zwischen 1 und 99 sein. er darf nicht 0, null oder leer sein. Je höher die Zahl, desto größer ist ihr Wert für die Verbesserung Ihrer Compliance-Einstellung. Die folgende Abbildung zeigt, wie Der Compliance-Manager Steuerelemente abwertet:

![Compliance-Manager steuert Punktwerte](../media/compliance-score-action-scoring.png "Compliance-Manager steuert Punktwerte")

- **actionDescriptionTitle**: Dies ist der Titel der Beschreibung und ist erforderlich. Mit diesem Beschreibungstitel können Sie dieselbe Aktion in mehreren Vorlagen verwenden und in jeder Vorlage eine andere Beschreibung anzeigen.  Dieses Feld hilft Ihnen zu verdeutlichen, auf welche Vorlage die Beschreibung verweisen soll. In den meisten Fällen können Sie den Namen der Vorlage, die Sie erstellen, in dieses Feld einfügen.

- **actionDescription**: Geben Sie eine Beschreibung der Aktion an. Sie können Formatierungen wie fett formatierten Text und Hyperlinks anwenden. Dieses Feld ist erforderlich.

- **dimension-Action Purpose**: Dies ist ein optionales Feld. Wenn Sie sie hinzufügen, muss die Kopfzeile das Präfix "dimension-" enthalten. Alle dimensionen, die Sie hier enthalten, werden als Filter im Compliance-Manager verwendet und werden auf der Detailseite zu Verbesserungsmaßnahmen im Compliance-Manager angezeigt.

##### <a name="dimensions-tab"></a>Registerkarte Dimensionen

Die **Registerkarte Dimensionen** ist optional. Wenn Sie jedoch an anderer Stelle auf eine Dimension verweisen, müssen Sie sie hier angeben, wenn sie nicht in einer vorlage vorhanden ist, die Sie bereits erstellt haben, oder in einer Microsoft-Vorlage. Die Spalten für diese Registerkarte sind unten aufgeführt:

- **dimensionKey**: list as "product", "certifications", "action purpose"
- **dimensionValue**: Beispiele: Office 365, HIPPA, Preventative, Detective

Sie können ihre vorhandenen Dimensionen anzeigen, indem Sie zur **Mandantenverwaltung gehen** und die Registerkarte **Dimensionen** auswählen. Wenn Sie eine vorhandene Vorlage exportieren, verfügt die  exportierte Kalkulationstabelle außerdem über die Registerkarte Dimensionen, auf der alle in der Vorlage verwendeten Dimensionen aufgeführt sind.

## <a name="modify-a-template"></a>Ändern einer Vorlage

Möglicherweise möchten Sie eine bereits erstellte Vorlage ändern, z. B. Steuerelemente hinzufügen oder Verbesserungsaktionen hinzufügen oder entfernen. Der Vorgang ähnelt dem Erstellungsprozess der Vorlage, indem Sie formatierte Excel-Dateien mit Ihren Vorlagendaten hochladen.

Beim Formatieren der Datei mit Änderungen an vorhandenen Vorlagendaten sind jedoch besondere Details zu beachten. **Es wird empfohlen, diese Anweisungen sorgfältig zu lesen, um sicherzustellen, dass sie keine vorhandenen Daten überschreiben, die Sie beibehalten möchten.**

### <a name="template-modification-process-steps"></a>Schritte zum Ändern von Vorlagen

Führen Sie die folgenden Schritte aus, um eine Vorlage zu ändern:

1. Wählen Sie **auf der Seite** Bewertungsvorlagen die Vorlage aus, die Sie ändern möchten, wodurch die Detailseite angezeigt wird.
2. Wählen **Sie Exportieren nach Excel aus.** Eine Excel-Datei mit allen Vorlagendaten wird heruntergeladen. Speichern Sie die Datei auf Ihrem lokalen Computer.
3. Nehmen Sie Ihre Vorlagenänderungen [vor, indem Sie die Excel-Datei mithilfe der folgenden Anweisungen ändern.](#formatting-your-excel-file-to-modify-a-template)
4. Wenn Sie die Änderungen an Ihrer Excel-Datei vorgenommen haben, speichern Sie die Datei.
5. Wählen Sie auf der Detailseite Ihrer Vorlage Die Vorlage **ändern aus,** um den Änderungs-Assistenten zu initiieren. 
6. Wählen Sie **auf dem Bildschirm** Datei hochladen die Option **Durchsuchen** aus, um Ihre Excel-Datei zu suchen und hochzuladen.
7. Wenn keine Probleme mit ihrer Datei auftreten, wird auf dem nächsten Bildschirm der Name der hochgeladenen Datei angezeigt. Wählen **Sie Weiter** aus, um fortzufahren (wenn Sie die Datei ändern müssen, wählen Sie Hochladen einer anderen Datei **aus).**
    - Wenn ein Problem mit Ihrer Datei vor liegt, wird in einer Fehlermeldung oben erklärt, was falsch ist. Sie müssen Ihre Datei korrigieren und erneut hochladen. Fehler resultieren, wenn Ihre Kalkulationstabelle nicht ordnungsgemäß formatiert ist oder wenn in bestimmten Feldern ungültige Informationen enthalten sind.

8. Der **Bildschirm Überprüfen und Fertig** stellen zeigt die Anzahl der Verbesserungsaktionen und -steuerelemente sowie die maximale Bewertung für die Vorlage an. Wenn Sie zur Genehmigung bereit sind, wählen Sie **Weiter aus.**
9. Der letzte Bildschirm bestätigt, dass die Vorlage geändert wurde. Wählen **Sie Fertig** aus, um den Assistenten zu beenden.

Ihre Vorlage enthält nun die änderungen, die Sie vorgenommen haben. Alle Bewertungen, die diese geänderte Vorlage verwenden, zeigen nun ausstehende Updates an, und Sie müssen die Aktualisierungen der Bewertungen akzeptieren, um die in der Vorlage vorgenommenen Änderungen widerspiegeln zu können. Erfahren Sie mehr über [Updates für Bewertungen](compliance-manager-assessments.md#accepting-updates-to-assessments).

> [!NOTE]
> Wenn Sie Compliance Manager in einer anderen Sprache als Englisch verwenden, werden Sie feststellen, dass beim Exportieren einer Vorlage nach Excel text in Englisch angezeigt wird. Die Titel von Aktionen (sowohl Ihre Verbesserungsaktionen als auch Microsoft-Aktionen) müssen auf Englisch sein, damit sie von Steuerelementen erkannt werden. Wenn Sie Änderungen an einem Aktionstitel vornehmen, schreiben Sie ihn unbedingt in Englisch, damit die Datei ordnungsgemäß importiert wird.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Formatieren der Excel-Datei zum Ändern einer Vorlage

Wechseln Sie zu einem Abschnitt unten, um schnell die benötigten Anweisungen zu finden:

- [Bearbeiten der Hauptvorlagenattribute](#edit-the-main-template-attributes)
- [Hinzufügen einer Verbesserungsaktion](#add-an-improvement-action)
- [Bearbeiten der Informationen einer Verbesserungsaktion](#edit-an-improvement-actions-information)
- [Ändern des Namens einer Verbesserungsaktion](#change-an-improvement-actions-name)
- [Entfernen einer Verbesserungsaktion](#remove-an-improvement-action)
- [Entfernen eines Steuerelements](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Bearbeiten der Hauptvorlagenattribute

Auf der **Registerkarte Vorlagen** können Sie  alles in der Titelspalte, **in der Spalte inScopeServices** und in jeder anderen Spalte bearbeiten, die Sie möglicherweise hinzugefügt haben. Sie können jedoch nichts in den Produkt- oder **Zertifizierungsspalten** bearbeiten. 

#### <a name="add-an-improvement-action"></a>Hinzufügen einer Verbesserungsaktion

1. Wechseln Sie zur **Registerkarte Aktionen.** Fügen Sie Ihre Informationen in den erforderlichen Feldern in der ersten leeren Zeile unterhalb Der vorhandenen Aktionen hinzu.
2. Wechseln Sie zu **Ihrer Registerkarte ControlFamily.** Suchen Sie die Zeile, die das Steuerelement enthält, dem Ihre Verbesserungsaktion zu ordnet. Fügen Sie ihre neue Aktion der **Spalte controlActionTitle** in dieser Zeile hinzu (denken Sie daran, mehrere Aktionen in diesem Feld mit zwei Semikolonen zu trennen, kein Leerzeichen dazwischen).
3. Speichern Sie Ihre Kalkulationstabelle.

#### <a name="edit-an-improvement-actions-information"></a>Bearbeiten der Informationen einer Verbesserungsaktion

Sie können die Informationen jeder Verbesserungsaktion mit Ausnahme *des Titels ändern.* Sie können jede Zelle ab Spalte B bearbeiten, und wenn Sie die Datei wieder in die Vorlage importieren, enthalten die Verbesserungsaktionen in dieser Vorlage nun die aktualisierten Daten.

Sie können **actionTitle** (Spalte A) nicht bearbeiten, da der Compliance-Manager dies in diesem Falls als neue Verbesserungsaktion betrachtet. Wenn Sie den Namen einer Verbesserungsaktion ändern möchten, lesen Sie die Anweisungen direkt unten.

#### <a name="change-an-improvement-actions-name"></a>Ändern des Namens einer Verbesserungsaktion

Wenn Sie den Namen einer Verbesserungsaktion ändern möchten, müssen Sie in der Tabelle explizit festlegen, dass Sie einen vorhandenen Namen durch einen neuen Namen ersetzen. Gehen Sie wie folgt vor:

1. Fügen Sie **auf** der Registerkarte Aktionen ihrer Tabelle der Tabelle nach Spalte A eine neue Spalte hinzu.
2. In dieser neuen Spalte, die jetzt Spalte B ist, wird die Kopfzeile in Zeile 1: **oldActionTitle angezeigt.**
3. Kopieren Sie den Inhalt der Spalte A, und fügen Sie sie in Spalte B ein. Dadurch werden die vorhandenen Titel der Verbesserungsaktion, die Sie ändern möchten, in Spalte B versetzt.
4. Löschen Sie in Spalte **A, actionTitle,** den alten Namen, und ersetzen Sie ihn durch den neuen Namen für Ihre Verbesserungsaktion.

Beachten Sie, dass Aktionstitel sowohl für Ihre Verbesserungsaktionen als auch für Microsoft-Aktionen in Englisch geschrieben werden müssen, um erkannt zu werden, wenn in Steuerelementen auf sie verwiesen wird.

#### <a name="remove-an-improvement-action"></a>Entfernen einer Verbesserungsaktion

Um eine Verbesserungsaktion aus einer Vorlage zu entfernen, müssen Sie sie aus jedem Steuerelement entfernen, das darauf verweist. Führen Sie die folgenden Schritte aus, um Ihre Kalkulationstabelle zu ändern:

1. Suchen Sie auf der Registerkarte **ControlFamily** nach dem Titel der Verbesserungsaktion, die Sie entfernen möchten.
2. Löschen Sie den Titel der Verbesserungsaktion in den Zellen, in denen sie angezeigt wird. Wenn die Verbesserungsaktion die einzige Aktion in dieser Zeile ist, löschen Sie die gesamte Zeile (wodurch das Steuerelement entfernt wird).
3. Löschen Sie **auf** der Registerkarte Aktionen die Zeile, die die zu löschende Verbesserungsaktion enthält.
4. Speichern Sie Ihre Kalkulationstabelle.

Wenn Sie ihre Kalkulationstabelle wieder in die Vorlage importieren, wird Ihre Verbesserungsaktion aus der Vorlage entfernt.

Durch das Entfernen einer Verbesserungsaktion aus einer Vorlage wird die Verbesserungsaktion nicht vollständig aus dem Compliance-Manager entfernt. Auf diese Aktion kann weiterhin von einer anderen Vorlage verwiesen werden.

#### <a name="remove-a-control"></a>Entfernen eines Steuerelements

Um ein Steuerelement zu entfernen, ändern Sie Ihre Kalkulationstabelle, indem Sie die folgenden Schritte ausführen, und importieren Sie die Kalkulationstabelle erneut:

1. Suchen Sie auf der Registerkarte **ControlFamily** das Steuerelement, das Sie entfernen möchten, in der **Spalte controlName.**
2. Löschen Sie die Zeile für dieses Steuerelement.
    - Wenn dieses gelöschte Steuerelement Verbesserungsaktionen enthält, auf die von keinem anderen Steuerelement verwiesen wird, müssen Sie diese Verbesserungsaktionen auf der Registerkarte **Aktionen** entfernen. Andernfalls wird ein Überprüfungsfehler angezeigt.

3. Speichern Sie Ihre Kalkulationstabelle.

Wenn Sie Ihre Kalkulationstabelle wieder in die Vorlage importieren, wird Ihr Steuerelement aus der Vorlage entfernt.

## <a name="export-a-template"></a>Exportieren einer Vorlage

Sie können eine Excel-Datei exportieren, die alle Daten einer Vorlage enthält. Sie müssen eine Vorlage exportieren, um die Vorlage zu ändern, da dies die Excel-Datei ist, die Sie bearbeiten und im [Änderungsprozess hochladen.](#modify-a-template)

Um Ihre Vorlage zu exportieren, wechseln Sie zur Seite Vorlagendetails, und wählen Sie **die Schaltfläche Exportieren nach Excel** aus.

Beachten Sie, dass beim Exportieren einer Vorlage, die Sie aus einer Compliance -Manager-Vorlage erweitert haben, die exportierte Datei nur die Attribute enthält, die Sie der Vorlage hinzugefügt haben. Die exportierte Datei enthält nicht die ursprünglichen Vorlagendaten, die von Microsoft bereitgestellt wurden. Informationen zum Erhalten eines solchen Berichts finden Sie in den Anweisungen zum [Exportieren eines Bewertungsberichts](compliance-manager-assessments.md#export-an-assessment-report).