---
title: Arbeiten mit Bewertungs Vorlagen im Microsoft Compliance-Manager
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
description: Hier erfahren Sie, wie Sie Vorlagen für die Erstellung von Assessments im Microsoft Compliance-Manager verwenden und verwalten. Erstellen und Ändern von Vorlagen mit einer formatierten Excel-Datei.
ms.openlocfilehash: cc3092e486e4f25fa1edad1ff64e638410cf3a63
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791807"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Arbeiten mit Bewertungs Vorlagen im Compliance-Manager

**In diesem Artikel:** Grundlegendes zur Funktions **Weise von Vorlagen** und **deren Verwaltung auf** der Seite mit den Bewertungs Vorlagen. Hier finden Sie Anweisungen zum **Erstellen** neuer Vorlagen, zum **ändern** vorhandener Vorlagen, zum **Formatieren der Vorlagendaten mit Excel** und zum Exportieren von Vorlagen **Berichten** .

> [!IMPORTANT]
> Die für Ihre Organisation verfügbaren Bewertungs Vorlagen hängen von Ihrem Lizenzvertrag ab. Über [prüfen Sie die Details](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="templates-overview"></a>Vorlagen (Übersicht)

Eine Vorlage ist ein Framework zum Erstellen einer Bewertung im Compliance-Manager. Sie enthalten die Steuerelemente für die Erfüllung der Anforderungen einer Zertifizierung mit einem bestimmten Produkt. Compliance-Manager bietet eine umfassende Palette von Vorlagen, mit denen Ihre Organisation nationale, regionale und branchenspezifische Anforderungen für die Erfassung und Verwendung von Daten erfüllen kann.

## <a name="list-of-pre-built-templates-for-assessments"></a>Liste der vordefinierten Vorlagen für Bewertungen

Compliance-Manager stellt Vorlagen zum Erstellen von Bewertungen bereit, die Ihnen dabei helfen, verschiedene Vorschriften und Standards einzuhalten. Zeigen Sie die [Liste der Vorlagen](compliance-manager-templates-list.md) an, die vom Compliance-Manager bereitgestellt werden. Neue Vorlagen werden regelmäßig hinzugefügt, daher sollten Sie die Liste häufig überprüfen.

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Anzeigen und Verwalten von Vorlagen auf der Seite "Bewertungs Vorlagen"

Auf der Seite "Bewertungs Vorlagen" im Compliance-Manager wird eine Liste der Vorlagen und Schlüssel Details angezeigt. Die Liste enthält Vorlagen, die vom Compliance-Manager bereitgestellt werden, sowie alle Vorlagen, die Ihre Organisation geändert oder erstellt hat. Sie können Filter anwenden, um eine Vorlage basierend auf der Zertifizierung, dem Produktbereich, dem Land, der Branche, der Person, die Sie erstellt hat, zu suchen und zu ermitteln, ob die Vorlage für die Erstellung von Bewertungen aktiviert ist.

Wählen Sie in der Zeile eine Vorlage aus, um die zugehörige Detailseite aufzurufen. Diese Seite enthält eine Beschreibung der Vorlage und weitere Informationen zu Zertifizierungs-, Bereichs-und Steuerelement Details. Auf dieser Seite können Sie die entsprechenden Schaltflächen auswählen, um eine Bewertung zu erstellen, die Vorlagendaten nach Excel zu exportieren oder die Vorlage zu ändern.

## <a name="creating-and-modifying-templates-overview"></a>Erstellen und Ändern von Vorlagen (Übersicht)

Um eine vorhandene Vorlage zu ändern oder eine eigene neue Vorlage zu erstellen, verwenden Sie eine speziell formatierte Excel-Tabelle ([Beispiel herunterladen](https://go.microsoft.com/fwlink/?linkid=2124865)), um die erforderlichen Steuerelementdaten zusammenzustellen. Nachdem Sie die Kalkulationstabelle abgeschlossen haben, importieren Sie Sie während des Prozesses zum Erstellen oder Ändern einer Vorlage in Compliance-Manager.

> [!NOTE]
> Das Arbeitsblatt hat ein bestimmtes Format und Schema, das verwendet werden muss, oder es wird nicht ordnungsgemäß in den Compliance-Manager importiert. Die [Formatierungsanweisungen](#formatting-your-template-data-with-excel) finden Sie unten.

**Erforderliche Rollen**

Nur Benutzer, die eine globale Administrator-oder Compliance-Manager-Verwaltungsrolle innehaben, können Vorlagen erstellen und ändern. Erfahren Sie mehr über [Rollen und Berechtigungen](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

## <a name="create-a-new-template"></a>Erstellen einer neuen Vorlage

Führen Sie die folgenden Schritte aus, um eine eigene neue Vorlage zu erstellen (für das Erstellen von benutzerdefinierten Bewertungen verwendet).

1. Wechseln Sie im Compliance-Manager zu Ihrer Seite mit den **Bewertungs Vorlagen** .
2. Wählen Sie **neue Vorlage erstellen** aus. Ein Vorlagen Erstellungs-Assistent wird geöffnet.
3. Wählen Sie den Typ der Vorlage aus, die Sie erstellen möchten. Wählen Sie in diesem Fall **eine benutzerdefinierte Vorlage erstellen** aus, und wählen Sie dann **weiter** aus.
4. Wählen Sie auf dem Bildschirm **Datei hochladen** die Option **Durchsuchen** aus, um die formatierte Excel-Datei zu suchen und hochzuladen, die alle erforderlichen Vorlagendaten enthält (siehe [Anweisungen zum ordnungsgemäßen Formatieren Ihrer Datei](#formatting-your-template-data-with-excel)).
5. Wenn keine Probleme mit Ihrer Datei auftreten, wird der Name der hochgeladenen Datei angezeigt. Wählen Sie **weiter** aus, um fortzufahren. (Wenn Sie die Datei ändern müssen, wählen Sie **Hochladen einer anderen Datei** ).
    - Wenn ein Fehler mit der Datei vorliegt, wird in einer Fehlermeldung am oberen Rand erläutert, was falsch ist. Sie müssen die Datei korrigieren und erneut hochladen. Wenn Ihr Arbeitsblatt nicht ordnungsgemäß formatiert ist oder wenn ungültige Informationen in bestimmten Feldern vorhanden sind (Lesen Sie erneut die [Formatierungsanweisungen](#formatting-your-template-data-with-excel)), tritt ein Fehler auf.  
    
6. Auf dem Bildschirm **überprüfen und beenden** werden die Anzahl der Verbesserungs Aktionen und-Steuerelemente sowie die maximale Punktzahl für die Vorlage angezeigt. Wählen Sie bei Genehmigungs Bereitschaft die Option **Vorlage erstellen aus.** (Wenn Sie Änderungen vornehmen müssen, wählen Sie **zurück** aus.)
7. Auf dem letzten Bildschirm wird bestätigt, dass eine neue Vorlage erstellt wurde. Wählen Sie **Fertig** aus, um den Assistenten zu beenden.
8. Sie gelangen auf die Detailseite der neuen Vorlage, auf der Sie [Ihre Bewertung erstellen](compliance-manager-assessments.md#create-your-own-custom-assessment)können.

## <a name="formatting-your-template-data-with-excel"></a>Formatieren der Vorlagendaten mit Excel

Die zum Erstellen von Vorlagen verwendete Excel-Arbeitsmappe enthält vier Registerkarten, von denen drei erforderlich sind:

1. [Vorlage](#template-tab) (erforderlich)
2. [ControlFamily](#controlfamily-tab) (erforderlich)
3. [Aktionen](#actions-tab) (erforderlich)
4. [Dimensionen](#dimensions-tab) (optional)

Beim Ausfüllen Ihres Arbeitsblatts mit Vorlagendaten muss das Arbeitsblatt  **die Registerkarten in der oben aufgeführten Reihenfolge enthalten** , da andernfalls Ihre Daten nicht erfolgreich in eine Vorlage importiert werden.

##### <a name="template-tab"></a>Registerkarte "Vorlage"

Die Registerkarte **Vorlage** ist erforderlich. Die Informationen auf dieser Registerkarte bieten Metadaten zur Vorlage. Es gibt vier erforderliche Spalten. Die Spalten müssen die Reihenfolge auf dem Excel-Blatt beibehalten, wie unten aufgeführt. Sie können **nach** den vier Spalten eine eigene Spalte hinzufügen, um eigene Dimensionen bereitzustellen. Wenn Sie dies tun, müssen Sie Sie auf der Registerkarte **Dimensionen** mithilfe der [Anweisungen unten](#dimensions-tab)hinzufügen.

- **Title** : Dies ist der Titel für Ihre Vorlage, der eindeutig sein muss. Es kann keinen Namen für eine andere Vorlage im Compliance-Manager freigeben, einschließlich ihrer eigenen Vorlagen oder einer Compliance-Manager-Vorlage.

- **Product** : Dies ist eine erforderliche Dimension. Listet das der Vorlage zugeordnete Produkt auf.

- **Zertifizierung** : Dies ist die Verordnung, die Sie für die Vorlage verwenden.

- **inScopeServices** : Dies sind die Dienste innerhalb des Produkts, die diese Bewertung anwendet (wenn Sie beispielsweise Office 365 als Produkt aufgeführt haben, kann Microsoft Teams ein in-Scope-Dienst sein). Sie können mehrere Dienste auflisten, die durch zwei Semikolons getrennt sind.

> [!NOTE]
> Die Daten, die Sie in die **Produkt** -und **Zertifizierungs** Zellen einfügen, können nicht bearbeitet werden, nachdem Sie das Arbeitsblatt importiert haben, um eine Vorlage zu erstellen oder anzupassen. Außerdem kann eine Gruppe nicht zwei Bewertungen enthalten, die die gleiche **Produkt/Zertifizierungs** Kombination aufweisen. Sie können mehrere Vorlagen mit derselben Kombination aus Produkt/Zertifizierung haben.

##### <a name="controlfamily-tab"></a>Registerkarte "ControlFamily"

Die Registerkarte **ControlFamily** ist erforderlich.  Die erforderlichen Spalten auf dieser Registerkarte, die der in der Beispieltabelle angegebenen Reihenfolge folgen müssen, lauten wie folgt:

- **ControlName** : Dies ist der Steuerelementname aus der Zertifizierung, dem Standard oder der Verordnung, bei dem es sich normalerweise um einen Typ von ID handelt. Steuerelementnamen müssen innerhalb einer Vorlage eindeutig sein. Sie können nicht mehrere Steuerelemente mit dem gleichen Namen in der Kalkulationstabelle haben.

- **controlFamily** : Geben Sie ein Wort oder eine Phrase für die controlFamily an, die eine breite Gruppierung von Steuerelementen identifiziert. Ein controlFamily muss nicht eindeutig sein; Es kann in einer Tabellenkalkulation mehrmals aufgeführt werden. Dieselbe controlFamily kann auch in mehreren Vorlagen aufgeführt werden, obwohl Sie nicht miteinander verwandt sind. Jeder controlFamily muss mindestens einem Steuerelement zugeordnet werden.

- **controlTitle** : Geben Sie einen Titel für das Steuerelement an. Während es sich bei ControlName um einen Referenz Code handelt, handelt es sich bei dem Titel um ein Rich-Text-Format, das normalerweise in den Regeln angezeigt

- **controlDescription** : Geben Sie eine Beschreibung des Steuerelements an.

- **controlActionTitle** : Dies ist der Titel einer Aktion, die Sie mit diesem Steuerelement verknüpfen möchten. Sie können mehrere Aktionen hinzufügen, indem Sie durch zwei Semikolons ohne Leerzeichen voneinander getrennt werden. Jedes Steuerelement, das Sie auflisten, muss mindestens eine Aktion enthalten, und die Aktion muss vorhanden sein (was bedeutet, dass Sie eine Aktion auflisten können, die Sie auf der Registerkarte **Aktionen** desselben Arbeitsblatts auflisten, eine Aktion, die in einer anderen Vorlage vorhanden ist, oder eine Aktion, die von Microsoft erstellt wurde). Verschiedene Steuerelemente können auf dieselbe Aktion verweisen.

##### <a name="actions-tab"></a>Registerkarte "Aktionen"

Die Registerkarte **Aktionen** ist erforderlich.  Er kennzeichnet Verbesserungs Aktionen, die von Ihrer Organisation verwaltet werden, und nicht die von Microsoft, die bereits im Compliance-Manager vorhanden sind. Die erforderlichen Spalten für diese Registerkarte, die der in der Beispieltabelle angegebenen Reihenfolge folgen müssen, lauten wie folgt:

- **actionTitle** : Dies ist der Titel für Ihre Aktion und ist ein erforderliches Feld. Der von Ihnen bereitgestellte Titel muss eindeutig sein. **Wichtig** : Wenn Sie auf eine bereits vorhandene Aktion verweisen (beispielsweise in einer anderen Vorlage) und die zugehörigen Elemente in den nachfolgenden Spalten ändern, werden diese Änderungen an dieselbe Aktion in anderen Vorlagen weitergegeben.

- **implementationtype** : führen Sie in diesem Feld einen der drei folgenden Implementierungstypen auf:
    - **Operative** Aktionen, die von Personen und Prozessen implementiert werden, um die Vertraulichkeit, Integrität und Verfügbarkeit von Organisationssystemen, Ressourcen, Daten und Personal zu schützen (Beispiel: Sicherheitsbewusstsein und Schulung)
    - **Technische** Aktionen, die durch die Verwendung von Technologien und Mechanismen in den Hardware-, Software-oder Firmware-Komponenten des Informationssystems abgeschlossen wurden, um die Vertraulichkeit, Integrität und Verfügbarkeit von Organisationssystemen und Daten zu schützen (Beispiel: mehrstufige Authentifizierung)
    - **Dokumentation** – durch dokumentierte Richtlinien und Verfahren implementierte Aktionen zur Erstellung und Definition der erforderlichen Steuerelemente zum Schutz der Vertraulichkeit, Integrität und Verfügbarkeit von Organisationssystemen, Ressourcen, Daten und Personal (Beispiel: eine Informationssicherheitsrichtlinie)

- **actionScore** : Geben Sie in diesem Pflichtfeld einen numerischen Bewertungs Wert für Ihre Aktion an. Es muss eine ganze Zahl zwischen 1 und 99 sein; Er darf nicht 0, NULL oder leer sein. Je höher die Zahl, desto größer ist ihr Wert zur Verbesserung Ihrer Compliance-Haltung. Das folgende Bild zeigt, wie der Kompatibilitäts-Manager Ergebnisse steuert:

![Compliance-Manager steuert Punktewerte](../media/compliance-score-action-scoring.png "Compliance-Manager steuert Punktewerte")

- **actionDescriptionTitle** : Dies ist der Titel der Beschreibung und ist erforderlich. Mit diesem Beschreibungstitel können Sie dieselbe Aktion in mehreren Vorlagen ausführen und in jeder Vorlage eine andere Beschreibung anzeigen.  Dieses Feld hilft Ihnen zu erläutern, auf welche Vorlage die Beschreibung verweist. In den meisten Fällen können Sie den Namen der Vorlage, die Sie erstellen, in dieses Feld einfügen.

- **actionDescription** : Geben Sie eine Beschreibung der Aktion an. Sie können Formatierungen wie fett formatierten Text und Hyperlinks anwenden. Dieses Feld ist erforderlich.

- **Dimension-Aktion Zweck** : Dies ist ein optionales Feld. Wenn Sie diesen einschließen, muss die Kopfzeile das Präfix "Dimension-" enthalten. Alle Dimensionen, die Sie hier einschließen, werden im Compliance-Manager als Filter verwendet und auf der Seite Details der Verbesserungs Aktionen im Compliance-Manager angezeigt.

##### <a name="dimensions-tab"></a>Registerkarte Dimensionen

Die Registerkarte **Dimensionen** ist optional. Wenn Sie jedoch anderweitig auf eine Dimension verweisen, müssen Sie Sie hier angeben, wenn Sie nicht in einer bereits erstellten oder in einer Microsoft-Vorlage vorhandenen Vorlage vorhanden ist. Die Spalten für diese Registerkarte sind unten aufgeführt:

- **dimensionKey** : als "Produkt", "Zertifizierungen", "Aktions Zweck" auflisten
- **dimensionvalue** : Beispiele: Office 365, HIPPA, vorbeugend, Detektiv

Sie können Ihre vorhandenen Dimensionen anzeigen, indem Sie zur **Mandantenverwaltung** wechseln und die Registerkarte **Dimensionen** auswählen. Auch wenn Sie eine vorhandene Vorlage exportieren, verfügt die exportierte Arbeitsmappe über die Registerkarte **Dimensionen** , in der alle in der Vorlage verwendeten Dimensionen aufgelistet werden.

## <a name="modify-a-template"></a>Ändern einer Vorlage

Möglicherweise möchten Sie eine Vorlage ändern, die Sie bereits erstellt haben, beispielsweise zum Hinzufügen von Steuerelementen oder zum Hinzufügen oder Entfernen von Verbesserungs Aktionen. Der Prozess ähnelt dem Vorlagen Erstellungsprozess darin, dass Sie die formatierte Excel-Datei mit ihren Vorlagendaten hochladen.

Es gibt jedoch bestimmte Details, die Sie beachten müssen, wenn Sie die Datei mit Änderungen an vorhandenen Vorlagendaten formatieren. **Es wird empfohlen, diese Anweisungen sorgfältig zu lesen, um sicherzustellen, dass Sie keine vorhandenen Daten überschreiben, die Sie beibehalten möchten.**

### <a name="template-modification-process-steps"></a>Prozessschritte bei der Vorlagenänderung

Führen Sie die folgenden Schritte aus, um eine Vorlage zu ändern:

1. Wählen Sie auf der Seite mit den **Bewertungs Vorlagen** die Vorlage aus, die Sie ändern möchten, um die Detailseite anzuzeigen.
2. Wählen Sie **in Excel exportieren** aus. Eine Excel-Datei mit allen Vorlagendaten wird heruntergeladen. Speichern Sie die Datei auf Ihrem lokalen Computer.
3. Nehmen Sie Ihre Vorlagenänderungen vor, indem Sie [die Excel-Datei mit den Anweisungen unten ändern](#formatting-your-excel-file-to-modify-a-template).
4. Wenn Sie mit dem vornehmen von Änderungen an Ihrer Excel-Datei fertig sind, speichern Sie die Datei.
5. Wählen Sie auf der Detailseite ihrer Vorlage die Option **Vorlage ändern** aus, um den Änderungs Assistenten zu initiieren. 
6. Wählen Sie auf dem Bildschirm **Datei hochladen** die Option **Durchsuchen** aus, um Ihre Excel-Datei zu suchen und hochzuladen.
7. Wenn keine Probleme mit Ihrer Datei auftreten, zeigt der nächste Bildschirm den Namen der hochgeladenen Datei an. Wählen Sie **weiter** aus, um den Vorgang fortzusetzen (wenn Sie die Datei ändern müssen, wählen Sie **Hochladen einer anderen Datei** aus).
    - Wenn ein Problem mit Ihrer Datei vorliegt, wird in einer Fehlermeldung am oberen Rand erläutert, was falsch ist. Sie müssen die Datei korrigieren und erneut hochladen. Wenn Ihr Arbeitsblatt nicht ordnungsgemäß formatiert ist oder wenn ungültige Informationen in bestimmten Feldern vorhanden sind, treten Fehler auf.

8. Auf dem Bildschirm **überprüfen und beenden** werden die Anzahl der Verbesserungs Aktionen und-Steuerelemente sowie die maximale Punktzahl für die Vorlage angezeigt. Wenn Sie zur Genehmigung berechtigt sind, wählen Sie **weiter** aus.
9. Auf dem letzten Bildschirm wird bestätigt, dass die Vorlage geändert wurde. Wählen Sie **Fertig** aus, um den Assistenten zu beenden.

Ihre Vorlage enthält nun die Änderungen, die Sie vorgenommen haben. Bei allen Bewertungen, die diese geänderte Vorlage verwenden, werden jetzt ausstehende Updates angezeigt, und Sie müssen die Updates für die Bewertungen akzeptieren, um die in der Vorlage vorgenommenen Änderungen widerzuspiegeln. Erfahren Sie mehr über [Updates für Assessments](compliance-manager-assessments.md#accepting-updates-to-assessments).

> [!NOTE]
> Wenn Sie den Compliance-Manager in einer anderen Sprache als Englisch verwenden, werden Sie feststellen, dass einige Texte in Englisch angezeigt werden, wenn Sie eine Vorlage nach Excel exportieren. Die Titel der Aktionen (sowohl Ihre Verbesserungs Aktionen als auch Microsoft-Aktionen) müssen in Englisch sein, um von Steuerelementen erkannt zu werden. Wenn Sie Änderungen an einem Aktionstitel vornehmen, müssen Sie ihn in Englisch schreiben, damit die Datei ordnungsgemäß importiert wird.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Formatieren der Excel-Datei zum Ändern einer Vorlage

Wechseln Sie zu einem Abschnitt, um schnell die benötigten Anweisungen zu finden:

- [Bearbeiten der Hauptvorlagen Attribute](#edit-the-main-template-attributes)
- [Hinzufügen einer Verbesserungs Aktion](#add-an-improvement-action)
- [Bearbeiten der Informationen einer Verbesserungs Aktion](#edit-an-improvement-actions-information)
- [Ändern des Namens einer Verbesserungs Aktion](#change-an-improvement-actions-name)
- [Entfernen einer Verbesserungs Aktion](#remove-an-improvement-action)
- [Entfernen eines Steuerelements](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Bearbeiten der Hauptvorlagen Attribute

Auf der Registerkarte **Vorlagen** können Sie alle Elemente in der Spalte **Title** , in der Spalte **inScopeServices** und in jeder anderen Spalte bearbeiten, die Sie möglicherweise hinzugefügt haben. Sie können jedoch nichts in den Spalten **Product** oder **Certification** bearbeiten.

#### <a name="add-an-improvement-action"></a>Hinzufügen einer Verbesserungs Aktion

1. Wechseln Sie zur Registerkarte **Aktionen** . Fügen Sie Ihre Informationen in die erforderlichen Felder in der ersten leeren Zeile unterhalb der vorhandenen Aktionen ein.
2. Wechseln Sie zur Registerkarte **ControlFamily** . Suchen Sie die Zeile mit dem Steuerelement, dem Ihre Verbesserungs Aktion zugeordnet ist. Fügen Sie die neue Aktion zur Spalte **controlActionTitle** in dieser Zeile hinzu (denken Sie daran, mehrere Aktionen in diesem Feld mit zwei Semikolons, kein Leerzeichen dazwischen) zu trennen.
3. Speichern Sie Ihre Arbeitsmappe.

#### <a name="edit-an-improvement-actions-information"></a>Bearbeiten der Informationen einer Verbesserungs Aktion

Sie können alle Informationen zur Verbesserungs Aktion *mit Ausnahme des Titels* ändern. Sie können jede Zelle von Spalten B vorwärts bearbeiten, und wenn Sie die Datei wieder in die Vorlage importieren, werden die Verbesserungs Aktionen in dieser Vorlage nun die aktualisierten Daten enthalten.

Sie können das **actionTitle** (Spalte A) nicht bearbeiten, da Compliance-Manager dies als neue Verbesserungs Aktion betrachtet. Wenn Sie den Namen einer Verbesserungs Aktion ändern möchten, lesen Sie die Anweisungen unmittelbar unten.

#### <a name="change-an-improvement-actions-name"></a>Ändern des Namens einer Verbesserungs Aktion

Wenn Sie den Namen einer Verbesserungs Aktion ändern möchten, müssen Sie in der Kalkulationstabelle explizit festlegen, dass Sie einen vorhandenen Namen durch einen neuen Namen ersetzen. Gehen Sie folgendermaßen vor:

1. Fügen Sie auf der Registerkarte **Aktionen** Ihrer Tabelle eine neue Spalte zu der Kalkulationstabelle nach Spalte a hinzu.
2. In dieser neuen Spalte, die jetzt Spalte B ist, legen Sie die Kopfzeile in Zeile 1: **oldActionTitle** .
3. Kopieren Sie den Inhalt von Spalte a, und fügen Sie ihn in Spalte B ein. Dadurch werden Ihre vorhandenen Verbesserungs Aktionstitel, die Sie ändern möchten, in Spalte B eingefügt.
4. Löschen Sie in Spalte A, **actionTitle** den alten Namen, und ersetzen Sie ihn durch den neuen Namen für Ihre Verbesserungs Aktion.

Beachten Sie, dass Aktionstitel sowohl für Ihre Verbesserungs Aktionen als auch für Microsoft-Aktionen in Englisch geschrieben werden müssen, damit Sie erkannt werden, wenn in Steuerelementen darauf verwiesen wird.

#### <a name="remove-an-improvement-action"></a>Entfernen einer Verbesserungs Aktion

Wenn Sie eine Verbesserungs Aktion aus einer Zeile in einem Arbeitsblatt löschen, wird die Aktion **nicht** aus der Vorlage entfernt, die Sie gerade bearbeiten. Führen Sie stattdessen den folgenden Vorgang aus:

1. Fügen Sie auf der Registerkarte **Aktionen** eine neue Spalte als Spalte a ein, und legen Sie den **Vorgang** in die Kopfzeile ein, wobei es sich um die Nummer 1 der Zeile handelt.
2. Legen Sie in der Zeile für die Verbesserungs Aktion, die Sie entfernen möchten, in Spalte A für diese Zeile den **Lösch** Vorgang fest.
3. Stellen Sie sicher, dass auf diese Verbesserungs Aktion nicht mehr von einem Steuerelement verwiesen wird. Wechseln Sie zur Registerkarte **ControlFamily** , und suchen Sie nach dem Titel Ihrer Verbesserungs Aktion in Spalte F, die **controlActionTitle** ist.
4. Wenn Sie Ihre Verbesserungs Aktion in der Spalte **controlActionTitle** finden, löschen Sie Sie.
5. Speichern Sie Ihre Arbeitsmappe.

Wenn Sie Ihre Kalkulationstabelle wieder in die Vorlage importieren, wird Ihre Aktion aus der Vorlage entfernt. Durch das Entfernen einer Aktion aus einer Vorlage wird die Aktion nicht vollständig entfernt. Auf diese Aktion kann weiterhin von einer anderen Vorlage verwiesen werden.

Wenn Sie die letzte Verbesserungs Aktion Entfernen, auf die ein Steuerelement verweist, müssen Sie das Steuerelement entfernen.

#### <a name="remove-a-control"></a>Entfernen eines Steuerelements

Wenn Sie ein Steuerelement entfernen möchten, führen Sie denselben Vorgang aus, um eine Verbesserungs Aktion wie oben beschrieben zu entfernen. Fügen Sie auf der Registerkarte **ControlFamily** eine **Vorgangs** Spalte hinzu, und legen Sie neben dem Steuerelement, das Sie entfernen möchten, **Delete** .

## <a name="export-a-template"></a>Exportieren einer Vorlage

Sie können eine Excel-Datei exportieren, die alle Daten einer Vorlage enthält. Sie müssen eine Vorlage exportieren, um die Vorlage zu ändern, da dies die Excel-Datei ist, die Sie im [Änderungsprozess](#modify-a-template)bearbeiten und hochladen.

Um Ihre Vorlage zu exportieren, navigieren Sie zur Seite Vorlagen Details, und wählen Sie die Schaltfläche **nach Excel exportieren** aus.

Beachten Sie, dass beim Exportieren einer Vorlage, die Sie von einer Compliance-Manager-Vorlage erweitert haben, die exportierte Datei nur die Attribute enthalten wird, die Sie der Vorlage hinzugefügt haben. Die exportierte Datei enthält nicht die von Microsoft bereitgestellten Original Vorlagendaten. Informationen zum Abrufen eines solchen Berichts finden Sie in den Anweisungen zum [Exportieren eines Bewertungsberichts](compliance-manager-assessments.md#export-an-assessment-report).