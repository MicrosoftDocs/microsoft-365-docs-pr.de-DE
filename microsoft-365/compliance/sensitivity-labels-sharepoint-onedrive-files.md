---
title: Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Administratoren können die Unterstützung für die Sensitivitäts Bezeichnung für Word-, Excel-und PowerPoint-Dateien in SharePoint und OneDrive aktivieren.
ms.openlocfilehash: 5946fc193b0f96501a2f8168eef0d3e694d9cfcb
ms.sourcegitcommit: 21be88a1b38b6554ffa1bc5b743c129fe8547704
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41830979"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)

Vor dieser Vorschau haben Sie bei der Anwendung von Sensitivitäts Bezeichnungen, die die Verschlüsselung in Office-Dateien in SharePoint und OneDrive gespeichert haben, den Inhalt dieser Dateien nicht verarbeiten können. Die gemeinsame Dokumenterstellung, eDiscovery, Verhinderung von Datenverlust, Suche, vertiefen und anderen kollaborativen Features funktionierte unter diesen Umständen nicht. In dieser Vorschau werden diese Funktionen aktiviert, wenn die Verschlüsselung mit einem cloudbasierten Schlüssel angewendet wurde:

- SharePoint erkennt Vertraulichkeits Bezeichnungen, die auf Word-, Excel-und PowerPoint-Dateien in SharePoint und OneDrive angewendet werden. SharePoint erzwingt auch die Einstellungen, die mit den einzelnen Bezeichnungen übereinstimmen.

- Wenn Sie eine Datei aus SharePoint oder OneDrive herunterladen, wird die Vertraulichkeits Bezeichnung mit der Datei durchgesetzt, und die Einstellungen bleiben erhalten.

- Wenden Sie Sensitivitäts Bezeichnungen auf Office-Dateien an, und öffnen und bearbeiten Sie Dateien, auf die die Vertraulichkeits Bezeichnungen angewendet werden (sofern die Berechtigungen der Bezeichnung dies zulassen), indem Sie die Webversionen von Word, Excel und PowerPoint verwenden. Bei Word im Internet können Sie beim Bearbeiten von Dokumenten auch die automatische Beschriftung verwenden.

- Office 365 eDiscovery unterstützt die Volltextsuche in Dateien, auf die Sensitivitäts Bezeichnungen angewendet wurden. DLP-Richtlinien (Data Loss Prevention) decken Inhalte in diesen Dateien ab.

- Für die Überwachung von Sensitivitäts Bezeichnungen stehen drei neue Überwachungsereignisse zur Verfügung:
  - FileSensitivityApplied
  - FileSensitivityLabelChanged
  - FileSensitivityLabelRemoved

> [!NOTE]
> Wenn die Verschlüsselung nicht mit einem cloudbasierten Schlüssel, sondern mit einem lokalen Schlüssel, einer wichtigen Verwaltungstopologie, die häufig als "eigenen Schlüssel halten" (Hyok), verwendet wurde, ändert sich das SharePoint-Verhalten bei dieser Vorschau nicht. 

Sie können jetzt auch Vertraulichkeits Bezeichnungen auf Microsoft Teams, Office 365 Gruppen und SharePoint-Websites anwenden. Weitere Informationen zu dieser separaten Vorschau finden Sie unter [use Sensitivity Labels with Microsoft Teams, Office 365 Groups, and SharePoint Sites (Public Preview)](sensitivity-labels-teams-groups-sites.md).

Sie haben jederzeit die Möglichkeit, diese Vorschau jederzeit zu deaktivieren.

Sehen Sie sich das folgende Video (kein Audio) an, um diese neuen Funktionen in Aktion anzuzeigen:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a>Anforderungen

