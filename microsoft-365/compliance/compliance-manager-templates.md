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
description: Hier erfahren Sie, wie Sie Vorlagen zum Erstellen von Bewertungen im Microsoft Compliance Manager verwenden und verwalten. Erstellen und Ändern von Vorlagen mithilfe einer formatierten Excel-Datei.
ms.openlocfilehash: 34adb79392b235152cc0e00f5b7d661e90c9005e
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849609"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Arbeiten mit Bewertungsvorlagen im Compliance-Manager

**In diesem Artikel:** Erfahren **Sie, wie Vorlagen funktionieren** und wie Sie sie **auf** der Seite mit den Bewertungsvorlagen verwalten. Erhalten Sie Anweisungen **zum Erstellen neuer** Vorlagen, **Ändern** vorhandener Vorlagen, Formatieren der Vorlagendaten mit **Excel** und Exportieren von **Vorlagenberichten.**

> [!IMPORTANT]
> Die Für Ihre Organisation verfügbaren Bewertungsvorlagen hängen von Ihrem Lizenzvertrag ab. [Überprüfen Sie die Details.](https://go.microsoft.com/fwlink/?linkid=2132371)

## <a name="templates-overview"></a>Vorlagenübersicht

Eine Vorlage ist ein Framework zum Erstellen einer Bewertung im Compliance-Manager. Sie enthalten die Steuerelemente, um die Anforderungen einer Zertifizierung mit einem bestimmten Produkt zu erfüllen. Der Compliance-Manager bietet einen umfassenden Satz von Vorlagen, mit deren Hilfe Ihre Organisation nationale, regionale und branchenspezifische Anforderungen für die Erfassung und Verwendung von Daten erfüllen kann.

## <a name="list-of-pre-built-templates-for-assessments"></a>Liste vordefinierter Vorlagen für Bewertungen

Der Compliance-Manager stellt Vorlagen zum Erstellen von Bewertungen bereit, mit deren Hilfe Sie verschiedene Vorschriften und Standards einhalten können. Zeigen Sie [die Liste der Vorlagen an, die](compliance-manager-templates-list.md) vom Compliance-Manager bereitgestellt werden. Neue Vorlagen werden regelmäßig hinzugefügt, daher sollten Sie die Liste häufig überprüfen.

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Anzeigen und Verwalten von Vorlagen auf der Seite "Bewertungsvorlagen"

Auf der Seite "Bewertungsvorlagen" im Compliance-Manager wird eine Liste mit Vorlagen und wichtigen Details angezeigt. Die Liste enthält Vorlagen, die vom Compliance Manager bereitgestellt werden, sowie alle Vorlagen, die Ihre Organisation geändert oder erstellt hat. Sie können Filter anwenden, um eine Vorlage basierend auf zertifizierung, Produktbereich, Land, Branche, wer sie erstellt hat und ob die Vorlage für die Erstellung von Bewertung aktiviert ist.

Wählen Sie eine Vorlage aus der Zeile aus, um die Detailseite anzuzeigen. Diese Seite enthält eine Beschreibung der Vorlage sowie weitere Informationen zu Zertifizierung, Umfang und Steuerelementdetails. Auf dieser Seite können Sie die entsprechenden Schaltflächen auswählen, um eine Bewertung zu erstellen, die Vorlagendaten nach Excel zu exportieren oder die Vorlage zu ändern.

## <a name="creating-and-modifying-templates-overview"></a>Übersicht über das Erstellen und Ändern von Vorlagen

Um eine vorhandene Vorlage zu ändern oder eine eigene neue Vorlage zu erstellen, verwenden Sie eine speziell formatierte Excel-Kalkulationstabelle[(Beispiel](https://go.microsoft.com/fwlink/?linkid=2124865)herunterladen), um die erforderlichen Steuerelementdaten zusammenstellen. Nach Abschluss der Tabellenkalkulation importieren Sie sie während des Erstellens oder Änderns einer Vorlage in den Compliance-Manager.

> [!NOTE]
> Die Kalkulationstabelle verfügt über ein bestimmtes Format und Schema, das verwendet werden muss, oder sie wird nicht ordnungsgemäß in den Compliance-Manager importiert. Die [Formatierungsanweisungen](#formatting-your-template-data-with-excel) sind unten aufgeführt.

**Erforderliche Rollen**

Nur Benutzer mit der Rolle "Globaler Administrator" oder "Compliance-Manager-Verwaltung" können Vorlagen erstellen und ändern. Erfahren Sie mehr über [Rollen und Berechtigungen.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

## <a name="create-a-new-template"></a>Erstellen einer neuen Vorlage

Führen Sie die folgenden Schritte aus, um eine eigene neue Vorlage zu erstellen (die zum Erstellen benutzerdefinierter Bewertungen verwendet wird).

1. Wechseln Sie **im** Compliance-Manager zu Ihrer Seite mit Bewertungsvorlagen.
2. Wählen Sie **"Neue Vorlage erstellen" aus.** Ein Assistent zum Erstellen von Vorlagen wird geöffnet.
3. Wählen Sie den Typ der Vorlage aus, die Sie erstellen möchten. Wählen Sie in diesem Fall **"Benutzerdefinierte** Vorlage erstellen" und dann **"Weiter" aus.**
4. Wählen Sie auf dem  **Bildschirm "Datei** hochladen" die Option "Durchsuchen" aus, um die formatierte Excel-Datei, die alle erforderlichen Vorlagendaten enthält, zu suchen und [hochzuladen](#formatting-your-template-data-with-excel)(siehe Anweisungen zum ordnungsgemäßen Formatieren Der Datei).
5. Wenn keine Probleme mit ihrer Datei auftreten, wird der Name der hochgeladenen Datei angezeigt. Wählen Sie **"Weiter"** aus, um fortzufahren. (Wenn Sie die Datei ändern müssen, wählen **Sie "Andere Datei hochladen" aus.**
    - Wenn bei Ihrer Datei ein Fehler auftritt, wird in einer Fehlermeldung oben erläutert, was falsch ist. Sie müssen Ihre Datei korrigieren und erneut hochladen. Fehler werden auftreten, wenn Ihre Tabelle nicht ordnungsgemäß formatiert ist oder wenn in bestimmten Feldern ungültige Informationen enthalten sind (lesen Sie erneut die [Formatierungsanweisungen).](#formatting-your-template-data-with-excel)  
    
6. Der **Bildschirm "Überprüfen und Fertig** stellen" zeigt die Anzahl der Verbesserungsmaßnahmen und Steuerelemente sowie die Maximale Punktzahl für die Vorlage an. Wenn Sie zur Genehmigung bereit sind, wählen Sie **"Vorlage erstellen" aus.** (Wenn Sie Änderungen vornehmen müssen, wählen Sie **"Zurück"** aus.)
7. Auf dem letzten Bildschirm wird bestätigt, dass eine neue Vorlage erstellt wurde. Wählen Sie **"Fertig"** aus, um den Assistenten zu beenden.
8. Sie gelangen zur Detailseite Ihrer neuen Vorlage, auf der Sie [Ihre Bewertung erstellen können.](compliance-manager-assessments.md#create-your-own-custom-assessment)

## <a name="formatting-your-template-data-with-excel"></a>Formatieren der Vorlagendaten mit Excel

Die zum Erstellen von Vorlagen verwendete Excel-Kalkulationstabelle enthält vier Registerkarten, von denen drei erforderlich sind:

1. [Vorlage](#template-tab) (erforderlich)
2. [ControlFamily](#controlfamily-tab) (erforderlich)
3. [Aktionen](#actions-tab) (erforderlich)
4. [Dimensionen](#dimensions-tab) (optional)

Wenn Sie Ihre  **Kalkulationstabelle** mit Vorlagendaten ausfüllen, muss die Tabelle die Registerkarten in der oben aufgeführten Reihenfolge enthalten, andernfalls werden Ihre Daten nicht erfolgreich in eine Vorlage importiert.

##### <a name="template-tab"></a>Registerkarte "Vorlage"

Die **Registerkarte "Vorlage"** ist erforderlich. Die Informationen auf dieser Registerkarte enthalten Metadaten zur Vorlage. Es gibt vier erforderliche Spalten. Die Spalten müssen die Reihenfolge auf dem Excel-Blatt wie unten aufgeführt beibehalten. Sie können nach den vier Spalten eine **eigene Spalte** hinzufügen, um ihre eigenen Dimensionen zur Verfügung zu stellen. Wenn Sie dies tun, stellen  Sie sicher, dass Sie sie mithilfe der folgenden Anweisungen zur Registerkarte "Dimensionen" [hinzufügen.](#dimensions-tab)

- **title:** Dies ist der Titel für Ihre Vorlage, der eindeutig sein muss. Es kann keinen Namen für eine andere Vorlage im Compliance Manager freigeben, einschließlich Ihrer eigenen Vorlagen oder einer Compliance-Manager-Vorlage.

- **product**: Dies ist eine erforderliche Dimension. Listet das der Vorlage zugeordnete Produkt auf.

- **Zertifizierung:** Dies ist die Vorschrift, die Sie für die Vorlage verwenden.

- **inScopeServices:** Dies sind die Dienste innerhalb des Produkts, auf die sich diese Bewertung richtet (wenn Sie beispielsweise Office 365 als Produkt aufgelistet haben, könnte Microsoft Teams ein Dienst im Bereich sein). Sie können mehrere Dienste durch zwei Semikolon getrennt auflisten.

> [!NOTE]
> Die Daten, die  Sie  in die Produkt- und Zertifizierungszellen einfügen, können nach dem Importieren der Kalkulationstabelle zum Erstellen oder Anpassen einer Vorlage nicht bearbeitet werden. Außerdem kann eine Gruppe nicht zwei Bewertungen mit derselben **Produkt-/Zertifizierungskombination** enthalten. Sie können mehrere Vorlagen mit derselben Produkt-/Zertifizierungskombination verwenden.

##### <a name="controlfamily-tab"></a>Registerkarte "ControlFamily"

Die **Registerkarte "ControlFamily"** ist erforderlich.  Die erforderlichen Spalten auf dieser Registerkarte, die der in der Beispieltabelle angegebenen Reihenfolge folgen müssen, sind:

- **controlName**: Dies ist der Steuerelementname aus der Zertifizierung, dem Standard oder der Vorschrift, die in der Regel eine Art von ID ist. Steuerelementnamen müssen innerhalb einer Vorlage eindeutig sein. In der Tabelle können nicht mehrere Steuerelemente mit demselben Namen angezeigt werden.

- **controlFamily**: Stellen Sie ein Wort oder einen Ausdruck für controlFamily zur Verfügung, das eine breite Gruppierung von Steuerelementen identifiziert. Ein controlFamily muss nicht eindeutig sein. Sie kann in einer Kalkulationstabelle mehr als einmal aufgeführt werden. Die gleiche controlFamily kann auch in mehreren Vorlagen aufgeführt werden, obwohl sie keine Beziehung zueinander haben. Jede controlFamily muss mindestens einem Steuerelement zugeordnet sein.

- **controlTitle**: Geben Sie einen Titel für das Steuerelement an. Während es sich bei "controlName" um einen Referenzcode handelt, handelt es sich bei dem Titel um ein Rich-Text-Format, das in der Regel in den Bestimmungen verwendet wird.

- **controlDescription**: Geben Sie eine Beschreibung des Steuerelements an.

- **controlActionTitle**: Dies ist der Titel einer Aktion, die Sie mit diesem Steuerelement in Beziehung bringen möchten. Sie können mehrere Aktionen hinzufügen, indem Sie durch zwei Semikolon ohne Leerzeichen dazwischen trennen. Jedes Steuerelement, das Sie auflisten, muss mindestens eine Aktion enthalten, und die Aktion  muss vorhanden sein (d. h., Sie können eine Aktion, die Sie auf der Registerkarte "Aktionen" derselben Tabelle auflisten, eine Aktion, die in einer anderen Vorlage vorhanden ist, oder eine von Microsoft erstellte Aktion auflisten). Verschiedene Steuerelemente können auf dieselbe Aktion verweisen.

##### <a name="actions-tab"></a>Registerkarte "Aktionen"

Die **Registerkarte "Aktionen"** ist erforderlich.  Er bestimmt Verbesserungsmaßnahmen, die von Ihrer Organisation verwaltet werden, und nicht die von Microsoft, die bereits im Compliance Manager vorhanden sind. Die erforderlichen Spalten für diese Registerkarte, die der in der Beispieltabelle angegebenen Reihenfolge folgen müssen, sind:

- **actionTitle**: Dies ist der Titel ihrer Aktion und ein erforderliches Feld. Der von Ihnen zur Verfügung stellende Titel muss eindeutig sein. **Wichtig:** Wenn Sie auf eine Aktion verweisen, die Bereits vorhanden ist (z. B. in einer anderen Vorlage), und sie elemente in den nachfolgenden Spalten ändern, werden diese Änderungen in anderen Vorlagen an dieselbe Aktion dehiert.

- **implementationType:** Listen Sie in diesem erforderlichen Feld einen der drei folgenden Implementierungstypen auf:
    - **Operational** – Von Personen und Prozessen implementierte Aktionen zum Schutz der Vertraulichkeit, Integrität und Verfügbarkeit von Organisationssystemen, Ressourcen, Daten und Personal (Beispiel: Sicherheitsbewusstsein und Schulung)
    - **Technisch** – Aktionen, die mithilfe von Technologien und Mechanismen durchgeführt werden, die in den Hardware-, Software- oder Firmwarekomponenten des Informationssystems enthalten sind, um die Vertraulichkeit, Integrität und Verfügbarkeit von Organisationssystemen und -daten zu schützen (Beispiel: mehrstufige Authentifizierung)
    - **Dokumentation** – Aktionen, die durch dokumentierte Richtlinien und Verfahren implementiert werden und die zum Schutz der Vertraulichkeit, Integrität und Verfügbarkeit von Organisationssystemen, Ressourcen, Daten und Personal erforderlichen Kontrollen einrichten und definieren (Beispiel: eine Informationssicherheitsrichtlinie)

- **actionScore**: Geben Sie in diesem erforderlichen Feld einen numerischen Bewertungswert für Ihre Aktion an. Es muss eine ganze Zahl zwischen 1 und 99 sein. Er darf nicht 0, NULL oder leer sein. Je höher die Zahl, desto größer ist ihr Wert zur Verbesserung Ihrer Compliance-Situation. Die folgende Abbildung zeigt, wie der Compliance-Manager Steuerelemente abwertet:

![Compliance-Manager steuert Punktwerte](../media/compliance-score-action-scoring.png "Compliance-Manager steuert Punktwerte")

- **actionDescriptionTitle**: Dies ist der Titel der Beschreibung und ist erforderlich. Mit diesem Beschreibungstitel können Sie dieselbe Aktion in mehreren Vorlagen verwenden und in jeder Vorlage eine andere Beschreibung anzeigen.  Dieses Feld hilft Ihnen zu verdeutlichen, auf welche Vorlage sich die Beschreibung bezieht. In den meisten Fällen können Sie den Namen der Vorlage, die Sie erstellen, in dieses Feld einfügen.

- **actionDescription**: Geben Sie eine Beschreibung der Aktion an. Sie können Formatierungen wie fett formatierten Text und Hyperlinks anwenden. Dies ist das erforderliche Feld.

- **dimension-Action Purpose**: Dies ist ein optionales Feld. Wenn Sie sie hinzufügen, muss die Kopfzeile das Präfix "dimension-" enthalten. Alle Dimensionen, die Sie hier hinzufügen, werden als Filter im Compliance-Manager verwendet und auf der Detailseite zu Verbesserungsmaßnahmen im Compliance-Manager angezeigt.

##### <a name="dimensions-tab"></a>Registerkarte "Dimensionen"

Die **Registerkarte "Dimensionen"** ist optional. Wenn Sie jedoch an anderer Stelle auf eine Dimension verweisen, müssen Sie sie hier angeben, wenn sie nicht in einer Vorlage vorhanden ist, die Sie bereits erstellt haben, oder in einer Microsoft-Vorlage. Die Spalten für diese Registerkarte sind unten aufgeführt:

- **dimensionKey**: list as "product", "certifications," "action purpose"
- **dimensionValue**: Beispiele: Office 365, HIPPA, Preventative, Detective

Sie können Ihre vorhandenen Dimensionen anzeigen, indem Sie zur Mandantenverwaltung **gehen** und die Registerkarte **"Dimensionen"** auswählen. Wenn Sie eine vorhandene Vorlage exportieren, verfügt die  exportierte Kalkulationstabelle außerdem über die Registerkarte "Dimensionen", auf der alle in der Vorlage verwendeten Dimensionen aufgeführt sind.

## <a name="modify-a-template"></a>Ändern einer Vorlage

Möglicherweise möchten Sie eine Vorlage ändern, die Sie bereits erstellt haben, z. B. Steuerelemente hinzufügen oder Verbesserungsmaßnahmen hinzufügen oder entfernen. Der Vorgang ähnelt dem Erstellungsprozess der Vorlage, da Sie formatierte Excel-Dateien mit Ihren Vorlagendaten hochladen.

Beim Formatieren der Datei mit Änderungen an vorhandenen Vorlagendaten sind jedoch bestimmte Details zu beachten. **Es wird empfohlen, diese Anweisungen sorgfältig zu lesen, um sicherzustellen, dass vorhandene Daten, die Sie beibehalten möchten, nicht überschrieben werden.**

### <a name="template-modification-process-steps"></a>Schritte zum Ändern von Vorlagen

Führen Sie die folgenden Schritte aus, um eine Vorlage zu ändern:

1. Wählen Sie **auf der Seite** mit den Bewertungsvorlagen die Vorlage aus, die Sie ändern möchten, wodurch die Detailseite angezeigt wird.
2. Wählen Sie **"Nach Excel exportieren" aus.** Eine Excel-Datei mit allen Vorlagendaten wird heruntergeladen. Speichern Sie die Datei auf Ihrem lokalen Computer.
3. Nehmen Sie Ihre Vorlagenänderungen [vor, indem Sie die Excel-Datei mithilfe der folgenden Anweisungen ändern.](#formatting-your-excel-file-to-modify-a-template)
4. Wenn Sie mit dem Vornehmen von Änderungen an Ihrer Excel-Datei fertig sind, speichern Sie die Datei.
5. Wählen Sie auf der Detailseite Ihrer Vorlage die Option **"Vorlage ändern"** aus, um den Assistenten zum Ändern zu initiieren. 
6. Wählen Sie **auf dem Bildschirm "Datei hochladen"** die Option **"Durchsuchen"** aus, um Ihre Excel-Datei zu suchen und hochzuladen.
7. Wenn keine Probleme mit der Datei auftreten, wird auf dem nächsten Bildschirm der Name der hochgeladenen Datei angezeigt. Wählen **Sie "Weiter"** aus, um fortzufahren (wenn Sie die Datei ändern müssen, wählen **Sie "Andere Datei hochladen" aus).**
    - Wenn es ein Problem mit Ihrer Datei gibt, wird in einer Fehlermeldung oben erläutert, was falsch ist. Sie müssen Ihre Datei korrigieren und erneut hochladen. Fehler werden angezeigt, wenn Ihre Kalkulationstabelle falsch formatiert ist oder wenn in bestimmten Feldern ungültige Informationen enthalten sind.

8. Der **Bildschirm "Überprüfen und Fertig** stellen" zeigt die Anzahl der Verbesserungsmaßnahmen und Steuerelemente sowie die Maximale Punktzahl für die Vorlage an. Wenn Sie zur Genehmigung bereit sind, wählen Sie **"Weiter" aus.**
9. Auf dem letzten Bildschirm wird bestätigt, dass die Vorlage geändert wurde. Wählen Sie **"Fertig"** aus, um den Assistenten zu beenden.

Ihre Vorlage enthält nun die änderungen, die Sie vorgenommen haben. Alle Bewertungen, die diese geänderte Vorlage verwenden, zeigen nun ausstehende Updates an, und Sie müssen die Aktualisierungen der Bewertungen akzeptieren, um die in der Vorlage vorgenommenen Änderungen widerspiegeln zu können. Erfahren Sie mehr über [Updates für Bewertungen.](compliance-manager-assessments.md#accepting-updates-to-assessments)

> [!NOTE]
> Wenn Sie den Compliance Manager in einer anderen Sprache als Englisch verwenden, werden Sie feststellen, dass beim Exportieren einer Vorlage nach Excel Text in Englisch angezeigt wird. Die Titel von Aktionen (sowohl Ihre Verbesserungsmaßnahmen als auch Microsoft-Aktionen) müssen in Englisch sein, damit sie von Steuerelementen erkannt werden. Wenn Sie Änderungen an einem Aktionstitel vornehmen, schreiben Sie ihn unbedingt in Englisch, damit die Datei ordnungsgemäß importiert wird.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Formatieren der Excel-Datei, um eine Vorlage zu ändern

Wechseln Sie zu einem abschnitt weiter unten, um die benötigten Anweisungen schnell zu finden:

- [Bearbeiten der Hauptvorlagenattribute](#edit-the-main-template-attributes)
- [Hinzufügen einer Verbesserungsaktion](#add-an-improvement-action)
- [Bearbeiten der Informationen einer Verbesserungsaktion](#edit-an-improvement-actions-information)
- [Ändern des Namens einer Verbesserungsaktion](#change-an-improvement-actions-name)
- [Entfernen einer Verbesserungsaktion](#remove-an-improvement-action)
- [Entfernen eines Steuerelements](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Bearbeiten der Hauptvorlagenattribute

Auf der **Registerkarte "Vorlagen"** können  Sie alles in der Titelspalte, in der **Spalte "inScopeServices"** und in jeder anderen Spalte bearbeiten, die Sie möglicherweise hinzugefügt haben. Sie können jedoch nichts in  den Spalten "Produkt" oder **"Zertifizierung"** bearbeiten.

#### <a name="add-an-improvement-action"></a>Hinzufügen einer Verbesserungsaktion

1. Wechseln Sie zur Registerkarte **"Aktionen".** Fügen Sie Ihre Informationen in den erforderlichen Feldern in der ersten leeren Zeile unterhalb Ihrer vorhandenen Aktionen hinzu.
2. Wechseln Sie zur **Registerkarte "ControlFamily".** Suchen Sie die Zeile mit dem Steuerelement, dem Ihre Verbesserungsaktion zu ordnet. Fügen Sie die neue Aktion der **Spalte "controlActionTitle"** in dieser Zeile hinzu (trennen Sie mehrere Aktionen in diesem Feld durch zwei Semikolon, kein Leerzeichen dazwischen).
3. Speichern Sie Ihre Kalkulationstabelle.

#### <a name="edit-an-improvement-actions-information"></a>Bearbeiten der Informationen einer Verbesserungsaktion

Sie können die Informationen von Verbesserungsmaßnahmen mit Ausnahme *des Titels ändern.* Sie können jede Zelle aus Spalten B und darüber bearbeiten, und wenn Sie die Datei wieder in die Vorlage importieren, enthalten die Verbesserungsmaßnahmen in dieser Vorlage jetzt die aktualisierten Daten.

Sie können **actionTitle** (Spalte A) nicht bearbeiten, da dies im Compliance Manager als neue Verbesserungsaktion betrachtet wird. Wenn Sie den Namen einer Verbesserungsaktion ändern möchten, lesen Sie die Anweisungen direkt unten.

#### <a name="change-an-improvement-actions-name"></a>Ändern des Namens einer Verbesserungsaktion

Wenn Sie den Namen einer Verbesserungsaktion ändern möchten, müssen Sie in der Tabelle explizit angeben, dass Sie einen vorhandenen Namen durch einen neuen Namen ersetzen. Gehen Sie folgendermaßen vor:

1. Fügen Sie **der** Tabelle auf der Registerkarte "Aktionen" nach Spalte A eine neue Spalte hinzu.
2. In dieser neuen Spalte, die jetzt Spalte B ist, wird die Kopfzeile in Zeile 1: **oldActionTitle .**
3. Kopieren Sie den Inhalt von Spalte A, und fügen Sie ihn in Spalte B ein. Dadurch werden ihre vorhandenen Titel für Verbesserungsmaßnahmen, die Sie ändern möchten, in Spalte B geändert.
4. Löschen Sie in Spalte A, **actionTitle,** den alten Namen, und ersetzen Sie ihn durch den neuen Namen für Ihre Verbesserungsaktion.

Beachten Sie, dass Aktionstitel, sowohl für Verbesserungsmaßnahmen als auch für Microsoft-Aktionen, in Englisch geschrieben werden müssen, damit sie erkannt werden, wenn in Steuerelementen darauf verwiesen wird.

#### <a name="remove-an-improvement-action"></a>Entfernen einer Verbesserungsaktion

Um eine Verbesserungsaktion aus einer Vorlage zu entfernen, müssen Sie sie aus jedem Steuerelement entfernen, das darauf verweist. Führen Sie die folgenden Schritte aus, um Ihre Kalkulationstabelle zu ändern:

1. Suchen Sie auf der Registerkarte **"ControlFamily"** nach dem Titel der Verbesserungsaktion, die Sie entfernen möchten.
2. Löschen Sie den Titel der Verbesserungsaktion in den Zellen, in denen sie angezeigt wird. Wenn die Verbesserungsaktion die einzige Aktion für diese Zeile ist, löschen Sie die gesamte Zeile (wodurch das Steuerelement entfernt wird).
3. Löschen Sie **auf der** Registerkarte "Aktionen" die Zeile, die die zu löschende Verbesserungsaktion enthält.
4. Speichern Sie Ihre Kalkulationstabelle.

Wenn Sie Ihre Tabelle wieder in die Vorlage importieren, wird Ihre Verbesserungsaktion aus der Vorlage entfernt.

Durch das Entfernen einer Verbesserungsaktion aus einer Vorlage wird die Verbesserungsaktion des Compliance-Managers nicht vollständig entfernt. Auf diese Aktion kann weiterhin von einer anderen Vorlage verwiesen werden.

#### <a name="remove-a-control"></a>Entfernen eines Steuerelements

Wenn Sie ein Steuerelement entfernen möchten, ändern Sie Ihre Kalkulationstabelle, indem Sie die folgenden Schritte ausführen, und importieren Sie die Kalkulationstabelle erneut:

1. Suchen Sie auf der Registerkarte **"ControlFamily"** das Steuerelement, das Sie entfernen möchten, in der **Spalte "controlName".**
2. Löschen Sie die Zeile für dieses Steuerelement.
    - Wenn dieses gelöschte Steuerelement Verbesserungsmaßnahmen enthält, auf die von keinem anderen Steuerelement verwiesen  wird, müssen Sie diese Verbesserungsmaßnahmen von der Registerkarte "Aktionen" entfernen. Andernfalls erhalten Sie einen Überprüfungsfehler.

3. Speichern Sie Ihre Kalkulationstabelle.

Wenn Sie Ihre Kalkulationstabelle wieder in die Vorlage importieren, wird Ihr Steuerelement aus der Vorlage entfernt.

## <a name="export-a-template"></a>Exportieren einer Vorlage

Sie können eine Excel-Datei exportieren, die alle Daten einer Vorlage enthält. Sie müssen eine Vorlage exportieren, um die Vorlage zu ändern, da dies die Excel-Datei ist, die Sie bearbeiten und im [Änderungsprozess hochladen.](#modify-a-template)

Um Ihre Vorlage zu exportieren, wechseln Sie zur Seite mit den Vorlagendetails, und wählen Sie die Schaltfläche **"Nach Excel exportieren"** aus.

Beachten Sie, dass beim Exportieren einer Vorlage, die Sie aus einer Compliance-Manager-Vorlage erweitert haben, die exportierte Datei nur die Attribute enthält, die Sie der Vorlage hinzugefügt haben. Die exportierte Datei enthält nicht die ursprünglichen Vorlagendaten, die von Microsoft bereitgestellt werden. Informationen zum Erhalten eines solchen Berichts finden Sie in den Anweisungen zum [Exportieren eines Bewertungsberichts.](compliance-manager-assessments.md#export-an-assessment-report)