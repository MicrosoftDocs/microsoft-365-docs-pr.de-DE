---
title: Microsoft Defender Antivirus in der Windows-Sicherheit App
description: Mit Microsoft Defender Antivirus, die jetzt in der Windows-Sicherheit-App enthalten sind, können Sie allgemeine Aufgaben überprüfen, vergleichen und ausführen.
keywords: wdav, antivirus, firewall, security, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ccb0d4cf168bbb4d3c1575c1e6611829909d0817
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275408"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Microsoft Defender Antivirus in der Windows-Sicherheit App

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In Windows 10 Version 1703 und höher ist die Windows Defender-App Teil der Windows-Sicherheit.

Einstellungen, die zuvor Teil des Windows Defender- und Hauptclients Windows Einstellungen waren, wurden kombiniert und in die neue App verschoben, die standardmäßig als Teil von Windows 10, Version 1703, installiert ist.

> [!IMPORTANT]
> Das Deaktivieren des Windows-Sicherheit Center-Diensts deaktiviert nicht Microsoft Defender Antivirus oder [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security). Diese werden automatisch deaktiviert, wenn ein Antiviren- oder Firewallprodukt eines Drittanbieters installiert und auf dem neuesten Stand gehalten wird.
>
> Wenn Sie den Windows-Sicherheit Center-Dienst deaktivieren oder die zugehörigen Gruppenrichtlinieneinstellungen so konfigurieren, dass er nicht gestartet oder ausgeführt wird, zeigt die Windows-Sicherheit-App möglicherweise veraltete oder ungenaue Informationen zu Antiviren- oder Firewallprodukten an, die Sie auf dem Gerät installiert haben.
> Es kann auch verhindern, Microsoft Defender Antivirus, sich selbst zu aktivieren, wenn Sie über einen alten oder veralteten Antivirenprogramm eines Drittanbieters verfügen oder wenn Sie Antivirenprodukte von Drittanbietern deinstallieren, die Sie möglicherweise zuvor installiert haben.
> Dies verringert den Schutz Ihres Geräts erheblich und kann zu einer Schadsoftwareinfektion führen.

Weitere Informationen zu Windows-Sicherheit Sicherheitsfeatures, die in der App überwacht werden können Windows finden Sie im Artikel Windows-Sicherheit. [](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center)

