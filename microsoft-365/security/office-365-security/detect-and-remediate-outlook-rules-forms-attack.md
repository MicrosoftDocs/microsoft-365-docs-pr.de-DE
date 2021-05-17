---
title: Erkennen und Behebung der Outlook und benutzerdefinierten Formularinjektionsangriffen.
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
description: Erfahren Sie, wie Sie die Outlook und benutzerdefinierten Formularinjektionsangriffe in Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0846051b65b34ec26358f87bb4ca49302573e6e7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205918"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Erkennen und Outlook von Regel- und Benutzerdefinierten Formularinjektionsangriffen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Zusammenfassung** Erfahren Sie, wie Sie die Outlook und benutzerdefinierten Forms-Injections-Angriffe in Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Was ist der Outlook Rules and Custom Forms-Injection-Angriff?

Nachdem ein Angreifer Zugriff auf Ihre Organisation erhalten hat, versucht er, eine Fußstapfe zu schaffen, in der er bleiben oder sich wieder einmisten kann, nachdem er entdeckt wurde. Diese Aktivität wird als *Einrichten eines Persistenzmechanismus bezeichnet.* Es gibt zwei Möglichkeiten, mit deren Outlook Angreifer einen Persistenzmechanismus einrichten können:

- Durch ausnutzen Outlook Regeln.
- Durch Injizieren von benutzerdefinierten Formularen in Outlook.

Das erneute Outlook oder sogar der betroffenen Person einen neuen Computer zu geben, hilft nicht. Wenn die Neuinstallation von Outlook eine Verbindung mit dem Postfach herstellt, werden alle Regeln und Formulare aus der Cloud synchronisiert. Die Regeln oder Formulare sind in der Regel so konzipiert, dass Remotecode ausgeführt und Schadsoftware auf dem lokalen Computer installiert wird. Die Schadsoftware stiehlt Anmeldeinformationen oder führt andere unerlaubte Aktivitäten aus.

Die gute Nachricht ist: Wenn Sie Ihre Outlook-Clients auf die neueste Version gepatcht halten, sind Sie nicht anfällig für die Bedrohung, da aktuelle Outlook Clienteinstellungen beide Mechanismen blockieren.

Die Angriffe folgen in der Regel folgenden Mustern:

**Der Regel-Exploit**:

1. Der Angreifer stiehlt die Anmeldeinformationen eines Benutzers.

2. Der Angreifer meldet sich beim Postfach des Benutzers Exchange (Exchange Online oder lokalen Exchange).

3. Der Angreifer erstellt eine Posteingangsregel für die Weiterleitung im Postfach. Die Weiterleitungsregel wird ausgelöst, wenn das Postfach eine bestimmte Nachricht vom Angreifer empfängt, die den Bedingungen der Regel entspricht. Die Regelbedingungen und das Nachrichtenformat sind aufeinander zugeschnitten.

4. Der Angreifer sendet die Trigger-E-Mail an das gefährdete Postfach, das vom ahnungslosen Benutzer weiterhin normal verwendet wird.

5. Wenn das Postfach eine Nachricht empfängt, die den Bedingungen der Regel entspricht, wird die Aktion der Regel angewendet. In der Regel besteht die Regelaktion im Starten einer Anwendung auf einem Remoteserver (WebDAV).

