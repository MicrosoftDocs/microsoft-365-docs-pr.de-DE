---
title: Selbstregistrieren neuer Geräte
description: Registrieren Sie Geräte selbst, damit sie von Microsoft Managed Desktop verwaltet werden können.
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: df6013f2f7fec32e79557a82f9b56fe4ad487786
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840681"
---
# <a name="register-new-devices-yourself"></a>Selbstregistrieren neuer Geräte

Microsoft Managed Desktop kann mit ganz neuen Geräten verwendet werden, oder Sie können bereits vorhandene Geräte wiederverwenden (für die ein Reimage erforderlich ist). Sie können Geräte bei Microsoft Managed Desktop im Microsoft Endpoint Manager-Portal registrieren.

> [!NOTE]
> Arbeiten Sie mit einem Partner zusammen, um Geräte zu erhalten? Wenn ja, müssen Sie sich keine Gedanken über das Abrufen der Hardwarehashes machen. Sie übernehmen dies für Sie. Stellen Sie sicher, dass Ihr Partner eine Beziehung mit Ihnen im [Partner Center aufbaut.](https://partner.microsoft.com/dashboard) Weitere Informationen finden Sie in der [Partner Center-Hilfe.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer) Sobald diese Beziehung hergestellt ist, registriert Ihr Partner einfach Geräte in Ihrem Namen – keine weiteren Aktionen von Ihnen erforderlich. Wenn Sie die Details anzeigen möchten oder Ihr Partner Fragen hat, lesen Sie die Schritte für [Partner, um Geräte zu registrieren.](register-devices-partner.md) Nachdem die Geräte registriert wurden, [](#check-the-image) können Sie mit der Überprüfung des Images und der Bereitstellung der Geräte [für](#deliver-the-device) Ihre Benutzer fortfahren.

## <a name="prepare-to-register-brand-new-devices"></a>Vorbereiten der Registrierung von ganz neuen Geräten


Sobald Sie die neuen Geräte in der Hand haben, führen Sie die folgenden Schritte aus:

1. [Rufen Sie den Hardwarehash für jedes Gerät ab.](#obtain-the-hardware-hash)
2. [Zusammenführen der Hashdaten](#merge-hash-data)
3. [Registrieren Sie die Geräte in Microsoft Managed Desktop.](#register-devices-by-using-the-admin-portal)
4. [Überprüfen Sie, ob das Bild korrekt ist.](#check-the-image)
5. [Bereitstellen des Geräts](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Abrufen des Hardwarehashs

Microsoft Managed Desktop identifiziert jedes Gerät eindeutig, indem auf den Hardwarehash bezuget wird. Sie haben drei Optionen, um diese Informationen zu erhalten:

- Fragen Sie Ihren #A0 nach der AutoPilot-Registrierungsdatei, die die Hardwarehashes enthält.
- Führen Sie [ein Windows PowerShell auf](#powershell-script-method) jedem Gerät aus, und sammeln Sie die Ergebnisse in einer Datei.
- Starten Sie jedes Gerät – aber schließen Sie die #A0 nicht ab – und sammeln Sie die Hashes auf einem [Wechseldatenträger.](#flash-drive-method)

#### <a name="powershell-script-method"></a>PowerShell-Skriptmethode

Sie können [](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) dasGet-WindowsAutoPilotInfo.ps1A0 auf der PowerShell-Katalog-Website verwenden. Weitere Informationen zur Geräteidentifikation und zum Hardwarehash finden Sie unter [Hinzufügen von Geräten zu Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2.  Ausführen `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Ausführen `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  Ausführen, `powershell -ExecutionPolicy restricted` um zu verhindern, dass nachfolgende uneingeschränkte Skripts ausgeführt werden.


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

>[!IMPORTANT]
>Schalten Sie das Gerät, das Sie registrieren, erst wieder ein, wenn Sie die Registrierung für das Gerät abgeschlossen haben. 


### <a name="merge-hash-data"></a>Zusammenführen von Hashdaten

Sie müssen die Daten in den CSV-Dateien in einer einzigen Datei kombinieren, um die Registrierung abzuschließen. Hier sehen Sie ein Beispiel für ein PowerShell-Skript, um dies einfach zu machen:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrieren von Geräten über das Verwaltungsportal

Wählen [Sie in Microsoft Endpoint Manager](https://endpoint.microsoft.com/)im linken Navigationsbereich "Geräte" aus.  Suchen Sie im Menü nach dem Abschnitt "Microsoft Managed Desktop", und wählen Sie **"Geräte" aus.** Wählen Sie im Arbeitsbereich "Microsoft Managed Desktop Devices" die Option **+Geräte** registrieren aus, wodurch ein Fly-In zum Registrieren neuer Geräte geöffnet wird.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Gehen Sie folgendermaßen vor:

1. Geben **Sie im Dateiupload** einen Pfad zu der zuvor erstellten CSV-Datei an.
3. Wählen Sie **Geräte registrieren aus.** Das System fügt die Geräte ihrer Liste der Geräte auf Geräten **hinzu,** die als **Registrierung ausstehend markiert sind.** Die Registrierung dauert in der Regel weniger als 10 Minuten, und bei erfolgreicher Verwendung wird das Gerät als bereit für den Benutzer angezeigt, was bedeutet, dass es bereit ist und darauf wartet, dass ein Benutzer mit der Verwendung beginnt. 


Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite überwachen. Mögliche gemeldete Zustände sind:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Check back later. |
| Registrierung fehlgeschlagen | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen [finden Sie unter Problembehandlung bei](#troubleshooting-device-registration) der Geräteregistrierung. |
| Bereit für Benutzer | Die Registrierung war erfolgreich, und das Gerät kann jetzt an den Benutzer zugestellt werden. Microsoft Managed Desktop führt sie durch die erste Einrichtung, sodass Sie keine weiteren Vorbereitungen machen müssen. |
| Aktiv | Das Gerät wurde an den Benutzer zugestellt und bei Ihrem Mandanten registriert. Dieser Zustand gibt auch an, dass sie das Gerät regelmäßig verwenden. |
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





