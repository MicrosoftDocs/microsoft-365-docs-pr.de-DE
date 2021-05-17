---
title: Microsoft Defender for Endpoint Device Control Wechseldatenträgerzugriffssteuerung
description: Ein Walk-Through zu Microsoft Defender for Endpoint
keywords: Wechselmedien
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 46ea74d11f9c54cd1d967058433a74ef4c1ead19
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300176"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint Device Control Wechseldatenträgerzugriffssteuerung

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control Removable Storage Access Control ermöglicht Ihnen die folgende Aufgabe:
- Überwachung, Zulassen oder Verhindern des Lese-, Schreib- oder Ausführungszugriffs auf Wechselmedien mit oder ohne Ausschluss

|Berechtigung |Berechtigung  |
|---------|---------|
|Zugriff    |  Lese-/Schreib-/Ausführungszugriff       |
|Aktionsmodus    |    Überwachung, Zulassen, Verhindern     |
|CSP-Unterstützung   |   Ja      |
|GPO-Unterstützung    |   Ja      |
|Benutzerbasierter Support     |   Ja      |
|Computerbasierte Unterstützung    |    Ja     |

## <a name="prepare-your-endpoints"></a>Vorbereiten der Endpunkte

Bereitstellen der Wechseldatenträgerzugriffssteuerung auf Windows 10-Geräten mit Clientversion **4.18.2103.3 oder höher.**
1. **4.18.2104 oder höher**: Hinzufügen von SerialNumberId, VID_PID, filepath-basierter Gruppenrichtlinienobjektunterstützung

2. **4.18.2105 oder höher**: Hinzufügen von Platzhalterunterstützung für HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, die Kombination bestimmter Benutzer auf einem bestimmten Computer, absetzbare SSD (eine SanDisk Extreme SSD)/USB Attached SCSI (UAS)

:::image type="content" source="images/powershell.png" alt-text="Die PowerShell-Schnittstelle":::

## <a name="policy-properties"></a>Richtlinieneigenschaften

Sie können die folgenden Eigenschaften verwenden, um eine Wechselspeichergruppe zu erstellen:

**Eigenschaftsname: Gruppen-ID**

1. Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Gruppe dar und wird in der Richtlinie verwendet.

**Eigenschaftsname: DescriptorIdList**

1. Beschreibung: Listet die Geräteeigenschaften auf, die Sie in der Gruppe abdecken möchten.
Listet die Geräteeigenschaften auf, die Sie in der Gruppe abdecken möchten.
Weitere Informationen zu jeder Geräteeigenschaft finden Sie **weiter** oben im Abschnitt Geräteeigenschaften.

1. Optionen:
    - Primäre ID
        - RemovableMediaDevices
        - CdRomDevices
    - DeviceId
    - HardwareId
    - InstancePathId
    - FriendlyNameId
    - SerialNumberId
    - VID
    - PID
    - VID_PID
        - 0751_55E0: Übereinstimmung mit diesem genauen VID/PID-Paar
        - _55E0: Übereinstimmen beliebiger Medien mit PID=55E0
        - 0751_: Übereinstimmen beliebiger Medien mit VID=0751
        
**Eigenschaftsname: MatchType** 

1. Beschreibung: Wenn mehrere Geräteeigenschaften in descriptorIDList verwendet werden, definiert MatchType die Beziehung.

1. Optionen:
    - MatchAll: Alle Attribute unter descriptorIdList sind **And-Beziehung;** Wenn der Administrator z. B. DeviceID und InstancePathID für jeden angeschlossenen USB-Speicher einriert, überprüft das System, ob der USB beide Werte erfüllt.

    - MatchAny: Die Attribute unter descriptorIdList lauten **Or-Beziehung;** Wenn der Administrator z. B. DeviceID und InstancePathID für jeden angeschlossenen USB-Speicher einriert, führt das System die Erzwingung aus, solange der USB entweder einen identischen **DeviceID-** oder **InstanceID-Wert** hat.

Im Folgenden finden Sie die Eigenschaften der Zugriffssteuerungsrichtlinie:

