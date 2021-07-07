---
title: Richtlinien für Testpakete
description: Überprüfen der Richtlinien für das Testpaket
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322758"
---
# <a name="test-package-guidelines"></a>Richtlinien für Testpakete

## <a name="1---script-referencing"></a>1. Skriptreferenzierung

Wenn Sie eine .zip-Datei in das Portal hochladen, entpacken wir den gesamten Inhalt dieser Datei in einen Stammordner. Sie müssen keinen Code schreiben, um diesen anfänglichen Entzippenvorgang durchzuführen. Sie können auch auf eine beliebige Datei innerhalb des .zip verweisen, indem Sie den Pfad relativ zur hochgeladenen ZIP-Datei verwenden.

Im folgenden Beispiel wird gezeigt, wie Sie über das Eingabefeld auf der Registerkarte "Aufgaben" auf Ihre Binärdateien/Skripts verweisen können. Der Text in Blau sollte ohne **Anführungszeichen** in das **Feld "Skriptpfad"** eingegeben werden.

Es ist wichtig, dass Sie die Inhalte in Ihrer ZIP-Datei kennen, bevor Sie sie hochladen. Beim Zippen eines Ordners erstellt Ihr lokaler Computer häufig einen Hauptordner unter der ZIP-Datei. In diesem Fall ist der Verweis wie unten **fett** dargestellt:

 **Contoso_App_Folder.zip**
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**
  - Script.ps1 – **"Contoso_App_Folder/folder1/script.ps1"**

In anderen Fällen enthält Ihre ZIP-Datei möglicherweise Ihre Dateien oder Inhalte direkt darunter, d. h. keinen Ordner auf 2. Ebene:

 **Zip_file_uploaded.zip**
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - ScriptX.ps1 – **"ScriptX.ps1"**
  - Script.ps1 – **"folder1/script.ps1"**
  
## <a name="2---script-execution"></a>2. Skriptausführung

**Out-of-Box-Tests:** Das Anwendungspaket muss mindestens drei PowerShell-Skripts enthalten, die das unbeaufsichtigte Installieren, Starten und Schließen der Anwendung und ihrer Abhängigkeiten ausführen. Jedes Skript sollte die Überprüfung der eigenen Voraussetzungen, das Überprüfen des Erfolgreichen sowie das Aufräumen nach sich selbst (falls erforderlich) durchführen.

**Funktionstests:** Das Anwendungspaket muss mindestens ein PowerShell-Skript enthalten. Wenn mehrere Skripts bereitgestellt werden, werden die Skripts in der Uploadsequenz ausgeführt, und ein Fehler in einem bestimmten Skript beendet die Ausführung nachfolgender Skripts.

### <a name="script-requirements"></a>Skriptanforderungen

• PowerShell Version 5.1+     

• Unbeaufsichtigte Ausführung    

• Fehlerrückgabecode               

• Überprüfen des Erfolgs            

• Protokollierung in skriptspezifischen Protokollordnern

Jedes Skript muss vollständig unbeaufsichtigt ausgeführt werden, um in der Testpipeline erfolgreich ausgeführt zu werden.

> [!Note]
> Skripts sollten bei erfolgreichem Abschluss "0" und einen Fehlercode ungleich Null zurückgeben, wenn während der Ausführung ein Fehler auftritt.

Jedes Skript sollte überprüfen, ob es erfolgreich ausgeführt wurde. Beispiel: Das Installationsskript sollte überprüfen, ob bestimmte Binärdateien und/oder Registrierungsschlüssel auf dem System vorhanden sind, nachdem die Ausführung der Binärdatei des Installationsprogramms abgeschlossen ist, um mit einem angemessenen Maß an Zuverlässigkeit sicherzustellen, dass die Installation erfolgreich war. 

Dies ist erforderlich, um ordnungsgemäß zu diagnostizieren, wo während eines Testlaufs Fehler auftreten, z. B. dass die Anwendung nicht erfolgreich installiert werden kann oder nicht gestartet werden kann.

> [!Important]
> **Vermeiden Sie Folgendes:** Skripts sollten den Computer nicht neu starten, wenn ein Neustart erforderlich ist, geben Sie dies während des Uploads Ihrer Skripts an.

## <a name="3---log-collection"></a>3. Protokollsammlung

Jedes Skript sollte alle generierten Protokolle in einem Ordner mit dem Namen ```logs``` ausgeben. Alle Ordner im benannten Verzeichnis ```logs``` werden kopiert und zum Download auf der Seite ```Test Results``` angezeigt.

Beispielsweise kann das Installationsskript (das sich im Verzeichnis **"App/skripts/install"** befindet) seine Protokolle ausgeben an: **logs/install.log,** sodass sich das endgültige Protokoll unter: **Apps/scripts/install/logs/install.log befindet.**

Das System übernimmt die ```install.log``` Datei zusammen mit anderen Dateien in anderen ```logs``` Ordnern und sortiert sie zum Download.


## <a name="4---application-binaries"></a>4. Anwendungsbinärdateien

Alle Binärdateien und Abhängigkeiten sollten in der einzelnen ZIP-Datei enthalten sein. 

Diese sollten alles enthalten, was für die Installation der Anwendung erforderlich ist (z. B. das Installationsprogramm der Anwendung); wenn die Anwendung von Frameworks wie .NET Core/Standard oder .NET Framework abhängig ist, sollten diese in der Datei enthalten sein und in den bereitgestellten Skripts korrekt referenziert werden.


> [!Note]
> Die hochgeladene ZIP-Datei darf keine Leerzeichen oder Sonderzeichen im Namen enthalten.

## <a name="next-steps"></a>Nächste Schritte

Wechseln Sie zum nächsten Artikel, um einige **häufig gestellte Fragen (FAQ)** anzuzeigen.
> [!div class="nextstepaction"]
> [Nächster Schritt](faq.md)
