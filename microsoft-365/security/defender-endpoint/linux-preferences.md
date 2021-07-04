---
title: Festlegen von Einstellungen für Microsoft Defender für Endpunkt unter Linux
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Linux in Unternehmen konfiguriert wird.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Linux, Installation, bereitstellen, Deinstallation, entinstallation, ansible, linux, redhat, ubuntu, git, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289487"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a>Festlegen von Einstellungen für Microsoft Defender für Endpunkt unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> Dieses Thema enthält Anweisungen zum Festlegen von Einstellungen für Defender für Endpunkt unter Linux in Unternehmensumgebungen. Wenn Sie an der Konfiguration des Produkts auf einem Gerät über die Befehlszeile interessiert sind, finden Sie weitere Informationen unter ["Ressourcen".](linux-resources.md#configure-from-the-command-line)

In Unternehmensumgebungen kann Defender für Endpunkt unter Linux über ein Konfigurationsprofil verwaltet werden. Dieses Profil wird über das Verwaltungstool Ihrer Wahl bereitgestellt. Vom Unternehmen verwaltete Einstellungen haben Vorrang vor den Einstellungen, die lokal auf dem Gerät festgelegt sind. Mit anderen Worten: Benutzer in Ihrem Unternehmen können keine Einstellungen ändern, die über dieses Konfigurationsprofil festgelegt werden.

In diesem Artikel werden die Struktur dieses Profils (einschließlich eines empfohlenen Profils, das Sie für die ersten Schritte verwenden können) und Anweisungen zum Bereitstellen des Profils beschrieben.

## <a name="configuration-profile-structure"></a>Konfigurationsprofilstruktur

Das Konfigurationsprofil ist eine JSON-Datei, die aus Einträgen besteht, die durch einen Schlüssel identifiziert werden (der den Namen der Einstellung angibt), gefolgt von einem Wert, der von der Art der Einstellung abhängt. Werte können einfach sein, z. B. ein numerischer Wert, oder komplex sein, z. B. eine geschachtelte Liste von Einstellungen.

In der Regel verwenden Sie ein Konfigurationsverwaltungstool, um eine Datei mit dem Namen am Speicherort zu ```mdatp_managed.json``` ```/etc/opt/microsoft/mdatp/managed/``` übertragen.

Die oberste Ebene des Konfigurationsprofils enthält produktweite Einstellungen und Einträge für Unterbereiche des Produkts, die in den nächsten Abschnitten ausführlicher erläutert werden.

### <a name="antivirus-engine-preferences"></a>Einstellungen des Antivirusmoduls

Der Abschnitt *"antivirusEngine"* des Konfigurationsprofils wird verwendet, um die Einstellungen der Antivirenkomponente des Produkts zu verwalten.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|antivirusEngine|
|**Datentyp**|Wörterbuch (geschachtelte Präferenz)|
|**Comments**|Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.|
|

#### <a name="enable--disable-real-time-protection"></a>Aktivieren/Deaktivieren des Echtzeitschutzes

Bestimmt, ob der Echtzeitschutz (Beim Zugriff auf Dateien scannen) aktiviert ist oder nicht.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|enableRealTimeProtection|
|**Datentyp**|Boolesch|
|**Mögliche Werte**|true (Standard) <p> false|
|

#### <a name="enable--disable-passive-mode"></a>Aktivieren/Deaktivieren des passiven Modus

Bestimmt, ob das Antivirenmodul im passiven Modus ausgeführt wird oder nicht. Im passiven Modus:

- Der Echtzeitschutz ist deaktiviert.
- On-Demand-Überprüfung ist aktiviert.
- Die automatische Bedrohungsbehebung ist deaktiviert.
- Sicherheitsupdates sind aktiviert.
- Das Statusmenüsymbol ist ausgeblendet.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|passiveMode|
|**Datentyp**|Boolesch|
|**Mögliche Werte**|false (Standard) <p> true|
|**Comments**|Verfügbar in Defender für Endpunkt Version 100.67.60 oder höher.|
|

#### <a name="exclusion-merge-policy"></a>Richtlinie zum Zusammenführen von Ausschlüssen

Gibt die Zusammenführungsrichtlinie für Ausschlüsse an. Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Ausschlüssen ( `merge` ) oder nur von einem Administrator definierten Ausschlüssen ( ) `admin_only` sein. Diese Einstellung kann verwendet werden, um lokale Benutzer daran zu hindern, ihre eigenen Ausschlüsse zu definieren.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|exclusionsMergePolicy|
|**Datentyp**|String|
|**Mögliche Werte**|Zusammenführen (Standard) <p> admin_only|
|**Comments**|Verfügbar in Defender für Endpunkt Version 100.83.73 oder höher.|
|

