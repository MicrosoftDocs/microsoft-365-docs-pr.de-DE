---
title: Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Administratoren können die Unterstützung für die Sensitivitäts Bezeichnung für Word-, Excel-und PowerPoint-Dateien in SharePoint und OneDrive aktivieren.
ms.openlocfilehash: c050aefb9feebbb3ff37a8504ba1b8385fb0ff49
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "38686186"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>Aktivieren von Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)

Wenn Sie zuvor Sensitivitäts Bezeichnungen angewendet haben, die die Verschlüsselung in Office-Dateien in SharePoint und OneDrive gespeichert haben, konnte der Dienst den Inhalt dieser Dateien nicht verarbeiten. Die gemeinsame Dokumenterstellung, eDiscovery, Verhinderung von Datenverlust, Suche, vertiefen und anderen kollaborativen Features funktionierte unter diesen Umständen nicht. In dieser Vorschau werden diese Funktionen aktiviert:

- SharePoint erkennt Vertraulichkeits Bezeichnungen, die auf Word-, Excel-und PowerPoint-Dateien in SharePoint und OneDrive angewendet werden. SharePoint erzwingt auch die Einstellungen, die mit den einzelnen Bezeichnungen übereinstimmen.

- Wenn Sie eine Datei aus SharePoint oder OneDrive herunterladen, wird die Vertraulichkeits Bezeichnung mit der Datei durchgesetzt, und die Einstellungen bleiben erhalten.

- Wenden Sie Sensitivitäts Bezeichnungen auf Office-Dateien an, und öffnen und bearbeiten Sie Dateien, auf die die Vertraulichkeits Bezeichnungen angewendet werden (sofern die Berechtigungen der Bezeichnung dies zulassen), indem Sie die Webversionen von Word, Excel und PowerPoint verwenden. Bei Word im Internet können Sie beim Bearbeiten von Dokumenten auch die automatische Beschriftung verwenden.

- Office 365 eDiscovery unterstützt die Volltextsuche in Dateien, auf die Sensitivitäts Bezeichnungen angewendet wurden. DLP-Richtlinien (Data Loss Prevention) decken Inhalte in diesen Dateien ab.

- Für die Überwachung von Sensitivitäts Bezeichnungen stehen drei neue Überwachungsereignisse zur Verfügung:
  - FileSensitivityApplied
  - FileSensitivityLabelChanged
  - FileSensitivityLabelRemoved

Sie können jetzt auch Vertraulichkeits Bezeichnungen auf Microsoft Teams, Office 365 Gruppen und SharePoint-Websites anwenden. [Weitere Informationen](sensitivity-labels-teams-groups-sites.md)

Bei Bedarf können Sie die Vorschau jederzeit deaktivieren.

## <a name="requirements"></a>Anforderungen