**Eigenschaftsname: PolicyRuleId**

1. Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Richtlinie dar und wird in der Berichterstellung und Problembehandlung verwendet.

**Eigenschaftsname: IncludedIdList**

1. Beschreibung: Die Gruppen, auf die die Richtlinie angewendet wird. Wenn mehrere Gruppen hinzugefügt werden, wird die Richtlinie auf alle Medien in allen diesen Gruppen angewendet.

1. Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.

Das folgende Beispiel zeigt die Verwendung von GroupID:

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

**Eigenschaftsname: ExcludedIDList**

1. Beschreibung: Die Gruppen, auf die die Richtlinie nicht angewendet wird.
1. Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.

**Eigenschaftsname: Eintrags-ID**

1. Beschreibung: Ein PolicyRule kann mehrere Einträge haben; Jeder Eintrag mit einer eindeutigen GUID teilt der Gerätesteuerung eine Einschränkung mit.

**Eigenschaftsname: Type**

1. Beschreibung: Definiert die Aktion für die Wechselspeichergruppen in IncludedIDList.
    - Erzwingung: Zulassen oder Verweigern
    - Überwachung: AuditAllowed oder AuditDenied 
1. Optionen:
    - Zulassen
    - Verweigern
    - AuditAllowed: Definiert Benachrichtigung und Ereignis, wenn der Zugriff zulässig ist
    - AuditDenied: Definiert Benachrichtigung und Ereignis, wenn der Zugriff verweigert wird; muss mit dem Eintrag **Verweigern zusammenarbeiten.**

Wenn Konflikttypen für dasselbe Medium verfügbar sind, wird der erste in der Richtlinie vom System angewendet. Ein Beispiel für einen Konflikttyp ist **Allow** und **Deny**.

**Eigenschaftsname: Optionen**

1. Beschreibung: Definiert, ob eine Benachrichtigung angezeigt werden soll oder nicht.

   :::image type="content" source="images/device-status.png" alt-text="Der Bildschirm, auf dem der Status des Geräts angezeigt werden kann":::

1. Optionen: 0-4. Wenn Typ Zulassen oder Verweigern ausgewählt ist:

   - 0: nothing
   - 4: Deaktivieren **Sie AuditAllowed** und **AuditDenied** für diesen Eintrag. Selbst wenn **Block** auftritt und **die Einstellung AuditDenied** konfiguriert ist, zeigt das System keine Benachrichtigung an.

   Wenn Typ **AuditAllowed oder** **AuditDenied** ausgewählt ist:

   - 0: nothing
   - 1: Benachrichtigung anzeigen
   - 2: Send-Ereignis
   - 3: Benachrichtigungs- und Sendeereignis anzeigen

**Eigenschaftsname: AccessMask**

1. Beschreibung: Definiert den Zugriff.

1. Optionen: 1-7:
    - 1: Lesen
    - 2: Schreiben
    - 3: Lese- und Schreibzugriff
    - 4: Ausführen
    - 5: Lesen und Ausführen
    - 6: Schreiben und Ausführen
    - 7: Lesen und Schreiben und Ausführen

## <a name="common-removable-storage-access-control-scenarios"></a>Allgemeine Szenarien für die Speicherzugriffssteuerung für Wechselmedien

Um Sie mit Microsoft Defender for Endpoint Removable Storage Access Control vertraut zu machen, haben wir einige gängige Szenarien für Sie 2013 2013 2013 2013 2014 2013 2013 2013 2013 2013 2013 2014 20

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Szenario 1: Verhindern des Schreib- und Ausführungszugriffs für alle, jedoch bestimmte genehmigte USBs zulassen

