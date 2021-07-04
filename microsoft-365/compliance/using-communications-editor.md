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
description: Verwenden Sie den Kommunikations-Editor, um Text zu ändern und Feldvariablen zusammenzuführen, wenn Sie Ihre Inhalte formatieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 26076ff82ba226c2993c7c40e36bca2e08cbf683
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288119"
---
# <a name="use-the-communications-editor"></a>Verwenden des Kommunikations-Editors

Wenn Sie die Inhalte Ihrer Portalinhalte, Benachrichtigungen über gesetzliche Aufbewahrungspflicht und zugehörige Erinnerungen/Eskalationen definieren, können Sie den Kommunikations-Editor verwenden, um Ihre Inhalte zu formatieren und dynamisch anzupassen.

## <a name="rich-text-editor"></a>Rich-Text-Editor

Mit dem Kommunikations-Editor können Benutzer den Text mithilfe der Editoroptionen anpassen. Beispielsweise können Benutzer Schriftartentypen ändern, Aufzählungen erstellen, Inhalte hervorheben und vieles mehr.

## <a name="merge-field-variables"></a>Zusammenführen von Feldvariablen

Sie können E-Mail-Seriendruckvariablen aus dem Kommunikations-Editor verwenden, um angepasste Verwahrerattribute in den Textkörper einer Kommunikation einzubetten. Wenn es an den Verwahrer gesendet wird, wird das Seriendruckfeld mit dem entsprechenden Feld aufgefüllt. Wenn sie beispielsweise an den Verwalter John Smith gesendet werden, wird das Seriendruckfeld [Verwahrername] mit dem entsprechenden Namen übersetzt.

Sie können Seriendruckfelder verwenden, indem Sie die **Seriendruckfeldsymbole** oben im Rich-Text-Editor-Steuerelement auswählen. Der Platzhalter wird basierend auf der Position des Cursors des Benutzers hinzugefügt.

### <a name="list-of-merge-field-variables"></a>Liste der Zusammenführungsfeldvariablen

<br>

****

|Feldname|Felddetails|
|---|---|
|Anzeigename|Vor- und Nachname des Verwalters.|
|Bestätigungslink|Ein angepasster Link zum Aufzeichnen der Bestätigung jedes Verwahrers.|
|Portallink|Ein angepasster Link für das Compliance-Portal des Verwalters.|
|Ausstellende Beauftragte|Die E-Mail-Adresse des angegebenen Ausstellenden Beauftragten.|
|Ausgabedatum|Das Datum, an dem die Benachrichtigung ausgegeben wurde (UTC).|
|
