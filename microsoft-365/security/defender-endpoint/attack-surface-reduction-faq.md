---
title: Häufig gestellte Fragen (FAQ) zur Verringerung der Angriffsfläche
description: Hier finden Sie Antworten auf häufig gestellte Fragen zu den Regeln zur Verringerung der Angriffsfläche von Microsoft Defender für Endpunkt.
keywords: Attack Surface Reduction-Regeln, Asr, Hips, Host Intrusion Prevention System, Schutzregeln, Anti-Exploit, Antiexploit, Exploit, Infektionsverhinderung, Microsoft Defender für Endpunkt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56d4ac95ab49310cc5fc74168158672e7a0d65d1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843222"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>Häufig gestellte Fragen (FAQ) zur Verringerung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>Gehört die Verringerung der Angriffsfläche (Attack Surface Reduction, ASR) zu Windows?

ASR war ursprünglich ein Feature der Suite von Exploit Guard-Features, die in Windows 10 Version 1709 als ein wichtiges Update für Microsoft Defender Antivirus eingeführt wurde. Microsoft Defender Antivirus ist die systemeigene Antischadsoftwarekomponente von Windows. Der vollständige ASR-Featuresatz ist jedoch nur mit einer Windows Enterprise-Lizenz verfügbar. Beachten Sie außerdem, dass ASR-Regelausschlüsse getrennt von Microsoft Defender Antivirus Ausschlüssen verwaltet werden.

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>Muss ich über eine Unternehmenslizenz verfügen, um ASR-Regeln auszuführen?

Der vollständige Satz von ASR-Regeln und -Features wird nur unterstützt, wenn Sie über eine Unternehmenslizenz für Windows 10 verfügen. Eine begrenzte Anzahl von Regeln kann ohne Unternehmenslizenz funktionieren. Wenn Sie Microsoft 365 Business haben, legen Sie Microsoft Defender Antivirus als primäre Sicherheitslösung fest, und aktivieren Sie die Regeln über PowerShell. Die Verwendung von ASR ohne Unternehmenslizenz wird offiziell nicht unterstützt, und Sie können nicht die gesamten Funktionen von ASR nutzen.

