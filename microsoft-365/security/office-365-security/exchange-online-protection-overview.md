---
title: Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, Exchange Online Protection (EOP) Ihre lokale E-Mail-Organisation in eigenständigen und Hybridumgebungen schützen kann.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad083e828fbed27cce4b8929c1bee3081c983c17
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707284"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection im Überblick

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) ist der cloudbasierte Filterdienst, der Ihre Organisation vor Spam, Schadsoftware und anderen E-Mail-Bedrohungen schützt. EOP ist in allen organisationen Microsoft 365 mit Exchange Online enthalten.

> [!NOTE]
> EOP ist auch für sich allein verfügbar, um lokale Postfächer und in Hybridumgebungen zu schützen, um lokale Postfächer Exchange schützen. Weitere Informationen finden Sie unter [Eigenständige Exchange Online Protection](/exchange/standalone-eop/standaonline-eop).

Die Schritte zum Einrichten von EOP-Sicherheitsfeatures und ein Vergleich mit der zusätzlichen Sicherheit, die Sie in Microsoft Defender for Office 365 erhalten, finden Sie unter [Protect against threats](protect-against-threats.md). Die empfohlenen Einstellungen für EOP-Features finden Sie unter Empfohlene Einstellungen für EOP und [Microsoft Defender für Office 365 Sicherheit.](recommended-settings-for-eop-and-office365.md)

Im Rest dieses Artikels wird erläutert, wie EOP funktioniert und welche Features in EOP verfügbar sind.

## <a name="how-eop-works"></a>Funktionsweise von EOP

Die Funktionsweise von EOP lässt sich am besten an der Verarbeitung eingehender E-Mails veranschaulichen:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Grafik von E-Mails aus dem Internet oder Kundenfeedback, die an EOP und über die Verbindung, an Schadsoftware, E-Mail-Regeln-Schrägstrich-Richtlinienfilterung und Inhaltsfilterung übergeben werden, vor dem Urteil der Junk-E-Mail oder Quarantäne oder der Endbenutzer-E-Mail-Zustellung.":::

1. Wenn eine eingehende Nachricht EOP eingibt, überläuft sie zunächst die Verbindungsfilterung, die die Reputation des Absenders überprüft. Die Mehrzahl der Spamnachrichten wird zu diesem Zeitpunkt beendet und von EOP abgelehnt. Weitere Informationen finden Sie unter [Konfigurieren der Richtlinie für Verbindungsfilter](configure-the-connection-filter-policy.md).

2. Anschließend wird die Nachricht auf Schadsoftware überprüft. Wenn schadsoftware in der Nachricht oder in den Anlagen gefunden wird, wird die Nachricht an einen Nur-Administrator-Quarantänespeicher geroutet. Weitere Informationen zum Schutz vor Schadsoftware finden Sie unter [An malware protection in EOP](anti-malware-protection.md).

3. Die Nachricht wird über die Richtlinienfilterung fortgesetzt, wobei sie anhand der von Ihnen erstellten Nachrichtenflussregeln (auch als Transportregeln bezeichnet) ausgewertet wird. Beispielsweise kann eine Regel eine Benachrichtigung an einen Vorgesetzten senden, wenn eine Nachricht von einem bestimmten Absender eintrifft.

   In einer lokalen Organisation mit Exchange Enterprise CAL mit Services-Lizenzen finden an diesem Punkt auch [DLP-Prüfungen (Data Loss Prevention,](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) Verhinderung von Datenverlust) in EOP statt.

4. Die Nachricht durchläuft die Inhaltsfilterung (Antispam und Antis spoofing), bei der schädliche Nachrichten als Spam, Spam mit hoher Vertrauenssicherheit, Phishing, Phishing mit hoher Vertrauenssicherheit oder Massen (Antispamrichtlinien) oder Spoofing (Spoofeinstellungen in Antiphishingrichtlinien) identifiziert werden. Sie können die Aktion konfigurieren, die für die Nachricht basierend auf dem Filterverkündungs-Urteil (Quarantäne, Verschieben in den Junk-E-Mail-Ordner usw.) zu ergreifen ist. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien und](configure-your-spam-filter-policies.md) Konfigurieren von [Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md).

Eine Nachricht, die alle diese Schutzebenen erfolgreich übergibt, wird an die Empfänger übermittelt.

Weitere Informationen finden Sie unter [Reihenfolge und Rangfolge des E-Mail-Schutzes](how-policies-and-protections-are-combined.md).

### <a name="eop-datacenters"></a>EOP-Datencenter

EOP wird in einem weltweiten Netzwerk von Rechenzentren ausgeführt, die die beste Verfügbarkeit bieten. Wenn beispielsweise ein Datencenter nicht mehr verfügbar ist, werden E-Mail-Nachrichten automatisch ohne Dienstunterbrechung an ein anderes Datencenter geroutet. Server in jedem Datencenter akzeptieren Nachrichten in Ihrem Auftrag und bieten eine Schicht der Trennung zwischen Ihrer Organisation und dem Internet, wodurch die Last auf Ihren Servern reduziert wird. Über dieses hochverf nkte Netzwerk kann Microsoft sicherstellen, dass E-Mails ihre Organisation zeitnah erreichen.

