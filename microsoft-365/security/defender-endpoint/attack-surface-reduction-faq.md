---
title: Häufig gestellte Fragen (FAQ) zur Reduzierung der Angriffsfläche
description: Hier finden Sie Antworten auf häufig gestellte Fragen zu den Regeln zur Reduzierung der Angriffsfläche von Microsoft Defender ATP.
keywords: Attack Surface Reduction Rules, Asr, Hips, Host Intrusion Prevention System, Protection Rules, Anti-Exploit, Antiexploit, Exploit, Infection Prevention, microsoft defender for endpoint
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
ms.technology: mde
ms.openlocfilehash: 7685bd70d85ecebe759ade762b78ee2c3639cea8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061799"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>Häufig gestellte Fragen (FAQ) zur Reduzierung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>Ist attack surface reduction (ASR) Teil von Windows?

ASR war ursprünglich ein Feature der Suite von Exploit Guard-Features, die als wichtiges Update für Microsoft Defender Antivirus in Windows 10, Version 1709, eingeführt wurde. Microsoft Defender Antivirus ist die systemeigene Antischalwarekomponente von Windows. Das vollständige ASR-Featureset ist jedoch nur mit einer Windows Enterprise-Lizenz verfügbar. Beachten Sie außerdem, dass ASR-Regelausschlüsse getrennt von Microsoft Defender Antivirus-Ausschlüssen verwaltet werden.

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>Muss ich über eine Unternehmenslizenz zum Ausführen von ASR-Regeln verfügen?

Der vollständige Satz von ASR-Regeln und -Features wird nur unterstützt, wenn Sie über eine Unternehmenslizenz für Windows 10 verfügen. Eine begrenzte Anzahl von Regeln kann ohne Unternehmenslizenz funktionieren. Wenn Sie über Microsoft 365 Business verfügen, legen Sie Microsoft Defender Antivirus als primäre Sicherheitslösung ein, und aktivieren Sie die Regeln über PowerShell. Die Nutzung von ASR ohne Unternehmenslizenz wird jedoch nicht offiziell unterstützt, und die vollständigen Funktionen von ASR stehen nicht zur Verfügung.

