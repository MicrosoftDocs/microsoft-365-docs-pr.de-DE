---
title: Datenschutz für Microsoft Defender for Endpoint auf Dem Mac
description: Datenschutzsteuerelemente, konfigurieren von Richtlinieneinstellungen, die sich auf den Datenschutz auswirken, sowie Informationen zu den diagnosedaten, die in Microsoft Defender for Endpoint auf Mac gesammelt werden.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, privacy, diagnostic
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
ms.openlocfilehash: 2884ffc695abc1c6b4b5be9bbd7c9ad37ad05439
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651296"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a>Datenschutz für Microsoft Defender for Endpoint unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Microsoft verpflichtet sich, Ihnen die Informationen und Steuerelemente zur Verfügung zu stellen, die Sie benötigen, um entscheidungen darüber zu treffen, wie Ihre Daten gesammelt und verwendet werden, wenn Sie Microsoft Defender for Endpoint unter macOS verwenden.

In diesem Thema werden die im Produkt verfügbaren Datenschutzsteuerelemente, die Verwaltung dieser Steuerelemente mit Richtlinieneinstellungen und weitere Details zu den erfassten Datenereignissen beschrieben.

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a>Übersicht über Datenschutzsteuerelemente in Microsoft Defender for Endpoint unter macOS

In diesem Abschnitt werden die Datenschutzsteuerelemente für die verschiedenen Arten von Daten beschrieben, die von Microsoft Defender for Endpoint unter macOS erfasst werden.

### <a name="diagnostic-data"></a>Diagnosedaten

Diagnosedaten werden verwendet, um Microsoft Defender for Endpoint sicher und auf dem neuesten Stand zu halten, Probleme zu erkennen, zu diagnostizieren und zu beheben sowie Produktverbesserungen vorzunehmen.

Einige Diagnosedaten sind erforderlich, während andere Diagnosedaten optional sind. Durch die Verwendung von Datenschutzsteuerelementen wie Richtlinieneinstellungen für Organisationen bieten wir Ihnen die Möglichkeit auszuwählen, ob Sie uns erforderliche oder optionale Diagnosedaten senden wollen oder nicht.

Es gibt zwei Ebenen von Diagnosedaten für Microsoft Defender for Endpoint-Clientsoftware, aus der Sie auswählen können:

* **Erforderlich:** Die Mindestdaten, die erforderlich sind, um Microsoft Defender for Endpoint auf dem gerät, auf dem es installiert ist, sicher, auf dem neuesten Stand zu halten und wie erwartet zu gewährleisten.

* **Optional:** Zusätzliche Daten, die Microsoft dabei unterstützen, Produktverbesserungen vorzunehmen und erweiterte Informationen zur Erkennung, Diagnose und Behebung von Problemen zur Verfügung zu stellen.

Standardmäßig werden nur erforderliche Diagnosedaten an Microsoft gesendet.

### <a name="cloud-delivered-protection-data"></a>Von der Cloud übermittelte Schutzdaten

Cloud-zugestellter Schutz wird verwendet, um einen erhöhten und schnelleren Schutz mit Zugriff auf die neuesten Schutzdaten in der Cloud zu bieten.

Das Aktivieren des in der Cloud übermittelten Schutzdiensts ist optional, wird jedoch dringend empfohlen, da er einen wichtigen Schutz vor Schadsoftware auf Ihren Endpunkten und im gesamten Netzwerk bietet.

### <a name="sample-data"></a>Beispieldaten

Beispieldaten werden verwendet, um die Schutzfunktionen des Produkts zu verbessern, indem verdächtige Microsoft-Beispiele gesendet werden, damit sie analysiert werden können. Das Aktivieren der automatischen Beispielübermittlung ist optional.

Wenn dieses Feature aktiviert ist und das gesammelte Beispiel wahrscheinlich personenbezogene Informationen enthält, wird der Benutzer zur Zustimmung aufgefordert.

## <a name="manage-privacy-controls-with-policy-settings"></a>Verwalten von Datenschutzsteuerelementen mit Richtlinieneinstellungen

Wenn Sie ein IT-Administrator sind, können Sie diese Steuerelemente auf Unternehmensebene konfigurieren. 

Die Datenschutzsteuerelemente für die verschiedenen Arten von Daten, die im vorherigen Abschnitt beschrieben werden, werden unter Festlegen von Einstellungen für Microsoft Defender for Endpoint unter [macOS ausführlich beschrieben.](mac-preferences.md)

