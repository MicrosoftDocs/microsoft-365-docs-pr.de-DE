---
title: Onboarding von Windows 10-Geräten über Gruppenrichtlinie
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Verwenden Sie Gruppenrichtlinien, um das Konfigurationspaket auf Windows 10 bereitstellen, sodass sie in den Dienst onboardiert werden.
ms.openlocfilehash: 284de5169324b6da4038cfe0b50b2f2ffa40e3fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893286"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Onboarding Windows 10 Geräte mithilfe von Gruppenrichtlinien 

**Gilt für:**

- [Microsoft 365 Verhinderung von Endpunktdatenverlusten (Endpoint Data Loss Prevention, DLP)](./endpoint-dlp-learn-about.md)
- Gruppenrichtlinien

> [!NOTE]
> Zum Verwenden von Gruppenrichtlinienupdates zum Bereitstellen des Pakets müssen Sie sich auf Windows Server 2008 R2 oder höher befinden.

> Für Windows Server 2019 müssen Sie möglicherweise NT AUTHORITY\Well-Known-System-Account durch NT AUTHORITY\SYSTEM der VON der Gruppenrichtlinieneinstellung erstellten XML-Datei ersetzen.

## <a name="onboard-devices-using-group-policy"></a>Onboarding von Geräten mithilfe von Gruppenrichtlinien

1. Öffnen Sie die Gp.zip datei (*DeviceComplianceOnboardingPackage.zip*), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben. Sie können das Paket auch über das [Microsoft Compliance Center erhalten.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. Wählen Sie im Navigationsbereich die **option Einstellungen**  >  **Device Onboarding aus.**

3. Wählen Sie **im Feld Bereitstellungsmethode** die Option **Gruppenrichtlinie aus.**

4. Klicken **Sie auf Paket** herunterladen, und speichern .zip Datei.

5. Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann. Sie sollten über einen Ordner *namens OptionalParamsPolicy* und die Datei *DeviceComplianceLocalOnboardingScript.cmd verfügen.*

6. Öffnen Sie die Gruppenrichtlinienverwaltungskonsole (Group [Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt(GPO), das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

7. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** dann Einstellungen und dann **Systemsteuerungseinstellungen**. 

8. Klicken Sie mit der rechten Maustaste auf Geplante **Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **Sofortaufgabe (mindestens Windows 7).**

9. Wechseln Sie **im** geöffneten Aufgabenfenster zur Registerkarte **Allgemein.** Klicken **Sie unter Sicherheitsoptionen** **auf Benutzer oder Gruppe ändern,** und geben Sie SYSTEM ein, und klicken Sie dann **auf Namen überprüfen** und dann **OK**. NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.

10. Aktivieren **Sie Ausführen, ob der Benutzer** angemeldet ist oder nicht, und aktivieren Sie das Kontrollkästchen Mit höchsten **Rechten** ausführen.

11. Wechseln Sie zur **Registerkarte Aktionen,** und klicken Sie auf **Neu...** Stellen Sie **sicher, dass Programm starten** im Feld **Aktion ausgewählt** ist. Geben Sie den Dateinamen und speicherort der freigegebenen *Datei WindowsDefenderATPOnboardingScript.cmd* ein.

12. Klicken Sie **auf OK,** und schließen Sie alle geöffneten GPMC-Fenster.


## <a name="offboard-devices-using-group-policy"></a>Offboardgeräte mithilfe von Gruppenrichtlinien
Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.

1. Holen Sie sich das offboarding-Paket aus [dem Microsoft Compliance Center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).

2. Wählen Sie im Navigationsbereich **die option Einstellungen**  >  **/Device onboarding**  >  **Offboarding aus.**

3. Wählen Sie **im Feld Bereitstellungsmethode** die Option **Gruppenrichtlinie aus.**

4. Klicken **Sie auf Paket** herunterladen, und speichern .zip Datei.

5. Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann. Sie sollten über eine Datei namens *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*

6. Öffnen Sie die Gruppenrichtlinienverwaltungskonsole (Group [Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt(GPO), das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

7. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** dann Einstellungen und dann **Systemsteuerungseinstellungen**. 

8. Klicken Sie mit der rechten Maustaste auf Geplante **Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **Sofortaufgabe**.

9. Wechseln Sie **im** geöffneten Aufgabenfenster zur Registerkarte **Allgemein.** Wählen Sie unter Sicherheitsoptionen das lokale SYSTEM-Benutzerkonto (BUILTIN\SYSTEM) **aus.**

10. Aktivieren **Sie Ausführen, ob der** Benutzer angemeldet ist oder nicht, und aktivieren Sie das Kontrollkästchen **Ausführen** mit den höchsten Rechten.

11. Wechseln Sie zur **Registerkarte Aktionen,** und klicken Sie **auf Neu...**. Stellen Sie **sicher, dass Programm starten** im Feld **Aktion ausgewählt** ist. Geben Sie den Dateinamen und den Speicherort der freigegebenen  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd-Datei* ein.

12. Klicken Sie **auf OK,** und schließen Sie alle geöffneten GPMC-Fenster.

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät nicht mehr Sensordaten an das Portal sendet, sondern Daten vom Gerät.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration
Mit Gruppenrichtlinien gibt es keine Option zum Überwachen der Bereitstellung von Richtlinien auf den Geräten. Die Überwachung kann direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools durchgeführt werden.

## <a name="monitor-devices-using-the-portal"></a>Überwachen von Geräten mithilfe des Portals
1. Wechseln Sie zu [Microsoft Compliance Center](https://compliance.microsoft.com/).
2. Klicken Sie **auf Geräteliste.**
3. Stellen Sie sicher, dass Geräte angezeigt werden.

> [!NOTE]
> Es kann mehrere Tage dauern, bis Geräte in der Geräteliste **angezeigt werden.** Dies umfasst die Zeit, die für die Verteilung der Richtlinien auf das Gerät benötigt wird, die Zeit, die der Benutzer benötigt, bevor sich der Benutzer anmeldet, und die Zeit, die der Endpunkt benötigt, um mit der Berichterstellung zu beginnen.


## <a name="related-topics"></a>Verwandte Themen
- [Onboarding Windows 10 Geräte mithilfe Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](dlp-configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](dlp-configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Problembehandlung bei Microsoft Defender Advanced Threat Protection Onboardingproblemen](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)