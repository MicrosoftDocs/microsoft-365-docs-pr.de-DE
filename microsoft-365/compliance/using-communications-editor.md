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
description: Verwenden Sie den Kommunikations-Editor, um Text- und Serienfeldvariablen zu ändern, wenn Sie Ihre Inhalte formatieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769160"
---
# <a name="use-the-communications-editor"></a>Verwenden des Kommunikations-Editors

Wenn Sie den Inhalt Ihrer Portalinhalte, Benachrichtigungen über gesetzliche Benachrichtigungen und zugehörige Erinnerungen/Eskalationen definieren, können Sie den Kommunikations-Editor verwenden, um Ihre Inhalte zu formatieren und dynamisch anzupassen.

## <a name="rich-text-editor"></a>Rich-Text-Editor

Der Kommunikations-Editor ermöglicht benutzern das Anpassen des Texts mithilfe der Editoroptionen. Beispielsweise können Benutzer Schriftartentypen ändern, Aufzählungen erstellen, Inhalte hervorheben und vieles mehr.

## <a name="merge-field-variables"></a>Zusammenführen von Feldvariablen

Sie können E-Mail-Zusammenführungsvariablen aus dem Kommunikations-Editor verwenden, um angepasste Verwahrerattribute in den Textkörper einer Kommunikation einzubetten. Wenn es an den Verwahrer gesendet wird, wird das Seriendruckfeld mit dem entsprechenden Feld aufgefüllt. Wenn sie z. B. an den Verwahrer John Smith gesendet werden, wird das Seriendruckfeld [Custodian Name] mit dem entsprechenden Namen übersetzt.

Sie können E-Mail-Seriendruckfelder verwenden, indem Sie die Symbole des Seriendruckfelds oben im Rich-Text-Editor-Steuerelement auswählen.  Der Platzhalter wird basierend auf der Position des Cursors der Benutzer hinzugefügt.

### <a name="list-of-merge-field-variables"></a>Liste der Seriendruckfeldvariablen

| Feldname                  | Felddetails |
| :------------------- | :------------------- |
| Anzeigename  | Der Vor- und Nachname des Verwahrers. | 
| Bestätigungslink | Ein angepasster Link zum Aufzeichnen der Bestätigung jedes Custodians.|                 |
| Portallink     | Ein angepasster Link für das Complianceportal des Custodians.|                |
| Ausstellende Beauftragte                   | Die E-Mail-Adresse des angegebenen ausstellenden Beauftragten.|                   |
| Ausgabedatum                   | Das Datum, an dem der Hinweis ausgegeben wurde (UTC).              |
|||
