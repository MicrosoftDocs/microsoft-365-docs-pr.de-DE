---
title: Sammeln von Diagnosedaten für update compliance and Windows Defender Microsoft Defender Antivirus
description: Verwenden eines Tools zum Sammeln von Daten zur Problembehandlung von Problemen mit der Updatekonformität bei Verwendung des Microsoft Defender Antivirus Assessment-Add-Ins
keywords: Problembehandlung, Fehler, Behebung, Updatekonformität, Oms, Monitor, Bericht, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f2b3060d7f0d9daf0f923c674f2fe45ba976fdfc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764735"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a>Sammeln von Diagnosedaten zur Updatekonformität für die Microsoft Defender AV-Bewertung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In diesem Artikel wird beschrieben, wie Sie Diagnosedaten sammeln, die von Microsoft-Support- und Engineeringteams verwendet werden können, um Probleme zu beheben, die möglicherweise auftreten, wenn Sie den Abschnitt Microsoft Defender AV Assessment im Update Compliance-Add-In verwenden.

Bevor Sie diesen Prozess versuchen, stellen Sie sicher, dass Sie die Problembehandlung für [Microsoft Defender Antivirus](troubleshoot-reporting.md)gelesen haben, alle erforderlichen Voraussetzungen erfüllt haben und alle anderen vorgeschlagenen Schritte zur Problembehandlung ausgeführt haben.

Rufen Sie auf mindestens zwei Geräten, die nicht in update compliance berichten oder angezeigt werden, die Cab-Diagnosedatei ab, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie eine Administratorversion der Eingabeaufforderung wie folgt:
        
    a. Öffnen Sie das **Startmenü.**

    b. Geben **Sie cmd ein.** Klicken Sie mit der rechten Maustaste **auf Eingabeaufforderung,** und klicken **Sie auf Als Administrator ausführen**.

    c. Geben Sie Administratoranmeldeinformationen ein, oder genehmigen Sie die Eingabeaufforderung.
        
2. Navigieren Sie zum Windows Defender Verzeichnis. Der Standardwert ist `C:\Program Files\Windows Defender`.

3. Geben Sie den folgenden Befehl ein, und drücken Sie dann die **EINGABETASTE.**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. Es wird eine CAB-Datei generiert, die verschiedene Diagnoseprotokolle enthält. Der Speicherort der Datei wird in der Ausgabe in der Eingabeaufforderung angegeben. Standardmäßig ist der Speicherort `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

5. Kopieren Sie diese CAB-Dateien an einen Speicherort, auf den vom Microsoft-Support zugegriffen werden kann. Ein Beispiel könnte ein kennwortgeschützter OneDrive-Ordner sein, den Sie für uns freigeben können.

6. Senden Sie eine E-Mail mithilfe der E-Mail-Vorlage update <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">compliance</a>support, und füllen Sie die Vorlage mit den folgenden Informationen aus:
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>Siehe auch

- [Problembehandlung Windows Defender Microsoft Defender Antivirus-Berichterstellung](troubleshoot-reporting.md)