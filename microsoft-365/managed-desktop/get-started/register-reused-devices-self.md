---
title: Registrieren vorhandener Geräte
description: Wiederverwendete Geräte registrieren, die Sie möglicherweise bereits haben, damit Sie von Microsoft Managed Desktop verwaltet werden können
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2527b18c422d53060398f90b7470db8b4959afa
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982948"
---
# <a name="register-existing-devices-yourself"></a>Registrieren vorhandener Geräte

>[!NOTE]
>In diesem Thema werden die Schritte beschrieben, mit denen Sie bereits verwendete Geräte wieder verwenden und in Microsoft Managed Desktop registrieren können. Wenn Sie mit brandneuen Geräten arbeiten, befolgen Sie stattdessen die Schritte unter [Registrieren neuer Geräte in Microsoft Managed Desktop](register-devices-self.md) .

Der Prozess für Partner ist in [Schritten für Partner zum Registrieren von Geräten](register-devices-partner.md)dokumentiert.

Microsoft Managed Desktop kann mit brandneuen Geräten verwendet werden, oder Sie können Geräte wieder verwenden, die Sie möglicherweise bereits haben (Dies erfordert ein erneutes Abbild). Sie können Geräte mithilfe von Microsoft Managed Desktop im Azure-Portal registrieren.

## <a name="prepare-to-register-existing-devices"></a>Vorbereiten der Registrierung vorhandener Geräte


Führen Sie die folgenden Schritte aus, um vorhandene Geräte zu registrieren:

1. [Rufen Sie den Hardwarehash für jedes Gerät ab.](#obtain-the-hardware-hash)
2. [Zusammenführen der Hash Daten](#merge-hash-data)
3. [Registrieren Sie die Geräte in Microsoft Managed Desktop](#register-devices).
4. [Stellen Sie sicher, dass das Bild korrekt ist.](#check-the-image)
5. [Verteilen des Geräts](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Abrufen des Hardwarehash

Microsoft Managed Desktop identifiziert jedes Gerät eindeutig, indem es auf seinen Hardwarehash verweist. Sie haben vier Optionen, um diese Informationen von Geräten abzurufen, die Sie bereits verwenden:

- Fragen Sie Ihren OEM-Lieferanten nach der Autopilot-Registrierungsdatei, die die Hardware-Hashes enthält.
- Erstellen Sie einen benutzerdefinierten Bericht in [Configuration Manager](#configuration-manager).
- Führen Sie ein Windows PowerShell-Skript aus, indem Sie entweder [Active Directory](#active-directory-powershell-script-method) oder [manuell](#manual-powershell-script-method) auf jedem Gerät verwenden und die Ergebnisse in einer Datei sammeln.
- Starten Sie jedes Gerät, aber schließen Sie nicht die Windows Setup-Umgebung ab – und [sammeln Sie die Hashes auf einem wechselbaren Flashlaufwerk](#flash-drive-method).

#### <a name="configuration-manager"></a>Configuration Manager

Sie können den System Center Configuration Manager verwenden, um die Hardware Hashes von vorhandenen Geräten zu erfassen, die Sie bei Microsoft Managed Desktop registrieren möchten.

> [!IMPORTANT]
> Für alle Geräte, für die Sie diese Informationen abrufen möchten, muss Windows 10, Version 1703 oder höher, installiert sein. Sie benötigen auch ein Gerät, bei dem es sich um einen Configuration Manager-Client handelt, der mit dem aktuellen Zweigstellenstandort von System Center verbunden ist Sie benötigen auch die Reporting Points-Standort System Rolle, die in Ihrer Umgebung mit aktivierter SQL Server Reporting Services eingerichtet wurde. 

Wenn Sie alle diese Voraussetzungen erfüllt haben, können Sie die Informationen mit den folgenden Schritten erfassen:

1. Wählen Sie in der Configuration Manager-Konsole **Überwachung**aus. 
2. Erweitern Sie im Bereich Überwachung den Knoten **Berichterstellung**, und wählen Sie dann **Berichte**aus. 
3. Wählen Sie auf der Registerkarte **Start** im Abschnitt **Erstellen** die Option **Bericht erstellen** aus, um den Assistenten zum Erstellen von Berichten zu öffnen. 
4. Legen Sie auf der Seite **Informationen** die folgenden Einstellungen fest: 
    - **Name:** Geben Sie einen Namen für den Bericht an. 
    - **Beschreibung:** Geben Sie eine Beschreibung für den Bericht an. 
    - **Server:** Zeigt den Namen des Berichtsservers an, auf dem Sie diesen Bericht erstellen. 
    - **Pfad:** Wählen Sie **Durchsuchen** aus, um einen Ordner anzugeben, in dem der Bericht gespeichert werden soll. 
5. Wählen Sie **Weiter** aus. 
6. Überprüfen Sie auf der Seite **Zusammenfassung** die Einstellungen. Wählen Sie **Previous** aus, um die Einstellungen zu ändern, oder wählen Sie **weiter** aus, um den Bericht in Configuration Manager zu erstellen. 
7. Wählen Sie auf der Seite **Fertigstellung** die Option **Schließen** aus, um den Assistenten zu beenden und den Berichts- **Generator** zu öffnen, um die Berichtseinstellungen einzugeben. Geben Sie Ihr Benutzerkonto und Ihr Kennwort ein, wenn Sie dazu aufgefordert werden, und wählen Sie dann **OK aus.** Wenn der Berichts-Generator nicht auf dem Gerät installiert ist, werden Sie aufgefordert, ihn zu installieren. Wählen Sie ausführen aus, **um den Berichts-Generator zu installieren**, der zum Ändern und Erstellen von Berichten erforderlich ist. 


Geben Sie **im Microsoft Berichts-Generator**die SQL-Anweisung für den Bericht an, und führen Sie die folgenden Schritte aus:

1. Wählen Sie im linken Bereich Datasets aus, und **Klicken Sie dann**mit der rechten Maustaste, um **Dataset hinzuzufügen**.
2. Wechseln Sie zur Registerkarte **Abfrage** , und geben Sie den Namen als *DataSet0*ein. 
3. Wählen Sie **Verwenden eines in meinem Bericht eingebetteten Datasets**; Der Berichts-Generator wird geöffnet.
4. Wählen Sie im **Berichts-Generator**die Option **Datenquelle:** aus. Wählen Sie die Standarddatenquelle aus, die mit "Autogen" beginnen soll. 
5. Wählen Sie **als Text den gewünschten Abfragetyp**aus, und geben Sie dann diese Abfrage ein:

```

SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp  
       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid


```
5. Navigieren Sie zur Registerkarte **Feld** , wehre Werte für **Feldname** und **Feld Quelle** sollten bereits aufgefüllt werden. Wenn dies nicht der Fall ist, wählen Sie **Hinzufügen**aus, und wählen Sie dann **Abfragefeld**aus. Geben Sie den **Namen des Felds** und die **Feld Quelle**ein.
6. Wiederholen Sie diesen Vorgang für jeden der folgenden Werte: 
    - Hersteller 
    - Modell 
    - Serial_Number 
    - HardwareHash
7. Wählen Sie **OK** aus.

**Definieren Sie als nächstes die Berichtsanzeige, und erstellen Sie den Bericht,** indem Sie die folgenden Schritte ausführen:

1. **Tabelle oder Matrix**auswählen; ein neuer Assistent wird geöffnet.
2. Wählen Sie unter **Dataset auswählen** **die Option vorhandenes Dataset in diesem Bericht oder ein freigegebenes DataSet**auswählen aus.  
3. Wählen Sie **DataSet0** (Standardeinstellung) aus, und wählen Sie dann **weiter**aus.
4. Ziehen Sie **Hersteller**, **Modell**und **Seriennummer** in das Feld **Zeilengruppen** . Ziehen Sie **HardwareHash** in das Feld **Werte** , und wählen Sie dann **weiter**aus.
5. Deaktivieren Sie die Kontrollkästchen für Teil **Ergebnisse anzeigen und Gesamtergebnisse** und **Gruppen erweitern/reduzieren**. Wählen Sie **Weiter** aus.
6. Wählen Sie **Fertig stellen** aus.
7. Wählen Sie **Ausführen** aus, um den Bericht auszuführen. Stellen Sie sicher, dass der Bericht die erwarteten Informationen bereitstellt. Wählen Sie bei Bedarf **Design** aus, um zur Entwurfsansicht zurückzukehren, um den Bericht zu ändern.
8. Wählen Sie **Speichern** aus, um den Bericht auf dem Berichtsserver zu speichern. Sie können den neuen Bericht im Überwachungs Arbeitsbereich im Knoten Berichte ausführen. 

**Exportieren Sie den Bericht schließlich, und verwenden Sie ihn zum Registrieren von Geräten** , indem Sie die folgenden Schritte ausführen. (Sie sollten nur die Schritte 1 und 2 dieses Abschnitts befolgen, wenn Sie nach den vorherigen Schritten weggelaufen sind.):

1. Wählen Sie in der Configuration Manager-Konsole **Überwachung**aus.
2. Erweitern Sie unter **Überwachung**die Option **Berichterstellung**, und wählen Sie dann **Berichte**aus.
3. Suchen Sie den Bericht mit dem Namen, den Sie zuvor erstellt haben.
4. Klicken Sie mit der rechten Maustaste auf diesen Bericht, und wählen Sie **Ausführen**aus.
5. Wählen Sie im daraufhin geöffneten Dialogfeld **Export** aus, und wählen Sie dann **als CSV speichern**aus.
6. In dieser Version des Berichts werden Hashwerte von allen Windows 10-Geräten extrahiert, mit denen Configuration Manager kommuniziert. Sie müssen die Ergebnisse nur auf die Gerätefiltern, die Sie bei Microsoft Managed Desktop registrieren möchten.


> [!IMPORTANT]
> Die Abfrage in Configuration Manager lässt keine Leerzeichen in exportierten Spaltennamen zu; Deshalb haben die Schritte Sie "Serial_Number" und "HardwareHash" eingegeben. Nachdem Sie nun die exportierte CSV-Datei haben, müssen Sie die Berichtskopfzeilen bearbeiten, um die *Seriennummer* und den *Hardware Hash* zu lesen, bevor Sie mit der Geräteregistrierung fortfahren.

Nun können Sie [mithilfe des Azure-Portals mit dem Registrieren von Geräten](#register-devices-by-using-the-azure-portal)fortfahren.


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell-Skriptmethode

In einer Active Directory Umgebung können Sie das `Get-MMDRegistrationInfo` PowerShell-Cmdlet verwenden, um die Informationen von Geräten in Active Directory Gruppen mithilfe von WinRM Remote zu erfassen. Sie können auch das `Get-AD Computer` Cmdlet verwenden und gefilterte Ergebnisse für bestimmte Hardwaremodell Namen abrufen, die im Katalog enthalten sind. Bestätigen Sie dazu zunächst diese Voraussetzungen, und fahren Sie mit den folgenden Schritten fort:

- WinRM ist aktiviert.
- Die zu registrierenden Geräte sind im Netzwerk aktiv (Sie sind nicht getrennt oder ausgeschaltet).
- Stellen Sie sicher, dass Sie über einen Domänenanmelde Parameter verfügen, der die Berechtigung hat, Remote auf den Geräten auszuführen.
- Stellen Sie sicher, dass der Windows-Firewall Zugriff auf WMI zulässt. Führen Sie dazu die folgenden Schritte aus:
    1. Öffnen Sie die **Windows Defender-Firewall** -Systemsteuerung, und wählen Sie **app oder Feature über die Windows Defender-Firewall zulassen**aus.
    2. Suchen Sie in der Liste nach **Windows-Verwaltungsinstrumentation (WMI)** , aktivieren Sie für **Privat und öffentlich**, und wählen Sie dann **OK**aus.

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2.  Führen Sie *eines* der folgenden Skripts aus:
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. Greifen Sie auf alle Verzeichnisse zu, in denen Einträge für die Geräte vorhanden sein können. Entfernen Sie Einträge für jedes Gerät aus *allen* Verzeichnissen, einschließlich Windows Server Active Directory-Domänendienste und Azure Active Directory. Beachten Sie, dass diese Entfernung einige Stunden dauern kann, um den Vorgang vollständig zu verarbeiten.
4. Access Management Services, bei denen Einträge für die Geräte vorhanden sein können. Entfernen Sie Einträge für jedes Gerät aus *allen* Verwaltungsdiensten, einschließlich System Center Configuration Manger, Microsoft InTune und Windows Autopilot. Beachten Sie, dass diese Entfernung einige Stunden dauern kann, um den Vorgang vollständig zu verarbeiten.

Jetzt können Sie mit dem [Registrieren von Geräten](#register-devices)fortfahren.

#### <a name="manual-powershell-script-method"></a>Manuelle PowerShell-Skriptmethode

1.  Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
2.  Ausführen`Install-Script -Name Get-MMDRegistrationInfo`
3.  Ausführen`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
4. [Führen Sie die Hash Daten zusammen.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash Drive-Methode

1. Legen Sie auf einem anderen Gerät als dem, das Sie gerade registrieren, ein USB-Laufwerk ein.
2. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.
3. Ausführen`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Aktivieren Sie das Gerät, das Sie registrieren, aber *beginnen Sie nicht mit der Setup-Umgebung*. Wenn Sie das Setupprogramm versehentlich gestartet haben, müssen Sie das Gerät zurücksetzen oder neu abbilden.
5. Legen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT + F10.
6. Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten, `cd <pathToUsb>`und führen Sie dann aus.
7. Ausführen`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Ausführen`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. Entfernen Sie das USB-Laufwerk, und fahren Sie dann das Gerät herunter, indem Sie`shutdown -s -t 0`
10. [Führen Sie die Hash Daten zusammen.](#merge-hash-data)

>[!IMPORTANT]
>Schalten Sie das Gerät, das Sie erneut registrieren, erst wieder ein, wenn Sie die Registrierung dafür abgeschlossen haben. 



### <a name="merge-hash-data"></a>Zusammenführen von Hash Daten

Wenn Sie die Hardwarehash Daten nach den manuellen PowerShell-oder Flash Drive-Methoden gesammelt haben, müssen Sie nun die Daten in den CSV-Dateien in einer einzigen Datei zusammenfassen, um die Registrierung abzuschließen. Hier ist ein Beispiel für PowerShell-Skripts, um dies zu vereinfachen:

`Get-ChildItem -Filter *.csv |Select-Object -expandproperty FullName | Import-Csv |ConvertTo-Csv -NoTypeInformation | %{$_.Replace('"','')}| Out-File -Append .\joinedcsv\aggregatedDevices.csv`

Nachdem die Hashdaten in einer CSV-Datei zusammengeführt wurden, können Sie nun mit [dem Registrieren der Geräte](#register-devices)fortfahren.

### <a name="register-devices"></a>Registrieren von Geräten

Die CSV-Datei muss sich in einem bestimmten Format für die Registrierung befinden. Wenn Sie die Daten in den vorherigen Schritten selbst gesammelt haben, sollte die Datei bereits im richtigen Format vorhanden sein. Wenn Sie die Datei von einem Lieferanten beziehen, müssen Sie das Format möglicherweise anpassen.

>[!NOTE]
>Für Ihre Bequemlichkeit können Sie eine [Vorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) für diese CSV-Datei herunterladen.

Die Datei muss **exakt dieselben Spaltenüberschriften** wie das Beispiel 1 (Hersteller, Modell usw.) enthalten, aber ihre eigenen Daten für die anderen Zeilen. Wenn Sie die Vorlage verwenden, öffnen Sie Sie in einem Textbearbeitungstool wie Notepad, und lassen Sie alle Daten in Zeile 1 allein, und geben Sie nur Daten in Zeilen 2 und darunter ein. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Wenn Sie vergessen, die Beispieldaten zu ändern, tritt bei der Registrierung ein Fehler auf.

#### <a name="register-devices-by-using-the-azure-portal"></a>Registrieren von Geräten mithilfe des Azure-Portals

Wählen Sie im linken Navigationsbereich **Geräte** aus dem Microsoft Managed Desktop [Azure-Portal](https://aka.ms/mmdportal)aus. Select **+ Register Devices**; das Einfliegen wird geöffnet:

[![Einfliegen nach Auswahl von Register Geräten](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


[//]: # (Leider ist dies nicht der Fall. Wir können diese Notiz entfernen – aber jetzt so lange, bis wir eine Möglichkeit haben, darüber zu chatten.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Führen Sie die folgenden Schritte aus:

1. Geben Sie im Feld **Dateiupload**einen Pfad zu der CSV-Datei an, die Sie zuvor erstellt haben.
2. Optional können Sie eine **Auftrags-ID** oder eine **Einkaufs-ID** für eigene Tracking-Zwecke hinzufügen. Für diese Werte gibt es keine Formatanforderungen.
3. Wählen Sie **Geräte registrieren**aus. Das System fügt die Geräte zu ihrer Geräteliste auf dem Blade- **Gerät**hinzu, das als " **Registrierung ausstehend**" gekennzeichnet wird. Die Registrierung dauert in der Regel weniger als 10 Minuten, und wenn das Gerät erfolgreich ist, wird es **für den Benutzer bereit** angezeigt, was darauf wartet, dass ein Endbenutzer mit der Verwendung beginnt.


Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite von **Microsoft Managed Desktop-Devices** überwachen. Mögliche Zustände, die dort gemeldet werden, umfassen:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Überprüfen Sie später erneut. |
| Registrierung fehlgeschlagen | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen erhalten Sie unter [Problembehandlung bei der Geräteregistrierung](#troubleshooting-device-registration) . |
| Benutzer einsatzfähig | Die Registrierung wurde erfolgreich ausgeführt, und das Gerät ist jetzt bereit, an den Endbenutzer zugestellt zu werden. Microsoft Managed Desktop führt Sie durch die erstmalige Einrichtung, sodass Sie keine weiteren Vorbereitungen treffen müssen. |
| Aktiv | Das Gerät wurde an den Endbenutzer übermittelt, und Sie haben sich bei Ihrem Mandanten registriert. Dies deutet auch darauf hin, dass das Gerät regelmäßig verwendet wird. |
| Inaktiv | Das Gerät wurde an den Endbenutzer übermittelt, und Sie haben sich bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch vor kurzem nicht verwendet (in den letzten 7 Tagen).  | 

#### <a name="troubleshooting-device-registration"></a>Problembehandlung bei der Geräteregistrierung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Dieses Gerät konnte nicht registriert werden, da keine Übereinstimmung für den bereitgestellten Hersteller, das Modell oder die Seriennummer gefunden werden konnte. Bestätigen Sie diese Werte mit Ihrem Gerätelieferanten. |
| Hardware Hash ungültig | Der für dieses Gerät angegebene Hardwarehash wurde nicht ordnungsgemäß formatiert. Überprüfen Sie den Hardwarehash doppelt, und senden Sie dann erneut. |
| Gerät ist bereits registriert | Dieses Gerät ist bereits für Ihre Organisation registriert. Keine weitere Aktion erforderlich. |
| Von einer anderen Organisation beanspruchtes Gerät | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Erkundigen Sie sich bei Ihrem Gerätelieferanten. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Kontaktieren Sie den Support, und geben Sie die Anforderungs-ID an:<requestId> |

### <a name="check-the-image"></a>Überprüfen des Bilds

Wenn Ihr Gerät von einem Microsoft Managed Desktop Partner-Anbieter stammt, sollte das Bild korrekt sein.

Sie können das Bild auch auf eigene Faust anwenden, wenn Sie es vorziehen. Um zu beginnen, wenden Sie sich an den Microsoft-Mitarbeiter, mit dem Sie zusammenarbeiten, und Sie werden den Speicherort und die Schritte zum Anwenden des Abbilds erhalten.

### <a name="deliver-the-device"></a>Verteilen des Geräts

> [!IMPORTANT]
> Bevor Sie das Gerät an Ihren Benutzer übergeben, müssen Sie sicherstellen, dass Sie die [entsprechenden Lizenzen](../get-ready/prerequisites.md) für diesen Benutzer erworben und angewendet haben.

Wenn alle Lizenzen angewendet werden, können Sie [Ihre Benutzer zur Verwendung von Geräten verwenden](get-started-devices.md), und dann kann Ihr Benutzer das Gerät starten und die Windows Setup-Umgebung durchlaufen.









