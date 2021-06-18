---
title: Microsoft Defender Antivirus in der Windows-Sicherheit-App
description: Da Microsoft Defender Antivirus jetzt in der Windows-Sicherheit-App enthalten sind, können Sie allgemeine Aufgaben überprüfen, vergleichen und ausführen.
keywords: Wdav, Antivirus, Firewall, Sicherheit, Fenster
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: c15e68a74c9bf518822fce211d6c7d5c4dbc3f2c
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007446"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Microsoft Defender Antivirus in der Windows-Sicherheit-App

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In Windows 10, Version 1703 und höher, ist die Windows Defender-App Teil des Windows-Sicherheit.

Einstellungen, die zuvor Teil des Windows Defender-Clients und haupt-Windows Einstellungen waren, wurden kombiniert und in die neue App verschoben, die standardmäßig als Teil von Windows 10, Version 1703, installiert ist.

> [!IMPORTANT]
> Durch das Deaktivieren des Windows-Sicherheit Center-Diensts wird Microsoft Defender Antivirus oder [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)nicht deaktiviert. Diese werden automatisch deaktiviert, wenn ein Antiviren- oder Firewallprodukt eines Drittanbieters installiert und auf dem neuesten Stand gehalten wird.
>
> Wenn Sie den Windows-Sicherheit Center-Dienst deaktivieren oder die zugehörigen Gruppenrichtlinieneinstellungen konfigurieren, um zu verhindern, dass er gestartet oder ausgeführt wird, zeigt die Windows-Sicherheit App möglicherweise veraltete oder ungenaue Informationen zu antiviren- oder Firewallprodukten an, die Sie auf dem Gerät installiert haben.
> Es kann auch verhindern, dass Microsoft Defender Antivirus sich selbst aktivieren, wenn Sie über ein altes oder veraltetes Antivirenprogramm eines Drittanbieters verfügen oder wenn Sie Antivirenprodukte von Drittanbietern deinstallieren, die Sie möglicherweise zuvor installiert haben.
> Dies verringert den Schutz Ihres Geräts erheblich und kann zu einer Infektion mit Schadsoftware führen.

Weitere Informationen zu anderen Windows Sicherheitsfeatures, die in der App überwacht werden können, finden Sie im [artikel](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) Windows-Sicherheit.

Die Windows-Sicherheit-App ist eine Clientschnittstelle auf Windows 10, Version 1703 und höher. Es ist nicht das Microsoft Defender Security Center Webportal, das zum Überprüfen und Verwalten von [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)verwendet wird.

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Überprüfen der Viren- und Bedrohungsschutzeinstellungen in der Windows-Sicherheit-App

:::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Viren- und Bedrohungsschutzeinstellungen in Windows-Sicherheit App":::

1. Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder das Startmenü nach **Defender** durchsuchen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.
   
In den folgenden Abschnitten wird beschrieben, wie Sie einige der gängigsten Aufgaben beim Überprüfen oder Interagieren mit dem Bedrohungsschutz ausführen, der von Microsoft Defender Antivirus in der Windows-Sicherheit-App bereitgestellt wird.

> [!NOTE]
> Wenn diese Einstellungen mithilfe von Gruppenrichtlinien konfiguriert und bereitgestellt werden, sind die in diesem Abschnitt beschriebenen Einstellungen abgeblendet und für die Verwendung auf einzelnen Endpunkten nicht verfügbar. Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen wurden, müssen zunächst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird. Im Thema "Konfigurieren der [Endbenutzerinteraktion mit Microsoft Defender Antivirus"](configure-end-user-interaction-microsoft-defender-antivirus.md) wird beschrieben, wie Einstellungen für die Außerkraftsetzung lokaler Richtlinien konfiguriert werden können.

## <a name="run-a-scan-with-the-windows-security-app"></a>Ausführen einer Überprüfung mit der Windows-Sicherheit-App

1. Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach **Sicherheit** suchen und dann **Windows-Sicherheit** auswählen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen Sie **"Schnellscan"** aus. Oder wählen Sie zum Ausführen eines vollständigen Scans **die Scanoptionen** aus, und wählen Sie dann eine Option aus, z. B. **vollständige Überprüfung.**

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>Überprüfen Sie die Version des Security Intelligence-Updates, und laden Sie die neuesten Updates in der Windows-Sicherheit-App herunter.

:::image type="content" source="../../media/wdav-wdsc-defs.png" alt-text="Versionsnummer der Security Intelligence":::

1. Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit** auswählen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen Sie **Viren- & Bedrohungsschutzupdates** aus. Die aktuell installierte Version wird zusammen mit einigen Informationen darüber angezeigt, wann sie heruntergeladen wurde. Sie können Ihre aktuelle Version mit der neuesten Version abgleichen, die für den manuellen Download verfügbar ist, oder das Änderungsprotokoll für diese Version überprüfen. Informationen [zu Microsoft Defender Antivirus und anderen Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates)von Microsoft finden Sie unter Security Intelligence-Updates.

4. Wählen Sie **"Nach Updates suchen"** aus, um neue Schutzupdates herunterzuladen (falls vorhanden).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Stellen Sie sicher, dass Microsoft Defender Antivirus in der Windows-Sicherheit-App aktiviert ist.

1. Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit** auswählen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen Sie **Einstellungen für den Viren- & Bedrohungsschutz** aus.

4. Umschalten des **Echtzeitschutzschalters** auf **"Ein".**

    > [!NOTE]
    > Wenn Sie den **Echtzeitschutz** deaktivieren, wird er nach kurzer Verzögerung automatisch wieder aktiviert. Dadurch wird sichergestellt, dass Sie vor Schadsoftware und Bedrohungen geschützt sind.
    > Wenn Sie ein anderes Antivirenprodukt installieren, deaktiviert Microsoft Defender Antivirus sich automatisch selbst und wird in der Windows-Sicherheit-App als solche gekennzeichnet. Es wird eine Einstellung angezeigt, mit der Sie [eingeschränkte regelmäßige Überprüfungen](limited-periodic-scanning-microsoft-defender-antivirus.md)aktivieren können.

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Hinzufügen von Ausschlüssen für Microsoft Defender Antivirus in der Windows-Sicherheit-App

1. Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit** auswählen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen Sie unter **"Einstellungen verwalten"** **die Einstellungen für den Viren- & Bedrohungsschutz** aus.

4. Wählen Sie unter der Einstellung **"Ausschlüsse"** die Option **"Ausschlüsse hinzufügen oder entfernen" aus.** 

5. Wählen Sie das Plussymbol ( **+** ) aus, um den Typ auszuwählen, und legen Sie die Optionen für jeden Ausschluss fest. 

In der folgenden Tabelle sind Ausschlusstypen zusammengefasst und was passiert:

|Ausschlusstyp  |Definiert durch  |Aktionen  |
|---------|---------|---------|
|**Datei** |Speicherort <br/>Beispiel: `c:\sample\sample.test` |Die spezifische Datei wird von Microsoft Defender Antivirus übersprungen. |
|**Folder**    |Speicherort <br/>Beispiel: `c:\test\sample`       |Alle Elemente im angegebenen Ordner werden von Microsoft Defender Antivirus übersprungen.         |
|**Dateityp**   |Dateierweiterung <br/>Beispiel: `.test` |Alle Dateien mit der `.test` Erweiterung an beliebiger Stelle auf Ihrem Gerät werden von Microsoft Defender Antivirus übersprungen.         |
|**Prozess**     |Pfad der ausführbaren Datei <br>Beispiel: `c:\test\process.exe`         |Der spezifische Prozess und alle Dateien, die von diesem Prozess geöffnet werden, werden von Microsoft Defender Antivirus übersprungen.         |

Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:
- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf der Dateierweiterung und dem Speicherort des Ordners](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [Konfigurieren von Ausschlüssen für Dateien, die von Prozessen geöffnet werden](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>Überprüfen des Verlaufs der Bedrohungserkennung in der Windows Defender Security Center-App

1. Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit** auswählen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen Sie **"Schutzverlauf" aus.** Alle zuletzt verwendeten Elemente werden aufgelistet.

## <a name="set-ransomware-protection-and-recovery-options"></a>Festlegen von Ransomware-Schutz- und Wiederherstellungsoptionen

1. Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit** auswählen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.

3. Wählen Sie unter **Ransomware-Schutz** Den **Ransomware-Schutz verwalten** aus.

4. Informationen zum Ändern der Einstellungen für den **kontrollierten Ordnerzugriff** finden Sie unter ["Schützen wichtiger Ordner mit kontrollierten Ordnerzugriff".](/microsoft-365/security/defender-endpoint/controlled-folders)

5. Um Ransomware-Wiederherstellungsoptionen einzurichten, wählen Sie unter **Ransomware-Datenwiederherstellung** **einrichten** aus, und folgen Sie den Anweisungen zum Verknüpfen oder Einrichten Ihres OneDrive Kontos, damit Sie sich leicht von einem Ransomware-Angriff wiederherstellen können.

## <a name="see-also"></a>Siehe auch
- [Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md)