EOP führt einen Lastenausgleich zwischen Rechenzentren aus, jedoch nur innerhalb einer Region. Wenn Sie über eine Bereitstellung in einer bestimmten Region verfügen, werden alle Nachrichten mit dem E-Mail-Routing für diese Region verarbeitet. Die folgende Liste zeigt, wie regionales E-Mail-Routing für die EOP-Datencenter funktioniert:

- In Europa, dem Nahen Osten und Afrika (EMEA) befinden sich alle Exchange Online-Postfächer in EMEA-Rechenzentren, und alle Nachrichten werden zur EOP-Filterung über EMEA-Rechenzentren geleitet.
- In Asia-Pacific (APAC) befinden sich alle Exchange Online Postfächer in APAC-Rechenzentren, und Nachrichten werden zurzeit zur EOP-Filterung über APAC-Rechenzentren geroutet.
- In Amerika werden Dienste an den folgenden Standorten verteilt:
  - Südamerika: Exchange Online Postfächer befinden sich in Rechenzentren in Brasilien und Chile. Alle Nachrichten werden für die EOP-Filterung über lokale Rechenzentren geroutet. Isolierte Nachrichten werden im Datencenter gespeichert, in dem sich der Mandant befindet.
  - Kanada: Exchange Online Postfächer befinden sich in Rechenzentren in Kanada. Alle Nachrichten werden für die EOP-Filterung über lokale Rechenzentren geroutet. Isolierte Nachrichten werden im Datencenter gespeichert, in dem sich der Mandant befindet.
  - USA: Exchange Online postfächer befinden sich in US-Rechenzentren. Alle Nachrichten werden für die EOP-Filterung über lokale Rechenzentren geroutet. Isolierte Nachrichten werden im Datencenter gespeichert, in dem sich der Mandant befindet.
- Alle Exchange Online-Postfächer für die Government Community Cloud (GCC) befinden sich in US-Rechenzentren, und alle Nachrichten werden zur EOP-Filterung über US-Rechenzentren geleitet.

### <a name="eop-features"></a>EOP-Funktionen

Dieser Abschnitt bietet eine übersicht über die wichtigsten Features, die in EOP verfügbar sind.

