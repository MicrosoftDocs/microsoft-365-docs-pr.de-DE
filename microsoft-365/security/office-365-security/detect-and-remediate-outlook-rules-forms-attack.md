---
title: Erkennen und Behebung der Angriffe auf die Regeln und benutzerdefinierten Formularinjektionen.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Erfahren Sie, wie Sie die Angriffe auf Outlook-Regeln und benutzerdefinierte Formularinjektionen in Office 365 erkennen und benutzerdefinierte Formulare enlegieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22cfa97ae59fdd094c161cdaeff899dc1dd6507
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286393"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Erkennen und Behebung von Angriffen auf Outlook-Regeln und benutzerdefinierte Formulare

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Zusammenfassung** Erfahren Sie, wie Sie die Outlook-Regeln und benutzerdefinierten Forms-Injection-Angriffe in Office 365 erkennen und benutzerdefinierte Lösungen finden.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Was ist der Angriff auf die Einlösung von Outlook-Regeln und benutzerdefinierten Formularen?

Nachdem ein Angreifer ein Konto in Ihrem Mandanz verletzt hat und sich einräumt, wird versucht, eine Möglichkeit zu schaffen, in dem Unternehmen zu bleiben, oder eine Möglichkeit zu schaffen, wieder ein- und zurück zu kommen, nachdem sie gefunden und entfernt wurden. Dies wird als Einrichten eines Persistenzmechanismus bezeichnet. Zwei Möglichkeiten, dies zu tun, sind die Ausnutzung von Outlook-Regeln oder das Injizieren von benutzerdefinierten Formularen in Outlook.
In beiden Fällen wird die Regel oder das Formular vom Clouddienst bis zum Desktopclient synchronisiert, sodass ein vollständiges Format und die erneute Installation der Clientsoftware den Einfeinsmechanismus nicht ausschließen. Dies liegt daran, dass die Outlook-Clientsoftware, die sich erneut mit dem Postfach in der Cloud verbindet, die Regeln und Formulare aus der Cloud erneut herunter laden wird. Sobald die Regeln und Formulare vorhanden sind, verwendet der Angreifer sie zum Ausführen von Remote- oder benutzerdefiniertem Code, in der Regel zum Installieren von Schadsoftware auf dem lokalen Computer. Die Schadsoftware stiehlt dann erneut Anmeldeinformationen oder führt andere schädliche Aktivitäten aus.
Die gute Nachricht ist: Wenn Sie Ihre Clients auf die neueste Version gepatcht halten, sind Sie nicht anfällig für die Bedrohung, da aktuelle Outlook-Client-Standardeinstellungen beide Mechanismen blockieren.

Die Angriffe folgen in der Regel den folgenden Mustern:

**Der Regel-Exploit:**

1. Der Angreifer stiehlt den Benutzernamen und das Kennwort eines Ihrer Benutzer.

2. Der Angreifer meldet sich dann bei diesem Benutzer-Exchange-Postfach an. Das Postfach kann sich entweder in Exchange online oder lokal in Exchange benennen.

3. Der Angreifer erstellt dann eine Weiterleitungsregel im Postfach, die ausgelöst wird, wenn das Postfach eine E-Mail empfängt, die den Kriterien der Regel entspricht. Die Kriterien der Regel und der Inhalt der Trigger-E-Mail sind aufeinander zugeschnitten.

4. Der Angreifer sendet die Trigger-E-Mail an den Benutzer, der sein Postfach normal verwendet.

5. Wenn die E-Mail empfangen wird, wird die Regel ausgelöst. Die Regelaktion besteht in der Regel im Starten einer Anwendung auf einem Remoteserver (WebDAV).

