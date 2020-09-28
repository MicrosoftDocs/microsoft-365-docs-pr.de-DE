---
title: Erklärungs Typen
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Weitere Informationen zu Erklärungs Typen in Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295848"
---
# <a name="introduction-to-explanation-types"></a>Einführung in Erklärungs Typen

Verwenden Sie Erläuterungen, um die Informationen zu definieren, die Sie bezeichnen möchten, und extrahieren Sie in Ihrem Dokument die grundlegenden Modelle für Microsoft SharePoint Syntex. Wenn Sie eine Erklärung erstellen, müssen Sie einen Erklärungs auswählen. 

Dieser Artikel hilft Ihnen, die verschiedenen Erklärungs Typen und deren Verwendung zu verstehen.

   ![Erklärungs Typen](../media/content-understanding/explanation-types.png) 
   
Diese Erklärungs Typen stehen zur Verfügung:

- **Phrase List**: Liste der Wörter, Ausdrücke, Zahlen oder andere Zeichen, die Sie in dem Dokument oder den Informationen, die Sie extrahieren möchten, verwenden können. Beispielsweise ist die Textzeichenfolge **verweisenden Arzt** in allen medizinischen Empfehlungs Dokumenten, die Sie identifizieren.</br>

- **Musterliste**: Listen Muster von Zahlen, Buchstaben oder anderen Zeichen, mit denen Sie die extrahierten Informationen identifizieren können. Sie können beispielsweise die **Telefonnummer** des überweisenden Arztes aus dem von Ihnen identifizierten medizinischen Empfehlungs Dokument extrahieren.</br>

- **Proximity**: Beschreibt, wie sich nahe Erläuterungen zueinander befinden. Beispielsweise wird eine Liste mit *Straßennummern* Mustern direkt vor der Liste mit den *Straßennamen* Phrasen angezeigt, wobei keine Token dazwischen liegen (Sie erfahren mehr über Token später in diesem Artikel). 
 
## <a name="phrase-list"></a>Phrasen Liste

Ein Phrase List-Erklärungs wird normalerweise verwendet, um ein Dokument über das Modell zu identifizieren und zu klassifizieren. Wie im Beispiel zum *verweisenden Arzt* Etikett beschrieben, handelt es sich um eine Reihe von Wörtern, Ausdrücken, Zahlen oder Zeichen, die konsistent in den zu identifizierenden Dokumenten enthalten sind.

Obwohl dies nicht erforderlich ist, können Sie mit ihrer Erläuterung einen besseren Erfolg erzielen, wenn sich die von Ihnen erfasste Phrase an einem konsistenten Ort in Ihrem Dokument befindet. Beispielsweise kann die Bezeichnung des *verweisenden Arztes* im ersten Absatz des Dokuments konsistent gefunden werden.

