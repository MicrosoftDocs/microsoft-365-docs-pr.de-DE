---
title: Onboarding von Windows 10 Geräten in Microsoft Defender für Endpunkt über Gruppenrichtlinien
description: Verwenden Sie gruppenrichtlinien, um das Konfigurationspaket auf Windows 10 Geräten bereitzustellen, damit sie in den Dienst integriert sind.
keywords: Konfigurieren von Geräten mithilfe von Gruppenrichtlinien, Geräteverwaltung, Konfigurieren von Microsoft Defender für Endpunktgeräte, Onboarding von Microsoft Defender für Endpunktgeräte, Gruppenrichtlinie
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
ms.openlocfilehash: b4418cca035710c6b938dad31a2b55423d2ab458
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314404"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- Gruppenrichtlinien
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)

> [!NOTE]
> Um Gruppenrichtlinienupdates zum Bereitstellen des Pakets zu verwenden, müssen Sie sich auf Windows Server 2008 R2 oder höher befinden.
>
> Für Windows Server 2019 müssen Sie möglicherweise NT AUTHORITY\Well-Known-System-Account durch NT AUTHORITY\SYSTEM der XML-Datei ersetzen, die von der Gruppenrichtlinieneinstellung erstellt wird.

## <a name="onboard-devices-using-group-policy"></a>Onboarding von Geräten mithilfe von Gruppenrichtlinien

