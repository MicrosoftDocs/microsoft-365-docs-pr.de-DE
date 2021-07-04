---
title: Selbstregistrieren neuer Geräte
description: Registrieren Sie Geräte selbst, damit sie von Microsoft Managed Desktop verwaltet werden können.
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
ms.openlocfilehash: a66ad53faf1b38c3db4ab4446dbc1d175fbd99e4
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289535"
---
# <a name="register-new-devices-yourself"></a>Selbstregistrieren neuer Geräte

Microsoft Managed Desktop können mit völlig neuen Geräten arbeiten oder Bereits-Geräte wiederverwenden (dies erfordert ein erneutes Image). Sie können Geräte mit Microsoft Managed Desktop im Microsoft Endpoint Manager-Portal registrieren.

> [!NOTE]
> Arbeiten Sie mit einem Partner zusammen, um Geräte zu erhalten? Wenn dies der Fall ist, müssen Sie sich keine Gedanken über das Abrufen der Hardwarehashes machen. sie kümmern sich darum. Stellen Sie sicher, dass Ihr Partner im [Partner Center](https://partner.microsoft.com/dashboard)eine Beziehung mit Ihnen herstellt. Ihr Partner kann weitere Informationen in der [Partner Center-Hilfe](/partner-center/request-a-relationship-with-a-customer)erhalten. Nachdem diese Beziehung hergestellt wurde, registriert Ihr Partner einfach Geräte in Ihrem Namen – keine weiteren Maßnahmen von Ihnen erforderlich. Wenn Sie die Details anzeigen möchten oder Ihr Partner Fragen hat, lesen Sie [die Schritte für Partner zum Registrieren von Geräten.](register-devices-partner.md) Nachdem die Geräte registriert wurden, können Sie mit [der Überprüfung des Bilds](#check-the-image) fortfahren und die Geräte an Ihre Benutzer [übermitteln.](#deliver-the-device)



## <a name="prepare-to-register-brand-new-devices"></a>Vorbereiten der Registrierung ganz neuer Geräte


Nachdem Sie die neuen Geräte zur Hand haben, führen Sie die folgenden Schritte aus:

1. [Rufen Sie den Hardwarehash für jedes Gerät ab.](#obtain-the-hardware-hash)
2. [Zusammenführen der Hashdaten](#merge-hash-data)
3. [Registrieren Sie die Geräte in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Überprüfen Sie, ob das Bild korrekt ist.](#check-the-image)
5. [Bereitstellen des Geräts](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Abrufen des Hardwarehashs

Microsoft Managed Desktop identifiziert jedes Gerät eindeutig, indem er auf seinen Hardwarehash verweist. Sie haben drei Optionen zum Abrufen dieser Informationen:

- Fragen Sie Ihren OEM-Lieferanten nach der AutoPilot-Registrierungsdatei, die die Hardwarehashes enthält.
- Führen Sie auf jedem Gerät ein [Windows PowerShell Skript](#powershell-script-method) aus, und erfassen Sie die Ergebnisse in einer Datei.
- Starten Sie jedes Gerät , aber schließen Sie nicht die Windows Setup ab, und [sammeln Sie die Hashes auf einem Wechseldatenträger.](#flash-drive-method)

#### <a name="powershell-script-method"></a>PowerShell-Skriptmethode

Sie können das [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell-Skript auf der PowerShell-Katalogwebsite verwenden. Weitere Informationen zur Geräteidentifikation und zum Hardwarehash finden Sie unter [Hinzufügen von Geräten zu Windows Autopilot.](/mem/autopilot/add-devices#device-identification)

1. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2. Ausführen `Install-Script -Name Get-WindowsAutoPilotInfo`
3. Ausführen `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. Ausführen, `powershell -ExecutionPolicy restricted` um zu verhindern, dass nachfolgende uneingeschränkte Skripts ausgeführt werden.

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

> [!IMPORTANT]
> Schalten Sie das Gerät, das Sie registrieren, erst wieder ein, nachdem Sie die Registrierung für das Gerät abgeschlossen haben. 

### <a name="merge-hash-data"></a>Zusammenführen von Hashdaten

Sie müssen die Daten in den CSV-Dateien in einer einzigen Datei zusammenstellen, um die Registrierung abzuschließen. Hier ist ein Beispiel für ein PowerShell-Skript, um dies zu vereinfachen:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

### <a name="register-devices-by-using-the-admin-portal"></a>Registrieren von Geräten mithilfe des Verwaltungsportals

Wählen Sie in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)im linken Navigationsbereich **"Geräte"** aus. Suchen Sie im Menü nach Microsoft Managed Desktop Abschnitt, und wählen Sie **"Geräte"** aus. Wählen Sie im Arbeitsbereich Microsoft Managed Desktop Geräte die Option **+Geräte registrieren** aus, wodurch ein Fly-In zum Registrieren neuer Geräte geöffnet wird.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

Führen Sie die folgenden Schritte aus:

1. Geben Sie im **Dateiupload** einen Pfad zu der CSV-Datei an, die Sie zuvor erstellt haben.
2. Wählen Sie im Dropdownmenü ein [Geräteprofil](../service-description/profiles.md) aus.
3. Wählen Sie **"Geräte registrieren"** aus. Das System fügt die Geräte zu Ihrer Liste der Geräte auf **Geräten** hinzu, die als **Registrierung ausstehend** gekennzeichnet sind. Die Registrierung dauert in der Regel weniger als 10 Minuten, und bei erfolgreicher Ausführung wird das Gerät als **"Bereit für Benutzer"** angezeigt, was bedeutet, dass es bereit ist und darauf wartet, dass ein Benutzer mit der Verwendung beginnt.

> [!NOTE]
> Wenn Sie die Azure Active Directory (AAD)-Gruppenmitgliedschaft eines Geräts manuell ändern, wird sie automatisch der Gruppe für ihr Geräteprofil zugewiesen und aus allen in Konflikt stehende Gruppen entfernt.

Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite überwachen. Mögliche gemeldete Zustände sind:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Check back later. |
| Registrierung fehlgeschlagen | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen finden Sie unter Problembehandlung bei [der Geräteregistrierung.](#troubleshooting-device-registration) |
| Bereit für Benutzer | Die Registrierung war erfolgreich, und das Gerät kann jetzt an den Benutzer übermittelt werden. Microsoft Managed Desktop führen sie durch die erstmalige Einrichtung, sodass Sie keine weiteren Vorbereitungen durchführen müssen. |
| Aktiv | Das Gerät wurde an den Benutzer übermittelt und bei Ihrem Mandanten registriert. Dieser Zustand gibt auch an, dass sie das Gerät regelmäßig verwenden. |
| Inaktiv | Das Gerät wurde an den Benutzer übermittelt und bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch vor kurzem nicht verwendet (in den letzten 7 Tagen).  | 

#### <a name="troubleshooting-device-registration"></a>Problembehandlung bei der Geräteregistrierung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Wir konnten dieses Gerät nicht registrieren, da wir keine Übereinstimmung für den bereitgestellten Hersteller, das Modell oder die Seriennummer finden konnten. Bestätigen Sie diese Werte bei Ihrem Geräteanbieter. |
| Hardwarehash ungültig | Der Hardwarehash, den Sie für dieses Gerät bereitgestellt haben, wurde nicht richtig formatiert. Überprüfen Sie den Hardwarehash, und übermitteln Sie es dann erneut. |
| Gerät bereits registriert | Dieses Gerät ist bereits in Ihrer Organisation registriert. Es sind keine weiteren Aktionen erforderlich. |
| Gerät, das von einer anderen Organisation beansprucht wird | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Wenden Sie sich an Ihren Geräteanbieter. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Wenden Sie sich an den Support, und geben Sie die Anforderungs-ID an: <requestId> |

### <a name="check-the-image"></a>Bild überprüfen

Wenn Ihr Gerät von einem Microsoft Managed Desktop Partneranbieter stammt, sollte das Image korrekt sein.

Sie können das Bild auch selbst anwenden, wenn Sie möchten. Wenden Sie sich zunächst an den Microsoft-Mitarbeiter, mit dem Sie arbeiten, und dieser stellt Ihnen den Speicherort und die Schritte zum Anwenden des Bilds bereit.

### <a name="autopilot-group-tag"></a>Autopilot-Gruppentag

Wenn Sie das Verwaltungsportal zum Registrieren von Geräten verwenden, weisen wir automatisch das **Microsoft365Managed_Autopilot** Autopilot Group Tag zu.
Der Dienst überwacht täglich alle Microsoft Managed Desktop Geräte und weist das Gruppentag allen Geräten zu, die es noch nicht besitzen.

### <a name="deliver-the-device"></a>Bereitstellen des Geräts

> [!IMPORTANT]
> Bevor Sie das Gerät an Ihren Benutzer übergeben, stellen Sie sicher, dass Sie die [entsprechenden Lizenzen](../get-ready/prerequisites.md) für diesen Benutzer abgerufen und angewendet haben.

Wenn alle Lizenzen angewendet werden, können Sie Ihre Benutzer für die Verwendung von [Geräten vorbereiten.](get-started-devices.md)Anschließend kann der Benutzer das Gerät starten und die Windows Einrichtungsoberfläche durchlaufen.
