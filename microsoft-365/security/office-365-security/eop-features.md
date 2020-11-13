---
title: EOP-Funktionen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: Die folgende Tabelle enthält eine Liste der Funktionen, die im gehosteten E-Mail-Filterdienst Exchange Online Protection (EOP) verfügbar sind.
ms.openlocfilehash: dcbb7d2e31e230633d0401eee0ef0874eb6af615
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021037"
---
# <a name="eop-features"></a>EOP-Funktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Die folgende Tabelle enthält eine Liste der Funktionen, die im gehosteten E-Mail-Filterdienst Exchange Online Protection (EOP) verfügbar sind.

> [!TIP]
> Die [Microsoft 365 for Business-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) ist eine gute Ressource für die Suche nach Informationen über kommende neue Features. Einen umfassenderen Überblick über die Funktionen in den verschiedenen EOP-Abonnementplänen finden Sie unter [Exchange Online Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

****

|Feature|Beschreibung|
|---|---|
|**Antispamschutz**||
|Eingehende Spamerkennung|Weitere Informationen finden Sie unter [Anti-Spam Protection in Microsoft 365](anti-spam-protection.md). <p> In Umgebungen mit eigenständigem EOP, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie im lokalen Exchange Nachrichtenflussregeln zur Übersetzung der EOP-Spamfilterbewertung konfigurieren (auch als Transportregeln bezeichnet), damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann. Ausführliche Informationen finden Sie unter [Konfigurieren von eigenständigen EoP zur Zustellung von Spam an den Junk-e-Mail-Ordner in Hybrid Umgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) .|
|Ausgehende Spamerkennung|Der ausgehende Antispam-Schutz ist immer aktiviert, wenn Sie den Dienst zum Senden ausgehender e-Mails verwenden. Weitere Informationen finden Sie unter [Outbound Spam Protection](outbound-spam-controls.md).|
|Rück Streu Schutz|Weitere Informationen finden Sie unter [Backscatter und EOP](backscatter-messages-and-eop.md).|
|Massen-E-Mail-Filterung|EoP verwendet den Massen Reklamations Schwellenwert (BCL), um Massen-e-Mails als Spam zu markieren. Weitere Informationen hierzu finden Sie in den folgenden Themen: <p> [Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [Massen Reklamations Ebene (BCL) in EoP](bulk-complaint-level-values.md) <p> [Konfigurieren von Antispamrichtlinien](configure-your-spam-filter-policies.md)|
|Sperrlisten für schädliche URLs|EOP verwendet mehrere URL-Sperrlisten, die Unterstützung beim Erkennen bekannter schädlicher Links in Nachrichten bieten.|
|Antiphishingschutz|EOP umfasst 750.000 Domänen bekannter Spammer.|
|Antispoofingschutz|Weitere Informationen finden Sie unter [Anti-Spoofing-Schutz](anti-spoofing-protection.md).|
|**Spamverwaltung**||
|Konfigurieren sicherer Absender und blockierter Absender|Weitere Informationen finden Sie unter [Erstellen sicherer Absenderlisten](create-safe-sender-lists-in-office-365.md) und [Erstellen blockierter Absenderlisten](create-block-sender-lists-in-office-365.md).|
|Erstellen benutzerdefinierter Anti-Spam-Richtlinien|Um eine höhere Granularität zu erzielen, können Sie benutzerdefinierte Anti-Spam-Richtlinien erstellen und diese auf bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation anwenden. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie, die Priorität (das heißt, die Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|Konfigurieren der Aktionen für Spam gefilterte Nachrichten|Beispielsweise können Sie Nachrichten löschen, auf die Inhaltsfilter angewendet wurden, oder sie in den Junk-E-Mail-Ordner oder das Quarantäneverzeichnis verschieben. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|Internationale Spamfilterung|Sie können die Antispam-Filterung so konfigurieren, dass Nachrichten gefiltert werden, die in bestimmten Sprachen verfasst oder aus bestimmten Ländern oder Regionen gesendet werden. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|Verwalten von Spam über Outlook oder Outlook im Internet (früher bekannt als Outlook Web App)|Administratoren und Endbenutzer können Listen sicherer Absender und Listen blockierter Absender erstellen. Weitere Informationen finden Sie unter [Informationen zu Junk-e-Mail-Einstellungen in Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook). <p> Wenn Sie EoP zum Schutz von lokalen Postfächern verwenden, müssen Sie unbedingt die Verzeichnissynchronisierung verwenden, um sicherzustellen, dass diese Einstellungen mit dem Dienst synchronisiert werden. Weitere Informationen zum Einrichten der Verzeichnissynchronisierung finden Sie unter "Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung" in [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).|
|Falsch positive und falsch negative Meldungen an Microsoft melden.|Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).|
|Spamquarantänebenachrichtigungen für Endbenutzer|Weitere Informationen finden Sie unter [Endbenutzer-Spambenachrichtigungen](use-spam-notifications-to-release-and-report-quarantined-messages.md) und [Konfigurieren von Spambenachrichtigungen für Endbenutzer](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications).|
|Anzeigen, suchen und Verwalten von Nachrichten im Quarantäne Portal.|Weitere Informationen finden Sie unter [Manage Quarantined Messages and files as a admin in EoP](manage-quarantined-messages-and-files.md) oder [Find and Release Quarantined Messages as a User](find-and-release-quarantined-messages-as-a-user.md).|
|Anzeigen Spam isolierter Nachrichtenkopfzeilen|Nachdem Sie die Nachrichtenkopfzeile in der Quarantäne angezeigt haben, können Sie auch den Kopfzeilentext in der [Nachrichtenkopf Analyse](https://mha.azurewebsites.net/) kopieren und einfügen, um herauszufinden, was mit der Nachricht geschah.|
|**Schutz vor Schadsoftware**||
|Schadsoftwareschutz durch Einsatz mehrerer Module|Durch mehrere Antischadsoftwaremodule sind unsere Kunden jederzeit automatisch geschützt.|
|Möglichkeit zum Deaktivieren der Malware Filterung|Sie können die Malware Filterung nicht deaktivieren. Wir sind der Ansicht, dass ein konsistentes und strenges Sicherheitsniveau für alle Kunden ein wichtiger Bestandteil der notwendigen tiefgreifenden Verteidigung zum Schutz Ihrer E-Mail-Umgebung ist. Infolgedessen ist die Schadsoftwarefilterung für alle Kunden automatisch aktiviert.|
|Prüfung des Nachrichtentexts und der Anlagen auf Schadsoftware|Der Dienst untersucht die aktive Nutzlast im Nachrichtentext und in allen Anlagen auf Schadsoftware.|
|Standardmäßige oder benutzerdefinierte Warnbenachrichtigungen bei Schadsoftware|Sie können eine Benachrichtigung an Absender oder Administratoren senden. Weitere Informationen finden Sie unter [configure Anti-Malware Policies](configure-anti-malware-policies.md).|
|Empfänger Benachrichtigungen|Sie können die Nachricht automatisch isolieren oder die Nachricht isolieren und mit allen Anlagen durch eine einzelne Textdatei mit Standard-oder benutzerdefiniertem Text ersetzen. Weitere Informationen finden Sie unter [configure Anti-Malware Policies](configure-anti-malware-policies.md).|
|Allgemeine Anlagenfilterung|Sie können eine Liste von Dateitypen aktivieren und anpassen, die immer als Schadsoftware gelten. Weitere Informationen finden Sie unter [Schutz vor Schadsoftware in EoP](anti-malware-protection.md).|
|Antispywareschutz|Antischadsoftwareschutz umfasst Virenschutz und Antispywareschutz.|
|Erstellen benutzerdefinierter Filterrichtlinien für Schadsoftware|Für eine höhere Granularität können Sie benutzerdefinierte Schadsoftware-Filterrichtlinien erstellen und diese bestimmten Benutzern, Gruppen oder Domänen in Ihrer Organisation zuweisen. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie, die Priorität (das heißt, die Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern. Weitere Informationen finden Sie unter [configure Anti-Malware Policies](configure-anti-malware-policies.md).|
|**E-Mail-Weiterleitung und Connectors**||
|Bedingtes E-Mail-Routing|Weitere Informationen finden Sie unter [Szenario: Bedingtes E-Mail-Routing in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|Opportunistisches oder erzwungenes TLS|Opportunistisches oder erzwungenes TLS ist mit Connectors verfügbar. Opportunistisches TLS versucht eine TLS-Verbindung, verwendet jedoch eine SMTP-Verbindung, wenn die TLS-Verbindung nicht erfolgreich ist. Force TLS erzwingt TLS-Verbindungen, was bedeutet, dass die Nachricht zurückgewiesen wird, wenn die TLS-Verbindung nicht erfolgreich ist. Weitere Informationen zu TLS, Sicherheit und Connectors finden Sie unter [Set up connectors for secure mail flow with a partner organization](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).|
|Regionales Routing (Einschränkung des E-Mail-Flusses auf eine bestimmte Region)|Weitere Informationen finden Sie im Abschnitt "EOP-Datencenter" unter [Exchange Online Protection im Überblick](exchange-online-protection-overview.md).|
|SMTP-Konnektivitätsprüfung|Weitere Informationen zur Verwendung dieses Tools zum Testen Ihres e-Mail-Flusses finden Sie unter [Testen der Nachrichtenübermittlung durch validieren Ihrer Microsoft 365-Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).|
|Untergeordnete Domänen abgleichen|Weitere Informationen zum Aktivieren des Nachrichtenflusses zu und von Unterdomänen der akzeptierten Domänen finden Sie unter [e-Mail-Fluss in EoP](mail-flow-in-eop.md).|
|**Nachrichtenflussregeln**||
|Richtlinienbasierte Filterung und Aktionen|Benutzerdefinierte Richtlinien basieren auf Exchange-Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet). Sie können nach Domäne, Schlüsselwort, Dateiname, Dateityp, Betreffzeile, Nachrichtentext, Absender, Empfänger, Kopfzeile und IP-Adresse filtern. Weitere Informationen finden Sie unter [Mail Flow Rules (Transport Rules) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Nach Textmustern filtern|Nachrichtenfluss Regeln können ein Array oder reguläre Ausdrücke verwenden, um Text zuzuordnen. Sie können auch eine Zeichenfolge oder ein Array von Zeichenfolgen verwenden, um Nachrichteneigenschaften wie beispielsweise Adresse, Betreff, Nachrichtentext oder Anlagennamen abzugleichen. Weitere Informationen finden Sie unter [Mail Flow Rules (Transport Rules) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) .|
|Benutzerdefinierte Wörterbücher|Nachrichtenfluss Regeln können lange Listen von Text und Stichwörtern enthalten, die die gleiche Funktionalität wie ein Benutzerwörterbuch bieten.|
|Richtlinienregeln pro Domäne|Der Bereich einer e-Mail-Fluss Regel kann so angepasst werden, dass Absender-oder Empfängerdomänen Namen, IP-Adressbereiche, Adress Schlüsselwörter oder Muster, Gruppenmitgliedschaften und andere Bedingungen übereinstimmen.|
|Anlagenüberprüfung|Es können Regeln für die Überprüfung des Dateinamens, der Erweiterung und des Inhalts der Anlage erstellt werden.|
|Richtlinienregelbenachrichtigungen an den Absender senden|Sie können Nachrichten ablehnen und einen Unzustellbarkeitsbericht (auch als NDR-oder Bounce-Nachricht bezeichnet) an den Absender senden, indem Sie die **Nachricht mit der Erklärung ablehnen** oder **die Nachricht mit der Aktion erweiterter Statuscode ablehnen** . Weitere Informationen finden Sie unter [Aktionen für Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Nachrichten umleiten oder kopieren|Nachrichtenfluss Regeln können umleiten, Empfänger durch CC oder Bcc hinzufügen, Empfänger einfach hinzufügen und andere Optionen. Weitere Informationen finden Sie unter [Aktionen für Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Anpassen der Regelpriorität in mehreren Regeln|Die Reihenfolge, in der Regeln verarbeitet werden, können Sie im Exchange Admin Center ändern.|
|Filtern von Nachrichten und Ändern des Routings oder der Attribute einer Nachricht|Sie können Nachrichten basierend auf einer Vielzahl von Bedingungen filtern und anschließend jeder Nachricht verschiedene Aktionen zuweisen. Weitere Informationen finden Sie unter [Mail Flow Rules (Transport Rules) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Ändern Sie die SCL-Bewertung (Spam Confidence Level) einer Nachricht nach Regel.|Sie können eine Nachricht während der Übertragung untersuchen und der Nachricht basierend auf den gewählten Kriterien eine SCL-Bewertung zuweisen. Weitere Informationen finden Sie unter [Verwenden von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).|
|Überprüfen von Nachrichtenanlagen|Sie können die Inhalte einer Anlage oder die Merkmale einer angehängten Daten untersuchen und ausgehend von den gefundenen Informationen eine durchzuführende Maßnahmen definieren. Weitere Informationen finden Sie unter [using Mail Flow Rules to Inspect Message Attachments in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).|
|**Verwaltung**||
|Webbasierte Verwaltung|Administratoren können den Dienst in der Exchange-Verwaltungskonsole (EAC) verwalten, die in 60 Sprachen unterstützt wird. Weitere Informationen finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).|
|Verzeichnissynchronisierung|Die Verzeichnissynchronisierung ist über das Azure Active Directory-Synchronisierungstool verfügbar. Weitere Informationen finden Sie unter "Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung" unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).  |
|Verzeichnisbasierte Edge-Blockierung (DBEB)|DBEB ermöglicht es Ihnen, Nachrichten für ungültige Empfänger im Dienstnetzwerkumkreis abzulehnen. Mit Blockierung können Administratoren e-Mail-aktivierte Empfänger zu Microsoft 365 hinzufügen und alle an e-Mail-Adressen gesendeten Nachrichten blockieren, die in Microsoft 365 nicht vorhanden sind. Weitere Informationen zum Konfigurieren von Blockierung finden Sie unter [Verwenden der verzeichnisbasierten Edge-Blockierung zum ablehnen von Nachrichten, die an ungültige Empfänger gesendet](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)werden.|
|PowerShell|Die vollständige EoP-Funktionalität ist in eigenständigen EoP PowerShell verfügbar. Weitere Informationen finden Sie unter [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).|
|**Berichterstellung und Protokollierung**||
|Nachrichtenablaufverfolgung|Administratoren können e-Mail-Nachrichten verfolgen, während Sie den Dienst durchlaufen. Sie können bestimmen, ob eine Ziel-e-Mail-Nachricht empfangen, abgelehnt, zurückgestellt oder vom Dienst gesendet wurde. So können Sie in effizienter Weise Fragen der Benutzer beantworten, Probleme mit dem Nachrichtenfluss behandeln und Richtlinienänderungen überprüfen und müssen seltener den technischen Support um Unterstützung bitten. Weitere Informationen finden Sie unter [Nachrichtenablaufverfolgung im Security & Compliance Center](message-trace-scc.md).|
|Webbasierte Berichte|Die e-Mail-Schutz Berichte im Security & Compliance Center stellen Messagingdaten bereit. Beispielsweise können Sie überwachen, wie viel Spam und Schadsoftware erkannt wird oder wie oft ihre Nachrichtenfluss Regeln abgeglichen werden. Mithilfe dieser interaktiven Berichte erhalten Sie schnell einen visuellen Überblick über die zusammengefassten Daten und können Details zu einzelnen Nachrichten der letzten 90 Tage überprüfen. Weitere Informationen finden Sie unter [Verwenden von e-Mail-Schutz Berichten zum Anzeigen von Daten über Schadsoftware, Spam und Regel Erkennungen](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).|
|Überwachungsprotokollierung|Der Administrator-Rollengruppenbericht und das Administrator-Überwachungsprotokoll stehen EOP-Administratoren zur Verfügung. Weitere Informationen finden Sie unter [Überwachungsberichte in EOP](auditing-reports-in-eop.md).  |
|**Vereinbarungen zum Servicelevel (SLA) und Support**||
|SLA zur Effektivität der Antispamfunktion|\> 99%|
|SLA zum Anteil fälschlicherweise gefilterter Nachrichten|\< 1:250000|
|SLA zu Virenerkennung und Virenschutz|100 % der bekannten Viren|
|SLA zu monatlicher Betriebszeit|99,999 %|
|Technischer Telefon- und Onlinesupport rund um die Uhr|Weitere Informationen zu Hilfe und Support für EOP finden Sie unter [Hilfe und Support für EOP](help-and-support-for-eop.md).|
|**Sonstige Funktionen**||
|Georedundantes globales Servernetzwerk|EOP wird in einem weltweiten Rechenzentrennetzwerk ausgeführt, das für eine optimale Verfügbarkeit entworfen wurde. Weitere Informationen finden Sie im Abschnitt "EOP-Rechenzentrum" unter [Exchange Online Protection im Überblick](exchange-online-protection-overview.md).  |
|Nachrichtenwarteschlangen, wenn lokaler Server keine E-Mails akzeptieren kann|Nachrichten in Stundung verbleiben einen Tag lang in unseren Warteschlangen. Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird. Das Wiederholungsintervall für die Übertragung von Nachrichten beträgt im Durchschnitt 5 Minuten. Weitere Informationen finden Sie unter [Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten](eop-queued-deferred-and-bounced-messages-faq.md).|
|Office 365-Nachrichtenverschlüsselung als Add-On-Dienst erhältlich|Weitere Informationen finden Sie unter [Verschlüsselung in Office 365](../../compliance/encryption.md).|
|
