---
title: Verwenden des Kommunikations-Editors
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie den Kommunikations-Editor, um Text-und Seriendruckfeld Variablen beim Formatieren Ihres Inhalts zu ändern.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769160"
---
# <a name="use-the-communications-editor"></a>Verwenden des Kommunikations-Editors

Wenn Sie den Inhalt Ihrer Portalinhalte, Benachrichtigungen über rechtliche Aufbewahrungszeit und zugehörige Erinnerungen/Eskalationen definieren, können Sie den Kommunikations-Editor verwenden, um Ihre Inhalte zu formatieren und dynamisch anzupassen.

## <a name="rich-text-editor"></a>Rich-Text-Editor

Mit dem Kommunikations-Editor können Benutzer den Text mithilfe der Editor-Optionen anpassen. Beispielsweise können Benutzer Schriftarttypen ändern, Aufzählungslisten erstellen, Inhalte hervorheben und vieles mehr.

## <a name="merge-field-variables"></a>Zusammenführen von Feld Variablen

Sie können e-Mail-Zusammenführungs Variablen aus dem Kommunikations-Editor verwenden, um angepasste Depot Attribute in den Textkörper einer Kommunikation einzubetten. Beim Senden an die Depotbank wird das Seriendruckfeld mit dem entsprechenden Feld aufgefüllt. Wenn beispielsweise an den Depotbank John Smith gesendet wird, würde das Seriendruckfeld [Depot Name] mit dem entsprechenden Namen übersetzt werden.

Sie können Seriendruckfelder verwenden, indem Sie die **Seriendruckfeld** Symbole oben im Rich-Text-Editor-Steuerelement auswählen. Der Platzhalter wird basierend auf dem Speicherort des Cursors der Benutzer hinzugefügt.

### <a name="list-of-merge-field-variables"></a>Liste der Seriendruckfeld Variablen

| Feldname                  | Feld Details |
| :------------------- | :------------------- |
| Anzeigename  | Der vor-und Nachname des Depotbank. | 
| Bestätigungs Link | Ein benutzerdefinierter Link zum Aufzeichnen der Bestätigung jeder Depotbank.|                 |
| Portal Link     | Ein benutzerdefinierter Link für das Compliance-Portal des Depotbank.|                |
| Ausstellenden Offizier                   | Die e-Mail-Adresse des angegebenen ausstellenden Offiziers.|                   |
| Ausstellendes Datum                   | Das Datum, an dem der Hinweis ausgegeben wurde (UTC).              |
|||
