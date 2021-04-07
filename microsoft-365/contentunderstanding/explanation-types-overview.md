---
title: Erklärungstypen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Weitere Informationen über Erklärungstypen in Microsoft SharePoint Syntex
ms.openlocfilehash: a5404230a59d1740a2b855527229a7aca92195a8
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604405"
---
# <a name="introduction-to-explanation-types"></a>Einführung in Erklärungstypen

Erklärungen werden verwendet, um die Informationen zu definieren, die Sie in Ihren Document Understanding-Modellen in Microsoft SharePoint Syntex bezeichnen und extrahieren möchten. Wenn Sie eine Erklärung erstellen, müssen Sie einen Erklärungstyp auswählen. Dieser Artikel hilft Ihnen dabei, die verschiedenen Erklärungstypen und ihre Verwendung zu verstehen. 

![Erklärungstypen](../media/content-understanding/explanation-types.png) 
   
Diese Erklärungstypen stehen zur Verfügung:

- **Begriffsliste**: Liste von Wörtern, Phrasen, Zahlen oder anderen Zeichen, die Sie in dem Dokument oder der Information, die Sie extrahieren, verwenden können. Zum Beispiel ist die Textzeichenfolge **Überweisender Arzt** in allen Dokumenten "Ärztliche Überweisung" enthalten, die Sie identifizieren. Oder die **Telefonnummer** des überweisenden Arztes aus allen von Ihnen identifizierten medizinischen Überweisungsdokumenten.

- **Näherung**: Beschreibt, wie nahe die Erklärungen beieinander liegen. Eine *Straßennummern*-Begriffsliste wird beispielsweise direkt vor der *Straßennamen*-Begriffsliste ohne dazwischen liegende Token angezeigt (Informationen zu Token finden Sie weiter unten in diesem Artikel). Die Verwendung des Näherungstyps erfordert, dass Sie mindestens zwei Erklärungen in Ihrem Modell haben, ansonsten die Option deaktiviert wird. 
 
## <a name="phrase-list"></a>Begriffsliste

Der Erklärungstyp "Begriffsliste" wird normalerweise verwendet, um ein Dokument durch Ihr Modell zu identifizieren und zu klassifizieren. Wie im Beispiel der Bezeichnung *Überweisender Arzt* beschrieben, handelt es sich dabei um eine Kette von Wörtern, Phrasen, Zahlen oder Zeichen, die in den Dokumenten, die Sie identifizieren, konsistent ist.