6. Die Anwendung installiert in der Regel Schadsoftware, z. B. [Powershell - lokal](https://www.powershellempire.com/)auf dem Computer des Benutzers.

7. Die Schadsoftware ermöglicht es dem Angreifer, den Benutzernamen und das Kennwort des Benutzers oder andere Anmeldeinformationen vom lokalen Computer erneut zu stehlen und andere schädliche Aktivitäten durchzuführen.

**Der Forms Exploit:**

1. Der Angreifer stiehlt den Benutzernamen und das Kennwort eines Ihrer Benutzer.

2. Der Angreifer melden sich dann bei diesem Benutzer-Exchange-Postfach an. Das Postfach kann sich entweder in Exchange online oder lokal in Exchange benennen.

3. Anschließend erstellt der Angreifer eine benutzerdefinierte E-Mail-Formularvorlage und fügt sie in das Postfach des Benutzers ein. Das benutzerdefinierte Formular wird ausgelöst, wenn das Postfach eine E-Mail empfängt, für die das Postfach das benutzerdefinierte Formular laden muss. Das benutzerdefinierte Formular und das E-Mail-Format sind aufeinander zugeschnitten.
4. Der Angreifer sendet die Trigger-E-Mail an den Benutzer, der sein Postfach normal verwendet.

5. Wenn die E-Mail empfangen wird, wird das Formular geladen. Das Formular startet eine Anwendung auf einem Remoteserver (WebDAV).

6. Die Anwendung installiert in der Regel Schadsoftware, z. B. [Powershell - lokal](https://www.powershellempire.com/)auf dem Computer des Benutzers.

7. Die Schadsoftware ermöglicht es dem Angreifer, den Benutzernamen und das Kennwort des Benutzers oder andere Anmeldeinformationen vom lokalen Computer erneut zu stehlen und andere schädliche Aktivitäten durchzuführen.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Wie könnte ein Angriff auf Regeln und benutzerdefinierte Formulare wie office 365 aussehen?

Diese Persistenzmechanismen werden ihren Benutzern wahrscheinlich nicht aufgefallen sein und sind in einigen Fällen sogar unsichtbar. In diesem Artikel erfahren Sie, wie Sie nach einem der sieben unten aufgeführten Zeichen (Indicators of Compromise) suchen. Wenn Sie eine dieser Lösungen finden, müssen Sie Korrekturschritte ausführen.

- Indikatoren für die Regelkompromittiert:

  - Regelaktion ist das Starten einer Anwendung.

  - Regel verweist auf EXE, ZIP oder URL.

  - Suchen Sie auf dem lokalen Computer nach neuen Prozessstarts, die von der Outlook-PID stammen.

- Indikatoren der Benutzerdefinierten Formulare:

  - Benutzerdefiniertes Formular, das als eigene Nachrichtenklasse gespeichert wurde.

  - Die Nachrichtenklasse enthält ausführbaren Code.

  - In der Regel in persönlichen Formularbibliothek- oder Posteingangsordnern gespeichert.

  - Das Formular heißt IPM. Hinweis. [Benutzerdefinierter Name].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Schritte zum Suchen von Anzeichen für diesen Angriff und deren Bestätigung

Sie können eine dieser beiden Methoden verwenden, um den Angriff zu bestätigen:

- Überprüfen Sie manuell die Regeln und Formulare für jedes Postfach mithilfe des Outlook-Clients. Diese Methode ist sorgfältig, Aber Sie können den Postfachbenutzer nur zu einem Zeitpunkt überprüfen, was sehr zeitaufwändig sein kann, wenn sie von vielen Benutzern überprüft werden müssen. Es kann auch zu einer Verletzung des Computers führen, von dem aus Sie die Überprüfung ausführen.

- Verwenden Sie [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-Skript, um automatisch alle E-Mail-Weiterleitungsregeln und benutzerdefinierten Formulare für alle Benutzer in Ihrer Mandanz zu dumpen. Dies ist die schnellste und sicherste Methode mit dem geringsten Aufwand.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Bestätigen des Regelangriffs mithilfe des Outlook-Clients

1. Öffnen Sie den Benutzer-Outlook-Client als Benutzer. Der Benutzer benötigt möglicherweise Ihre Hilfe, um die Regeln für sein Postfach zu untersuchen.

2. Informationen zum [Öffnen der](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) Regelschnittstelle in Outlook finden Sie im Artikel "Verwalten von E-Mail-Nachrichten mithilfe von Regeln".

3. Suchen Sie nach Regeln, die der Benutzer nicht erstellt hat, oder nach unerwarteten Regeln oder Regeln mit verdächtigen Namen.

4. Suchen Sie in der Regelbeschreibung nach Regelaktionen, die gestartet und verwendet werden oder auf eine verweisen. EXE, . ZIP-Datei oder zum Starten einer URL.

5. Suchen Sie nach neuen Prozessen, die mit der Verwendung der Outlook-Prozess-ID beginnen. Weitere Informationen finden [Sie unter "Prozess-ID suchen".](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Schritte zum Bestätigen des Formularangriffs mithilfe des Outlook-Clients

1. Öffnen Sie den Benutzer-Outlook-Client als Benutzer.

2. Führen Sie die Schritte unter ["Anzeigen der Registerkarte "Entwickler"](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) für die Benutzerversion von Outlook aus.

3. Öffnen Sie die jetzt sichtbare Entwicklerregisterkarte in Outlook, und klicken Sie **auf "Formular entwerfen".**

4. Wählen Sie **den Posteingang aus** der Liste **"Suchen in"** aus. Suchen Sie nach benutzerdefinierten Formularen. Benutzerdefinierte Formulare sind selten genug, dass sie einen tiefer liegenden Einblick wert sind, wenn Sie benutzerdefinierte Formulare haben.

5. Untersuchen Sie alle benutzerdefinierten Formulare, insbesondere solche, die als ausgeblendet markiert sind.

6. Öffnen Sie benutzerdefinierte  Formulare, und klicken Sie in der Formulargruppe auf **"Code** anzeigen", um zu sehen, was beim Laden des Formulars ausgeführt wird.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Schritte zum Bestätigen des Regel- und Formularangriffs mithilfe von PowerShell

Die einfachste Möglichkeit zum Überprüfen eines Regel- oder benutzerdefinierten Formularangriffs besteht in der Ausführung des [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-Skripts. Dieses Skript stellt eine Verbindung mit jedem Postfach in Ihrem Mandanten und stellt alle Regeln und Formulare in zwei .csv-Dateien ab.

#### <a name="pre-requisites"></a>Voraussetzungen

Sie benötigen einen globalen Administrator, um das Skript ausführen zu können, da das Skript eine Verbindung mit jedem Postfach in der Mandanz herstellt, um die Regeln und Formulare zu lesen.

1. Melden Sie sich bei dem Computer an, auf dem Sie das Skript mit lokalen Administratorrechten ausführen.

2. Laden Sie das Skript Get-AllTenantRulesAndForms.ps1 GitHub herunter, oder kopieren Sie es in einen Ordner, aus dem Sie es ausführen. Das Skript erstellt zwei dateien mit Datumsstempeln in diesem Ordner, MailboxFormsExport-yyyy-mm-dd.csv und MailboxRulesExport-yyyy-mm-dd.csv.

3. Öffnen Sie eine PowerShell-Instanz als Administrator, und öffnen Sie den Ordner, in dem Sie das Skript gespeichert haben.

4. Führen Sie diese Befehlszeile von PowerShell wie folgt `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretieren der Ausgabe

- **MailboxRulesExport-*yyyy-mm-dd*.csv**: Untersuchen Sie die Regeln (eine pro Zeile) auf Aktionsbedingungen, die Anwendungen oder ausführbare Dateien enthalten:

  - **ActionType (Spalte A):** Wenn der Wert "ID_ACTION_CUSTOM" angezeigt wird, ist die Regel wahrscheinlich bösartig.

  - **Is PotentiallyMalicious (Spalte D):** Wenn dieser Wert "TRUE" ist, ist die Regel wahrscheinlich schädlich.

  - **ActionCommand (Spalte G):** Wenn hier eine Anwendung oder eine Datei mit einer EXE-, ZIP-Erweiterung oder einem Eintrag aufgeführt wird, der auf eine URL verweist, die nicht enthalten sein soll, ist die Regel wahrscheinlich schädlich.

- **MailboxFormsExport-*yyyy-mm-dd*.csv:** Im Allgemeinen ist die Verwendung von benutzerdefinierten Formularen sehr selten. Wenn sie in dieser Arbeitsmappe enthalten sind, öffnen Sie das Postfach dieses Benutzers und untersuchen das Formular selbst. Wenn Ihre Organisation sie nicht absichtlich dort abting, ist dies wahrscheinlich schädlich.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Beenden und Behebung des Angriffs auf Regeln und Formulare in Outlook

Wenn Sie Nachweise für einen dieser Angriffe finden, ist die Behebung einfach, löschen Sie einfach die Regel oder das Formular aus dem Postfach. Sie können dies mit dem Outlook-Client oder mithilfe der Remote-PowerShell tun, um Regeln zu entfernen.

### <a name="using-outlook"></a>Verwenden von Outlook

1. Identifizieren Sie alle Geräte, die der Benutzer mit Outlook verwendet hat. Alle müssen von potenzieller Schadsoftware bereinigt werden. Lassen Sie nicht zu, dass sich der Benutzer anmeldet und E-Mails verwendet, bis alle Geräte bereinigt wurden.

2. Führen Sie die Schritte in ["Löschen einer Regel"](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) für jedes Gerät aus.

3. Wenn Sie sich nicht sicher sind, ob andere Schadsoftware vor auftritt, können Sie die software auf dem Gerät formatieren und erneut installieren. Für mobile Geräte können Sie den Schritten des Herstellers folgen, um das Gerät auf das Werksimage zurückzusetzen.

4. Installieren Sie die neuesten Versionen von Outlook. Denken Sie daran, dass die aktuelle Version von Outlook beide Arten dieses Angriffs standardmäßig blockiert.

5. Nachdem alle Offlinekopien des Postfachs entfernt wurden, setzen Sie das Kennwort des Benutzers zurück (verwenden Sie ein qualitativ hochwertiges Kennwort), und führen Sie die Schritte im [Setup](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) der mehrstufigen Authentifizierung für Benutzer aus, wenn MFA noch nicht aktiviert wurde. Dadurch wird sichergestellt, dass die Anmeldeinformationen des Benutzers nicht auf andere Weise verfügbar gemacht werden (z. B. Phishing oder Kennwort erneut).

### <a name="using-powershell"></a>Verwendung von PowerShell

Es gibt zwei Remote-PowerShell-Cmdlets, die Sie verwenden können, um gefährliche Regeln zu entfernen oder zu deaktivieren. Führen Sie einfach die folgenden Schritte aus.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Schritte für Postfächer auf einem Exchange-Server

1. Stellen Sie mithilfe der Remote-PowerShell eine Verbindung mit dem Exchange Server herzustellen. Führen Sie die Schritte in [Connect to Exchange servers using remote PowerShell aus.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Wenn Sie eine einzelne Regel, mehrere Regeln oder alle Regeln vollständig aus einem Postfach entfernen möchten, verwenden Sie das [Cmdlet "Remove-InboxRule".](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule)

3. Wenn Sie die Regel und deren Inhalt zur weiteren Untersuchung beibehalten möchten, verwenden Sie das [Cmdlet "Disable-InboxRule".](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Schritte für Postfächer in Exchange Online

1. Führen Sie die Schritte unter [Herstellen einer Verbindung mit Exchange Online mithilfe von PowerShell aus.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Wenn Sie eine einzelne Regel, mehrere Regeln oder alle Regeln vollständig aus einem Postfach entfernen möchten, verwenden Sie das Cmdlet ["Remove-Inbox Rule".](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule)

3. Wenn Sie die Regel und deren Inhalt zur weiteren Untersuchung beibehalten möchten, verwenden Sie das [Cmdlet "Disable-InboxRule".](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Minimieren zukünftiger Angriffe

### <a name="first-protect-your-accounts"></a>First: protect your accounts

Die Exploits für Regeln und Formulare werden nur von einem Angreifer verwendet, nachdem er eines der Benutzerkonten gestohlen oder verletzt hat. Der erste Schritt, die Verwendung dieser Exploits gegen Ihre Organisation zu verhindern, besteht also im aggressiven Schutz Ihrer Benutzerkonten. Einige der am häufigsten verwendeten Arten, wie Konten verletzt werden, sind Phishing- oder [Kennwort-Spray-Angriffe.](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)

Die beste Möglichkeit zum Schutz Ihrer Benutzerkonten und insbesondere Ihrer Administratorkonten ist die Einrichtung der [mehrstufigen Authentifizierung für Benutzer.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) Sie sollten außerdem:

- Überwachen Sie, wie auf Ihre Benutzerkonten [zugegriffen und diese verwendet werden.](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) Möglicherweise verhindern Sie die anfängliche Verletzung nicht, aber Sie kürzen die Dauer und die Auswirkungen der Verletzung, indem Sie sie früher erkennen. Sie können diese [Office 365 Cloud App Security-Richtlinien](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) verwenden, um Ihre Konten zu überwachen und bei ungewöhnlichen Aktivitäten zu warnen:

  - **Mehrere** fehlgeschlagene Anmeldeversuche: Diese Richtlinie profiliert Ihre Umgebung und löst Warnungen aus, wenn Benutzer mehrere fehlgeschlagene Anmeldeaktivitäten in einer einzigen Sitzung im Hinblick auf die gelernte Basis ausführen, was auf eine versuchte Verletzung hinweisen könnte.

  - **Unmögliche Reise:** Diese Richtlinie profiliert Ihre Umgebung und löst Warnungen aus, wenn Aktivitäten von demselben Benutzer innerhalb eines Zeitraums erkannt werden, der kürzer als die erwartete Reisezeit zwischen den beiden Standorten ist. Dies kann darauf hinweisen, dass ein anderer Benutzer dieselben Anmeldeinformationen verwendet. Das Erkennen dieses anomalen Verhaltens erfordert einen anfänglichen Lernzeitraum von sieben Tagen, in dem das Aktivitätsmuster eines neuen Benutzers erlernen wird.

  - Ungewöhnliche **imitierte Aktivität (nach Benutzer):** Diese Richtlinie profiliert Ihre Umgebung und löst Benachrichtigungen aus, wenn Benutzer mehrere imitierte Aktivitäten in einer einzigen Sitzung im Hinblick auf den gelernten Basisplan ausführen, was auf eine versuchte Verletzung hinweisen kann.

- Nutzen Sie ein Tool wie [Office 365 Secure Score,](https://securescore.office.com/) um Kontosicherheitskonfigurationen und -verhaltensweisen zu verwalten.

### <a name="second-keep-your-outlook-clients-current"></a>Zweitens: Halten Sie Ihre Outlook-Clients auf dem aktuellen Stand

Vollständig aktualisierte und gepatchte Versionen von Outlook 2013 und 2016 deaktivieren standardmäßig die Regel-/Formularaktion "Anwendung starten". Dadurch wird sichergestellt, dass die Regel- und Formularaktionen blockiert werden, auch wenn ein Angreifer das Konto verletzt. Sie können die neuesten Updates und Sicherheitspatches installieren, indem Sie die Schritte unter ["Installieren von Office-Updates" ausführen.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Hier sind die Patchversionen für Ihre Outlook 2013- und 2016-Clients:

- **Outlook 2016**: 16.0.4534.1001 oder höher.

- **Outlook 2013**: 15.0.4937.1000 oder höher.

Weitere Informationen zu den einzelnen Sicherheitspatches finden Sie unter:

- [Outlook 2016-Sicherheitspatch](https://support.microsoft.com/help/3191883)

- [Outlook 2013-Sicherheitspatch](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Dritte: Überwachen Ihrer Outlook-Clients

Beachten Sie, dass es auch bei installierten Patches und Updates möglich ist, dass ein Angreifer die Konfiguration des lokalen Computers so ändert, dass das Verhalten "Anwendung starten" erneut aktiviert wird. Sie können die [erweiterte Gruppenrichtlinienverwaltung verwenden,](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) um lokale Computerrichtlinien auf Ihren Clients zu überwachen und zu erzwingen.

Anhand der Informationen unter "Anzeigen der Systemregistrierung mithilfe von [64-Bit-Versionen](https://support.microsoft.com/help/305097)von Windows" können Sie sehen, ob "Anwendung starten" über eine Außerkraftsetzung in der Registrierung erneut aktiviert wurde. Überprüfen Sie die folgenden Unterschlüssel:

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Suchen Sie nach dem Schlüssel "EnableUnsafeClientMailRules". Wenn er dort ist und auf 1 festgelegt ist, wurde der Outlook-Sicherheitspatch außer Kraft gesetzt, und der Computer ist anfällig für den Formular-/Regelangriff. Wenn der Wert 0 ist, ist die Aktion "Anwendung starten" deaktiviert. Wenn die aktualisierte und gepatchte Version von Outlook installiert ist und dieser Registrierungsschlüssel nicht vorhanden ist, ist ein System nicht anfällig für diese Angriffe.

Kunden mit lokalen Exchange-Installationen sollten erwägen, ältere Versionen von Outlook zu blockieren, für die keine Patches verfügbar sind. Details zu diesem Vorgang finden Sie im Artikel "Konfigurieren der [Blockierung von Outlook-Clients".](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Sichern von Microsoft 365 wie ein Profi für Internetsicherheit

Ihr Microsoft 365-Abonnement bietet eine Reihe von leistungsfähigen Funktionen für Sicherheit, die Sie zum Schutz Ihrer Daten und Ihrer Benutzer verwenden können. Verwenden Sie die [Microsoft 365-Sicherheits-Roadmap: Top-Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](security-roadmap.md) zum Implementieren von empfohlenen Microsoft-Best-Practices für den Schutz Ihres Microsoft 365-Mandanten.

- Aufgaben, die in den ersten 30 Tagen ausgeführt werden sollten. Diese sind unmittelbar gültig und haben nur geringe Auswirkungen für die Benutzer.

- Aufgaben, die innerhalb von 90 Tagen ausgeführt werden sollten. Diese erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

- Über 90 Tage hinaus. Diese Verbesserungen werden in den ersten 90 Tagen Ihrer Arbeit umgesetzt.

## <a name="see-also"></a>Siehe auch:

- [Bösartige Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post über Rules Vector bietet eine detaillierte Überprüfung der Funktionsweise der Outlook-Regeln.

- [MAPI über HTTP und Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) im Blog "Sensepost" zu Mailrule Pwnage diskutieren ein Tool namens Ruler, mit dem Sie Postfächer über Die Regeln von Outlook ausnutzen können.

- [Outlook Forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.

- [Linealcodebase](https://github.com/sensepost/ruler)

- [Lineal Indicators of Compromise](https://github.com/sensepost/notruler/blob/master/iocs.md)
