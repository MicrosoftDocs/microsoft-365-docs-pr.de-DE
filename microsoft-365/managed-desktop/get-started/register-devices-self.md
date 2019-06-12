---
title: Selbst registrieren von Geräten in Microsoft Managed Desktop
description: Geräte selbst registrieren, damit Sie von Microsoft Managed Desktop verwaltet werden können
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1e61cfc7fd1d6d597efbfa2480155e06a3d3eb7
ms.sourcegitcommit: d6fcd57a0689abbe4ab47489034f52e327f4e5f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857298"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a>Registrieren von Geräten in Microsoft Managed Desktop

>[!NOTE]
>In diesem Thema werden die Schritte beschrieben, mit denen Sie Geräte selbst registrieren können. Der Prozess für Partner ist unter [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md)dokumentiert.

Microsoft Managed Desktop kann mit brandneuen Geräten verwendet werden, oder Sie können Geräte wieder verwenden, die Sie möglicherweise bereits haben (Dies erfordert ein erneutes Abbild). Sie können Geräte mithilfe von Microsoft Managed Desktop im Azure-Portal registrieren oder mithilfe einer API Flexibilität erzielen.

## <a name="prepare-to-register-devices"></a>Vorbereiten der Registrierung von Geräten

Wenn Sie die Geräte, die Sie verwenden möchten, noch nicht erhalten haben, überprüfen Sie [Microsoft Managed Desktop-Geräte](../service-description/device-list.md) , und arbeiten Sie mit einem Geräte Partner zusammen, um unterstützte Geräte zu beschaffen.

Unabhängig davon, ob Sie mit vollständig neuen Geräten arbeiten oder vorhandene wieder verwenden, um Sie bei Microsoft Managed Desktop zu registrieren, müssen Sie eine durch **trennzeichengetrennte CSV-Datei**vorbereiten. Diese Datei sollte die folgenden Informationen für jedes Gerät enthalten:

>[!NOTE]
>Dieses Format ist nur für Self-Service-Registrierungen. Die Format Partner sollten in [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md)dokumentiert werden.

Diese Werte werden für Anzeigezwecke verwendet und müssen nicht genau mit den Eigenschaften des Geräts übereinstimmen.
- Gerätehersteller (Beispiel: SpiralOrbit) 
- Gerätemodell (Beispiel: ContosoABC)
- Seriennummer des Geräts

Der Hardwarehash muss eine exakte Übereinstimmung aufweisen.
- Hardware Hash

Um den Hardwarehash zu erhalten, können Sie Hilfe von Ihrem OEM oder Partner anfordern oder die folgenden Schritte für jedes Gerät durchführen:

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2.  Ausführen`Install-Script -Name Get-MMDRegistrationInfo`
3.  Ausführen`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`


Alternativ können Sie diese Schritte auf einem brandneuen Gerät befolgen (bevor Sie die OOBE zum ersten Mal durchgehen):