Auch wenn dies keine Voraussetzung ist, können Sie mit Ihrer Erklärung einen besseren Erfolg erzielen, wenn die Phrase, die Sie erfassen, sich an einer konsistenten Stelle in Ihrem Dokument befindet. Beispielsweise kann sich die Bezeichnung *Überweisender Arzt* durchgängig im ersten Absatz des Dokuments befinden. Sie können auch die Option **[Konfigurieren von im Dokument vorkommenden Begriffen](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** in der erweiterten Dokumenteinstellung verwenden, um bestimmte Bereiche auszuwählen, in denen sich der Begriff befindet, insbesondere wenn die Möglichkeit besteht, dass der Begriff an mehreren Stellen in Ihrem Dokument vorkommt.

Wenn die Groß-/Kleinschreibung bei der Identifizierung Ihrer Bezeichnung beachtet werden muss, können Sie dies in Ihrer Erklärung mit dem Typ "Begriffsliste" angeben, indem Sie das Kontrollkästchen **Nur exakte Groß-/Kleinschreibung** aktivieren.

![Unterscheidung nach Groß-/Kleinschreibung](../media/content-understanding/case-sensitivity.png) 

Ein Begriffstyp ist besonders nützlich, wenn Sie eine Erklärung erstellen, die Informationen in verschiedenen Formaten wie Datum, Telefonnummer und Kreditkartennummer identifiziert und extrahiert. Beispielsweise kann ein Datum in verschiedenen Formaten angezeigt werden (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1.1.2020 usw.). Durch das Definieren einer Begriffsliste wird Ihre Erklärung effizienter, indem mögliche Abweichungen in den Daten erfasst werden, die Sie identifizieren und extrahieren möchten. 

Für das Beispiel **Telefonnummer** extrahieren Sie die Telefonnummer für jeden überweisenden Arzt aus allen Dokumenten "Ärztliche Überweisung", die das Modell identifiziert. Geben Sie beim Erstellen der Erklärung die verschiedenen Formate ein, die eine Telefonnummer möglicherweise in Ihrem Dokument anzeigt, damit Sie mögliche Abweichungen erfassen können. 

![Begriffsmuster von Telefonnummern](../media/content-understanding/pattern-list.png)

In diesem Beispiel aktivieren Sie unter **Erweiterte Einstellungen** das Kontrollkästchen **Beliebige Ziffer von 0-9**, um zu erkennen, dass jeder in Ihrer Begriffsliste verwendete "0" -Wert eine beliebige Ziffer von 0 bis 9 ist.

![Beliebige Ziffer von 0-9](../media/content-understanding/digit-identity.png)

Wenn Sie eine Begriffsliste erstellen, die Textzeichen enthält, aktivieren Sie das Kontrollkästchen **Beliebiger Buchstabe von a-z**, um zu erkennen, dass jedes in der Begriffsliste verwendete "a" -Zeichen ein beliebiges Zeichen von "a" bis "z" ist.

Wenn Sie beispielsweise eine **Datum**-Begriffsliste erstellen und sicherstellen möchten, dass ein Datumsformat wie der *1. Januar 2020* erkannt wird, müssen Sie:
- Fügen Sie Ihrer Begriffsliste *aaa 0, 0000* und *aaa 00, 0000* hinzu.
- Stellen Sie sicher, dass auch **Beliebiger Buchstabe von a-z** ausgewählt ist.

![Beliebiger Buchstabe von a-z](../media/content-understanding/any-letter.png)

Wenn Ihre Begriffsliste Großschreibungsanforderungen enthält, können Sie außerdem das Kontrollkästchen **Nur genaue Großschreibung** aktivieren. Wenn Sie für das Beispiel "Datum" den ersten Buchstaben des Monats groß schreiben möchten, müssen Sie Folgendes tun:

- Fügen Sie Ihrer Begriffsliste *Aaa 0, 0000* und *Aaa 00, 0000* hinzu.
- Stellen Sie sicher, dass auch **Nur genaue Groß-/Kleinschreibung** ausgewählt ist.

![Nur genaue Groß-/Kleinschreibung](../media/content-understanding/exact-caps.png)

> [!NOTE]
> Anstatt manuell eine Erklärung für die Begriffsliste zu erstellen, verwenden Sie die [Erklärungsbibliothek](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates), um Begriffslistenvorlagen für eine allgemeine Begriffsliste wie *Datum*, *Telefonnummer*, *Kreditkartennummer* usw. zu verwenden.

## <a name="proximity"></a>Näherung 

Der Erklärungstyp "Näherung" hilft Ihrem Modell bei der Identifizierung von Daten, indem er definiert, wie nahe ein anderes Datenelement an ihm liegt. Beispielsweise haben Sie in Ihrem Modell zwei Erklärungen definiert, die sowohl die *Straßennummer* als auch die *Telefonnummer* des Kunden bezeichnen. 

Beachten Sie, dass die Telefonnummern des Kunden immer vor der Straßennummer steht. 

Alex Wilburn<br>
555-555-5555<br>
Langgasse 18<br>
54123 Münchfeld<br>

Verwenden Sie die Näherungserklärung, um festzulegen, wie weit die Erklärung "Telefonnummer" entfernt ist, um die Straßennummer in Ihren Dokumenten besser identifizieren zu können.

![Näherungserklärung](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a>Was sind Token?

Um den Erklärungstyp "Näherung" verwenden zu können, müssen Sie verstehen, was ein Token ist, da die Anzahl der Token angibt, wie die Näherungserklärung den Abstand von einer Erklärung zur anderen misst. Ein Token ist eine kontinuierliche Reihe (ohne Leerzeichen oder Interpunktionen) von Buchstaben und Zahlen. 

Die folgende Tabelle zeigt Beispiele, wie die Anzahl der Token in einer Phrase ermittelt wird.

|Phrase|Anzahl von Token|Erklärung|
|--|--|--|
|`Dog`|1|Ein einzelnes Wort ohne Interpunktionszeichen oder Leerzeichen.|
|`RMT33W`|1|Eine Datensatz-Locator-Nummer. Sie kann Zahlen und Buchstaben beinhalten, hat aber keine Interpunktion.|
|`425-555-5555`|5|Eine Telefonnummer. Jedes Interpunktionszeichen ist ein einzelnes Token, also ist `425-555-5555` 5 Tokens:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Konfigurieren des Erklärungstyps "Näherung"

Konfigurieren Sie für das Beispiel die Näherungseinstellung, um den Bereich der Anzahl der Token in der *Telefonnummer*-Erklärung aus der *Straßenadressnummer*-Erklärung zu definieren. Beachten sie, dass der Mindestbereich „0“ ist, da es keine Token zwischen der Telefonnummer und der Straßenadressnummer gibt.

Einige Telefonnummern in den Beispieldokumenten sind jedoch mit *(Mobil)* ergänzt.

Nestor Wilke<br>
111-111-1111 (Mobil)<br>
Langgasse 18<br>
54123 Münchfeld<br>

Es gibt drei Token in *(Mobil)*:

|Phrase|Tokenzahl|
|--|--|
|(|1|
|Mobil|2|
|)|3|

Konfigurieren Sie die Einstellung für die Näherung so, dass sie einen Wert von 0 bis 3 aufweist.

![Beispiel einer Näherung](../media/content-understanding/proximity-example.png)


## <a name="configure-where-phrases-occur-in-the-document"></a>Konfigurieren Sie, wo Ausdrücke im Dokument vorkommen.

Wenn Sie eine Erklärung erstellen, wird standardmäßig im gesamten Dokument nach dem Ausdruck gesucht, den Sie extrahieren möchten. Sie können jedoch die erweiterte Einstellung **Wo diese Ausdrücke vorkommen** verwenden, um eine bestimmte Stelle im Dokument zu isolieren, an der ein Ausdruck vorkommt. Dies ist in Situationen hilfreich, in denen ähnliche Instanzen eines Ausdrucks möglicherweise an einer anderen Stelle im Dokument auftreten und Sie sicherstellen möchten, dass der richtige Ausdruck ausgewählt ist. Unter Bezugnahme auf unser Dokument mit medizinischen Empfehlungen wird der **überweisende Arzt** immer im ersten Absatz des Dokuments erwähnt. Mit der Einstellung **Wo diese Ausdrücke vorkommen, können Sie in diesem Beispiel Ihre Erklärung so konfigurieren, dass nach dieser Bezeichnung nur im Anfangsabschnitt des Dokuments oder an einer anderen Stelle gesucht wird, an der sie möglicherweise vorkommt.

![Einstellung „Wo diese Ausdrücke vorkommen“](../media/content-understanding/phrase-location.png)

Sie können für diese Einstellung die folgenden Optionen auswählen:

- An beliebiger Stelle in der Datei: Es wird das gesamte Dokument nach dem Ausdruck durchsucht.

- Anfang der Datei: Das Dokument wird vom Anfang bis zur Position des Ausdrucks durchsucht.

   ![Anfang der Datei](../media/content-understanding/beginning-of-file.png)

    Im Viewer können Sie das Auswahlfeld manuell anpassen, um die Position einzugeben, an der die Phase erscheint. Der Wert **Endposition** wird aktualisiert und zeigt die Anzahl der Token an, die im ausgewählten Bereich enthalten sind. Beachten Sie, dass Sie auch den Endpositionswert aktualisieren können, um den ausgewählten Bereich anzupassen.

   ![Anfang des Dateipositionsfelds](../media/content-understanding/beginning-box.png)

- Ende der Datei: Das Dokument wird vom Ende bis zur Position des Ausdrucks durchsucht.

   ![Ende der Datei](../media/content-understanding/end-of-file.png)

    Im Viewer können Sie das Auswahlfeld manuell anpassen, um die Position einzugeben, an der die Phase erscheint. Der Wert **Startposition** wird aktualisiert und zeigt die Anzahl der Token an, die im ausgewählten Bereich enthalten sind. Beachten Sie, dass Sie auch den Startpositionswert aktualisieren können, um den ausgewählten Bereich anzupassen.

   ![Ende des Dateipositionsfelds](../media/content-understanding/end-box.png)

- Benutzerdefiniert: Das Dokument wird in einem bestimmten Bereich innerhalb des Dokuments nach der Position des Ausdrucks durchsucht.

   ![Benutzerdefinierter Bereich](../media/content-understanding/custom-file.png)

    Im Viewer können Sie das Auswahlfeld manuell anpassen, um die Position einzugeben, an der die Phase erscheint. Für diese Einstellung müssen Sie je eine Position **Start** und **Ende** auswählen. Diese Werte stellen die Anzahl der Token ab dem Anfang des Dokuments dar. Sie können diese Werte zwar manuell eingeben, doch ist es einfacher, das Auswahlfeld im Viewer manuell anzupassen. 
   
## <a name="use-explanation-templates"></a>Verwenden von Erklärungsvorlagen

Während Sie manuell verschiedene Begriffslistenwerte für Ihre Erklärung hinzufügen können, kann es einfacher sein, die Vorlagen zu verwenden, die Ihnen in der Erklärungsbibliothek zur Verfügung gestellt werden.

Statt beispielsweise alle Varianten für *Datum* manuell hinzuzufügen, können Sie die Begriffslistenvorlage für *Datum* verwenden, da diese bereits eine Reihe von Begriffslistenwerten enthält:

![Erklärungsbibliothek](../media/content-understanding/explanation-template.png)
 
Die Erklärungsbibliothek enthält häufig verwendeten Begriffslistenerklärungen, einschließlich:

- Datum: Kalenderdaten, alle Formate. Enthält Text und Zahlen (z. B. „Dec 9, 2020“).
- Datum (numerisch): Kalenderdaten, alle Formate. Beinhaltet Zahlen (zum Beispiel 1-11-2020).
- Zeit: 12- und 24-Stunden-Format.
- Zahl: Positive und negative Zahlen bis zu 2 Dezimalstellen. 
- Prozentsatz: Eine Liste von Mustern, die einen Prozentsatz darstellen. Zum Beispiel 1%, 11%, 100%, 11,11%, usw.
- Rufnummer: Gängige Vereinigte Staaten- und internationale Formate. Zum Beispiel: 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, usw.
- Postleitzahl: Vereinigte Staaten-Postleitzahlenformate. Zum Beispiel, 11111, 11111-1111.
- Erstes Wort des Satzes: Gemeinsame Muster für Wörter mit bis zu 9 Zeichen. 
- Ende des Satzes: Gängige Interpunktion für das Ende eines Satzes
- Kreditkarte: Gängige Formate für Kreditkartennummern. Zum Beispiel: 1111-1111-1111-1111. 
- Sozialversicherungsnummer: Format der Vereinigten Staaten-Sozialversicherungsnummer. Zum Beispiel, 111-11-1111. 
- Ankreuzfeld: Eine Begriffsliste, die Variationen für ein ausgefülltes Kontrollkästchen darstellt. Zum Beispiel: _X_, _ _X_, usw.
- Währung: Wichtige internationale Symbole. Zum Beispiel: $. 
- E-Mail-CC: Eine Begriffsliste mit dem Begriff „CC:“, die oft in der Nähe der Namen oder E-Mail-Adressen von zusätzlichen Personen oder Gruppen zu finden ist, an die die Nachricht gesendet wurde.
- E-Mail-Datum: Eine Begriffsliste mit dem Begriff „Gesendet am:“, die oft in der Nähe des Datums zu finden ist, an dem die E-Mail gesendet wurde.
- E-Mail-Begrüßung: Gängige Anfangszeilen für E-Mails.
- E-Mail-Empfänger: Eine Begriffsliste mit dem Begriff „An:“, die oft in der Nähe der Namen oder E-Mail-Adressen von Personen oder Gruppen zu finden ist, an die die Nachricht gesendet wurde. 
- E-Mail-Absender: Eine Begriffsliste mit dem Begriff „Von:“, die oft in der Nähe des Namens oder der E-Mail-Adresse des Absenders zu finden ist. 
- E-Mail-Betreff: Eine Begriffsliste mit dem Begriff „Betreff:“, die oft in der Nähe des Betreffs der E-Mail zu finden ist. 

Die Erläuterungsbibliothek beinhaltet auch drei automatische Vorlagentypen, die mit den von Ihnen in Ihren Beispieldateien bezeichneten Daten funktionieren:

- Nach der Bezeichnung: Die Wörter oder Zeichen, die nach den Bezeichnungen in den Beispieldateien aufscheinen.
- Vor der Bezeichnung: Die Wörter oder Zeichen, die vor den Bezeichnungen in den Beispieldateien aufscheinen.
- Bezeichnungen: Bis zu den ersten 10 Bezeichnungen der Beispieldateien.

Als Beispiel dafür, wie automatische Vorlagen funktionieren, verwenden wir in der folgenden Beispieldatei die Erläuterungsvorlage „Vor der Bezeichnung“, die dazu beiträgt, dem Modell weitere Informationen zur Verfügung zu stellen, um eine genauere Übereinstimmung zu erzielen.

![Beispieldatei](../media/content-understanding/before-label.png)

Wenn Sie die Erläuterungsvorlage „Vor der Bezeichnung“ auswählen, sucht diese zunächst nach der Gruppe an Wörtern, die vor der Bezeichnung in Ihren Beispieldateien aufscheinen. In dem Beispiel lauten die in der ersten Beispieldatei identifizierten Wörter „Ab dem“.

![Vorlage für „Vor der Bezeichnung“](../media/content-understanding/before-label-explanation.png)

Sie können **Hinzufügen** wählen, um aus der Vorlage eine Erläuterung zu erstellen.  Sobald Sie weitere Beispieldateien hinzufügen, werden zusätzliche Wörter identifiziert und zur Begriffsliste hinzugefügt.

![Die Bezeichnung hinzufügen](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a>Verwenden einer Vorlage aus der Erklärungsbibliothek

1. Wählen Sie im Abschnitt **Erklärungen** auf der Seite **Trainieren** Ihres Modells **Neu** aus und dann **Aus einer Vorlage**.

   ![„Vor der Bezeichnung „hinzufügen](../media/content-understanding/from-template.png)

2.  Wählen Sie auf der Seite **Erklärungsvorlagen** die Erklärung aus, die Sie verwenden möchten, dann wählen Sie **Hinzufügen** aus.

    ![Auswählen einer Vorlage](../media/content-understanding/phone-template.png)

3. Die Informationen für die von Ihnen ausgewählte Vorlage sind auf der Seite **Erklärung erstellen** dargestellt. Bearbeiten Sie bei Bedarf den Namen der Erläuterung und fügen Sie Elemente zur Begriffsliste hinzu oder entfernen Sie diese.  

    ![Vorlage bearbeiten](../media/content-understanding/phone-template-live.png)

4. Wählen Sie anschließend **Speichern**.