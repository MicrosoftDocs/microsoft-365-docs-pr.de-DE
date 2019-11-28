---
title: Überprüfen der Inhaltssuchabfrage auf Fehler
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: Überprüfen Sie Ihre Stichwortabfrage auf die Inhaltssuche nach Fehlern und Tippfehlern, wie nicht unterstützten Zeichen und booleschen Kleinbuchstaben Operatoren, bevor Sie die Suche ausführen. Wenn ein Fehler vorliegt, schlagen wir eine überarbeitete Abfrage vor.
ms.openlocfilehash: 1d2c9a9f3e2204fa65fe29c9adaffe818d2f7a4c
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633992"
---
# <a name="check-your-content-search-query-for-errors"></a>Überprüfen der Inhaltssuchabfrage auf Fehler

Wenn Sie eine Inhaltssuche erstellen oder bearbeiten, können Sie Office 365 Ihre Abfrage auf nicht unterstützte Zeichen und boolesche Operatoren mit Kleinbuchstaben überprüfen lassen. Wie? Klicken Sie auf der Seite Abfrage einer Inhaltssuche einfach auf **Abfrage für Tippfehler überprüfen** . 
  
![Klicken Sie auf "Abfrage für Tippfehler überprüfen", um Ihre Suchabfrage auf nicht unterstützte Zeichen zu überprüfen.](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
Im folgenden finden Sie eine Liste der nicht unterstützten Zeichen, die wir überprüfen. Nicht unterstützte Zeichen werden häufig ausgeblendet, und Sie verursachen in der Regel einen Suchfehler oder geben unbeabsichtigte Ergebnisse zurück.
  
- **Typografische Anführungs** Zeichen – intelligente einfache und doppelte Anführungszeichen (auch als Curly Anführungszeichen bezeichnet) werden nicht unterstützt. Nur gerade Anführungszeichen können in einer Suchabfrage verwendet werden. 
    
- Nicht **druckbare und Steuerzeichen** -nicht druckbare und Steuerzeichen stellen kein schriftliches Symbol dar, beispielsweise ein alphanumerisches Zeichen. Beispiele für nicht druckbare Zeichen und Steuerzeichen sind Zeichen, die Text formatieren oder Textzeilen trennen. 
    
- **Links-nach-rechts-und rechts-nach-links-Markierungen** -diese Zeichen sind Steuerzeichen, die zum Anzeigen der Textrichtung für Links-nach-rechts-Sprachen (wie Englisch und Spanisch) und Sprachen mit Schreibrichtung von rechts nach Links verwendet werden (beispielsweise Arabisch und Hebräisch).
    
- **Kleinbuchstaben-boolesche Operatoren** – Wenn Sie einen booleschen Operator wie **and**, **or**und **Not** in einer Suchabfrage verwenden, muss er in Großbuchstaben eingegeben werden. Wenn eine Abfrage auf Tippfehler überprüft wird, gibt die Abfragesyntax häufig an, dass ein boolescher Operator verwendet wird, obwohl klein-Operatoren verwendet werden können; andernfalls false. Beispiel: `(WordA or WordB) and (WordC or WordD)`.
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>Was passiert, wenn eine Abfrage ein nicht unterstütztes Zeichen hat?

Wenn in Ihrer Abfrage nicht unterstützte Zeichen gefunden werden, wird eine Warnmeldung angezeigt, die besagt, dass nicht unterstützte Zeichen gefunden wurden, und schlägt eine Alternative vor. Anschließend können Sie die ursprüngliche Abfrage beibehalten oder durch die vorgeschlagene geänderte Abfrage ersetzen. Hier ist ein Beispiel für die Warnmeldung, die angezeigt wird, nachdem Sie im vorherigen Screenshot auf **Abfrage für Tippfehler** für die Suchabfrage prüfen klicken. Beachten Sie, dass die ursprüngliche Abfrage intelligente Anführungszeichen und Kleinbuchstaben-boolesche Operatoren enthält. 
  
![Eine Warnmeldung mit einer vorgeschlagenen Überarbeitung für Ihre Abfrage wird angezeigt.](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Vorgehensweise verhindern, dass nicht unterstützte Zeichen in Ihren Suchabfragen

Nicht unterstützte Zeichen werden normalerweise einer Abfrage hinzugefügt, wenn Sie die Abfrage oder Teile der Abfrage aus anderen Anwendungen (wie Microsoft Word oder Microsoft Excel) kopieren und in das Feld Schlüsselwort auf der Seite Abfrage einer Inhaltssuche einfügen. Die beste Möglichkeit zur Verhinderung nicht unterstützter Zeichen besteht darin, die Abfrage direkt in das Schlüsselwortfeld einzugeben. Sie können auch eine Abfrage aus Word oder Excel kopieren und dann in einem nur-Text-Editor wie Microsoft Notepad einfügen. Speichern Sie die Textdatei, und wählen Sie in der Dropdownliste **Codierung** den Wert **ANSI** aus. Dadurch werden alle Formatierungen und nicht unterstützten Zeichen entfernt. Anschließend können Sie die Abfrage aus der Textdatei kopieren und im Schlüsselwort-Abfragefeld einfügen. 
