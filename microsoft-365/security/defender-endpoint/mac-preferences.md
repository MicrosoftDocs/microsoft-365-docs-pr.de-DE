---
title: Festlegen von Einstellungen für Microsoft Defender for Endpoint für Mac
description: Konfigurieren von Microsoft Defender für Endpoint für Mac in Unternehmensorganisationen.
keywords: microsoft, defender, atp, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d2bea469031e2c5932e859fbad7d442ebe4d34ed
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860923"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a>Festlegen von Einstellungen für Microsoft Defender for Endpoint unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt unter Mac OS](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
>Dieser Artikel enthält Anweisungen zum Festlegen von Einstellungen für Microsoft Defender for Endpoint auf macOS in Unternehmensorganisationen. Informationen zum Konfigurieren von Microsoft Defender for Endpoint unter macOS über die Befehlszeilenschnittstelle finden Sie unter [Resources](mac-resources.md#configuring-from-the-command-line).

## <a name="summary"></a>Zusammenfassung

In Unternehmensorganisationen kann Microsoft Defender for Endpoint unter macOS über ein Konfigurationsprofil verwaltet werden, das mithilfe eines von mehreren Verwaltungstools bereitgestellt wird. Einstellungen, die vom Sicherheitsbetriebsteam verwaltet werden, haben Vorrang vor Einstellungen, die lokal auf dem Gerät festgelegt werden. Das Ändern der Einstellungen, die über das Konfigurationsprofil festgelegt werden, erfordert eskalierte Berechtigungen und ist für Benutzer ohne Administratorberechtigungen nicht verfügbar.

Dieser Artikel beschreibt die Struktur des Konfigurationsprofils, enthält ein empfohlenes Profil, das Sie für die ersten Schritte verwenden können, und enthält Anweisungen zum Bereitstellen des Profils.

## <a name="configuration-profile-structure"></a>Konfigurationsprofilstruktur

Das Konfigurationsprofil ist eine *.plist-Datei,* die aus Einträgen besteht, die durch einen Schlüssel identifiziert werden (der den Namen der Einstellung angibt), gefolgt von einem Wert, der von der Art der Einstellung abhängt. Werte können entweder einfach (z. B. ein numerischer Wert) oder komplex sein, z. B. eine geschachtelte Liste von Einstellungen.

>[!CAUTION]
>Das Layout des Konfigurationsprofils hängt von der verwendeten Verwaltungskonsole ab. Die folgenden Abschnitte enthalten Beispiele für Konfigurationsprofile für JAMF und Intune.

Die oberste Ebene des Konfigurationsprofils enthält produktweite Einstellungen und Einträge für Unterbereiche von Microsoft Defender for Endpoint, die in den nächsten Abschnitten ausführlicher erläutert werden.

### <a name="antivirus-engine-preferences"></a>Einstellungen des Antivirusmoduls

Der *Abschnitt antivirusEngine* des Konfigurationsprofils wird verwendet, um die Einstellungen der Antiviruskomponente von Microsoft Defender for Endpoint zu verwalten.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | antivirusEngine |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Kommentare** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

#### <a name="enable--disable-real-time-protection"></a>Aktivieren/Deaktivieren des Echtzeitschutzes

Geben Sie an, ob der Echtzeitschutz aktiviert werden soll, der Dateien beim Zugriff überprüft.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | enableRealTimeProtection |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | true (Standard) <br/> false |

#### <a name="enable--disable-passive-mode"></a>Aktivieren/Deaktivieren des passiven Modus

Geben Sie an, ob das Antivirenmodul im passiven Modus ausgeführt wird. Der passive Modus hat die folgenden Auswirkungen: 
- Echtzeitschutz ist deaktiviert
- Die Überprüfung bei Bedarf ist aktiviert.
- Automatische Bedrohungsbehebung ist deaktiviert
- Sicherheitsintelligenzupdates sind aktiviert
- Statusmenüsymbol ist ausgeblendet

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | passiveMode |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | false (Standard) <br/> true |
| **Kommentare** | Verfügbar in Microsoft Defender for Endpoint, Version 100.67.60 oder höher. |

#### <a name="exclusion-merge-policy"></a>Ausschlusszusammenführungsrichtlinie

Geben Sie die Seriendruckrichtlinie für Ausschlüsse an. Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Ausschlüssen ( ) oder nur vom Administrator definierten `merge` Ausschlüssen ( `admin_only` ) sein. Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Ausschlüsse zu beschränken.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | exclusionsMergePolicy |
| **Datentyp** | String |
| **Mögliche Werte** | merge (Standard) <br/> admin_only |
| **Kommentare** | Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher. |

#### <a name="scan-exclusions"></a>Scannen von Ausschlüssen

Geben Sie Entitäten an, die von der Gescannten ausgeschlossen werden. Ausschlüsse können durch vollständige Pfade, Erweiterungen oder Dateinamen angegeben werden.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Ausschlüsse |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Kommentare** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

##### <a name="type-of-exclusion"></a>Art des Ausschlusses

Geben Sie Inhalte an, die vom Typ ausgeschlossen werden.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | $type |
| **Datentyp** | String |
| **Mögliche Werte** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |

##### <a name="path-to-excluded-content"></a>Pfad zu ausgeschlossenen Inhalten

Geben Sie Inhalte an, die nicht durch den vollständigen Dateipfad gescannt werden.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | path |
| **Datentyp** | String |
| **Mögliche Werte** | gültige Pfade |
| **Kommentare** | Gilt nur, *$type* *ausgeschlossen IstPath* |

##### <a name="path-type-file--directory"></a>Pfadtyp (Datei/Verzeichnis)

Gibt an, ob *die path-Eigenschaft* auf eine Datei oder ein Verzeichnis verweist. 

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | isDirectory |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | false (Standard) <br/> true |
| **Kommentare** | Gilt nur, *$type* *ausgeschlossen IstPath* |

##### <a name="file-extension-excluded-from-the-scan"></a>Dateierweiterung, die von der Überprüfung ausgeschlossen wurde

Geben Sie Inhalte an, die von der Dateierweiterung nicht gescannt werden.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | erweiterung |
| **Datentyp** | String |
| **Mögliche Werte** | Gültige Dateierweiterungen |
| **Kommentare** | Gilt nur, *$type* *ausgeschlossen istFileExtension* |

##### <a name="process-excluded-from-the-scan"></a>Prozess, der von der Überprüfung ausgeschlossen wurde

Geben Sie einen Prozess an, für den alle Dateiaktivitäten von der Überprüfung ausgeschlossen werden. Der Prozess kann entweder durch seinen Namen (z. B. ) oder den vollständigen `cat` Pfad (z. B. ) angegeben werden. `/bin/cat`

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Name |
| **Datentyp** | String |
| **Mögliche Werte** | eine beliebige Zeichenfolge |
| **Kommentare** | Gilt nur, *$type* *ausgeschlossen istFileName* |

#### <a name="allowed-threats"></a>Zulässige Bedrohungen

Geben Sie Bedrohungen nach Namen an, die nicht von Defender for Endpoint für Mac blockiert werden. Diese Bedrohungen können ausgeführt werden.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | allowedThreats |
| **Datentyp** | Array aus Zeichenfolgen |

#### <a name="disallowed-threat-actions"></a>Unzulässige Bedrohungsaktionen

Schränkt die Aktionen ein, die der lokale Benutzer eines Geräts ausführen kann, wenn Bedrohungen erkannt werden. Die in dieser Liste enthaltenen Aktionen werden nicht auf der Benutzeroberfläche angezeigt.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | disallowedThreatActions |
| **Datentyp** | Array aus Zeichenfolgen |
| **Mögliche Werte** | allow (schränkt ein, dass Benutzer Bedrohungen zulassen) <br/> restore (schränkt benutzer das Wiederherstellen von Bedrohungen aus der Quarantäne ein) |
| **Kommentare** | Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher. |

#### <a name="threat-type-settings"></a>Einstellungen für den Bedrohungstyp

Geben Sie an, wie bestimmte Bedrohungstypen von Microsoft Defender for Endpoint unter macOS behandelt werden.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | threatTypeSettings |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Kommentare** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

##### <a name="threat-type"></a>Bedrohungstyp

Geben Sie Bedrohungstypen an.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Schlüssel |
| **Datentyp** | String |
| **Mögliche Werte** | potentially_unwanted_application <br/> archive_bomb |

##### <a name="action-to-take"></a>Zu ergreifende Maßnahme

Geben Sie an, welche Aktion ausgeführt werden soll, wenn eine Bedrohung des im vorherigen Abschnitt angegebenen Typs erkannt wird. Wählen Sie aus den folgenden Optionen aus:

- **Überwachung:** Ihr Gerät ist nicht vor dieser Art von Bedrohung geschützt, aber ein Eintrag über die Bedrohung wird protokolliert.
- **Block**: Ihr Gerät ist vor dieser Art von Bedrohung geschützt, und Sie werden über die Benutzeroberfläche und die Sicherheitskonsole benachrichtigt.
- **Aus**: Ihr Gerät ist nicht vor dieser Art von Bedrohung geschützt, und es wird nichts protokolliert.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Wert |
| **Datentyp** | String |
| **Mögliche Werte** | Überwachung (Standard) <br/> block <br/> off |

#### <a name="threat-type-settings-merge-policy"></a>Richtlinie zum Zusammenführen von Bedrohungstypeinstellungen

Geben Sie die Seriendruckrichtlinie für Bedrohungstypeinstellungen an. Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Einstellungen ( ) oder nur vom Administrator definierten Einstellungen `merge` ( ) `admin_only` sein. Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Einstellungen für verschiedene Bedrohungstypen zu beschränken.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | threatTypeSettingsMergePolicy |
| **Datentyp** | String |
| **Mögliche Werte** | merge (Standard) <br/> admin_only |
| **Kommentare** | Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher. |

#### <a name="antivirus-scan-history-retention-in-days"></a>Aufbewahrung des Antivirusscanverlaufs (in Tagen)

Geben Sie die Anzahl der Tage an, die Ergebnisse im Scanverlauf auf dem Gerät aufbewahrt werden. Alte Scanergebnisse werden aus dem Verlauf entfernt. Alte isolierte Dateien, die ebenfalls vom Datenträger entfernt wurden.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | scanResultsRetentionDays |
| **Datentyp** | String |
| **Mögliche Werte** | 90 (Standard). Zulässige Werte liegen zwischen 1 Tag und 180 Tagen. |
| **Kommentare** | Verfügbar in Microsoft Defender for Endpoint, Version 101.07.23 oder höher. |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Maximale Anzahl von Elementen im Antivirusscanverlauf

Geben Sie die maximale Anzahl von Einträgen an, die im Scanverlauf bleiben sollen. Zu den Einträgen gehören alle in der Vergangenheit durchgeführten Bedarfsscans und alle Antivirenerkennungen.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | scanHistoryMaximumItems |
| **Datentyp** | String |
| **Mögliche Werte** | 10000 (Standard). Zulässige Werte liegen zwischen 5.000 und 15.000 Elementen. |
| **Kommentare** | Verfügbar in Microsoft Defender for Endpoint, Version 101.07.23 oder höher. |

### <a name="cloud-delivered-protection-preferences"></a>Von der Cloud übermittelte Schutzeinstellungen

Konfigurieren Sie die cloudgesteuerten Schutzfunktionen von Microsoft Defender for Endpoint unter macOS.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | cloudService |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Kommentare** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

#### <a name="enable--disable-cloud-delivered-protection"></a>Aktivieren/Deaktivieren des in der Cloud übermittelten Schutzes

Geben Sie an, ob der in der Cloud zugestellte Schutz auf dem Gerät aktiviert werden soll. Um die Sicherheit Ihrer Dienste zu verbessern, wird empfohlen, dieses Feature aktiviert zu halten.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | aktiviert |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | true (Standard) <br/> false |

#### <a name="diagnostic-collection-level"></a>Diagnosesammlungsebene

Diagnosedaten werden verwendet, um Microsoft Defender for Endpoint sicher und auf dem neuesten Stand zu halten, Probleme zu erkennen, zu diagnostizieren und zu beheben sowie Produktverbesserungen vorzunehmen. Diese Einstellung bestimmt die Diagnosestufe, die von Microsoft Defender for Endpoint an Microsoft gesendet wird.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | diagnosticLevel |
| **Datentyp** | String |
| **Mögliche Werte** | optional (Standard) <br/> erforderlich |

#### <a name="enable--disable-automatic-sample-submissions"></a>Aktivieren/Deaktivieren automatischer Beispielübermittlungen

Bestimmt, ob verdächtige Beispiele (die wahrscheinlich Bedrohungen enthalten) an Microsoft gesendet werden. Sie werden aufgefordert, wenn die übermittelte Datei wahrscheinlich personenbezogene Informationen enthält.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | automaticSampleSubmission |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | true (Standard) <br/> false |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Aktivieren/Deaktivieren automatischer Sicherheitsintelligenzupdates

Bestimmt, ob Sicherheitsintelligenzupdates automatisch installiert werden:

|Abschnitt|Wert|
|:---|:---|
| **Key** | automaticDefinitionUpdateEnabled |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | true (Standard) <br/> false |

### <a name="user-interface-preferences"></a>Benutzeroberflächeneinstellungen

Verwalten Sie die Einstellungen für die Benutzeroberfläche von Microsoft Defender for Endpoint unter macOS.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | userInterface |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Kommentare** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

#### <a name="show--hide-status-menu-icon"></a>Symbol für Das Menü "Status anzeigen/ausblenden"

Geben Sie an, ob das Statusmenüsymbol in der oberen rechten Ecke des Bildschirms ein- oder ausgeblendet werden soll.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | hideStatusMenuIcon |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | false (Standard) <br/> true |

#### <a name="show--hide-option-to-send-feedback"></a>Ein-/Ausblenden der Option zum Senden von Feedback

Geben Sie an, ob Benutzer Feedback an Microsoft senden können, indem Sie zu `Help`  >  `Send Feedback` gehen.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | userInitiatedFeedback |
| **Datentyp** | String |
| **Mögliche Werte** | aktiviert (Standard) <br/> deaktiviert |
| **Kommentare** | Verfügbar in Microsoft Defender for Endpoint, Version 101.19.61 oder höher. |

### <a name="endpoint-detection-and-response-preferences"></a>Einstellungen für endpunkterkennung und -reaktion

Verwalten Sie die Einstellungen der Endpunkterkennungs- und -antwortkomponente von Microsoft Defender for Endpoint unter macOS.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | edr |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Kommentare** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

#### <a name="device-tags"></a>Gerätetags

Geben Sie einen Tagnamen und dessen Wert an. 

- Das GROUP-Tag tagt das Gerät mit dem angegebenen Wert. Das Tag wird im Portal unter der Geräteseite angezeigt und kann zum Filtern und Gruppieren von Geräten verwendet werden.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | tags |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Kommentare** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

##### <a name="type-of-tag"></a>Tagtyp

Gibt den Typ des Tags an.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Schlüssel |
| **Datentyp** | String |
| **Mögliche Werte** | `GROUP` |

##### <a name="value-of-tag"></a>Wert des Tags

Gibt den Wert des Tags an.

|Abschnitt|Wert|
|:---|:---|
| **Domäne** | `com.microsoft.wdav` |
| **Key** | Wert |
| **Datentyp** | String |
| **Mögliche Werte** | eine beliebige Zeichenfolge |

> [!IMPORTANT]  
> - Pro Tagtyp kann nur ein Wert festgelegt werden.
> - Der Typ von Tags ist eindeutig und sollte nicht im gleichen Konfigurationsprofil wiederholt werden.

## <a name="recommended-configuration-profile"></a>Empfohlenes Konfigurationsprofil

Für die ersten Schritte empfehlen wir die folgende Konfiguration für Ihr Unternehmen, um alle Von Microsoft Defender for Endpoint-Funktionen zur Nutzung zu nutzen.

Das folgende Konfigurationsprofil (oder im Fall von JAMF eine Eigenschaftenliste, die in das Konfigurationsprofil für benutzerdefinierte Einstellungen hochgeladen werden könnte) wird verwendet:
- Aktivieren des Echtzeitschutzes (Real-Time Protection, RTP)
- Geben Sie an, wie die folgenden Bedrohungstypen behandelt werden:
  - **Potenziell unerwünschte Anwendungen (PUA)** werden blockiert
  - **Archivangriffe** (Datei mit hoher Komprimierungsrate) werden bei Microsoft Defender für Endpunktprotokolle überwacht.
- Aktivieren automatischer Sicherheitsintelligenzupdates
- Aktivieren des in der Cloud übermittelten Schutzes
- Aktivieren der automatischen Beispielübermittlung

### <a name="property-list-for-jamf-configuration-profile"></a>Eigenschaftenliste für das JAMF-Konfigurationsprofil

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Intune-Profil

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>Beispiel für ein vollständiges Konfigurationsprofil

Die folgenden Vorlagen enthalten Einträge für alle in diesem Dokument beschriebenen Einstellungen und können für erweiterte Szenarien verwendet werden, in denen Sie mehr Kontrolle über Microsoft Defender for Endpoint unter macOS wünschen.

### <a name="property-list-for-jamf-configuration-profile"></a>Eigenschaftenliste für das JAMF-Konfigurationsprofil

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Intune-Profil

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a>Eigenschaftenlistenüberprüfung

Die Eigenschaftenliste muss eine gültige *.plist-Datei* sein. Dies kann durch Ausführen von:

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

Wenn die Datei wohlgeformt ist, wird mit dem obigen Befehl der `OK` Exitcode ausgegeben und `0` zurückgegeben. Andernfalls wird ein Fehler angezeigt, der das Problem beschreibt, und der Befehl gibt den Exitcode von `1` zurück.

## <a name="configuration-profile-deployment"></a>Konfigurationsprofilbereitstellung

Nachdem Sie das Konfigurationsprofil für Ihr Unternehmen erstellt haben, können Sie es über die Verwaltungskonsole bereitstellen, die Ihr Unternehmen verwendet. In den folgenden Abschnitten finden Sie Anweisungen zum Bereitstellen dieses Profils mithilfe von JAMF und Intune.

### <a name="jamf-deployment"></a>JAMF-Bereitstellung

Öffnen Sie in der JAMF-Konsole  >  **Computerkonfigurationsprofile,** navigieren Sie zu dem Konfigurationsprofil, das Sie verwenden möchten, und wählen Sie dann **Benutzerdefinierte Einstellungen aus.** Erstellen Sie einen Eintrag `com.microsoft.wdav` mit als Einstellungsdomäne, und laden Sie die zuvor produzierte *.plist* hoch.

>[!CAUTION]
>Sie müssen die richtige Einstellungsdomäne eingeben ( ); andernfalls werden die Einstellungen von `com.microsoft.wdav` Microsoft Defender for Endpoint nicht erkannt.

### <a name="intune-deployment"></a>Intune-Bereitstellung

1. Öffnen **Sie**  >  **Gerätekonfiguration verwalten**. Wählen **Sie Profil** erstellen von  >    >  **Profilen verwalten aus.**

2. Wählen Sie einen Namen für das Profil aus. Ändern **sie Platform=macOS** in **Profile type=Custom**. Wählen Sie Konfigurieren aus.

3. Speichern Sie die .plist, die zuvor als erstellt `com.microsoft.wdav.xml` wurde.

4. Geben `com.microsoft.wdav` Sie als **benutzerdefinierter Konfigurationsprofilname ein.**

5. Öffnen Sie das Konfigurationsprofil, und laden Sie die Datei `com.microsoft.wdav.xml` hoch. (Diese Datei wurde in Schritt 3 erstellt.)

6. Wählen Sie **OK** aus.

7. Wählen **Sie**  >  **Zuordnungen verwalten aus.** Wählen Sie **auf** der Registerkarte Include die Option **Allen Benutzern & Alle Geräte zuweisen aus.**

>[!CAUTION]
>Sie müssen den richtigen namen des benutzerdefinierten Konfigurationsprofils eingeben. Andernfalls werden diese Einstellungen von Microsoft Defender for Endpoint nicht erkannt.

## <a name="resources"></a>Ressourcen

- [Konfigurationsprofilreferenz (Apple-Entwicklerdokumentationen)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