Weitere Informationen zu Windows Lizenzierung finden Sie unter [Windows 10 Lizenzierung](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) und im [Volumenlizenzierungshandbuch für Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>Wird ASR unterstützt, wenn ich eine E3-Lizenz habe?

Ja. ASR wird für Windows Enterprise E3 und höher unterstützt. 

## <a name="which-features-are-supported-with-an-e5-license"></a>Welche Features werden mit einer E5-Lizenz unterstützt?

Alle mit E3 unterstützten Regeln werden auch mit E5 unterstützt.

E5 bietet eine bessere Integration in Defender für Endpunkt. Mit E5 können Sie Warnungen in Echtzeit anzeigen, Regelausschlüsse optimieren, ASR-Regeln konfigurieren und Listen von Ereignisberichten anzeigen.

## <a name="what-are-the-currently-supported-asr-rules"></a>Was sind die derzeit unterstützten ASR-Regeln?
ASR unterstützt derzeit alle unten aufgeführten Regeln.

## <a name="what-rules-to-enable-all-or-can-i-turn-on-individual-rules"></a>Welche Regeln müssen aktiviert werden? Alle oder kann ich einzelne Regeln aktivieren?
Um herauszufinden, was für Ihre Umgebung am besten geeignet ist, wird empfohlen, ASR-Regeln im [Überwachungsmodus](audit-windows-defender.md)zu aktivieren. Bei diesem Ansatz bestimmen Sie die möglichen Auswirkungen auf Ihre Organisation. Beispielsweise Ihre Branchenanwendungen.

## <a name="how-do-asr-rules-exclusions-work"></a>Wie funktionieren ASR-Regelausschlüsse?
Wenn Sie einen Ausschluss hinzufügen, wirkt sich dies bei ASR-Regeln auf jede ASR-Regel aus.
Die folgenden beiden spezifischen Regeln unterstützen keine Ausschlüsse:

|Regelname|GUID|Datei- & Ordnerausschlüsse|
|:--|:--|:--|
|JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern|D3E037E1-3EB8-44C8-A917-57927947596D|Nicht unterstützt|
|Persistenz durch WMI-Ereignisabonnement blockieren|e6db77e5-3df2-4cf1-b95a-636979351e5b|Nicht unterstützt|

ASR-Regelausschlüsse unterstützen Platzhalter, Pfade und Umgebungsvariablen. Weitere Informationen zur Verwendung von Platzhaltern in ASR-Regeln finden Sie unter [Konfigurieren und Validieren von Ausschlüssen basierend auf Dateierweiterung und Ordnerspeicherort.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus)

Beachten Sie die folgenden Elemente zu ASR-Regelausschlüssen (einschließlich Platzhaltern und Env. Variablen):

- ASR-Regelausschlüsse sind unabhängig von Defender AV-Ausschlüssen
- Platzhalter können nicht zum Definieren eines Laufwerkbuchstabens verwendet werden
- Wenn Sie mehrere Ordner ausschließen möchten, verwenden Sie in einem Pfad mehrere Instanzen von \* \, um mehrere geschachtelte Ordner anzugeben (z. B. c:\Folder \* \* \Test)
- Microsoft Endpoint Configuration Manager unterstützt *keine* Platzhalter (* oder ?)
- Wenn Sie eine Datei ausschließen möchten, die zufällige Zeichen (automatische Dateigenerierung) enthält, können Sie das Symbol "?" verwenden (z. B. C:\Folder\fileversion?.docx)
- ASR-Ausschlüsse in Gruppenrichtlinien unterstützen keine Anführungszeichen (das Modul verarbeitet nativ langen Pfad, Leerzeichen usw., sodass keine Anführungszeichen verwendet werden müssen)
- ASR-Regeln werden unter dem NT AUTHORITY\SYSTEM-Konto ausgeführt, sodass Umgebungsvariablen auf Computervariablen beschränkt sind.

## <a name="how-do-i-know-what-i-need-to-exclude"></a>Woher weiß ich, was ich ausschließen muss?
Unterschiedliche ASR-Regeln haben unterschiedliche Schutzflüsse. Überlegen Sie immer, wovor die ASR-Regel, die Sie konfigurieren, schützt und wie der tatsächliche Ausführungsfluss verschoben wird.

Beispiel: **Blockieren des Diebstahls von Anmeldeinformationen aus dem Windows Subsystems der lokalen Sicherheitsautorität,** das direkt aus dem LSASS-Prozess (Local Security Authority Subsystem) liest, kann ein Sicherheitsrisiko darstellen, da möglicherweise Unternehmensanmeldeinformationen verfügbar gemacht werden.

Diese Regel verhindert, dass nicht vertrauenswürdige Prozesse direkten Zugriff auf den LSASS-Speicher haben. Wenn ein Prozess versucht, die OpenProcess()-Funktion für den Zugriff auf LSASS mit einem Zugriffsrecht von PROCESS_VM_READ zu verwenden, blockiert die Regel dieses Zugriffsrecht ausdrücklich.

:::image type="content" source="images/asrfaq1.png" alt-text="Blockieren des Diebstahls von Anmeldeinformationen durch LSASS":::

Wenn Sie im obigen Beispiel tatsächlich eine Ausnahme für den Prozess erstellen müssten, für den die Zugriffsberechtigung blockiert wurde, würde das Hinzufügen des Dateinamens zusammen mit dem vollständigen Pfad die Blockierung und den Zugriff auf den LSASS-Prozessspeicher ausschließen. Der Wert 0 bedeutet, dass ASR-Regeln diese Datei/diesen Prozess ignorieren und nicht blockieren/überwachen.

:::image type="content" source="images/asrfaq2.png" alt-text="Ausschließen von Dateien asr":::

## <a name="what-are-the-rules-microsoft-recommends-enabling"></a>Welche Regeln empfiehlt Microsoft für die Aktivierung?

Es wird empfohlen, jede mögliche Regel zu aktivieren. Es gibt jedoch Fälle, in denen Sie keine Regel aktivieren sollten. Es wird beispielsweise nicht empfohlen, die Blockierung von Prozesserstellungen, die von der PSExec- und WMI-Befehlsregel stammen, zu aktivieren, wenn Sie Microsoft Endpoint Configuration Manager (oder System Center Configuration Manager - SCCM) zum Verwalten Ihrer Endpunkte verwenden.

Es wird dringend empfohlen, dass Sie alle regelspezifischen Informationen und/oder Warnungen lesen, die in unserer [öffentlichen Dokumentation](/microsoft-365/security/defender-endpoint/attack-surface-reduction.md)verfügbar sind.
umfasst mehrere Säulen des Schutzes, z. B. Office, Anmeldeinformationen, Skripts, E-Mail usw. Alle ASR-Regeln, mit Ausnahme der Blockpersistenz über WMI-Ereignisabonnement, werden ab Windows 1709 unterstützt:

* [Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [Office-Anwendungen am Erstellen ausführbarer Inhalte hindern](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [Ausführung potenziell verborgener Skripts blockieren](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [Blockieren von Win32-API-Aufrufen von Office Makro](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [Erweiterten Schutz vor Ransomware verwenden](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [Blockieren des Diebstahls von Anmeldeinformationen aus dem Windows Subsystem der lokalen Sicherheitsautorität](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) (lsass.exe)
* [Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [Blockieren der Ausführung ausführbarer Dateien, es sei denn, sie erfüllen verbreitungs-, alters- oder vertrauenswürdige Listenkriterien.](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [Verhindern, dass Office Kommunikationsanwendungen untergeordnete Prozesse erstellen](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [Adobe Reader am Erstellen von untergeordneten Prozessen hindern](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [Persistenz durch WMI-Ereignisabonnement blockieren](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>Was sind einige gute Empfehlungen für die ersten Schritte mit ASR?

Testen Sie, wie sich ASR-Regeln auf Ihre Organisation auswirken, bevor Sie sie aktivieren, indem Sie ASR-Regeln für einen kurzen Zeitraum im Überwachungsmodus ausführen. Während Sie die Regeln im Überwachungsmodus ausführen, können Sie alle Branchenanwendungen identifizieren, die fälschlicherweise blockiert werden, und sie von ASR ausschließen.

Größere Organisationen sollten die Einführung von ASR-Regeln in "Ringen" in Betracht ziehen, indem Sie Regeln in immer umfangreicheren Teilmengen von Geräten überwachen und aktivieren. Sie können die Geräte Ihrer Organisation in Ringe anordnen, indem Sie Intune oder ein Gruppenrichtlinienverwaltungstool verwenden.

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>Wie lange sollte ich eine ASR-Regel im Überwachungsmodus testen, bevor sie aktiviert wird?

Behalten Sie die Regel ca. 30 Tage im Überwachungsmodus bei, um einen guten Basisplan für die Funktionsweise der Regel zu erhalten, sobald sie in Der gesamten Organisation aktiv ist. Während des Überwachungszeitraums können Sie alle Branchenanwendungen identifizieren, die möglicherweise durch die Regel blockiert werden, und die Regel so konfigurieren, dass sie ausgeschlossen werden.

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>Ich erstelle den Wechsel von einer Drittanbieter-Sicherheitslösung zu Defender für Endpunkt. Gibt es eine "einfache" Möglichkeit, Regeln aus einer anderen Sicherheitslösung nach ASR zu exportieren?

In den meisten Fällen ist es einfacher und besser, mit den von [Defender für Endpunkt](/windows/security/threat-protection) vorgeschlagenen Basisempfehlungen zu beginnen, als zu versuchen, Regeln aus einer anderen Sicherheitslösung zu importieren. Verwenden Sie dann Tools wie Überwachungsmodus, Überwachung und Analyse, um Ihre neue Lösung für Ihre individuellen Anforderungen zu konfigurieren. 

Die Standardkonfiguration für die meisten ASR-Regeln in Kombination mit dem Echtzeitschutz von Defender für Endpunkt schützt vor einer großen Anzahl von Exploits und Sicherheitsrisiken.

Innerhalb von Defender für Endpunkt können Sie Ihre Verteidigung mit benutzerdefinierten Indikatoren aktualisieren, um bestimmte Softwareverhalten zuzulassen und zu blockieren. ASR ermöglicht auch einige Anpassungen von Regeln in Form von Datei- und Ordnerausschlüssen. Als allgemeine Regel empfiehlt es sich, eine Regel für einen bestimmten Zeitraum zu überwachen und Ausschlüsse für alle Branchenanwendungen zu konfigurieren, die möglicherweise blockiert werden.

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>Unterstützt ASR Datei- oder Ordnerausschlüsse, die Systemvariablen und Platzhalter im Pfad enthalten?

Ja. Weitere Informationen zum Ausschließen [von Dateien und Ordnern von ASR-Regeln](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) finden Sie unter "Ausschließen von Dateien und Ordnern aus ASR-Regeln" sowie zum Konfigurieren und Validieren von [Ausschlüssen basierend auf Dateierweiterungen und Ordnerspeicherorten,](/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) um weitere Informationen zur Verwendung von Systemvariablen und Platzhaltern in ausgeschlossenen Dateipfaden zu erhalten.

## <a name="do-asr-rules-cover-all-applications-by-default"></a>Gelten ASR-Regeln standardmäßig für alle Anwendungen?

Dies hängt von der Regel ab. Die meisten ASR-Regeln beziehen sich auf das Verhalten von Microsoft Office Produkten und Diensten, z. B. Word, Excel, PowerPoint und OneNote oder Outlook. Bestimmte ASR-Regeln, z. B. *das Blockieren der Ausführung potenziell verborgener Skripts,* sind allgemeiner.

## <a name="does-asr-support-third-party-security-solutions"></a>Unterstützt ASR Sicherheitslösungen von Drittanbietern?

ASR verwendet Microsoft Defender Antivirus, um Anwendungen zu blockieren. Es ist derzeit nicht möglich, ASR so zu konfigurieren, dass eine andere Sicherheitslösung zum Blockieren verwendet wird.

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>Ich habe eine E5-Lizenz und einige ASR-Regeln in Verbindung mit Defender für Endpunkt aktiviert. Ist es möglich, dass ein ASR-Ereignis überhaupt nicht in der Ereigniszeitachse von Defender für Endpunkt angezeigt wird?

Wenn eine Benachrichtigung lokal durch eine ASR-Regel ausgelöst wird, wird auch ein Bericht über das Ereignis an das Defender für Endpunkt-Portal gesendet. Wenn Sie Probleme bei der Suche nach dem Ereignis haben, können Sie die Ereigniszeitachse mithilfe des Suchfelds filtern. Sie können ASR-Ereignisse auch anzeigen, indem Sie über das Symbol für die **Konfigurationsverwaltung** in der Taskleiste des Security Centers die Option **"Gehe zu Angriffsflächenverwaltung"** besuchen. Die Seite "Angriffsflächenverwaltung" enthält eine Registerkarte für Berichtserkennungen, die eine vollständige Liste der ASR-Regelereignisse enthält, die an Defender für Endpunkt gemeldet werden.

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>Ich habe eine Regel mithilfe von Gruppenrichtlinienobjekten angewendet. Wenn ich nun versuche, die Indizierungsoptionen für die Regel in Microsoft Outlook zu überprüfen, erhalte ich die Meldung "Zugriff verweigert".

Versuchen Sie, die Indizierungsoptionen direkt über Windows 10 zu öffnen.

1. Wählen Sie das **Suchsymbol** auf der Windows Taskleiste aus.

1. Geben Sie **Indizierungsoptionen** in das Suchfeld ein.

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>Sind die von der Regel verwendeten Kriterien "Ausführung ausführbarer Dateien blockieren, es sei denn, sie erfüllen ein Verbreitungs-, Alters- oder vertrauenswürdiges Listenkriterium", von einem Administrator konfigurierbar?

Nein. Die von dieser Regel verwendeten Kriterien werden von Microsoft Cloud Protection beibehalten, um die vertrauenswürdige Liste mit Daten aus der ganzen Welt auf dem neuesten Stand zu halten. Lokale Administratoren haben keinen Schreibzugriff, um diese Daten zu ändern. Wenn Sie diese Regel so konfigurieren möchten, dass sie an Ihr Unternehmen angepasst wird, können Sie der Ausschlussliste bestimmte Anwendungen hinzufügen, um zu verhindern, dass die Regel ausgelöst wird.

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>I enabled the ASR rule, *Block executable files from running unless they meet a prevalence, age, or trusted list criterion*. Nach einiger Zeit habe ich eine Software aktualisiert, und die Regel blockiert sie jetzt, obwohl dies noch nicht der Fall war. Ist ein Fehler aufgetreten?

Diese Regel basiert darauf, dass jede Anwendung über einen bekannten Ruf verfügt, gemessen anhand der Verbreitung, des Alters oder der Aufnahme in eine Liste vertrauenswürdiger Apps. Die Entscheidung der Regel, eine Anwendung zu blockieren oder zuzulassen, wird letztlich durch die Bewertung dieser Kriterien durch Microsoft Cloud Protection bestimmt.

In der Regel kann der Cloudschutz feststellen, dass eine neue Version einer Anwendung den vorherigen Versionen ähnlich genug ist, dass sie nicht ausführlich überprüft werden muss. Es kann jedoch einige Zeit dauern, bis die App nach dem Wechseln der Versionen eine Zuverlässigkeit aufbaut, insbesondere nach einem größeren Update. In der Zwischenzeit können Sie die Anwendung der Ausschlussliste hinzufügen, um zu verhindern, dass diese Regel wichtige Anwendungen blockiert. Wenn Sie häufig aktualisieren und mit neuen Versionen von Anwendungen arbeiten, können Sie stattdessen diese Regel im Überwachungsmodus ausführen.

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>Ich habe kürzlich die ASR-Regel aktiviert, das *Stehlen von Anmeldeinformationen aus dem Windows Subsystem der lokalen Sicherheitsautorität (lsass.exe) blockiert,* und ich erhalte eine große Anzahl von Benachrichtigungen. Was ist los?

Eine von dieser Regel generierte Benachrichtigung weist nicht unbedingt auf böswillige Aktivitäten hin. Diese Regel ist jedoch weiterhin nützlich, um böswillige Aktivitäten zu blockieren, da Schadsoftware häufig auf lsass.exe ausgerichtet ist, um unbefugten Zugriff auf Konten zu erhalten. Der lsass.exe Prozess speichert Benutzeranmeldeinformationen im Speicher, nachdem sich ein Benutzer angemeldet hat. Windows verwendet diese Anmeldeinformationen, um Benutzer zu überprüfen und lokale Sicherheitsrichtlinien anzuwenden.

Da viele legitime Prozesse an einem typischen Tag lsass.exe für Anmeldeinformationen aufrufen, kann diese Regel besonders laut sein. Wenn eine bekannte legitime Anwendung bewirkt, dass diese Regel eine übermäßige Anzahl von Benachrichtigungen generiert, können Sie sie der Ausschlussliste hinzufügen. Die meisten anderen ASR-Regeln generieren im Vergleich zu diesem eine relativ kleinere Anzahl von Benachrichtigungen, da das Aufrufen von lsass.exe typisch für die normale Funktionsweise vieler Anwendungen ist.

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>Empfiehlt es sich, die Regel zu aktivieren: *Blockieren des Diebstahls von Anmeldeinformationen aus dem Windows Subsystem der lokalen Sicherheitsautorität (lsass.exe)* zusammen mit dem LSA-Schutz?

Das Aktivieren dieser Regel bietet keinen zusätzlichen Schutz, wenn Sie auch [den LSA-Schutz](/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) aktiviert haben. Sowohl die Regel als auch der LSA-Schutz funktionieren in etwa auf die gleiche Weise, sodass beide gleichzeitig ausgeführt werden, was redundant wäre. Manchmal ist es jedoch möglicherweise nicht möglich, den LSA-Schutz zu aktivieren. In diesen Fällen können Sie diese Regel aktivieren, um einen gleichwertigen Schutz vor Schadsoftware bereitzustellen, die auf lsass.exe ausgerichtet ist.

## <a name="see-also"></a>Siehe auch

* [Übersicht über die Verringerung der Angriffsfläche](attack-surface-reduction.md)
* [Auswerten der Regeln zur Verringerung der Angriffsfläche](evaluate-attack-surface-reduction.md)
* [Anpassen der Regeln zur Verringerung der Angriffsfläche](customize-attack-surface-reduction.md)
* [Aktivieren der Regeln zur Verringerung der Angriffsfläche](enable-attack-surface-reduction.md)
* [Kompatibilität von Microsoft Defender mit anderen Antivirensoftware/Antischadsoftware](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)


