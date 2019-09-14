---
title: Schritte für Partner zum Registrieren von Geräten
description: Wie Partner Geräte registrieren können, damit Sie von Microsoft Managed Desktop verwaltet werden können
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 69d9387047cbb14a97f3da1d401b30a97bd7fd90
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982716"
---
# <a name="steps-for-partners-to-register-devices"></a>Schritte für Partner zum Registrieren von Geräten


In diesem Thema werden die Schritte beschrieben, die für Partner zum Registrieren von Geräten befolgt werden müssen. Das Verfahren zum Registrieren von Geräten selbst ist unter [Registrieren von Geräten in Microsoft Managed Desktop selbst](register-devices-self.md)dokumentiert.



## <a name="prepare-for-registration"></a>Vorbereiten der Registrierung 
Bevor Sie die Registrierung für einen Kunden abschließen, müssen Sie zunächst eine Beziehung mit diesen im [Partner Center](https://partner.microsoft.com/dashboard)herstellen. Stellen Sie sicher, dass Sie die **Berechtigungen für die delegierte Verwaltung für Azure Active Directory und Office 365 einschließen**auswählen. Weitere Informationen finden Sie unter [Hilfe zum Partner Center](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer).

Um die Registrierung für Ihren Kunden abzuschließen, erstellen Sie zunächst eine CSV-Datei.

>[!NOTE]
>Für Ihre Bequemlichkeit können Sie eine [Vorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) für diese *Partner Version* der CSV-Datei herunterladen.

Die Datei muss **exakt dieselben Spaltenüberschriften** wie das Beispiel 1 (Hersteller, Modell usw.) enthalten, aber ihre eigenen Daten für die anderen Zeilen. Wenn Sie die Vorlage verwenden, öffnen Sie Sie in einem Textbearbeitungstool wie Notepad, und lassen Sie alle Daten in Zeile 1 allein, und geben Sie nur Daten in Zeilen 2 und darunter ein. 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```


>[!NOTE]
>Dieses Format ist nur für den Partner Prozess. Der Prozess für die Selbstregistrierung ist in [Register Devices in Microsoft Managed Desktop selbst](register-devices-self.md)dokumentiert.

>[!IMPORTANT]
>Diese Werte müssen mit den Hersteller Werten von SMBIOS genau übereinstimmen, einschließlich Groß-/Kleinschreibung und Sonderzeichen. 

- Gerätehersteller (Beispiel: SpiralOrbit) 
- Gerätemodell (Beispiel: ContosoABC)
- Seriennummer des Geräts

## <a name="register-devices-by-using-the-azure-portal"></a>Registrieren von Geräten mithilfe des Azure-Portals

Die Registrierung mithilfe des Azure-Portals ist identisch mit der von Self-Service, außer dass Sie unterschiedlich auf das Portal zugreifen. Führen Sie die folgenden Schritte aus:

1. Wechseln zum [Partner Center](https://partner.microsoft.com/dashboard)
2. Wählen Sie **Kunden**aus.
3. Wählen Sie den Kunden aus, den Sie verwalten möchten.
4. Wählen Sie **Dienstverwaltung**aus.
5. Wählen Sie **InTune**aus.
6. Suchen Sie im oberen Suchfeld des Azure-Portals nach "MMD".
7. Wählen Sie **Geräte**aus.
8. Geben Sie im Feld **Dateiupload**einen Pfad zu der CSV-Datei an, die Sie zuvor erstellt haben.
9. Optional können Sie eine **Auftrags-ID** oder eine **Einkaufs-ID** für eigene Tracking-Zwecke hinzufügen. Für diese Werte gibt es keine Formatanforderungen.
10. Wählen Sie **Geräte registrieren**aus. Das System fügt die Geräte zu ihrer Geräteliste auf dem Blade- **Gerät**hinzu, das als " **Registrierung ausstehend**" gekennzeichnet wird. Die Registrierung dauert in der Regel weniger als 10 Minuten, und wenn das Gerät erfolgreich ist, wird es **für den Benutzer bereit** angezeigt, was darauf wartet, dass ein Endbenutzer mit der Verwendung beginnt.


Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite von **Microsoft Managed Desktop-Devices** überwachen. Mögliche Zustände, die dort gemeldet werden, umfassen:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Überprüfen Sie später erneut. |
| Registrierung fehlgeschlagen | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen erhalten Sie unter [Problembehandlung bei der Geräteregistrierung](register-devices-self.md#troubleshooting-device-registration) . |
| Benutzer einsatzfähig | Die Registrierung wurde erfolgreich ausgeführt, und das Gerät ist jetzt bereit, an den Endbenutzer zugestellt zu werden. Microsoft Managed Desktop führt Sie durch die erstmalige Einrichtung, sodass Sie keine weiteren Vorbereitungen treffen müssen. |
| Aktiv | Das Gerät wurde an den Endbenutzer übermittelt, und Sie haben sich bei Ihrem Mandanten registriert. Dies deutet auch darauf hin, dass das Gerät regelmäßig verwendet wird. |
| Inaktiv | Das Gerät wurde an den Endbenutzer übermittelt, und Sie haben sich bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch vor kurzem nicht verwendet (in den letzten 7 Tagen).  |



## <a name="troubleshooting"></a>Problembehandlung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Dieses Gerät konnte nicht registriert werden, da keine Übereinstimmung für den bereitgestellten Hersteller, das Modell oder die Seriennummer gefunden werden konnte. Bestätigen Sie diese Werte mit Ihrem Gerätelieferanten. |
| Hardware Hash ungültig | Der für dieses Gerät angegebene Hardwarehash wurde nicht ordnungsgemäß formatiert. Überprüfen Sie den Hardwarehash doppelt, und senden Sie dann erneut. |
| Gerät ist bereits registriert | Dieses Gerät ist bereits für Ihre Organisation registriert. Keine weitere Aktion erforderlich. |
| Von einer anderen Organisation beanspruchtes Gerät | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Erkundigen Sie sich bei Ihrem Gerätelieferanten. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Wenden Sie sich<support link>an den Support () und geben Sie die Anforderungs-ID an:<requestId> |
