---
title: Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Verwenden Sie ein lokales Skript, um das Konfigurationspaket auf Geräten bereitzustellen, damit sie in den Dienst integriert sind.
ms.openlocfilehash: 55109d8fda52db6651d4398cd84ffd6668b4d871
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843446"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts

**Gilt für:**

- [Microsoft 365 Verhinderung von Datenverlust am Endpunkt (Endpoint Data Loss Prevention, DLP)](./endpoint-dlp-learn-about.md)

Sie können auch einzelne Geräte manuell in Microsoft 365 Endpunkt-Verhinderung von Datenverlust integrieren. Sie sollten dies zuerst tun, wenn Sie den Dienst testen, bevor Sie einen Commit für das Onboarding aller Geräte in Ihrem Netzwerk ausführen.

> [!IMPORTANT]
> Dieses Skript wurde für die Verwendung auf bis zu 10 Geräten optimiert.
>
> Verwenden Sie andere [Bereitstellungsoptionen,](dlp-configure-endpoints.md)um eine skalierungsbezogene Bereitstellung durchzuführen. Beispielsweise können Sie ein Onboardingskript auf mehr als 10 Geräten in der Produktion bereitstellen, wobei das Skript im [Onboard-Windows 10-Geräten mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)verfügbar ist.

## <a name="onboard-devices"></a>Onboarding von Geräten
 
1.  Öffnen Sie das GP-Konfigurationspaket .zip Datei (*DeviceComplianceOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben. Sie können das Paket auch aus dem [Microsoft Compliance Center](https://compliance.microsoft.com) abrufen.

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Geräte-Onboarding** aus.

3. Wählen Sie im Feld **"Bereitstellungsmethode"** die Option **"Lokales Skript"** aus.

4. Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.
  
5. Extrahieren Sie den Inhalt des Konfigurationspakets an einen Speicherort auf dem Gerät, das Sie integrieren möchten (z. B. desktop). Sie sollten über eine Datei mit dem Namen *DeviceOnboardingScript.cmd verfügen.*

6.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:

7.  Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

8.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

    ![Startmenü des Fensters, das auf "Als Administrator ausführen" verweist](../media/dlp-run-as-admin.png)

9.  Geben Sie den Speicherort der Skriptdatei ein. Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie Folgendes ein: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Drücken Sie die **EINGABETASTE,** oder klicken Sie auf **"OK".**

Informationen dazu, wie Sie manuell überprüfen können, ob das Gerät kompatibel ist und Sensordaten ordnungsgemäß meldet, finden Sie unter [Problembehandlung bei Microsoft Defender Advanced Threat Protection Integrationsproblemen.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)

## <a name="offboard-devices-using-a-local-script"></a>Offboarding von Geräten mithilfe eines lokalen Skripts
Aus Sicherheitsgründen läuft das Paket, das für Offboard-Geräte verwendet wird, 30 Tage nach dem Datum ab, an dem es heruntergeladen wurde. Abgelaufene Offboardingpakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines Offboardingpakets werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, andernfalls führt dies zu unvorhersehbaren Kollisionen.

1. Abrufen des Offboarding-Pakets aus dem [Microsoft Compliance Center](https://compliance.microsoft.com)

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Geräte-Offboarding** aus.

3. Wählen Sie im Feld **"Bereitstellungsmethode"** die Option **"Lokales Skript"** aus.

4. Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.

5. Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Geräte zugreifen können. Sie sollten über eine Datei mit dem Namen *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* verfügen.

6.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:

7.  Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

8.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

    ![Startmenü des Fensters, das auf "Als Administrator ausführen" verweist](../media/dlp-run-as-admin.png)

9.  Geben Sie den Speicherort der Skriptdatei ein. Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie Folgendes ein: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

10.  Drücken Sie die **EINGABETASTE,** oder klicken Sie auf **"OK".**

> [!IMPORTANT]
> Das Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration
Sie können die verschiedenen Überprüfungsschritte in der [Problembehandlung bei Integrationsproblemen]((/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) ausführen, um zu überprüfen, ob das Skript erfolgreich abgeschlossen wurde und der Agent ausgeführt wird.

Die Überwachung kann auch direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools erfolgen.

### <a name="monitor-devices-using-the-portal"></a>Überwachen von Geräten mithilfe des Portals
1. Wechseln Sie zum [Microsoft 365 Compliance Center.](https://compliance.microsoft.com)

2. Wählen Sie **Einstellungen**  >  **Geräte-Onboardinggeräte**  >  aus.

3. Stellen Sie sicher, dass Geräte angezeigt werden.


## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Onboarding von Windows 10 Geräten mithilfe von Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](dlp-configure-endpoints-mdm.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](dlp-configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Behandeln von Problemen beim Microsoft Defender Advanced Threat Protection Onboarding](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)