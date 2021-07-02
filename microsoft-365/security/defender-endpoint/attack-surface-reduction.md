---
title: Verwenden von Regeln zur Verringerung der Angriffsfläche, um eine Infektion durch Schadsoftware zu verhindern
description: Regeln zur Verringerung der Angriffsfläche können dazu beitragen, zu verhindern, dass Exploits Apps und Skripts verwenden, um Geräte mit Schadsoftware zu infizieren.
keywords: Attack Surface Reduction-Regeln, Asr, Hips, Host Intrusion Prevention System, Schutzregeln, Anti-Exploit, Antiexploit, Exploit, Infektionsverhinderung, Microsoft Defender für Endpunkt
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ed6dc9956c3e78f8ed39dca9cd6bf0421dd28456
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276989"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>Verwenden von Regeln zur Verringerung der Angriffsfläche, um eine Infektion durch Schadsoftware zu verhindern

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>Warum Regeln zur Verringerung der Angriffsfläche wichtig sind

Die Angriffsfläche Ihrer Organisation umfasst alle Stellen, an denen ein Angreifer die Geräte oder Netzwerke Ihrer Organisation kompromittieren könnte. Die Reduzierung der Angriffsfläche bedeutet, die Geräte und das Netzwerk Ihrer Organisation zu schützen, sodass Angreifer weniger Möglichkeiten haben, Angriffe auszuführen. Das Konfigurieren von Regeln zur Verringerung der Angriffsfläche in Microsoft Defender für Endpunkt kann hilfreich sein!

Regeln zur Verringerung der Angriffsfläche zielen auf bestimmte Softwareverhalten ab, z. B.:

- Starten von ausführbaren Dateien und Skripts, die versuchen, Dateien herunterzuladen oder auszuführen
- Ausführen verborgener oder anderweitig verdächtiger Skripts
- Ausführen von Verhaltensweisen, die Apps in der Regel während der normalen täglichen Arbeit nicht initiieren

Solche Softwareverhaltensweisen werden manchmal in legitimen Anwendungen angezeigt. Diese Verhaltensweisen werden jedoch häufig als riskant betrachtet, da sie häufig von Angreifern durch Schadsoftware missbraucht werden. Regeln zur Verringerung der Angriffsfläche können softwarebasiertes riskantes Verhalten einschränken und dazu beitragen, ihre Organisation zu schützen.

Weitere Informationen zum Konfigurieren von Regeln zur Verringerung der Angriffsfläche finden Sie unter Aktivieren von [Regeln zur Verringerung der Angriffsfläche.](enable-attack-surface-reduction.md)

## <a name="assess-rule-impact-before-deployment"></a>Bewerten der Auswirkungen auf die Regel vor der Bereitstellung

