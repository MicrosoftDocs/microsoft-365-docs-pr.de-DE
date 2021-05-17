---
title: Selbstregistrieren vorhandener Geräte
description: Registrieren Sie wiederverwendete Geräte, die Sie möglicherweise bereits selbst haben, damit sie von der Microsoft Managed Desktop
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
ms.openlocfilehash: 21b0062a337dbeb3c7dec8b715971dbbc4917db1
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893275"
---
# <a name="register-existing-devices-yourself"></a>Selbstregistrieren vorhandener Geräte

>[!NOTE]
>In diesem Thema werden die Schritte beschrieben, wie Sie bereits vorhandene Geräte wiederverwenden und in Microsoft Managed Desktop. Wenn Sie mit brandneuen Geräten arbeiten, führen Sie die Schritte unter Registrieren neuer Geräte [in Microsoft Managed Desktop selbst](register-devices-self.md) aus.

Der Prozess für Partner ist unter Schritte für Partner zum Registrieren [von Geräten dokumentiert.](register-devices-partner.md)

Microsoft Managed Desktop können mit brandneuen Geräten arbeiten oder Sie können bereits vorhandene Geräte wiederverwenden (dies erfordert, dass Sie sie neu abbilden). Sie können Geräte mit Microsoft Managed Desktop im Microsoft Endpoint Manager registrieren.

## <a name="prepare-to-register-existing-devices"></a>Vorbereiten der Registrierung vorhandener Geräte


Führen Sie die folgenden Schritte aus, um vorhandene Geräte zu registrieren:

1. [Rufen Sie den Hardwarehash für jedes Gerät ab.](#obtain-the-hardware-hash)
2. [Zusammenführen der Hashdaten](#merge-hash-data)
3. [Registrieren Sie die Geräte in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Überprüfen Sie, ob das Bild richtig ist.](#check-the-image)
5. [Bereitstellen des Geräts](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Abrufen des Hardwarehashs

Microsoft Managed Desktop identifiziert jedes Gerät durch Verweisen auf den Hardwarehash eindeutig. Sie haben vier Optionen, um diese Informationen von Geräten zu erhalten, die Sie bereits verwenden:

- Fragen Sie Ihren OEM-Lieferanten nach der AutoPilot-Registrierungsdatei, die die Hardwarehashes enthält.
- Sammeln von Informationen in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).
- Führen Sie Windows PowerShell -- entweder mithilfe von [](#manual-powershell-script-method) [Active Directory](#active-directory-powershell-script-method) oder manuell auf jedem Gerät - aus, und sammeln Sie die Ergebnisse in einer Datei.
- Starten Sie jedes Gerät, aber schließen Sie Windows Einrichtungserfahrung nicht ab, und sammeln Sie die Hashes auf einem [Wechseldatenträger.](#flash-drive-method)

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Sie können die Microsoft Endpoint Configuration Manager verwenden, um die Hardwarehashes von vorhandenen Geräten zu sammeln, die Sie bei Microsoft Managed Desktop.

> [!IMPORTANT]
> Alle Geräte, für die Sie diese Informationen erhalten möchten, müssen Windows 10 Version 1703 oder höher ausgeführt werden. 

Wenn Sie alle diese Voraussetzungen erfüllt haben, können Sie die Informationen sammeln, indem Sie die folgenden Schritte ausführen:

1. Wählen Sie in der Configuration Manager-Konsole Überwachung **aus.** 
2. Erweitern Sie im Arbeitsbereich Überwachung den Knoten **Berichterstellung,** erweitern Sie **Berichte,** und wählen Sie **den Knoten Hardware – Allgemein** aus. 
3. Führen Sie den Bericht aus, **Windows Autopilot Device Information**, und zeigen Sie die Ergebnisse an.
4. Wählen Sie in der Berichtsanzeige das Symbol **Exportieren** aus, und wählen Sie die **Option CSV (durch** Trennzeichen getrennt) aus.
5. Nach dem Speichern der Datei müssen Sie die Ergebnisse nur auf die Geräte filtern, auf denen Sie sich bei Microsoft Managed Desktop registrieren und die Daten auf Microsoft Managed Desktop. Öffnen Microsoft Endpoint Manager, navigieren Sie zum Menü **Geräte,** suchen Sie nach Microsoft Managed Desktop, und wählen Sie **Geräte aus.** Wählen **Sie + Geräte registrieren** aus, wodurch ein Fly-In zum Registrieren neuer Geräte geöffnet wird.


Weitere Informationen finden Sie unter Registrieren [von Geräten mithilfe des Administratorportals.](#register-devices-by-using-the-admin-portal)


#### <a name="active-directory-powershell-script-method"></a>Active Directory -PowerShell-Skriptmethode

In einer Active Directory-Umgebung können Sie das PowerShell-Cmdlet verwenden, um die Informationen von Geräten in Active Directory-Gruppen mithilfe von `Get-WindowsAutoPilotInfo` WinRM remote zu erfassen. Sie können auch das Cmdlet verwenden und gefilterte Ergebnisse für einen bestimmten Hardwaremodellnamen im `Get-AD Computer` Katalog erhalten. Bevor Sie fortfahren, bestätigen Sie zunächst diese Voraussetzungen, und fahren Sie dann mit den Schritten fort:

- WinRM ist aktiviert.
- Die Geräte, die Sie registrieren möchten, sind im Netzwerk aktiv (d. h., sie werden nicht getrennt oder deaktiviert).
- Stellen Sie sicher, dass Sie über einen Domänenanmeldeinformationsparameter verfügen, der über die Berechtigung zum Remote ausführen auf den Geräten verfügt.
- Stellen Sie sicher, Windows Firewall den Zugriff auf WMI zulässt. Gehen Sie dazu folgendermaßen vor:

    1. Öffnen Sie **Windows Defender Firewall** Systemsteuerung, und wählen Sie **App oder Feature über Windows Defender Firewall.**
    
    2. Suchen **Windows Verwaltungsinstrumentation (Management Instrumentation, WMI)** in der Liste, aktivieren Sie **für Private** und Public , und wählen Sie dann **OK aus.**

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.

2.  Führen *Sie eines der* folgenden Skripts aus:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. Greifen Sie auf verzeichnisse zu, in denen Einträge für die Geräte enthalten sein können. Entfernen Sie Einträge für jedes Gerät aus *allen* Verzeichnissen, einschließlich Windows Server Active Directory Domain Services und Azure Active Directory. Beachten Sie, dass das Entfernen einige Stunden dauern kann, um den Vorgang vollständig zu verarbeiten.

4. Zugriff auf Verwaltungsdienste, bei denen Einträge für die Geräte enthalten sein können. Entfernen Sie Einträge für jedes Gerät *aus* allen Verwaltungsdiensten, einschließlich Microsoft Endpoint Configuration Manager, Microsoft Intune und Windows Autopilot. Beachten Sie, dass das Entfernen einige Stunden dauern kann, um den Vorgang vollständig zu verarbeiten.

Jetzt können Sie mit der [Registrierung von Geräten fortfahren.](#register-devices-by-using-the-admin-portal)

#### <a name="manual-powershell-script-method"></a>Manuelle PowerShell-Skriptmethode

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2.  Ausführen `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Ausführen `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [Zusammenführen der Hashdaten.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash drive-Methode

1. Fügen Sie auf einem anderen Gerät als dem, das Sie registrieren, ein USB-Laufwerk ein.
2. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
3. Ausführen `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Aktivieren Sie das Gerät, das Sie registrieren, *starten Sie jedoch nicht die Einrichtungserfahrung*. Wenn Sie die Einrichtung versehentlich starten, müssen Sie das Gerät zurücksetzen oder neu abbilden.
5. Legen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT + F10.
6. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie dann `cd <pathToUsb>` aus.
7. Ausführen `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Ausführen `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Entfernen Sie das USB-Laufwerk, und fahren Sie das Gerät herunter, indem Sie `shutdown -s -t 0`
10. [Zusammenführen der Hashdaten.](#merge-hash-data)

>[!IMPORTANT]
>Schalten Sie das Gerät, das Sie registrieren, erst wieder ein, wenn Sie die Registrierung für das Gerät abgeschlossen haben. 



### <a name="merge-hash-data"></a>Zusammenführen von Hashdaten

Wenn Sie die Hardwarehashdaten mithilfe der manuellen PowerShell- oder Flashlaufwerkmethoden gesammelt haben, müssen Sie die Daten in den #A0 nun in einer einzigen Datei kombinieren, um die Registrierung abzuschließen. Im Folgenden finden Sie ein PowerShell-Beispielskript, um es einfach zu machen:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Nachdem die Hashdaten in einer #A0 zusammengeführt wurden, können Sie nun mit der [Registrierung der Geräte fortfahren.](#register-devices-by-using-the-admin-portal)


## <a name="register-devices-by-using-the-admin-portal"></a>Registrieren von Geräten mithilfe des Administratorportals

Wählen [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)im linken **Navigationsbereich** Geräte aus. Suchen Sie nach dem Microsoft Managed Desktop im Menü, und wählen Sie **Geräte aus.** Wählen Sie im arbeitsbereich Microsoft Managed Desktop Geräte auswählen **+ registrieren** Geräte aus, der ein Fly-In öffnet, um neue Geräte zu registrieren.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Führen Sie die folgenden Schritte aus:

1. Geben **Sie unter Dateiupload** einen Pfad zur zuvor erstellten CSV-Datei an.
2. Wählen Sie [im](../service-description/profiles.md) Dropdownmenü ein Geräteprofil aus.
3. Wählen **Sie Geräte registrieren aus.** Das System fügt die Geräte ihrer Liste der Geräte auf dem **Blatt Geräte** hinzu, das als **Registrierung ausstehend gekennzeichnet ist.** Die Registrierung dauert in der Regel weniger als 10 Minuten, und bei erfolgreicher Verwendung wird das Gerät als **Bereit** für Benutzer angezeigt, was bedeutet, dass es bereit ist und darauf wartet, dass ein Benutzer mit der Verwendung beginnt.

> [!NOTE]
> Wenn Sie die Azure Active Directory (AAD)-Gruppenmitgliedschaft eines Geräts manuell ändern, wird sie automatisch der Gruppe für ihr Geräteprofil zugewiesen und aus allen in Konflikt enden Gruppen entfernt.

Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite überwachen. Mögliche gemeldete Zustände sind:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Überprüfen Sie später. |
| Fehler bei der Registrierung | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen [finden Sie unter Problembehandlung](#troubleshooting-device-registration) bei der Geräteregistrierung. |
| Bereit für Benutzer | Die Registrierung ist erfolgreich, und das Gerät kann jetzt an den Benutzer zugestellt werden. Microsoft Managed Desktop führt sie durch das erste Einrichten, sodass Sie keine weiteren Vorbereitungen mehr machen müssen. |
| Aktiv | Das Gerät wurde an den Benutzer zugestellt und bei Ihrem Mandanten registriert. Dies bedeutet auch, dass sie das Gerät regelmäßig verwenden. |
| Inaktiv | Das Gerät wurde an den Benutzer zugestellt und bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch in letzter Zeit (in den letzten 7 Tagen) nicht verwendet.  | 

### <a name="troubleshooting-device-registration"></a>Problembehandlung bei der Geräteregistrierung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Wir konnten dieses Gerät nicht registrieren, da wir keine Übereinstimmung für den angegebenen Hersteller, das Modell oder die Seriennummer finden konnten. Bestätigen Sie diese Werte mit Ihrem Geräteanbieter. |
| Hardwarehash ungültig | Der Hardwarehash, den Sie für dieses Gerät bereitgestellt haben, wurde nicht ordnungsgemäß formatiert. Überprüfen Sie den Hardwarehash, und übermitteln Sie dann erneut. |
| Gerät bereits registriert | Dieses Gerät ist bereits in Ihrer Organisation registriert. Keine weiteren Aktionen erforderlich. |
| Von einer anderen Organisation beanspruchtes Gerät | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Informieren Sie sich bei Ihrem Geräteanbieter. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Wenden Sie sich an den Support, und geben Sie die Anforderungs-ID an: <requestId> |

## <a name="check-the-image"></a>Überprüfen des Bilds

Wenn Ihr Gerät von einem Microsoft Managed Desktop Partneranbieters stammen, sollte das Bild korrekt sein.

Sie können das Bild auch selbst anwenden, wenn Sie es bevorzugen. Um zu beginnen, wenden Sie sich an den Microsoft-Vertreter, mit dem Sie arbeiten, und er stellt Ihnen den Speicherort und die Schritte zum Anwenden des Bilds zur Verfügung.

## <a name="deliver-the-device"></a>Bereitstellen des Geräts

> [!IMPORTANT]
> Bevor Sie das Gerät an Ihren Benutzer senden, stellen Sie sicher, dass Sie die entsprechenden [Lizenzen](../get-ready/prerequisites.md) für diesen Benutzer erhalten und angewendet haben.

Wenn alle Lizenzen angewendet werden, können Sie Ihre Benutzer für die Verwendung von Geräten bereit [machen.](get-started-devices.md)Anschließend kann der Benutzer das Gerät starten und die Windows ausführen.