#### <a name="scan-exclusions"></a>Scanausschlüsse

Entitäten, die von der Überprüfung ausgeschlossen wurden. Ausschlüsse können durch vollständige Pfade, Erweiterungen oder Dateinamen angegeben werden.
(Ausschlüsse werden als Array von Elementen angegeben, der Administrator kann beliebig viele Elemente angeben.)

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|Ausschlüsse|
|**Datentyp**|Wörterbuch (geschachtelte Präferenz)|
|**Comments**|Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.|
|

##### <a name="type-of-exclusion"></a>Art des Ausschlusses

Gibt den Vom Scan ausgeschlossenen Inhaltstyp an.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|$type|
|**Datentyp**|String|
|**Mögliche Werte**|excludedPath <p> excludedFileExtension <p> excludedFileName|
|

##### <a name="path-to-excluded-content"></a>Pfad zu ausgeschlossenen Inhalten

Wird verwendet, um Inhalte vom Scan nach vollständigem Dateipfad auszuschließen.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|path|
|**Datentyp**|String|
|**Mögliche Werte**|Gültige Pfade|
|**Comments**|Gilt nur, wenn *$type* *ausgeschlossen IstPath*|
|

##### <a name="path-type-file--directory"></a>Pfadtyp (Datei/Verzeichnis)

Gibt an, ob die *Pfadeigenschaft* auf eine Datei oder ein Verzeichnis verweist.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|Isdirectory|
|**Datentyp**|Boolesch|
|**Mögliche Werte**|false (Standard) <p> true|
|**Comments**|Gilt nur, wenn *$type* *ausgeschlossen IstPath*|
|

##### <a name="file-extension-excluded-from-the-scan"></a>Dateierweiterung, die von der Überprüfung ausgeschlossen ist

Wird verwendet, um Inhalte von der Überprüfung mithilfe der Dateierweiterung auszuschließen.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|Erweiterung|
|**Datentyp**|String|
|**Mögliche Werte**|gültige Dateierweiterungen|
|**Comments**|Gilt nur, wenn *$type* *ausgeschlossen istFileExtension*|
|

##### <a name="process-excluded-from-the-scan"></a>Vom Scan ausgeschlossener Prozess*

Gibt einen Prozess an, für den alle Dateiaktivitäten von der Überprüfung ausgeschlossen werden. Der Prozess kann entweder durch seinen Namen (z. `cat` B. ) oder durch den vollständigen Pfad (z. B. ) angegeben `/bin/cat` werden.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|name|
|**Datentyp**|String|
|**Mögliche Werte**|Eine beliebige Zeichenfolge|
|**Comments**|Gilt nur, wenn *$type* *ausgeschlossen IstFileName*|
|

#### <a name="allowed-threats"></a>Zulässige Bedrohungen

Liste der Bedrohungen (identifiziert durch ihren Namen), die nicht vom Produkt blockiert werden und stattdessen ausgeführt werden dürfen.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|allowedThreats|
|**Datentyp**|Array aus Zeichenfolgen|
|

#### <a name="disallowed-threat-actions"></a>Unzulässige Bedrohungsaktionen

Schränkt die Aktionen ein, die der lokale Benutzer eines Geräts ausführen kann, wenn Bedrohungen erkannt werden. Die in dieser Liste enthaltenen Aktionen werden nicht auf der Benutzeroberfläche angezeigt.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|disallowedThreatActions|
|**Datentyp**|Array aus Zeichenfolgen|
|**Mögliche Werte**|zulassen (verhindert, dass Benutzer Bedrohungen zulassen) <p> Wiederherstellen (verhindert, dass Benutzer Bedrohungen aus der Quarantäne wiederherstellen)|
|**Comments**|Verfügbar in Defender für Endpunkt Version 100.83.73 oder höher.|
|

#### <a name="threat-type-settings"></a>Einstellungen für den Bedrohungstyp

Die *Einstellung "threatTypeSettings"* im Antivirenmodul wird verwendet, um zu steuern, wie bestimmte Bedrohungstypen vom Produkt behandelt werden.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|threatTypeSettings|
|**Datentyp**|Wörterbuch (geschachtelte Präferenz)|
|**Comments**|Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.|
|