Diese Features funktionieren nur mit [Sensitivitäts Bezeichnungen](sensitivity-labels.md). Wenn Sie Azure Information Protection-Bezeichnungen verwendet haben, können Sie diese in Sensitivitäts Bezeichnungen umwandeln, um diese Funktionen für neue Dateien, die Sie hochladen, zu aktivieren. [Erfahren Sie, wie](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Verwenden Sie für diese Vorschau die OneDrive-Synchronisierungs-App-Version 19.002.0121.0008 oder höher unter Windows und Version 19.002.0107.0008 oder höher unter Mac. Beide Versionen wurden am 28. Januar 2019 veröffentlicht und sind derzeit für alle Ringe freigegeben. [Weitere Informationen finden Sie in den OneDrive-Versions](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)hinweisen. Nachdem Sie diese Vorschau aktiviert haben, werden Benutzer, die eine ältere Version der Synchronisierungs-app ausführen, zur Aktualisierung aufgefordert.

## <a name="limitations"></a>Einschränkungen

- Wenn Sie diese Vorschau aktivieren, können Benutzer, die mithilfe des Office-Desktops oder Mobile Apps eine Bezeichnung auf eine Datei anwenden, möglicherweise keine weiteren Änderungen speichern, die Sie an der Datei vorgenommen haben. Stattdessen werden Benutzer von der APP aufgefordert, lokale Änderungen zu speichern oder zu verwerfen. Führen Sie eine der folgenden Aktionen aus, um einen Verlust der Arbeit zu vermeiden:

  - Verwenden Sie die Webversionen der Office-Apps, um Bezeichnungen anzuwenden.

  - Schließen Sie eine Datei, nachdem Sie eine Bezeichnung angewendet haben, und öffnen Sie die Datei erneut, um weitere Änderungen vorzunehmen.

- SharePoint wendet die neuen Bezeichnungen nicht automatisch auf vorhandene Dateien an, die Sie bereits mithilfe von Azure Information Protection-Bezeichnungen verschlüsselt haben. Um die Funktionen zu erhalten, nachdem Sie diese Vorschau aktiviert haben, müssen Sie die folgenden Aufgaben ausführen:

  - Konvertieren Sie die Azure Information Protection-Bezeichnungen in Sensitivitäts Bezeichnungen.

  - Laden Sie die Dateien herunter, und laden Sie Sie in SharePoint hoch.

- SharePoint kann keine Beschriftungen mit benutzerdefinierten Berechtigungen und Beschriftungen mit Ablaufdaten verarbeiten.

- Wenn Benutzer über Bearbeitungsberechtigungen verfügen, können die Webversionen der Office-Apps unabhängig von der Einstellung der Kopierrichtlinie in der Bezeichnung kopiert werden.

- RMS-Sperrung,-Nachverfolgung und-Berichterstellung werden nicht unterstützt.

- Office-Desktop-Apps und Mobile Apps unterstützen nicht die gemeinsame Dokumenterstellung. Stattdessen öffnen diese apps weiterhin Dateien im exklusiven Bearbeitungsmodus.

- Wenn eine Beschriftung eine Verschlüsselung enthält, kann Microsoft Cloud App Security die Bezeichnungsinformationen für die Dateien in SharePoint nicht lesen.

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>Vorbereiten der SharePoint Online Management-Shell für die Vorschau

Vergewissern Sie sich vor dem Aktivieren der Vorschau, dass Sie die neueste SharePoint Online-Verwaltungsshell ausführen. Wenn Sie bereits über die neueste Version verfügen, können Sie die Vorschau aktivieren.

So bereiten Sie die SharePoint Online Management-Shell für die Vorschau vor:

1. Wenn Sie eine frühere Version der SharePoint Online-Verwaltungsshell installiert haben, wechseln Sie zu **Software hinzufügen oder entfernen** , und deinstallieren Sie "SharePoint Online Verwaltungsshell".

2. Wechseln Sie in einem Webbrowser zur Seite Download Center, und [Laden Sie die neueste SharePoint Online Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).

3. Wählen Sie Ihre Sprache aus, und klicken Sie dann auf **herunterladen**.

4. Wählen Sie zwischen der Datei x64 und x86. msi aus. Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows oder die x86-Datei ausführen, wenn Sie die 32-Bit-Version ausführen. Wenn Sie nicht wissen, finden Sie unter [welche Version des Windows-Betriebssystems soll ich ausführen?](https://support.microsoft.com/help/13443/windows-which-operating-system).

5. Nachdem Sie die Datei heruntergeladen haben, führen Sie die Datei aus, und führen Sie die Schritte im Setup-Assistenten aus.

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>Aktivieren der Vorschau mithilfe von Microsoft PowerShell (Opt-in)

Verwenden Sie zum Aktivieren der Vorschau das Cmdlet "SPOTenant":

1. Stellen Sie eine Verbindung mit SharePoint her, indem Sie ein Arbeits-oder Schulkonto mit globalen Administrator-oder SharePoint-Administratorrechten in Office 365 verwenden. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

2. Führen Sie den folgenden Befehl aus:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>Planen des Roll-out nach dem Erstellen oder Ändern einer Sensitivitäts Bezeichnung

Nachdem Sie eine Sensitivitäts Bezeichnung im Microsoft 365 Compliance Center erstellt oder geändert haben, veröffentlichen Sie Sie in Phasen. Wenn Sie Bezeichnungen veröffentlichen, die nicht vollständig synchronisiert sind, können die Dateien nicht in den Webversionen der Office-Apps geöffnet werden, wenn die Benutzer die Bezeichnungen auf Dateien anwenden und in SharePoint hochladen. Such-und eDiscovery funktionieren auch nicht für die Dateien.

Es wird empfohlen, dass Sie die folgenden Schritte ausführen:

1. Veröffentlichen Sie die neue oder geänderte Vertraulichkeits Bezeichnung nur für eine oder zwei Personen.

2. Warten Sie mindestens 24 Stunden nach der ersten Veröffentlichung. Stellen Sie sicher, dass die Bezeichnung vollständig synchronisiert wurde.

3. Veröffentlichen Sie das Label breiter.

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a>Deaktivieren der Vorschau mithilfe von Microsoft PowerShell (Opt-out)

Wenn Sie diese Vorschau deaktivieren, werden Dateien, die Sie während der Vorschau hochgeladen haben, weiterhin durch die Bezeichnung geschützt. Die entsprechenden Einstellungen werden weiterhin erzwungen. Wenn Sie Bezeichnungen auf neue Dateien anwenden, nachdem Sie die Vorschau deaktiviert haben, können die Volltextsuche, eDiscovery und die gemeinsame Dokumenterstellung nicht mehr verwendet werden.

Verwenden Sie das Cmdlet "SPOTenant", um die Vorschau zu deaktivieren:

1. Stellen Sie eine Verbindung mit SharePoint her, indem Sie ein Arbeits-oder Schulkonto mit globalen Administrator-oder SharePoint-Administratorrechten in Office 365 verwenden. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

2. Führen Sie den folgenden Befehl aus:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
