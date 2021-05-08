---
title: Selbstregistrieren neuer Geräte
description: Registrieren Sie Geräte selbst, damit sie von der Microsoft Managed Desktop
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
ms.openlocfilehash: 850d7e6692d3ccbfda6e15c8d5ca95301bd4d094
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245612"
---
# <a name="register-new-devices-yourself"></a>Selbstregistrieren neuer Geräte

Microsoft Managed Desktop können mit brandneuen Geräten arbeiten oder Sie können bereits vorhandene Geräte wiederverwenden (dies erfordert, dass Sie sie neu abbilden). Sie können Geräte mit Microsoft Managed Desktop im Microsoft Endpoint Manager registrieren.

> [!NOTE]
> Arbeiten Sie mit einem Partner zusammen, um Geräte zu erhalten? Wenn ja, müssen Sie sich keine Gedanken über das Abrufen der Hardwarehashes machen. Sie kümmern sich um dies für Sie. Stellen Sie sicher, dass Ihr Partner eine Beziehung mit Ihnen im [Partner Center aufbaut.](https://partner.microsoft.com/dashboard) Weitere Informationen finden Sie unter [Partner Center help](/partner-center/request-a-relationship-with-a-customer). Sobald diese Beziehung hergestellt wurde, registriert Ihr Partner einfach Geräte in Ihrem Namen – keine weiteren Aktionen, die von Ihnen erforderlich sind. Wenn Sie die Details anzeigen möchten oder Ihr Partner Fragen hat, lesen Sie Schritte für [Partner, um Geräte zu registrieren.](register-devices-partner.md) Nachdem die Geräte registriert wurden, [](#check-the-image) können Sie mit der Überprüfung des Bilds und der Bereitstellung der Geräte [an](#deliver-the-device) Ihre Benutzer fortfahren.



## <a name="prepare-to-register-brand-new-devices"></a>Vorbereiten der Registrierung neuer Geräte


Sobald Sie die neuen Geräte in der Hand haben, führen Sie die folgenden Schritte aus:

1. [Rufen Sie den Hardwarehash für jedes Gerät ab.](#obtain-the-hardware-hash)
2. [Zusammenführen der Hashdaten](#merge-hash-data)
3. [Registrieren Sie die Geräte in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Überprüfen Sie, ob das Bild richtig ist.](#check-the-image)
5. [Bereitstellen des Geräts](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Abrufen des Hardwarehashs

Microsoft Managed Desktop identifiziert jedes Gerät durch Verweisen auf den Hardwarehash eindeutig. Sie haben drei Optionen, um diese Informationen zu erhalten:

- Fragen Sie Ihren OEM-Lieferanten nach der AutoPilot-Registrierungsdatei, die die Hardwarehashes enthält.
- Führen Sie [ein Windows PowerShell auf](#powershell-script-method) jedem Gerät aus, und sammeln Sie die Ergebnisse in einer Datei.
- Starten Sie jedes Gerät, aber schließen Sie Windows Einrichtungserfahrung nicht ab, und sammeln Sie die Hashes auf einem [Wechseldatenträger.](#flash-drive-method)

#### <a name="powershell-script-method"></a>PowerShell-Skriptmethode

Sie können das [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell-Skripts auf der PowerShell Gallery-Website verwenden. Weitere Informationen zur Geräteidentifizierung und zum Hardwarehash finden Sie unter Hinzufügen von Geräten [Windows Autopilot](/mem/autopilot/add-devices#device-identification).

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2.  Ausführen `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Ausführen `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  Führen `powershell -ExecutionPolicy restricted` Sie aus, um zu verhindern, dass nachfolgende uneingeschränkte Skripts ausgeführt werden.


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

>[!IMPORTANT]
>Schalten Sie das Gerät, das Sie registrieren, erst wieder ein, wenn Sie die Registrierung für das Gerät abgeschlossen haben. 


### <a name="merge-hash-data"></a>Zusammenführen von Hashdaten

Sie müssen die Daten in den CSV-Dateien in einer einzigen Datei kombinieren, um die Registrierung abzuschließen. Im Folgenden finden Sie ein PowerShell-Beispielskript, um es einfach zu machen:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


### <a name="register-devices-by-using-the-admin-portal"></a>Registrieren von Geräten mithilfe des Administratorportals

Wählen [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)im linken **Navigationsbereich** Geräte aus. Suchen Sie nach dem Microsoft Managed Desktop im Menü, und wählen Sie **Geräte aus.** Wählen Sie im arbeitsbereich Microsoft Managed Desktop Geräte auswählen **+ registrieren** Geräte aus, der ein Fly-In öffnet, um neue Geräte zu registrieren.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Führen Sie die folgenden Schritte aus:

1. Geben **Sie unter Dateiupload** einen Pfad zur zuvor erstellten CSV-Datei an.
2. Wählen Sie [im](../service-description/profiles.md) Dropdownmenü ein Geräteprofil aus.
3. Wählen **Sie Geräte registrieren aus.** Das System fügt die Geräte ihrer Liste der Geräte auf **Geräten** hinzu, die als **Registrierung ausstehend gekennzeichnet sind.** Die Registrierung dauert in der Regel weniger als 10 Minuten, und bei erfolgreicher Verwendung wird das Gerät als **Bereit** für Benutzer angezeigt, was bedeutet, dass es bereit ist und darauf wartet, dass ein Benutzer mit der Verwendung beginnt.

> [!NOTE]
> Wenn Sie die Azure Active Directory (AAD)-Gruppenmitgliedschaft eines Geräts manuell ändern, wird sie automatisch der Gruppe für ihr Geräteprofil zugewiesen und aus allen in Konflikt enden Gruppen entfernt.

Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite überwachen. Mögliche gemeldete Zustände sind:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Überprüfen Sie später. |
| Fehler bei der Registrierung | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen [finden Sie unter Problembehandlung](#troubleshooting-device-registration) bei der Geräteregistrierung. |
| Bereit für Benutzer | Die Registrierung ist erfolgreich, und das Gerät kann jetzt an den Benutzer zugestellt werden. Microsoft Managed Desktop führt sie durch das erste Einrichten, sodass Sie keine weiteren Vorbereitungen mehr machen müssen. |
| Aktiv | Das Gerät wurde an den Benutzer zugestellt und bei Ihrem Mandanten registriert. Dieser Zustand gibt auch an, dass sie das Gerät regelmäßig verwenden. |
| Inaktiv | Das Gerät wurde an den Benutzer zugestellt und bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch in letzter Zeit (in den letzten 7 Tagen) nicht verwendet.  | 

#### <a name="troubleshooting-device-registration"></a>Problembehandlung bei der Geräteregistrierung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Wir konnten dieses Gerät nicht registrieren, da wir keine Übereinstimmung für den angegebenen Hersteller, das Modell oder die Seriennummer finden konnten. Bestätigen Sie diese Werte mit Ihrem Geräteanbieter. |
| Hardwarehash ungültig | Der Hardwarehash, den Sie für dieses Gerät bereitgestellt haben, wurde nicht ordnungsgemäß formatiert. Überprüfen Sie den Hardwarehash, und übermitteln Sie dann erneut. |
| Gerät bereits registriert | Dieses Gerät ist bereits in Ihrer Organisation registriert. Keine weiteren Aktionen erforderlich. |
| Von einer anderen Organisation beanspruchtes Gerät | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Informieren Sie sich bei Ihrem Geräteanbieter. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Wenden Sie sich an den Support, und geben Sie die Anforderungs-ID an: <requestId> |

### <a name="check-the-image"></a>Überprüfen des Bilds

Wenn Ihr Gerät von einem Microsoft Managed Desktop Partneranbieters stammen, sollte das Bild korrekt sein.

Sie können das Bild auch selbst anwenden, wenn Sie es bevorzugen. Um zu beginnen, wenden Sie sich an den Microsoft-Vertreter, mit dem Sie arbeiten, und er stellt Ihnen den Speicherort und die Schritte zum Anwenden des Bilds zur Verfügung.

### <a name="autopilot-group-tag"></a>Autopilot-Gruppentag

Wenn Sie das Admin-Portal zum Registrieren von Geräten verwenden, weisen wir automatisch das **Microsoft365Managed_Autopilot** Autopilot-Gruppentag zu.
Der Dienst überwacht alle Microsoft Managed Desktop geräte täglich und weist das Gruppentag allen zu, die es noch nicht haben.

### <a name="deliver-the-device"></a>Bereitstellen des Geräts

> [!IMPORTANT]
> Bevor Sie das Gerät an Ihren Benutzer senden, stellen Sie sicher, dass Sie die entsprechenden [Lizenzen](../get-ready/prerequisites.md) für diesen Benutzer erhalten und angewendet haben.

Wenn alle Lizenzen angewendet werden, können Sie Ihre Benutzer für die Verwendung von Geräten bereit [machen.](get-started-devices.md)Anschließend kann der Benutzer das Gerät starten und die Windows ausführen.