Weitere Informationen zur Windows-Lizenzierung finden Sie unter [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) und im Handbuch zur [Volumenlizenzierung für Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>Wird ASR unterstützt, wenn ich eine E3-Lizenz habe?

Ja. ASR wird für Windows Enterprise E3 und höher unterstützt. 

## <a name="which-features-are-supported-with-an-e5-license"></a>Welche Features werden mit einer E5-Lizenz unterstützt?

Alle mit E3 unterstützten Regeln werden auch mit E5 unterstützt.

E5 hat außerdem eine bessere Integration in Defender for Endpoint hinzugefügt. Mit E5 können Sie [Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender/monitor-devices?view=o365-worldwide&preserve-view=true#monitor-and-manage-asr-rule-deployment-and-detections) verwenden, um Analysen zu Warnungen in Echtzeit zu überwachen und zu überprüfen, Regelausschlüsse zu optimieren, ASR-Regeln zu konfigurieren und Listen von Ereignisberichten anzuzeigen.

## <a name="what-are-the-currently-supported-asr-rules"></a>Was sind die derzeit unterstützten ASR-Regeln?

ASR unterstützt derzeit alle folgenden Regeln:

* [Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [Office-Anwendungen am Erstellen ausführbarer Inhalte hindern](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [Ausführung potenziell verborgener Skripts blockieren](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [Blockieren von Win32-API-Aufrufen von Office-Makros](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [Erweiterten Schutz vor Ransomware verwenden](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [Blockieren des Diebstahls von Anmeldeinformationen aus dem Windows Local Security Authority Subsystem](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) (lsass.exe)
* [Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [Blockieren der Ausführung ausführbarer Dateien, es sei denn, sie erfüllen ein Prävalenz-, Alters- oder vertrauenswürdiges Listenkriterium](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [Blockieren der Erstellung untergeordneter Prozesse durch Office-Kommunikationsanwendungen](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [Adobe Reader am Erstellen von untergeordneten Prozessen hindern](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [Persistenz durch WMI-Ereignisabonnement blockieren](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>Was sind einige gute Empfehlungen für die ersten Schritte mit ASR?

Testen Sie, wie sich ASR-Regeln auf Ihre Organisation auswirken, bevor Sie sie aktivieren, indem Sie ASR-Regeln für einen kurzen Zeitraum im Überwachungsmodus ausführen. Während Sie die Regeln im Überwachungsmodus ausführen, können Sie alle Geschäftsanwendungen identifizieren, die möglicherweise fälschlicherweise blockiert werden, und sie von ASR ausschließen.

Größere Organisationen sollten das Roll out von ASR-Regeln in "Ringen" in Betracht ziehen, indem Sie Regeln in immer umfangreicheren Untergruppen von Geräten überwachen und aktivieren. Sie können die Geräte Ihrer Organisation mithilfe von Intune oder einem Gruppenrichtlinienverwaltungstool in Ringe anordnen.

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>Wie lange sollte ich eine ASR-Regel im Überwachungsmodus testen, bevor sie aktiviert wird?

Halten Sie die Regel für ca. 30 Tage im Überwachungsmodus, um eine gute Basis für die Funktionsweise der Regel zu erhalten, sobald sie in Ihrer Organisation in Betrieb geht. Während des Überwachungszeitraums können Sie alle Geschäftsanwendungen identifizieren, die möglicherweise von der Regel blockiert werden, und die Regel so konfigurieren, dass sie ausgeschlossen werden.

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>Ich möchte von einer Sicherheitslösung eines Drittanbieters zu Defender for Endpoint wechseln. Gibt es eine "einfache" Möglichkeit, Regeln aus einer anderen Sicherheitslösung in ASR zu exportieren?

In den meisten Fällen ist es einfacher und besser, mit den von [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) vorgeschlagenen Basisempfehlungen zu beginnen, als Regeln aus einer anderen Sicherheitslösung zu importieren. Verwenden Sie dann Tools wie Überwachungsmodus, Überwachung und Analyse, um Ihre neue Lösung für Ihre individuellen Anforderungen zu konfigurieren. 

Die Standardkonfiguration für die meisten ASR-Regeln in Kombination mit dem Echtzeitschutz von Defender for Endpoint schützt vor einer großen Anzahl von Exploits und Sicherheitsrisiken.

In Defender for Endpoint können Sie Ihre Verteidigung mit benutzerdefinierten Indikatoren aktualisieren, um bestimmte Softwareverhalten zu erlauben und zu blockieren. AsR ermöglicht auch einige Anpassungen von Regeln in Form von Datei- und Ordnerausschlüssen. In der Regel ist es am besten, eine Regel für einen bestimmten Zeitraum zu überwachen und Ausschlüsse für alle Geschäftsanwendungen zu konfigurieren, die möglicherweise blockiert werden.

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>Unterstützt ASR Datei- oder Ordnerausschlüsse, die Systemvariablen und Platzhalter im Pfad enthalten?

Ja. Weitere Informationen zum Ausschließen von Dateien oder Ordnern von [ASR-Regeln](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) finden [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) Sie unter Ausschließen von Dateien und Ordnern von ASR-Regeln und Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateierweiterung und Ordnerspeicherort, um weitere Informationen zur Verwendung von Systemvariablen und Platzhaltern in ausgeschlossenen Dateipfaden zu erhalten.

## <a name="do-asr-rules-cover-all-applications-by-default"></a>Gelten asr-Regeln standardmäßig für alle Anwendungen?

Dies hängt von der Regel ab. Die meisten ASR-Regeln decken das Verhalten von Microsoft Office und Diensten ab, z. B. Word, Excel, PowerPoint und OneNote oder Outlook. Bestimmte ASR-Regeln, z. B. Die Ausführung *von* potenziell verschleierten Skripts blockieren, sind allgemeiner.

## <a name="does-asr-support-third-party-security-solutions"></a>Unterstützt ASR Sicherheitslösungen von Drittanbietern?

ASR verwendet Microsoft Defender Antivirus, um Anwendungen zu blockieren. Es ist derzeit nicht möglich, ASR so zu konfigurieren, dass eine andere Sicherheitslösung zum Blockieren verwendet wird.

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>Ich habe eine E5-Lizenz und habe einige ASR-Regeln in Verbindung mit Defender for Endpoint aktiviert. Ist es möglich, dass ein ASR-Ereignis überhaupt nicht in der Ereigniszeitachse von Defender for Endpoint angezeigt wird?

Wenn eine Benachrichtigung lokal durch eine ASR-Regel ausgelöst wird, wird auch ein Bericht über das Ereignis an das Defender for Endpoint-Portal gesendet. Wenn Sie Probleme beim Suchen des Ereignisses haben, können Sie die Ereigniszeitachse mithilfe des Suchfelds filtern. Sie können auch ASR-Ereignisse anzeigen, indem Sie **go to attack surface management** über das **Konfigurationsverwaltungssymbol** in der Taskleiste des Security Center besuchen. Die Seite "Angriffsoberflächenverwaltung" enthält eine Registerkarte für Berichtserkennungen, die eine vollständige Liste der an Defender for Endpoint gemeldeten ASR-Regelereignisse enthält.

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>Ich habe eine Regel mit GPO angewendet. Wenn ich nun versuche, die Indizierungsoptionen für die Regel in Microsoft Outlook zu überprüfen, wird eine Meldung mit der Meldung "Zugriff verweigert" angezeigt.

Versuchen Sie, die Indizierungsoptionen direkt aus Windows 10 zu öffnen.

1. Wählen Sie **auf der** Windows-Taskleiste das Symbol Suchen aus.

1. Geben **Sie Indizierungsoptionen** in das Suchfeld ein.

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>Sind die von der Regel verwendeten Kriterien "Ausführung ausführbarer Dateien blockieren, es sei denn, sie erfüllen ein Prävalenz-, Alters- oder vertrauenswürdiges Listenkriterium" von einem Administrator konfigurierbar?

Nein. Die von dieser Regel verwendeten Kriterien werden vom Microsoft Cloud Protection beibehalten, um die vertrauenswürdige Liste mit daten aus der ganzen Welt auf dem neuesten Stand zu halten. Lokale Administratoren haben keinen Schreibzugriff, um diese Daten zu ändern. Wenn Sie diese Regel so konfigurieren möchten, dass sie für Ihr Unternehmen geeignet ist, können Sie der Ausschlussliste bestimmte Anwendungen hinzufügen, um zu verhindern, dass die Regel ausgelöst wird.

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>Ich habe die ASR-Regel aktiviert, ausführbare Dateien an der Ausführung blockieren, es sei denn, sie erfüllen ein Prävalenz-, Alters- oder *vertrauenswürdiges Listenkriterium.* Nach einiger Zeit habe ich eine Software aktualisiert, und die Regel blockiert sie jetzt, auch wenn sie noch nicht zuvor war. Ist etwas schief gelaufen?

Diese Regel basiert darauf, dass jede Anwendung einen bekannten Ruf hat, gemessen an der Verbreitung, dem Alter oder der Aufnahme in eine Liste vertrauenswürdiger Apps. Die Entscheidung der Regel, eine Anwendung zu blockieren oder zu erlauben, hängt letztlich von der Bewertung dieser Kriterien durch Microsoft Cloud Protection ab.

In der Regel kann der Cloudschutz feststellen, dass eine neue Version einer Anwendung so ähnlich wie frühere Versionen ist, dass sie nicht länger neu bewertet werden muss. Es kann jedoch einige Zeit dauern, bis die App nach dem Wechseln von Versionen, insbesondere nach einem größeren Update, eine Reputation aufbaut. In der Zwischenzeit können Sie die Anwendung der Ausschlussliste hinzufügen, um zu verhindern, dass diese Regel wichtige Anwendungen blockiert. Wenn Sie häufig neue Versionen von Anwendungen aktualisieren und mit diesen arbeiten, können Sie diese Regel stattdessen im Überwachungsmodus ausführen.

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>Ich habe kürzlich die ASR-Regel aktiviert, den Diebstahl von Anmeldeinformationen aus dem Windows Local Security Authority Subsystem *(lsass.exe)* blockieren, und ich habe eine große Anzahl von Benachrichtigungen erhalten. Was ist los?

Eine von dieser Regel generierte Benachrichtigung weist nicht unbedingt auf böswillige Aktivitäten hin. Diese Regel ist jedoch weiterhin hilfreich, um schädliche Aktivitäten zu blockieren, da Schadsoftware häufig lsass.exe, um unrechtmäßigen Zugriff auf Konten zu erhalten. Der lsass.exe speichert Benutzeranmeldeinformationen im Arbeitsspeicher, nachdem sich ein Benutzer angemeldet hat. Windows verwendet diese Anmeldeinformationen, um Benutzer zu überprüfen und lokale Sicherheitsrichtlinien anzuwenden.

Da viele legitime Prozesse an einem typischen Tag lsass.exe Anmeldeinformationen aufrufen, kann diese Regel besonders laut sein. Wenn eine bekannte legitime Anwendung bewirkt, dass diese Regel eine übermäßig viele Benachrichtigungen generiert, können Sie sie der Ausschlussliste hinzufügen. Die meisten anderen ASR-Regeln generieren eine relativ kleinere Anzahl von Benachrichtigungen im Vergleich zu diesem, da das Aufrufen von lsass.exe für die normale Funktionsweise vieler Anwendungen typisch ist.

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>Ist es eine gute Idee, die Regel Blockieren des Diebstahls von Anmeldeinformationen aus dem Lokalen Windows-Sicherheitsbehörde-Subsystem *(lsass.exe)* neben dem LSA-Schutz zu aktivieren?

Wenn Sie diese Regel aktivieren, bietet dies keinen zusätzlichen Schutz, wenn Sie [auch den LSA-Schutz](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) aktiviert haben. Sowohl der Regel- als auch der LSA-Schutz funktionieren auf dieselbe Weise, sodass beide gleichzeitig ausgeführt werden, wäre redundant. Manchmal können Sie den LSA-Schutz jedoch nicht aktivieren. In diesen Fällen können Sie diese Regel aktivieren, um einen gleichwertigen Schutz vor Schadsoftware zu bieten, die auf lsass.exe.

## <a name="see-also"></a>Siehe auch

* [Übersicht über die Reduzierung der Angriffsfläche](attack-surface-reduction.md)
* [Bewerten von Regeln zur Reduzierung der Angriffsfläche](evaluate-attack-surface-reduction.md)
* [Anpassen von Regeln zur Reduzierung der Angriffsfläche](customize-attack-surface-reduction.md)
* [Aktivieren von Regeln zur Reduzierung der Angriffsfläche](enable-attack-surface-reduction.md)
* [Kompatibilität von Microsoft Defender mit anderen Antiviren-/Antischasoftwareprogrammen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