Sie können bewerten, wie sich eine Regel zur Verringerung der Angriffsfläche auf Ihr Netzwerk auswirken kann, indem Sie die Sicherheitsempfehlungen für diese Regel in [Bedrohungs- und Sicherheitsrisikomanagement](/windows/security/threat-protection/#tvm)öffnen.

:::image type="content" source="images/asrrecommendation.png" alt-text="Sicherheitsreco für Attack Surface Reduction-Regel":::

Überprüfen Sie im Bereich mit den Empfehlungsdetails, welche Auswirkungen auf die Benutzer haben, um festzustellen, welcher Prozentsatz Ihrer Geräte eine neue Richtlinie akzeptieren kann, die die Regel im Blockierungsmodus aktiviert, ohne die Produktivität zu beeinträchtigen.

Weitere Informationen zu unterstützten Betriebssystemen und zusätzliche Anforderungsinformationen finden Sie unter ["Anforderungen"](enable-attack-surface-reduction.md#requirements) im Artikel "Attack Surface Reduction-Regeln aktivieren".

## <a name="audit-mode-for-evaluation"></a>Überwachungsmodus für die Auswertung

Verwenden Sie [den Überwachungsmodus,](audit-windows-defender.md) um zu bewerten, wie sich Regeln zur Verringerung der Angriffsfläche auf Ihre Organisation auswirken, wenn sie aktiviert sind. Führen Sie zuerst alle Regeln im Überwachungsmodus aus, damit Sie verstehen können, wie sich diese auf Ihre Branchenanwendungen auswirken. Viele Branchenanwendungen sind mit eingeschränkten Sicherheitsbedenken geschrieben und führen möglicherweise Aufgaben auf ähnliche Weise wie Schadsoftware aus. Durch die Überwachung von Überwachungsdaten und [das Hinzufügen von Ausschlüssen](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) für erforderliche Anwendungen können Sie Regeln zur Verringerung der Angriffsfläche bereitstellen, ohne die Produktivität zu verringern.

## <a name="warn-mode-for-users"></a>Warnmodus für Benutzer

(**NEU**!) Vor den Funktionen des Warnmodus können aktivierte Regeln für die Verringerung der Angriffsfläche entweder auf den Überwachungsmodus oder den Blockierungsmodus festgelegt werden. Mit dem neuen Warnmodus wird Benutzern bei jeder Blockierung von Inhalten durch eine Regel zur Verringerung der Angriffsfläche ein Dialogfeld angezeigt, das angibt, dass der Inhalt blockiert ist. Das Dialogfeld bietet dem Benutzer auch die Möglichkeit, die Blockierung des Inhalts aufzuheben. Der Benutzer kann dann seine Aktion wiederholen, und der Vorgang wird abgeschlossen. Wenn ein Benutzer die Blockierung von Inhalten freigibt, bleibt der Inhalt 24 Stunden lang entsperrt, und dann wird die Fortsetzung blockiert.

Der Warnmodus hilft Ihrer Organisation bei der Anwendung von Regeln zur Verringerung der Angriffsfläche, ohne dass Benutzer auf die Inhalte zugreifen können, die sie zum Ausführen ihrer Aufgaben benötigen.

### <a name="requirements-for-warn-mode-to-work"></a>Anforderungen für die Funktion des Warnmodus

Der Warnmodus wird auf Geräten unterstützt, auf denen die folgenden Versionen von Windows ausgeführt werden:

- [Windows 10, Version 1809](/windows/whats-new/whats-new-windows-10-version-1809) oder höher
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809) oder höher

Microsoft Defender Antivirus muss mit Echtzeitschutz im aktiven [Modus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)ausgeführt werden.

Stellen Sie außerdem sicher, dass [Microsoft Defender Antivirus- und Antischadsoftwareupdates](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) installiert sind.

- Mindestanforderung für die Plattformversion: `4.18.2008.9`
- Mindestanforderung für die Veröffentlichung des Moduls: `1.1.17400.5`

Weitere Informationen und Zum Abrufen Ihrer Updates finden Sie unter [Update für die Microsoft Defender-Antischadsoftwareplattform.](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)

### <a name="cases-where-warn-mode-is-not-supported"></a>Fälle, in denen der Warnmodus nicht unterstützt wird

Der Warnmodus wird für drei Regeln zur Verringerung der Angriffsfläche nicht unterstützt, wenn Sie sie in Microsoft Endpoint Manager konfigurieren. (Wenn Sie gruppenrichtlinien verwenden, um die Regeln zur Verringerung der Angriffsfläche zu konfigurieren, wird der Warnmodus unterstützt.) Die drei Regeln, die den Warnmodus nicht unterstützen, wenn Sie sie in Microsoft Endpoint Manager konfigurieren, sind wie folgt:

- [Verhindern, dass JavaScript oder VBScript heruntergeladene ausführbare Inhalte](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID) startet `d3e037e1-3eb8-44c8-a917-57927947596d`
- [Blockieren der Persistenz über das WMI-Ereignisabonnement](#block-persistence-through-wmi-event-subscription) `e6db77e5-3df2-4cf1-b95a-636979351e5b` (GUID)
- [Verwenden des erweiterten Schutzes vor Ransomware](#use-advanced-protection-against-ransomware) (GUID) `c1db55ab-c21a-4637-bb3f-a12568109d35`

Darüber hinaus wird der Warnmodus auf Geräten mit älteren Versionen von Windows nicht unterstützt. In diesen Fällen werden Attack Surface Reduction-Regeln, die für die Ausführung im Warnmodus konfiguriert sind, im Blockierungsmodus ausgeführt.

## <a name="notifications-and-alerts"></a>Benachrichtigungen und Warnungen

Wenn eine Regel zur Verringerung der Angriffsfläche ausgelöst wird, wird eine Benachrichtigung auf dem Gerät angezeigt. Mit Ihren Unternehmensdetails und Kontaktinformationen können Sie [die Benachrichtigung anpassen](customize-attack-surface-reduction.md#customize-the-notification).

Wenn außerdem bestimmte Regeln zur Verringerung der Angriffsfläche ausgelöst werden, werden Warnungen generiert.

Benachrichtigungen und generierte Warnungen können im Microsoft 365 Defender-Portal ( [https://security.microsoft.com](https://security.microsoft.com) ) (früher [Microsoft Defender Security Center](microsoft-defender-security-center.md)genannt) angezeigt werden.

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Erweiterte Suche und Attack Surface Reduction-Ereignisse

Sie können die erweiterte Suche verwenden, um Attack Surface Reduction-Ereignisse anzuzeigen. Um das Volumen der eingehenden Daten zu optimieren, können mit der erweiterten Suche nur eindeutige Prozesse pro Stunde angezeigt werden. Die Zeit eines Attack Surface Reduction-Ereignisses ist das erste Mal, dass das Ereignis innerhalb der Stunde angezeigt wird.

Nehmen wir beispielsweise an, dass ein Angriffsflächenreduzierungsereignis auf 10 Geräten während der Stunde 14:00 Uhr auftritt. Angenommen, das erste Ereignis ist um 2:15 Und das letzte um 2:45 aufgetreten. Bei der erweiterten Suche sehen Sie eine Instanz dieses Ereignisses (obwohl es tatsächlich auf 10 Geräten aufgetreten ist), und der Zeitstempel lautet 14:15 Uhr.

Weitere Informationen zur erweiterten Suche finden Sie unter [proaktive Suche nach Bedrohungen mit erweiterter Suche.](advanced-hunting-overview.md)

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Attack Surface Reduction-Features in Windows Versionen

Sie können Regeln zur Verringerung der Angriffsfläche für Geräte festlegen, auf denen eine der folgenden Editionen und Versionen von Windows ausgeführt wird:

- Windows 10 Pro, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows 10 Enterprise, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows Server, [Version 1803 (Halbjährlicher Kanal)](/windows-server/get-started/whats-new-in-windows-server-1803) oder höher
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Obwohl die Regeln zur Verringerung der Angriffsfläche keine [Windows E5-Lizenz](/windows/deployment/deploy-enterprise-licenses)erfordern, erhalten Sie, wenn Sie über Windows E5 verfügen, erweiterte Verwaltungsfunktionen. Die erweiterten Funktionen – nur in Windows E5 verfügbar – umfassen:

- Überwachung, Analyse und Workflows, die in [Defender für Endpunkt](microsoft-defender-endpoint.md) verfügbar sind
- Die Berichterstellungs- und Konfigurationsfunktionen in [Microsoft 365 Defender.](/microsoft-365/security/defender/overview-security-center)

Diese erweiterten Funktionen sind nicht mit einer Windows Professional- oder Windows E3-Lizenz verfügbar. Wenn Sie jedoch über diese Lizenzen verfügen, können Sie die Ereignisanzeige und Microsoft Defender Antivirus Protokolle verwenden, um ihre Regelereignisse zur Verringerung der Angriffsfläche zu überprüfen.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>Überprüfen von Attack Surface Reduction-Ereignissen im Microsoft 365 Defender Portal

Defender für Endpunkt bietet detaillierte Berichte für Ereignisse und Blöcke im Rahmen von Warnungsuntersuchungsszenarien.

Sie können Defender für Endpunktdaten in [Microsoft 365 Defender](microsoft-defender-security-center.md) abfragen, indem Sie [die erweiterte Suche](advanced-hunting-query-language.md)verwenden. Wenn Sie den [Überwachungsmodus](audit-windows-defender.md)ausführen, können Sie die erweiterte Suche verwenden, um zu verstehen, wie sich Regeln zur Verringerung der Angriffsfläche auf Ihre Umgebung auswirken können.

Hier ist eine Beispielabfrage:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Überprüfen von Ereignissen zur Verringerung der Angriffsfläche in Windows Ereignisanzeige

Sie können das Windows Ereignisprotokoll überprüfen, um Ereignisse anzuzeigen, die durch Attack Surface Reduction-Regeln generiert werden:

1. Laden Sie das [Evaluierungspaket herunter,](https://aka.ms/mp7z2w) und extrahieren Sie die Datei *cfa-events.xml* an einen leicht zugänglichen Speicherort auf dem Gerät.

2. Geben Sie die Wörter *Ereignisanzeige* in die Startmenü ein, um die Windows Ereignisanzeige zu öffnen.

3. Wählen Sie unter **"Aktionen"** die Option **"Benutzerdefinierte Ansicht importieren" aus...**.

4. Wählen Sie die Datei *cfa-events.xml* aus, aus der sie extrahiert wurde. Alternativ können [Sie den XML-Code direkt kopieren.](event-views.md)

5. Wählen Sie **OK** aus.

Sie können eine benutzerdefinierte Ansicht erstellen, die Ereignisse filtert, um nur die folgenden Ereignisse anzuzeigen, die alle mit dem kontrollierten Ordnerzugriff zusammenhängen:

|Ereignis-ID|Beschreibung|
|---|---|
|5007|Ereignis, wenn Einstellungen geändert werden|
|1121|Ereignis beim Auslösen der Regel im Blockierungsmodus|
|1122|Ereignis, wenn die Regel im Überwachungsmodus ausgelöst wird|

Die "Modulversion", die für Attack Surface Reduction-Ereignisse im Ereignisprotokoll aufgeführt ist, wird von Defender für Endpunkt und nicht vom Betriebssystem generiert. Defender für Endpunkt ist in Windows 10 integriert, sodass dieses Feature auf allen Geräten funktioniert, auf Windows 10 installiert ist.

## <a name="attack-surface-reduction-rules"></a>Regeln zur Verringerung der Angriffsfläche

In der folgenden Tabelle und den unteren Abschnitten werden die einzelnen Regeln zur Reduzierung der Angriffsfläche beschrieben. Die Regeln zur Verringerung der Angriffsfläche werden in alphabetischer Reihenfolge nach Regelname aufgelistet.

Wenn Sie Regeln zur Verringerung der Angriffsfläche mithilfe von Gruppenrichtlinien oder PowerShell konfigurieren, benötigen Sie die GUIDs. Wenn Sie andererseits Microsoft Endpoint Manager oder Microsoft Intune verwenden, benötigen Sie die GUIDs nicht.

|Regelname|GUID|Datei- & Ordnerausschlüsse|Unterstützte Mindestversion des Betriebssystems|
|---|:---:|---|---|
|[Blockieren des Missbrauchs von gefährdeten signierten Treibern](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher) |
|[Adobe Reader am Erstellen von untergeordneten Prozessen hindern](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Diebstahl von Anmeldeinformationen aus dem Subsystem für die lokale Sicherheitsautorität (lsass.exe) blockieren](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Ausführbare Dateien an der Ausführung hindern, außer sie erfüllen ein Verbreitungs-, Alters- oder vertrauenswürdige Listen-Kriterium](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Ausführung potenziell verborgener Skripts blockieren](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Office-Anwendungen am Erstellen ausführbarer Inhalte hindern](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Office-Kommunikationsanwendung am Erstellen von untergeordneten Prozessen hindern](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Persistenz durch WMI-Ereignisabonnement blockieren](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|Nicht unterstützt|[Windows 10, Version 1903](/windows/whats-new/whats-new-windows-10-version-1903) (Build 18362) oder höher|
|[Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Win32-API-Aufrufe von Office-Makros blockieren](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|
|[Erweiterten Schutz vor Ransomware verwenden](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|Unterstützt|[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, Build 16299) oder höher|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>Blockieren des Missbrauchs von gefährdeten signierten Treibern

Diese Regel verhindert, dass eine Anwendung einen anfälligen signierten Treiber auf den Datenträger schreibt. Gefährdete signierte Treiber können von lokalen Anwendungen ausgenutzt werden, \- _die über ausreichende Berechtigungen_ für den Zugriff auf den Kernel \- verfügen. Anfällige signierte Treiber ermöglichen Es Angreifern, Sicherheitslösungen zu deaktivieren oder zu umgehen, was letztendlich zu Systemkompromittierungen führt.

Die Regel zum **Blockieren des Missbrauchs gefährdeter signierter Treiber** verhindert nicht, dass ein bereits auf dem System vorhandener Treiber geladen wird.

>[!NOTE]
>
> Sie können diese Regel mithilfe von [MEM-OMA-URI](enable-attack-surface-reduction.md#mem) für benutzerdefinierte Mem-OMA-URI-Regel-Prozedurinformationen konfigurieren.
>
> Sie können diese Regel auch mithilfe von [PowerShell](enable-attack-surface-reduction.md#powershell)konfigurieren.
>
> Um einen Treiber untersuchen zu lassen, verwenden Sie diese Website, um [einen Treiber für die Analyse zu übermitteln.](https://www.microsoft.com/en-us/wdsi/driversubmission)

Unterstützte Betriebssysteme:

- [Windows 10 Pro, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- [Windows 10 Enterprise, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- [Windows Server, Version 1803 (Halbjährlicher Kanal)](/windows-server/get-started/whats-new-in-windows-server-1803) oder höher
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune-Name: `Block abuse of exploited vulnerable signed drivers`

Guid:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

### <a name="block-adobe-reader-from-creating-child-processes"></a>Adobe Reader am Erstellen von untergeordneten Prozessen hindern

Diese Regel verhindert Angriffe, indem Adobe Reader am Erstellen von Prozessen gehindert wird.

Durch Social Engineering oder Exploits kann Schadsoftware Nutzlasten herunterladen und starten und aus Adobe Reader ausbrechen. Durch das Blockieren der Generierung von untergeordneten Prozessen durch Adobe Reader wird verhindert, dass Schadsoftware versucht, sie als Vektor zu verwenden.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune-Name: `Process creation from Adobe Reader (beta)`

Configuration Manager-Name: Noch nicht verfügbar

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern

Mit dieser Regel wird verhindert, dass Office Apps untergeordnete Prozesse erstellen. Office Apps umfassen Word, Excel, PowerPoint, OneNote und Access.

Das Erstellen bösartiger untergeordneter Prozesse ist eine gängige Schadsoftwarestrategie. Schadsoftware, die Office als Vektor missbraucht, führt häufig VBA-Makros und Exploit-Code aus, um weitere Nutzlasten herunterzuladen und auszuführen. Einige legitime Branchenanwendungen können jedoch auch untergeordnete Prozesse für unfreundliche Zwecke generieren. z. B. das Auslösen einer Eingabeaufforderung oder die Verwendung von PowerShell zum Konfigurieren von Registrierungseinstellungen.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-Name: `Office apps launching child processes`

Configuration Manager-Name: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Blockieren des Diebstahls von Anmeldeinformationen aus dem Windows Subsystem der lokalen Sicherheitsautorität

Diese Regel trägt dazu bei, das Stehlen von Anmeldeinformationen zu verhindern, indem der Subsystemdienst der lokalen Sicherheitsautorität (Local Security Authority Subsystem Service, LSASS) gesperrt wird.

LSASS authentifiziert Benutzer, die sich auf einem Windows Computer anmelden. Microsoft Defender Credential Guard in Windows 10 verhindert normalerweise Versuche, Anmeldeinformationen aus LSASS zu extrahieren. Einige Organisationen können Credential Guard jedoch aufgrund von Kompatibilitätsproblemen mit benutzerdefinierten Smartcardtreibern oder anderen Programmen, die in die lokale Sicherheitsautorität (Local Security Authority, LSA) geladen werden, nicht auf allen ihren Computern aktivieren. In diesen Fällen können Angreifer Hacktools wie Mimikatz verwenden, um Klartextkennwörter und NTLM-Hashes von LSASS zu verwischen.

> [!NOTE]
> In einigen Apps zählt der Code alle ausgeführten Prozesse auf und versucht, sie mit vollständigen Berechtigungen zu öffnen. Diese Regel verweigert die Vorgangsöffnungsaktion der App und protokolliert die Details im Sicherheitsereignisprotokoll. Diese Regel kann viel Rauschen erzeugen. Wenn Sie über eine App verfügen, die LSASS einfach aufzählt, aber keine echten Auswirkungen auf die Funktionalität hat, ist es NICHT erforderlich, sie der Ausschlussliste hinzuzufügen. Dieser Ereignisprotokolleintrag allein weist nicht unbedingt auf eine böswillige Bedrohung hin.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune-Name: `Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager-Name: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren

Diese Regel verhindert, dass die folgenden Dateitypen von E-Mails gestartet werden, die in der Microsoft Outlook-Anwendung oder Outlook.com und anderen beliebten Webmailanbietern geöffnet wurden:

- Ausführbare Dateien (z. B. .exe, .dll oder SCR)
- Skriptdateien (z. B. eine PowerShell-PS-, Visual Basic -VBS- oder JavaScript-.js datei)

Unterstützte Betriebssysteme:

- [Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-Name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager Name:`Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> Die Regel **zum Blockieren von ausführbaren Inhalten vom E-Mail-Client und webmail** verfügt über die folgenden alternativen Beschreibungen, je nachdem, welche Anwendung Sie verwenden:
>
> - Intune (Konfigurationsprofile): Ausführung von ausführbaren Inhalten (exe, dll, ps, js, vbs usw.), die aus E-Mails (Webmail/Mail-Client) verworfen wurden (keine Ausnahmen).
> - Endpoint Manager: Blockieren des Downloads ausführbarer Inhalte von E-Mail- und Webmailclients.
> - Gruppenrichtlinie: Blockieren von ausführbaren Inhalten vom E-Mail-Client und webmail.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Ausführbare Dateien an der Ausführung hindern, außer sie erfüllen ein Verbreitungs-, Alters- oder vertrauenswürdige Listen-Kriterium

Mit dieser Regel wird verhindert, dass ausführbare Dateien wie .exe, .dll oder SCR gestartet werden, es sei denn, eine der folgenden Bedingungen ist erfüllt:

- Verbreitung: Die ausführbaren Dateien werden auf mehr als 1.000 Endpunkten gefunden.
- Alter: Die ausführbaren Dateien wurden vor mehr als 24 Stunden veröffentlicht.
- Speicherort: Die ausführbaren Dateien sind in einer vertrauenswürdigen Liste oder einer Ausschlussliste enthalten.

Das Starten nicht vertrauenswürdiger oder unbekannter ausführbarer Dateien kann riskant sein, da möglicherweise zunächst nicht klar ist, ob die Dateien bösartig sind.

> [!IMPORTANT]
> Sie müssen den über die [Cloud bereitgestellten Schutz aktivieren,](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) um diese Regel verwenden zu können.
>
> Die Regel **zum Blockieren der Ausführung ausführbarer Dateien, es sei denn, sie erfüllen ein Prävalenz-, Alters- oder vertrauenswürdiges Listenkriterium** mit GUID, gehört Microsoft und wird nicht von Administratoren `01443614-cd74-433a-b99e-2ecdc07bfc25` angegeben. Diese Regel verwendet über die Cloud bereitgestellten Schutz, um ihre vertrauenswürdige Liste regelmäßig zu aktualisieren.
>
> Sie können einzelne Dateien oder Ordner (mithilfe von Ordnerpfaden oder vollqualifizierten Ressourcennamen) angeben, jedoch nicht angeben, welche Regeln oder Ausschlüsse gelten.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune-Name: `Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager-Name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Ausführung potenziell verborgener Skripts blockieren

Diese Regel erkennt verdächtige Eigenschaften in einem verborgenen Skript.

Das Verbergen von Skripts ist eine gängige Technik, die sowohl Von Schadsoftwareautoren als auch legitimen Anwendungen verwendet wird, um geistiges Eigentum auszublenden oder die Ladezeiten von Skripts zu verringern. Autoren von Schadsoftware verwenden auch die Verschleierung, um das Lesen von schadhaftem Code zu erschweren, wodurch eine genaue Prüfung durch Menschen und Sicherheitssoftware verhindert wird.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-Name: `Obfuscated js/vbs/ps/macro code`

Configuration Manager-Name: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern

Diese Regel verhindert, dass Skripts potenziell schädliche heruntergeladene Inhalte starten. In JavaScript oder VBScript geschriebene Schadsoftware dient häufig als Downloader, um andere Schadsoftware aus dem Internet abzurufen und zu starten.

Obwohl branchenspezifische Anwendungen nicht üblich sind, verwenden sie manchmal Skripts, um Installationsprogramme herunterzuladen und zu starten.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-Name: `js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager-Name: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>Office-Anwendungen am Erstellen ausführbarer Inhalte hindern

Diese Regel verhindert, dass Office Apps, einschließlich Word, Excel und PowerPoint, potenziell schädliche ausführbare Inhalte erstellen, indem verhindert wird, dass bösartiger Code auf den Datenträger geschrieben wird.

Schadsoftware, die Office als Vektor missbraucht, versucht möglicherweise, Office zu unterbrechen und schädliche Komponenten auf dem Datenträger zu speichern. Diese schädlichen Komponenten würden einen Computerneustart überstehen und auf dem System beibehalten. Daher schützt diese Regel vor einer gängigen Persistenztechnik.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM ist jetzt Microsoft Endpoint Configuration Manager)

Intune-Name: `Office apps/macros creating executable content`

SCCM-Name: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern

Diese Regel blockiert Codeeinfügungsversuche von Office Apps in andere Prozesse.

Angreifer versuchen möglicherweise, Office-Apps zu verwenden, um bösartigen Code durch Codeeinschleusung in andere Prozesse zu migrieren, damit sich der Code als sauberen Prozess maskieren kann.

Es gibt keine bekannten legitimen Geschäftszwecke für die Verwendung von Codeeinfügung.

Diese Regel gilt für Word, Excel und PowerPoint.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-Name: `Office apps injecting code into other processes (no exceptions)`

Configuration Manager-Name: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>Office-Kommunikationsanwendung am Erstellen von untergeordneten Prozessen hindern

Diese Regel verhindert, dass Outlook untergeordnete Prozesse erstellen und gleichzeitig legitime Outlook Funktionen zulassen.

Diese Regel schützt vor Social Engineering-Angriffen und verhindert, dass Code Sicherheitslücken in Outlook missbraucht. Es schützt auch vor [Outlook Regeln und Formularen,](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) die Angreifer verwenden können, wenn die Anmeldeinformationen eines Benutzers kompromittiert werden.

> [!NOTE]
> Diese Regel blockiert DLP-Richtlinientipps und QuickInfos in Outlook. Diese Regel gilt nur für Outlook und Outlook.com.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune-Name: `Process creation from Office communication products (beta)`

Configuration Manager-Name: Nicht verfügbar

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>Persistenz durch WMI-Ereignisabonnement blockieren

Diese Regel verhindert, dass Schadsoftware WMI missbraucht, um Dauerhaftigkeit auf einem Gerät zu erreichen.

> [!IMPORTANT]
> Datei- und Ordnerausschlüsse gelten nicht für diese Regel zur Verringerung der Angriffsfläche.

Dateilose Bedrohungen verwenden verschiedene Taktiken, um ausgeblendet zu bleiben, um zu verhindern, dass sie im Dateisystem angezeigt werden, und um eine regelmäßige Ausführungskontrolle zu erhalten. Einige Bedrohungen können das WMI-Repository und das Ereignismodell missbrauchen, um ausgeblendet zu bleiben.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1903](/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Server 1903](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Intune-Name: Nicht verfügbar

Configuration Manager-Name: Nicht verfügbar

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren

Diese Regel blockiert die Ausführung von Prozessen, die über [PsExec](/sysinternals/downloads/psexec) und [WMI](/windows/win32/wmisdk/about-wmi) erstellt wurden. Sowohl PsExec als auch WMI können Code remote ausführen, sodass das Risiko besteht, dass Schadsoftware diese Funktionalität zu Befehls- und Steuerungszwecken missbraucht oder eine Infektion im gesamten Netzwerk einer Organisation verbreitet.

> [!WARNING]
> Verwenden Sie diese Regel nur, wenn Sie Ihre Geräte mit [Intune](/intune) oder einer anderen MDM-Lösung verwalten. Diese Regel ist mit der Verwaltung über [Microsoft Endpoint Configuration Manager](/configmgr) nicht kompatibel, da diese Regel WMI-Befehle blockiert, die der Configuration Manager-Client verwendet, um ordnungsgemäß zu funktionieren.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune-Name: `Process creation from PSExec and WMI commands`

Configuration Manager-Name: Nicht zutreffend

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren

Mit dieser Regel können Administratoren verhindern, dass nicht signierte oder nicht vertrauenswürdige ausführbare Dateien von USB-Wechseldatenträgern ausgeführt werden, einschließlich SD-Karten. Zu den blockierten Dateitypen gehören ausführbare Dateien (z. B. .exe, .dll oder SCR).

Unterstützte Betriebssysteme:

- [Windows 10, Version 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune-Name: `Untrusted and unsigned processes that run from USB`

Configuration Manager-Name: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Win32-API-Aufrufe von Office-Makros blockieren

Diese Regel verhindert, dass VBA-Makros Win32-APIs aufrufen.

Office VBA aktiviert Win32-API-Aufrufe. Schadsoftware kann diese Funktion missbrauchen, z. B. [indem sie Win32-APIs aufruft, um bösartige Shellcode zu starten,](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) ohne etwas direkt auf die Festplatte zu schreiben. Die meisten Organisationen verlassen sich nicht auf die Möglichkeit, Win32-APIs in ihrer täglichen Funktionsweise aufzurufen, auch wenn sie Makros auf andere Weise verwenden.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune-Name: `Win32 imports from Office macro code`

Configuration Manager-Name: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>Erweiterten Schutz vor Ransomware verwenden

Diese Regel bietet eine zusätzliche Schutzebene vor Ransomware. Es verwendet Client- und Cloud-Heuristiken, um festzustellen, ob eine Datei Ransomware ähnelt. Diese Regel blockiert keine Dateien mit einem oder mehreren der folgenden Merkmale:

- Die Datei wurde bereits in der Microsoft-Cloud als nicht vertrauenswürdig eingestuft.
- Die Datei ist eine gültige signierte Datei.
- Die Datei ist weit verbreitet genug, um nicht als Ransomware betrachtet zu werden.

Die Regel tendiert zu einem Fehler auf der Seite der Vorsicht, um Ransomware zu verhindern.

> [!NOTE]
> Sie müssen den über die [Cloud bereitgestellten Schutz aktivieren,](enable-cloud-protection-microsoft-defender-antivirus.md) um diese Regel verwenden zu können.

Unterstützte Betriebssysteme:

- [Windows 10, Version 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, Version 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune-Name: `Advanced ransomware protection`

Configuration Manager-Name: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`