Die Windows-Sicherheit-App ist eine Clientschnittstelle auf Windows 10 Version 1703 und höher. Es ist nicht das Microsoft Defender Security Center, das zum Überprüfen und Verwalten von [Microsoft Defender for Endpoint verwendet wird.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Überprüfen der Viren- und Bedrohungsschutzeinstellungen in Windows-Sicherheit App

![Screenshot der Bezeichnung für die Einstellungen des Viren- und Bedrohungsschutzes in der Windows-Sicherheit-App](images/defender/wdav-protection-settings-wdsc.png)

1. Öffnen Sie Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Defender suchen.**

2. Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.
   
In den folgenden Abschnitten wird beschrieben, wie Sie einige der am häufigsten verwendeten Aufgaben beim Überprüfen oder Interagieren mit dem bedrohungsschutz ausführen, der von Microsoft Defender Antivirus in der Windows-Sicherheit bereitgestellt wird.

> [!NOTE]
> Wenn diese Einstellungen mithilfe von Gruppenrichtlinien konfiguriert und bereitgestellt werden, sind die in diesem Abschnitt beschriebenen Einstellungen ausgegraut und für die Verwendung auf einzelnen Endpunkten nicht verfügbar. Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen wurden, müssen zunächst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird. Im [Thema Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) wird beschrieben, wie Lokale Richtlinienüberschreibungseinstellungen konfiguriert werden können.

## <a name="run-a-scan-with-the-windows-security-app"></a>Ausführen einer Überprüfung mit der Windows-Sicherheit App

1. Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach **Sicherheit** suchen und dann **Windows-Sicherheit.**

2. Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen Sie **Schnellscan aus.** Wenn Sie einen vollständigen Scan ausführen möchten, wählen Sie **Scanoptionen** aus, und wählen Sie dann eine Option aus, z. B. **Vollständige Überprüfung.**

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>Überprüfen Sie die Version des Security Intelligence-Updates, und laden Sie die neuesten Updates in der Windows-Sicherheit herunter

![Informationen zur Versionsnummer der Sicherheitsintelligenz](images/defender/wdav-wdsc-defs.png)

1. Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit.**

2. Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen **Sie Virenschutzupdates & Bedrohungsschutz aus.** Die aktuell installierte Version wird zusammen mit einigen Informationen zum Download angezeigt. Sie können Ihre aktuelle Version mit der neuesten Version überprüfen, die für den manuellen Download verfügbar ist, oder das Änderungsprotokoll für diese Version überprüfen. Weitere Informationen finden Sie unter Security [Intelligence updates for Microsoft Defender Antivirus and other Microsoft anmalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).

4. Wählen **Sie Nach Updates suchen aus,** um neue Schutzupdates herunterzuladen (sofern verfügbar).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Sicherstellen, Microsoft Defender Antivirus in der app aktiviert Windows-Sicherheit ist

1. Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit.**

2. Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen **Sie Virenschutzeinstellungen & Bedrohungsschutz aus.**

4. Umschalten Sie **die Option Echtzeitschutz** auf **Ein**.

    > [!NOTE]
    > Wenn Sie den **Echtzeitschutz deaktivieren,** wird er nach kurzer Verzögerung automatisch wieder aktiviert. Dadurch wird sichergestellt, dass Sie vor Schadsoftware und Bedrohungen geschützt sind.
    > Wenn Sie ein anderes Antivirenprodukt installieren, Microsoft Defender Antivirus automatisch selbst deaktiviert und wird als solches in der Windows-Sicherheit angezeigt. Es wird eine Einstellung angezeigt, mit der Sie eine eingeschränkte regelmäßige [Überprüfung aktivieren können.](limited-periodic-scanning-microsoft-defender-antivirus.md)

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Hinzufügen von Ausschlüssen für Microsoft Defender Antivirus in der Windows-Sicherheit App

1. Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit.**

2. Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen Sie **unter Einstellungen verwalten** die Option **Virenschutz & Bedrohungsschutzeinstellungen aus.**

4. Wählen Sie unter der Einstellung **Ausschlüsse** die Option **Ausschlüsse hinzufügen oder entfernen aus.** 

5. Wählen Sie das Plussymbol ( **+** ) aus, um den Typ auszuwählen und die Optionen für jeden Ausschluss festlegen. 

In der folgenden Tabelle werden Ausschlusstypen und die folgenden Schritte zusammengefasst:

|Ausschlusstyp  |Definiert durch  |Aktionen  |
|---------|---------|---------|
|**Datei** |Speicherort <br/>Beispiel: `c:\sample\sample.test` |Die spezifische Datei wird von der Microsoft Defender Antivirus. |
|**Folder**    |Speicherort <br/>Beispiel: `c:\test\sample`       |Alle Elemente im angegebenen Ordner werden von der Microsoft Defender Antivirus.         |
|**Dateityp**   |Dateierweiterung <br/>Beispiel: `.test` |Alle Dateien mit der Erweiterung an einer beliebigen Stelle auf Ihrem Gerät werden `.test` von Microsoft Defender Antivirus.         |
|**Prozess**     |Pfad der ausführbaren Datei <br>Beispiel: `c:\test\process.exe`         |Der spezifische Prozess und alle Dateien, die von diesem Prozess geöffnet werden, werden von der Microsoft Defender Antivirus.         |

Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:
- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateierweiterung und Ordnerspeicherort](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [Konfigurieren von Ausschlüssen für Dateien, die von Prozessen geöffnet werden](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>Überprüfen des Verlaufs der Bedrohungserkennung in Windows Defender Security Center-App

1. Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit.**

2. Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen **Sie Schutzverlauf aus.** Alle zuletzt verwendeten Elemente werden aufgelistet.

## <a name="set-ransomware-protection-and-recovery-options"></a>Festlegen von Schutz- und Wiederherstellungsoptionen für Ransomware

1. Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit.**

2. Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen **Sie unter Ransomware-Schutz** die Option **Ransomware-Schutz verwalten aus.**

4. Informationen zum **Ändern der Einstellungen für den kontrollierten** Ordnerzugriff finden Sie unter Schützen wichtiger Ordner mit [kontrolliertem Ordnerzugriff.](/microsoft-365/security/defender-endpoint/controlled-folders)

5. Zum Einrichten von Ransomware-Wiederherstellungsoptionen wählen Sie Unter **Ransomware** Datenwiederherstellung einrichten aus, und folgen Sie den Anweisungen zum Verknüpfen oder Einrichten Ihres OneDrive-Kontos, damit Sie sich problemlos von einem Ransomware-Angriff wiederherstellen können. 

## <a name="see-also"></a>Siehe auch
- [Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md)