6. In der Regel installiert die Anwendung Schadsoftware auf dem Computer des Benutzers (z. B. [PowerShell-Reich](https://www.powershellempire.com/)).

7. Die Schadsoftware ermöglicht es dem Angreifer, den Benutzernamen und das Kennwort des Benutzers oder andere Anmeldeinformationen vom lokalen Computer zu stehlen (oder erneut zu stehlen) und andere schädliche Aktivitäten durchzuführen.

**Der Forms Exploit**:

1. Der Angreifer stiehlt die Anmeldeinformationen eines Benutzers.

2. Der Angreifer meldet sich beim Postfach des Benutzers Exchange (Exchange Online oder lokalen Exchange).

3. Der Angreifer fügt eine benutzerdefinierte E-Mail-Formularvorlage in das Postfach des Benutzers ein. Das benutzerdefinierte Formular wird ausgelöst, wenn das Postfach eine bestimmte Nachricht vom Angreifer empfängt, für die das Postfach das benutzerdefinierte Formular laden muss. Das benutzerdefinierte Formular und das Nachrichtenformat sind aufeinander zugeschnitten.

4. Der Angreifer sendet die Trigger-E-Mail an das gefährdete Postfach, das vom ahnungslosen Benutzer weiterhin normal verwendet wird.

5. Wenn das Postfach die Nachricht empfängt, lädt das Postfach das erforderliche Formular. Das Formular startet eine Anwendung auf einem Remoteserver (WebDAV).

6. In der Regel installiert die Anwendung Schadsoftware auf dem Computer des Benutzers (z. B. [PowerShell-Reich](https://www.powershellempire.com/)).

7. Die Schadsoftware ermöglicht es dem Angreifer, den Benutzernamen und das Kennwort des Benutzers oder andere Anmeldeinformationen vom lokalen Computer zu stehlen (oder erneut zu stehlen) und andere schädliche Aktivitäten durchzuführen.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Wie könnte ein Regel- und Benutzerdefinierte Formularinjektionsangriff aussehen, Office 365?

Diese Persistenzmechanismen werden ihren Benutzern wahrscheinlich nicht aufgefallen sein und können in einigen Fällen sogar für sie unsichtbar sein. In diesem Artikel erfahren Sie, wie Sie nach den sieben unten aufgeführten Zeichen (Indikatoren für Kompromisse) suchen. Wenn Sie einen dieser Schritte finden, müssen Sie Korrekturschritte ausführen.

- **Indikatoren für den Regelkompromiss:**
  - Regelaktion ist das Starten einer Anwendung.
  - Regel verweist auf EXE, ZIP oder URL.
  - Suchen Sie auf dem lokalen Computer nach neuen Prozessstarts, die von der Outlook stammen.

- **Indikatoren des Benutzerdefinierten Formularkompromisss:**
  - Benutzerdefinierte Formulare, die als eigene Nachrichtenklasse gespeichert werden.
  - Die Nachrichtenklasse enthält ausführbaren Code.
  - In der Regel werden bösartige Formulare in Ordnern der Persönlichen Formularbibliothek oder des Posteingangs gespeichert.
  - Das Formular heißt IPM. Hinweis. [benutzerdefinierter Name].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Schritte zum Suchen nach Anzeichen dieses Angriffs und zur Bestätigung dieses Angriffs

Sie können eine der folgenden Methoden verwenden, um den Angriff zu bestätigen:

- Untersuchen Sie manuell die Regeln und Formulare für jedes Postfach mithilfe des Outlook Client. Diese Methode ist gründlich, Sie können jedoch nur ein Postfach gleichzeitig überprüfen. Diese Methode kann sehr zeitaufwändig sein, wenn Sie viele Benutzer zu überprüfen haben, und kann auch den computer infizieren, den Sie verwenden.

- Verwenden Sie [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-Skript, um automatisch alle E-Mail-Weiterleitungsregeln und benutzerdefinierten Formulare für alle Benutzer in Ihrer Mandanz zu dumpen. Dies ist die schnellste und sicherste Methode mit dem geringsten Aufwand.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Bestätigen des Regelangriffs mithilfe des Outlook Client

1. Öffnen Sie die Benutzer Outlook Client als Benutzer. Der Benutzer benötigt möglicherweise Ihre Hilfe bei der Untersuchung der Regeln für sein Postfach.

2. Im Artikel [Verwalten von E-Mail-Nachrichten mithilfe von Regeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) finden Sie Informationen zum Öffnen der Regelschnittstelle in Outlook.

3. Suchen Sie nach Regeln, die der Benutzer nicht erstellt hat, oder nach unerwarteten Regeln oder Regeln mit verdächtigen Namen.

4. Suchen Sie in der Regelbeschreibung nach Regelaktionen, die starten und anwendung oder auf eine .EXE, .ZIP oder auf das Starten einer URL verweisen.

5. Suchen Sie nach neuen Prozessen, die mit der Outlook prozess-ID beginnen. Weitere Informationen [finden Sie unter Suchen der Prozess-ID](/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Schritte zum Bestätigen des Forms-Angriffs mithilfe des Outlook Client

1. Öffnen Sie den Outlook Client als Benutzer.

2. Führen Sie die Schritte unter [Anzeigen der Registerkarte Entwickler](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) für die Benutzerversion von Outlook.

3. Öffnen Sie die jetzt sichtbare Registerkarte Entwickler in Outlook, und klicken Sie **auf Formular entwerfen**.

4. Wählen Sie **den Posteingang** aus der Liste **Suchen in** aus. Suchen Sie nach benutzerdefinierten Formularen. Benutzerdefinierte Formulare sind selten genug, dass es einen tieferen Blick wert ist, wenn Sie über benutzerdefinierte Formulare verfügen.

5. Untersuchen Sie alle benutzerdefinierten Formulare, insbesondere die als ausgeblendet markierten.

6. Öffnen Sie benutzerdefinierte Formulare, und klicken Sie in der **Gruppe Formular** auf **Code** anzeigen, um zu sehen, was beim Laden des Formulars ausgeführt wird.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Schritte zum Bestätigen des Regel- und Formularangriffs mithilfe von PowerShell

Die einfachste Möglichkeit zum Überprüfen eines Regel- oder benutzerdefinierten Formularangriffs besteht in der Ausführung des [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-Skripts. Mit diesem Skript wird eine Verbindung mit jedem Postfach in Ihrem Mandanten hergestellt, und alle Regeln und Formulare werden in zwei .csv gespeichert.

#### <a name="pre-requisites"></a>Voraussetzungen

Sie benötigen globale Administratorrechte, um das Skript ausführen zu können, da das Skript eine Verbindung mit jedem Postfach in der Mandanz herstellt, um die Regeln und Formulare zu lesen.

1. Melden Sie sich bei dem Computer an, auf dem Sie das Skript mit lokalen Administratorrechten ausführen.

2. Laden Sie das Skript Get-AllTenantRulesAndForms.ps1 aus GitHub in einen Ordner herunter, aus dem Sie es ausführen. Das Skript erstellt zwei Datumsstempeldateien für diesen Ordner, MailboxFormsExport-yyyy-mm-dd.csv und MailboxRulesExport-yyyy-mm-dd.csv.

3. Öffnen Sie eine PowerShell-Instanz als Administrator, und öffnen Sie den Ordner, in dem Sie das Skript gespeichert haben.

4. Führen Sie diese PowerShell-Befehlszeile wie folgt `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretieren der Ausgabe

- **MailboxRulesExport-*yyyy-mm-dd*.csv**: Untersuchen Sie die Regeln (eine pro Zeile) auf Aktionsbedingungen, die Anwendungen oder ausführbare Dateien enthalten:

  - **ActionType (Spalte A):** Wenn der Wert "ID_ACTION_CUSTOM" angezeigt wird, ist die Regel wahrscheinlich bösartig.

  - **IsPotentiallyMalicious (Spalte D):** Wenn dieser Wert "TRUE" ist, ist die Regel wahrscheinlich bösartig.

  - **ActionCommand (Spalte G):** Wenn in dieser Spalte eine Anwendung oder eine Datei mit .exe- oder .zip-Erweiterungen oder ein unbekannter Eintrag aufgeführt wird, der auf eine URL verweist, ist die Regel wahrscheinlich bösartig.

- **MailboxFormsExport-*yyyy-mm-dd*.csv**: Im Allgemeinen ist die Verwendung von benutzerdefinierten Formularen selten. Wenn Sie eine in dieser Arbeitsmappe finden, öffnen Sie das Postfach dieses Benutzers und untersuchen das Formular selbst. Wenn Ihre Organisation sie nicht absichtlich dort ausgedrückt hat, ist dies wahrscheinlich bösartig.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Beenden und Behebung des Outlook und Formularangriffs

Wenn Sie einen Nachweis für einen dieser Angriffe finden, ist die Behebung einfach, löschen Sie einfach die Regel oder das Formular aus dem Postfach. Sie können dies mit dem Outlook oder mithilfe von Remote PowerShell tun, um Regeln zu entfernen.

### <a name="using-outlook"></a>Verwenden Outlook

1. Identifizieren Sie alle Geräte, die der Benutzer mit Outlook. Sie alle müssen von potenzieller Schadsoftware bereinigt werden. Lassen Sie nicht zu, dass sich der Benutzer anmeldet und E-Mails verwendet, bis alle Geräte bereinigt sind.

2. Führen Sie die Schritte unter [Löschen einer Regel für](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) jedes Gerät aus.

3. Wenn Sie sich nicht sicher sind, ob andere Schadsoftware auftritt, können Sie die software auf dem Gerät formatieren und neu installieren. Für mobile Geräte können Sie die Schritte des Herstellers ausführen, um das Gerät auf das Werksimage zurückzusetzen.

4. Installieren Sie die neuesten Versionen von Outlook. Beachten Sie, dass die aktuelle Version Outlook beide Arten dieses Angriffs standardmäßig blockiert.

5. Nachdem alle Offlinekopien des Postfachs entfernt wurden, setzen Sie das Kennwort des Benutzers zurück (verwenden Sie ein qualitativ hochwertiges Kennwort), und führen Sie die Schritte unter [Setup multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) if MFA has not already been enabled aus. Dadurch wird sichergestellt, dass die Anmeldeinformationen des Benutzers nicht auf andere Weise verfügbar gemacht werden (z. B. Phishing oder Kennwort erneut).

### <a name="using-powershell"></a>Verwendung von PowerShell

Es gibt zwei Remote-PowerShell-Cmdlets, die Sie verwenden können, um gefährliche Regeln zu entfernen oder zu deaktivieren. Führen Sie einfach die Schritte aus.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Schritte für Postfächer, die sich auf einem Exchange befinden

1. Verbinden auf den Exchange server mithilfe von Remote PowerShell. Führen Sie die Schritte in [Verbinden, Exchange Server mithilfe von Remote PowerShell zu verwenden.](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Wenn Sie eine einzelne Regel, mehrere Regeln oder alle Regeln vollständig aus einem Postfach entfernen möchten, verwenden Sie das [Cmdlet Remove-InboxRule.](/powershell/module/exchange/Remove-InboxRule)

3. Wenn Sie die Regel und deren Inhalt für weitere Untersuchungen beibehalten möchten, verwenden Sie das [Cmdlet Disable-InboxRule.](/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Schritte für Postfächer in Exchange Online

1. Führen Sie die Schritte in [Verbinden, um Exchange Online PowerShell zu verwenden.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Wenn Sie eine einzelne Regel, mehrere Regeln oder alle Regeln vollständig aus einem Postfach entfernen möchten, verwenden Sie das [Cmdlet Remove-Inbox Rule.](/powershell/module/exchange/Remove-InboxRule)

3. Wenn Sie die Regel und deren Inhalt für weitere Untersuchungen beibehalten möchten, verwenden Sie das [Cmdlet Disable-InboxRule.](/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Minimieren zukünftiger Angriffe

### <a name="first-protect-your-accounts"></a>First: protect your accounts

Die Exploits für Regeln und Formulare werden nur von einem Angreifer verwendet, nachdem er eines der Konten Ihres Benutzers gestohlen oder verletzt hat. Ihr erster Schritt, um die Verwendung dieser Exploits gegen Ihre Organisation zu verhindern, besteht also im aggressiven Schutz Ihrer Benutzerkonten. Einige der am häufigsten verwendeten Methoden, mit der Konten verletzt werden, sind Phishing- oder [Kennwort-Spray-Angriffe.](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)

Die beste Möglichkeit zum Schutz Ihrer Benutzerkonten und insbesondere Ihrer Administratorkonten besteht in der Einrichtung der [mehrstufigen Authentifizierung für Benutzer.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) Sie sollten außerdem:

- Überwachen Sie, wie auf Ihre [Benutzerkonten zugegriffen und verwendet wird.](/azure/active-directory/active-directory-view-access-usage-reports) Sie können die anfängliche Verletzung möglicherweise nicht verhindern, aber Sie kürzen die Dauer und die Auswirkungen der Verletzung, indem Sie sie früher erkennen. Sie können diese Richtlinien Office 365 Cloud App Security [verwenden,](/cloud-app-security/what-is-cloud-app-security) um Ihre Konten zu überwachen und bei ungewöhnlichen Aktivitäten zu warnen:

  - **Mehrere** fehlgeschlagene Anmeldeversuche: Diese Richtlinie profiliert Ihre Umgebung und löst Warnungen aus, wenn Benutzer mehrere fehlgeschlagene Anmeldeaktivitäten in einer einzigen Sitzung im Hinblick auf die gelernte Basislinie ausführen, was auf eine versuchte Verletzung hinweisen kann.

  - **Unmögliche Reise:** Diese Richtlinie profiliert Ihre Umgebung und löst Warnungen aus, wenn Aktivitäten vom gleichen Benutzer an unterschiedlichen Orten innerhalb eines Zeitraums erkannt werden, der kürzer als die erwartete Reisezeit zwischen den beiden Standorten ist. Dies kann darauf hinweisen, dass ein anderer Benutzer dieselben Anmeldeinformationen verwendet. Das Erkennen dieses anomalen Verhaltens erfordert einen anfänglichen Lernzeitraum von sieben Tagen, in dem er das Aktivitätsmuster eines neuen Benutzers lernt.

  - Ungewöhnliche imitierte Aktivität **(nach Benutzer):** Diese Richtlinie profiliert Ihre Umgebung und löst Warnungen aus, wenn Benutzer mehrere identitätswechselte Aktivitäten in einer einzigen Sitzung im Hinblick auf die gelernte Basislinie ausführen, was auf eine versuchte Verletzung hinweisen kann.

- Verwenden Sie ein Tool wie [Office 365 Secure Score zum](https://securescore.office.com/) Verwalten von Kontosicherheitskonfigurationen und -verhaltensweisen.

### <a name="second-keep-your-outlook-clients-current"></a>Second: Keep your Outlook clients current

Vollständig aktualisierte und gepatchte Versionen von Outlook 2013 und 2016 deaktivieren standardmäßig die Regel-/Formularaktion "Anwendung starten". Dadurch wird sichergestellt, dass auch wenn ein Angreifer das Konto verletzt, die Regel- und Formularaktionen blockiert werden. Sie können die neuesten Updates und Sicherheitspatches installieren, indem Sie die Schritte unter [Install Office updates ausführen.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Hier sind die Patchversionen für Ihre Outlook 2013- und 2016-Clients:

- **Outlook 2016**: 16.0.4534.1001 oder höher.

- **Outlook 2013**: 15.0.4937.1000 oder höher.

Weitere Informationen zu den einzelnen Sicherheitspatches finden Sie unter:

- [Outlook 2016 Sicherheitspatch](https://support.microsoft.com/help/3191883)

- [Outlook 2013 Security Patch](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Drittens: Überwachen Ihrer Outlook Clients

Beachten Sie, dass ein Angreifer auch bei installierten Patches und Updates die Konfiguration des lokalen Computers ändern kann, um das Verhalten "Anwendung starten" erneut zu aktivieren. Sie können die [erweiterte Gruppenrichtlinienverwaltung verwenden,](/microsoft-desktop-optimization-pack/agpm/) um lokale Computerrichtlinien auf Ihren Clients zu überwachen und zu erzwingen.

Anhand der Informationen in How to view the system registry by using [64-bit](https://support.microsoft.com/help/305097)versions of Windows können Sie sehen, ob "Anwendung starten" über eine Außerkraftsetzung in der Registrierung wieder aktiviert wurde. Überprüfen Sie die folgenden Unterschlüssel:

- **Outlook 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Suchen Sie nach dem Schlüssel EnableUnsafeClientMailRules. Wenn er dort ist und auf 1 festgelegt ist, wurde der Outlook-Sicherheitspatch außer Kraft gesetzt, und der Computer ist anfällig für den Formular-/Regelangriff. Wenn der Wert 0 ist, ist die Aktion "Anwendung starten" deaktiviert. Wenn die aktualisierte und gepatchte Version von Outlook installiert ist und dieser Registrierungsschlüssel nicht vorhanden ist, ist ein System nicht anfällig für diese Angriffe.

Kunden mit lokalen installationen Exchange sollten erwägen, ältere Versionen von Outlook zu blockieren, für die keine Patches verfügbar sind. Details zu diesem Prozess finden Sie im Artikel [Configure Outlook client blocking](/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Sichern von Microsoft 365 wie ein Profi für Internetsicherheit

Ihr Microsoft 365-Abonnement bietet eine Reihe von leistungsfähigen Funktionen für Sicherheit, die Sie zum Schutz Ihrer Daten und Ihrer Benutzer verwenden können. Verwenden Sie die [Microsoft 365-Sicherheits-Roadmap: Top-Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](security-roadmap.md) zum Implementieren von empfohlenen Microsoft-Best-Practices für den Schutz Ihres Microsoft 365-Mandanten.

- Aufgaben, die in den ersten 30 Tagen ausgeführt werden sollten. Diese haben sofortige Wirkung und wirken sich nur wenig auf Ihre Benutzer aus.

- Aufgaben, die innerhalb von 90 Tagen ausgeführt werden sollten. Diese erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

- Über 90 Tage hinaus. Diese Verbesserungen werden in den ersten 90 Tagen Ihrer Arbeit umgesetzt.

## <a name="see-also"></a>Siehe auch:

- [Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector bietet eine detaillierte Übersicht darüber, wie Outlook regeln.

- [MAPI über HTTP und Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) im Sensepost-Blog über Mailrule Pwnage erläutert ein Tool namens Ruler, mit dem Sie Postfächer über regeln Outlook können.

- [Outlook Formularen und Shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) im Sensepost-Blog zu Forms Threat Vector.

- [Ruler Codebase](https://github.com/sensepost/ruler)

- [Ruler Indicators of Compromise](https://github.com/sensepost/notruler/blob/master/iocs.md)