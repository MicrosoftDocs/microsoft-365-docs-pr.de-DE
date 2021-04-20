---
title: Onboarding von Windows 10-Geräten in Microsoft Defender for Endpoint über Gruppenrichtlinien
description: Verwenden Sie Gruppenrichtlinien, um das Konfigurationspaket auf Windows 10-Geräten so zu bereitstellen, dass sie in den Dienst onboardiert werden.
keywords: Konfigurieren von Geräten mithilfe von Gruppenrichtlinien, Geräteverwaltung, Konfigurieren von Windows ATP-Geräten, Onboarding von Microsoft Defender for Endpoint-Geräten, Gruppenrichtlinie
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b839cf204e8ab042e0c88a8f8c48df79770e7b4f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893634"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- Gruppenrichtlinien
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> Um Gruppenrichtlinienupdates (GP)-Updates zum Bereitstellen des Pakets zu verwenden, müssen Sie sich auf Windows Server 2008 R2 oder höher.
> 
> Für Windows Server 2019 müssen Sie möglicherweise NT AUTHORITY\Well-Known-System-Account durch NT AUTHORITY\SYSTEM der XML-Datei ersetzen, die von der Gruppenrichtlinieneinstellung erstellt wird.

## <a name="onboard-devices-using-group-policy"></a>Onboarding von Geräten mithilfe von Gruppenrichtlinien