##### <a name="threat-type"></a>Bedrohungstyp

Art der Bedrohung, für die das Verhalten konfiguriert ist.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|Schlüssel|
|**Datentyp**|String|
|**Mögliche Werte**|potentially_unwanted_application <p> archive_bomb|
|

##### <a name="action-to-take"></a>Zu ergreifende Maßnahme

Auszuführende Aktion, wenn eine Bedrohung des im vorherigen Abschnitt angegebenen Typs angezeigt wird. Dies kann folgende sein:

- **Überwachung:** Das Gerät ist nicht vor dieser Art von Bedrohung geschützt, aber ein Eintrag über die Bedrohung wird protokolliert.
- **Blockieren:** Das Gerät ist vor dieser Art von Bedrohung geschützt, und Sie werden in der Sicherheitskonsole benachrichtigt.
- **Deaktiviert:** Das Gerät ist nicht vor dieser Art von Bedrohung geschützt, und es wird nichts protokolliert.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|Wert|
|**Datentyp**|String|
|**Mögliche Werte**|Überwachung (Standard) <p> Block <p> Aus|
|

#### <a name="threat-type-settings-merge-policy"></a>Richtlinie zum Zusammenführen von Bedrohungstypeinstellungen

Gibt die Zusammenführungsrichtlinie für Einstellungen für den Bedrohungstyp an. Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Einstellungen ( `merge` ) oder nur administratordefinierten Einstellungen ( `admin_only` ) sein. Diese Einstellung kann verwendet werden, um zu verhindern, dass lokale Benutzer ihre eigenen Einstellungen für unterschiedliche Bedrohungstypen definieren.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|threatTypeSettingsMergePolicy|
|**Datentyp**|String|
|**Mögliche Werte**|Zusammenführen (Standard) <p> admin_only|
|**Comments**|Verfügbar in Defender für Endpunkt Version 100.83.73 oder höher.|
|

#### <a name="antivirus-scan-history-retention-in-days"></a>Aufbewahrung des Antivirusscanverlaufs (in Tagen)

Geben Sie die Anzahl der Tage an, für die die Ergebnisse im Scanverlauf auf dem Gerät aufbewahrt werden. Alte Scanergebnisse werden aus dem Verlauf entfernt. Alte isolierte Dateien, die ebenfalls vom Datenträger entfernt werden.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|scanResultsRetentionDays|
|**Datentyp**|String|
|**Mögliche Werte**|90 (Standard). Zulässige Werte liegen zwischen 1 Tag und 180 Tagen.|
|**Comments**|Verfügbar in Defender für Endpunkt Version 101.04.76 oder höher.|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Maximale Anzahl von Elementen im Antivirusscanverlauf

Geben Sie die maximale Anzahl von Einträgen an, die im Scanverlauf beibehalten werden sollen. Die Einträge enthalten alle on-Demand-Scans, die in der Vergangenheit durchgeführt wurden, sowie alle Antivirenerkennungen.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|scanHistoryMaximumItems|
|**Datentyp**|String|
|**Mögliche Werte**|10000 (Standard). Zulässige Werte liegen zwischen 5000 Elementen und 15.000 Elementen.|
|**Comments**|Verfügbar in Defender für Endpunkt Version 101.04.76 oder höher.|
|

### <a name="cloud-delivered-protection-preferences"></a>Über die Cloud bereitgestellte Schutzeinstellungen

Der *cloudService-Eintrag* im Konfigurationsprofil wird verwendet, um das cloudgesteuerte Schutzfeature des Produkts zu konfigurieren.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|cloudService|
|**Datentyp**|Wörterbuch (geschachtelte Präferenz)|
|**Comments**|Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.|
|

#### <a name="enable--disable-cloud-delivered-protection"></a>Aktivieren/Deaktivieren des über die Cloud bereitgestellten Schutzes

Bestimmt, ob der über die Cloud bereitgestellte Schutz auf dem Gerät aktiviert ist oder nicht. Um die Sicherheit Ihrer Dienste zu verbessern, empfehlen wir, dieses Feature aktiviert zu halten.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|aktiviert|
|**Datentyp**|Boolesch|
|**Mögliche Werte**|true (Standard) <p> false|
|

#### <a name="diagnostic-collection-level"></a>Diagnosesammlungsebene