Diese Features funktionieren nur mit [Vertraulichkeits Bezeichnungen](sensitivity-labels.md) . Wenn Sie derzeit über Azure Information Protection-Bezeichnungen verfügen, migrieren Sie Sie zunächst zu Sensitivitäts Bezeichnungen, sodass Sie diese Funktionen für neue Dateien, die Sie hochladen, aktivieren können. Anweisungen finden Sie unter [How to migrate Azure Information Protection Labels to Unified Sensitivity Labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Verwenden Sie für diese Vorschau die OneDrive-Synchronisierungs-App-Version 19.002.0121.0008 oder höher unter Windows und Version 19.002.0107.0008 oder höher unter Mac. Beide Versionen wurden am 28. Januar 2019 veröffentlicht und sind derzeit für alle Ringe freigegeben. Weitere Informationen finden Sie in den [Anmerkungen zur OneDrive-Version](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Nachdem Sie diese Vorschau aktiviert haben, werden Benutzer, die eine ältere Version der Synchronisierungs-app ausführen, aufgefordert, Sie zu aktualisieren.

## <a name="limitations"></a>Einschränkungen

- Wenn Sie diese Vorschau aktivieren, können Benutzer, die eine Bezeichnung für eine Datei in einem OneDrive-synchronisierungsordner ändern, möglicherweise keine anderen an der Datei vorgenommenen Änderungen speichern.  Benutzer sehen einen [roten Kreis mit einem weißen Kreuz Symbol Fehler](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), und Sie werden aufgefordert, neue Änderungen als separate Kopie zu speichern.  Neben Bezeichnungsänderungen, die von Benutzern initiiert werden, kann dasselbe Verhalten auftreten, wenn ein Administratoreinstellungen für eine veröffentlichte Bezeichnung ändert, die bereits auf Dateien angewendet wird, die auf den synchronisierungsclient des Benutzers heruntergeladen wurden.
    
    Führen Sie eine der folgenden Aktionen aus, um den Verlust von Arbeit für diese Szenarien zu vermeiden:
    - Verwenden Sie die Webversionen der Office-Apps, um Bezeichnungen anzuwenden.
    - Schließen Sie eine Datei, nachdem Sie eine Bezeichnung angewendet haben, und öffnen Sie die Datei erneut, um weitere Änderungen vorzunehmen.

- SharePoint wendet die neuen Bezeichnungen nicht automatisch auf vorhandene Dateien an, die Sie bereits mithilfe von Azure Information Protection-Bezeichnungen verschlüsselt haben. Um die Funktionen zu erhalten, nachdem Sie diese Vorschau aktiviert haben, müssen Sie die folgenden Aufgaben ausführen:
    
    1. Stellen Sie sicher, dass Sie die Azure Information Protection-Bezeichnungen zu Sensitivitäts Bezeichnungen migriert und diese im Microsoft 365 Compliance Center oder in einer entsprechenden Bezeichnungs Verwaltungskonsole veröffentlicht haben.
    
    2. Laden Sie die Dateien herunter, und laden Sie Sie in SharePoint hoch.

- In SharePoint können keine verschlüsselten Dateien verarbeitet werden, wenn die Bezeichnung, auf die die Verschlüsselung angewendet wird, eine der folgenden Konfigurationen für die Verschlüsselung aufweist:
    - **Zulassen, dass Benutzerberechtigungen zuweisen, wenn Sie die Bezeichnung anwenden** , und **in Word, PowerPoint und Excel Benutzer zur Angabe von Berechtigungen auffordern**
    - Der **Benutzer Zugriff auf Inhalts Ablauf** wird auf einen anderen Wert als **Never**festgelegt.

- Für ein verschlüsseltes Dokument, das Bearbeitungsberechtigungen für einen Benutzer gewährt, kann das Kopieren in den Webversionen der Office-Apps nicht blockiert werden.

- Die Dokument Verfolgungs Website für Azure Information Protection wird nicht unterstützt.

- Office-Desktop-Apps und Mobile Apps unterstützen nicht die gemeinsame Dokumenterstellung. Stattdessen öffnen diese apps weiterhin Dateien im exklusiven Bearbeitungsmodus.

- Wenn eine Beschriftung eine Verschlüsselung enthält, kann Microsoft Cloud App Security die Bezeichnungsinformationen für die Dateien in SharePoint nicht lesen.

- Wenn ein beschriftetes Dokument in SharePoint hochgeladen wird und die Bezeichnung angewandte Verschlüsselung mithilfe eines Kontos aus einem Dienstprinzipalnamen verwendet wird, kann das Dokument nicht in Office im Internet geöffnet werden. Zu den Beispielszenarien zählen Microsoft Cloud-App-Sicherheit und eine Datei, die per e-Mail an Teams gesendet wird.

- Dokumente, die auf folgende Weise verschlüsselt wurden, können nicht in Office im Internet geöffnet werden:
    - Verschlüsselung, die einen lokalen Schlüssel verwendet ("eigenen Schlüssel halten" oder Hyok)
    - Verschlüsselung, die unabhängig von einer Bezeichnung angewendet wurde, beispielsweisedurch direkte Anwendung einer Vorlage zum Schutz von Rechteverwaltung.

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>Vorbereiten der SharePoint Online Management-Shell für die Vorschau

Vergewissern Sie sich vor dem Aktivieren der Vorschau, dass SharePoint Online Verwaltungsshell Version 16.0.19418.12000 oder höher ausgeführt wird. Wenn Sie bereits über die neueste Version verfügen, können Sie die Vorschau aktivieren.

1. Wenn Sie eine frühere Version der SharePoint Online Management Shell aus dem PowerShell-Katalog installiert haben, können Sie das Modul aktualisieren, indem Sie das folgende Cmdlet ausführen.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Wenn Sie eine frühere Version der SharePoint Online Management Shell aus dem Microsoft Download Center installiert haben, können Sie auch zum **Hinzufügen oder Entfernen von Software** wechseln und die SharePoint Online Management Shell deinstallieren.

3. Wechseln Sie in einem Webbrowser zur Download Center-Seite, und [laden Sie die neueste SharePoint Online-Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Wählen Sie die gewünschte Sprache aus, und klicken Sie auf **Download**.

5. Wählen Sie zwischen der x64- und der x86-Version der MSI-Datei aus. Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows oder die x86-Datei ausführen, wenn Sie die 32-Bit-Version ausführen. Wenn Sie nicht wissen, finden Sie unter [welche Version des Windows-Betriebssystems soll ich ausführen?](https://support.microsoft.com/help/13443/windows-which-operating-system)


6. Nachdem Sie die Datei heruntergeladen haben, führen Sie die Datei aus, und führen Sie die Schritte im Setup-Assistenten aus.

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
