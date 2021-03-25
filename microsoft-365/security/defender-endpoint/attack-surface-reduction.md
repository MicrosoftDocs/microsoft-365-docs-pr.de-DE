---
title: Verwenden von Regeln zur Reduzierung der Angriffsfläche, um Schadsoftwareinfektionen zu verhindern
description: Regeln zur Reduzierung der Angriffsfläche können verhindern, dass Exploits Apps und Skripts verwenden, um Geräte mit Schadsoftware zu infizieren.
keywords: Regeln zur Reduzierung der Angriffsfläche, Asr, Hips, Host Intrusion Prevention System, Schutzregeln, Anti-Exploit, Antiexploit, Exploit, Infektionsschutz, Microsoft Defender for Endpoint, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 62f1f5f2d47482f642f00c870b3e0f3112f5f639
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185767"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>Verwenden von Regeln zur Reduzierung der Angriffsfläche, um Schadsoftwareinfektionen zu verhindern

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



## <a name="why-attack-surface-reduction-rules-are-important"></a>Warum Regeln zur Reduzierung der Angriffsfläche wichtig sind

Die Angriffsfläche Ihrer Organisation umfasst alle Orte, an denen ein Angreifer die Geräte oder Netzwerke Ihrer Organisation gefährdet. Die Reduzierung der Angriffsfläche bedeutet, die Geräte und das Netzwerk Ihrer Organisation zu schützen, wodurch Angreifer weniger Möglichkeiten haben, Angriffe durchzuführen. Das Konfigurieren von Regeln zur Reduzierung der Angriffsfläche in Microsoft Defender for Endpoint kann hilfreich sein!

Regeln zur Reduzierung der Angriffsfläche zielen auf bestimmte Softwareverhalten ab, z. B.:

- Starten von ausführbaren Dateien und Skripts, die versuchen, Dateien herunterzuladen oder auszuführen;
- Ausführen verschleierter oder anderweitig verdächtiger Skripts; und 
- Durchführen von Verhaltensweisen, die Apps normalerweise nicht während der normalen täglichen Arbeit initiieren.

Solche Softwareverhaltensmuster werden manchmal in legitimen Anwendungen gesehen. Diese Verhaltensweisen werden jedoch häufig als riskant betrachtet, da sie häufig von Angreifern durch Schadsoftware missbraucht werden. Regeln zur Reduzierung der Angriffsfläche können riskante Verhaltensweisen einschränken und ihre Organisation schützen.

Weitere Informationen zum Konfigurieren von Regeln zur Reduzierung der Angriffsfläche finden Sie unter [Enable attack surface reduction rules](enable-attack-surface-reduction.md).

## <a name="assess-rule-impact-before-deployment"></a>Bewerten der Auswirkungen der Regel vor der Bereitstellung  

