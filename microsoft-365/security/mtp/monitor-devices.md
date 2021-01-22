---
title: Geräteüberwachung & Berichterstellung – Security Center
description: Beschreibt, wie Sie Ihre Geräte sicher, auf dem neuesten Stand halten und potenzielle Bedrohungen in Ihrer Organisation erkennen können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Security Center, Überwachen, Bericht, Geräte
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930498"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Geräteüberwachung und Berichterstellung im Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Schützen Sie Ihre Geräte, halten Sie sie auf dem neuesten Stand und erkennen Sie potenzielle Bedrohungen im Microsoft 365 Security Center.

## <a name="view-device-alerts"></a>Anzeigen von Gerätewarnungen

Erhalten Sie aktuelle Warnungen zu Sicherheitsverletzungen und anderen Bedrohungen auf Ihren Geräten von Microsoft Defender for Endpoint (verfügbar mit einer E5-Lizenz). Microsoft 365 Security Center überwacht diese Warnungen mithilfe Ihres bevorzugten Workflows effektiv auf hoher Ebene.

### <a name="monitor-high-impact-alerts"></a>Überwachen von Warnungen mit hoher Auswirkung

Jede Microsoft Defender for Endpoint-Warnung hat einen entsprechenden Schweregrad (hoch, mittel, niedrig oder informationell). Dies weist auf potenzielle Auswirkungen auf Ihr Netzwerk hin, wenn sie unbeaufsichtigt bleiben.  

Verwenden Sie **die Karte mit dem Schweregrad der** Gerätewarnung, um sich speziell auf Warnungen zu konzentrieren, die schwerwiegender sind und eine sofortige Reaktion erfordern. Auf dieser Karte können Sie weitere Informationen im Microsoft Defender Security Center-Portal anzeigen.

