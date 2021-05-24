---
title: Anzeigen einer Vorschau von Ergebnissen eDiscovery-Suche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Anzeigen einer Vorschau einer Stichprobe der Ergebnisse, die von einer Inhaltssuche oder einer eDiscovery-Suche im Microsoft 365 Compliance Center zurückgegeben wurden.
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538601"
---
# <a name="preview-ediscovery-search-results"></a>Anzeigen einer Vorschau von eDiscovery-Suchergebnissen

Nachdem Sie eine Inhaltssuche oder eine mit einem Core eDiscovery-Fall zugeordnete Suche ausgeführt haben, können Sie eine Vorschau einer Stichprobe der von der Suche zurückgegebenen Ergebnisse anzeigen. Mit der Vorschau von Elementen, die von der Suchabfrage zurückgegeben wurden, können Sie bestimmen, ob die Suche die Ergebnisse zurückgesendet, die Sie möchten, oder ob Sie die Suchabfrage ändern müssen und die Suche erneut ausführen müssen.

So zeigen Sie eine Stichprobe der von einer Suche zurückgegeben Ergebnisse:

1. Wechseln Sie im Microsoft 365 Compliance Center zur Seite „Inhaltssuche“ oder zu einem Core eDiscovery-Fall.

2. Wählen Sie „Suche“ aus, um die Flyoutseite anzuzeigen.

3. Klicken Sie unten auf der Flyoutseite auf **Stichprobe überprüfen**.

   ![Klicken Sie auf der Flyoutseite auf "Beispiel überprüfen", um eine Vorschau der Ergebnisse anzuzeigen.](../media/PreviewSearchResults1.png)

   Es wird eine Seite mit einer Stichprobe der Suchergebnisse angezeigt.

4. Wählen Sie ein Element aus, um dessen Inhalt im Lesebereich anzuzeigen.

   ![Vorschau der Elemente im Lesebereich](../media/PreviewSearchResults2.png)

   Beachten Sie, dass im vorherigen Screenshot Schlüsselwörter aus der Suchabfrage hervorgehoben werden, wenn Sie eine Vorschau von Elementen anzeigen.

## <a name="how-the-search-result-samples-are-selected"></a>So werden die Beispiele für Suchergebnisse ausgewählt

Zur Vorschau stehen maximal 1 000 zufällig ausgewählte Elemente zur Verfügung. Die für die Vorschau verfügbaren Elemente müssen nicht nur zufällig ausgewählt werden, sondern müssen auch die folgenden Kriterien erfüllen:

- Es können maximal 100 Elemente aus einem einzigen Inhaltsspeicherort (einem Postfach oder einer Website) in der Vorschau angezeigt werden. Dies bedeutet, dass möglicherweise weniger als 1 000 Elemente zur Vorschau zur Verfügung stehen. Wenn Sie beispielsweise vier Postfächer durchsuchen und die Suche 1 500 geschätzte Elemente zurückgibt, stehen nur 400 zur Vorschau zur Verfügung, da nur 100 Elemente aus jedem Postfach in der Vorschau angezeigt werden können.

- Bei Postfachelementen stehen nur E-Mail-Nachrichten zur Vorschau zur Verfügung. Elemente wie Aufgaben, Kalenderelemente und Kontakte können nicht in der Vorschau angezeigt werden.

- Bei Websiteelementen stehen nur Dokumente zur Vorschau zur Verfügung. Elemente wie Ordner, Listen oder Listenanlagen können nicht in der Vorschau angezeigt werden.

## <a name="file-types-supported-when-previewing-search-results"></a>Unterstützte Dateitypen beim Anzeigen der Suchergebnisse in der Vorschau

Unterstützte Dateitypen können im Vorschaufenster angezeigt werden. Wenn ein Dateityp nicht unterstützt wird, müssen Sie eine Kopie der Datei auf Ihren lokalen Computer herunterladen (indem Sie auf **Originalelement herunterladen** klicken). Bei ASPX-Webseiten ist die URL der Seite eingeschlossen, Sie haben möglicherweise jedoch keine Berechtigungen zum Zugriff auf die Seite. Nicht indizierte Elemente können nicht in der Vorschau angezeigt werden.

Die folgenden Dateitypen werden unterstützt und können im Suchergebnisbereich in einer Vorschau angezeigt werden.
  
- .TXT, .HTML, .MHTML

- .EML

- .DOC, .DOCX, .DOCM

- .PPTM, .PPTX

- .PDF

Darüber hinaus werden die folgenden Dateicontainertypen unterstützt. Eine Liste der Dateien in einem Container können Sie im Vorschaubereich anzeigen.
  
- .ZIP

- .GZIP