Sie können bewerten, wie sich eine Regel zur Reduzierung der Angriffsfläche auf Ihr Netzwerk auswirken kann, indem Sie die Sicherheitsempfehlung für diese Regel im Bedrohungs- und [Sicherheitsrisikomanagement öffnen.](https://docs.microsoft.com/windows/security/threat-protection/#tvm) 

:::image type="content" source="images/asrrecommendation.png" alt-text="Sicherheits-Reco für die Regel zur Reduzierung der Angriffsfläche":::

Überprüfen Sie im Detailbereich der Empfehlung, ob die Auswirkungen auf den Benutzer beeinträchtigt werden, um zu ermitteln, welcher Prozentsatz Ihrer Geräte eine neue Richtlinie akzeptieren kann, die die Regel im Sperrmodus aktiviert, ohne die Produktivität zu beeinträchtigen.

## <a name="audit-mode-for-evaluation"></a>Überwachungsmodus für die Auswertung

Verwenden [Sie den Überwachungsmodus,](audit-windows-defender.md) um zu bewerten, wie sich Regeln zur Reduzierung der Angriffsfläche auf Ihre Organisation auswirken würden, wenn sie aktiviert würden. Führen Sie zuerst alle Regeln im Überwachungsmodus aus, damit Sie verstehen können, wie sich diese auf Ihre Geschäftsanwendungen auswirken. Viele Geschäftsanwendungen werden mit eingeschränkten Sicherheitsbedenken geschrieben, und sie können Aufgaben auf ähnliche Weise wie Schadsoftware ausführen. Durch überwachen von Überwachungsdaten und [Hinzufügen von Ausschlüssen](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) für erforderliche Anwendungen können Sie Regeln zur Reduzierung der Angriffsfläche bereitstellen, ohne die Produktivität zu reduzieren.

## <a name="warn-mode-for-users"></a>Warnmodus für Benutzer

(**NEU**!) Vor den Funktionen für den Warnmodus können aktivierte Regeln zur Reduzierung der Angriffsfläche entweder auf den Überwachungsmodus oder den Blockmodus festgelegt werden. Im neuen Warnmodus wird benutzern ein Dialogfeld angezeigt, das angibt, dass der Inhalt durch eine Regel zur Reduzierung der Angriffsfläche blockiert wird. Das Dialogfeld bietet dem Benutzer auch eine Option zum Aufheben der Blockierung des Inhalts. Der Benutzer kann dann seine Aktion wiederholen, und der Vorgang wird abgeschlossen. Wenn ein Benutzer die Blockierung von Inhalten aufgehoben hat, bleibt die Blockierung für 24 Stunden aufgehoben, und die Blockierung wird fortgesetzt.

Der Warnmodus hilft Ihrer Organisation, Regeln zur Reduzierung der Angriffsfläche zu verwenden, ohne zu verhindern, dass Benutzer auf die Inhalte zugreifen, die sie zum Ausführen ihrer Aufgaben benötigen. 

### <a name="requirements-for-warn-mode-to-work"></a>Anforderungen für den Warnmodus

Der Warnmodus wird auf Geräten mit den folgenden Versionen von Windows unterstützt:
- [Windows 10, Version 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) oder höher
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) oder höher
 
Microsoft Defender Antivirus muss mit Echtzeitschutz im [Aktiven Modus ausgeführt werden.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)

Stellen Sie außerdem sicher, [dass Microsoft Defender Antivirus- und Antischalwareupdates](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) installiert sind.
- Minimale Plattformfreigabeanforderung: `4.18.2008.9`  
- Mindestanforderung für die Modulfreigabe: `1.1.17400.5`

Weitere Informationen und Informationen zum Herunterladen Ihrer Updates finden Sie [unter Update for Microsoft Defender anmalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).

### <a name="cases-where-warn-mode-is-not-supported"></a>Fälle, in denen der Warnmodus nicht unterstützt wird

Der Warnmodus wird für die folgenden Regeln zur Reduzierung der Angriffsfläche nicht unterstützt:

- [Blockieren des Startens heruntergeladener ausführbarer](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) Inhalte (GUID) durch JavaScript oder VBScript `d3e037e1-3eb8-44c8-a917-57927947596d`
- [Blockieren der Persistenz über das WMI-Ereignisabonnement](#block-persistence-through-wmi-event-subscription) `e6db77e5-3df2-4cf1-b95a-636979351e5b` (GUID)
- [Verwenden des erweiterten Schutzes vor Ransomware](#use-advanced-protection-against-ransomware) (GUID) `c1db55ab-c21a-4637-bb3f-a12568109d35`

Darüber hinaus wird der Warnmodus auf Geräten mit älteren Versionen von Windows nicht unterstützt. In diesen Fällen werden Regeln zur Reduzierung der Angriffsfläche, die für die Ausführung im Warnmodus konfiguriert sind, im Blockmodus ausgeführt.

## <a name="notifications-and-alerts"></a>Benachrichtigungen und Warnungen

Wenn eine Regel zur Reduzierung der Angriffsfläche ausgelöst wird, wird auf dem Gerät eine Benachrichtigung angezeigt. Sie können [die Benachrichtigung mit](customize-attack-surface-reduction.md#customize-the-notification) Ihren Unternehmensdetails und Kontaktinformationen anpassen.

Darüber hinaus werden Warnungen generiert, wenn bestimmte Regeln zur Reduzierung der Angriffsfläche ausgelöst werden. 

Benachrichtigungen und generierte Warnungen können im Microsoft Defender Security Center ( ) und [https://securitycenter.windows.com](https://securitycenter.windows.com) im Microsoft 365 Security Center ( ) angezeigt werden. [https://security.microsoft.com](https://security.microsoft.com)

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Erweiterte Ereignisse zur Reduzierung der Suche und Angriffsfläche

Sie können die erweiterte Suche verwenden, um Ereignisse zur Reduzierung der Angriffsfläche zu sehen. Um das Volumen eingehender Daten zu optimieren, sind bei der erweiterten Suche nur eindeutige Prozesse für jede Stunde angezeigt. Die Uhrzeit eines Angriffsflächenreduzierungsereigniss ist das erste Mal, dass das Ereignis innerhalb der Stunde gesehen wird.

Angenommen, ein Ereignis zur Reduzierung der Angriffsfläche tritt während der 14:00 Uhr-Stunde auf 10 Geräten auf. Angenommen, das erste Ereignis ist um 2:15 Uhr und das letzte um 2:45 Uhr aufgetreten. Bei der erweiterten Suche wird eine Instanz dieses Ereignisses angezeigt (obwohl es tatsächlich auf 10 Geräten aufgetreten ist), und der Zeitstempel ist 14:15 Uhr. 

Weitere Informationen zur erweiterten Suche finden Sie unter [Proaktive Suche nach Bedrohungen mit erweiterter Suche.](advanced-hunting-overview.md)

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Features zur Reduzierung der Angriffsfläche in allen Windows-Versionen

Sie können Regeln zur Reduzierung der Angriffsfläche für Geräte festlegen, auf der eine der folgenden Editionen und Versionen von Windows ausgeführt wird:
- Windows 10 Pro, [Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows 10 Enterprise, [Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows Server, [Version 1803 (Halbjährskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) oder höher
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Obwohl Regeln zur Reduzierung der Angriffsfläche keine [Windows E5-Lizenz](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses)erfordern, erhalten Sie bei Windows E5 erweiterte Verwaltungsfunktionen. Diese Funktionen, die nur in Windows E5 verfügbar sind, umfassen Überwachung, Analyse und Workflows, die in [Defender for Endpoint](microsoft-defender-endpoint.md)verfügbar sind, sowie Berichterstellungs- und Konfigurationsfunktionen im Microsoft [365 Security Center](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center). Diese erweiterten Funktionen sind nicht mit einer Windows Professional- oder Windows E3-Lizenz verfügbar. Wenn Sie jedoch über diese Lizenzen verfügen, können Sie die Ereignisanzeige- und Microsoft Defender Antivirus-Protokolle verwenden, um Ihre Ereignisse der Regel zur Reduzierung der Angriffsfläche zu überprüfen.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a>Überprüfen von Ereignissen zur Reduzierung der Angriffsfläche im Microsoft Defender Security Center

Defender for Endpoint bietet detaillierte Berichte für Ereignisse und Blöcke im Rahmen von Warnungsuntersuchungsszenarien.

Sie können Defender for Endpoint-Daten mithilfe der erweiterten [Suche abfragen.](advanced-hunting-query-language.md) Wenn Sie den Überwachungsmodus [ausführen,](audit-windows-defender.md)können Sie die erweiterte Suche verwenden, um zu verstehen, wie sich Regeln zur Reduzierung der Angriffsfläche auf Ihre Umgebung auswirken können.

Hier ist eine Beispielabfrage:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Überprüfen von Ereignissen zur Reduzierung der Angriffsfläche in der Windows-Ereignisanzeige

Sie können das Windows-Ereignisprotokoll überprüfen, um Ereignisse zu sehen, die von Regeln zur Reduzierung der Angriffsfläche generiert wurden:

1. Laden Sie [das Evaluierungspaket](https://aka.ms/mp7z2w) herunter, und *extrahierencfa-events.xml* an einen leicht zugänglichen Speicherort auf dem Gerät.
2. Geben Sie die Wörter *Ereignisanzeige* in das Menü Start ein, um die Windows-Ereignisanzeige zu öffnen.
3. Wählen **Sie unter Aktionen** die Option **Benutzerdefinierte Ansicht importieren... aus.**
4. Wählen Sie die Datei *cfa-events.xml,* aus der sie extrahiert wurde. Alternativ können [Sie die XML direkt kopieren.](event-views.md)
5. Wählen Sie **OK** aus.

Sie können eine benutzerdefinierte Ansicht erstellen, die Ereignisse so filtert, dass nur die folgenden Ereignisse angezeigt werden, die alle im Zusammenhang mit dem kontrollierten Ordnerzugriff stehen:

|Ereignis-ID | Beschreibung |
|:---|:---|
|5007 | Ereignis, wenn Einstellungen geändert werden |
|1121 | Ereignis, wenn die Regel im Blockmodus gestartet wird |
|1122 | Ereignis, wenn die Regel im Überwachungsmodus abgeschaltet wird |

Die "Modulversion", die für Ereignisse zur Reduzierung der Angriffsfläche im Ereignisprotokoll aufgeführt ist, wird von Defender for Endpoint generiert, nicht vom Betriebssystem. Defender for Endpoint ist in Windows 10 integriert, sodass dieses Feature auf allen Geräten funktioniert, auf dem Windows 10 installiert ist.

## <a name="attack-surface-reduction-rules"></a>Regeln zur Verringerung der Angriffsfläche

In der folgenden Tabelle und in den Unterabschnitten werden die 15 Regeln zur Reduzierung der Angriffsfläche beschrieben. Die Regeln zur Reduzierung der Angriffsfläche werden in alphabetischer Reihenfolge nach Dem Namen der Regel aufgelistet. 

Wenn Sie Regeln zur Reduzierung der Angriffsfläche mithilfe von Gruppenrichtlinien oder PowerShell konfigurieren, benötigen Sie die GUIDs. Wenn Sie dagegen Microsoft Endpoint Manager oder Microsoft Intune verwenden, benötigen Sie die GUIDs nicht.


| Regelname | GUID | Datei- & Ordnerausschlüsse | Mindestens unterstütztes Betriebssystem |
|:-----|:-----:|:-----|:-----|
|[Adobe Reader am Erstellen von untergeordneten Prozessen hindern](#block-adobe-reader-from-creating-child-processes) | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern](#block-all-office-applications-from-creating-child-processes) | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Diebstahl von Anmeldeinformationen aus dem Subsystem für die lokale Sicherheitsautorität (lsass.exe) blockieren](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren](#block-executable-content-from-email-client-and-webmail) | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Ausführbare Dateien an der Ausführung hindern, außer sie erfüllen ein Verbreitungs-, Alters- oder vertrauenswürdige Listen-Kriterium](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | `01443614-cd74-433a-b99e-2ecdc07bfc25` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Ausführung potenziell verborgener Skripts blockieren](#block-execution-of-potentially-obfuscated-scripts) | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | `D3E037E1-3EB8-44C8-A917-57927947596D` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Office-Anwendungen am Erstellen ausführbarer Inhalte hindern](#block-office-applications-from-creating-executable-content) | `3B576869-A4EC-4529-8536-B80A7769E899` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern](#block-office-applications-from-injecting-code-into-other-processes) | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Office-Kommunikationsanwendung am Erstellen von untergeordneten Prozessen hindern](#block-office-communication-application-from-creating-child-processes) |`26190899-1602-49e8-8b27-eb1d0a1ce869` |Unterstützt |[Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher  |
|[Persistenz durch WMI-Ereignisabonnement blockieren](#block-persistence-through-wmi-event-subscription) | `e6db77e5-3df2-4cf1-b95a-636979351e5b` | Nicht unterstützt | [Windows 10, Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (Build 18362) oder höher |
|[Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren](#block-process-creations-originating-from-psexec-and-wmi-commands) | `d1e49aac-8f56-4280-b9ba-993a6d77406c` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren](#block-untrusted-and-unsigned-processes-that-run-from-usb) | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Win32-API-Aufrufe von Office-Makros blockieren](#block-win32-api-calls-from-office-macros) | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |
|[Erweiterten Schutz vor Ransomware verwenden](#use-advanced-protection-against-ransomware) | `c1db55ab-c21a-4637-bb3f-a12568109d35` | Unterstützt | [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher |

### <a name="block-adobe-reader-from-creating-child-processes"></a>Adobe Reader am Erstellen von untergeordneten Prozessen hindern

Diese Regel verhindert Angriffe, indem Adobe Reader am Erstellen von Prozessen hindert.

Mithilfe von Social Engineering oder Exploits kann Schadsoftware Nutzlasten herunterladen und starten und Adobe Reader ausbrechen. Indem verhindert wird, dass untergeordnete Prozesse von Adobe Reader generiert werden, wird die Verbreitung von Schadsoftware verhindert, die versucht, sie als Vektor zu verwenden.

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Intune-Name: `Process creation from Adobe Reader (beta)`

Configuration Manager-Name: Noch nicht verfügbar

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern

Mit dieser Regel wird verhindert, dass Office-Apps untergeordnete Prozesse erstellen. Office-Apps umfassen Word, Excel, PowerPoint, OneNote und Access.

Das Erstellen schädlicher untergeordneter Prozesse ist eine gängige Schadsoftwarestrategie. Bei Schadsoftware, die Office als Vektor missbraucht, werden häufig VBA-Makros ausgeführt und Code zum Herunterladen und Ausführen von weiteren Nutzlasten ausgenutzt. Einige legitime Geschäftsanwendungen können jedoch auch untergeordnete Prozesse für gutartige Zwecke generieren, z. B. das Erstellen einer Eingabeaufforderung oder die Verwendung von PowerShell zum Konfigurieren von Registrierungseinstellungen.

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-Name: `Office apps launching child processes`

Configuration Manager-Name: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Blockieren des Diebstahls von Anmeldeinformationen aus dem Subsystem der lokalen Windows-Sicherheitsbehörden

Diese Regel verhindert, dass Anmeldeinformationen gestohlen werden, indem der LSASS (Local Security Authority Subsystem Service) gesperrt wird.

LSASS authentifiziert Benutzer, die sich auf einem Windows-Computer anmelden. Microsoft Defender Credential Guard in Windows 10 verhindert normalerweise Versuche, Anmeldeinformationen aus LSASS zu extrahieren. Einige Organisationen können Credential Guard jedoch nicht auf allen Computern aktivieren, da Kompatibilitätsprobleme mit benutzerdefinierten Smartcardtreibern oder anderen Programmen auftreten, die in die lokale Sicherheitsbehörde (Local Security Authority, LSA) geladen werden. In diesen Fällen können Angreifer #A0 wie Mimikatz verwenden, um Klartextkennwörter und #A1 aus LSASS zu schrottieren.

> [!NOTE]
> In einigen Apps listet der Code alle ausgeführten Prozesse auf und versucht, sie mit vollständigen Berechtigungen zu öffnen. Diese Regel verweigert die Aktion zum Öffnen des Prozesses der App und protokolliert die Details im Sicherheitsereignisprotokoll. Diese Regel kann viel Rauschen erzeugen. Wenn Sie über eine App verfügen, die LSASS einfach aufzählt, aber keine wirklichen Auswirkungen auf die Funktionalität hat, ist es nicht erforderlich, sie der Ausschlussliste hinzuzufügen. Allein dieser Ereignisprotokolleintrag weist nicht unbedingt auf eine böswillige Bedrohung hin.

Diese Regel wurde eingeführt in:
- [Windows 10, Version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-Name: `Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager-Name: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren

Mit dieser Regel wird verhindert, dass die folgenden Dateitypen aus E-Mails gestartet werden, die in der Microsoft Outlook-Anwendung oder Outlook.com und anderen beliebten Webmailanbietern geöffnet werden:

- Ausführbare Dateien (z. B. EXE, DLL oder SCR)
- Skriptdateien (z. B. eine PowerShell-PS-, Visual Basic .vbs- oder JavaScript-JS-Datei)

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Microsoft Endpoint Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-Name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager-Name: `Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> Die Regel **Ausführbaren Inhalt von E-Mail-Client** und Webmail blockieren enthält die folgenden alternativen Beschreibungen, je nachdem, welche Anwendung Sie verwenden:
> - Intune (Konfigurationsprofile): Ausführung ausführbarer Inhalte (exe, dll, ps, js, vbs usw.) aus E-Mails (Webmail/E-Mail-Client) (keine Ausnahmen).
> - Endpoint Manager: Blockieren des Herunterladens ausführbarer Inhalte von E-Mail- und Webmailclients.
> - Gruppenrichtlinie: Blockieren ausführbarer Inhalte vom E-Mail-Client und webmail.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Ausführbare Dateien an der Ausführung hindern, außer sie erfüllen ein Verbreitungs-, Alters- oder vertrauenswürdige Listen-Kriterium

Diese Regel blockiert das Starten der folgenden Dateitypen, es sei denn, sie erfüllen die Prävalenz- oder Alterskriterien oder sind in einer vertrauenswürdigen Liste oder Ausschlussliste enthalten:

- Ausführbare Dateien (z. B. EXE, DLL oder SCR)

Das Starten nicht vertrauenswürdiger oder unbekannter ausführbarer Dateien kann riskant sein, da es anfangs nicht klar ist, ob die Dateien schädlich sind.

> [!IMPORTANT]
> Sie müssen [den in der Cloud übermittelten Schutz aktivieren,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) um diese Regel verwenden zu können. <br/><br/> Die Regel Ausführbare Dateien darf nicht ausgeführt werden, es sei **denn,** sie erfüllen ein Prävalenz-, Alters- oder vertrauenswürdiges Listenkriterium mit GUID gehört Microsoft und wird nicht von Administratoren `01443614-cd74-433a-b99e-2ecdc07bfc25` angegeben. Diese Regel verwendet den in der Cloud übermittelten Schutz, um seine vertrauenswürdige Liste regelmäßig zu aktualisieren.
>
>Sie können einzelne Dateien oder Ordner angeben (mithilfe von Ordnerpfaden oder vollqualifizierten Ressourcennamen), sie können jedoch nicht angeben, für welche Regeln oder Ausschlüsse gelten.

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-Name: `Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager-Name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Ausführung potenziell verborgener Skripts blockieren

Diese Regel erkennt verdächtige Eigenschaften in einem verschleierten Skript.

Skriptverschleierung ist eine gängige Technik, die sowohl Schadsoftwareautoren als auch legitime Anwendungen verwenden, um geistiges Eigentum auszublenden oder die Ladezeiten von Skripts zu verringern. Schadsoftwareautoren verwenden auch Verschleierung, um schädlichen Code zu erschweren, was eine genaue Überprüfung durch Menschen und Sicherheitssoftware verhindert.

Diese Regel wurde eingeführt in:
- [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-Name: `Obfuscated js/vbs/ps/macro code`

Configuration Manager-Name: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern

Diese Regel verhindert, dass Skripts potenziell schädliche heruntergeladene Inhalte starten. In JavaScript oder VBScript geschriebene Schadsoftware dient häufig als Downloader, um andere Schadsoftware aus dem Internet zu holen und zu starten.

Obwohl nicht üblich, verwenden Geschäftsbereichsanwendungen manchmal Skripts, um Installationsprogramme herunterzuladen und zu starten.

Diese Regel wurde eingeführt in:  
- [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-Name: `js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager-Name: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>Office-Anwendungen am Erstellen ausführbarer Inhalte hindern

Diese Regel hindert Office-Apps, einschließlich Word, Excel und PowerPoint, am Erstellen potenziell schädlicher ausführbarer Inhalte, indem verhindert wird, dass schädlicher Code auf den Datenträger geschrieben wird.

Schadsoftware, die Office als Vektor missbraucht, kann versuchen, Office zu brechen und schädliche Komponenten auf dem Datenträger zu speichern. Diese schädlichen Komponenten würden einen Neustart des Computers überstehen und auf dem System beibehalten. Daher wehrt sich diese Regel gegen eine gängige Persistenzmethode.

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM ist jetzt Microsoft Endpoint Configuration Manager)

Intune-Name: `Office apps/macros creating executable content`

SCCM-Name: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern

Diese Regel blockiert Codeinjektionsversuche von Office-Apps in andere Prozesse.

Angreifer versuchen möglicherweise, mithilfe von Office-Apps bösartigen Code mithilfe von Codeeinspritzung in andere Prozesse zu migrieren, sodass der Code als bereinigende Prozesse maskiert werden kann.

Es gibt keine bekannten legitimen Geschäftszwecke für die Verwendung von Codeeinspritzung.

Diese Regel gilt für Word, Excel und PowerPoint.

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-Name: `Office apps injecting code into other processes (no exceptions)`

Configuration Manager-Name: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>Office-Kommunikationsanwendung am Erstellen von untergeordneten Prozessen hindern

Diese Regel verhindert, dass Outlook untergeordnete Prozesse erstellt und gleichzeitig legitime Outlook-Funktionen zu lässt.

Diese Regel schützt vor Social Engineering-Angriffen und verhindert, dass Code missbraucht wird, um Sicherheitsrisiken in Outlook zu missbrauchen. Es schützt auch vor [Outlook-Regeln und Formular-Exploits,](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) die Angreifer verwenden können, wenn die Anmeldeinformationen eines Benutzers gefährdet sind.

> [!NOTE]
> Diese Regel gilt nur für Outlook und Outlook.com.

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Intune-Name: `Process creation from Office communication products (beta)`

Configuration Manager-Name: Nicht verfügbar

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>Persistenz durch WMI-Ereignisabonnement blockieren

Diese Regel verhindert, dass Schadsoftware WMI missbraucht, um dauerhaft auf einem Gerät zu bestehen.

> [!IMPORTANT]
> Datei- und Ordnerausschlüsse gelten nicht für diese Regel zur Reduzierung der Angriffsfläche.

Dateilose Bedrohungen verwenden verschiedene Taktiken, um ausgeblendet zu bleiben, um zu vermeiden, dass sie im Dateisystem angezeigt werden, und um eine regelmäßige Ausführungskontrolle zu erhalten. Einige Bedrohungen können das WMI-Repository und das Ereignismodell missbrauchen, um ausgeblendet zu bleiben.

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Server 1903](https://docs.microsoft.com/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Intune-Name: Nicht verfügbar

Configuration Manager-Name: Nicht verfügbar

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren

Diese Regel blockiert die Ausführung von Prozessen, die über [PsExec und](https://docs.microsoft.com/sysinternals/downloads/psexec) [WMI](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) erstellt wurden. Sowohl PsExec als auch WMI können Code remote ausführen, sodass das Risiko besteht, dass Schadsoftware diese Funktionalität zu Befehls- und Kontrollzwecken missbraucht oder eine Infektion im Netzwerk einer Organisation verteilt.

> [!WARNING]
> Verwenden Sie diese Regel nur, wenn Sie Ihre Geräte mit [Intune](https://docs.microsoft.com/intune) oder einer anderen MDM-Lösung verwalten. Diese Regel ist mit der Verwaltung über [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr) nicht kompatibel, da diese Regel WMI-Befehle blockiert, die vom Configuration Manager-Client verwendet werden, um ordnungsgemäß zu funktionieren.

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Intune-Name: `Process creation from PSExec and WMI commands`

Configuration Manager-Name: Nicht zutreffend

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren

Mit dieser Regel können Administratoren verhindern, dass nicht signierte oder nicht vertrauenswürdige ausführbare Dateien von USB-Wechseldatenträgern ausgeführt werden, einschließlich SD-Karten. Blockierte Dateitypen umfassen ausführbare Dateien (z. B. EXE, DLL oder SCR)

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-Name: `Untrusted and unsigned processes that run from USB`

Configuration Manager-Name: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Win32-API-Aufrufe von Office-Makros blockieren

Diese Regel verhindert, dass VBA-Makros Win32-APIs aufrufen.

Office VBA aktiviert Win32-API-Aufrufe. Schadsoftware kann diese Funktion missbrauchen, z. B. [win32-APIs](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) aufrufen, um schädlichen Shellcode zu starten, ohne etwas direkt auf den Datenträger zu schreiben. Die meisten Organisationen verlassen sich nicht auf die Möglichkeit, Win32-APIs im täglichen Betrieb aufrufen zu können, auch wenn sie Makros auf andere Weise verwenden.

Diese Regel wurde eingeführt in:
- [Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-Name: `Win32 imports from Office macro code`

Configuration Manager-Name: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>Erweiterten Schutz vor Ransomware verwenden

Diese Regel bietet eine zusätzliche Schutzebene vor Ransomware. Es überprüft ausführbare Dateien, die in das System ein- und ausgeführt werden, um festzustellen, ob sie vertrauenswürdig sind. Wenn die Dateien Ransomware sehr ähnlich sind, wird die Ausführung durch diese Regel blockiert, es sei denn, sie sind in einer vertrauenswürdigen Liste oder einer Ausschlussliste enthalten.

> [!NOTE]
> Sie müssen [den in der Cloud übermittelten Schutz aktivieren,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) um diese Regel verwenden zu können.

Diese Regel wurde eingeführt in: 
- [Windows 10, Version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, Version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-Name: `Advanced ransomware protection`

Configuration Manager-Name: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

## <a name="see-also"></a>Siehe auch

- [Häufig gestellte Fragen zur Reduzierung der Angriffsfläche](attack-surface-reduction-faq.md)
- [Aktivieren von Regeln zur Reduzierung der Angriffsfläche](enable-attack-surface-reduction.md)
- [Bewerten von Regeln zur Reduzierung der Angriffsfläche](evaluate-attack-surface-reduction.md)
- [Kompatibilität von Microsoft Defender Antivirus mit anderen Antiviren-/Antischalwarelösungen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
