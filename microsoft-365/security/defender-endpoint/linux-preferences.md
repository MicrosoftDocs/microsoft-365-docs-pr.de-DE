---
title: Festlegen von Einstellungen für Microsoft Defender ATP für Linux
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender ATP für Linux in Unternehmen konfiguriert wird.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: ed28d3b5b7bafaea2d72b7a8c45f66bf69033bc2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187793"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a>Festlegen von Einstellungen für Microsoft Defender for Endpoint für Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
>Dieses Thema enthält Anweisungen zum Festlegen von Einstellungen für Defender for Endpoint für Linux in Unternehmensumgebungen. Wenn Sie das Produkt auf einem Gerät über die Befehlszeile konfigurieren möchten, lesen Sie [Ressourcen](linux-resources.md#configure-from-the-command-line).

In Unternehmensumgebungen kann Defender for Endpoint für Linux über ein Konfigurationsprofil verwaltet werden. Dieses Profil wird über das Verwaltungstool Ihrer Wahl bereitgestellt. Vom Unternehmen verwaltete Einstellungen haben Vorrang vor den einstellungen, die lokal auf dem Gerät festgelegt werden. Anders ausgedrückt: Benutzer in Ihrem Unternehmen können einstellungen, die über dieses Konfigurationsprofil festgelegt sind, nicht ändern.

In diesem Artikel werden die Struktur dieses Profils (einschließlich eines empfohlenen Profils, das Sie für die ersten Schritte verwenden können) und Anweisungen zum Bereitstellen des Profils beschrieben.

## <a name="configuration-profile-structure"></a>Konfigurationsprofilstruktur

Das Konfigurationsprofil ist eine JSON-Datei, die aus Einträgen besteht, die durch einen Schlüssel identifiziert werden (der den Namen der Einstellung angibt), gefolgt von einem Wert, der von der Art der Einstellung abhängt. Werte können einfach sein, z. B. ein numerischer Wert oder komplex, z. B. eine geschachtelte Liste von Einstellungen.

In der Regel würden Sie ein Konfigurationsverwaltungstool verwenden, um eine Datei mit dem Namen am ```mdatp_managed.json``` Speicherort zu ```/etc/opt/microsoft/mdatp/managed/``` pushen.

Die oberste Ebene des Konfigurationsprofils enthält produktweite Einstellungen und Einträge für Unterbereiche des Produkts, die in den nächsten Abschnitten ausführlicher erläutert werden.

### <a name="antivirus-engine-preferences"></a>Einstellungen des Antivirusmoduls

Der *Abschnitt antivirusEngine* des Konfigurationsprofils wird zum Verwalten der Einstellungen der Antiviruskomponente des Produkts verwendet.

|||
|:---|:---|
| **Schlüssel** | antivirusEngine |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Comments** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

#### <a name="enable--disable-real-time-protection"></a>Aktivieren/Deaktivieren des Echtzeitschutzes

Bestimmt, ob der Echtzeitschutz (Scandateien, wie auf sie zugegriffen wird) aktiviert ist oder nicht.

|||
|:---|:---|
| **Schlüssel** | enableRealTimeProtection |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | true (Standard) <br/> false |

#### <a name="enable--disable-passive-mode"></a>Aktivieren/Deaktivieren des passiven Modus

Bestimmt, ob das Antivirenmodul im passiven Modus ausgeführt wird oder nicht. Im passiven Modus:
- Der Echtzeitschutz ist deaktiviert.
- Die Überprüfung bei Bedarf ist aktiviert.
- Die automatische Bedrohungsbehebung ist deaktiviert.
- Sicherheitsintelligenzupdates sind aktiviert.
- Das Symbol für das Statusmenü ist ausgeblendet.

|||
|:---|:---|
| **Schlüssel** | passiveMode |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | false (Standard) <br/> true |
| **Comments** | Verfügbar in Defender for Endpoint, Version 100.67.60 oder höher. |

#### <a name="exclusion-merge-policy"></a>Ausschlusszusammenführungsrichtlinie

Gibt die Seriendruckrichtlinie für Ausschlüsse an. Es kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Ausschlüssen ( ) oder nur vom Administrator definierten `merge` Ausschlüssen ( ) sein. `admin_only` Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Ausschlüsse zu beschränken.

|||
|:---|:---|
| **Schlüssel** | exclusionsMergePolicy |
| **Datentyp** | String |
| **Mögliche Werte** | merge (Standard) <br/> admin_only |
| **Comments** | Verfügbar in Defender for Endpoint, Version 100.83.73 oder höher. |

#### <a name="scan-exclusions"></a>Scannen von Ausschlüssen

Entitäten, die von der Überprüfung ausgeschlossen wurden. Ausschlüsse können durch vollständige Pfade, Erweiterungen oder Dateinamen angegeben werden.

|||
|:---|:---|
| **Schlüssel** | Ausschlüsse |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Comments** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

**Art des Ausschlusses**

Gibt den Typ des Inhalts an, der von der Überprüfung ausgeschlossen wurde.

|||
|:---|:---|
| **Schlüssel** | $type |
| **Datentyp** | String |
| **Mögliche Werte** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |

**Pfad zu ausgeschlossenen Inhalten**

Wird verwendet, um Inhalte nach vollständigem Dateipfad von der Überprüfung auszuschließen.

|||
|:---|:---|
| **Schlüssel** | path |
| **Datentyp** | String |
| **Mögliche Werte** | gültige Pfade |
| **Comments** | Gilt nur, *$type* *ausgeschlossen IstPath* |

**Pfadtyp (Datei/Verzeichnis)**

Gibt an, ob *die path-Eigenschaft* auf eine Datei oder ein Verzeichnis verweist. 

|||
|:---|:---|
| **Schlüssel** | isDirectory |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | false (Standard) <br/> true |
| **Comments** | Gilt nur, *$type* *ausgeschlossen IstPath* |

**Dateierweiterung, die von der Überprüfung ausgeschlossen wurde**

Wird verwendet, um Inhalte von der Überprüfung nach Dateierweiterung auszuschließen.

|||
|:---|:---|
| **Schlüssel** | erweiterung |
| **Datentyp** | String |
| **Mögliche Werte** | Gültige Dateierweiterungen |
| **Comments** | Gilt nur, *$type* *ausgeschlossen istFileExtension* |

**Prozess, der von der Überprüfung ausgeschlossen wurde**

Gibt einen Prozess an, für den alle Dateiaktivitäten von der Überprüfung ausgeschlossen werden. Der Prozess kann entweder durch seinen Namen (z. B. ) oder den `cat` vollständigen Pfad (z. B. ) angegeben werden. `/bin/cat`

|||
|:---|:---|
| **Schlüssel** | Name |
| **Datentyp** | String |
| **Mögliche Werte** | eine beliebige Zeichenfolge |
| **Comments** | Gilt nur, *$type* *ausgeschlossen istFileName* |

#### <a name="allowed-threats"></a>Zulässige Bedrohungen

Liste der Bedrohungen (die durch ihren Namen identifiziert werden), die nicht vom Produkt blockiert werden und stattdessen ausgeführt werden dürfen.

|||
|:---|:---|
| **Schlüssel** | allowedThreats |
| **Datentyp** | Array aus Zeichenfolgen |

#### <a name="disallowed-threat-actions"></a>Unzulässige Bedrohungsaktionen

Schränkt die Aktionen ein, die der lokale Benutzer eines Geräts ausführen kann, wenn Bedrohungen erkannt werden. Die in dieser Liste enthaltenen Aktionen werden nicht auf der Benutzeroberfläche angezeigt.

|||
|:---|:---|
| **Schlüssel** | disallowedThreatActions |
| **Datentyp** | Array aus Zeichenfolgen |
| **Mögliche Werte** | allow (schränkt ein, dass Benutzer Bedrohungen zulassen) <br/> restore (schränkt benutzer das Wiederherstellen von Bedrohungen aus der Quarantäne ein) |
| **Comments** | Verfügbar in Defender for Endpoint, Version 100.83.73 oder höher. |

#### <a name="threat-type-settings"></a>Einstellungen für den Bedrohungstyp

Die *ThreatTypeSettings-Einstellung* im Antivirusmodul wird verwendet, um zu steuern, wie bestimmte Bedrohungstypen vom Produkt behandelt werden.

|||
|:---|:---|
| **Schlüssel** | threatTypeSettings |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Comments** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

**Bedrohungstyp**

Typ der Bedrohung, für die das Verhalten konfiguriert ist.

|||
|:---|:---|
| **Schlüssel** | Schlüssel |
| **Datentyp** | String |
| **Mögliche Werte** | potentially_unwanted_application <br/> archive_bomb |

**Zu ergreifende Maßnahme**

Maßnahmen, die ausgeführt werden müssen, wenn eine Bedrohung des im vorherigen Abschnitt angegebenen Typs angezeigt wird. Dies kann:

- **Überwachung**: Das Gerät ist nicht vor dieser Art von Bedrohung geschützt, aber ein Eintrag über die Bedrohung wird protokolliert.
- **Block**: Das Gerät ist vor dieser Art von Bedrohung geschützt, und Sie werden in der Sicherheitskonsole benachrichtigt.
- **Aus**: Das Gerät ist nicht vor dieser Art von Bedrohung geschützt, und es wird nichts protokolliert.

|||
|:---|:---|
| **Schlüssel** | Wert |
| **Datentyp** | String |
| **Mögliche Werte** | Überwachung (Standard) <br/> block <br/> off |

#### <a name="threat-type-settings-merge-policy"></a>Richtlinie zum Zusammenführen von Bedrohungstypeinstellungen

Gibt die Seriendruckrichtlinie für Bedrohungstypeinstellungen an. Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Einstellungen ( ) oder nur vom Administrator definierten Einstellungen `merge` ( ) `admin_only` sein. Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Einstellungen für verschiedene Bedrohungstypen zu beschränken.

|||
|:---|:---|
| **Schlüssel** | threatTypeSettingsMergePolicy |
| **Datentyp** | String |
| **Mögliche Werte** | merge (Standard) <br/> admin_only |
| **Comments** | Verfügbar in Defender for Endpoint, Version 100.83.73 oder höher. |

#### <a name="antivirus-scan-history-retention-in-days"></a>Aufbewahrung des Antivirusscanverlaufs (in Tagen)

Geben Sie die Anzahl der Tage an, die Ergebnisse im Scanverlauf auf dem Gerät aufbewahrt werden. Alte Scanergebnisse werden aus dem Verlauf entfernt. Alte isolierte Dateien, die ebenfalls vom Datenträger entfernt wurden.

|||
|:---|:---|
| **Schlüssel** | scanResultsRetentionDays |
| **Datentyp** | String |
| **Mögliche Werte** | 90 (Standard). Zulässige Werte liegen zwischen 1 Tag und 180 Tagen. |
| **Comments** | Verfügbar in Defender for Endpoint, Version 101.04.76 oder höher. |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Maximale Anzahl von Elementen im Antivirusscanverlauf

Geben Sie die maximale Anzahl von Einträgen an, die im Scanverlauf bleiben sollen. Zu den Einträgen gehören alle in der Vergangenheit durchgeführten Bedarfsscans und alle Antivirenerkennungen.

|||
|:---|:---|
| **Schlüssel** | scanHistoryMaximumItems |
| **Datentyp** | String |
| **Mögliche Werte** | 10000 (Standard). Zulässige Werte liegen zwischen 5.000 und 15.000 Elementen. |
| **Comments** | Verfügbar in Defender for Endpoint, Version 101.04.76 oder höher. |

### <a name="cloud-delivered-protection-preferences"></a>Von der Cloud übermittelte Schutzeinstellungen

Der *cloudService-Eintrag* im Konfigurationsprofil wird verwendet, um das cloudgesteuerte Schutzfeature des Produkts zu konfigurieren.

|||
|:---|:---|
| **Schlüssel** | cloudService |
| **Datentyp** | Wörterbuch (geschachtelte Einstellung) |
| **Comments** | Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten. |

#### <a name="enable--disable-cloud-delivered-protection"></a>Aktivieren/Deaktivieren des von der Cloud übermittelten Schutzes

Bestimmt, ob der in der Cloud zugestellte Schutz auf dem Gerät aktiviert ist oder nicht. Um die Sicherheit Ihrer Dienste zu verbessern, wird empfohlen, dieses Feature aktiviert zu halten.

|||
|:---|:---|
| **Schlüssel** | aktiviert |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | true (Standard) <br/> false |

#### <a name="diagnostic-collection-level"></a>Diagnosesammlungsebene

Diagnosedaten werden verwendet, um Defender for Endpoint sicher und auf dem neuesten Stand zu halten, Probleme zu erkennen, zu diagnostizieren und zu beheben sowie Produktverbesserungen vorzunehmen. Diese Einstellung bestimmt die Diagnosestufe, die vom Produkt an Microsoft gesendet wird.

|||
|:---|:---|
| **Schlüssel** | diagnosticLevel |
| **Datentyp** | String |
| **Mögliche Werte** | optional (Standard) <br/> erforderlich |

#### <a name="enable--disable-automatic-sample-submissions"></a>Aktivieren/Deaktivieren automatischer Beispielübermittlungen

Bestimmt, ob verdächtige Beispiele (die wahrscheinlich Bedrohungen enthalten) an Microsoft gesendet werden. Es gibt drei Ebenen zum Steuern der Beispielübermittlung:

- **Keine**: Es werden keine verdächtigen Beispiele an Microsoft übermittelt.
- **Sicher:** Nur verdächtige Beispiele, die keine personenbezogenen Informationen (PII) enthalten, werden automatisch übermittelt. Dies ist der Standardwert für diese Einstellung.
- **Alle**: Alle verdächtigen Beispiele werden an Microsoft übermittelt.

|||
|:---|:---|
| **Schlüssel** | automaticSampleSubmissionConsent |
| **Datentyp** | String |
| **Mögliche Werte** | keine <br/> sicher (Standard) <br/> all |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Aktivieren/Deaktivieren automatischer Sicherheitsintelligenzupdates

Bestimmt, ob Sicherheitsintelligenzupdates automatisch installiert werden:

|||
|:---|:---|
| **Schlüssel** | automaticDefinitionUpdateEnabled |
| **Datentyp** | Boolesch |
| **Mögliche Werte** | true (Standard) <br/> false |

## <a name="recommended-configuration-profile"></a>Empfohlenes Konfigurationsprofil

Für die ersten Schritte wird das folgende Konfigurationsprofil für Ihr Unternehmen empfohlen, um alle Schutzfunktionen zu nutzen, die Defender for Endpoint bietet.

Das folgende Konfigurationsprofil hat Folgendes:

- Aktivieren des Echtzeitschutzes (Real-Time Protection, RTP)
- Geben Sie an, wie die folgenden Bedrohungstypen behandelt werden:
  - **Potenziell unerwünschte Anwendungen (PUA)** werden blockiert
  - **Archivangriffe** (Datei mit hoher Komprimierungsrate) werden in den Produktprotokollen überwacht.
- Aktivieren automatischer Sicherheitsintelligenzupdates
- Aktivieren des in der Cloud übermittelten Schutzes
- Aktivieren der automatischen Beispielübermittlung auf `safe` Ebene

### <a name="sample-profile"></a>Beispielprofil

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true
   }
}
```

## <a name="full-configuration-profile-example"></a>Beispiel für ein vollständiges Konfigurationsprofil

Das folgende Konfigurationsprofil enthält Einträge für alle in diesem Dokument beschriebenen Einstellungen und kann für erweiterte Szenarien verwendet werden, in denen Sie mehr Kontrolle über das Produkt wünschen.

### <a name="full-profile"></a>Vollständiges Profil

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true
   }
}
```

## <a name="configuration-profile-validation"></a>Konfigurationsprofilüberprüfung

Das Konfigurationsprofil muss eine gültige JSON-formatierte Datei sein. Es gibt eine Reihe von Tools, die verwendet werden können, um dies zu überprüfen. Beispiel: Wenn Sie auf `python` Ihrem Gerät installiert sind:

```bash
python -m json.tool mdatp_managed.json
```

Wenn das JSON wohlgeformt ist, gibt der obige Befehl es zurück an das Terminal aus und gibt den Exitcode von `0` zurück. Andernfalls wird ein Fehler angezeigt, der das Problem beschreibt, und der Befehl gibt den Exitcode von `1` zurück.

## <a name="configuration-profile-deployment"></a>Konfigurationsprofilbereitstellung

Nachdem Sie das Konfigurationsprofil für Ihr Unternehmen erstellt haben, können Sie es über das Verwaltungstool bereitstellen, das Ihr Unternehmen verwendet. Defender for Endpoint für Linux liest die verwaltete Konfiguration aus der *Datei /etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*
