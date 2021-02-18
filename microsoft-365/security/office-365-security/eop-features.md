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
ms.openlocfilehash: 7dbdf30df0659565d775bfba2cf968ac56f6a4ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286849"
---
# <a name="eop-features"></a>EOP-Funktionen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection als eigenständige Lösung](exchange-online-protection-overview.md)

Die folgende Tabelle enthält eine Liste der Funktionen, die im gehosteten E-Mail-Filterdienst Exchange Online Protection (EOP) verfügbar sind.

> [!TIP]
> Die [Microsoft 365 Business Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) ist eine gute Ressource, um Informationen zu bevorstehenden neuen Features zu erhalten. Einen umfassenderen Überblick über die Funktionen in den verschiedenen EOP-Abonnementplänen finden Sie unter [Exchange Online Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

****

|Feature|Beschreibung|
|---|---|
|**Antispamschutz**||
|Eingehende Spamerkennung|Weitere Informationen finden Sie unter [Antispamschutz in Microsoft 365.](anti-spam-protection.md) <p> In Umgebungen mit eigenständigem EOP, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie im lokalen Exchange Nachrichtenflussregeln zur Übersetzung der EOP-Spamfilterbewertung konfigurieren (auch als Transportregeln bezeichnet), damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann. Weitere Informationen finden Sie unter ["Konfigurieren von eigenständigem EOP zum Senden von Spam an den Junk-E-Mail-Ordner in Hybridumgebungen".](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|Ausgehende Spamerkennung|Der Antispamschutz für ausgehende Nachrichten ist immer aktiviert, wenn Sie den Dienst zum Senden ausgehender E-Mails verwenden. Weitere Informationen finden Sie unter ["Ausgehender Spamschutz".](outbound-spam-controls.md)|
|Rückscatterschutz|Weitere Informationen finden Sie unter [Backscatter und EOP](backscatter-messages-and-eop.md).|
|Massen-E-Mail-Filterung|EOP verwendet den Schwellenwert für Massenbeanstandung (Bulk Complaint Threshold, BCL), um Massen-E-Mail-Nachrichten als Spam zu kennzeichnen. Weitere Informationen hierzu finden Sie in den folgenden Themen: <p> [Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [BCL (Bulk Complaint Level) in EOP](bulk-complaint-level-values.md) <p> [Konfigurieren von Antispamrichtlinien](configure-your-spam-filter-policies.md)|
|Sperrlisten für schädliche URLs|EOP verwendet mehrere URL-Sperrlisten, die Unterstützung beim Erkennen bekannter schädlicher Links in Nachrichten bieten.|
|Antiphishingschutz|EOP umfasst 750.000 Domänen bekannter Spammer.|
|Antispoofingschutz|Weitere Informationen finden Sie unter [Antis spoofing protection](anti-spoofing-protection.md).|
|**Spamverwaltung**||
|Konfigurieren sicherer und blockierter Absender|Weitere Informationen finden Sie unter ["Listen sicherer Absender erstellen"](create-safe-sender-lists-in-office-365.md) und ["Listen blockierter Absender erstellen".](create-block-sender-lists-in-office-365.md)|
|Erstellen benutzerdefinierter Antispamrichtlinien|Für eine höhere Granularität können Sie benutzerdefinierte Antispamrichtlinien erstellen und auf bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation anwenden. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie, die Priorität (das heißt, die Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|Konfigurieren der Aktionen für spamgefilterte Nachrichten|Beispielsweise können Sie Nachrichten löschen, auf die Inhaltsfilter angewendet wurden, oder sie in den Junk-E-Mail-Ordner oder das Quarantäneverzeichnis verschieben. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|Internationale Spamfilterung|Sie können die Antispamfilterung so konfigurieren, dass Nachrichten gefiltert werden, die in bestimmten Sprachen geschrieben oder aus bestimmten Ländern oder Regionen gesendet wurden. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).|
|Verwalten von Spam über Outlook oder Outlook im Web (früher als Outlook Web App bekannt)|Administratoren und Endbenutzer können Listen sicherer Absender und Listen blockierter Absender erstellen. Weitere Informationen finden Sie unter ["Informationen zu Junk-E-Mail-Einstellungen in Outlook".](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook) <p> Wenn Sie EOP zum Schutz von lokalen Postfächern verwenden, müssen Sie die Verzeichnissynchronisierung verwenden, um sicherzustellen, dass diese Einstellungen mit dem Dienst synchronisiert werden. Weitere Informationen zum Einrichten der Verzeichnissynchronisierung finden Sie unter "Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung" in [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).|
|Melden Sie falsch positive ergebnisse und falsch negative Ergebnisse an Microsoft.|Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).|
|Spamquarantänebenachrichtigungen für Endbenutzer|Weitere Informationen finden Sie unter [Spambenachrichtigungen für](use-spam-notifications-to-release-and-report-quarantined-messages.md) Endbenutzer und [Konfigurieren von Spambenachrichtigungen für Endbenutzer.](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)|
|Anzeigen, Suchen und Verwalten von Nachrichten im Quarantäneportal.|Weitere Informationen finden Sie unter Verwalten von isolierten Nachrichten und Dateien als Administrator [in EOP](manage-quarantined-messages-and-files.md) oder Suchen und Veröffentlichen von Isolierten [Nachrichten als Benutzer.](find-and-release-quarantined-messages-as-a-user.md)|
|Anzeigen von Nachrichtenkopfzeilen in Spamquarantäne|Nachdem Sie die Nachrichtenkopfzeile in quarantäne angezeigt haben, können [](https://mha.azurewebsites.net/) Sie den Kopfzeilentext auch kopieren und in die Nachrichtenkopfanalyse einfügen, um herauszufinden, was mit der Nachricht passiert ist.|
|**Schutz vor Schadsoftware**||
|Schadsoftwareschutz durch Einsatz mehrerer Module|Durch mehrere Antischadsoftwaremodule sind unsere Kunden jederzeit automatisch geschützt.|
|Möglichkeit zum Deaktivieren der Schadsoftwarefilterung|Die Schadsoftwarefilterung kann nicht deaktiviert werden. Wir sind der Ansicht, dass ein konsistentes und strenges Sicherheitsniveau für alle Kunden ein wichtiger Bestandteil der notwendigen tiefgreifenden Verteidigung zum Schutz Ihrer E-Mail-Umgebung ist. Infolgedessen ist die Schadsoftwarefilterung für alle Kunden automatisch aktiviert.|
|Prüfung des Nachrichtentexts und der Anlagen auf Schadsoftware|Der Dienst untersucht die aktive Nutzlast im Nachrichtentext und in allen Anlagen auf Schadsoftware.|
|Standardmäßige oder benutzerdefinierte Warnbenachrichtigungen bei Schadsoftware|Sie können eine Benachrichtigung an Absender oder Administratoren senden. Weitere Informationen finden Sie unter ["Konfigurieren von An malware-Richtlinien".](configure-anti-malware-policies.md)|
|Empfängerbenachrichtigungen|Isolieren Sie die Nachricht im Hintergrund, oder isolieren Sie die Nachricht, und stellen Sie sie auch mit allen Anlagen in Quarantäne, die durch eine einzelne Textdatei ersetzt werden, die Standardtext oder benutzerdefinierten Text enthält. Weitere Informationen finden Sie unter ["Konfigurieren von An malware-Richtlinien".](configure-anti-malware-policies.md)|
|Allgemeine Anlagenfilterung|Sie können eine Liste von Dateitypen aktivieren und anpassen, bei denen immer davon ausgegangen wird, dass es sich um Schadsoftware handelt. Weitere Informationen finden Sie unter [An malware protection in EOP](anti-malware-protection.md).|
|Antispywareschutz|Antischadsoftwareschutz umfasst Virenschutz und Antispywareschutz.|
|Erstellen benutzerdefinierter Filterrichtlinien für Schadsoftware|Für eine höhere Granularität können Sie benutzerdefinierte Schadsoftware-Filterrichtlinien erstellen und diese bestimmten Benutzern, Gruppen oder Domänen in Ihrer Organisation zuweisen. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie, die Priorität (das heißt, die Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern. Weitere Informationen finden Sie unter ["Konfigurieren von An malware-Richtlinien".](configure-anti-malware-policies.md)|
|**E-Mail-Weiterleitung und Connectors**||
|Bedingtes E-Mail-Routing|Weitere Informationen finden Sie unter [Szenario: Bedingtes E-Mail-Routing in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|Opportunistisches oder erzwungenes TLS|Opportunistisches oder erzwungenes TLS ist mit Connectors verfügbar. Opportunistisches TLS versucht eine TLS-Verbindung, verwendet jedoch eine SMTP-Verbindung, wenn die TLS-Verbindung nicht erfolgreich ist. Erzwingen von TLS erzwingt TLS-Verbindungen, d. h., die Nachricht wird zurückgewiesen, wenn die TLS-Verbindung nicht erfolgreich ist. Weitere Informationen zu TLS, Sicherheit und Connectors finden Sie unter [Set up connectors for secure mail flow with a partner organization](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).|
|Regionales Routing (Einschränkung des E-Mail-Flusses auf eine bestimmte Region)|Weitere Informationen finden Sie im Abschnitt "EOP-Datencenter" unter [Exchange Online Protection im Überblick](exchange-online-protection-overview.md).|
|SMTP-Konnektivitätsprüfung|Weitere Informationen zur Verwendung dieses Tools zum Testen des Nachrichtenflusses finden Sie unter "Testen des Nachrichtenflusses durch Überprüfen [Ihrer Microsoft 365-Connectors".](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)|
|Untergeordnete Domänen abgleichen|Weitere Informationen zum Aktivieren des Nachrichtenflusses zu und von Unterdomänen Ihrer akzeptierten Domänen finden Sie [unter Nachrichtenfluss in EOP](mail-flow-in-eop.md).|
|**Nachrichtenflussregeln**||
|Richtlinienbasierte Filterung und Aktionen|Benutzerdefinierte Richtlinien basieren auf Exchange-Nachrichtenflussregeln (auch bekannt als Transportregeln). Sie können nach Domäne, Schlüsselwort, Dateiname, Dateityp, Betreffzeile, Nachrichtentext, Absender, Empfänger, Kopfzeile und IP-Adresse filtern. Weitere Informationen finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Nach Textmustern filtern|Nachrichtenflussregeln können ein Array oder reguläre Ausdrücke verwenden, um Text zu finden. Sie können auch eine Zeichenfolge oder ein Array von Zeichenfolgen verwenden, um Nachrichteneigenschaften wie beispielsweise Adresse, Betreff, Nachrichtentext oder Anlagennamen abzugleichen. Weitere Informationen finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)|
|Benutzerdefinierte Wörterbücher|Nachrichtenflussregeln können lange Listen mit Text und Schlüsselwörtern enthalten, die die gleiche Funktionalität wie ein Benutzerwörterbuch bieten.|
|Richtlinienregeln pro Domäne|Der Bereich einer Nachrichtenflussregel kann so angepasst werden, dass er den Domänennamen von Absendern oder Empfängern, IP-Adressbereichen, Adressschlüsselwörtern oder -mustern, Gruppenmitgliedschaften und anderen Bedingungen zupasst.|
|Anlagenüberprüfung|Es können Regeln für die Überprüfung des Dateinamens, der Erweiterung und des Inhalts der Anlage erstellt werden.|
|Richtlinienregelbenachrichtigungen an den Absender senden|Sie können Nachrichten ablehnen und einen Unzustellbarkeitsbericht (auch als NDR oder  Unzustellbarkeitsnachricht  bezeichnet) an den Absender senden, wenn Sie die Nachricht mit der Erklärung ablehnen oder die Nachricht mit der erweiterten Statuscodeaktion ablehnen. Weitere Informationen finden Sie unter Aktionen für [Nachrichtenflussregel in Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|Umleiten oder Kopieren von Nachrichten|Nachrichtenflussregeln können Umleiten, Hinzufügen von Empfängern nach Cc oder Bcc, einfaches Hinzufügen von Empfängern und anderen Optionen. Weitere Informationen finden Sie unter Aktionen für [Nachrichtenflussregel in Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|Anpassen der Regelpriorität über mehrere Regeln hinweg|Die Reihenfolge, in der Regeln verarbeitet werden, können Sie im Exchange Admin Center ändern.|
|Filtern von Nachrichten und anschließendes Ändern des Routings oder der Attribute einer Nachricht|Sie können Nachrichten basierend auf einer Vielzahl von Bedingungen filtern und anschließend jeder Nachricht verschiedene Aktionen zuweisen. Weitere Informationen finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Ändern Sie den SCL (Spam Confidence Level) einer Nachricht nach Regel.|Sie können eine Nachricht während der Übertragung untersuchen und der Nachricht basierend auf den gewählten Kriterien eine SCL-Bewertung zuweisen. Weitere Informationen finden Sie unter Verwenden von [Nachrichtenflussregeln zum Festlegen der SCL (Spam Confidence Level) in Nachrichten.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)|
|Überprüfen von Nachrichtenanlagen|Sie können die Inhalte einer Anlage oder die Merkmale einer angehängten Daten untersuchen und ausgehend von den gefundenen Informationen eine durchzuführende Maßnahmen definieren. Weitere Informationen finden Sie unter Verwenden von [Nachrichtenflussregeln zum Überprüfen von Nachrichtenanlagen in Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)|
|**Verwaltung**||
|Webbasierte Verwaltung|Administratoren können den Dienst im Exchange Admin Center (EAC) verwalten, der in 60 Sprachen unterstützt wird. Weitere Informationen finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)|
|Verzeichnissynchronisierung|Die Verzeichnissynchronisierung ist über das Azure Active Directory-Synchronisierungstool verfügbar. Weitere Informationen finden Sie unter "Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung" unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).  |
|Verzeichnisbasierte Edge-Blockierung (DBEB)|DBEB ermöglicht es Ihnen, Nachrichten für ungültige Empfänger im Dienstnetzwerkumkreis abzulehnen. MIT DBEB können Administratoren Microsoft 365 E-Mail-aktivierte Empfänger hinzufügen und alle Nachrichten blockieren, die an E-Mail-Adressen gesendet werden, die in Microsoft 365 nicht vorhanden sind. Weitere Informationen zum Konfigurieren von DBEB finden Sie unter Verwenden der verzeichnisbasierten Edge-Blockierung, um An [ungültige Empfänger gesendete Nachrichten abzulehnen.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|PowerShell|Die vollständige EOP-Funktionalität ist in der eigenständigen EOP PowerShell verfügbar. Weitere Informationen finden Sie unter [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).|
|**Berichterstellung und Protokollierung**||
|Nachrichtenablaufverfolgung|Administratoren können E-Mail-Nachrichten verfolgen, während sie den Dienst passieren. Sie können bestimmen, ob eine gezielte E-Mail-Nachricht vom Dienst empfangen, abgelehnt, zurückgestellt oder zugestellt wurde. So können Sie in effizienter Weise Fragen der Benutzer beantworten, Probleme mit dem Nachrichtenfluss behandeln und Richtlinienänderungen überprüfen und müssen seltener den technischen Support um Unterstützung bitten. Weitere Informationen finden Sie unter [Nachrichtenablaufverfolgung im Security & Compliance Center](message-trace-scc.md).|
|Webbasierte Berichte|Die E-Mail-Schutzberichte im Security & Compliance Center stellen Messagingdaten zur Verfügung. Sie können beispielsweise überwachen, wie viel Spam und Schadsoftware erkannt wird oder wie oft Ihre Nachrichtenflussregeln übereinstimmen. Mithilfe dieser interaktiven Berichte erhalten Sie schnell einen visuellen Überblick über die zusammengefassten Daten und können Details zu einzelnen Nachrichten der letzten 90 Tage überprüfen. Weitere Informationen finden Sie unter Verwenden [von E-Mail-Schutzberichten zum Anzeigen von](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)Daten zu Schadsoftware, Spam und Regelerkennungen.|
|Überwachungsprotokollierung|Der Administrator-Rollengruppenbericht und das Administrator-Überwachungsprotokoll stehen EOP-Administratoren zur Verfügung. Weitere Informationen finden Sie unter [Überwachungsberichte in EOP](auditing-reports-in-eop.md).  |
|**Vereinbarungen zum Servicelevel (SLA) und Support**||
|SLA zur Effektivität der Antispamfunktion|\> 99%|
|SLA zum Anteil fälschlicherweise gefilterter Nachrichten|\< 1:250,000|
|SLA zu Virenerkennung und Virenschutz|100 % der bekannten Viren|
|SLA zu monatlicher Betriebszeit|99,999 %|
|Technischer Telefon- und Onlinesupport rund um die Uhr|Weitere Informationen zu Hilfe und Support für EOP finden Sie unter [Hilfe und Support für EOP](help-and-support-for-eop.md).|
|**Sonstige Funktionen**||
|Georedundantes globales Servernetzwerk|EOP wird in einem weltweiten Rechenzentrennetzwerk ausgeführt, das für eine optimale Verfügbarkeit entworfen wurde. Weitere Informationen finden Sie im Abschnitt "EOP-Rechenzentrum" unter [Exchange Online Protection im Überblick](exchange-online-protection-overview.md).  |
|Nachrichtenwarteschlangen, wenn lokaler Server keine E-Mails akzeptieren kann|Nachrichten, die sich in der Warteschlange befinden, verbleiben für einen Tag in der Warteschlange. Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird. Das Wiederholungsintervall für die Übertragung von Nachrichten beträgt im Durchschnitt 5 Minuten. Weitere Informationen finden Sie unter [Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten](eop-queued-deferred-and-bounced-messages-faq.md).|
|Office 365-Nachrichtenverschlüsselung als Add-On-Dienst erhältlich|Weitere Informationen finden Sie unter [Verschlüsselung in Office 365](../../compliance/encryption.md).|
|