![Karte zum Schweregrad von Gerätewarnungen](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Verstehen der Quellen von Warnungen

Microsoft Defender for Endpoint nutzt Daten aus einer Vielzahl von Sicherheitssensoren und Intelligencequellen, um Warnungen zu generieren. Beispielsweise können Erkennungsinformationen von Microsoft Defender Antivirus und Antischsoftware von Drittanbietern verwendet werden. Sie kann auch Ihre eigene benutzerdefinierte Bedrohungsintelligenz verwenden, die über die Webdienst-API bereitgestellt wird.

Die **Karte "Gerätewarnungserkennungsquellen"** zeigt die Verteilung von Warnungen nach Quelle an. Verfolgen Sie Aktivitäten im Zusammenhang mit bestimmten Quellen, insbesondere Ihren benutzerdefinierten Quellen. Sie können die Karte auch verwenden, um sich auf Warnungen von Sensoren zu konzentrieren, die nicht so konfiguriert sind, dass schädliche Aktivitäten oder Komponenten automatisch blockiert werden.

![Karte für Gerätewarnungserkennungsquellen](../../media/device-alert-detection-sources.png)

Auf dieser Karte können Sie weitere Informationen im Microsoft Defender Security Center-Portal anzeigen.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Verstehen der Arten von Bedrohungen, die Warnungen auslösen

Microsoft Defender for Endpoint sortiert jede Warnung in eine Kategorie, die eine bestimmte Phase in der Angriffskette oder den Typ der Bedrohungskomponente darstellt. Beispielsweise kann eine erkannte Bedrohungsaktivität als "laterale Bewegung" kategorisiert werden, um anzuzeigen, dass versucht wurde, andere Geräte im Netzwerk zu erreichen. Die Aktivität ist wahrscheinlich aufgetreten, nachdem Angreifer einen anfänglichen Fußweg gewonnen haben. Wenn eine Bedrohungskomponente erkannt wird, kann sie allgemein als Schadsoftware oder speziell als bestimmter Bedrohungstyp klassifiziert werden. Zu den Besonderheiten gehören Ransomware, Diebstahl von Anmeldeinformationen oder andere Arten von schadhafter oder unerwünschter Software.

Die **Karte "Gerätebedrohungskategorien"** zeigt die Verteilung von Warnungen in diese Kategorien an. Verwenden Sie diese Informationen, um Bedrohungsaktivitäten zu identifizieren, z. B. Versuche des Diebstahls von Anmeldeinformationen, die in der Regel größere Auswirkungen haben als Social Engineering-Versuche. Sie können auch auf potenziell schädliche Bedrohungen wie Ransomware überwachen.

![Karte "Gerätebedrohungskategorien"](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Überwachen aktiver Warnungen

Die **Statuskarte für Gerätewarnungen** gibt die Anzahl der Warnungen an, die nicht aufgelöst wurden und möglicherweise Aufmerksamkeit erfordern. Auf dieser Karte können Sie weitere Informationen im Microsoft Defender Security Center-Portal anzeigen.

![Statuskarte für Gerätewarnungen](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Überwachen der Klassifizierung aufgelöster Warnungen

Beim Auflösen einer Microsoft Defender for Endpoint-Warnung können Ihre Sicherheitsmitarbeiter angeben, ob eine Warnung wie folgt überprüft wurde:

* Eine echte Warnung, die tatsächliche Sicherheitsverletzungen oder Bedrohungskomponenten identifiziert
* Eine falsche Warnung, die normale Aktivität fälschlicherweise erkannt hat

Die **Klassifizierungskarte für Gerätewarnungen** zeigt an, ob ihre aufgelösten Warnungen als "wahr" oder "Falsch" klassifiziert wurden. Auf dieser Karte können Sie weitere Informationen im Microsoft Defender Security Center-Portal anzeigen.

Hinweis: In einigen Fällen sind Klassifizierungsinformationen für bestimmte Warnungen nicht verfügbar.

![Klassifizierungskarte für Gerätewarnungen](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Überwachen der Ermittlung aufgelöster Warnungen

Neben der Klassifizierung, ob eine Warnung während der Auflösung wahr oder falsch ist, können Ihre Sicherheitsmitarbeiter eine Bestimmung bereitstellen. Eine Bestimmung gibt den Typ normaler oder böswilliger Aktivitäten an, die bei der Validierung der Warnung gefunden wurden.

Die **Karte zur Ermittlung von Gerätewarnungen** zeigt die Für jede Warnung bereitgestellte Bestimmung an.

* **APT:** erweiterte dauerhafte Bedrohung, die angibt, dass die erkannte Aktivität oder Bedrohungskomponente Teil einer ausgeklügelten Verletzung ist, die dazu dient, im betroffenen Netzwerk Fuß zu fassen.  
* **Schadsoftware:** schädliche Datei oder Code
* **Sicherheitspersonal:** normale Aktivitäten, die von Sicherheitsmitarbeitern ausgeführt werden
* **Sicherheitstests:** Aktivitäten oder Komponenten, die zur Simulation tatsächlicher Bedrohungen entwickelt wurden und voraussichtlich Sicherheitssensoren auslösen und Warnungen generieren
* **Unerwünschte Software:** Apps und andere Software, die nicht als bösartig betrachtet werden, aber andernfalls gegen Richtlinien oder akzeptable Nutzungsstandards verstoßen
* **Sonstiges:** jede andere Bestimmung, die nicht unter die bereitgestellten Typen fällt

Auf dieser Karte können Sie weitere Informationen im Microsoft Defender Security Center anzeigen.

![Karte zur Ermittlung von Gerätewarnungen](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Verstehen, welche Geräte gefährdet sind

**Der Geräteschutz** zeigt die Risikostufe für Geräte an. Die Risikostufe basiert auf Faktoren wie Art und Schweregrad von Warnungen auf dem Gerät.

![Geräteschutzkarte](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Überwachen und Melden des Status von von Intune verwalteten Geräten

Die folgenden Berichte enthalten Daten von Geräten, die in Intune registriert sind. Daten von nicht registrierungsierten Geräten sind nicht enthalten. Nur globale Administratoren können diese Karten anzeigen.

Zu den in Intune registrierten Gerätedaten gehören:

* Gerätekompatibilität
* Geräte mit aktiver Schadsoftware
* Arten von Schadsoftware auf Geräten
* Schadsoftware auf Geräten
* Geräte mit Schadsoftwareerkennungen
* Benutzer mit Schadsoftwareerkennungen

### <a name="monitor-device-compliance"></a>Überwachen der Gerätekonformität

**Die Gerätekonformität** zeigt, wie viele Geräte, die in Intune registriert sind, Konfigurationsrichtlinien einhalten.

![Gerätekonformitätskarte](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Ermitteln von Geräten mit Schadsoftwareerkennungen

**Schadsoftwareerkennungen** für Geräte stellen die Anzahl der in Intune registrierten Geräte mit Schadsoftware zur Verfügung, die noch nicht vollständig aufgelöst wurde. Eine fehlende Lösung kann auf ausstehende Aktionen, einen Neustart, einen vollständigen Scan, manuelle Benutzeraktionen oder darauf, dass die Korrekturaktion nicht erfolgreich abgeschlossen wurde, sein.

![Karte "Erkennung von Schadsoftware für Geräte"](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Verstehen der erkannten Schadsoftwaretypen

**Arten von Schadsoftware auf** Geräten zeigen verschiedene Arten von Schadsoftware, die auf Geräten erkannt wurden, die in Intune registriert sind. Sie können jeden Typ im Microsoft 365 Security Center untersuchen.

![Arten von Schadsoftware auf Gerätekarte](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Verstehen der spezifischen Schadsoftware, die auf Ihren Geräten erkannt wird

**Schadsoftware auf** Geräten bietet eine Liste der spezifischen Schadsoftware, die auf Ihren Geräten erkannt wird.

![Karte "Schadsoftware auf Geräten"](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Verstehen, welche Geräte am häufigsten Schadsoftware enthalten

**Geräte mit Schadsoftwareerkennungen** zeigen, welche Geräte die meisten Schadsoftwareerkennungen haben. im Microsoft 365 Security Center können Sie untersuchen, ob Schadsoftware aktiv ist, wer das Gerät verwendet, und dessen Verwaltungsstatus in Intune.

![Karte "Geräte mit Schadsoftwareerkennung"](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Verstehen, welche Benutzer Geräte mit der meisten Schadsoftware haben

**Benutzer mit Schadsoftwareerkennungen** zeigen Benutzern mit Geräten mit den meisten Schadsoftwareerkennungen an. Im Microsoft 365 Security Center können Sie sehen, wie viele Geräte jedem Benutzer zugewiesen sind, sowie weitere Informationen zu jedem Gerät und der Art von Schadsoftware.

![Benutzer mit Karte zur Erkennung von Schadsoftware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a>Überwachen und Verwalten der Bereitstellung und Erkennung von Regeln zur Reduzierung der Angriffsfläche

[Attack Surface Reduction (ASR)-Regeln](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) verhindern Aktionen und Apps, die in der Regel von Schadsoftware verwendet werden, um Geräte zu infizieren. Mit diesen Regeln wird gesteuert, wann und wie ausführbare Dateien ausgeführt werden. So können Sie beispielsweise verhindern, dass JavaScript oder VBScript eine heruntergeladene ausführbare Datei startet, Win32-API-Aufrufe aus Office-Makros blockiert oder Prozesse blockiert, die von USB-Laufwerken ausgeführt werden.

![Karte zur Reduzierung der Angriffsfläche](../../media/attack-surface-reduction-rules.png)

Die Karte **Regeln zur Verringerung der Angriffsfläche** bietet einen Überblick über die Bereitstellung von Regeln auf Ihren Geräten.

Die obere Leiste auf der Karte zeigt die Gesamtzahl der Geräte an, die sich in den folgenden Bereitstellungsmodi befinden:

* **Blockmodus:** Geräte mit mindestens einer Regel, die so konfiguriert sind, dass erkannte Aktivitäten blockiert werden
* **Überwachungsmodus:** Geräte ohne Regeln, die zum Blockieren erkannter Aktivitäten festgelegt sind, aber mindestens einen Regelsatz zum Überwachen der erkannten Aktivität haben  
* **Aus:** Geräte mit deaktivierten AsR-Regeln

Der untere Teil dieser Karte zeigt die Einstellungen nach Regeln auf Ihren Geräten an. Jede Leiste gibt die Anzahl der Geräte an, die zum Blockieren, Überwachen der Erkennung oder zum vollständigen Deaktivieren der Regel festgelegt sind.

### <a name="view-asr-detections"></a>Anzeigen von ASR-Erkennungen

Wählen Sie zum Anzeigen detaillierter Informationen zu Erkennungen von ASR-Regeln in Ihrem Netzwerk die Option "Erkennungen anzeigen" auf der **Regelkarte** zur Reduzierung der **Angriffsfläche** aus. Die **Registerkarte "Erkennungen"** auf der detaillierten Berichtsseite wird geöffnet.

![Registerkarte "Erkennungen"](../../media/detections-tab.png)

Das Diagramm oben auf der Seite zeigt Erkennungen im Laufe der Zeit beim Stapeln von Erkennungen, die entweder blockiert oder überwacht wurden. Die Tabelle am unteren Rand listet die aktuellsten Erkennungen auf. Verwenden Sie die folgenden Informationen in der Tabelle, um die Art der Erkennungen zu verstehen:

* **Erkannte Datei:** die Datei, in der Regel ein Skript oder Dokument, deren Inhalt die mutmaßliche Angriffsaktivität ausgelöst hat
* **Regel:** Name, der die Angriffsaktivitäten beschreibt, auf die die Regel ausgelegt ist. Informationen zu vorhandenen AsR-Regeln
* **Quell-App:** die Anwendung, die Inhalte geladen oder ausgeführt hat, die die mutmaßliche Angriffsaktivität auslösen. Dies kann eine legitime Anwendung sein, z. B. ein Webbrowser, eine Office-Anwendung oder ein Systemtool wie PowerShell.
* **Herausgeber:** der Anbieter, der die Quell-App veröffentlicht hat

### <a name="review-device-asr-rule-settings"></a>Überprüfen der Geräte-ASR-Regeleinstellungen

Wechseln Sie **auf der Seite "Attack Surface Reduction Rules"** zur Registerkarte **"Konfiguration",** um die Regeleinstellungen für einzelne Geräte zu überprüfen. Wählen Sie ein Gerät aus, um detaillierte Informationen darüber zu erhalten, ob sich jede Regel im Sperrmodus, Überwachungsmodus oder vollständig deaktiviert befindet.

![Registerkarte "Konfiguration"](../../media/configuration-tab.png)

Microsoft Intune bietet Verwaltungsfunktionen für Ihre ASR-Regeln. Wenn Sie Ihre Einstellungen aktualisieren möchten, wählen Sie unter **"Geräte** **konfigurieren"** auf der Registerkarte "Erste Schritte" aus, um die Geräteverwaltung in Intune zu öffnen.

### <a name="exclude-files-from-asr-rules"></a>Ausschließen von Dateien von ASR-Regeln

Das Microsoft 365 Security Center [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) sammelt die Namen der Dateien, die Sie möglicherweise von Erkennungen durch Regeln zur Reduzierung der Angriffsfläche ausschließen möchten. Wenn Sie Dateien ausschließen, können Sie falsch positive Erkennungen reduzieren und Angriffsflächenreduzierungsregeln im Blockmodus sicherer bereitstellen.

Die Ausschlüsse werden in Microsoft Intune verwaltet, aber Microsoft 365 Security Center bietet ein Analysetool, mit dem Sie die Dateien besser verstehen können. To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.

>[!NOTE]  
>Das Tool analysiert Erkennungen durch alle Regeln zur Reduzierung der Angriffsfläche, aber [nur einige Regeln unterstützen Ausschlüsse.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)

![Registerkarte "Ausschlüsse hinzufügen"](../../media/add-exclusions-tab.png)

In der Tabelle sind alle Dateinamen aufgeführt, die von den Regeln zur Reduzierung der Angriffsfläche erkannt werden. Sie können Dateien auswählen, um die Auswirkungen des Ausschließens zu überprüfen:

* Wie viele Erkennungen weniger
* Wie viele geräte melden die Erkennungen

Um eine Liste der ausgewählten Dateien mit ihren vollständigen Pfaden für den Ausschluss zu erhalten, wählen **Sie Ausschlusspfade erhalten aus.**

Protokolle für die ASR-Regel Zum Blockieren von Anmeldeinformationen, die aus dem Subsystem der lokalen Sicherheitsbehörde **(lsass.exe)** von Windows gestohlen werden, erfassen die **Quell-App-lsass.exe.** Es handelt sich um eine normale Systemdatei, die jedoch als erkannte Datei erfasst wird. Daher enthält die generierte Liste der Ausschlusspfade diese Datei. Wenn Sie die Datei, die diese Regel ausgelöst hat, anstellelsass.exe **ausschließen** möchten, verwenden Sie den Pfad zur Quell-App anstelle der erkannten Datei.

Führen Sie zum Suchen der [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) Quell-App die folgende Erweiterte Suchabfrage für diese bestimmte Regel aus (identifiziert durch regel-ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Überprüfen von Dateien auf Ausschluss

Bevor Sie eine Datei von ASR ausschließen, sollten Sie die Datei überprüfen, um festzustellen, ob sie wirklich nicht schädlich ist.

Um eine Datei zu überprüfen, verwenden Sie die [Dateiinformationsseite im](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) Microsoft Defender Security Center. Die Seite enthält Verbreitungsinformationen und das Virentotal-Antiviruserkennungsverhältnis. Sie können auch die Seite verwenden, um die Datei für eine tiefgehende Analyse zu übermitteln.

Um eine erkannte Datei im Microsoft Defender Security Center zu finden, suchen Sie mithilfe der folgenden erweiterten Suchabfrage nach allen ASR-Erkennungen:

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Verwenden Sie **SHA1** oder **InitiierenProcessSHA1** in den Ergebnissen, um mithilfe der universellen Suchleiste im Microsoft Defender Security Center nach der Datei zu suchen.
