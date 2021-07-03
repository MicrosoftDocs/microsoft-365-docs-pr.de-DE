---
title: Selbstregistrieren vorhandener Geräte
description: Registrieren Sie wiederverwendete Geräte, die Sie möglicherweise bereits selbst haben, damit sie von Microsoft Managed Desktop verwaltet werden können.
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: ed254234109bc5ff9865ff49ed3fa0fff8770ab0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286909"
---
# <a name="register-existing-devices-yourself"></a>Selbstregistrieren vorhandener Geräte

>[!NOTE]
>In diesem Thema werden die Schritte beschrieben, mit denen Sie bereits bestehende Geräte wiederverwenden und in Microsoft Managed Desktop registrieren können. Wenn Sie mit völlig neuen Geräten arbeiten, führen Sie stattdessen die Schritte unter ["Registrieren neuer Geräte in Microsoft Managed Desktop selbst"](register-devices-self.md) aus.

Der Prozess für Partner ist in [den Schritten für Partner zum Registrieren von Geräten](register-devices-partner.md)dokumentiert.

Microsoft Managed Desktop können mit völlig neuen Geräten arbeiten oder Bereits-Geräte wiederverwenden (dies erfordert ein erneutes Image). Sie können Geräte mit Microsoft Managed Desktop im Microsoft Endpoint Manager-Portal registrieren.

## <a name="prepare-to-register-existing-devices"></a>Vorbereiten der Registrierung vorhandener Geräte


Führen Sie die folgenden Schritte aus, um vorhandene Geräte zu registrieren:

