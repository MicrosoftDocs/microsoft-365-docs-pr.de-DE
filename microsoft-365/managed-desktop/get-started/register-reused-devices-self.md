---
title: Selbstregistrieren vorhandener Geräte
description: Registrieren Sie wiederverwendete Geräte, die Sie möglicherweise bereits selbst haben, damit sie von Microsoft Managed Desktop verwaltet werden können.
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840515"
---
# <a name="register-existing-devices-yourself"></a>Selbstregistrieren vorhandener Geräte

>[!NOTE]
>In diesem Thema werden die Schritte beschrieben, die Sie ausführen müssen, um bereits vorhandene Geräte wiederzuverwenden und in Microsoft Managed Desktop zu registrieren. Wenn Sie mit völlig neuen Geräten arbeiten, führen Sie stattdessen die Schritte unter "Registrieren neuer Geräte [in Microsoft Managed Desktop"](register-devices-self.md) selbst aus.

Der Prozess für Partner ist in den Schritten für [Partner zum Registrieren von Geräten dokumentiert.](register-devices-partner.md)

Microsoft Managed Desktop kann mit ganz neuen Geräten verwendet werden, oder Sie können bereits vorhandene Geräte wiederverwenden (für die ein Reimage erforderlich ist). Sie können Geräte bei Microsoft Managed Desktop im Microsoft Endpoint Manager-Portal registrieren.

## <a name="prepare-to-register-existing-devices"></a>Vorbereiten der Registrierung vorhandener Geräte


Führen Sie die folgenden Schritte aus, um vorhandene Geräte zu registrieren:

