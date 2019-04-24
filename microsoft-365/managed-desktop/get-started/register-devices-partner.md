---
title: Registrieren von Geräten in Microsoft Managed Desktop für Partner
description: Wie Partner Geräte registrieren können, damit Sie von Microsoft Managed Desktop verwaltet werden können
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 23a2eae6435f5ce234cf6406f2753ec54f675bce
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291669"
---
# <a name="register-devices-in-microsoft-managed-desktop-for-partners"></a>Registrieren von Geräten in Microsoft Managed Desktop für Partner


In diesem Thema werden die Schritte beschrieben, die Partner für das Registrieren von Geräten ausführen müssen. Der Prozess für die Registrierung von Geräten selbst ist in [Registrieren von Geräten in Microsoft Managed Desktop selbst](register-devices-self.md)dokumentiert.



## <a name="prepare-for-registration"></a>Vorbereiten der Registrierung 
Bevor Sie die Registrierung für einen Kunden abschließen, müssen Sie zunächst im [Partner Center](https://partner.microsoft.com/dashboard)eine Beziehung mit diesen Personen herstellen. Weitere Informationen finden Sie unter [Hilfe zum Partner Center](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer).

Um die Registrierung für Ihren Kunden abzuschließen, erstellen Sie zunächst eine CSV-Datei.

>[!NOTE]
>Zur Vereinfachung können Sie eine [Vorlage](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) für diese *Partner Version* der CSV-Datei herunterladen.

Die Datei muss **genau die gleichen Spaltenüberschriften** wie das Beispiel 1 (Hersteller, Modell usw.), aber eigene Daten für die anderen Zeilen aufweisen. Wenn Sie die Vorlage verwenden, öffnen Sie Sie in einem Text Bearbeitungstool wie Editor, und ziehen Sie in Erwägung, alle Daten in Zeile 1 allein zu lassen, und geben Sie nur Daten in den Zeilen 2 und darunter ein. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,
  
  
  ```


>[!NOTE]
>Dieses Format ist nur für den Partner Prozess. Der Prozess der Selbstregistrierung wird unter Registrieren von [Geräten in Microsoft Managed Desktop selbst](register-devices-self.md)dokumentiert.

>[!IMPORTANT]
>Diese Werte müssen genau mit den Hersteller Werten von SMBIOS übereinstimmen. Sie müssen auch *Hardware-Hash* in die erste Zeile (aber keinen Wert in der zweiten Zeile) des nachfolgenden Kommas nach dem Wert der *Seriennummer* in der zweiten Zeile einfügen.

- Gerätehersteller (Beispiel: SpiralOrbit) 
- Gerätemodell (Beispiel: ContosoABC)
- Seriennummer des Geräts

## <a name="register-devices-by-using-the-azure-portal"></a>Registrieren von Geräten mithilfe des Azure-Portals

Die Registrierung über das Azure-Portal ist identisch mit der für Self-Service, mit der Ausnahme, dass Sie auf das Portal unterschiedlich zugreifen. Führen Sie die folgenden Schritte aus:

1. Navigieren zum [Partner Center](https://partner.microsoft.com/dashboard)
2. Wählen Sie **Kunden**aus.
3. Wählen Sie den Kunden aus, den Sie verwalten möchten.
4. Wählen Sie **Dienstverwaltung**aus.
5. Wählen Sie **InTune**aus.
6. Suchen Sie im oberen Suchfeld des Azure-Portals nach "MMD".
7. Wählen Sie **Geräte**aus.
8. Geben Sie im Feld **Dateiupload**einen Pfad zu der zuvor erstellten CSV-Datei an.
9. Optional können Sie eine **Auftrags-ID** oder eine **Einkaufs-ID** für eigene Tracking-Zwecke hinzufügen. Für diese Werte gibt es keine Formatanforderungen.
10. Wählen Sie **Geräte registrieren**aus. Das System fügt die Geräte der Geräteliste auf dem **Blade Devices**hinzu, die als **Registrierung**ausstehend markiert sind. Die Registrierung dauert in der Regel weniger als 10 Minuten, und wenn das Gerät erfolgreich ist, wird es **für den Benutzer bereit** angezeigt, sodass es bereit ist und darauf wartet, dass ein Endbenutzer verwendet wird.


Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite von **Microsoft Managed Desktop-Devices** überwachen. Mögliche Statusberichte:

| Status | Beschreibung |
|---------------|-------------|
| Registrierung ausstehend | Die Registrierung ist noch nicht abgeschlossen. Überprüfen Sie später. |
| Registrierung fehlgeschlagen | Die Registrierung konnte nicht abgeschlossen werden. Weitere Informationen finden Sie unter [Problembehandlung](register-devices-self.md#troubleshooting) . |
| Bereit für Benutzer | Die Registrierung wurde erfolgreich durchgeführt, und das Gerät kann nun an den Endbenutzer übermittelt werden. Microsoft Managed Desktop führt Sie durch die erstmalige Einrichtung, daher müssen Sie keine weiteren Vorbereitungen treffen. |
| Aktiv | Das Gerät wurde an den Endbenutzer übermittelt und ist bei Ihrem Mandanten registriert. Dies bedeutet auch, dass Sie das Gerät regelmäßig verwenden. |
| Inaktiven | Das Gerät wurde an den Endbenutzer übermittelt und ist bei Ihrem Mandanten registriert. Sie haben das Gerät jedoch erst kürzlich (in den letzten 7 Tagen) verwendet.  |

## <a name="register-devices-by-using-an-api"></a>Registrieren von Geräten mithilfe einer API

Die Registrierung über die API ist identisch mit Self-Service, mit der Ausnahme, dass die Hardware-Hash-Eigenschaft der Device-Auflistung optional ist, wie im Abschnitt CSV beschrieben. 

## <a name="troubleshooting"></a>Problembehandlung

| Fehlermeldung | Details |
|---------------|-------------|
| Gerät nicht gefunden | Dieses Gerät konnte nicht registriert werden, da keine Übereinstimmung für den angegebenen Hersteller, das Modell oder die Seriennummer gefunden werden konnte. Bestätigen Sie diese Werte mit Ihrem Gerätelieferanten. |
| Gerät nicht gefunden | Dieses Gerät kann nicht deregistriert werden, da es in Ihrer Organisation nicht vorhanden ist. Es ist keine weitere Aktion erforderlich. |
| Hardware Hash ist ungültig | Der für dieses Gerät angegebene Hardwarehash wurde nicht ordnungsgemäß formatiert. Überprüfen Sie den Hardwarehash, und senden Sie ihn erneut. |
| Gerät bereits registriert | Dieses Gerät ist bereits für Ihre Organisation registriert. Es ist keine weitere Aktion erforderlich. |
| Von einer anderen Organisation beanspruchtes Gerät | Dieses Gerät wurde bereits von einer anderen Organisation beansprucht. Erkundigen Sie sich bei Ihrem Gerätelieferanten. |
| Unerwarteter Fehler | Ihre Anforderung konnte nicht automatisch verarbeitet werden. Kontaktieren Sie den<support link>Support (), und geben Sie die ANFORDERUNGS-ID an:<requestId> |