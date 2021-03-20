---
title: Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts
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
description: Verwenden Sie ein lokales Skript, um das Konfigurationspaket auf Geräten so zu bereitstellen, dass sie in den Dienst onboardiert werden.
ms.openlocfilehash: 69a8295b170f9186d14862a7247cac3fb4c4ef3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917971"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts

**Gilt für:**

- [Microsoft 365 Endpoint Data Loss Prevention (DLP)](./endpoint-dlp-learn-about.md)

Sie können auch einzelne Geräte manuell in microsoft 365 Endpoint-Verhinderung von Datenverlust integrieren. Möglicherweise möchten Sie dies zuerst tun, wenn Sie den Dienst testen, bevor Sie sich zum Onboarding aller Geräte in Ihrem Netzwerk verpflichten.

> [!IMPORTANT]
> Dieses Skript wurde für die Verwendung auf bis zu 10 Geräten optimiert.
>
> Verwenden Sie andere Bereitstellungsoptionen, um die Bereitstellung [in der Skalierung zu implementieren.](dlp-configure-endpoints.md) Beispielsweise können Sie ein Onboardingskript auf mehr als 10 Geräten in der Produktion bereitstellen, mit dem Skript, das unter [Onboard Windows 10 devices using Group Policy verfügbar ist.](dlp-configure-endpoints-gp.md)

## <a name="onboard-devices"></a>Onboarding von Geräten
 
1.  Öffnen Sie die ZIP-Datei des *GP-Konfigurationspakets*(DeviceComplianceOnboardingPackage.zip), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben. Sie können das Paket auch über das [Microsoft Compliance Center erhalten.](https://compliance.microsoft.com)

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Geräte onboarding aus.**

3. Wählen Sie **im Feld Bereitstellungsmethode** die Option **Lokales Skript aus.**

4. Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.
  
5. Extrahieren Sie den Inhalt des Konfigurationspakets an einen Speicherort auf dem Gerät, das Sie onboarden möchten (z. B. desktop). Sie sollten über eine Datei mit dem Namen *DeviceOnboardingScript.cmd verfügen.*

6.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:

7.  Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

8.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

![Fensteranfangsmenü, das auf Als Administrator ausführen zeigt](../media/dlp-run-as-admin.png)

9.  Geben Sie den Speicherort der Skriptdatei ein. Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie ein: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Drücken Sie die **EINGABETASTE,** oder klicken Sie auf **OK**.

Informationen dazu, wie Sie manuell überprüfen können, ob das Gerät kompatibel ist und Sensordaten ordnungsgemäß meldet, finden Sie unter Problembehandlung bei [Onboardingproblemen](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)mit Microsoft Defender Advanced Threat Protection .

## <a name="offboard-devices-using-a-local-script"></a>Offboardgeräte mit einem lokalen Skript
Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.

1. Das Offboardingpaket aus dem [Microsoft Compliance Center erhalten](https://compliance.microsoft.com)

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Geräte offboarding aus.**

3. Wählen Sie **im Feld Bereitstellungsmethode** die Option **Lokales Skript aus.**

4. Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.

5. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den die Geräte zugreifen können. Sie sollten über eine Datei namens *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*

6.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:

7.  Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

8.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

![Fensteranfangsmenü, das auf Als Administrator ausführen zeigt](../media/dlp-run-as-admin.png)

9.  Geben Sie den Speicherort der Skriptdatei ein. Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie ein: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

10.  Drücken Sie die **EINGABETASTE,** oder klicken Sie auf **OK**.

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät sensordaten nicht mehr an das Portal sendet.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration
Sie können die verschiedenen Überprüfungsschritte in der [Problembehandlung von Onboardingproblemen](( ausführen, um zu überprüfen, ob das Skript erfolgreich abgeschlossen wurde und https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) der Agent ausgeführt wird.

Die Überwachung kann auch direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools durchgeführt werden.

### <a name="monitor-devices-using-the-portal"></a>Überwachen von Geräten mithilfe des Portals
1. Wechseln Sie zu [Microsoft 365 Compliance Center](https://compliance.microsoft.com).

2. Wählen **Sie Einstellungen** Geräte  >  **onboarding** Geräte  >  **aus.**

3. Stellen Sie sicher, dass Geräte angezeigt werden.


## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Onboarding von Windows 10-Geräten mithilfe von Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](dlp-configure-endpoints-mdm.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](dlp-configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender ATP-Gerät](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Behandeln von Problemen mit dem Microsoft Defender Advanced Threat Protection-Onboarding](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)