---
title: Geräteüberwachung & Berichterstellung – Sicherheitscenter
description: Beschreibt, wie Sie Ihre Geräte sicher, auf dem neuesten Stand halten und potenzielle Bedrohungen in Ihrer Organisation erkennen können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, Überwachung, Bericht, Geräte
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 92760ef14fb1192e4462bab656e22f3595f9b449
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843864"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Geräteüberwachung und-Berichterstellung im Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Halten Sie Ihre Geräte im Microsoft 365 Security Center sicher, auf dem neuesten Stand und stellen Sie potenzielle Bedrohungen vor Ort dar.

## <a name="view-device-alerts"></a>Anzeigen von Geräte Warnungen

Erhalten Sie aktuelle Benachrichtigungen zu Sicherheitsverletzungen und anderen Bedrohungen auf Ihren Geräten von Microsoft Defender für Endpoint (verfügbar mit einer E5-Lizenz). Das Microsoft 365 Security Center überwacht diese Warnungen effektiv mithilfe Ihres bevorzugten Workflows auf einer hohen Ebene.

### <a name="monitor-high-impact-alerts"></a>Überwachen von Warnungen mit hoher Wirkung

Jeder Microsoft Defender für die Endpunkt Warnung weist einen entsprechenden Schweregrad auf (hoch, Mittel, niedrig oder Information). Sie weist auf mögliche Auswirkungen auf Ihr Netzwerk hin, wenn Sie unbeaufsichtigt bleiben.  

Verwenden Sie die **Geräte Warnungs schwere** Karte, um sich speziell auf Warnungen zu konzentrieren, die gravierender sind und möglicherweise sofort reagieren müssen. Auf dieser Karte können Sie weitere Informationen im Microsoft Defender-Sicherheits Center-Portal anzeigen.

