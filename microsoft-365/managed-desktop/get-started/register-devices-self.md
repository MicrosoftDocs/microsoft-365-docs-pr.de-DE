---
title: Registrieren von Geräten in Microsoft Managed Desktop yourself
description: Registrieren Sie Geräte selbst, damit Sie von Microsoft Managed Desktop verwaltet werden können.
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 217418cfce66baa02b30ae7d8a01b938a1f2366e
ms.sourcegitcommit: 7af6350fb5a6d37934c1b6bfdc38acd09b2d5d86
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988431"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a>Registrieren von Geräten in Microsoft Managed Desktop

>[!NOTE]
>In diesem Thema werden die Schritte beschrieben, mit denen Sie Geräte auf eigene Faust registrieren können. Der Prozess für Partner wird unter [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md)dokumentiert.

Microsoft Managed Desktop kann mit brandneuen Geräten verwendet werden, oder Sie können Geräte, die Sie möglicherweise bereits haben (für die Sie Sie erneut abbilden müssen) wieder verwenden. Sie können Geräte mithilfe von Microsoft Managed Desktop im Azure-Portal registrieren oder mithilfe einer API Flexibilität gewinnen.

## <a name="prepare-to-register-devices"></a>Vorbereiten der Registrierung von Geräten

Wenn Sie die gewünschten Geräte noch nicht erhalten haben, überprüfen Sie [Microsoft Managed Desktop-Geräte](../service-description/device-list.md) , und arbeiten Sie mit einem Geräte Partner zusammen, um unterstützte Geräte zu beschaffen.

Unabhängig davon, ob Sie mit vollständig neuen Geräten arbeiten oder vorhandene wieder verwenden, um Sie bei Microsoft Managed Desktop zu registrieren, müssen Sie eine durch **trennzeichengetrennte Datei (CSV)** erstellen. Diese Datei sollte die folgenden Informationen für jedes Gerät aufweisen:

>[!NOTE]
>Dieses Format ist nur für die Self-Service-Registrierung. Die zu verwendenden Format-Partner werden in [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md)dokumentiert.

Diese Werte werden zu Anzeigezwecken verwendet und müssen nicht genau mit den Eigenschaften des Geräts übereinstimmen.
- Gerätehersteller (Beispiel: SpiralOrbit) 
- Gerätemodell (Beispiel: ContosoABC)
- Seriennummer des Geräts

Der Hardwarehash muss eine exakte Übereinstimmung aufweisen.
- Hardware Hash

Zum Abrufen des Hardware Hashs können Sie von Ihrem OEM oder Partner Hilfe anfordern oder die folgenden Schritte für jedes Gerät ausführen:

1.  Öffnen Sie eine PowerShell-Ansage mit Administratorrechten.
2.  Führen`Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Führen`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`


Alternativ können Sie die folgenden Schritte auf einem nagelneuen Gerät ausführen (bevor Sie OOBE zum ersten Mal durchgehen):

1. Legen Sie auf einem anderen Gerät ein USB-Laufwerk ein.
2. Öffnen Sie eine PowerShell-Ansage mit Administratorrechten.
3. Führen`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Aktivieren Sie das Zielgerät, aber beginnen Sie nicht mit der Einrichtung. Wenn Sie das Setupprogramm versehentlich starten, müssen Sie das Gerät zurücksetzen oder neu abbilden.
5. Legen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT + F10.
6. Öffnen Sie eine PowerShell-Ansage mit Administratorrechten, und `cd <pathToUsb>`führen Sie dann aus.
7. Führen`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Führen`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
3. Entfernen Sie das USB-Laufwerk, und fahren Sie dann das Gerät herunter, indem Sie`shutdown -s -t 0`

>[!IMPORTANT]
>Schalten Sie das Zielgerät erst wieder ein, wenn Sie die Registrierung dafür abgeschlossen haben. 

>[!NOTE]
>Zur Vereinfachung können Sie eine [Vorlage](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) für diese CSV-Datei herunterladen.

