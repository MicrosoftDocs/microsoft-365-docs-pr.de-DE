---
title: Gerätesteuerung für macOS
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt auf dem Mac konfigurieren, um Bedrohungen durch Wechselmedien wie USB-Geräte zu reduzieren.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Mac, Gerät, Steuerelement, USB, Wechseldatenträger, Medien
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5cb819daa11a50ef54c758a6aa696a5fc645029c
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363979"
---
# <a name="device-control-for-macos"></a>Gerätesteuerung für macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a>Anforderungen

Für die Gerätesteuerung für macOS sind die folgenden Voraussetzungen erforderlich:

>[!div class="checklist"]
> - Microsoft Defender für Endpunkt-Berechtigung (kann Testversion sein)
> - Mindestversion des Betriebssystems: macOS 11 oder höher
> - Mindestversion des Produkts: 101.34.20

## <a name="device-control-policy"></a>Gerätesteuerungsrichtlinie

Um die Gerätesteuerung für macOS zu konfigurieren, müssen Sie eine Richtlinie erstellen, die die Einschränkungen beschreibt, die Innerhalb Ihrer Organisation eingerichtet werden sollen.

Die Gerätesteuerungsrichtlinie ist im Konfigurationsprofil enthalten, das zum Konfigurieren aller anderen Produkteinstellungen verwendet wird. Weitere Informationen finden Sie unter [Konfigurationsprofilstruktur.](mac-preferences.md#configuration-profile-structure)

Innerhalb des Konfigurationsprofils wird die Gerätesteuerungsrichtlinie im folgenden Abschnitt definiert:

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | deviceControl |
| **Datentyp** | Wörterbuch (geschachtelte Präferenz) |
| **Comments** | Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten. |

Die Gerätesteuerungsrichtlinie kann für Folgendes verwendet werden:

- [Anpassen des URL-Ziels für Benachrichtigungen, die vom Gerätesteuerelement ausgelöst werden](#customize-url-target-for-notifications-raised-by-device-control)
- [Zulassen oder Blockieren von Wechselmedien](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a>Anpassen des URL-Ziels für Benachrichtigungen, die vom Gerätesteuerelement ausgelöst werden

Wenn die von Ihnen eingerichtete Gerätesteuerungsrichtlinie auf einem Gerät erzwungen wird (z. B. ist der Zugriff auf ein Wechselmediengerät eingeschränkt), wird dem Benutzer eine Benachrichtigung angezeigt.

![Gerätesteuerungsbenachrichtigung](images/mac-device-control-notification.png)

Wenn Endbenutzer auf diese Benachrichtigung klicken, wird eine Webseite im Standardbrowser geöffnet. Sie können die URL konfigurieren, die geöffnet wird, wenn Endbenutzer auf die Benachrichtigung klicken.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | navigationTarget |
| **Datentyp** | Zeichenfolge |
| **Comments** | Wenn nicht definiert, verwendet das Produkt eine Standard-URL, die auf eine generische Seite verweist, auf der die vom Produkt ausgeführte Aktion erläutert wird. |

### <a name="allow-or-block-removable-devices"></a>Zulassen oder Blockieren von Wechselmedien

Der Abschnitt "Wechselmedien" der Gerätesteuerungsrichtlinie wird verwendet, um den Zugriff auf Wechselmedien einzuschränken. 

> [!NOTE]
> Die folgenden Arten von Wechselmedien werden derzeit unterstützt und können in die Richtlinie einbezogen werden: USB-Speichergeräte.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | removableMediaPolicy |
| **Datentyp** | Wörterbuch (geschachtelte Präferenz) |
| **Comments** | Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten. |

Dieser Abschnitt der Richtlinie ist hierarchisch aufgebaut und ermöglicht maximale Flexibilität und deckt eine Vielzahl von Anwendungsfällen ab. Auf der obersten Ebene befinden sich Anbieter, die durch eine Anbieter-ID identifiziert werden. Für jeden Anbieter gibt es Produkte, die durch eine Produkt-ID identifiziert werden. Schließlich gibt es für jedes Produkt Seriennummern, die bestimmte Geräte kennzeichnen.

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

Informationen dazu, wie Sie die Geräte-IDs finden, finden Sie unter Nachschlagen von [Geräte-IDs.](#look-up-device-identifiers)

Die Richtlinie wird vom spezifischsten Eintrag zum allgemeinen ausgewertet. Wenn ein Gerät angeschlossen ist, versucht das Produkt also, die spezifischste Übereinstimmung in der Richtlinie für jedes Wechselmediengerät zu finden und die Berechtigungen auf dieser Ebene anzuwenden. Wenn keine Übereinstimmung vorhanden ist, wird die nächste beste Übereinstimmung angewendet, bis hin zu der auf der obersten Ebene angegebenen Berechtigung. Dies ist die Standardeinstellung, wenn ein Gerät keinem anderen Eintrag in der Richtlinie entspricht.

#### <a name="policy-enforcement-level"></a>Richtlinienerzwingungsstufe

Im Abschnitt "Wechselmedien" gibt es eine Option zum Festlegen der Erzwingungsstufe, die einen der folgenden Werte annehmen kann:

- `audit` – Wenn der Zugriff auf ein Gerät unter dieser Erzwingungsstufe eingeschränkt ist, wird dem Benutzer eine Benachrichtigung angezeigt, das Gerät kann jedoch weiterhin verwendet werden. Diese Erzwingungsstufe kann nützlich sein, um die Effektivität einer Richtlinie zu bewerten.
- `block` – Unter dieser Erzwingungsstufe sind die Vorgänge, die der Benutzer auf dem Gerät ausführen kann, auf die in der Richtlinie definierten Vorgänge beschränkt. Darüber hinaus wird eine Benachrichtigung für den Benutzer ausgelöst. 

> [!NOTE] 
> Standardmäßig ist die Erzwingungsstufe `audit` auf . 

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | enforcementLevel |
| **Datentyp** | String |
| **Mögliche Werte** | Überwachung (Standard) <br/> Block |

#### <a name="default-permission-level"></a>Standardberechtigungsstufe

Auf der obersten Ebene des Abschnitts "Wechselmedien" können Sie die Standardberechtigungsstufe für Geräte konfigurieren, die keiner anderen In der Richtlinie entsprechen.

Diese Einstellung kann wie folgt festgelegt werden:

- `none` – Es können keine Vorgänge auf dem Gerät ausgeführt werden.
- Eine Kombination der folgenden Werte:
    - `read` – Lesevorgänge sind auf dem Gerät zulässig
    - `write` – Schreibvorgänge sind auf dem Gerät zulässig
    - `execute` - Ausführen von Vorgängen auf dem Gerät zulässig

> [!NOTE]
> Wenn `none` die Berechtigungsstufe vorhanden ist, werden alle anderen Berechtigungen ( `read` oder ) `write` `execute` ignoriert.

> [!NOTE]
> Die `execute` Berechtigung bezieht sich nur auf die Ausführung von binären Binärdateien. Es umfasst nicht die Ausführung von Skripts oder anderen Arten von Nutzlasten.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Berechtigung |
| **Datentyp** | Array aus Zeichenfolgen |
| **Mögliche Werte** | keine <br/> Lesen <br/> Schreiben <br/> Ausführen |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a>Einschränken von Wechselmedien nach Hersteller, Produkt und Seriennummer

Wie unter ["Zulassen oder Blockieren von Wechselmedien"](#allow-or-block-removable-devices)beschrieben, können Wechselmedien wie USB-Geräte anhand der Hersteller-ID, der Produkt-ID und der Seriennummer identifiziert werden.

Auf der obersten Ebene der Richtlinie für Wechselmedien können Sie optional detailliertere Einschränkungen auf Herstellerebene definieren. 

Das `vendors` Wörterbuch enthält einen oder mehrere Einträge, wobei jeder Eintrag durch die Anbieter-ID identifiziert wird.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Anbieter |
| **Datentyp** | Wörterbuch (geschachtelte Präferenz) |

Für jeden Anbieter können Sie die gewünschte Berechtigungsstufe für Geräte von diesem Anbieter angeben.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Berechtigung |
| **Datentyp** | Array aus Zeichenfolgen |
| **Mögliche Werte** | Identisch mit [der Standardberechtigungsstufe](#default-permission-level) |

Darüber hinaus können Sie optional den Satz von Produkten angeben, die zu diesem Anbieter gehören, für den detailliertere Berechtigungen definiert sind. Das `products` Wörterbuch enthält einen oder mehrere Einträge, wobei jeder Eintrag durch die Produkt-ID identifiziert wird. 

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Produkte |
| **Datentyp** | Wörterbuch (geschachtelte Präferenz) |

Für jedes Produkt können Sie die gewünschte Berechtigungsstufe für dieses Produkt angeben.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Berechtigung |
| **Datentyp** | Array aus Zeichenfolgen |
| **Mögliche Werte** | Identisch mit [der Standardberechtigungsstufe](#default-permission-level) |

Darüber hinaus können Sie einen optionalen Satz von Seriennummern angeben, für die detailliertere Berechtigungen definiert sind.

Das `serialNumbers` Wörterbuch enthält einen oder mehrere Einträge, wobei jeder Eintrag durch die Seriennummer identifiziert wird.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | serialNumbers |
| **Datentyp** | Wörterbuch (geschachtelte Präferenz) |

Für jede Seriennummer können Sie die gewünschte Berechtigungsstufe angeben.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Berechtigung |
| **Datentyp** | Array aus Zeichenfolgen |
| **Mögliche Werte** | Identisch mit [der Standardberechtigungsstufe](#default-permission-level) |

#### <a name="example-device-control-policy"></a>Beispiel für eine Gerätesteuerungsrichtlinie

Das folgende Beispiel zeigt, wie alle oben genannten Konzepte in einer Gerätesteuerungsrichtlinie kombiniert werden können. Beachten Sie im folgenden Beispiel die hierarchische Natur der Richtlinie für Wechselmedien.

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

Wir haben weitere Beispiele für Gerätesteuerungsrichtlinien in die folgenden Dokumente aufgenommen:

- [Beispiele für Gerätesteuerungsrichtlinien für Intune](mac-device-control-intune.md)
- [Beispiele für Gerätesteuerungsrichtlinien für JAMF](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a>Nachschlagen von Gerätebezeichnern

So suchen Sie die Anbieter-ID, Produkt-ID und Seriennummer eines USB-Geräts:

1. Melden Sie sich bei einem Mac-Gerät an.
1. Schließen Sie das USB-Gerät an, für das Sie die Bezeichner nachschlagen möchten.
1. Wählen Sie im Menü der obersten Ebene von macOS **"Info zu diesem Mac"** aus.

    ![Informationen zu diesem Mac](images/mac-device-control-lookup-1.png)

1. Wählen Sie **"Systembericht" aus.**

    ![Systembericht](images/mac-device-control-lookup-2.png)

1. Wählen Sie in der linken Spalte **USB** aus.

    ![Ansicht aller USB-Geräte](images/mac-device-control-lookup-3.png)

1. Navigieren Sie unter **der USB-Gerätestruktur** zu dem USB-Gerät, das Sie angeschlossen haben.

    ![Details zu einem USB-Gerät](images/mac-device-control-lookup-4.png)

1. Die Anbieter-ID, Produkt-ID und Seriennummer werden angezeigt. Wenn Sie die Anbieter-ID und die Produkt-ID zur Richtlinie für Wechselmedien hinzufügen, müssen Sie den Teil erst nach `0x` hinzufügen. In der folgenden Abbildung ist z. B. die Anbieter-ID `1000` und die Produkt-ID `090c` .

#### <a name="discover-usb-devices-in-your-organization"></a>Ermitteln von USB-Geräten in Ihrer Organisation

Sie können Mount-, Unmount- und Volumeänderungsereignisse von USB-Geräten in der erweiterten Suche in Microsoft Defender für Endpunkt anzeigen. Diese Ereignisse können hilfreich sein, um verdächtige Nutzungsaktivitäten zu identifizieren oder interne Untersuchungen durchzuführen.

```
DeviceEvents 
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a>Bereitstellung von Gerätesteuerungsrichtlinien

Die Gerätesteuerungsrichtlinie muss neben den anderen Produkteinstellungen enthalten sein, wie unter Festlegen der [Einstellungen für Microsoft Defender für Endpunkt unter macOS](mac-preferences.md)beschrieben.

Dieses Profil kann mithilfe der Anweisungen bereitgestellt werden, die in der Bereitstellung des [Konfigurationsprofils](mac-preferences.md#configuration-profile-deployment)aufgeführt sind.

## <a name="troubleshooting-tips"></a>Tipps zur Problembehandlung

Nachdem Sie das Konfigurationsprofil über Intune oder JAMF übertragen haben, können Sie überprüfen, ob es vom Produkt erfolgreich aufgenommen wurde, indem Sie den folgenden Befehl aus dem Terminal ausführen:

```bash
mdatp device-control removable-media policy list
```

Dieser Befehl druckt in der Standardausgabe der Gerätesteuerungsrichtlinie, die das Produkt verwendet. Falls dies gedruckt `Policy is empty` wird, stellen Sie sicher, dass (a) das Konfigurationsprofil tatsächlich von der Verwaltungskonsole an Ihr Gerät übertragen wurde und (b) es sich um eine gültige Gerätesteuerungsrichtlinie handelt, wie in diesem Dokument beschrieben.

Auf einem Gerät, auf dem die Richtlinie erfolgreich bereitgestellt wurde und ein oder mehrere Geräte angeschlossen sind, können Sie den folgenden Befehl ausführen, um alle Geräte und die effektiven Berechtigungen aufzuführen, die ihnen zugewiesen wurden.

```bash
mdatp device-control removable-media devices list
```

Beispielausgabe:

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

Im obigen Beispiel ist nur ein Wechselmediengerät angeschlossen und verfügt `read` über berechtigungen gemäß der `execute` Gerätesteuerungsrichtlinie, die an das Gerät übermittelt wurde.

## <a name="related-topics"></a>Verwandte Themen

- [Beispiele für Gerätesteuerungsrichtlinien für Intune](mac-device-control-intune.md)
- [Beispiele für Gerätesteuerungsrichtlinien für JAMF](mac-device-control-jamf.md)
