---
title: Sammeln von Diagnosedaten von Microsoft Defender Antivirus
description: Verwenden eines Tools zum Sammeln von Daten zur Problembehandlung bei Microsoft Defender Antivirus
keywords: Troubleshoot, error, fix, update compliance, oms, monitor, report, Microsoft Defender av, group policy object, setting, diagnostic data
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 7686f28646135986a78b4c269e41e2fc3a70dff9
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904044"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a>Sammeln von Microsoft Defender AV-Diagnosedaten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In diesem Artikel wird beschrieben, wie Sie Diagnosedaten sammeln, die von Microsoft-Support- und -Entwicklungsteams zur Behandlung von Problemen verwendet werden können, die bei der Verwendung von Microsoft Defender AV auftreten können.

> [!NOTE]
> Im Rahmen des Untersuchungs- oder Reaktionsprozesses können Sie ein Untersuchungspaket von einem Gerät erfassen. Hier sehen Sie, wie: [Erfassen Sie untersuchungspaket von Geräten](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).

Rufen Sie auf mindestens zwei Geräten, auf denen dasselbe Problem auftritt, die .cab Diagnosedatei ab, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie eine Version der Eingabeaufforderung auf Administratorebene wie folgt:

    a. Öffnen Sie das **Startmenü.**

    b. Geben Sie **cmd ein.** Klicken Sie mit der rechten Maustaste auf **die Eingabeaufforderung,** und wählen Sie dann **als Administrator ausführen** aus.

    c. Geben Sie Administratoranmeldeinformationen an, oder genehmigen Sie die Eingabeaufforderung.

2. Navigieren Sie zum Microsoft Defender-Verzeichnis. Der Standardwert ist `C:\Program Files\Windows Defender`.

> [!NOTE]
> Wenn Sie eine [aktualisierte Version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)von Microsoft Defender Platform ausführen, führen Sie dies bitte `MpCmdRun` an folgendem Speicherort aus: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .

3. Geben Sie den folgenden Befehl ein, und drücken Sie dann die **EINGABETASTE.**  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. Es wird eine .cab Datei generiert, die verschiedene Diagnoseprotokolle enthält. Der Speicherort der Datei wird in der Ausgabe in der Eingabeaufforderung angegeben. Standardmäßig lautet der Speicherort `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .

> [!NOTE]
> Um die CAB-Datei an einen anderen Pfad oder eine andere UNC-Freigabe umzuleiten, verwenden Sie den folgenden Befehl: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`  <br/>Weitere Informationen finden Sie unter [Umleiten von Diagnosedaten an eine UNC-Freigabe.](#redirect-diagnostic-data-to-a-unc-share)

5. Kopieren Sie diese .cab-Dateien an einen Speicherort, auf den der Microsoft-Support zugreifen kann. Ein Beispiel könnte ein kennwortgeschützter OneDrive Ordner sein, den Sie für uns freigeben können.

> [!NOTE]
>Wenn Sie ein Problem mit der Updatecompliance haben, senden Sie eine E-Mail mithilfe der <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">E-Mail-Vorlage zur Updatecompliance-Unterstützung,</a>und füllen Sie die Vorlage mit den folgenden Informationen aus:
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a>Umleiten von Diagnosedaten an eine UNC-Freigabe
Um Diagnosedaten in einem zentralen Repository zu sammeln, können Sie den SupportLogLocation-Parameter angeben.

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

Kopiert die Diagnosedaten in den angegebenen Pfad. Wenn der Pfad nicht angegeben ist, werden die Diagnosedaten an den in der Konfiguration des Supportprotokollspeicherorts angegebenen Speicherort kopiert.

Wenn der Parameter SupportLogLocation verwendet wird, wird eine Ordnerstruktur wie folgt im Zielpfad erstellt:

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| Feld  | Beschreibung   |
|:----|:----|
| path | Der Pfad, wie in der Befehlszeile angegeben oder aus der Konfiguration abgerufen
| MMDD | Monat und Tag, an dem die Diagnosedaten gesammelt wurden (z. B. 0530)
| Hostname | Der Hostname des Geräts, auf dem die Diagnosedaten gesammelt wurden.
| HHMM | Stunden und Minuten, in dem die Diagnosedaten gesammelt wurden (z. B. 1422)

> [!NOTE]
> Stellen Sie bei Verwendung einer Dateifreigabe sicher, dass das konto, das zum Sammeln des Diagnosepakets verwendet wird, Schreibzugriff auf die Freigabe hat.  

## <a name="specify-location-where-diagnostic-data-is-created"></a>Angeben des Speicherorts, an dem Diagnosedaten erstellt werden

Sie können auch angeben, wo die Diagnosedatei .cab mithilfe eines Gruppenrichtlinienobjekts (Group Policy Object, GPO) erstellt wird. 

1. Öffnen Sie den Editor für lokale Gruppenrichtlinien, und suchen Sie das SupportLogLocation-Gruppenrichtlinienobjekt unter: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`
   
1. Wählen Sie **den Verzeichnispfad zum Kopieren von Supportprotokolldateien** aus.

    ![Screenshot des Editors für lokale Gruppenrichtlinien](images/GPO1-SupportLogLocationDefender.png)  
        
     ![Screenshot der Einstellung zum Definieren des Pfads für Protokolldateien](images/GPO2-SupportLogLocationGPPage.png)  
3. Wählen Sie im Richtlinien-Editor **aktiviert** aus.
       
4. Geben Sie den Verzeichnispfad an, in den Sie die Supportprotokolldateien im Feld **"Optionen"** kopieren möchten.
     ![Screenshot der benutzerdefinierten Einstellung für aktivierten Verzeichnispfad](images/GPO3-SupportLogLocationGPPageEnabledExample.png) 
5. Wählen Sie **"OK"** oder **"Anwenden"** aus.

## <a name="see-also"></a>Siehe auch

- [Problembehandlung bei Microsoft Defender Antivirus Berichterstellung](troubleshoot-reporting.md)