Die Datei muss **genau die gleichen Spaltenüberschriften** wie das Beispiel 1 (Hersteller, Modell usw.), aber eigene Daten für die anderen Zeilen aufweisen. Wenn Sie die Vorlage verwenden, öffnen Sie Sie in einem Text Bearbeitungstool wie Editor, und ziehen Sie in Erwägung, alle Daten in Zeile 1 allein zu lassen, und geben Sie nur Daten in den Zeilen 2 und darunter ein. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Wenn Sie vergessen haben, die Beispieldaten zu ändern, schlägt die Registrierung fehl.   


## <a name="register-devices-by-using-the-azure-portal"></a>Registrieren von Geräten mithilfe des Azure-Portals

Wählen Sie im Microsoft Managed Desktop [Azure](https://aka.ms/mmdportal)-Portal **Geräte** im linken Navigationsbereich aus. Select **+ Register Devices**; das Fly-in wird geöffnet:

[![Fly-in nach der Auswahl der Register Geräte](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


[//]: # (Leider ist dies nicht der Fall. Wir können diese Notiz entfernen, aber Sie jetzt verlassen, bis wir Gelegenheit haben, darüber zu chatten.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Führen Sie die folgenden Schritte aus:

1. Geben Sie im Feld **Dateiupload**einen Pfad zu der zuvor erstellten CSV-Datei an.
2. Optional können Sie eine **Auftrags-ID** oder eine **Einkaufs-ID** für eigene Tracking-Zwecke hinzufügen. Für diese Werte gibt es keine Formatanforderungen.
3. Wählen Sie **Geräte registrieren**aus. Das System fügt die Geräte der Geräteliste auf dem **Blade Devices**hinzu, die als **Registrierung**ausstehend markiert sind. Die Registrierung dauert in der Regel weniger als 10 Minuten, und wenn das Gerät erfolgreich ist, wird es **für den Benutzer bereit** angezeigt, sodass es bereit ist und darauf wartet, dass ein Endbenutzer verwendet wird.


Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite von **Microsoft Managed Desktop-Devices** überwachen. Mögliche Statusberichte:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Überprüfen Sie später. |
| Registrierung fehlgeschlagen | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen finden Sie unter [Problembehandlung](register-devices-self.md#troubleshooting) . |
| Bereit für Benutzer | Die Registrierung wurde erfolgreich durchgeführt, und das Gerät kann nun an den Endbenutzer übermittelt werden. Microsoft Managed Desktop führt Sie durch die erstmalige Einrichtung, daher müssen Sie keine weiteren Vorbereitungen treffen. |
| Aktiv | Das Gerät wurde an den Endbenutzer übermittelt und ist bei Ihrem Mandanten registriert. Dies bedeutet auch, dass Sie das Gerät regelmäßig verwenden. |
| Inaktiven | Das Gerät wurde an den Endbenutzer übermittelt und ist bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch erst kürzlich (in den letzten 7 Tagen) verwendet.  | 


## <a name="register-devices-by-using-an-api"></a>Registrieren von Geräten mithilfe einer API

Eine REST-API steht zur Verfügung, die Ihnen größere Flexibilität und Wiederholbarkeit bei häufigen separaten Geräte Registrierungen ermöglicht. Um die API verwenden zu können, bitten Sie Ihre Microsoft Contact um Hilfe, um an einer Vorschau dieser Funktion teilzunehmen.



## <a name="troubleshooting"></a>Problembehandlung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Dieses Gerät konnte nicht registriert werden, da keine Übereinstimmung für den angegebenen Hersteller, das Modell oder die Seriennummer gefunden werden konnte. Bestätigen Sie diese Werte mit Ihrem Gerätelieferanten. |
| Gerät nicht gefunden | Dieses Gerät kann nicht deregistriert werden, da es in Ihrer Organisation nicht vorhanden ist. Es ist keine weitere Aktion erforderlich. |
| Hardware Hash ist ungültig | Der für dieses Gerät angegebene Hardwarehash wurde nicht ordnungsgemäß formatiert. Überprüfen Sie den Hardwarehash, und senden Sie ihn erneut. |
| Gerät bereits registriert | Dieses Gerät ist bereits für Ihre Organisation registriert. Es ist keine weitere Aktion erforderlich. |
| Von einer anderen Organisation beanspruchtes Gerät | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Erkundigen Sie sich bei Ihrem Gerätelieferanten. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Kontaktieren Sie den Support, und geben Sie die Anforderungs-ID an:<requestId> |




