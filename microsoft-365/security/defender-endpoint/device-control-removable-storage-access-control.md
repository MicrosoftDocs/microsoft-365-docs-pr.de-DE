---
title: Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung
description: Eine exemplarische Vorgehensweise zu Microsoft Defender für Endpunkt
keywords: Wechselmedien
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8b32ab5162e0022d9500f7ddba2fe5bbca1017e7
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229575"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung ermöglicht Ihnen die folgende Aufgabe:
- Überwachen, Zulassen oder Verhindern des Lese-, Schreib- oder Ausführungszugriffs auf Wechselmedien mit oder ohne Ausschluss

|Privileg |Berechtigung  |
|---------|---------|
|Zugriff    |  Lese-/Schreib-/Ausführungszugriff       |
|Aktionsmodus    |    Überwachen, Zulassen, Verhindern     |
|CSP-Unterstützung   |   Ja      |
|GPO-Unterstützung    |   Ja      |
|Benutzerbasierter Support     |   Ja      |
|Computerbasierter Support    |    Ja     |

## <a name="prepare-your-endpoints"></a>Vorbereiten der Endpunkte

Bereitstellen von Wechselmedien Storage Zugriffssteuerung auf Windows 10 Geräten mit Antischadsoftware-Clientversion **4.18.2103.3 oder höher.**

- **4.18.2104 oder höher:** Hinzufügen von SerialNumberId, VID_PID, dateipfadbasierter GPO-Unterstützung, ComputerSid

- **4.18.2105 oder höher:** Hinzufügen von Platzhalterunterstützung für HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, die Kombination aus einem bestimmten Benutzer auf einem bestimmten Computer, entfernender SSD (sanDisk Extreme SSD)/USB Attached SCSI (UAS)-Unterstützung

:::image type="content" source="images/powershell.png" alt-text="Die PowerShell-Schnittstelle":::

> [!NOTE]
> Keine der Windows-Sicherheit Komponenten aktiv sein muss, können Sie wechselbare Storage Zugriffssteuerung unabhängig von Windows-Sicherheit Status ausführen.

## <a name="policy-properties"></a>Richtlinieneigenschaften

Sie können die folgenden Eigenschaften verwenden, um eine Wechselmediengruppe zu erstellen:

**Eigenschaftenname: Gruppen-ID**

1. Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Gruppe dar und wird in der Richtlinie verwendet.

**Eigenschaftenname: DescriptorIdList**

1. Beschreibung: Auflisten der Geräteeigenschaften, die Sie in der Gruppe abdecken möchten.
Listet die Geräteeigenschaften auf, die Sie in der Gruppe abdecken möchten.
Weitere Informationen zu jeder Geräteeigenschaft finden Sie weiter oben im Abschnitt **"Geräteeigenschaften".**

1. Optionen:

    - Primäre ID
        - RemovableMediaDevices
        - CdRomDevices
    - Deviceid
    - HardwareId
    - InstancePathId: InstancePathId ist eine Zeichenfolge, die das Gerät im System eindeutig identifiziert, z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0. Die Zahl am Ende (z. **B.&0)** stellt den verfügbaren Steckplatz dar und kann sich von Gerät zu Gerät ändern. Um optimale Ergebnisse zu erzielen, verwenden Sie am Ende einen Platzhalter. Beispiel: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*
    - FriendlyNameId
    - SerialNumberId
    - Vid
    - Pid
    - VID_PID
        - 0751_55E0: Übereinstimmung mit diesem genauen VID/PID-Paar
        - _55E0: Abgleichen von Medien mit PID=55E0
        - 0751_: Alle Medien mit VID=0751 abgleichen
        
**Eigenschaftenname: MatchType** 

1. Beschreibung: Wenn mehrere Geräteeigenschaften in der DescriptorIDList verwendet werden, definiert MatchType die Beziehung.

1. Optionen:

    - MatchAll: Alle Attribute unter der DescriptorIdList sind **"And"-Beziehung;** Wenn der Administrator beispielsweise DeviceID und InstancePathID platziert, überprüft das System für jeden angeschlossenen USB-Stick, ob der USB beide Werte erfüllt.
    - MatchAny: Die Attribute unter "DescriptorIdList" sind **"Or".** Wenn der Administrator beispielsweise DeviceID und InstancePathID platziert, führt das System für jeden angeschlossenen USB-Stick die Erzwingung aus, solange der USB-Stick entweder über einen identischen **DeviceID-** oder **InstanceID-Wert** verfügt.

