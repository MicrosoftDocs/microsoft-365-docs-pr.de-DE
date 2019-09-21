---
title: Verwenden des Kommunikations-Editors
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
description: ''
ms.openlocfilehash: 78865efc5c10ebcff9742f922f675b637bb9b2b0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082127"
---
# <a name="use-the-communications-editor"></a>Verwenden des Kommunikations-Editors

Wenn Sie den Inhalt Ihrer Portalinhalte, Benachrichtigungen über rechtliche Aufbewahrungszeit und zugehörige Erinnerungen/Eskalationen definieren, können Sie den Kommunikations-Editor nutzen, um Ihre Inhalte zu formatieren und dynamisch anzupassen.

## <a name="rich-text-editor"></a>Rich-Text-Editor 

Mit dem Kommunikations-Editor können Benutzer den Text mithilfe der Editor-Optionen anpassen. Beispielsweise können Benutzer Schriftarttypen ändern, Aufzählungslisten erstellen, Inhalte hervorheben und vieles mehr. 

## <a name="merge-field-variables"></a>Zusammenführen von Feld Variablen

Sie können e-Mail-Zusammenführungs Variablen aus dem Kommunikations-Editor nutzen, um angepasste Depot Attribute in den Textkörper einer Kommunikation einzubetten. Beim Senden an die Depotbank wird das Seriendruckfeld mit dem entsprechenden Feld aufgefüllt. Wenn beispielsweise an den Depotbank John Smith gesendet wird, würde das Seriendruckfeld [Depot Name] mit dem entsprechenden Namen übersetzt werden. 

Sie können Seriendruckfelder verwenden, indem Sie die **Seriendruckfeld** Symbole oben im Rich-Text-Editor-Steuerelement auswählen. Der Platzhalter wird basierend auf dem Speicherort des Cursors der Benutzer hinzugefügt. 

### <a name="list-of-merge-field-variables"></a>Liste der Seriendruckfeld Variablen

| Feldname                  | Feld Details | 
| :------------------- | :------------------- |
| Anzeigename  | Der vor-und Nachname des Depotbank. | 
| Bestätigungs Link | Ein benutzerdefinierter Link zum Aufzeichnen der Bestätigung jedes Verwalters.|                 |
| Portal Link     | Ein benutzerdefinierter Link für das Compliance-Portal des Depotbank.|                |
| Ausstellenden Offizier                   | Die e-Mail-Adresse des angegebenen ausstellenden Offiziers.|                   |
| Ausstellendes Datum                   | Das Datum, an dem der Hinweis ausgegeben wurde (UTC).              |