![Geräte Warnungen-Schweregrad Karte](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Grundlegendes zu Warnungs Quellen

Microsoft Defender for Endpoint nutzt Daten aus einer breiten Palette von Sicherheitssensoren und Nachrichtenquellen, um Warnungen zu generieren. Beispielsweise kann es Erkennungsinformationen von Microsoft Defender Antivirus und Antischadsoftware von Drittanbietern verwenden. Es kann auch Ihre eigene benutzerdefinierte Bedrohungs Intelligenz verwenden, die über die Webdienst-API bereitgestellt wird.

Die Karte für die **Erkennung von Geräte Warnungen** zeigt die Verteilung von Benachrichtigungen nach Quelle an. Verfolgen Sie Aktivitäten im Zusammenhang mit bestimmten Quellen, insbesondere ihren benutzerdefinierten Quellen. Sie können die Karte auch verwenden, um sich auf Warnungen zu konzentrieren, die von Sensoren stammen, die nicht so konfiguriert sind, dass böswillige Aktivitäten oder Komponenten automatisch blockiert werden.

![Geräte Warnungs Erkennungsquellen-Karte](../../media/device-alert-detection-sources.png)

Auf dieser Karte können Sie weitere Informationen im Microsoft Defender-Sicherheits Center-Portal anzeigen.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Grundlegendes zu den Typen von Bedrohungen, die Warnungen auslösen

Microsoft Defender for Endpoint sortiert jede Warnung in eine Kategorie, die eine bestimmte Stufe in der Angriffs Kette oder dem Typ der Bedrohungs Komponente darstellt. Beispielsweise kann eine erkannte Bedrohungsaktivität als "laterale Bewegung" kategorisiert werden, um anzugeben, dass versucht wurde, andere Geräte im Netzwerk zu erreichen. Die Aktivität ist wahrscheinlich aufgetreten, nachdem Angreifer einen ersten Standbein erreicht haben. Wenn eine Bedrohungs Komponente erkannt wird, kann Sie weitgehend als Schadsoftware oder speziell als bestimmter Bedrohungs klassifiziert werden. Zu den Besonderheiten gehören Ransomware, das stehlen von Anmeldeinformationen oder andere Arten von bösartiger oder unerwünschter Software.

Die Karte **Bedrohungskategorien für Geräte** zeigt die Verteilung von Warnungen in diesen Kategorien an. Verwenden Sie diese Informationen, um die Bedrohungsaktivität zu identifizieren, wie beispielsweise Diebstahlversuche von Anmeldeinformationen, die in der Regel höhere Auswirkungen haben als Social Engineering-Versuche. Sie können auch auf potenziell destruktive Bedrohungen wie Ransomware überwachen.

![Geräte Bedrohungskategorien-Karte](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Überwachen aktiver Warnungen

Die **Geräte Warnungs-Status** Karte gibt die Anzahl der Warnungen an, die nicht aufgelöst wurden, und erfordert möglicherweise Aufmerksamkeit. Auf dieser Karte können Sie weitere Informationen im Microsoft Defender-Sicherheits Center-Portal anzeigen.

![Geräte Warnungsstatus Karte](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Überwachen der Klassifizierung der aufgelösten Warnungen

Beim Auflösen einer Warnung von Microsoft Defender for Endpoint können Ihre Sicherheitsmitarbeiter angeben, ob eine Warnung wie folgt überprüft wurde:

* Eine echte Warnung, die tatsächliche Verletzungs Aktivität oder Bedrohungs Komponenten identifiziert
* Eine falsche Warnung, bei der die normale Aktivität falsch erkannt wurde

Die **Geräte Warnungs Klassifizierungs** Karte zeigt an, ob Ihre aufgelösten Warnungen als true oder false Alerts klassifiziert wurden. Auf dieser Karte können Sie weitere Informationen im Microsoft Defender-Sicherheits Center-Portal anzeigen.

Hinweis: in einigen Fällen stehen Klassifizierungsinformationen für bestimmte Warnungen nicht zur Verfügung.

![Geräte Warnungs-Klassifikations Karte](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Überwachen der Ermittlung von aufgelösten Warnungen

Zusammen mit der Klassifizierung, ob eine Warnung bei der Lösung true oder false ist, kann Ihr Sicherheitspersonal eine Ermittlung bereitstellen. Eine Ermittlung gibt den Typ der normalen oder böswilligen Aktivität an, die bei der Überprüfung der Warnung gefunden wurde.

Die Karte für die **Geräte Warnungs Ermittlung** zeigt die für jede Warnung vorgesehene Ermittlung an.

* **Apt** : Fortgeschrittene beständige Bedrohung, die darauf hinweist, dass die erkannte Aktivität oder Bedrohungs Komponente Teil einer anspruchsvollen Sicherheitslücke ist, die im betroffenen Netzwerk Fuß fassen soll  
* **Schadsoftware** : bösartige Datei oder Code
* **Sicherheitspersonal** : normale Aktivitäten, die von Sicherheitsmitarbeitern ausgeführt werden
* **Sicherheitstests** : Aktivitäten oder Komponenten, die zum Simulieren von tatsächlichen Bedrohungen entwickelt wurden und erwartet wurden, um Sicherheitssensoren auszulösen und Warnungen zu generieren
* **Unerwünschte Software** : apps und andere Software, die nicht als bösartig eingestuft werden, andernfalls jedoch Richtlinien oder akzeptable Nutzungsstandards verletzen
* **Sonstiges** : jede andere Bestimmung, die nicht unter die angegebenen Typen fällt

Auf dieser Karte können Sie weitere Informationen im Microsoft Defender Security Center anzeigen.

![Karte für die Geräte Warnungs Ermittlung](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Grundlegendes zu den gefährdeten Geräten

Der **Geräteschutz** zeigt die Risikostufe für Geräte an. Die Risikostufe basiert auf Faktoren wie dem Typ und dem Schweregrad von Warnungen auf dem Gerät.

![Geräteschutz Karte](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Überwachen und melden des Status von InTune-verwalteten Geräten

Die folgenden Berichte enthalten Daten von Geräten, die in InTune registriert sind. Daten von nicht registrierten Geräten sind nicht enthalten. Nur globale Administratoren können diese Karten anzeigen.

Daten zu InTune-registrierten Geräten umfassen Folgendes:

* Gerätekompatibilität
* Geräte mit aktiver Schadsoftware
* Arten von Schadsoftware auf Geräten
* Schadsoftware auf Geräten
* Geräte mit Malware Erkennung
* Benutzer mit Malware Erkennung

### <a name="monitor-device-compliance"></a>Überwachen der Gerätekompatibilität

Die **Gerätekompatibilität** zeigt, wie viele Geräte, die in InTune registriert sind, den Konfigurationsrichtlinien entsprechen.

![Geräte Kompatibilitäts Karte](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Erkennen von Geräten mit Malwareerkennungen

**Erkennungen von Geräte-Schadsoftware** liefern die Anzahl von InTune-registrierten Geräten mit Schadsoftware, die noch nicht vollständig aufgelöst wurde. Ein Mangel an Auflösung kann aufgrund ausstehender Aktionen, eines Neustarts, einer vollständigen Überprüfung, manueller Benutzeraktionen oder wenn die Korrekturaktion nicht erfolgreich abgeschlossen wurde.

![Karte für die Erkennung von Geräte-Schadsoftware](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Grundlegendes zu den erkannten Malwaretypen

**Typen von Schadsoftware auf Geräten** zeigen verschiedene Arten von Schadsoftware auf, die auf Geräten erkannt wurden, die in InTune registriert sind. Sie können jeden Typ im Microsoft 365 Security Center untersuchen.

![Arten von Schadsoftware auf Geräte Karte](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Grundlegendes zur spezifischen auf Ihren Geräten erkannten Malware

**Malware auf Geräten** enthält eine Liste der spezifischen Schadsoftware, die auf Ihren Geräten erkannt wurde.

![Malware auf Geräte Karte](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Verstehen, welche Geräte die meisten Schadsoftware aufweisen

**Geräte mit Malwareerkennungen** zeigen, welche Geräte die meisten Malwareerkennungen aufweisen. im Microsoft 365 Security Center können Sie untersuchen, ob Schadsoftware aktiv ist, wer das Gerät verwendet und wie der Verwaltungsstatus in InTune.

![Geräte mit Schadsoftware-Erkennungskarte](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Verstehen, welche Benutzer Geräte mit den meisten Schadsoftware besitzen

**Benutzer mit Malwareerkennungen** zeigen Benutzern Geräte mit den meisten Malwareerkennungen. Im Microsoft 365 Security Center können Sie sehen, wie viele Geräte jedem Benutzer zugewiesen sind, und weitere Informationen zu jedem Gerät und dem Typ der Schadsoftware.

![Benutzer mit der Malware Erkennungskarte](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a>Überwachen und Verwalten der Bereitstellung und Erkennung von Angriffs Oberflächen Reduzierungs Regeln

[Regeln für die Angriffsflächen Reduzierung (ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) verhindern, dass Aktionen und apps, die in der Regel von Exploit sucht-Schadsoftware verwendet werden, Geräte infizieren. Mit diesen Regeln wird gesteuert, wann und wie ausführbare Dateien ausgeführt werden. So können Sie beispielsweise verhindern, dass JavaScript oder VBScript eine heruntergeladene ausführbare Datei startet, Win32-API-Aufrufe aus Office-Makros blockiert oder Prozesse blockiert, die von USB-Laufwerken ausgeführt werden.

![Angriffsfläche reduziert Karte](../../media/attack-surface-reduction-rules.png)

Die Karte **Regeln zur Verringerung der Angriffsfläche** bietet einen Überblick über die Bereitstellung von Regeln auf Ihren Geräten.

Die obere Leiste auf der Karte zeigt die Gesamtzahl der Geräte an, die sich in den folgenden Bereitstellungsmodi befinden:

* **Blockmodus** : Geräte mit mindestens einer Regel, die zum Blockieren der erkannten Aktivität konfiguriert ist
* **Überwachungsmodus** : Geräte, für die keine Regeln zum Blockieren der erkannten Aktivität festgelegt sind, aber mindestens eine Regel zum Überwachen der erkannten Aktivität festgelegt ist  
* **Off** : Geräte mit ausgeschalteten ASR-Regeln

Der untere Teil dieser Karte zeigt die Einstellungen nach Regeln auf Ihren Geräten an. Jeder Balken gibt die Anzahl der zu blockierenden Geräte an, die Überwachungs Erkennung, oder die Regel ist vollständig deaktiviert.

### <a name="view-asr-detections"></a>Anzeigen von ASR-Erkennungen

Wenn Sie detaillierte Informationen zu ASR-Regel Erkennungen in Ihrem Netzwerk anzeigen möchten, wählen Sie die Option **Erkennungen** auf der **Angriffsflächen Reduzierungs** Regelkarte anzeigen aus. Die Registerkarte **Erkennungen** auf der Seite detaillierter Bericht wird geöffnet.

![Registerkarte "Erkennungen"](../../media/detections-tab.png)

Im Diagramm oben auf der Seite werden Erkennungen im Laufe der Zeit angezeigt, die entweder blockiert oder überwacht wurden. Die Tabelle am unteren Rand listet die aktuellsten Erkennungen auf. Verwenden Sie die folgenden Informationen in der Tabelle, um die Art der Erkennungen zu verstehen:

* **Erkannte Datei** : die Datei, in der Regel ein Skript oder ein Dokument, dessen Inhalt die mutmaßliche Angriffs Aktivität ausgelöst hat
* **Regel** : Name, der die Angriffsaktivitäten beschreibt, die von der Regel erfasst werden sollen. Lesen Sie mehr über vorhandene ASR-Regeln
* **Quell-App** : die Anwendung, die Inhalte geladen oder ausgeführt hat, die die mutmaßliche Angriffs Aktivität ausgelöst haben. Es kann sich um eine legitime Anwendung wie Webbrowser, eine Office-Anwendung oder ein System Tool wie PowerShell handeln.
* **Herausgeber** : der Anbieter, der die Quell-APP freigegeben hat

### <a name="review-device-asr-rule-settings"></a>Überprüfen der Einstellungen für die Geräte ASR-Regel

Navigieren Sie auf der Seite " **Regeln für Angriffsfläche verringern** " zur Registerkarte " **Konfiguration** ", um die Regeleinstellungen für einzelne Geräte zu überprüfen. Wählen Sie ein Gerät aus, um detaillierte Informationen dazu zu erhalten, ob sich jede Regel im Blockmodus, im Überwachungsmodus oder ganz deaktiviert befindet.

![Registerkarte "Konfiguration"](../../media/configuration-tab.png)

Microsoft InTune bietet Verwaltungsfunktionen für Ihre ASR-Regeln. Wenn Sie Ihre Einstellungen aktualisieren möchten, wählen Sie unter **configure Devices** in the Tab **Erste Schritte** aus, um die Geräteverwaltung in InTune zu öffnen.

### <a name="exclude-files-from-asr-rules"></a>Ausschließen von Dateien aus ASR-Regeln

Microsoft 365 Security Center sammelt die Namen der [Dateien, die Sie möglicherweise](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) von Erkennungen nach Angriffs Oberflächen Reduzierungs Regeln ausschließen möchten. Durch das Ausschließen von Dateien können Sie falsch positive Erkennungen reduzieren und die Regeln für die Angriffs Oberflächenreduzierung im Blockmodus sicherer bereitstellen.

Die Ausschlüsse werden in Microsoft InTune verwaltet, das Microsoft 365 Security Center bietet jedoch ein Analyse Tool, mit dem Sie die Dateien besser verstehen. Um mit dem Sammeln von Dateien für den Ausschluss zu beginnen, navigieren Sie auf der Registerkarte **Ausnahmen hinzufügen** auf der Seite **Angriffs Regel Bericht für Angriffsfläche** .

>[!NOTE]  
>Das Tool analysiert Erkennungen nach allen Regeln für die Angriffs Oberflächenreduzierung, aber [nur einige Regeln unterstützen Ausschlüsse](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).

![Registerkarte "Ausschlüsse hinzufügen"](../../media/add-exclusions-tab.png)

In der Tabelle sind alle Dateinamen aufgeführt, die von den Regeln für Angriffs Oberflächenreduzierung erkannt wurden. Sie können Dateien auswählen, um die Auswirkungen zu überprüfen, die Sie ausschließen:

* Anzahl weniger Erkennungen
* Anzahl weniger Geräte melden die Erkennungen

Wenn Sie eine Liste der ausgewählten Dateien mit vollständigen Pfaden für den Ausschluss erhalten möchten, wählen Sie **Ausschluss Pfade abrufen** aus.

Protokolle für den ASR **-Regel Block Anmeldeinformationen, die vom Windows Local Security Authority Subsystem (lsass.exe) gestohlen** werden, erfassen die Quell-APP **lsass.exe**. Es handelt sich um eine normale System Datei, die jedoch als erkannte Datei erfasst wird. Daher enthält die generierte Liste der Ausschluss Pfade diese Datei. Verwenden Sie den Pfad zur Quell-APP anstelle der erkannten Datei, um die Datei auszuschließen, die diese Regel anstelle von **lsass.exe** ausgelöst hat.

Um die Quell-APP zu finden, führen Sie die folgende [erweiterte Suchabfrage](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) für diese spezielle Regel aus (identifiziert durch die Regel-ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Dateien auf Ausschluss überprüfen

Bevor Sie eine Datei von ASR ausschließen, sollten Sie die Datei überprüfen, um zu ermitteln, ob es sich tatsächlich nicht um bösartige Dateien handelt.

Verwenden Sie zum Überprüfen einer Datei die [Seite Dateiinformationen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) im Microsoft Defender Security Center. Die Seite enthält Informationen über die Prävalenz und das Antivirus-Erkennungs Verhältnis von virustotal. Sie können auch die Seite verwenden, um die Datei zur tiefen Analyse zu übermitteln.

Um eine erkannte Datei im Sicherheits Center von Microsoft Defender zu finden, suchen Sie mithilfe der folgenden erweiterten Suchabfrage nach allen ASR-Erkennungen:

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Verwenden Sie die **SHA1** oder **InitiatingProcessSHA1** in den Ergebnissen, um die Datei mithilfe der universellen Suchleiste im Microsoft Defender Security Center zu suchen.