Wie bei allen neuen Richtlinieneinstellungen sollten Sie sie sorgfältig in einer begrenzten, kontrollierten Umgebung testen, um sicherzustellen, dass die von Ihnen konfigurierten Einstellungen den gewünschten Effekt haben, bevor Sie die Richtlinieneinstellungen in Ihrer Organisation weiterverbreiten.

## <a name="diagnostic-data-events"></a>Diagnosedatenereignisse

In diesem Abschnitt werden die erforderlichen Diagnosedaten und optionalen Diagnosedaten sowie eine Beschreibung der erfassten Ereignisse und Felder beschrieben.

### <a name="data-fields-that-are-common-for-all-events"></a>Datenfelder, die für alle Ereignisse gemeinsam sind
Es gibt einige Informationen, die allen Ereignissen gemein sind, unabhängig von Kategorie oder Datenuntertyp. 

Die folgenden Felder gelten für alle Ereignisse als üblich:

| Feld                   | Beschreibung |
| ----------------------- | ----------- |
| Plattform                | Die breite Klassifizierung der Plattform, auf der die App ausgeführt wird. Ermöglicht Microsoft zu ermitteln, auf welchen Plattformen ein Problem auftreten kann, damit es ordnungsgemäß priorisiert werden kann. |
| machine_guid            | Eindeutige ID, die dem Gerät zugeordnet ist. Ermöglicht Microsoft zu ermitteln, ob sich Probleme auf eine ausgewählte Gruppe von Installationen auswirken und wie viele Benutzer betroffen sind. |
| sense_guid              | Eindeutige ID, die dem Gerät zugeordnet ist. Ermöglicht Microsoft zu ermitteln, ob sich Probleme auf eine ausgewählte Gruppe von Installationen auswirken und wie viele Benutzer betroffen sind. |
| org_id                  | Eindeutige ID, die dem Unternehmen zugeordnet ist, zu dem das Gerät gehört. Ermöglicht Microsoft zu ermitteln, ob sich Probleme auf eine ausgewählte Gruppe von Unternehmen auswirken und wie viele Unternehmen betroffen sind. |
| hostname                | Lokaler Gerätename (ohne DNS-Suffix). Ermöglicht Microsoft zu ermitteln, ob sich Probleme auf eine ausgewählte Gruppe von Installationen auswirken und wie viele Benutzer betroffen sind. |
| product_guid            | Eindeutige ID des Produkts. Ermöglicht Es Microsoft, Probleme zu unterscheiden, die sich auf unterschiedliche Produktrichtungen auswirken. |
| app_version             | Version der Microsoft Defender for Endpoint unter macOS-Anwendung. Ermöglicht Microsoft, zu ermitteln, welche Versionen des Produkts ein Problem anzeigen, damit es ordnungsgemäß priorisiert werden kann.|
| sig_version             | Version der Security Intelligence-Datenbank. Ermöglicht Microsoft, zu ermitteln, welche Versionen der Sicherheitsintelligenz ein Problem anzeigen, damit es ordnungsgemäß priorisiert werden kann. |
| supported_compressions  | Liste der von der Anwendung unterstützten Komprimierungsalgorithmen, z. B. `['gzip']` . Ermöglicht Microsoft zu verstehen, welche Arten von Komprimierung verwendet werden können, wenn es mit der Anwendung kommuniziert. |
| release_ring            | Ring, dem das Gerät zugeordnet ist (z. B. Insider Fast, Insider Slow, Production). Ermöglicht Microsoft, zu ermitteln, auf welchem Releasering ein Problem auftreten kann, damit es ordnungsgemäß priorisiert werden kann. |


### <a name="required-diagnostic-data"></a>Erforderliche Diagnosedaten

**Erforderliche Diagnosedaten** sind die Mindestdaten, die erforderlich sind, um Microsoft Defender for Endpoint sicher, auf dem neuesten Stand zu halten und auf dem Gerät, auf dem es installiert ist, wie erwartet durchzuführen.

Erforderliche Diagnosedaten helfen bei der Identifizierung von Problemen mit Microsoft Defender for Endpoint, die mit einer Geräte- oder Softwarekonfiguration in Zusammenhang stehen können. So kann beispielsweise ermittelt werden, ob ein Microsoft Defender for Endpoint-Feature auf einer bestimmten Betriebssystemversion mit neu eingeführten Features häufiger abstürzt oder ob bestimmte Microsoft Defender for Endpoint-Features deaktiviert sind. Erforderliche Diagnosedaten helfen Microsoft, diese Probleme schneller zu erkennen, zu diagnostizieren und zu beheben, sodass die Auswirkungen auf Benutzer oder Organisationen reduziert werden.

