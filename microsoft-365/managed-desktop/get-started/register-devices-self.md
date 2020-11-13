---
title: Selbstregistrieren neuer Geräte
description: Geräte selbst registrieren, damit Sie von Microsoft Managed Desktop verwaltet werden können
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 48c69a71a98e381123a8f87acc20a34eb6e99806
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071489"
---
# <a name="register-new-devices-yourself"></a>Selbstregistrieren neuer Geräte

Microsoft Managed Desktop kann mit brandneuen Geräten verwendet werden, oder Sie können Geräte wieder verwenden, die Sie möglicherweise bereits haben (Dies erfordert ein erneutes Abbild). Sie können Geräte mit Microsoft Managed Desktop im Microsoft Endpoint Manager-Portal registrieren.

> [!NOTE]
> Arbeiten mit einem Partner, um Geräte zu beziehen? Wenn dies der Fall ist, müssen Sie sich keine Gedanken über das erhalten der Hardware-Hashes machen. Das werden Sie für Sie erledigen. Stellen Sie sicher, dass Ihr Partner eine Beziehung mit Ihnen im [Partner Center](https://partner.microsoft.com/dashboard)herstellt. Ihr Partner kann weitere Informationen finden Sie unter [Hilfe zum Partner Center](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer). Nachdem diese Beziehung hergestellt wurde, registriert Ihr Partner einfach Geräte in Ihrem Namen – keine weiteren Schritte, die von Ihnen benötigt werden. Wenn Sie die Details anzeigen möchten oder Ihr Partner Fragen hat, finden Sie unter [Schritte für Partner zum Registrieren von Geräten](register-devices-partner.md). Nachdem die Geräte registriert wurden, können Sie mit der [Überprüfung des Images](#check-the-image) fortfahren und [die Geräte](#deliver-the-device) an Ihre Benutzer übermitteln.

## <a name="prepare-to-register-brand-new-devices"></a>Vorbereiten der Registrierung brandneuer Geräte


Nachdem Sie die neuen Geräte in der Hand haben, führen Sie die folgenden Schritte aus:

1. [Rufen Sie den Hardwarehash für jedes Gerät ab.](#obtain-the-hardware-hash)
2. [Zusammenführen der Hash Daten](#merge-hash-data)
3. [Registrieren Sie die Geräte in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Stellen Sie sicher, dass das Bild korrekt ist.](#check-the-image)
5. [Verteilen des Geräts](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Abrufen des Hardwarehash

Microsoft Managed Desktop identifiziert jedes Gerät eindeutig, indem es auf seinen Hardwarehash verweist. Sie haben drei Optionen zum erhalten dieser Informationen:

- Fragen Sie Ihren OEM-Lieferanten nach der Autopilot-Registrierungsdatei, die die Hardware-Hashes enthält.
- Führen Sie auf jedem Gerät ein [Windows PowerShell-Skript](#powershell-script-method) aus, und sammeln Sie die Ergebnisse in einer Datei.
- Starten Sie jedes Gerät, aber schließen Sie nicht die Windows Setup-Umgebung ab – und [sammeln Sie die Hashes auf einem wechselbaren Flashlaufwerk](#flash-drive-method).

#### <a name="powershell-script-method"></a>PowerShell-Skriptmethode

Sie können das [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell-Skript auf der PowerShell Gallery-Website verwenden. Weitere Informationen zur Geräteidentifikation und zum Hardwarehash finden Sie unter [Hinzufügen von Geräten zu Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2.  Ausführen `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Ausführen `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  Ausführen `powershell -ExecutionPolicy restricted` , um zu verhindern, dass nachfolgende uneingeschränkte Skripts ausgeführt werden.


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

>[!IMPORTANT]
>Schalten Sie das Gerät, das Sie erneut registrieren, erst wieder ein, wenn Sie die Registrierung dafür abgeschlossen haben. 


### <a name="merge-hash-data"></a>Zusammenführen von Hash Daten

Sie müssen die Daten in den CSV-Dateien in einer einzigen Datei zusammenfassen, um die Registrierung abzuschließen. Hier ist ein Beispiel für PowerShell-Skripts, um dies zu vereinfachen:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrieren von Geräten mithilfe des Verwaltungsportals

Wählen Sie in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)im linken Navigationsbereich **Geräte** aus. Suchen Sie im Menü nach dem Abschnitt Microsoft Managed Desktop, und wählen Sie **Geräte** aus. Wählen Sie im Arbeitsbereich von Microsoft Managed Desktop Geräte die Option **+ Register Geräte** aus, die ein einfliegen zum Registrieren neuer Geräte öffnen.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Gehen Sie folgendermaßen vor:

1. Geben Sie im Feld **Dateiupload** einen Pfad zu der CSV-Datei an, die Sie zuvor erstellt haben.
3. Wählen Sie **Geräte registrieren** aus. Das System fügt die Geräte zu ihrer Geräteliste auf dem Blade- **Gerät** hinzu, das als " **Registrierung ausstehend** " gekennzeichnet wird. Die Registrierung dauert in der Regel weniger als 10 Minuten, und wenn das Gerät erfolgreich ist, wird es **für den Benutzer bereit** angezeigt, sodass es bereit ist und darauf wartet, dass ein Benutzer mit der Verwendung beginnt.


Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite überwachen. Mögliche Zustände, die dort gemeldet werden, umfassen:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Überprüfen Sie später erneut. |
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