1. [Rufen Sie den Hardwarehash für jedes Gerät ab.](#obtain-the-hardware-hash)
2. [Zusammenführen der Hashdaten](#merge-hash-data)
3. [Registrieren Sie die Geräte in Microsoft Managed Desktop.](#register-devices-by-using-the-admin-portal)
4. [Überprüfen Sie, ob das Bild korrekt ist.](#check-the-image)
5. [Bereitstellen des Geräts](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Abrufen des Hardwarehashs

Microsoft Managed Desktop identifiziert jedes Gerät eindeutig, indem auf den Hardwarehash bezuget wird. Sie haben vier Optionen, um diese Informationen von Geräten zu erhalten, die Sie bereits verwenden:

- Fragen Sie Ihren #A0 nach der AutoPilot-Registrierungsdatei, die die Hardwarehashes enthält.
- Sammeln von Informationen in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).
- Führen Sie Windows PowerShell Skript aus– entweder mithilfe [](#manual-powershell-script-method) von [Active Directory](#active-directory-powershell-script-method) oder manuell auf jedem Gerät – und erfassen Sie die Ergebnisse in einer Datei.
- Starten Sie jedes Gerät – aber schließen Sie die #A0 nicht ab – und sammeln Sie die Hashes auf einem [Wechseldatenträger.](#flash-drive-method)

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Sie können Microsoft Endpoint Configuration Manager verwenden, um die Hardwarehashes von vorhandenen Geräten zu sammeln, die Sie bei Microsoft Managed Desktop registrieren möchten.

> [!IMPORTANT]
> Auf allen Geräten, für die Sie diese Informationen erhalten möchten, muss Windows 10, Version 1703 oder höher, ausgeführt werden. 

Wenn sie alle diese Voraussetzungen erfüllt haben, können Sie die Informationen sammeln, indem Sie die folgenden Schritte ausführen:

1. Wählen Sie in der Configuration Manager-Konsole **"Überwachung" aus.** 
2. Erweitern Sie im Arbeitsbereich "Überwachung" den Knoten **"Berichterstellung",** **erweitern** Sie "Berichte", und wählen Sie den Knoten **"Hardware – Allgemein"** aus. 
3. Führen Sie den Bericht, **Windows Autopilot Device Information** aus, und zeigen Sie die Ergebnisse an.
4. Wählen Sie in der Berichtsanzeige das **Exportsymbol** aus, und wählen Sie die Option **"CSV( durch** Trennzeichen getrennt) aus.
5. Nach dem Speichern der Datei müssen Sie die Ergebnisse nur auf die Geräte filtern, die Sie bei Microsoft Managed Desktop registrieren und die Daten auf Microsoft Managed Desktop hochladen möchten. Öffnen Sie Microsoft Endpoint Manager, navigieren Sie **zum** Menü "Geräte", suchen Sie nach dem Abschnitt "Microsoft Managed Desktop", und wählen Sie **"Geräte" aus.** Select **+ Register devices**, which opens a fly-in to register new devices.


Weitere Informationen [finden Sie unter "Registrieren von Geräten über das](#register-devices-by-using-the-admin-portal) Verwaltungsportal".


#### <a name="active-directory-powershell-script-method"></a>Active Directory -PowerShell-Skriptmethode

In einer Active Directory-Umgebung können Sie das PowerShell-Cmdlet verwenden, um die Informationen von Geräten in Active Directory-Gruppen mithilfe von `Get-WindowsAutoPilotInfo` WinRM remote zu erfassen. Sie können das Cmdlet auch verwenden und gefilterte Ergebnisse für einen bestimmten Namen des Hardwaremodells im `Get-AD Computer` Katalog erhalten. Bevor Sie fortfahren, bestätigen Sie zunächst diese Voraussetzungen, und fahren Sie dann mit den folgenden Schritten fort:

- WinRM ist aktiviert.
- Die Geräte, die Sie registrieren möchten, sind im Netzwerk aktiv (d. h., sie werden nicht getrennt oder deaktiviert).
- Stellen Sie sicher, dass Sie über einen Domänenanmeldeinformationsparameter verfügen, der über die Berechtigung zum Remote ausführen auf den Geräten verfügt.
- Stellen Sie sicher, dass die Windows-Firewall den Zugriff auf WMI zulässt. Führen Sie dazu die folgenden Schritte aus:

    1. Öffnen Sie Windows Defender Firewall-Systemsteuerung, und wählen **Sie "App oder Feature zulassen"** über Windows Defender Firewall aus. 
    
    2. Suchen **Sie die Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI)** in der Liste, aktivieren Sie sie sowohl für **privat** als auch für öffentlich, und wählen Sie dann **OK aus.**

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

3. Greifen Sie auf alle Verzeichnisse zu, in denen möglicherweise Einträge für die Geräte enthalten sind. Entfernen Sie Einträge für jedes Gerät aus *allen* Verzeichnissen, einschließlich Windows Server Active Directory Domain Services und Azure Active Directory. Beachten Sie, dass es einige Stunden dauern kann, bis die Entfernung vollständig abtransportiert wurde.

4. Zugriff auf Verwaltungsdienste, bei denen möglicherweise Einträge für die Geräte angezeigt werden. Entfernen Sie Einträge für jedes Gerät aus *allen* Verwaltungsdiensten, einschließlich Microsoft Endpoint Configuration Manager, Microsoft Intune und Windows Autopilot. Beachten Sie, dass es einige Stunden dauern kann, bis das Entfernen vollständig abtransportiert wurde.

Jetzt können Sie mit der Registrierung [von Geräten fortfahren.](#register-devices-by-using-the-admin-portal)

#### <a name="manual-powershell-script-method"></a>Manuelle PowerShell-Skriptmethode

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2.  Ausführen `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Ausführen `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [Führen Sie die Hashdaten zusammen.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flashlaufwerkmethode

1. Fügen Sie auf einem anderen Gerät als dem, das Sie registrieren, ein USB-Laufwerk ein.
2. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
3. Ausführen `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Aktivieren Sie das Gerät, das Sie registrieren, *aber starten Sie die Einrichtung nicht.* Wenn Sie versehentlich die Einrichtung starten, müssen Sie das Gerät zurücksetzen oder ein Reimaging durchführen.
5. Setzen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT+ F10.
6. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie dann `cd <pathToUsb>` aus.
7. Ausführen `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Ausführen `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Entfernen Sie das USB-Laufwerk, und fahren Sie dann das Gerät herunter, indem Sie `shutdown -s -t 0`
10. [Führen Sie die Hashdaten zusammen.](#merge-hash-data)

>[!IMPORTANT]
>Schalten Sie das Gerät, das Sie registrieren, erst wieder ein, wenn Sie die Registrierung für das Gerät abgeschlossen haben. 



### <a name="merge-hash-data"></a>Zusammenführen von Hashdaten

Wenn Sie die Hardwarehashdaten mithilfe der manuellen PowerShell- oder #A0 gesammelt haben, müssen Sie die Daten in den #A1 nun in einer einzigen Datei kombinieren, um die Registrierung abzuschließen. Hier sehen Sie ein Beispiel für ein PowerShell-Skript, um dies einfach zu machen:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Nachdem die Hashdaten in einer #A0 zusammengeführt wurden, können Sie jetzt mit der [Registrierung der Geräte fortfahren.](#register-devices-by-using-the-admin-portal)


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrieren von Geräten über das Verwaltungsportal

Wählen [Sie in Microsoft Endpoint Manager](https://endpoint.microsoft.com/)im linken Navigationsbereich "Geräte" aus.  Suchen Sie im Menü nach dem Abschnitt "Microsoft Managed Desktop", und wählen Sie **"Geräte" aus.** Wählen Sie im Arbeitsbereich "Microsoft Managed Desktop Devices" die Option **+Geräte** registrieren aus, wodurch ein Fly-In zum Registrieren neuer Geräte geöffnet wird.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Gehen Sie folgendermaßen vor:

1. Geben **Sie im Dateiupload** einen Pfad zu der zuvor erstellten CSV-Datei an.

1. Wählen Sie **Geräte registrieren aus.** Das System fügt die Geräte ihrer Liste der Geräte auf dem Blatt "Geräte" **hinzu,** das als **Registrierung ausstehend markiert ist.** Die Registrierung dauert in der Regel weniger als 10 Minuten, und bei erfolgreicher Verwendung wird das Gerät als bereit für den Benutzer angezeigt, was bedeutet, dass es bereit ist und darauf wartet, dass ein Benutzer mit der Verwendung beginnt. 


Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite überwachen. Mögliche gemeldete Zustände sind:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Check back later. |
| Registrierung fehlgeschlagen | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen [finden Sie unter Problembehandlung bei](#troubleshooting-device-registration) der Geräteregistrierung. |
| Bereit für Benutzer | Die Registrierung war erfolgreich, und das Gerät kann jetzt an den Benutzer zugestellt werden. Microsoft Managed Desktop führt sie durch die erste Einrichtung, sodass Sie keine weiteren Vorbereitungen machen müssen. |
| Aktiv | Das Gerät wurde an den Benutzer zugestellt und bei Ihrem Mandanten registriert. Dies weist auch darauf hin, dass sie das Gerät regelmäßig verwenden. |
| Inaktiv | Das Gerät wurde an den Benutzer zugestellt und bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch erst kürzlich (in den letzten 7 Tagen) verwendet.  | 

#### <a name="troubleshooting-device-registration"></a>Problembehandlung bei der Geräteregistrierung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Wir konnten dieses Gerät nicht registrieren, da wir keine Übereinstimmung für den angegebenen Hersteller, das Modell oder die Seriennummer finden konnten. Bestätigen Sie diese Werte bei Ihrem Geräteanbieter. |
| Hardwarehash ungültig | Der Hardwarehash, den Sie für dieses Gerät bereitgestellt haben, wurde nicht richtig formatiert. Überprüfen Sie den Hardwarehash, und übermitteln Sie es erneut. |
| Gerät bereits registriert | Dieses Gerät ist bereits in Ihrer Organisation registriert. Keine weitere Aktion erforderlich. |
| Von einer anderen Organisation beanspruchtes Gerät | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Er muss sich bei Ihrem Geräteanbieter ernennen. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Wenden Sie sich an den Support, und geben Sie die Anforderungs-ID an: <requestId> |

### <a name="check-the-image"></a>Überprüfen des Bilds

Wenn Ihr Gerät von einem Microsoft Managed Desktop -Partneranbieter stammen, sollte das Image korrekt sein.

Sie können das Bild auch selbst anwenden. Um zu beginnen, wenden Sie sich an den Microsoft-Vertreter, mit dem Sie arbeiten, und dieser stellt Ihnen den Speicherort und die Schritte zum Anwenden des Bilds zur Verfügung.

### <a name="deliver-the-device"></a>Bereitstellen des Geräts

> [!IMPORTANT]
> Bevor Sie das Gerät an Ihren Benutzer aus der Hand nehmen, stellen Sie sicher, dass Sie die entsprechenden [Lizenzen](../get-ready/prerequisites.md) für diesen Benutzer erhalten und angewendet haben.

Wenn alle Lizenzen angewendet werden, können Sie Ihre Benutzer für die Verwendung von Geräten bereit [machen.](get-started-devices.md)Anschließend kann der Benutzer das Gerät starten und die Windows-Setup-Erfahrung fortsetzen.