#### <a name="software-setup-and-inventory-data-events"></a>Softwaresetup und Inventurdatenereignisse

**Installation/Deinstallation von Microsoft Defender for Endpoint**

Die folgenden Felder werden erfasst:

| Feld            | Beschreibung |
| ---------------- | ----------- |
| correlation_id   | Eindeutige ID, die der Installation zugeordnet ist. |
| Version          | Version des Pakets. |
| Schweregrad         | Schweregrad der Nachricht (z. B. Information). |
| code             | Code, der den Vorgang beschreibt. |
| text             | Zusätzliche Informationen zur Produktinstallation. |

**Konfiguration von Microsoft Defender für Endpunkt**

Die folgenden Felder werden erfasst:

| Feld                                               | Beschreibung |
| --------------------------------------------------- | ----------- |
| antivirus_engine.enable_real_time_protection        | Gibt an, ob der Echtzeitschutz auf dem Gerät aktiviert ist oder nicht. |
| antivirus_engine.passive_mode                       | Gibt an, ob der passive Modus auf dem Gerät aktiviert ist oder nicht. |
| cloud_service.enabled                               | Gibt an, ob der in der Cloud zugestellte Schutz auf dem Gerät aktiviert ist oder nicht. |
| cloud_service.timeout                               | Zeitpunkt, wenn die Anwendung mit der Microsoft Defender for Endpoint-Cloud kommuniziert. |
| cloud_service.heartbeat_interval                    | Intervall zwischen aufeinander folgenden Takten, die vom Produkt an die Cloud gesendet werden. |
| cloud_service.service_uri                           | URI, der für die Kommunikation mit der Cloud verwendet wird. |
| cloud_service.diagnostic_level                      | Diagnosestufe des Geräts (erforderlich, optional). |
| cloud_service.automatic_sample_submission           | Gibt an, ob die automatische Beispielübermittlung aktiviert ist oder nicht. |
| cloud_service.automatic_definition_update_enabled   | Gibt an, ob die automatische Definitionsaktualisierung aktiviert ist oder nicht. |
| edr.early_preview                                   | Gibt an, ob das Gerät EDR vorschaufeatures ausgeführt werden soll. |
| edr.group_id                                        | Gruppen-ID, die von der Erkennungs- und Antwortkomponente verwendet wird. |
| edr.tags                                            | Benutzerdefinierte Tags. |
| Features. \[ Optionaler Featurename\]                  | Liste der Vorschaufeatures, unabhängig davon, ob sie aktiviert sind oder nicht. |

#### <a name="product-and-service-usage-data-events"></a>Produkt- und Dienstverwendungsdatenereignisse

**Security Intelligence Update Report**

Die folgenden Felder werden erfasst:

| Feld            | Beschreibung |
| ---------------- | ----------- |
| from_version     | Ursprüngliche Version der Sicherheitsintelligenz. |
| to_version       | Neue Security Intelligence-Version. |
| status           | Status des Updates, der den Erfolg oder Fehler angibt. |
| using_proxy      | Gibt an, ob das Update über einen Proxy durchgeführt wurde. |
| error            | Fehlercode, wenn das Update fehlgeschlagen ist. |
| reason           | Fehlermeldung, wenn die aktualisierte abgelegt wurde. |

#### <a name="product-and-service-performance-data-events"></a>Ereignisse im Zusammenhang mit Produkt- und Dienstleistungsdaten

**Unerwartete Anwendungsbeendung (Absturz)**

Sammelt Systeminformationen und den Status einer Anwendung, wenn eine Anwendung unerwartet beendet wird.

Die folgenden Felder werden erfasst:

| Feld                          | Beschreibung |
| ------------------------------ | ----------- |
| v1_crash_count                 | Anzahl der Stündlichabstürzen des V1-Modulprozesses auf dem Clientcomputer  |
| v2_crash_count                 | Anzahl der Stündlichabstürzen des V2-Modulprozesses auf dem Clientcomputer  |
| EDR_crash_count                | Anzahl der EDR Prozess stündlich auf dem Clientcomputer abgestürzt        |

**Kernelerweiterungsstatistiken**

Die folgenden Felder werden erfasst:

| Feld            | Beschreibung |
| ---------------- | ----------- |
| Version          | Version von Microsoft Defender for Endpoint unter macOS. |
| instance_id      | Eindeutiger Bezeichner, der beim Start der Kernelerweiterung generiert wird. |
| trace_level      | Ablaufverfolgungsebene der Kernelerweiterung. |
| Subsystem        | Das zugrunde liegende Subsystem, das für den Echtzeitschutz verwendet wird. |
| ipc.connects     | Die Anzahl der Verbindungsanforderungen, die von der Kernelerweiterung empfangen werden. |
| ipc.rejects      | Die Anzahl der Verbindungsanforderungen, die von der Kernelerweiterung abgelehnt werden. |
| ipc.connected    | Gibt an, ob eine aktive Verbindung mit der Kernelerweiterung besteht. |

#### <a name="support-data"></a>Supportdaten

**Diagnoseprotokolle**

Diagnoseprotokolle werden nur mit Zustimmung des Benutzers im Rahmen des Feedback-Übermittlungsfeatures gesammelt. Die folgenden Dateien werden im Rahmen der Supportprotokolle gesammelt:

- Alle Dateien unter */Library/Logs/Microsoft/mdatp/*
- Teilmenge der Dateien unter */Library/Application Support/Microsoft/Defender/,* die von Microsoft Defender for Endpoint unter macOS erstellt und verwendet werden
- Teilmenge der Dateien unter */Library/Managed Preferences,* die von Microsoft Defender for Endpoint unter macOS verwendet werden
- /Library/Logs/Microsoft/autoupdate.log
- $HOME/Library/Preferences/com.microsoft.autoupdate2.plist

### <a name="optional-diagnostic-data"></a>Optionale Diagnosedaten

**Optionale Diagnosedaten sind** zusätzliche Daten, die Microsoft dabei unterstützen, Produktverbesserungen vorzunehmen und erweiterte Informationen zur Erkennung, Diagnose und Behebung von Problemen zur Verfügung zu stellen.

Wenn Sie sich dafür entscheiden, uns optionale Diagnosedaten zu senden, werden auch die erforderlichen Diagnosedaten mitgeliefert.

Beispiele für optionale Diagnosedaten sind Daten, die Microsoft über die Produktkonfiguration (z. B. die Anzahl der auf dem Gerät festgelegten Ausschlüsse) und die Produktleistung (aggregierte Maßnahmen zur Leistung von Komponenten des Produkts) sammelt.

#### <a name="software-setup-and-inventory-data-events"></a>Softwaresetup und Inventurdatenereignisse

**Konfiguration von Microsoft Defender für Endpunkt**

Die folgenden Felder werden erfasst:

| Feld                                              | Beschreibung |
| -------------------------------------------------- | ----------- |
| connection_retry_timeout                           | Bei der Kommunikation mit der Cloud ist bei verbindungsversuchsversuchen ein Zeitverzich aus. |
| file_hash_cache_maximum                            | Größe des Produktcaches. |
| crash_upload_daily_limit                           | Grenzwert der täglich hochgeladenen Absturzprotokolle. |
| antivirus_engine.exclusions[].is_directory         | Gibt an, ob es sich bei dem Ausschluss von der Überprüfung um ein Verzeichnis handelt oder nicht. |
| antivirus_engine.exclusions[].path                 | Pfad, der von der Überprüfung ausgeschlossen wurde. |
| antivirus_engine.exclusions[].extension            | Erweiterung, die von der Überprüfung ausgeschlossen ist. |
| antivirus_engine.exclusions[].name                 | Name der Datei, die von der Überprüfung ausgeschlossen wurde. |
| antivirus_engine.scan_cache_maximum                | Größe des Produktcaches. |
| antivirus_engine.maximum_scan_threads              | Maximale Anzahl von Threads, die zum Scannen verwendet werden. |
| antivirus_engine.threat_restoration_exclusion_time | Zeit bis eine aus der Quarantäne wiederhergestellte Datei erneut erkannt werden kann. |
| antivirus_engine.threat_type_settings              | Konfiguration, wie verschiedene Bedrohungstypen vom Produkt behandelt werden. |
| filesystem_scanner.full_scan_directory             | Vollständiges Scanverzeichnis. |
| filesystem_scanner.quick_scan_directories          | Liste der Verzeichnisse, die beim Schnellscan verwendet werden. |
| edr.latency_mode                                   | Latenzmodus, der von der Erkennungs- und Antwortkomponente verwendet wird. |
| edr.proxy_address                                  | Von der Erkennungs- und Antwortkomponente verwendete Proxyadresse. |

**Microsoft Auto-Update-Konfiguration**

Die folgenden Felder werden erfasst:

| Feld                       | Beschreibung |
| --------------------------- | ----------- |
| how_to_check                | Bestimmt, wie Produktupdates überprüft werden (z. B. automatisch oder manuell). |
| channel_name                | Updatekanal, der dem Gerät zugeordnet ist. |
| manifest_server             | Server, der zum Herunterladen von Updates verwendet wird. |
| update_cache                | Speicherort des Caches, der zum Speichern von Updates verwendet wird. |

### <a name="product-and-service-usage"></a>Produkt- und Dienstnutzung

#### <a name="diagnostic-log-upload-started-report"></a>Bericht "Start des Diagnoseprotokolluploads"

Die folgenden Felder werden erfasst:

| Feld            | Beschreibung |
| ---------------- | ----------- |
| sha256           | SHA256-ID des Supportprotokolls. |
| Größe             | Größe des Supportprotokolls. |
| original_path    | Pfad zum Supportprotokoll (immer unter */Library/Application Support/Microsoft/Defender/wdavdiag/*). |
| Format           | Format des Supportprotokolls. |

#### <a name="diagnostic-log-upload-completed-report"></a>Abgeschlossener Bericht zum Hochladen des Diagnoseprotokolls

Die folgenden Felder werden erfasst:

| Feld            | Beschreibung |
| ---------------- | ----------- |
| request_id       | Korrelations-ID für die Anforderung zum Hochladen des Supportprotokolls. |
| sha256           | SHA256-ID des Supportprotokolls. |
| blob_sas_uri     | URI, der von der Anwendung zum Hochladen des Supportprotokolls verwendet wird. |

#### <a name="product-and-service-performance-data-events"></a>Ereignisse im Zusammenhang mit Produkt- und Dienstleistungsdaten

**Unerwartete Anwendungsbeendung (Absturz)**

Unerwartete Anwendungsbeendungen und der Anwendungsstatus zum Zeitpunkt des Beendung.

**Kernelerweiterungsstatistiken**

Die folgenden Felder werden erfasst:

| Feld                          | Beschreibung |
| ------------------------------ | ----------- |
| pkt_ack_timeout                | Die folgenden Eigenschaften sind aggregierte numerische Werte, die die Anzahl der Ereignisse darstellen, die seit dem Start der Kernelerweiterung passiert sind. |
| pkt_ack_conn_timeout             | |
| ipc.ack_pkts                     | |
| ipc.nack_pkts                    | |
| ipc.send.ack_no_conn             | |
| ipc.send.nack_no_conn            | |
| ipc.send.ack_no_qsq              | |
| ipc.send.nack_no_qsq             | |
| ipc.ack.no_space                 | |
| ipc.ack.timeout                  | |
| ipc.ack.ackd_fast                | |
| ipc.ack.ackd                     | |
| ipc.recv.bad_pkt_len             | |
| ipc.recv.bad_reply_len           | |
| ipc.recv.no_waiter               | |
| ipc.recv.copy_failed             | |
| ipc.kauth.vnode.mask             | |
| ipc.kauth.vnode.read             | |
| ipc.kauth.vnode.write            | |
| ipc.kauth.vnode.exec             | |
| ipc.kauth.vnode.del              | |
| ipc.kauth.vnode.read_attr        | |
| ipc.kauth.vnode.write_attr       | |
| ipc.kauth.vnode.read_ex_attr     | |
| ipc.kauth.vnode.write_ex_attr    | |
| ipc.kauth.vnode.read_sec         | |
| ipc.kauth.vnode.write_sec        | |
| ipc.kauth.vnode.take_own         | |
| ipc.kauth.vnode.link             | |
| ipc.kauth.vnode.create           | |
| ipc.kauth.vnode.move             | |
| ipc.kauth.vnode.mount            | |
| ipc.kauth.vnode.denied           | |
| ipc.kauth.vnode.ackd_before_deadline | |
| ipc.kauth.vnode.missed_deadline  | |
| ipc.kauth.file_op.mask           | |
| ipc.kauth_file_op.open           | |
| ipc.kauth.file_op.close          | |
| ipc.kauth.file_op.close_modified | |
| ipc.kauth.file_op.move           | |
| ipc.kauth.file_op.link           | |
| ipc.kauth.file_op.exec           | |
| ipc.kauth.file_op.remove         | |
| ipc.kauth.file_op.unmount        | |
| ipc.kauth.file_op.fork           | |
| ipc.kauth.file_op.create         | |

## <a name="resources"></a>Ressourcen

- [Datenschutz bei Microsoft](https://privacy.microsoft.com/)