1. Legen Sie auf einem anderen Gerät ein USB-Laufwerk ein.
2. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
3. Ausführen`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Aktivieren Sie das Ziel Gerät, starten Sie jedoch nicht die Setup-Umgebung. Wenn Sie das Setupprogramm versehentlich gestartet haben, müssen Sie das Gerät zurücksetzen oder neu abbilden.
5. Legen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT + F10.
6. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten, `cd <pathToUsb>`und führen Sie dann aus.
7. Ausführen`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Ausführen`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
3. Entfernen Sie das USB-Laufwerk, und fahren Sie dann das Gerät herunter, indem Sie`shutdown -s -t 0`

>[!IMPORTANT]
>Schalten Sie das Zielgerät erst wieder ein, wenn Sie die Registrierung für dieses Gerät abgeschlossen haben. 

>[!NOTE]
>Für Ihre Bequemlichkeit können Sie eine [Vorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) für diese CSV-Datei herunterladen.

Die Datei muss **exakt dieselben Spaltenüberschriften** wie das Beispiel 1 (Hersteller, Modell usw.) enthalten, aber ihre eigenen Daten für die anderen Zeilen. Wenn Sie die Vorlage verwenden, öffnen Sie Sie in einem Textbearbeitungstool wie Notepad, und lassen Sie alle Daten in Zeile 1 allein, und geben Sie nur Daten in Zeilen 2 und darunter ein. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Wenn Sie vergessen, die Beispieldaten zu ändern, tritt bei der Registrierung ein Fehler auf.   


## <a name="register-devices-by-using-the-azure-portal"></a>Registrieren von Geräten mithilfe des Azure-Portals

Wählen Sie im linken Navigationsbereich **Geräte** aus dem Microsoft Managed Desktop [Azure-Portal](https://aka.ms/mmdportal)aus. Select **+ Register Devices**; das Einfliegen wird geöffnet:

[![Einfliegen nach Auswahl von Register Geräten](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


[//]: # (Leider ist dies nicht der Fall. Wir können diese Notiz entfernen – aber jetzt so lange, bis wir eine Möglichkeit haben, darüber zu chatten.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Führen Sie die folgenden Schritte aus:

1. Geben Sie im Feld **Dateiupload**einen Pfad zu der CSV-Datei an, die Sie zuvor erstellt haben.
2. Optional können Sie eine **Auftrags-ID** oder eine **Einkaufs-ID** für eigene Tracking-Zwecke hinzufügen. Für diese Werte gibt es keine Formatanforderungen.
3. Wählen Sie **Geräte registrieren**aus. Das System fügt die Geräte zu ihrer Geräteliste auf dem Blade- **Gerät**hinzu, das als " **Registrierung**Ausstehend" gekennzeichnet wird. Die Registrierung dauert in der Regel weniger als 10 Minuten, und wenn das Gerät erfolgreich ist, wird es **für den Benutzer bereit** angezeigt, was darauf wartet, dass ein Endbenutzer mit der Verwendung beginnt.


Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite von **Microsoft Managed Desktop-Devices** überwachen. Mögliche Zustände, die dort gemeldet werden, umfassen:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Überprüfen Sie später erneut. |
| Registrierung fehlgeschlagen | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen erhalten Sie unter [Problembehandlung](register-devices-self.md#troubleshooting) . |
| Benutzer einsatzfähig | Die Registrierung wurde erfolgreich ausgeführt, und das Gerät ist jetzt bereit, an den Endbenutzer zugestellt zu werden. Microsoft Managed Desktop führt Sie durch die erstmalige Einrichtung, sodass Sie keine weiteren Vorbereitungen treffen müssen. |
| Aktiv | Das Gerät wurde an den Endbenutzer übermittelt, und Sie haben sich bei Ihrem Mandanten registriert. Dies deutet auch darauf hin, dass das Gerät regelmäßig verwendet wird. |
| Inaktiv | Das Gerät wurde an den Endbenutzer übermittelt, und Sie haben sich bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch vor kurzem nicht verwendet (in den letzten 7 Tagen).  | 


## <a name="register-devices-by-using-an-api"></a>Registrieren von Geräten mithilfe einer API

Eine Rest-API steht Ihnen zur Verfügung, um Ihnen größere Flexibilität und Wiederholbarkeit bei häufigen separaten Geräte Registrierungen zu ermöglichen. Um die API verwenden zu können, bitten Sie Ihren Microsoft-Kontakt um Hilfe, um an einer Vorschau dieser Funktion teilzunehmen.



## <a name="troubleshooting"></a>Problembehandlung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Dieses Gerät konnte nicht registriert werden, da keine Übereinstimmung für den bereitgestellten Hersteller, das Modell oder die Seriennummer gefunden werden konnte. Bestätigen Sie diese Werte mit Ihrem Gerätelieferanten. |
| Gerät nicht gefunden | Dieses Gerät konnte nicht registriert werden, da es in Ihrer Organisation nicht vorhanden ist. Keine weitere Aktion erforderlich. |
| Hardware Hash ungültig | Der für dieses Gerät angegebene Hardwarehash wurde nicht ordnungsgemäß formatiert. Überprüfen Sie den Hardwarehash doppelt, und senden Sie dann erneut. |
| Gerät ist bereits registriert | Dieses Gerät ist bereits für Ihre Organisation registriert. Keine weitere Aktion erforderlich. |
| Von einer anderen Organisation beanspruchtes Gerät | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Erkundigen Sie sich bei Ihrem Gerätelieferanten. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Kontaktieren Sie den Support, und geben Sie die Anforderungs-ID an:<requestId> |