1. [Rufen Sie den Hardwarehash für jedes Gerät ab.](#obtain-the-hardware-hash)
2. [Zusammenführen der Hashdaten](#merge-hash-data)
3. [Registrieren Sie die Geräte in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Überprüfen Sie, ob das Bild korrekt ist.](#check-the-image)
5. [Bereitstellen des Geräts](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Abrufen des Hardwarehashs

Microsoft Managed Desktop identifiziert jedes Gerät eindeutig, indem er auf seinen Hardwarehash verweist. Sie haben vier Optionen zum Abrufen dieser Informationen von Geräten, die Sie bereits verwenden:

- Fragen Sie Ihren OEM-Lieferanten nach der AutoPilot-Registrierungsdatei, die die Hardwarehashes enthält.
- Sammeln von Informationen in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).
- Führen Sie ein Windows PowerShell Skript aus – entweder [mithilfe](#active-directory-powershell-script-method) von Active Directory oder [manuell](#manual-powershell-script-method) auf jedem Gerät – und sammeln Sie die Ergebnisse in einer Datei.
- Starten Sie jedes Gerät , aber schließen Sie nicht die Windows Einrichtung ab, und [erfassen Sie die Hashes auf einem Wechseldatenträger.](#flash-drive-method)

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Sie können Microsoft Endpoint Configuration Manager verwenden, um die Hardwarehashes von vorhandenen Geräten zu sammeln, die Sie bei Microsoft Managed Desktop registrieren möchten.

> [!IMPORTANT]
> Alle Geräte, für die Sie diese Informationen abrufen möchten, müssen Windows 10 Version 1703 oder höher ausgeführt werden. 

Wenn Sie alle diese Voraussetzungen erfüllt haben, können Sie die Informationen mithilfe der folgenden Schritte sammeln:

1. Wählen Sie in der Configuration Manager-Konsole **"Überwachung"** aus. 
2. Erweitern Sie im Arbeitsbereich "Überwachung" den Knoten **"Berichterstellung",** **"Berichte",** und wählen Sie den Knoten **"Hardware – Allgemein"** aus. 
3. Führen Sie den Bericht **aus, Windows Autopilot-Geräteinformationen,** und zeigen Sie die Ergebnisse an.
4. Wählen Sie in der Berichtsanzeige das Symbol **"Exportieren"** aus, und wählen Sie die Option **CSV (durch Trennzeichen getrennt)** aus.
5. Nach dem Speichern der Datei müssen Sie die Ergebnisse nur auf die Geräte filtern, die Sie bei Microsoft Managed Desktop registrieren und die Daten in Microsoft Managed Desktop hochladen möchten. Öffnen Sie Microsoft Endpoint Manager, navigieren Sie zum Menü **"Geräte",** suchen Sie nach Microsoft Managed Desktop Abschnitt, und wählen Sie **"Geräte"** aus. Wählen Sie **+ Geräte registrieren** aus, wodurch ein Fly-In geöffnet wird, um neue Geräte zu registrieren.


Weitere Informationen finden Sie unter [Registrieren von Geräten über das Verwaltungsportal.](#register-devices-by-using-the-admin-portal)


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell-Skriptmethode

In einer Active Directory-Umgebung können Sie das `Get-WindowsAutoPilotInfo` PowerShell-Cmdlet verwenden, um die Informationen von Geräten in Active Directory-Gruppen mithilfe von WinRM remote zu sammeln. Sie können auch das Cmdlet verwenden `Get-AD Computer` und gefilterte Ergebnisse für einen bestimmten Hardwaremodellnamen abrufen, der im Katalog enthalten ist. Bevor Sie fortfahren, bestätigen Sie zunächst diese Voraussetzungen, und fahren Sie dann mit den Schritten fort:

- WinRM ist aktiviert.
- Die Geräte, die Sie registrieren möchten, sind im Netzwerk aktiv (d. a. sie sind nicht getrennt oder deaktiviert).
- Stellen Sie sicher, dass Sie über einen Domänenanmeldeinformationsparameter verfügen, der über die Berechtigung zum Remoteausführung auf den Geräten verfügt.
- Stellen Sie sicher, dass Windows Firewall den Zugriff auf WMI zulässt. Gehen Sie dazu folgendermaßen vor:

    1. Öffnen Sie die Windows Defender Firewall-Systemsteuerung, und wählen Sie  **"App oder Feature über Windows Defender Firewall zulassen"** aus.

    2. Suchen Sie **Windows Verwaltungsinstrumentation (WMI)** in der Liste, aktivieren Sie sowohl für private als auch **öffentliche**, und wählen Sie dann **OK** aus.

1. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.

2. Führen Sie *eines* der folgenden Skripts aus:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. Greifen Sie auf alle Verzeichnisse zu, in denen möglicherweise Einträge für die Geräte vorhanden sind. Entfernen Sie Einträge für jedes Gerät aus *allen* Verzeichnissen, einschließlich Windows Server Active Directory Domänendienste und Azure Active Directory. Beachten Sie, dass die vollständige Verarbeitung der Entfernung einige Stunden dauern kann.

4. Zugriffsverwaltungsdienste, bei denen möglicherweise Einträge für die Geräte vorhanden sind. Entfernen Sie Einträge für jedes Gerät aus *allen* Verwaltungsdiensten, einschließlich Microsoft Endpoint Configuration Manager, Microsoft Intune und Windows Autopilot. Beachten Sie, dass die vollständige Verarbeitung der Entfernung einige Stunden dauern kann.

Jetzt können Sie mit der Registrierung von [Geräten](#register-devices-by-using-the-admin-portal)fortfahren.

#### <a name="manual-powershell-script-method"></a>Manuelle PowerShell-Skriptmethode

1. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2. Ausführen `Install-Script -Name Get-WindowsAutoPilotInfo`
3. Ausführen `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [Zusammenführen der Hashdaten.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flashlaufwerkmethode

1. Fügen Sie auf einem anderen Gerät als dem, das Sie registrieren, ein USB-Laufwerk ein.
2. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
3. Ausführen `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Aktivieren Sie das Gerät, das Sie registrieren, *aber starten Sie die Einrichtung nicht.* Wenn Sie versehentlich die Einrichtung starten, müssen Sie das Gerät zurücksetzen oder neu erstellen.
5. Fügen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT + F10.
6. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie dann `cd <pathToUsb>` .
7. Ausführen `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Ausführen `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Entfernen Sie das USB-Laufwerk, und fahren Sie das Gerät durch Ausführen herunter. `shutdown -s -t 0`
10. [Zusammenführen der Hashdaten.](#merge-hash-data)

> [!IMPORTANT]
> Schalten Sie das Gerät, das Sie registrieren, erst wieder ein, nachdem Sie die Registrierung für das Gerät abgeschlossen haben. 

### <a name="merge-hash-data"></a>Zusammenführen von Hashdaten

Wenn Sie die Hardwarehashdaten mithilfe der manuellen PowerShell- oder Flashlaufwerkmethoden gesammelt haben, müssen die Daten nun in den CSV-Dateien in einer einzigen Datei zusammengefasst sein, um die Registrierung abzuschließen. Hier ist ein Beispiel für ein PowerShell-Skript, um dies zu vereinfachen:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Nachdem die Hashdaten in einer CSV-Datei zusammengeführt wurden, können Sie jetzt [mit der Registrierung der Geräte](#register-devices-by-using-the-admin-portal)fortfahren.

## <a name="register-devices-by-using-the-admin-portal"></a>Registrieren von Geräten mithilfe des Verwaltungsportals

Wählen Sie in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)im linken Navigationsbereich **"Geräte"** aus. Suchen Sie im Menü nach Microsoft Managed Desktop Abschnitt, und wählen Sie **"Geräte"** aus. Wählen Sie im Arbeitsbereich Microsoft Managed Desktop Geräte die Option **+Geräte registrieren** aus, wodurch ein Fly-In zum Registrieren neuer Geräte geöffnet wird.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

Führen Sie die folgenden Schritte aus:

1. Geben Sie im **Dateiupload** einen Pfad zu der CSV-Datei an, die Sie zuvor erstellt haben.
2. Wählen Sie im Dropdownmenü ein [Geräteprofil](../service-description/profiles.md) aus.
3. Wählen Sie **"Geräte registrieren"** aus. Das System fügt die Geräte der Liste der Geräte auf dem **Blatt "Geräte"** hinzu, die als **"Registrierung ausstehend"** gekennzeichnet ist. Die Registrierung dauert in der Regel weniger als 10 Minuten, und bei erfolgreicher Ausführung wird das Gerät als **"Bereit für Benutzer"** angezeigt, was bedeutet, dass es bereit ist und darauf wartet, dass ein Benutzer mit der Verwendung beginnt.

> [!NOTE]
> Wenn Sie die Azure Active Directory (AAD)-Gruppenmitgliedschaft eines Geräts manuell ändern, wird sie automatisch der Gruppe für ihr Geräteprofil zugewiesen und aus allen in Konflikt stehende Gruppen entfernt.

Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite überwachen. Mögliche gemeldete Zustände sind:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Check back later. |
| Registrierung fehlgeschlagen | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen finden Sie unter Problembehandlung bei [der Geräteregistrierung.](#troubleshooting-device-registration) |
| Bereit für Benutzer | Die Registrierung war erfolgreich, und das Gerät kann jetzt an den Benutzer übermittelt werden. Microsoft Managed Desktop führen sie durch die erstmalige Einrichtung, sodass Sie keine weiteren Vorbereitungen durchführen müssen. |
| Aktiv | Das Gerät wurde an den Benutzer übermittelt und bei Ihrem Mandanten registriert. Dies weist auch darauf hin, dass sie das Gerät regelmäßig verwenden. |
| Inaktiv | Das Gerät wurde an den Benutzer übermittelt und bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch vor kurzem nicht verwendet (in den letzten 7 Tagen).  | 

### <a name="troubleshooting-device-registration"></a>Problembehandlung bei der Geräteregistrierung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Wir konnten dieses Gerät nicht registrieren, da wir keine Übereinstimmung für den bereitgestellten Hersteller, das Modell oder die Seriennummer finden konnten. Bestätigen Sie diese Werte bei Ihrem Geräteanbieter. |
| Hardwarehash ungültig | Der Hardwarehash, den Sie für dieses Gerät bereitgestellt haben, wurde nicht richtig formatiert. Überprüfen Sie den Hardwarehash, und übermitteln Sie es dann erneut. |
| Gerät bereits registriert | Dieses Gerät ist bereits in Ihrer Organisation registriert. Es sind keine weiteren Aktionen erforderlich. |
| Gerät, das von einer anderen Organisation beansprucht wird | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Wenden Sie sich an Ihren Geräteanbieter. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Wenden Sie sich an den Support, und geben Sie die Anforderungs-ID an: <requestId> |

## <a name="check-the-image"></a>Bild überprüfen

Wenn Ihr Gerät von einem Microsoft Managed Desktop Partneranbieter stammt, sollte das Image korrekt sein.

Sie können das Bild auch selbst anwenden, wenn Sie möchten. Wenden Sie sich zunächst an den Microsoft-Mitarbeiter, mit dem Sie arbeiten, und dieser stellt Ihnen den Speicherort und die Schritte zum Anwenden des Bilds bereit.

## <a name="deliver-the-device"></a>Bereitstellen des Geräts

> [!IMPORTANT]
> Bevor Sie das Gerät an Ihren Benutzer übergeben, stellen Sie sicher, dass Sie die [entsprechenden Lizenzen](../get-ready/prerequisites.md) für diesen Benutzer abgerufen und angewendet haben.

Wenn alle Lizenzen angewendet werden, können Sie Ihre Benutzer für die Verwendung von [Geräten vorbereiten.](get-started-devices.md)Anschließend kann ihr Benutzer das Gerät starten und die Windows Einrichtungsoberfläche durchlaufen.