Informationen zu Anforderungen, wichtigen Grenzwerten und der Verfügbarkeit von Features in allen EOP-Abonnementplänen finden Sie unter [Exchange Online Protection Dienstbeschreibung](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

**Hinweise**:

- EOP verwendet mehrere URL-Sperrlisten, die Unterstützung beim Erkennen bekannter schädlicher Links in Nachrichten bieten.
- EOP verwendet eine umfangreiche Liste von Domänen, die als Spamnachrichten bekannt sind.
- EOP verwendet mehrere Ansoftwaremodule, mit deren Hilfe unsere Kunden jederzeit automatisch geschützt werden können.
- EOP überprüft die aktive Nutzlast im Nachrichtentext und alle Nachrichtenanlagen auf Schadsoftware.
- Empfohlene Werte für Schutzrichtlinien finden Sie unter [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).
- Schnelle Anweisungen zum Konfigurieren von Schutzrichtlinien finden Sie unter [Protect against threats](protect-against-threats.md).

<br>

****
|Feature|Kommentare|
|---|---|
|**Schutz**||
|Antischadsoftware|[Schutz vor Schadsoftware in EOP](anti-malware-protection.md) <p> [Häufig gestellte Fragen zum Schutz vor Schadsoftware](anti-malware-protection-faq-eop.yml) <p> [Konfigurieren von An malware-Richtlinien in EOP](configure-anti-malware-policies.md)|
|Eingehende Antispamnachrichten|[Antispamschutz in EOP](anti-spam-protection.md) <p> [Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.yml) <p> [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
|Ausgehender Antispam|[Ausgehender Spamschutz in EOP](outbound-spam-controls.md) <p> [Konfigurieren der Filterung ausgehender Spamnachrichten in EOP](configure-the-outbound-spam-policy.md) <p> [Automatische externe E-Mail-Weiterleitung in Microsoft 365 steuern](external-email-forwarding.md)|
|Verbindungsfilterung|[Konfigurieren von Verbindungsfiltern](configure-the-connection-filter-policy.md)|
|Antiphishing|[Antiphishingrichtlinien in Microsoft 365](set-up-anti-phishing-policies.md) <p> [Konfigurieren von Anti-Phishing-Richtlinien in EOP](configure-anti-phishing-policies-eop.md)|
|Antispoofingschutz|[Einblick in spoof intelligence in EOP](learn-about-spoof-intelligence.md) <p> [Verwalten der Zulassungs-/Sperrliste des Mandanten](tenant-allow-block-list.md)|
|Automatisches Löschen (Zero-Hour Auto Purge, ZAP) für zugestellte Schadsoftware, Spam und Phishingnachrichten|[ZAP in Exchange Online](zero-hour-auto-purge.md)|
|Voreingestellte Sicherheitsrichtlinien|[Vordefinierte Sicherheitsrichtlinien in EOP und Microsoft Defender für Office 365](preset-security-policies.md) <p> [Konfigurationsanalyse für Schutzrichtlinien in EOP und Microsoft Defender für Office 365](configuration-analyzer-for-security-policies.md)|
|Mandanten-Allow/Block List|[Verwalten der Zulassungs-/Sperrliste des Mandanten](tenant-allow-block-list.md)|
|Blockieren von Listen für Nachrichtensender|[Erstellen blockierter Absenderlisten in EOP](create-block-sender-lists-in-office-365.md)|
|Zulassen von Listen für Nachrichtensender|[Erstellen von Listen sicherer Absender in EOP](create-safe-sender-lists-in-office-365.md)|
|Directory Based Edge Blocking (DBEB)|[Verwenden von verzeichnisbasierter Edge-Blockierung zum Ablehnen von Nachrichten, die an ungültige Empfänger gesendet wurden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**Quarantäne und Übermittlungen**||
|Administratorübermittlung|[Verwenden der Admin-Übermittlung zum Übermitteln von mutmaßlichem Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md)|
|Benutzerübermittlungen (benutzerdefiniertes Postfach)|[Richtlinie für Benutzerübermittlungen](user-submission.md)|
|Quarantäne – Administratoren|[Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md) <p> [Häufig gestellte Fragen zu isolierten Nachrichten](quarantine-faq.yml) <p> [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md) <p> [Antispam-Nachrichtenkopfzeilen in Microsoft 365](anti-spam-message-headers.md) <p> Sie können die Nachrichtenkopfzeilen von isolierten Nachrichten mithilfe der [Nachrichtenkopfanalyse unter analysieren.](https://mha.azurewebsites.net/)|
|Quarantäne – Endbenutzer|[Suchen und Freigeben von isolierten Nachrichten als Benutzer in EOP](find-and-release-quarantined-messages-as-a-user.md) <p> [Verwenden von Spambenachrichtigungen von Benutzern zum Veröffentlichen und Melden isolierter Nachrichten](use-spam-notifications-to-release-and-report-quarantined-messages.md)|
|**Nachrichtenfluss**||
|Nachrichtenflussregeln|[Nachrichtenflussregeln (Transportregeln) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Aktionen für Nachrichtenflussregeln in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [Verwalten von Nachrichtenflussregeln in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [Nachrichtenflussregelprozeduren in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|Akzeptierte Domänen|[Verwalten akzeptierter Domänen in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|Connectors|[Konfigurieren des Nachrichtenflusses mithilfe von Connectors in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|Verbesserte Filterfunktionen für Connectors|[Erweiterte Filterung für Connectors in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**Überwachen**||
|Nachrichtenablaufverfolgung|[Nachrichtenablaufverfolgung](message-trace-scc.md) <p> [Nachrichtenverfolgung im Exchange Admin Center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|Berichte & E-Mail-Zusammenarbeit|[E-Mail-Sicherheitsberichte anzeigen](view-email-security-reports.md)|
|Nachrichtenflussberichte|[Nachrichtenflussberichte anzeigen](view-mail-flow-reports.md) <p> [Nachrichtenflussberichte im Exchange Admin Center](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|Einblicke in den Nachrichtenfluss|[Einblicke in den Nachrichtenfluss](mail-flow-insights-v2.md) <p> [Einblicke in den Nachrichtenfluss im Exchange Admin Center](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|Überwachungsberichte|[Überwachungsberichte im Exchange Admin Center](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|Warnungsrichtlinien|[Warnungsrichtlinien](../../compliance/alert-policies.md)|
|**Vereinbarungen zum Servicelevel (SLA) und Support**||
|SLA zur Effektivität der Antispamfunktion|\> 99%|
|SLA zum Anteil fälschlicherweise gefilterter Nachrichten|\< 1:250,000|
|SLA zu Virenerkennung und Virenschutz|100 % der bekannten Viren|
|SLA zu monatlicher Betriebszeit|99,999 %|
|Technischer Telefon- und Onlinesupport rund um die Uhr|[Hilfe und Unterstützung für EOP](help-and-support-for-eop.md).|
|**Sonstige Funktionen**||
|Georedundantes globales Servernetzwerk|EOP wird in einem weltweiten Rechenzentrennetzwerk ausgeführt, das für eine optimale Verfügbarkeit entworfen wurde. Weitere Informationen finden Sie im Abschnitt [EOP-Rechenzentren](#eop-datacenters) weiter oben in diesem Artikel.|
|Nachrichtenwarteschlangen, wenn lokaler Server keine E-Mails akzeptieren kann|Nachrichten, die sich in der Verschiebung befinden, verbleiben für einen Tag in unseren Warteschlangen. Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird. Das Wiederholungsintervall für die Übertragung von Nachrichten beträgt im Durchschnitt 5 Minuten. Weitere Informationen finden Sie unter [Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten](eop-queued-deferred-and-bounced-messages-faq.yml).|
|Office 365-Nachrichtenverschlüsselung als Add-On verfügbar|Weitere Informationen finden Sie unter [Verschlüsselung in Office 365](../../compliance/encryption.md).|
|||