Diagnosedaten werden verwendet, um Defender für Endpunkt sicher und auf dem neuesten Stand zu halten, Probleme zu erkennen, zu diagnostizieren und zu beheben sowie Produktverbesserungen vorzunehmen. Diese Einstellung bestimmt die Diagnosestufe, die vom Produkt an Microsoft gesendet wird.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|diagnosticLevel|
|**Datentyp**|String|
|**Mögliche Werte**|optional (Standard) <p> erforderlich|
|

#### <a name="enable--disable-automatic-sample-submissions"></a>Aktivieren/Deaktivieren automatischer Beispielübermittlungen

Bestimmt, ob verdächtige Beispiele (die wahrscheinlich Bedrohungen enthalten) an Microsoft gesendet werden. Es gibt drei Ebenen zum Steuern der Beispielübermittlung:

- **Keine:** Es werden keine verdächtigen Beispiele an Microsoft übermittelt.
- **Tresor:** nur verdächtige Beispiele, die keine personenbezogenen Informationen (PII) enthalten, werden automatisch übermittelt. Dies ist der Standardwert für diese Einstellung.
- **Alle:** Alle verdächtigen Beispiele werden an Microsoft übermittelt.

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|automaticSampleSubmissionConsent|
|**Datentyp**|String|
|**Mögliche Werte**|keine <p> sicher (Standard) <p> Alle|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Aktivieren/Deaktivieren automatischer Security Intelligence-Updates

Bestimmt, ob Sicherheitsupdates automatisch installiert werden:

<br>

****

|Beschreibung|Wert|
|---|---|
|**Key**|automaticDefinitionUpdateEnabled|
|**Datentyp**|Boolesch|
|**Mögliche Werte**|true (Standard) <p> false|
|

## <a name="recommended-configuration-profile"></a>Empfohlenes Konfigurationsprofil

Für die ersten Schritte empfehlen wir das folgende Konfigurationsprofil für Ihr Unternehmen, um alle Schutzfunktionen zu nutzen, die Defender für Endpunkt bietet.

Das folgende Konfigurationsprofil sieht wie folgt aus:

- Aktivieren des Echtzeitschutzes (Real-Time Protection, RTP)
- Geben Sie an, wie die folgenden Bedrohungstypen behandelt werden:
  - **Potenziell unerwünschte Anwendungen (PUA)** werden blockiert
  - **Archivdateien** (Datei mit hoher Komprimierungsrate) werden in den Produktprotokollen überwacht.
- Automatische Security Intelligence-Updates aktivieren
- Aus der Cloud bereitgestellten Schutz aktivieren
- Aktivieren der automatischen Beispielübermittlung `safe` auf Ebene

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
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>Beispiel für ein vollständiges Konfigurationsprofil

Das folgende Konfigurationsprofil enthält Einträge für alle in diesem Dokument beschriebenen Einstellungen und kann für komplexere Szenarien verwendet werden, in denen Sie mehr Kontrolle über das Produkt wünschen.

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
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
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
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a>Überprüfung des Konfigurationsprofils

Das Konfigurationsprofil muss eine gültige JSON-formatierte Datei sein. Es gibt eine Reihe von Tools, die verwendet werden können, um dies zu überprüfen. Wenn Sie beispielsweise `python` auf Ihrem Gerät installiert haben:

```bash
python -m json.tool mdatp_managed.json
```

Wenn der JSON-Code wohlgeformt ist, gibt der obige Befehl ihn zurück an das Terminal und gibt den Exitcode `0` von zurück. Andernfalls wird ein Fehler angezeigt, der das Problem beschreibt, und der Befehl gibt den Exitcode `1` .

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>Überprüfen, ob die mdatp_managed.json-Datei wie erwartet funktioniert

Um zu überprüfen, ob /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsordnungsgemäß funktioniert, sollte neben diesen Einstellungen "[verwaltet]" angezeigt werden:

- cloud_enabled
- cloud_automatic_sample_submission_consent
- passive_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> Damit die mdatp_managed.jswirksam wird, ist kein Neustart des Wdavdaemon erforderlich.

## <a name="configuration-profile-deployment"></a>Bereitstellung von Konfigurationsprofilen

Nachdem Sie das Konfigurationsprofil für Ihr Unternehmen erstellt haben, können Sie es über das von Ihrem Unternehmen verwendeten Verwaltungstool bereitstellen. Defender für Endpunkt unter Linux liest die verwaltete Konfiguration aus der Datei *"/etc/opt/microsoft/mdatp/managed/mdatp_managed.json".*
