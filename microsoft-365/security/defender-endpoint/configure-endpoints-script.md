---
title: Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts
description: Verwenden Sie ein lokales Skript, um das Konfigurationspaket auf Geräten bereitzustellen, damit sie in den Dienst integriert sind.
keywords: Konfigurieren von Geräten mithilfe eines lokalen Skripts, Geräteverwaltung, Konfigurieren von Microsoft Defender für Endpunktgeräte
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2510fb1a187bbe136669e11bc73103438b51d811
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842170"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Sie können auch einzelne Geräte manuell in Defender für Endpunkt integrieren. Sie sollten dies zuerst tun, wenn Sie den Dienst testen, bevor Sie einen Commit für das Onboarding aller Geräte in Ihrem Netzwerk ausführen.

> [!IMPORTANT]
> Dieses Skript wurde für die Verwendung auf bis zu 10 Geräten optimiert.
>
> Verwenden Sie andere [Bereitstellungsoptionen,](configure-endpoints.md)um eine skalierungsbezogene Bereitstellung durchzuführen. Beispielsweise können Sie ein Onboardingskript auf mehr als 10 Geräten in der Produktion bereitstellen, wobei das Skript im [Onboard-Windows 10-Geräten mithilfe von Gruppenrichtlinien](configure-endpoints-gp.md)verfügbar ist.

## <a name="onboard-devices"></a>Onboarding von Geräten 

[![Abbildung der PDF-Datei mit den verschiedenen Bereitstellungspfaden](images/onboard-script.png)](images/onboard-script.png#lightbox)


Sehen Sie sich die [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) oder [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Defender für Endpunkt anzuzeigen. 


1.  Öffnen Sie das GP-Konfigurationspaket .zip Datei (*WindowsDefenderATPOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben. Sie können das Paket auch von [Microsoft Defender Security Center](https://securitycenter.windows.com/)abrufen:

    1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding** aus.

    1. Wählen Sie Windows 10 als Betriebssystem aus.

    1. Wählen Sie im Feld **"Bereitstellungsmethode"** die Option **"Lokales Skript"** aus.

    1. Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.

  
2.  Extrahieren Sie den Inhalt des Konfigurationspakets an einen Speicherort auf dem Gerät, das Sie integrieren möchten (z. B. desktop). Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPLocalOnboardingScript.cmd verfügen.*

3.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:

    1.  Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

    1.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

        ![Startmenü des Fensters, das auf "Als Administrator ausführen" verweist](images/run-as-admin.png)

4.  Geben Sie den Speicherort der Skriptdatei ein. Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie Folgendes ein: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*

5.  Drücken Sie die **EINGABETASTE,** oder klicken Sie auf **"OK".**

Informationen dazu, wie Sie manuell überprüfen können, ob das Gerät kompatibel ist und Sensordaten ordnungsgemäß meldet, finden Sie unter "Behandeln von Problemen beim Onboarding von [Microsoft Defender für Endpunkten".](troubleshoot-onboarding.md)


>[!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob ein Gerät ordnungsgemäß in den Dienst integriert ist. Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt.](run-detection-test.md)

## <a name="configure-sample-collection-settings"></a>Konfigurieren von Beispielsammlungseinstellungen
Für jedes Gerät können Sie einen Konfigurationswert festlegen, um anzugeben, ob Beispiele vom Gerät erfasst werden können, wenn eine Anforderung über Microsoft Defender Security Center zum Übermitteln einer Datei für eine umfassende Analyse gestellt wird.

Sie können die Beispielfreigabeeinstellung auf dem Gerät manuell konfigurieren, indem Sie *regedit* verwenden oder eine *REG-Datei* erstellen und ausführen.  

Die Konfiguration wird über den folgenden Registrierungsschlüsseleintrag festgelegt:

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Dabei gilt:<br>
Der Namenstyp ist ein D-WORD-Element. <br>
Die folgenden Werte sind möglich:
- 0 – lässt keine Beispielfreigabe von diesem Gerät zu
- 1 – ermöglicht die Freigabe aller Dateitypen von diesem Gerät

Der Standardwert für den Fall, dass der Registrierungsschlüssel nicht vorhanden ist, ist 1.


## <a name="offboard-devices-using-a-local-script"></a>Offboarding von Geräten mithilfe eines lokalen Skripts
Aus Sicherheitsgründen läuft das Paket, das für Offboard-Geräte verwendet wird, 30 Tage nach dem Datum ab, an dem es heruntergeladen wurde. Abgelaufene Offboardingpakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines Offboardingpakets werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, andernfalls führt dies zu unvorhersehbaren Kollisionen.

1. Abrufen des Offboarding-Pakets aus [Microsoft Defender Security Center:](https://securitycenter.windows.com/)

    1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Offboarding** aus.

    1. Wählen Sie Windows 10 als Betriebssystem aus.

    1. Wählen Sie im Feld **"Bereitstellungsmethode"** die Option **"Lokales Skript"** aus.

    1. Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.

2. Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Geräte zugreifen können. Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*

3.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:

    1.  Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

    1.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

        ![Startmenü des Fensters, das auf "Als Administrator ausführen" verweist](images/run-as-admin.png)

4.  Geben Sie den Speicherort der Skriptdatei ein. Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie Folgendes ein: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5.  Drücken Sie die **EINGABETASTE,** oder klicken Sie auf **"OK".**

> [!IMPORTANT]
> Das Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweise auf warnungen, die es gesendet hat, werden bis zu 6 Monate lang aufbewahrt.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration
Sie können die verschiedenen Überprüfungsschritte in der [Problembehandlung von Integrationsproblemen](troubleshoot-onboarding.md) ausführen, um zu überprüfen, ob das Skript erfolgreich abgeschlossen wurde und der Agent ausgeführt wird.

Die Überwachung kann auch direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools erfolgen.

### <a name="monitor-devices-using-the-portal"></a>Überwachen von Geräten mithilfe des Portals
1. Wechseln Sie zu Microsoft Defender Security Center.

2. Klicken Sie auf **"Geräteliste".**

3. Stellen Sie sicher, dass Geräte angezeigt werden.


## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien](configure-endpoints-gp.md)
- [Onboarding von Windows 10 Geräten mithilfe von Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](configure-endpoints-mdm.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät](run-detection-test.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten](troubleshoot-onboarding.md)