1. Erstellen von Gruppen
    1. Gruppe 1: Alle Wechseldatenträger und CD/DVD. Ein Beispiel für einen Wechselspeicher und cd/DVD ist: Gruppe **9b28fae8-72f7-4267-a1a5-685f747a7146** im Beispiel [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Gruppe 2: Genehmigte USBs basierend auf Geräteeigenschaften. Ein Beispiel für diesen Verwendungsfall ist: Instanz-ID – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei ["Approved USBs Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)

    > [!NOTE]
    > Sie müssen im `&` Wert `&amp;` durch ersetzen.

2. Richtlinie erstellen
    1. Richtlinie 1: Blockieren des Schreib- und Ausführungszugriffs, aber Zulassen genehmigter USBs. Ein Beispiel für diesen Verwendungsfall ist: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** im [Beispielszenario 1 Schreib-](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) und Ausführungszugriff blockieren, aber genehmigte USBs .xmlzulassen.
    
    2. Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf zulässige USBs. Ein Beispiel für diesen Use Case ist: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** im [Beispielszenario 1 Überwachung](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) des Schreib- und Ausführungszugriffs auf genehmigte USBs.xml-Datei.

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Szenario 2: Überwachen des Schreib- und Ausführungszugriffs auf alle, aber bestimmte nicht genehmigte USBs blockieren

1. Erstellen von Gruppen
    1. Gruppe 1: Alle Wechseldatenträger und CD/DVD. Ein Beispiel für diesen Fall ist: Gruppe **9b28fae8-72f7-4267-a1a5-685f747a7146** im Beispiel [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Gruppe 2: Nicht genehmigte USBs basierend auf Geräteeigenschaften, z. B. Hersteller-ID/Produkt-ID, Anzeigename – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei Nicht genehmigte [USBs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 

    > [!NOTE]
    > Sie müssen im `&` Wert `&amp;` durch ersetzen.

2. Richtlinie erstellen
    1. Richtlinie 1: Blockieren des Schreib- und Ausführungszugriffs für alle, jedoch für bestimmte nicht genehmigte USBs. Ein Beispiel für diesen Verwendungsfall ist: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** im Beispielszenario 2 Audit Write and Execute access to all but block specific [unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf andere Personen. Ein Beispiel für diesen Verwendungsfall ist: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** im [Beispielszenario 2 Überwachung](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) des Schreib- und Ausführungszugriffs auf others.xmlDatei.

## <a name="deploying-and-managing-policy-via-group-policy"></a>Bereitstellen und Verwalten von Richtlinien über Gruppenrichtlinien

Mit der Funktion Wechselmedienzugriffssteuerung können Sie Richtlinien über Gruppenrichtlinien auf Benutzer oder Geräte oder beides anwenden.

### <a name="licensing"></a>Lizenzierung

Bevor Sie mit der Wechselmedienzugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365-Abonnement bestätigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) Für den Zugriff auf und die Verwendung der Wechselmedienzugriffssteuerung müssen Sie Microsoft 365 E5 verwenden.

### <a name="deploying-policy-via-group-policy"></a>Bereitstellen von Richtlinien über Gruppenrichtlinien

1. Kombinieren Sie alle Gruppen `<Groups>` `</Groups>` innerhalb einer XML-Datei. 

    Die folgende Abbildung veranschaulicht das Beispiel von [Szenario 1: Verhindern](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)des Schreib- und Ausführungszugriffs auf alle, erlaubt jedoch bestimmte genehmigte USBs .
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Der Bildschirm mit den Konfigurationseinstellungen, die bestimmte genehmigte USBs auf Geräten zulassen":::
    
2. Kombinieren Sie alle Regeln in `<PolicyRules>` `</PolicyRules>` einer XML-Datei. 

    Wenn Sie einen bestimmten Benutzer einschränken möchten, verwenden Sie die SID-Eigenschaft in den Eintrag. Wenn in der Richtlinie Eintrag keine SID vorhanden ist, wird der Eintrag auf alle Anmeldeinstanzen für den Computer angewendet.
    
    Die folgende Abbildung veranschaulicht die Verwendung der SID-Eigenschaft und ein Beispiel für [Szenario 1: Verhindern](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)des Schreib- und Ausführungszugriffs auf alle, erlaubt jedoch bestimmte genehmigte USBs .
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Der Bildschirm mit einem Code, der die Verwendung des SID-Eigenschaftsattributs angibt":::

3. Speichern Sie sowohl Regel- als auch Gruppen-XML-Dateien im Netzwerkfreigabeordner, und legen Sie den Pfad des Netzwerkfreigabeordners in die Gruppenrichtlinieneinstellung ein: Computerkonfiguration **-> Administrative Vorlagen -> Windows-Komponenten -> Microsoft Defender Antivirus -> Gerätesteuerung: 'Gerätesteuerungsrichtliniengruppen definieren'** und 'Richtlinienregeln für Gerätesteuerung definieren' .

    - Der Zielcomputer muss auf die Netzwerkfreigabe zugreifen können, damit die Richtlinie vorhanden ist. Sobald die Richtlinie jedoch gelesen wurde, ist die Netzwerkfreigabeverbindung auch nach dem Neustart des Computers nicht mehr erforderlich.

    :::image type="content" source="images/device-control.png" alt-text="Bildschirm &quot;Gerätesteuerung&quot;":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Bereitstellen und Verwalten von Richtlinien über Intune OMA-URI

Mit der Funktion Wechselmedienzugriffssteuerung können Sie Richtlinien über OMA-URI entweder auf Benutzer oder Geräte oder beides anwenden.

### <a name="licensing"></a>Lizenzierung

Bevor Sie mit der Wechselmedienzugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365-Abonnement bestätigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) Für den Zugriff auf und die Verwendung der Wechselmedienzugriffssteuerung müssen Sie über Microsoft 365 E3 verfügen.

### <a name="permission"></a>Berechtigung

Für die Richtlinienbereitstellung in Intune muss das Konto über Berechtigungen zum Erstellen, Bearbeiten, Aktualisieren oder Löschen von Gerätekonfigurationsprofilen verfügen. Sie können benutzerdefinierte Rollen erstellen oder eine der integrierten Rollen mit diesen Berechtigungen verwenden.

- Rolle "Richtlinien- und Profil-Manager"
- Benutzerdefinierte Rolle mit Berechtigungen zum Erstellen/Bearbeiten/Aktualisieren/Lesen/Löschen/Anzeigen von Berichten, die für Gerätekonfigurationsprofile aktiviert sind
- Globaler Administrator

### <a name="deploying-policy-via-oma-uri"></a>Bereitstellen von Richtlinien über OMA-URI

**Microsoft Endpoint Manager admin center ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**

1. Erstellen Sie für jede Gruppe eine OMA-URI-Regel:
    - OMA-URI: 

      /Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData

      Für jeden **Wechselspeicher und eine CD/DVD-Gruppe** im Beispiel muss der Link z. B.:

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData

    - Datentyp: Zeichenfolge (XML-Datei)
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="Die XML-Datei für den DATENTYP STRING":::

2. Erstellen Sie für jede Richtlinie auch einen OMA-URI:

    - OMA-URI: 

      /Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBF68E1%7d/RuleData

      Beispielsweise muss der Link für die **Regel Schreib-** und Ausführungszugriff blockieren, aber genehmigte USBs im Beispiel zulassen: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.

    - Datentyp: Zeichenfolge (XML-Datei)

      :::image type="content" source="images/xml-data-type-string-2.png" alt-text="Anzeigen der XML-Datei für den DATENTYP STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Bereitstellen und Verwalten von Richtlinien mithilfe der Intune-Benutzeroberfläche

Diese Funktion ist noch nicht verfügbar. 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Anzeigen von Daten der Gerätesteuerung für wechselbare Speicherzugriffssteuerung in Microsoft Defender for Endpoint

Das Microsoft 365-Sicherheitsportal zeigt wechselbaren Speicher an, der von der Gerätesteuerung Wechselmedienzugriffssteuerung blockiert wurde. Für den Zugriff auf die Microsoft 365-Sicherheit müssen Sie über das folgende Abonnement verfügen:

- Microsoft 365 für E5-Berichte

```
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

:::image type="content" source="images/block-removable-storage.png" alt-text="Der Bildschirm mit der Blockierung des Wechselspeichers":::
