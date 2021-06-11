---
title: Sammeln von Diagnosedaten für updatecompliance und Windows Defender Microsoft Defender Antivirus
description: Verwenden Sie ein Tool zum Sammeln von Daten, um Probleme mit der Updatecompliance zu beheben, wenn Sie das Microsoft Defender Antivirus Assessment-Add-In verwenden.
keywords: Troubleshoot, error, fix, update compliance, oms, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 9fbe2b624bec6bbe17bcf6bc8d3f842ba1e43ad7
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903732"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>Sammeln von Diagnosedaten zur Updatecompliance für Microsoft Defender Antivirus Bewertung


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In diesem Artikel wird beschrieben, wie Sie Diagnosedaten sammeln, die von Microsoft-Support- und -Entwicklungsteams zur Behandlung von Problemen verwendet werden können, die bei der Verwendung des Abschnitts Microsoft Defender Antivirus Bewertung im Updatecompliance-Add-In auftreten können.

Bevor Sie diesen Vorgang durchführen, stellen Sie sicher, dass Sie [die Problembehandlung Microsoft Defender Antivirus Berichterstellung](troubleshoot-reporting.md)gelesen haben, alle erforderlichen Voraussetzungen erfüllt und alle anderen vorgeschlagenen Schritte zur Problembehandlung ausgeführt haben.

Rufen Sie auf mindestens zwei Geräten, die keine Berichte erstellen oder in der Updatecompliance angezeigt werden, die .cab Diagnosedatei ab, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie eine Version der Eingabeaufforderung auf Administratorebene wie folgt:
        
    a. Öffnen Sie das **Startmenü.**

    b. Geben Sie **cmd ein.** Klicken Sie mit der rechten Maustaste auf **die Eingabeaufforderung,** und wählen Sie dann **als Administrator ausführen** aus.

    c. Geben Sie Administratoranmeldeinformationen an, oder genehmigen Sie die Eingabeaufforderung.
        
2. Navigieren Sie zum Windows Defender Verzeichnis. Der Standardwert ist `C:\Program Files\Windows Defender`.

3. Geben Sie den folgenden Befehl ein, und drücken Sie dann die **EINGABETASTE.**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. Es wird eine .cab Datei generiert, die verschiedene Diagnoseprotokolle enthält. Der Speicherort der Datei wird in der Ausgabe in der Eingabeaufforderung angegeben. Standardmäßig lautet der Speicherort `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

5. Kopieren Sie diese .cab-Dateien an einen Speicherort, auf den der Microsoft-Support zugreifen kann. Ein Beispiel kann ein kennwortgeschützter OneDrive Ordner sein, den Sie für uns freigeben können.

6. Senden Sie eine E-Mail mithilfe der <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">E-Mail-Vorlage zur Updatecomplianceunterstützung,</a>und füllen Sie die Vorlage mit den folgenden Informationen aus:
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>Siehe auch

- [Problembehandlung bei Windows Defender Microsoft Defender Antivirus Berichterstellung](troubleshoot-reporting.md)