Es folgen die Eigenschaften der Zugriffssteuerungsrichtlinie:

**Eigenschaftenname: PolicyRuleId**

1. Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Richtlinie dar und wird in der Berichterstellung und Problembehandlung verwendet.

**Eigenschaftenname: IncludedIdList**

2. Beschreibung: Die Gruppen, auf die die Richtlinie angewendet wird. Wenn mehrere Gruppen hinzugefügt werden, wird die Richtlinie auf alle Medien in allen diesen Gruppen angewendet.

3. Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.

Das folgende Beispiel zeigt die Verwendung von GroupID:

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

**Eigenschaftenname: ExcludedIDList**

Beschreibung: Die Gruppen, auf die die Richtlinie nicht angewendet wird.

Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.

**Eigenschaftenname: Eintrags-ID**

1. Beschreibung: One PolicyRule kann mehrere Einträge haben; Jeder Eintrag mit einer eindeutigen GUID teilt der Gerätesteuerung eine Einschränkung mit.

**Eigenschaftenname: Typ**

1. Beschreibung: Definiert die Aktion für die Wechselmediengruppen in IncludedIDList.
    - Erzwingung: Zulassen oder Verweigern
    - Audit: AuditAllowed oder AuditDenied 

2. Optionen:

    - Zulassen
    - Verweigern
    - AuditAllowed: Definiert Benachrichtigung und Ereignis, wenn der Zugriff zulässig ist
    - AuditDenied: Definiert Benachrichtigung und Ereignis, wenn der Zugriff verweigert wird; muss mit **der Verweigerungseingabe zusammenarbeiten.**

Wenn es Konflikttypen für dieselben Medien gibt, wendet das System den ersten in der Richtlinie an. Ein Beispiel für einen Konflikttyp ist **Allow** and **Deny**.

**Eigenschaftenname: Sid**

Beschreibung: Definiert, ob diese Richtlinie auf bestimmte Benutzer oder Benutzergruppen angewendet wird; Ein Eintrag kann maximal eine Sid haben, und ein Eintrag ohne Sid bedeutet, dass die Richtlinie auf dem Computer angewendet wird.

**Eigenschaftenname: ComputerSid**

Beschreibung: Definiert, ob diese Richtlinie auf bestimmte Computer oder Computergruppen angewendet wird; Ein Eintrag kann maximal eine ComputerSid haben, und ein Eintrag ohne ComputerSid bedeutet, dass die Richtlinie auf dem Computer angewendet wird. Wenn Sie einen Eintrag auf einen bestimmten Benutzer und einen bestimmten Computer anwenden möchten, fügen Sie sid und computerSid demselben Eintrag hinzu.

**Eigenschaftenname: Optionen**

Beschreibung: Definiert, ob eine Benachrichtigung angezeigt werden soll.

   :::image type="content" source="images/device-status.png" alt-text="Der Bildschirm, auf dem der Status des Geräts angezeigt werden kann":::

Optionen: 0-4. Wenn "Zulassen" oder "Verweigern" ausgewählt ist:

   - 0: nothing
   - 4: Deaktivieren Sie **"AuditAllowed"** und **"AuditDenied"** für diesen Eintrag. Selbst wenn **"Blockieren"** erfolgt und die **"AuditDenied"-Einstellung** konfiguriert ist, zeigt das System keine Benachrichtigung an.

   Wenn **"AuditAllowed"** oder **"AuditDenied"** ausgewählt ist:

   - 0: nothing
   - 1: Benachrichtigung anzeigen
   - 2: Send-Ereignis
   - 3: Benachrichtigungs- und Sendeereignis anzeigen

**Eigenschaftenname: AccessMask**

Beschreibung: Definiert den Zugriff.

Optionen 1 bis 7:
  - 1: Lesen
  - 2: Schreiben
  - 3: Lesen und Schreiben
  - 4: Ausführen
  - 5: Lesen und Ausführen
  - 6: Schreiben und Ausführen
  - 7: Lesen und Schreiben und Ausführen

## <a name="common-removable-storage-access-control-scenarios"></a>Allgemeine Szenarien für die Zugriffssteuerung für wechselbare Storage

Um Sie mit Microsoft Defender für Endpunkt-Wechselmedien Storage Zugriffssteuerung vertraut zu machen, haben wir einige häufige Szenarien für Sie zusammengestellt.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs, aber zulassen

