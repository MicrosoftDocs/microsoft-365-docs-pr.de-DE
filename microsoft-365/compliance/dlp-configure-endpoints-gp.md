---
title: Onboard-Windows 10-Geräte über Gruppenrichtlinien
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
description: Verwenden Sie Gruppenrichtlinien, um das Konfigurationspaket auf Windows 10-Geräten bereitzustellen, damit Sie mit dem Dienst an Bord sind.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769415"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien 

**Gilt für:**

- [Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Gruppenrichtlinien

> [!NOTE]
> Damit Sie das Paket mithilfe von Gruppenrichtlinienupdates (GP) bereitstellen können, müssen Sie sich auf Windows Server 2008 R2 oder höher befinden.

> Für Windows Server 2019 müssen Sie möglicherweise NT-AUTHORITY\Well-known-System-Account durch NT-AUTHORITY\SYSTEM der XML-Datei ersetzen, die von der Gruppenrichtlinieneinstellung erstellt wird.

## <a name="onboard-devices-using-group-policy"></a>Integrierte Geräte mithilfe von Gruppenrichtlinien

1. Öffnen Sie die ZIP-Datei des GP-Konfigurationspakets ( *DeviceComplianceOnboardingPackage.zip* ), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben. Sie können das Paket auch über das [Microsoft Compliance Center](https://compliance.microsoft.com/compliancesettings/deviceonboarding) abrufen.

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Gerät Onboarding** aus.

3. Wählen Sie im Feld **Bereitstellungsmethode** die Option **Gruppenrichtlinie** aus.

4. Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.

5. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann. Sie sollten über einen Ordner namens " *OptionalParamsPolicy* " und die Datei " *DeviceComplianceLocalOnboardingScript. cmd* " verfügen.

6. Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) , GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten** .

7. Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computer Konfiguration** , **Einstellungen und** dann in **System** Steuerung.

8. Klicken Sie mit der rechten Maustaste auf **geplante Vorgänge** , dann auf **neu** , und klicken Sie dann auf **sofortige Aufgabe (mindestens Windows 7)** .

9. Wechseln Sie im **Aufgaben** Fenster, das geöffnet wird, zur Registerkarte **Allgemein** . Klicken Sie unter **Sicherheitsoptionen** auf **Benutzer oder Gruppe ändern** , und geben Sie System ein, und klicken Sie dann auf **Namen überprüfen** und dann auf **OK** . NT-AUTHORITY\SYSTEM wird als das Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.

10. Wählen Sie **ausführen, ob Benutzer angemeldet ist oder nicht** , und aktivieren Sie das Kontrollkästchen **mit den höchsten Rechten ausführen** .

11. Wechseln Sie zur Registerkarte **Aktionen** , und klicken Sie auf **neu...** Stellen Sie sicher, dass im Feld **Aktion** die Option **Programm starten** ausgewählt ist. Geben Sie den Dateinamen und den Speicherort der freigegebenen Datei *WindowsDefenderATPOnboardingScript. cmd* ein.

12. Klicken Sie auf **OK** , und schließen Sie alle geöffneten GPMC-Fenster.


## <a name="offboard-devices-using-group-policy"></a>Extern-Geräte mithilfe von Gruppenrichtlinien
Aus Sicherheitsgründen läuft das Paket, das für extern-Geräte verwendet wird, 30 Tage nach dem heruntergeladenen Datum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden zurückgewiesen. Wenn Sie ein offboarding-Paket herunterladen, werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen eingeschlossen.

> [!NOTE]
> Onboarding-und offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da dies andernfalls zu unvorhersehbaren Konflikten führen kann.

1. Rufen Sie das offboarding-Paket im [Microsoft Compliance Center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)ab.

2. Wählen Sie im Navigationsbereich die Option **Einstellungen**  >  **//Device Onboarding**  >  **Offboarding** .

3. Wählen Sie im Feld **Bereitstellungsmethode** die Option **Gruppenrichtlinie** aus.

4. Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.

5. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann. Sie sollten über eine Datei mit dem Namen *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* verfügen.

6. Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) , GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten** .

7. Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computer Konfiguration,** **Einstellungen und** dann in **System** Steuerung.

8. Klicken Sie mit der rechten Maustaste auf **geplante Vorgänge** , dann auf **neu** , und klicken Sie dann auf **sofortige Aufgabe** .

9. Wechseln Sie im **Aufgaben** Fenster, das geöffnet wird, zur Registerkarte **Allgemein** . Wählen Sie das lokale System Benutzerkonto (BUILTIN\SYSTEM) unter **Sicherheitsoptionen** aus.

10. Wählen Sie **ausführen, ob der Benutzer angemeldet ist oder nicht** , und aktivieren Sie das Kontrollkästchen **mit den höchsten Rechten ausführen** .

11. Wechseln Sie zur Registerkarte **Aktionen** , und klicken Sie auf **neu...** . Stellen Sie sicher, dass im Feld **Aktion** die Option **Programm starten** ausgewählt ist. Geben Sie den Dateinamen und den Speicherort der freigegebenen  *DeviceComplianceOffboardingScript_valid_until_YYYY Datei-mm-dd. cmd* ein.

12. Klicken Sie auf **OK** , und schließen Sie alle geöffneten GPMC-Fenster.

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät keine Sensordaten mehr an das Portal sendet, sondern Daten vom Gerät.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration
Mit Gruppenrichtlinien gibt es keine Option zum Überwachen der Bereitstellung von Richtlinien auf den Geräten. Die Überwachung kann direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools erfolgen.

## <a name="monitor-devices-using-the-portal"></a>Überwachen von Geräten mithilfe des Portals
1. Wechseln Sie zum [Microsoft Compliance Center](https://compliance.microsoft.com/).
2. Klicken Sie auf **Geräte** Liste.
3. Stellen Sie sicher, dass die Geräte angezeigt werden.

> [!NOTE]
> Es kann mehrere Tage dauern, bis Geräte in der **Liste Geräte** gestartet werden. Dies umfasst die Zeit, die für die Verteilung der Richtlinien auf das Gerät benötigt wird, die Zeit bis zum Anmelden des Benutzers und die Zeit, die für den Endpunkt zum Starten der Berichterstellung benötigt wird.


## <a name="related-topics"></a>Verwandte Themen
- [Onboard-Windows 10-Geräte mit Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte](dlp-configure-endpoints-mdm.md)
- [Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md)
- [Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)](dlp-configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender-ATP-Gerät](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
