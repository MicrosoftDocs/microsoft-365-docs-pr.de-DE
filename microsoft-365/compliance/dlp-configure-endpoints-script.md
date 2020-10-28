---
title: Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts
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
description: Verwenden Sie ein lokales Skript, um das Konfigurationspaket auf Geräten bereitzustellen, damit diese in den Dienst eingehen.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769471"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts

**Gilt für:**

- [Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

Sie können auch einzelne Geräte manuell an die Microsoft 365-Endpunkt Verhinderung von Datenverlusten an Bord integrieren. Möglicherweise möchten Sie dies zunächst beim Testen des Diensts tun, bevor Sie ein Commit für das Onboarding aller Geräte in Ihrem Netzwerk ausführen.

> [!IMPORTANT]
> Dieses Skript wurde für die Verwendung auf bis zu 10 Geräten optimiert.
>
> Verwenden Sie [andere Bereitstellungsoptionen](dlp-configure-endpoints.md), um eine Skalierung bereitzustellen. Beispielsweise können Sie ein Onboarding-Skript für mehr als 10 Geräte in der Produktion mit dem Skript bereitstellen, das in integrierten [Windows 10-Geräten mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)zur Verfügung steht.

## <a name="onboard-devices"></a>Integrierte Geräte
 
1.  Öffnen Sie die ZIP-Datei des GP-Konfigurationspakets ( *DeviceComplianceOnboardingPackage.zip* ), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben. Sie können das Paket auch über das [Microsoft Compliance Center](https://compliance.microsoft.com) abrufen.

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Gerät Onboarding** aus.

3. Wählen Sie im Feld **Bereitstellungsmethode** die Option **Lokales Skript** aus.

4. Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.
  
5. Extrahieren Sie den Inhalt des Konfigurationspakets an einen Speicherort auf dem Gerät, das Sie onboardieren möchten (beispielsweise den Desktop). Sie sollten über eine Datei mit dem Namen " *DeviceOnboardingScript. cmd* " verfügen.

6.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:

7.  Wechseln Sie zu **Start** , und geben Sie **cmd** ein.

8.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** , und wählen Sie **als Administrator ausführen** aus.

![Fenster Start Menü, das auf als Administrator ausführen zeigt](../media/dlp-run-as-admin.png)

9.  Geben Sie den Speicherort der Skriptdatei ein. Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie Folgendes ein: *%UserProfile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Drücken Sie die **Eingabe** Taste, oder klicken Sie auf **OK** .

Informationen dazu, wie Sie manuell überprüfen können, ob das Gerät kompatibel ist und Sensordaten ordnungsgemäß meldet, finden Sie unter [Troubleshoot Microsoft Defender Advanced Threat Protection Onboarding Issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

## <a name="offboard-devices-using-a-local-script"></a>Extern-Geräte mit einem lokalen Skript
Aus Sicherheitsgründen läuft das Paket, das für extern-Geräte verwendet wird, 30 Tage nach dem heruntergeladenen Datum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden zurückgewiesen. Wenn Sie ein offboarding-Paket herunterladen, werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen eingeschlossen.

> [!NOTE]
> Onboarding-und offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da dies andernfalls zu unvorhersehbaren Konflikten führen kann.

1. Abrufen des offboarding-Pakets im [Microsoft Compliance Center](https://compliance.microsoft.com)

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Gerät offboarding** .

3. Wählen Sie im Feld **Bereitstellungsmethode** die Option **Lokales Skript** aus.

4. Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.

5. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Geräte zugreifen können. Sie sollten über eine Datei mit dem Namen *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* verfügen.

6.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:

7.  Wechseln Sie zu **Start** , und geben Sie **cmd** ein.

8.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** , und wählen Sie **als Administrator ausführen** aus.

![Fenster Start Menü, das auf als Administrator ausführen zeigt](../media/dlp-run-as-admin.png)

9.  Geben Sie den Speicherort der Skriptdatei ein. Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie Folgendes ein: *%UserProfile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd. cmd*

10.  Drücken Sie die **Eingabe** Taste, oder klicken Sie auf **OK** .

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration
Sie können die unterschiedlichen Überprüfungsschritte im Thema [Problembehandlung bei Problemen mit dem Onboarding] befolgen ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) um zu überprüfen, ob das Skript erfolgreich abgeschlossen wurde und der Agent ausgeführt wird.

Die Überwachung kann auch direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools erfolgen.

### <a name="monitor-devices-using-the-portal"></a>Überwachen von Geräten mithilfe des Portals
1. Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com).

2. Wählen Sie **Einstellungen**  >  **Geräte-Onboarding**  >  - **Geräte** aus.

3. Stellen Sie sicher, dass die Geräte angezeigt werden.


## <a name="related-topics"></a>Verwandte Themen
- [Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Onboard-Windows 10-Geräte mit Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte](dlp-configure-endpoints-mdm.md)
- [Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)](dlp-configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender-ATP-Gerät](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