1. Erstellen von Gruppen

    1. Gruppe 1: Wechselmedien und CD/DVD. Ein Beispiel für einen Wechselmedien und eine CD/DVD ist: Gruppe **9b28fae8-72f7-4267-a1a5-685f747a7146** in der Beispieldatei ["Any Removable Storage" und "CD-DVD Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)
    
    2. Gruppe 2: Genehmigte USBs basierend auf Geräteeigenschaften. Ein Beispiel für diesen Anwendungsfall ist: Instanz-ID – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei [für genehmigte USBs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)

    > [!NOTE]
    > Sie müssen `&` `&amp;` im Wert ersetzen.

2. Richtlinie erstellen

    1. Richtlinie 1: Schreib- und Ausführungszugriff blockieren, aber genehmigte USBs zulassen. Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf zulässige USBs. Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** im [Beispielszenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Szenario 2: Überwachen des Schreib- und Ausführungszugriffs auf alle nicht genehmigten USBs außer Blockieren bestimmter nicht genehmigter USBs

1. Erstellen von Gruppen

    1. Gruppe 1: Wechselmedien und CD/DVD. Ein Beispiel für diesen Anwendungsfall ist: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Gruppe 2: Nicht genehmigte USBs basierend auf Geräteeigenschaften, z. B. Anbieter-ID/Produkt-ID, Anzeigename – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei "Nicht genehmigte [USBs Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 

    > [!NOTE]
    > Sie müssen `&` `&amp;` im Wert ersetzen.

2. Richtlinie erstellen

    1. Richtlinie 1: Schreib- und Ausführungszugriff auf alle nicht genehmigten USBs blockieren. Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** im [Beispielszenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf andere Personen. Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** im [Beispielszenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

## <a name="deploying-and-managing-policy-via-group-policy"></a>Bereitstellen und Verwalten von Richtlinien über Gruppenrichtlinien

Mit dem Feature für die Zugriffssteuerung für Wechselmedien Storage können Sie Richtlinien über Gruppenrichtlinien entweder auf Benutzer oder Geräte oder auf beides anwenden.

### <a name="licensing"></a>Lizenzierung

Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365 Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)bestätigen. Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und sie zu verwenden, müssen Sie über Microsoft 365 E3 oder Microsoft 365 E5 verfügen.

### <a name="deploying-policy-via-group-policy"></a>Bereitstellen von Richtlinien über Gruppenrichtlinien

1. Kombinieren Sie alle Darin enthaltenen Gruppen `<Groups>` `</Groups>` in einer XML-Datei. 

    Die folgende Abbildung veranschaulicht das Beispiel von [Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)außer zulassen.
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Der Bildschirm mit den Konfigurationseinstellungen, die bestimmte genehmigte USBs auf Geräten zulassen":::
    
2. Kombinieren Sie alle darin enthaltenen Regeln `<PolicyRules>` `</PolicyRules>` in einer XML-Datei. 

    Wenn Sie einen bestimmten Benutzer einschränken möchten, verwenden Sie die SID-Eigenschaft im Eintrag. Wenn der Richtlinieneintrag keine SID enthält, wird der Eintrag auf alle Anmeldeinstanzen für den Computer angewendet.
    
    Die folgende Abbildung veranschaulicht die Verwendung der SID-Eigenschaft und ein Beispiel für [Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)außer zulassen.
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Der Bildschirm mit einem Code, der die Verwendung des SID-Eigenschaftsattributs angibt":::

3. Speichern Sie sowohl Regel- als auch Gruppen-XML-Dateien im Netzwerkfreigabeordner, und fügen Sie den Pfad des Netzwerkfreigabeordners in die Gruppenrichtlinieneinstellung ein: **Computerkonfiguration - > Administrative Vorlagen -> Windows Komponenten -> Microsoft Defender Antivirus -> Gerätesteuerung: "Gerätesteuerungsrichtliniengruppen definieren" und "Gerätesteuerungsrichtlinienregeln definieren".**

    - Der Zielcomputer muss auf die Netzwerkfreigabe zugreifen können, damit die Richtlinie vorhanden ist. Nachdem die Richtlinie gelesen wurde, ist die Netzwerkfreigabeverbindung jedoch auch nach dem Computerneustart nicht mehr erforderlich.

    :::image type="content" source="images/device-control.png" alt-text="Der Bildschirm des Gerätesteuerelements":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Bereitstellen und Verwalten von Richtlinien über Intune OMA-URI

Mit dem Feature für die Zugriffssteuerung für wechselbare Storage können Sie Richtlinien über OMA-URI entweder auf Benutzer oder Geräte oder auf beides anwenden.

### <a name="licensing"></a>Lizenzierung

Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365 Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)bestätigen. Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und sie zu verwenden, müssen Sie über Microsoft 365 E3 oder Microsoft 365 E5 verfügen.

### <a name="permission"></a>Berechtigung

Für die Richtlinienbereitstellung in Intune muss das Konto über Berechtigungen zum Erstellen, Bearbeiten, Aktualisieren oder Löschen von Gerätekonfigurationsprofilen verfügen. Sie können benutzerdefinierte Rollen erstellen oder eine der integrierten Rollen mit diesen Berechtigungen verwenden.

- Rolle "Richtlinien- und Profil-Manager"
- Benutzerdefinierte Rolle mit aktivierten Berechtigungen zum Erstellen/Bearbeiten/Aktualisieren/Lesen/Löschen/Anzeigen von Berichten für Gerätekonfigurationsprofile
- Globaler Administrator

### <a name="deploying-policy-via-oma-uri"></a>Bereitstellen von Richtlinien über OMA-URI

**Microsoft Endpoint Manager Admin Center ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**

1. Erstellen Sie für jede Gruppe eine OMA-URI-Regel:
    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData

      For example, for **any removable storage and CD/DVD** group in the sample, the link must be:

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData

    - Datentyp: Zeichenfolge (XML-Datei)
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="Die XML-Datei für den DATENTYP STRING":::

2. Erstellen Sie für jede Richtlinie auch einen OMA-URI:

    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData

      For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.

    - Datentyp: Zeichenfolge (XML-Datei)

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Anzeigen der XML-Datei für den DATENTYP STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Bereitstellen und Verwalten von Richtlinien mithilfe der Intune-Benutzeroberfläche

Diese Funktion (im Microsoft Endpoint Manager Admin Center ( https://endpoint.microsoft.com/) > Geräte > Konfigurationsprofile > Profil > Plattform erstellen: Windows 10 und höher & Profil: Gerätesteuerung) ist noch nicht verfügbar. 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Anzeigen von Wechseldaten von Gerätesteuerungen Storage Zugriffssteuerungsdaten in Microsoft Defender für Endpunkt

Das Microsoft 365-Sicherheitsportal zeigt Wechselmedien an, die von der Gerätesteuerung (Removable Storage Access Control) blockiert werden. Um auf die Microsoft 365 Sicherheit zugreifen zu können, müssen Sie über das folgende Abonnement verfügen:

- Microsoft 365 für E5-Berichte

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Der Bildschirm, der die Blockierung des Wechselspeichers darstellt":::

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen
**Was ist die Beschränkung für Wechselmedien für die maximale Anzahl von USBs?**

Wir haben eine USB-Gruppe mit 100.000 Medien – bis zu 7 MB Größe – überprüft. Die Richtlinie funktioniert sowohl in Intune als auch im Gruppenrichtlinienobjekt ohne Leistungsprobleme.

**Warum funktioniert die Richtlinie nicht?**

Der häufigste Grund ist, dass keine erforderliche [Antischadsoftware-Clientversion](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)vorhanden ist.

Ein weiterer Grund kann sein, dass die XML-Datei nicht richtig formatiert ist, z. B. nicht die richtige Markdownformatierung für das Zeichen "&" in der XML-Datei verwendet wird, oder dass der Texteditor am Anfang der Dateien eine Bytereihenfolgemarke (Byte Order Mark, BOM) 0xEF 0xBB 0xBF hinzugibt, was dazu führt, dass die XML-Analyse nicht funktioniert. Eine einfache Lösung besteht darin, die [Beispieldatei](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (wählen Sie **"Raw"** und dann **"Speichern unter")** herunterzuladen und dann zu aktualisieren.

Wenn ein Wert vorhanden ist und die Richtlinie über die Gruppenrichtlinie verwaltet wird, überprüfen Sie, ob das Clientgerät auf den RICHTLINIEN-XML-Pfad zugreifen kann.

**Wie kann ich wissen, welcher Computer die veraltete Clientversion für Antischadsoftware in der Organisation verwendet?**

Sie können die folgende Abfrage verwenden, um die Clientversion für Antischadsoftware im Microsoft 365 Sicherheitsportal abzurufen:
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```