[![Abbildung der PDF-Datei mit den verschiedenen Bereitstellungspfaden](images/onboard-gp.png)](images/onboard-gp.png#lightbox)

Sehen Sie sich die [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) oder [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Defender für Endpunkt anzuzeigen.

1. Öffnen Sie das GP-Konfigurationspaket .zip Datei (*WindowsDefenderATPOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben. Sie können das Paket auch von [Microsoft Defender Security Center](https://securitycenter.windows.com/)abrufen:

    1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding** aus.

    1. Wählen Sie Windows 10 als Betriebssystem aus.

    1. Wählen Sie im Feld **"Bereitstellungsmethode"** **die Gruppenrichtlinie** aus.

    1. Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.

2. Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann. Sie sollten über einen Ordner namens *"OptionalParamsPolicy"* und die Datei *"WindowsDefenderATPOnboardingScript.cmd" verfügen.*

3. Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt (Group Policy Object, GPO), das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

4. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **"Computerkonfiguration",** **"Einstellungen"** und dann **"Systemsteuerungseinstellungen".**

5. Klicken Sie mit der rechten Maustaste auf **geplante Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **"Sofortvorgang" (mindestens Windows 7).**

6. Wechseln Sie im geöffneten **Aufgabenfenster** zur Registerkarte **"Allgemein".** Klicken Sie unter **"Sicherheitsoptionen"** auf **"Benutzer oder Gruppe ändern",** und geben Sie "SYSTEM" ein, und klicken Sie dann auf **"Namen überprüfen",** und klicken Sie dann auf **"OK".** NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.

7. Wählen Sie **"Ausführen" aus, ob der Benutzer angemeldet ist oder nicht,** und aktivieren Sie das Kontrollkästchen **"Ausführen mit höchsten Berechtigungen".**

8. Wechseln Sie zur Registerkarte **"Aktionen",** und klicken Sie auf **"Neu"...** Stellen Sie sicher, dass **"Programm starten"** im Feld **"Aktion"** ausgewählt ist. Geben Sie den Dateinamen und speicherort der freigegebenen *Datei "WindowsDefenderATPOnboardingScript.cmd"* ein.

9. Klicken Sie auf **"OK",** und schließen Sie alle geöffneten GPMC-Fenster.

> [!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob das Gerät ordnungsgemäß in den Dienst integriert ist. Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender für Endpunkt-Gerät.](run-detection-test.md)

## <a name="additional-defender-for-endpoint-configuration-settings"></a>Zusätzliche Konfigurationseinstellungen für Defender für Endpunkt
Für jedes Gerät können Sie angeben, ob Beispiele vom Gerät erfasst werden können, wenn eine Anforderung über Microsoft Defender Security Center gestellt wird, um eine Datei für eine umfassende Analyse zu übermitteln.

Sie können Gruppenrichtlinien (GP) verwenden, um Einstellungen zu konfigurieren, z. B. Einstellungen für die Beispielfreigabe, die im Feature für die umfassende Analyse verwendet wird.

### <a name="configure-sample-collection-settings"></a>Konfigurieren von Beispielsammlungseinstellungen

1. Kopieren Sie auf Ihrem GP-Verwaltungsgerät die folgenden Dateien aus dem Konfigurationspaket:

    - Kopieren von _"AtpConfiguration.admx"_ in _"C: \\ Windows \\ PolicyDefinitions"_

    - Kopieren von _"AtpConfiguration.adml"_ in _"C: \\ Windows \\ PolicyDefinitions \\ en-US"_

    Wenn Sie eine [zentrale Store für administrative Gruppenrichtlinienvorlagen](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)verwenden, kopieren Sie die folgenden Dateien aus dem Konfigurationspaket:

    - Kopieren von _"AtpConfiguration.admx"_ in _\\ \\ \<forest.root\> \\ "SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions"_

    - Kopieren von _"AtpConfiguration.adml"_ in _\\ \\ \<forest.root\> \\ "SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions \\ en-US"_

2. Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)klicken Sie mit der rechten Maustaste auf das gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

3. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

4. Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**

5. Klicken Sie auf **Windows Komponenten,** und **Windows Defender Sie SmartScreen.**

6. Wählen Sie aus, ob Sie die Beispielfreigabe auf Ihren Geräten aktivieren oder deaktivieren möchten.

> [!NOTE]
> Wenn Sie keinen Wert festlegen, wird standardmäßig die Beispielsammlung aktiviert.

## <a name="other-recommended-configuration-settings"></a>Andere empfohlene Konfigurationseinstellungen

### <a name="update-endpoint-protection-configuration"></a>Aktualisieren der Endpunktschutzkonfiguration

Fahren Sie nach dem Konfigurieren des Onboardingskripts mit der Bearbeitung derselben Gruppenrichtlinie fort, um Endpunktschutzkonfigurationen hinzuzufügen. Durchführen von Gruppenrichtlinienbearbeitungen von einem System, auf dem Windows 10 oder Server 2019 ausgeführt wird, um sicherzustellen, dass Sie über alle erforderlichen Microsoft Defender Antivirus Funktionen verfügen. Möglicherweise müssen Sie das Gruppenrichtlinienobjekt schließen und erneut öffnen, um die Defender ATP-Konfigurationseinstellungen zu registrieren.

Alle Richtlinien befinden sich unter `Computer Configuration\Policies\Administrative Templates` .

**Richtlinienspeicherort:** \Windows-Komponenten\Windows Defender ATP

Richtlinie | Setting
:---|:---
Enable\Disable Sample collection| Aktiviert – "Beispielsammlung auf Computern aktivieren" aktiviert

<br>

**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus

Richtlinie | Setting
:---|:---
Konfigurieren der Erkennung für potenziell unerwünschte Anwendungen | Aktiviert, Blockieren

<br>

**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\MAPS

Richtlinie | Setting
:---|:---
Microsoft MAPS beitreten | Aktiviert, Erweiterte KARTEN
Senden von Dateibeispielen, wenn eine weitere Analyse erforderlich ist | Aktiviert, Sichere Beispiele senden

<br>

**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\Echtzeitschutz

Richtlinie | Setting
:---|:---
Deaktivieren des Echtzeitschutzes|Deaktiviert
Aktivieren der Verhaltensüberwachung|Aktiviert
Scannen aller heruntergeladenen Dateien und Anlagen|Aktiviert
Überwachen von Datei- und Programmaktivitäten auf Ihrem Computer|Aktiviert

<br>

**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\Scan

Diese Einstellungen konfigurieren regelmäßige Scans des Endpunkts. Es wird empfohlen, einen wöchentlichen Schnellscan durchzuführen, der die Leistung zulässt.

Richtlinie | Setting 
:---|:---
Überprüfen Sie die neuesten Informationen zur Viren- und Spywaresicherheit, bevor Sie einen geplanten Scan ausführen. |Aktiviert

<br>

**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction

Abrufen der aktuellen Liste der GUIDs zur Verringerung der Angriffsfläche aus der Anpassung der Regeln zur Verringerung der [Angriffsfläche](customize-attack-surface-reduction.md)

1. Öffnen Sie die **Richtlinie "Attack Surface Reduction konfigurieren".**

1. Wählen Sie **Aktiviert** aus.

1. Wählen Sie die Schaltfläche **"Anzeigen"** aus.

1. Fügen Sie jede GUID im **Feld Wertname** mit dem Wert 2 hinzu.

   Dadurch wird jede nur für die Überwachung eingerichtet.

   ![Abbildung der Attack Surface Reduction-Konfiguration](images/asr-guid.png)

Richtlinie | Setting
:---|:---
Konfigurieren des kontrollierten Ordnerzugriffs| Aktiviert, Überwachungsmodus

## <a name="offboard-devices-using-group-policy"></a>Offboarding von Geräten mithilfe von Gruppenrichtlinien

Aus Sicherheitsgründen läuft das Paket, das für Offboard-Geräte verwendet wird, 30 Tage nach dem Datum ab, an dem es heruntergeladen wurde. Abgelaufene Offboardingpakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines Offboardingpakets werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, andernfalls führt dies zu unvorhersehbaren Kollisionen.

1. Abrufen des Offboarding-Pakets aus [Microsoft Defender Security Center:](https://securitycenter.windows.com/)

    1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Offboarding** aus.

    1. Wählen Sie Windows 10 als Betriebssystem aus.

    1. Wählen Sie im Feld **"Bereitstellungsmethode"** **die Gruppenrichtlinie** aus.

    1. Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.

2. Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann. Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*

3. Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt (Group Policy Object, GPO), das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

4. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **"Computerkonfiguration",** **"Einstellungen"** und dann **"Systemsteuerungseinstellungen".**

5. Klicken Sie mit der rechten Maustaste auf **geplante Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **"Sofortvorgang".**

6. Wechseln Sie im geöffneten **Aufgabenfenster** zur Registerkarte **"Allgemein".** Wählen Sie das lokale SYSTEM-Benutzerkonto (BUILTIN\SYSTEM) unter **"Sicherheitsoptionen" aus.**

7. Wählen Sie **"Ausführen" aus, ob der Benutzer angemeldet ist oder nicht,** und aktivieren Sie das Kontrollkästchen **"Ausführen mit den höchsten Berechtigungen".**

8. Wechseln Sie zur Registerkarte **"Aktionen",** und klicken Sie auf **"Neu"...**. Stellen Sie sicher, dass **"Programm starten"** im Feld **"Aktion"** ausgewählt ist. Geben Sie den NetBIOS-Pfad der freigegebenen *Datei WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* ein.

9. Klicken Sie auf **"OK",** und schließen Sie alle geöffneten GPMC-Fenster.

> [!IMPORTANT]
> Das Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweise auf warnungen, die es gesendet hat, werden bis zu 6 Monate lang aufbewahrt.

## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration

Bei Gruppenrichtlinien gibt es keine Option zum Überwachen der Bereitstellung von Richtlinien auf den Geräten. Die Überwachung kann direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools erfolgen.

## <a name="monitor-devices-using-the-portal"></a>Überwachen von Geräten mithilfe des Portals

1. Wechseln Sie zu [Microsoft Defender Security Center](https://securitycenter.windows.com/).
2. Klicken Sie auf **"Geräteliste".**
3. Stellen Sie sicher, dass Geräte angezeigt werden.

> [!NOTE]
> Es kann mehrere Tage dauern, bis Geräte in der Geräteliste angezeigt **werden.** Dies umfasst die Zeit, die es dauert, bis die Richtlinien auf das Gerät verteilt werden, die Zeit, bis sich der Benutzer anmeldet, und die Zeit, die der Endpunkt benötigt, um mit der Berichterstellung zu beginnen.

## <a name="related-topics"></a>Verwandte Themen

- [Onboarding von Windows 10 Geräten mithilfe von Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](configure-endpoints-script.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunktgeräte](run-detection-test.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten](troubleshoot-onboarding.md)