Wenn die Groß-/Kleinschreibung bei der Identifizierung ihrer Bezeichnung erforderlich ist, können Sie Sie mithilfe des Listentyps Phrasen in ihrer Erklärung angeben, indem Sie das Kontrollkästchen **exakte Groß-/Kleinschreibung** aktivieren.

   ![Groß-/Kleinschreibung](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Muster Listen

Ein Muster Listentyp ist besonders nützlich, wenn Sie eine Erklärung erstellen, mit der Informationen aus einem Dokument identifiziert und extrahiert werden. Sie wird in der Regel in unterschiedlichen Formaten wie Datumsangaben, Telefonnummern oder Kreditkartennummern dargestellt. Beispielsweise kann ein Datum in einer Reihe von verschiedenen Formaten angezeigt werden (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1, 2020 usw.). Durch das Definieren einer Musterliste wird Ihre Erklärung effizienter, indem alle möglichen Variationen in den Daten erfasst werden, die Sie identifizieren und extrahieren möchten. 

Extrahieren Sie für das **Telefonnummern** Beispiel die Telefonnummer für jeden verweisenden Arzt aus allen medizinischen Empfehlungs Dokumenten, die das Modell identifiziert. Wenn Sie die Erläuterung erstellen, wählen Sie den Muster Listentyp aus, um zu ermöglichen, dass die verschiedenen Formate, die Sie möglicherweise erwarten, zurückgegeben werden.

   ![Liste der Telefonnummernmuster](../media/content-understanding/pattern-list.png)

Wählen Sie für dieses Beispiel das Kontrollkästchen **beliebige Ziffer von 0-9 aus** . Durch Auswahl dieser Option wird jeder 0-Wert erkannt, der in ihrer Musterliste als beliebige Ziffer von 0 bis 9 verwendet wird.

   ![Beliebige Ziffer aus 0-9](../media/content-understanding/digit-identity.png)

Wenn Sie eine Musterliste erstellen, die Textzeichen enthält, wählen Sie die Option **beliebiger Buchstabe von a-z** (CheckBox) aus. Durch Auswählen dieser Option wird jedes Zeichen "a" in der Musterliste als beliebiges Zeichen von "a" bis "z" erkannt.

Wenn Sie beispielsweise eine Liste mit **Datums** Mustern erstellen und sicherstellen möchten, dass ein Datumsformat wie *Jan 1, 2020* erkannt wird, müssen Sie Folgendes tun:
- Fügen Sie Ihrer Musterliste *AAA 0, 0000* und *AAA 00, 0000* hinzu.
- Stellen Sie sicher, dass **alle Buchstaben von a-z** ebenfalls ausgewählt sind.

   ![Jeder Buchstabe von a-z](../media/content-understanding/any-letter.png)

Außerdem haben Sie die Möglichkeit, das Kontrollkästchen **nur exakte Groß-/Kleinschreibung** auszuwählen, wenn Sie in ihrer Musterliste die Groß-/Kleinschreibung Voraussetzungen haben. Wenn Sie für das Beispiel Datum den ersten Buchstaben des Monats benötigen, der groß geschrieben werden soll, müssen Sie Folgendes tun:

- Fügen Sie Ihrer Musterliste *AAA 0, 0000* und *AAA 00, 0000* hinzu.
- Stellen Sie sicher, dass auch **nur exakte Großschreibung** ausgewählt ist.

   ![Nur exakte Großschreibung](../media/content-understanding/exact-caps.png)

> [!NOTE]
> Verwenden Sie die [Erklärungs Bibliothek]() , um vorgefertigte Muster Listenvorlagen für allgemeine Muster Listen wie *Datum*, *Telefonnummer*, *Kreditkartennummer*usw. zu verwenden, anstatt eine Erläuterung der Musterliste manuell zu erstellen. 

## <a name="proximity"></a>Näherung 

Der Näherungs Erklärungs unterstützt Ihr Modell beim Identifizieren von Daten, indem es definiert, wie nah ein anderes Datenelement ist. In Ihrem Modell haben Sie beispielsweise zwei Erläuterungen definiert, die sowohl die *Adresse* des Kunden als auch die *Telefonnummer*bezeichnen. 

Außerdem wird feststellen, dass Kundentelefon Nummern immer vor der Nummer der Straße angezeigt werden. 

Alex Wilburn<br>
555-555-5555<br>
Langgasse 18<br>
Redmond, WA 98034<br>

Verwenden Sie die Näherungs Erklärung, um festzulegen, wie weit entfernt die Telefonnummern Erklärung darin besteht, die Nummer der Straße in Ihren Dokumenten besser zu identifizieren.

   ![Näherungs Erklärung](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>Was sind Token?

Um den Näherungs Erklärungs zu verwenden, verstehen Sie, was ein Token ist, da die Anzahl der Token ist, wie die Annäherungs Erklärung misst Abstand von einer Erklärung zur anderen.  

Ein Token ist eine kontinuierliche Spanne (keine Leerzeichen oder Interpunktion) von Buchstaben und Zahlen. Ein Leerzeichen ist kein Token. Jedes Interpunktionszeichen ist ein Token. In der folgenden Tabelle sind einige Beispiele für die Ermittlung der Anzahl von Token in einem Ausdruck aufgeführt.

|Ausdruck|Anzahl von Token|Erklärung|
|--|--|--|
|`Dog`|1 |Ein einzelnes Wort ohne Interpunktion oder Leerzeichen.|
|`RMT33W`|1 |Eine Record Locator-Nummer. Es gibt möglicherweise Zahlen und Buchstaben, aber keine Interpunktion.|
|`425-555-5555`|5 |Eine Telefonnummer. Jedes Interpunktionszeichen ist ein einzelnes Token  `425-555-5555` , es wären also 5 Token:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7 |`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Konfigurieren des Näherungs Erklärungs Typs

Konfigurieren Sie für das Beispiel die Näherungs Einstellung, sodass der Bereich der Anzahl von Token definiert werden kann, die für die *Telefonnummern* Erklärung aus der Beschreibung der *Adresse der Straße angegeben* werden.

Sie sollten sehen, dass der Mindestbereich "0" ist, da es keine Token zwischen der Telefonnummer und der Adressnummer gibt.

Einige Telefonnummern in den Beispiel Dokumenten werden jedoch mit *(Mobile)* angehängt.

Nestor Wilke<br>
111-111-1111 (mobil)<br>
Langgasse 18<br>
Redmond, WA 98034<br>

Es gibt drei Token in *(Mobile)*:

|Ausdruck|Anzahl von Token|
|--|--|
|(|1 |
|Mobile|2 |
|)|3 |

Konfigurieren Sie die Näherungs Einstellung für einen Bereich von 0 bis 3.

   ![Näherungs Beispiel](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a>Verwenden der Erklärungs Bibliothek

Sie können zwar manuell verschiedene Muster Listenwerte für Ihre Erklärung hinzufügen, aber es ist viel einfacher, die vordefinierten Vorlagen zu verwenden, die Ihnen in der Erklärungs Bibliothek zur Verfügung gestellt wurden.

Verwenden Sie beispielsweise anstelle des manuellen Hinzufügens aller Variationen für *Date*die Muster Listenvorlage für *Date*, die bereits eine Reihe von Muster Listenwerten enthält:</br>

   ![Erklärungs Bibliothek](../media/content-understanding/explanation-template.png)</br>
 
Die Erklärungs Bibliothek enthält eine Reihe häufig verwendeter Muster Listen Erläuterungen, einschließlich:</br>

- Datum</br>
- Datum (numerisch)</br>
- Zeit</br>
- Zahl</br>
- Telefonnummer</br>
- PLZ</br>
- Erstes Wort des Satzes</br>
- Kreditkarte</br>
- Sozialversicherungsnummer</br>

Beachten Sie, dass die Erklärungs Bibliothek auch Vorlagen für Phrase List-Erläuterungen enthält, einschließlich:
- Ende des Satzes
- Währung

#### <a name="to-use-a-template-from-the-explanation-library"></a>So verwenden Sie eine Vorlage aus der Erklärungs Bibliothek

1. Wählen Sie im Abschnitt **Erläuterungen** des **Zuges** Ihres Modells die Option **neu**aus, und wählen Sie dann **aus einer Vorlage aus**.</br>

   ![Aus Vorlage erstellen](../media/content-understanding/from-template.png)</br>

2.  Wählen Sie auf der Seite **Erklärungs Vorlagen** die Erklärung aus, die Sie verwenden möchten, und wählen Sie dann **Hinzufügen**aus.</br>

       ![Auswählen einer Vorlage](../media/content-understanding/phone-template.png)</br>

3. Die Informationen für die ausgewählte Vorlage werden auf der Seite **Erklärung erstellen** angezeigt. Bearbeiten Sie bei Bedarf den Namen der Erklärung, und fügen Sie Elemente aus der Liste Muster hinzu oder entfernen Sie Sie. </br> 

   ![Vorlage bearbeiten](../media/content-understanding/phone-template-live.png)</br>

4. Wenn Sie fertig sind, wählen Sie **Speichern**aus.
