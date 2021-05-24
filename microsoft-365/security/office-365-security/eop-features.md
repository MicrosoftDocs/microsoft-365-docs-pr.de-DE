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
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: Die folgende Tabelle enthält eine Liste der Funktionen, die im gehosteten E-Mail-Filterdienst Exchange Online Protection (EOP) verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fa353b1e4e2560320b7e0fefae2dd302b35113b8
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624753"
---
# <a name="eop-features"></a>EOP-Funktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)

Die folgende Tabelle enthält eine Liste der Features Exchange Online Protection, die im E <3> <0>-E-Mail-Filterdienst (EOP) verfügbar sind.

> [!TIP]
> Die [Microsoft 365 business roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) ist eine gute Ressource, um Informationen zu bevorstehenden neuen Features zu finden. Einen umfassenderen Überblick über die Funktionen in den verschiedenen EOP-Abonnementplänen finden Sie unter [Exchange Online Protection-Dienstbeschreibung](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

<br>

****

|Feature|Beschreibung|
|---|---|
|**Antispamschutz**||
|Eingehende Spamerkennung|Weitere Informationen finden Sie unter [Antispamschutz in Microsoft 365](anti-spam-protection.md). <p> In Hybridumgebungen, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) in der lokalen Exchange konfigurieren, um das EOP-Spamfilter-Urteil zu übersetzen, damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann. Weitere Informationen finden Sie unter [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).|
|Ausgehende Spamerkennung|Ausgehender Antispamschutz ist immer aktiviert, wenn Sie den Dienst zum Senden ausgehender E-Mails verwenden. Weitere Informationen finden Sie unter [Ausgehender Spamschutz](outbound-spam-controls.md).|
|Schutz vor Rückscatter|Weitere Informationen finden Sie unter [Backscatter und EOP](backscatter-messages-and-eop.md).|
|Massen-E-Mail-Filterung|EOP verwendet den Schwellenwert für Massenbeschwerde (Bulk Complaint Threshold, BCL), um Massen-E-Mail-Nachrichten als Spam zu kennzeichnen. Weitere Informationen hierzu finden Sie in den folgenden Themen: <p> [Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [Massenbeschwerdestufe (Bulk Complaint Level, BCL) in EOP](bulk-complaint-level-values.md) <p> [Konfigurieren von Antispamrichtlinien](configure-your-spam-filter-policies.md)|
|Sperrlisten für schädliche URLs|EOP verwendet mehrere URL-Sperrlisten, die Unterstützung beim Erkennen bekannter schädlicher Links in Nachrichten bieten.|
|Antiphishingschutz|EOP umfasst 750.000 Domänen bekannter Spammer.|
|Antispoofingschutz|Weitere Informationen finden Sie unter [Anti-Spoofing Protection](anti-spoofing-protection.md).|
|**Spamverwaltung**||
|Konfigurieren sicherer und blockierter Absender|Weitere Informationen finden Sie unter [Create safe sender lists](create-safe-sender-lists-in-office-365.md) und Create blocked sender [lists](create-block-sender-lists-in-office-365.md).|
|Erstellen benutzerdefinierter Antispamrichtlinien|Für eine höhere Granularität können Sie benutzerdefinierte Antispamrichtlinien erstellen und diese auf bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation anwenden. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie, die Priorität (das heißt, die Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|Konfigurieren der Aktionen für spamgefilterte Nachrichten|Beispielsweise können Sie Nachrichten löschen, auf die Inhaltsfilter angewendet wurden, oder sie in den Junk-E-Mail-Ordner oder das Quarantäneverzeichnis verschieben. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|Internationale Spamfilterung|Sie können die Antispamfilterung so konfigurieren, dass Nachrichten gefiltert werden, die in bestimmten Sprachen geschrieben oder aus bestimmten Ländern oder Regionen gesendet werden. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|Verwalten von Spam Outlook oder Outlook im Web (früher bekannt als Outlook Web App)|Administratoren und Endbenutzer können Listen sicherer Absender und Listen blockierter Absender erstellen. Weitere Informationen finden Sie unter [Informationen zu Junk-E-Mail-Einstellungen in Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook). <p> Wenn Sie EOP zum Schutz von lokalen Postfächern verwenden, sollten Sie unbedingt die Verzeichnissynchronisierung verwenden, um sicherzustellen, dass diese Einstellungen mit dem Dienst synchronisiert werden. Weitere Informationen zum Einrichten der Verzeichnissynchronisierung finden Sie unter "Verwenden der Verzeichnissynchronisierung zum Verwalten von E-Mail-Benutzern" unter Verwalten von E-Mail-Benutzern [in eigenständigem EOP](/exchange/standalone-eop/manage-mail-users-in-eop).|
|Melden Sie falsch positive und falsch negative Ergebnisse an Microsoft.|Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).|
|Spamquarantänebenachrichtigungen für Endbenutzer|Weitere Informationen finden Sie unter [Spambenachrichtigungen für](use-spam-notifications-to-release-and-report-quarantined-messages.md) Endbenutzer und [Konfigurieren von Spambenachrichtigungen für Endbenutzer.](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)|
|Anzeigen, Suchen und Verwalten von Nachrichten im Quarantäneportal.|Weitere Informationen finden Sie unter [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md) oder [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).|
|Anzeigen von Nachrichtenkopfzeilen in Spamquarantäne|Nachdem Sie den Nachrichtenkopf in der Quarantäne angezeigt haben, können Sie den Kopfzeilentext auch kopieren und in die [Nachrichtenkopfanalyse](https://mha.azurewebsites.net/) einfügen, um herauszufinden, was mit der Nachricht passiert ist.|
|**Schutz vor Schadsoftware**||
|Schadsoftwareschutz durch Einsatz mehrerer Module|Durch mehrere Antischadsoftwaremodule sind unsere Kunden jederzeit automatisch geschützt.|
|Möglichkeit zum Deaktivieren der Schadsoftwarefilterung|Sie können die Schadsoftwarefilterung nicht deaktivieren. Wir sind der Ansicht, dass ein konsistentes und strenges Sicherheitsniveau für alle Kunden ein wichtiger Bestandteil der notwendigen tiefgreifenden Verteidigung zum Schutz Ihrer E-Mail-Umgebung ist. Infolgedessen ist die Schadsoftwarefilterung für alle Kunden automatisch aktiviert.|
|Prüfung des Nachrichtentexts und der Anlagen auf Schadsoftware|Der Dienst untersucht die aktive Nutzlast im Nachrichtentext und in allen Anlagen auf Schadsoftware.|
|Standardmäßige oder benutzerdefinierte Warnbenachrichtigungen bei Schadsoftware|Sie können eine Benachrichtigung an Absender oder Administratoren senden. Weitere Informationen finden Sie unter [Configure anti-malware policies](configure-anti-malware-policies.md).|
|Empfängerbenachrichtigungen|Isolieren Sie die Nachricht automatisch, oder isolieren Sie die Nachricht, und senden Sie sie auch mit allen Anlagen, die durch eine einzelne Textdatei ersetzt werden, die Standard- oder benutzerdefinierten Text enthält. Weitere Informationen finden Sie unter [Configure anti-malware policies](configure-anti-malware-policies.md).|
|Allgemeine Anlagenfilterung|Sie können eine Liste von Dateitypen aktivieren und anpassen, die immer als Schadsoftware gelten. Weitere Informationen finden Sie unter [Schutz vor Schadsoftware in EOP](anti-malware-protection.md).|
|Antispywareschutz|Antischadsoftwareschutz umfasst Virenschutz und Antispywareschutz.|
|Erstellen benutzerdefinierter Schadsoftwarefilterrichtlinien|Für eine höhere Granularität können Sie benutzerdefinierte Schadsoftware-Filterrichtlinien erstellen und diese bestimmten Benutzern, Gruppen oder Domänen in Ihrer Organisation zuweisen. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie, die Priorität (das heißt, die Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern. Weitere Informationen finden Sie unter [Configure anti-malware policies](configure-anti-malware-policies.md).|
|**E-Mail-Weiterleitung und Connectors**||
|Bedingtes E-Mail-Routing|Weitere Informationen finden Sie unter [Szenario: Bedingtes E-Mail-Routing in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|Opportunistisches oder erzwungenes TLS|Opportunistisches oder erzwungenes TLS ist mit Connectors verfügbar. Opportunistic TLS versucht eine TLS-Verbindung, verwendet jedoch eine SMTP-Verbindung, wenn die TLS-Verbindung nicht erfolgreich ist. Force TLS erzwingt TLS-Verbindungen, was bedeutet, dass die Nachricht abgelehnt wird, wenn die TLS-Verbindung nicht erfolgreich ist. Weitere Informationen zu TLS, Sicherheit und Connectors finden Sie unter [Set up connectors for secure mail flow with a partner organization](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).|
|Regionales Routing (Einschränkung des E-Mail-Flusses auf eine bestimmte Region)|Weitere Informationen finden Sie im Abschnitt "EOP-Datencenter" unter [Exchange Online Protection im Überblick](exchange-online-protection-overview.md).|
|SMTP-Konnektivitätsprüfung|Weitere Informationen zur Verwendung dieses Tools zum Testen des Nachrichtenflusses finden Sie unter [Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).|
|Untergeordnete Domänen abgleichen|Weitere Informationen zum Aktivieren des Nachrichtenflusses zu und von Unterdomänen Ihrer akzeptierten Domänen finden Sie unter [Nachrichtenfluss in EOP](mail-flow-in-eop.md).|
|**Nachrichtenflussregeln**||
|Richtlinienbasierte Filterung und Aktionen|Benutzerdefinierte Richtlinien basieren auf Exchange Nachrichtenflussregeln (auch als Transportregeln bekannt). Sie können nach Domäne, Schlüsselwort, Dateiname, Dateityp, Betreffzeile, Nachrichtentext, Absender, Empfänger, Kopfzeile und IP-Adresse filtern. Weitere Informationen finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Nach Textmustern filtern|Nachrichtenflussregeln können ein Array oder reguläre Ausdrücke verwenden, um Text zu entsprechen. Sie können auch eine Zeichenfolge oder ein Array von Zeichenfolgen verwenden, um Nachrichteneigenschaften wie beispielsweise Adresse, Betreff, Nachrichtentext oder Anlagennamen abzugleichen. Weitere Informationen finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)|
|Benutzerdefinierte Wörterbücher|Nachrichtenflussregeln können lange Listen mit Text und Schlüsselwörtern enthalten, die die gleiche Funktionalität wie ein benutzerdefiniertes Wörterbuch bieten.|
|Richtlinienregeln pro Domäne|Der Bereich einer Nachrichtenflussregel kann angepasst werden, um Absender- oder Empfängerdomänennamen, IP-Adressbereiche, Adressschlüsselwörter oder -muster, Gruppenmitgliedschaften und andere Bedingungen zu erfüllen.|
|Anlagenüberprüfung|Es können Regeln für die Überprüfung des Dateinamens, der Erweiterung und des Inhalts der Anlage erstellt werden.|
|Richtlinienregelbenachrichtigungen an den Absender senden|Sie können Nachrichten ablehnen und einen Unzustellbarkeitsbericht (auch als Unzustellbarkeitsbericht  oder Unzustellbarkeitsnachricht bezeichnet) an den Absender über die Nachricht mit der Erklärung ablehnen oder die Nachricht mit der erweiterten Statuscodeaktion ablehnen senden.  Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Umleiten oder Kopieren von Nachrichten|Nachrichtenflussregeln können umleiten, Empfänger von Cc oder Bcc hinzufügen, einfach Empfänger und andere Optionen hinzufügen. Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Anpassen der Regelpriorität über mehrere Regeln hinweg|Die Reihenfolge, in der Regeln verarbeitet werden, können Sie im Exchange Admin Center ändern.|
|Filtern von Nachrichten und anschließendes Ändern des Routings oder der Attribute einer Nachricht|Sie können Nachrichten basierend auf einer Vielzahl von Bedingungen filtern und anschließend jeder Nachricht verschiedene Aktionen zuweisen. Weitere Informationen finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Ändern Sie die Spamsicherheitsstufe (Spam Confidence Level, SCL) einer Nachricht nach Regel.|Sie können eine Nachricht während der Übertragung untersuchen und der Nachricht basierend auf den gewählten Kriterien eine SCL-Bewertung zuweisen. Weitere Informationen finden Sie unter Verwenden von Nachrichtenflussregeln zum Festlegen der Spamsicherheitsstufe [(Spam Confidence Level, SCL) in Nachrichten](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).|
|Überprüfen von Nachrichtenanlagen|Sie können die Inhalte einer Anlage oder die Merkmale einer angehängten Daten untersuchen und ausgehend von den gefundenen Informationen eine durchzuführende Maßnahmen definieren. Weitere Informationen finden Sie unter [Using mail flow rules to inspect message attachments in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).|
|**Verwaltung**||
|Webbasierte Verwaltung|Die meisten Features werden im [Security & Compliance Center verwaltet.](grant-access-to-the-security-and-compliance-center.md) <p> Andere Features erfordern eine Verwaltung im Exchange Admin Center (EAC). Weitere Informationen finden Sie [unter Exchange Admin Center in Exchange Online](/exchange/exchange-admin-center) oder Exchange Admin Center im eigenständigen [EOP](/exchange/standalone-eop/exchange-admin-center-eop).|
|Verzeichnissynchronisierung|Die Verzeichnissynchronisierung ist über das Azure Active Directory-Synchronisierungstool verfügbar. Weitere Informationen finden Sie im Abschnitt "Verwenden der Verzeichnissynchronisierung zum Verwalten von E-Mail-Benutzern" unter Verwalten von [E-Mail-Benutzern in eigenständigem EOP](/exchange/standalone-eop/manage-mail-users-in-eop).|
|Verzeichnisbasierte Edge-Blockierung (DBEB)|DBEB ermöglicht es Ihnen, Nachrichten für ungültige Empfänger im Dienstnetzwerkumkreis abzulehnen. MIT DBEB können Administratoren E-Mail-aktivierte Empfänger Microsoft 365 und alle Nachrichten blockieren, die an E-Mail-Adressen gesendet werden, die nicht in Microsoft 365. Weitere Informationen zum Konfigurieren von DBEB finden Sie unter [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).|
|PowerShell|Die vollständige EOP-Funktionalität ist in der eigenständigen EOP PowerShell verfügbar. Weitere Informationen finden Sie unter [Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell).|
|**Berichterstellung und Protokollierung**||
|Nachrichtenablaufverfolgung|Administratoren können E-Mail-Nachrichten beim Passieren des Diensts verfolgen. Sie können bestimmen, ob eine gezielte E-Mail-Nachricht vom Dienst empfangen, abgelehnt, zurückgestellt oder zugestellt wurde. So können Sie in effizienter Weise Fragen der Benutzer beantworten, Probleme mit dem Nachrichtenfluss behandeln und Richtlinienänderungen überprüfen und müssen seltener den technischen Support um Unterstützung bitten. Weitere Informationen finden Sie unter [Nachrichtenablaufverfolgung im Security & Compliance Center](message-trace-scc.md).|
|Webbasierte Berichte|Die E-Mail-Schutzberichte im Security & Compliance Center stellen Messagingdaten zur Verfügung. Sie können beispielsweise überwachen, wie viel Spam und Schadsoftware erkannt wird oder wie oft Ihre Nachrichtenflussregeln übereinstimmen. Mithilfe dieser interaktiven Berichte erhalten Sie schnell einen visuellen Überblick über die zusammengefassten Daten und können Details zu einzelnen Nachrichten der letzten 90 Tage überprüfen. Weitere Informationen finden Sie unter [Verwenden von E-Mail-Schutzberichten zum Anzeigen von Daten zu Schadsoftware, Spam und Regelerkennungen.](/exchange/monitoring/use-mail-protection-reports)|
|Überwachungsprotokollierung|Weitere Informationen finden Sie unter [Überwachung von Berichten in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).|
|**Vereinbarungen zum Servicelevel (SLA) und Support**||
|SLA zur Effektivität der Antispamfunktion|\> 99%|
|SLA zum Anteil fälschlicherweise gefilterter Nachrichten|\< 1:250,000|
|SLA zu Virenerkennung und Virenschutz|100 % der bekannten Viren|
|SLA zu monatlicher Betriebszeit|99,999 %|
|Technischer Telefon- und Onlinesupport rund um die Uhr|Weitere Informationen zu Hilfe und Support für EOP finden Sie unter [Hilfe und Support für EOP](help-and-support-for-eop.md).|
|**Sonstige Funktionen**||
|Georedundantes globales Servernetzwerk|EOP wird in einem weltweiten Rechenzentrennetzwerk ausgeführt, das für eine optimale Verfügbarkeit entworfen wurde. Weitere Informationen finden Sie im Abschnitt "EOP-Rechenzentrum" unter [Exchange Online Protection im Überblick](exchange-online-protection-overview.md).  |
|Nachrichtenwarteschlangen, wenn lokaler Server keine E-Mails akzeptieren kann|Nachrichten, die sich in der Verschiebung befinden, verbleiben für einen Tag in unseren Warteschlangen. Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird. Das Wiederholungsintervall für die Übertragung von Nachrichten beträgt im Durchschnitt 5 Minuten. Weitere Informationen finden Sie unter [Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten](eop-queued-deferred-and-bounced-messages-faq.yml).|
|Office 365-Nachrichtenverschlüsselung als Add-On-Dienst erhältlich|Weitere Informationen finden Sie unter [Verschlüsselung in Office 365](../../compliance/encryption.md).|
|