[![Abbildung der PDF mit den verschiedenen Bereitstellungspfaden](images/onboard-gp.png)](images/onboard-gp.png#lightbox)

Sehen Sie sich [die PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  oder  [Visio-Datei](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Defender for Endpoint zu sehen. 



1. Öffnen Sie die ZIP-Datei des *GP-Konfigurationspakets*(WindowsDefenderATPOnboardingPackage.zip), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben. Sie können das Paket auch über [das Microsoft Defender Security Center erhalten:](https://securitycenter.windows.com/)
 
    1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding aus.**

    1. Wählen Sie Windows 10 als Betriebssystem aus.
    
    1. Wählen Sie **im Feld Bereitstellungsmethode** die Option **Gruppenrichtlinie aus.**
    
    1. Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.

2. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den das Gerät zugreifen kann. Sie sollten über einen Ordner *namens OptionalParamsPolicy* und die *Datei WindowsDefenderATPOnboardingScript.cmd verfügen.*

3. Öffnen Sie die Gruppenrichtlinienverwaltungskonsole (Group [Policy Management Console,](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt(GPO), das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

4. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** dann Einstellungen und dann **Systemsteuerungseinstellungen**. 

5. Klicken Sie mit der rechten Maustaste auf Geplante **Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **Sofortaufgabe (Mindestens Windows 7).**

6. Wechseln Sie **im** geöffneten Aufgabenfenster zur Registerkarte **Allgemein.** Klicken **Sie unter Sicherheitsoptionen** **auf Benutzer oder Gruppe ändern,** und geben Sie SYSTEM ein, und klicken Sie dann **auf Namen überprüfen** und dann **OK**. NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.

7. Aktivieren **Sie Ausführen, ob der Benutzer** angemeldet ist oder nicht, und aktivieren Sie das Kontrollkästchen Mit höchsten **Rechten** ausführen.

8. Wechseln Sie zur **Registerkarte Aktionen,** und klicken Sie auf **Neu...** Stellen Sie **sicher, dass Programm starten** im Feld **Aktion ausgewählt** ist. Geben Sie den Dateinamen und speicherort der freigegebenen *Datei WindowsDefenderATPOnboardingScript.cmd* ein.

9. Klicken Sie **auf OK,** und schließen Sie alle geöffneten GPMC-Fenster.

>[!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um sicherzustellen, dass das Gerät ordnungsgemäß in den Dienst integrierte ist. Weitere Informationen finden Sie unter Ausführen eines Erkennungstests auf einem neu integrierten [Defender for Endpoint-Gerät.](run-detection-test.md)

## <a name="additional-defender-for-endpoint-configuration-settings"></a>Zusätzliche Defender for Endpoint-Konfigurationseinstellungen
Für jedes Gerät können Sie bestimmen, ob Beispiele vom Gerät gesammelt werden können, wenn über das Microsoft Defender Security Center eine Anforderung zum Übermitteln einer Datei zur tiefen Analyse gestellt wird.

Sie können Gruppenrichtlinien (GP) verwenden, um Einstellungen zu konfigurieren, z. B. Einstellungen für die Beispielfreigabe, die im Feature für die tiefen Analysen verwendet wird.

### <a name="configure-sample-collection-settings"></a>Konfigurieren von Beispielsammlungseinstellungen
1.  Kopieren Sie auf Ihrem GP-Verwaltungsgerät die folgenden Dateien aus dem Konfigurationspaket:

    - Kopieren _von AtpConfiguration.admx_ in _C: Windows \\ \\ PolicyDefinitions_

    - Kopieren _von AtpConfiguration.adml_ in _C: Windows \\ \\ PolicyDefinitions \\ en-US_

    Wenn Sie einen zentralen Speicher für administrative [Gruppenrichtlinienvorlagen verwenden,](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)kopieren Sie die folgenden Dateien aus dem Konfigurationspaket:
    
    - Kopieren _von "AtpConfiguration.admx"_ in _\\ \\ \<forest.root\> \\ "SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions"_

    - Kopieren _von AtpConfiguration.adml_ in _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions \\ en-US_

2.  Öffnen Sie [die Gruppenrichtlinienverwaltungskonsole,](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

3.  Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

4.  Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

5.  Klicken **Sie auf Windows-Komponenten,** und Windows Defender **ATP**.

6.  Wählen Sie aus, ob Sie die Beispielfreigabe auf Ihren Geräten aktivieren oder deaktivieren möchten.

>[!NOTE]
> Wenn Sie keinen Wert festlegen, ist der Standardwert die Aktivierung der Beispielsammlung.


## <a name="other-recommended-configuration-settings"></a>Weitere empfohlene Konfigurationseinstellungen

### <a name="update-endpoint-protection-configuration"></a>Aktualisieren der Endpunktschutzkonfiguration

Nachdem Sie das Onboardingskript konfiguriert haben, bearbeiten Sie weiterhin dieselbe Gruppenrichtlinie, um Endpunktschutzkonfigurationen hinzuzufügen. Führen Sie Gruppenrichtlinienbearbeitungen von einem System mit Windows 10 oder Server 2019 aus, um sicherzustellen, dass Sie über alle erforderlichen Microsoft Defender Antivirus-Funktionen verfügen. Möglicherweise müssen Sie das Gruppenrichtlinienobjekt schließen und erneut öffnen, um die Defender ATP-Konfigurationseinstellungen zu registrieren.

Alle Richtlinien befinden sich unter `Computer Configuration\Policies\Administrative Templates` .

**Richtlinienspeicherort:** \Windows-Komponenten\Windows Defender ATP

Richtlinie | Setting 
:---|:---
Enable\Disable Sample collection|   Aktiviert – "Beispielsammlung auf Computern aktivieren" aktiviert

<br/>

**Richtlinienspeicherort:**  \Windows-Komponenten\Windows Defender Antivirus

Richtlinie | Setting 
:---|:---
Konfigurieren der Erkennung für potenziell unerwünschte Anwendungen | Aktiviert, Blockieren

<br/>

**Richtlinienspeicherort:** \Windows-Komponenten\Windows Defender Antivirus\MAPS

Richtlinie | Setting 
:---|:---
Microsoft MAPS beitreten | Aktiviert, Erweiterte KARTEN
Senden von Dateibeispielen, wenn eine weitere Analyse erforderlich ist | Aktiviert, Sichere Beispiele senden

<br/>

**Richtlinienspeicherort:** \Windows-Komponenten\Windows Defender Antivirus\Echtzeitschutz

Richtlinie | Setting 
:---|:---
Deaktivieren des Echtzeitschutzes|Deaktiviert
Aktivieren der Verhaltensüberwachung|Aktiviert
Überprüfen aller heruntergeladenen Dateien und Anlagen|Aktiviert
Überwachen von Datei- und Programmaktivitäten auf Ihrem Computer|Aktiviert

<br/>

**Richtlinienspeicherort:**  \Windows-Komponenten\Windows Defender Antivirus\Scan

Diese Einstellungen konfigurieren regelmäßige Überprüfungen des Endpunkts. Es wird empfohlen, eine wöchentliche Schnellscan durchführen, was die Leistung erlaubt.

Richtlinie | Setting 
:---|:---
Überprüfen Sie vor dem Ausführen einer geplanten Überprüfung auf die neuesten Viren- und Spywaresicherheitsinformationen. |Aktiviert


<br/>

**Richtlinienspeicherort:** \Windows-Komponenten\Windows Defender Antivirus\Windows Defender Exploit Guard\Attack Surface Reduction

Aktuelle Liste der GUIDs zur Reduzierung der Angriffsfläche aus Anpassen von Regeln zur Reduzierung der [Angriffsfläche](customize-attack-surface-reduction.md)

1. Öffnen Sie die **Richtlinie Attack Surface Reduction** konfigurieren.

1. Wählen Sie **Aktiviert** aus.

1. Wählen Sie die **Schaltfläche Anzeigen** aus.

1. Fügen Sie jede GUID im **Feld Wertname** mit dem Wert 2 hinzu.

   Dadurch werden alle nur für die Überwachung eingerichtet.

   ![Abbildung der Konfiguration der Angriffsfläche](images/asr-guid.png)



Richtlinie | Setting 
:---|:---
Konfigurieren des kontrollierten Ordnerzugriffs| Aktiviert, Überwachungsmodus



## <a name="offboard-devices-using-group-policy"></a>Offboardgeräte mithilfe von Gruppenrichtlinien
Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.

1. Das offboarding-Paket aus [dem Microsoft Defender Security Center erhalten:](https://securitycenter.windows.com/)

    1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Offboarding aus.**

    1. Wählen Sie Windows 10 als Betriebssystem aus.
    
    1. Wählen Sie **im Feld Bereitstellungsmethode** die Option **Gruppenrichtlinie aus.**

    1. Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.

2. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den das Gerät zugreifen kann. Sie sollten über eine Datei namens *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*

3. Öffnen Sie die Gruppenrichtlinienverwaltungskonsole (Group [Policy Management Console,](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt(GPO), das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

4. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** dann Einstellungen und dann **Systemsteuerungseinstellungen**. 

5. Klicken Sie mit der rechten Maustaste auf Geplante **Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **Sofortaufgabe**.

6. Wechseln Sie **im** geöffneten Aufgabenfenster zur Registerkarte **Allgemein.** Wählen Sie unter Sicherheitsoptionen das lokale SYSTEM-Benutzerkonto (BUILTIN\SYSTEM) **aus.**

7. Aktivieren **Sie Ausführen, ob der** Benutzer angemeldet ist oder nicht, und aktivieren Sie das Kontrollkästchen **Ausführen** mit den höchsten Rechten.

8. Wechseln Sie zur **Registerkarte Aktionen,** und klicken Sie **auf Neu...**. Stellen Sie **sicher, dass Programm starten** im Feld **Aktion ausgewählt** ist. Geben Sie den Dateinamen und den Speicherort der freigegebenen  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd-Datei* ein.

9. Klicken Sie **auf OK,** und schließen Sie alle geöffneten GPMC-Fenster.

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweis auf alle Warnungen, die es erhalten hat, werden für bis zu 6 Monate aufbewahrt.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration
Mit Gruppenrichtlinien gibt es keine Option zum Überwachen der Bereitstellung von Richtlinien auf den Geräten. Die Überwachung kann direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools durchgeführt werden.

## <a name="monitor-devices-using-the-portal"></a>Überwachen von Geräten mithilfe des Portals
1. Wechseln Sie zu [Microsoft Defender Security Center](https://securitycenter.windows.com/).
2. Klicken Sie **auf Geräteliste**.
3. Stellen Sie sicher, dass Geräte angezeigt werden.

> [!NOTE]
> Es kann mehrere Tage dauern, bis Geräte in der Geräteliste **angezeigt werden.** Dies umfasst die Zeit, die für die Verteilung der Richtlinien auf das Gerät benötigt wird, die Zeit, die der Benutzer benötigt, bevor sich der Benutzer anmeldet, und die Zeit, die der Endpunkt benötigt, um mit der Berichterstellung zu beginnen.


## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten mithilfe von Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](configure-endpoints-script.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät](run-detection-test.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint](troubleshoot-onboarding.md)
