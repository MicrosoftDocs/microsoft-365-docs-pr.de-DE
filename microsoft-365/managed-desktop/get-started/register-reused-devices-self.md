---
title: Selbstregistrieren vorhandener Geräte
description: Wiederverwendete Geräte registrieren, die Sie möglicherweise bereits haben, damit Sie von Microsoft Managed Desktop verwaltet werden können
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 6c241894ab50b6b1341b06f47c107c8945fb6e8c
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104570"
---
# <a name="register-existing-devices-yourself"></a>Selbstregistrieren vorhandener Geräte

>[!NOTE]
>In diesem Thema werden die Schritte beschrieben, mit denen Sie bereits verwendete Geräte wieder verwenden und in Microsoft Managed Desktop registrieren können. Wenn Sie mit brandneuen Geräten arbeiten, befolgen Sie stattdessen die Schritte unter [Registrieren neuer Geräte in Microsoft Managed Desktop](register-devices-self.md) .

Der Prozess für Partner ist in [Schritten für Partner zum Registrieren von Geräten](register-devices-partner.md)dokumentiert.

Microsoft Managed Desktop kann mit brandneuen Geräten verwendet werden, oder Sie können Geräte wieder verwenden, die Sie möglicherweise bereits haben (Dies erfordert ein erneutes Abbild). Sie können Geräte mit Microsoft Managed Desktop im Microsoft Endpoint Manager-Portal registrieren.

## <a name="prepare-to-register-existing-devices"></a>Vorbereiten der Registrierung vorhandener Geräte


Führen Sie die folgenden Schritte aus, um vorhandene Geräte zu registrieren:

1. [Rufen Sie den Hardwarehash für jedes Gerät ab.](#obtain-the-hardware-hash)
2. [Zusammenführen der Hash Daten](#merge-hash-data)
3. [Registrieren Sie die Geräte in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Stellen Sie sicher, dass das Bild korrekt ist.](#check-the-image)
5. [Verteilen des Geräts](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Abrufen des Hardwarehash

Microsoft Managed Desktop identifiziert jedes Gerät eindeutig, indem es auf seinen Hardwarehash verweist. Sie haben vier Optionen, um diese Informationen von Geräten abzurufen, die Sie bereits verwenden:

- Fragen Sie Ihren OEM-Lieferanten nach der Autopilot-Registrierungsdatei, die die Hardware-Hashes enthält.
- Sammeln von Informationen im [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).
- Führen Sie ein Windows PowerShell-Skript aus, indem Sie entweder [Active Directory](#active-directory-powershell-script-method) oder [manuell](#manual-powershell-script-method) auf jedem Gerät verwenden und die Ergebnisse in einer Datei sammeln.
- Starten Sie jedes Gerät, aber schließen Sie nicht die Windows Setup-Umgebung ab – und [sammeln Sie die Hashes auf einem wechselbaren Flashlaufwerk](#flash-drive-method).

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Sie können den Microsoft Endpoint Configuration Manager verwenden, um die Hardware Hashes von vorhandenen Geräten zu erfassen, die Sie bei Microsoft Managed Desktop registrieren möchten.

> [!IMPORTANT]
> Für alle Geräte, für die Sie diese Informationen abrufen möchten, muss Windows 10, Version 1703 oder höher, installiert sein. 

Wenn Sie alle diese Voraussetzungen erfüllt haben, können Sie die Informationen mit den folgenden Schritten erfassen:

1. Wählen Sie in der Configuration Manager-Konsole **Überwachung**aus. 
2. Erweitern Sie im Überwachungs Arbeitsbereich den Knoten **Berichterstellung** , erweitern Sie **Berichte**, und wählen Sie den Knoten **Hardware-allgemein** aus. 
3. Führen Sie den Bericht, **Windows Autopilot-Geräteinformationen**aus, und zeigen Sie die Ergebnisse an.
4. Wählen Sie im Berichts-Viewer das **Export** Symbol aus, und wählen Sie die **CSV-Option (durch Trennzeichen-getrennt)** aus.
5. Nachdem Sie die Datei gespeichert haben, müssen Sie die Ergebnisse nur auf die Gerätefiltern, die Sie bei Microsoft Managed Desktop registrieren möchten, und die Daten in Microsoft Managed Desktop hochladen. Öffnen Sie Microsoft Endpoint Manager, navigieren Sie zum Menü **Geräte** , suchen Sie nach dem Abschnitt Microsoft Managed Desktop, und wählen Sie **Geräte**aus. Wählen Sie **+ Register Geräte** aus, die ein einfliegen öffnen, um neue Geräte zu registrieren.


Weitere Informationen hierzu erhalten Sie unter [Registrieren von Geräten mithilfe des Verwaltungsportals](#register-devices-by-using-the-admin-portal) .


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell-Skriptmethode

In einer Active Directory Umgebung können Sie das PowerShell- `Get-WindowsAutoPilotInfo` Cmdlet verwenden, um die Informationen von Geräten in Active Directory Gruppen mithilfe von WinRM Remote zu erfassen. Sie können auch das `Get-AD Computer` Cmdlet verwenden und gefilterte Ergebnisse für bestimmte Hardwaremodell Namen abrufen, die im Katalog enthalten sind. Bestätigen Sie dazu zunächst diese Voraussetzungen, und fahren Sie mit den folgenden Schritten fort:

- WinRM ist aktiviert.
- Die zu registrierenden Geräte sind im Netzwerk aktiv (Sie sind nicht getrennt oder ausgeschaltet).
- Stellen Sie sicher, dass Sie über einen Domänenanmelde Parameter verfügen, der die Berechtigung hat, Remote auf den Geräten auszuführen.
- Stellen Sie sicher, dass der Windows-Firewall Zugriff auf WMI zulässt. Führen Sie dazu die folgenden Schritte aus:

    1. Öffnen Sie die **Windows Defender-Firewall** -Systemsteuerung, und wählen Sie **app oder Feature über die Windows Defender-Firewall zulassen**aus.
    
    2. Suchen Sie in der Liste nach **Windows-Verwaltungsinstrumentation (WMI)** , aktivieren Sie für **Privat und öffentlich**, und wählen Sie dann **OK**aus.

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.

2.  Führen Sie *eines* der folgenden Skripts aus:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. Greifen Sie auf alle Verzeichnisse zu, in denen Einträge für die Geräte vorhanden sein können. Entfernen Sie Einträge für jedes Gerät aus *allen* Verzeichnissen, einschließlich Windows Server Active Directory-Domänendienste und Azure Active Directory. Beachten Sie, dass diese Entfernung einige Stunden dauern kann, um den Vorgang vollständig zu verarbeiten.

4. Access Management Services, bei denen Einträge für die Geräte vorhanden sein können. Entfernen Sie Einträge für jedes Gerät aus *allen* Verwaltungsdiensten, einschließlich Microsoft Endpoint Configuration Manager, Microsoft InTune und Windows Autopilot. Beachten Sie, dass diese Entfernung einige Stunden dauern kann, um den Vorgang vollständig zu verarbeiten.

Jetzt können Sie mit dem [Registrieren von Geräten](#register-devices-by-using-the-admin-portal)fortfahren.

#### <a name="manual-powershell-script-method"></a>Manuelle PowerShell-Skriptmethode

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2.  Ausführen `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Ausführen `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [Führen Sie die Hash Daten zusammen.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash Drive-Methode

1. Legen Sie auf einem anderen Gerät als dem, das Sie gerade registrieren, ein USB-Laufwerk ein.
2. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
3. Ausführen `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Aktivieren Sie das Gerät, das Sie registrieren, aber *beginnen Sie nicht mit der Setup-Umgebung*. Wenn Sie das Setupprogramm versehentlich gestartet haben, müssen Sie das Gerät zurücksetzen oder neu abbilden.
5. Legen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT + F10.
6. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie dann aus `cd <pathToUsb>` .
7. Ausführen `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Ausführen `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Entfernen Sie das USB-Laufwerk, und fahren Sie dann das Gerät herunter, indem Sie `shutdown -s -t 0`
10. [Führen Sie die Hash Daten zusammen.](#merge-hash-data)

>[!IMPORTANT]
>Schalten Sie das Gerät, das Sie erneut registrieren, erst wieder ein, wenn Sie die Registrierung dafür abgeschlossen haben. 



### <a name="merge-hash-data"></a>Zusammenführen von Hash Daten

Wenn Sie die Hardwarehash Daten nach den manuellen PowerShell-oder Flash Drive-Methoden gesammelt haben, müssen Sie nun die Daten in den CSV-Dateien in einer einzigen Datei zusammenfassen, um die Registrierung abzuschließen. Hier ist ein Beispiel für PowerShell-Skripts, um dies zu vereinfachen:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Nachdem die Hashdaten in einer CSV-Datei zusammengeführt wurden, können Sie nun mit [dem Registrieren der Geräte](#register-devices-by-using-the-admin-portal)fortfahren.


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrieren von Geräten mithilfe des Verwaltungsportals

Wählen Sie in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)im linken Navigationsbereich **Geräte** aus. Suchen Sie im Menü nach dem Abschnitt Microsoft Managed Desktop, und wählen Sie **Geräte**aus. Wählen Sie im Arbeitsbereich von Microsoft Managed Desktop Geräte die Option **+ Register Geräte** aus, die ein einfliegen zum Registrieren neuer Geräte öffnen.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Führen Sie die folgenden Schritte aus:

1. Geben Sie im Feld **Dateiupload**einen Pfad zu der CSV-Datei an, die Sie zuvor erstellt haben.

1. Wählen Sie **Geräte registrieren**aus. Das System fügt die Geräte zu ihrer Geräteliste auf dem Blade- **Gerät**hinzu, das als **AutopilotRegistrationRequested**gekennzeichnet ist. Die Registrierung dauert in der Regel weniger als 10 Minuten, und wenn das Gerät erfolgreich ist, wird es **für den Benutzer bereit** angezeigt, sodass es bereit ist und darauf wartet, dass ein Benutzer mit der Verwendung beginnt.


Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite überwachen. Mögliche Zustände, die dort gemeldet werden, umfassen:

| Status | Beschreibung |
|---------------|-------------|
| AutopilotRegistrationRequested | Die Registrierung ist noch nicht abgeschlossen. Überprüfen Sie später erneut. |
| Registrierung fehlgeschlagen | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen erhalten Sie unter [Problembehandlung bei der Geräteregistrierung](#troubleshooting-device-registration) . |
| Benutzer einsatzfähig | Die Registrierung wurde erfolgreich ausgeführt, und das Gerät kann nun für den Benutzer bereitgestellt werden. Microsoft Managed Desktop führt Sie durch die erstmalige Einrichtung, sodass Sie keine weiteren Vorbereitungen treffen müssen. |
| Aktiv | Das Gerät wurde dem Benutzer zugestellt und Sie haben sich bei Ihrem Mandanten registriert. Dies deutet auch darauf hin, dass das Gerät regelmäßig verwendet wird. |
| Inaktiv | Das Gerät wurde dem Benutzer zugestellt und Sie haben sich bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch vor kurzem nicht verwendet (in den letzten 7 Tagen).  | 

#### <a name="troubleshooting-device-registration"></a>Problembehandlung bei der Geräteregistrierung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Dieses Gerät konnte nicht registriert werden, da keine Übereinstimmung für den bereitgestellten Hersteller, das Modell oder die Seriennummer gefunden werden konnte. Bestätigen Sie diese Werte mit Ihrem Gerätelieferanten. |
| Hardware Hash ungültig | Der für dieses Gerät angegebene Hardwarehash wurde nicht ordnungsgemäß formatiert. Überprüfen Sie den Hardwarehash doppelt, und senden Sie dann erneut. |
| Gerät ist bereits registriert | Dieses Gerät ist bereits für Ihre Organisation registriert. Keine weitere Aktion erforderlich. |
| Von einer anderen Organisation beanspruchtes Gerät | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Erkundigen Sie sich bei Ihrem Gerätelieferanten. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Kontaktieren Sie den Support, und geben Sie die Anforderungs-ID an: <requestId> |

### <a name="check-the-image"></a>Überprüfen des Bilds

Wenn Ihr Gerät von einem Microsoft Managed Desktop Partner-Anbieter stammt, sollte das Bild korrekt sein.

Sie können das Bild auch auf eigene Faust anwenden, wenn Sie es vorziehen. Um zu beginnen, wenden Sie sich an den Microsoft-Mitarbeiter, mit dem Sie zusammenarbeiten, und Sie werden den Speicherort und die Schritte zum Anwenden des Abbilds erhalten.

### <a name="deliver-the-device"></a>Verteilen des Geräts

> [!IMPORTANT]
> Bevor Sie das Gerät an Ihren Benutzer übergeben, müssen Sie sicherstellen, dass Sie die [entsprechenden Lizenzen](../get-ready/prerequisites.md) für diesen Benutzer erworben und angewendet haben.

Wenn alle Lizenzen angewendet werden, können Sie [Ihre Benutzer zur Verwendung von Geräten verwenden](get-started-devices.md), und dann kann Ihr Benutzer das Gerät starten und die Windows Setup-Umgebung durchlaufen.









