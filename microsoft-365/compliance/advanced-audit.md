---
title: Erweiterte Überwachung in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Die erweiterte Überwachung in Microsoft 365 bietet neue Überwachungsfunktionen, die Ihre Organisation bei forensischen und Complianceuntersuchungen unterstützen.
ms.openlocfilehash: 3c91a388bc01a5531309b556a5a8532cb2efbaa6
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311736"
---
# <a name="advanced-audit-in-microsoft-365"></a>Erweiterte Überwachung in Microsoft 365

Die [einheitliche Überwachungsfunktionen](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 bieten Organisationen Einblick in viele Arten von überwachten Aktivitäten über viele verschiedene Dienste in Microsoft 365 hinweg. Die erweiterte Überwachung hilft Organisationen dabei, forensische und Compliance-Untersuchungen durchzuführen, da hierfür die Aufbewahrungsdauer des Überwachungsprotokolls verlängert wird. Dadurch wird der Zugang zu wichtigen Ereignissen ermöglicht, die für die Ermittlung des Umfangs der Kompromittierung hilfreich sind, sowie schneller Zugriff auf die Office 365-Verwaltungsaktivitäts-API.

> [!NOTE]
> Erweiterte Überwachung ist für Organisationen mit einem Office 365 E5/A5/G5- oder Microsoft 365 Enterprise E5/A5/G5-Abonnement verfügbar. Darüber hinaus kann Benutzern eine Microsoft 365 E5/A5/G5 Compliance- oder E5/A5/G5 eDiscovery und Überwachungs-Add-On-Lizenz zugewiesen werden, wenn für Features für die erweiterte Überwachung eine Lizenzierung pro Benutzer erforderlich ist, wie dies bei der langfristigen Aufbewahrung von Überwachungsprotokollen und für den Zugang zu wichtigen Ereignissen für Untersuchungen der Fall ist. Weitere Informationen zur Lizenzierung finden Sie unter:<br/>- [Lizenzierungsanforderungen für die erweiterte Überwachung](auditing-solutions-overview.md#licensing-requirements)<br/>- [Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).

In diesem Artikel finden Sie eine Übersicht der Funktionen der Erweiterten Überwachung und eine Anweisung, wie Sie Benutzer für die Erweiterte Überwachung einrichten können.

## <a name="long-term-retention-of-audit-logs"></a>Langfristige Aufbewahrung von Überwachungsprotokollen

Die erweiterte Überwachung bewahrt alle Exchange-, SharePoint- und Azure Active Directory-Überwachungsdatensätze für ein Jahr auf. Dies geschieht durch eine standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle, die jeden Überwachungsdatensatz ein Jahr lang aufbewahrt, der den Wert von **Exchange**, **SharePoint** oder **AzureActiveDirectory** für die Eigenschaft **Workload** aufweist (die den Dienst anzeigt, in dem die Aktivität aufgetreten ist). Das Aufbewahren von Überwachungsaufzeichnungen über einen längeren Zeitraum kann bei laufenden forensischen oder Compliance-Untersuchungen hilfreich sein. Weitere Informationen hierzu finden Sie im Abschnitt "Standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle" in [Verwalten von Aufbewahrungsrichtlinien für Überwachungsprotokolle](audit-log-retention-policies.md#default-audit-log-retention-policy).

Außerdem wird es zukünftig möglich sein, Überwachungsprotokolle 10 Jahre lang aufzubewahren. Die zehnjährige Aufbewahrung von Überwachungsprotokollen ist bei langfristigen Untersuchungen und zur Einhaltung behördlicher, rechtlicher und interner Vorgaben hilfreich.

> [!NOTE]
> Für die zehnjährige Aufbewahrung von Überwachungsprotokollen wird eine zusätzliche Lizenz erforderlich sein. Weitere Informationen hierzu finden Sie im Abschnitt [Häufig gestellte Fragen zur erweiterten Überwachung](#faqs-for-advanced-audit) in diesem Artikel.

### <a name="audit-log-retention-policies"></a>Aufbewahrungsrichtlinien für Überwachungsprotokolle

Alle Überwachungsdatensätze, die in anderen Diensten generiert wurden, die nicht unter die Standardaufbewahrungsrichtlinie für Überwachungsprotokolle fallen (im vorherigen Abschnitt beschrieben), werden für 90 Tage aufbewahrt. Sie können jedoch benutzerdefinierte Aufbewahrungsrichtlinien für Überwachungsprotokolle erstellen, um andere Überwachungsaufzeichnungen bis zu 10 Jahre lang aufzubewahren. Sie können eine Richtlinie erstellen, um Überwachungsaufzeichnungen auf der Grundlage eines oder mehrerer der folgenden Kriterien aufzubewahren:

- Der Microsoft 365-Dienst, in dem die überwachten Aktivitäten ausgeführt werden

- Bestimmte überwachte Aktivitäten

- Der Benutzer, der eine überwachte Aktivität ausführt

Sie können auch festlegen, wie lange Überwachungsdatensätze, die der Richtlinie entsprechen, aufbewahrt werden, und eine Prioritätsstufe angeben, damit bestimmte Richtlinien Vorrang vor anderen Richtlinien haben. Beachten Sie außerdem, dass jede benutzerdefinierte Aufbewahrungsrichtlinie für Überwachungsprotokolle Vorrang vor der Standardaufbewahrungsrichtlinie für Überwachungsprotokolle hat, wenn Sie für einige oder alle Benutzer in Ihrer Organisation Exchange-, SharePoint- oder Azure Active Directory-Überwachungsaufzeichnungen weniger als ein Jahr lang (oder für 10 Jahre) aufbewahren möchten. Weitere Informationen finden Sie unter [Verwalten der Aufbewahrungsrichtlinien für Überwachungsprotokolle](audit-log-retention-policies.md).

## <a name="access-to-crucial-events-for-investigations"></a>Zugriff auf wichtige Ereignisse für Untersuchungen

Die erweiterte Überwachung hilft Organisationen dabei, forensische und Compliance-Untersuchungen durchzuführen durch die Möglichkeit, auf wichtige Ereignisse zuzugreifen wie beispielsweise: wann auf E-Mail-Elemente zugegriffen wurde, wann auf E-Mail-Elemente geantwortet wurde bzw. diese weitergeleitet wurden sowie wann und wonach ein Benutzer in Exchange Online und SharePoint Online gesucht hat. Diese wichtigen Ereignisse können Ihnen dabei helfen, mögliche Verstöße zu untersuchen und das Ausmaß der Kompromittierung zu ermitteln.  Bei der erweiterten Überwachung werden die folgenden wichtigen Ereignisse protokolliert:

- [MailItemsAccessed](#mailitemsaccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)<sup>*</sup>

- [SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)<sup>*</sup>

> [!NOTE]
> <sup>*</sup> Derzeit ist dieses Ereignis in Umgebungen von Office 365 und Microsoft 365 Government nicht verfügbar. Dazu gehören GCC-, GCC High- und DoD-Umgebungen.

### <a name="mailitemsaccessed"></a>MailItemsAccessed

Beim MailItemsAccessed-Ereignis handelt es sich um eine Postfachüberwachungsaktion, die ausgelöst wird, wenn E-Mail-Protokolle und E-Mail-Clients auf E-Mail-Daten zugreifen. Die MailItemsAccessed-Aktion kann Ermittlern dabei helfen, Datenverstöße zu erkennen und den Umfang der Nachrichten zu ermitteln, die möglicherweise kompromittiert wurden. Wenn ein Angreifer Zugriff auf E-Mail-Nachrichten erlangt hat, wird die MailItemsAccessed-Aktion ausgelöst, selbst wenn kein explizites Zeichen dafür vorliegt, dass Nachrichten tatsächlich gelesen wurden (mit anderen Worten: Die Art des Zugriffs, z. B. Bindung oder Synchronisierung, wird im Überwachungsdatensatz erfasst).

Die MailItemsAccessed-Postfachaktion ersetzt "MessageBind" in der Postfachüberwachungsprotokollierung in Exchange Online und bietet folgende Verbesserungen:

- "MessageBind" war nur für den AuditAdmin-Benutzer-Anmeldetyp konfigurierbar und galt nicht für Aktionen von Stellvertretungen oder Besitzern. "MailItemsAccessed" gilt für alle Anmeldetypen.

- "MessageBind" betraf nur den Zugriff durch einen E-Mail-Client. Es galt nicht für Synchronisierungsaktivitäten. MailItemsAccessed-Ereignisse werden sowohl durch Bindungs als auch Synchronisierungszugriffstypen ausgelöst.

- MessageBind-Aktionen löste beim mehrfachen Zugriff auf dieselbe E-Mail-Nachricht die Erstellung mehrerer Überwachungsdatensätze aus und führte dadurch zu überfüllten Überwachungsprotokollen. Im Gegensatz dazu werden MailItemsAccessed-Ereignisse in weniger Überwachungsdatensätzen aggregiert.

Informationen zu Überwachungsdatensätzen für MailItemsAccessed-Aktivitäten finden Sie unter [Verwenden der erweiterten Überwachung zur Untersuchung kompromittierter Konten](mailitemsaccessed-forensics-investigations.md).

Um nach MailItemsAccessed-Überwachungsaufzeichnungen zu suchen, können Sie im Microsoft 365 Compliance Center im [Überwachungsprotokoll-Suchtool](search-the-audit-log-in-security-and-compliance.md) in der Dropdownliste der **Exchange-Postfachaktivitäten** nach der Aktivität **MailItemsAccessed** (Postfachelemente, auf die zugegriffen wurde) suchen.

![Suchen nach MailItemsAccessed-Aktionen im Überwachungsprotokoll-Suchtool](../media/AdvAudit_MailItemsAccessed.png)

Sie können auch die Befehle [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) oder [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) in Exchange Online PowerShell ausführen.

### <a name="send"></a>Send

Beim Send-Ereignis handelt es sich ebenfalls um eine Postfachüberwachungsaktion. Sie wird ausgelöst, wenn ein Benutzer eine der folgenden Aktionen ausführt:

- Eine E-Mail sendet

- Auf eine E-Mail-Nachricht antwortet

- Eine E-Mail-Nachricht weiterleitet

Die mit der Untersuchung beauftragten Personen können das Send-Ereignis verwenden, um E-Mails zu identifizieren, die von einem kompromittierten Konto aus gesendet wurden. Die Überwachungsaufzeichnung für ein Send-Ereignis enthält Informationen zu der Nachricht, z. B. wann sie gesendet wurde, die InternetMessage-ID, die Betreffzeile und ob die Nachricht Anlagen enthielt. Anhand dieser Informationen können die mit der Untersuchung beauftragten Personen Informationen zu E-Mails ermitteln, die von einem kompromittierten Konto aus oder von einem Angreifer gesendet wurden. Darüber hinaus können sie ein Microsoft 365-eDiscovery-Tool verwenden, um nach der Nachricht (anhand der Betreffzeile oder der Nachrichten-ID) zu suchen, um deren Empfänger und ihren eigentlichen Inhalt zu ermitteln.

Um nach Send-Überwachungsaufzeichnungen zu suchen, können Sie im Microsoft 365 Compliance Center im [Überwachungsprotokoll-Suchtool](search-the-audit-log-in-security-and-compliance.md) in der Dropdownliste der **Exchange-Postfachaktivitäten** nach der Aktivität **Nachricht gesendet** suchen.

![Suche nach "Nachricht gesendet"-Aktionen im Überwachungsprotokoll-Suchtool](../media/AdvAudit_SentMessage.png)

Sie können auch die Befehle [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) oder [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) in Exchange Online PowerShell ausführen.

### <a name="searchqueryinitiatedexchange"></a>SearchQueryInitiatedExchange

Das SearchQueryInitiatedExchange-Ereignis wird ausgelöst, wenn jemand Outlook verwendet, um in einem Postfach nach Elementen zu suchen. Ereignisse werden ausgelöst, wenn Suchvorgänge in den Outlook-Umgebungen durchgeführt werden:

- Outlook (Desktopclient)

- Outlook im Web (OWA)

- Outlook für iOS

- Outlook für Android

- Mail-App für Windows 10

Die mit der Untersuchung beauftragten Personen können das SearchQueryInitiatedExchange-Ereignis verwenden, um festzustellen, ob ein Angreifer, der möglicherweise ein Konto manipuliert hat, nach vertraulichen Informationen im Postfach gesucht oder versucht hat, darauf zuzugreifen. Die Überwachungsaufzeichnung für ein SearchQueryInitiatedExchange-Ereignis enthält Informationen wie z. B. den tatsächlichen Suchabfragetext und ob die Suche im Outlook-Desktop-Client oder in Outlook im Web durchgeführt wurde. Der Überwachungsdatensatz gibt auch die Outlook-Umgebung an, in der die Suche ausgeführt wurde. Durch die Überprüfung der Suchabfragen, die ein Angreifer durchgeführt hat, kann die ermittelnde Person besser verstehen, warum nach den E-Mail-Daten gesucht wurde.

Um nach SearchQueryInitiatedExchange-Überwachungsaufzeichnungen zu suchen, können Sie im Compliance Center im [Überwachungsprotokoll-Suchtool](search-the-audit-log-in-security-and-compliance.md) in der Dropdownliste der **Suchaktivitäten** nach der Aktivität **E-Mail-Suche durchgeführt** suchen.

![Suchen nach durchgeführten E-Mail-Suchaktionen im Überwachungsprotokoll-Suchtool](../media/AdvAudit_SearchExchange.png)

Sie können auch den Befehl [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell ausführen.

> [!NOTE]
> Sie müssen SearchQueryInitiatedExchange für die Anmeldung aktivieren, damit Sie im Überwachungsprotokoll nach diesem Ereignis suchen können. Anweisungen finden Sie unter [Erweiterte Überwachung für Benutzer einrichten](set-up-advanced-audit.md#step-2-enable-crucial-events).

### <a name="searchqueryinitiatedsharepoint"></a>SearchQueryInitiatedSharePoint

Ähnlich wie bei der Suche nach Postfachelementen wird das SearchQueryInitiatedSharePoint-Ereignis ausgelöst, wenn jemand nach Elementen in SharePoint sucht. Ereignisse werden ausgelöst, wenn Suchvorgänge in den folgenden Typen von SharePoint-Websites durchgeführt werden:

- Startsites

- Kommunikationswebsites

- Hubwebsites

- Mit Microsoft Teams verknüpfte Websites

Die ermittelnden Personen können das SearchQueryInitiatedSharePoint-Ereignis verwenden, um festzustellen, ob ein Angreifer versucht hat, vertrauliche Informationen in SharePoint zu finden (und möglicherweise darauf zugegriffen). Die Überwachungsaufzeichnung für ein SearchQueryInitiatedSharePoint-Ereignis enthält außerdem den eigentlichen Text der Suchabfrage. Der Überwachungsdatensatz gibt auch den Typ der SharePoint-Website an, die durchsucht wurde. Durch die Überprüfung der Suchabfragen, die ein Angreifer durchgeführt hat, kann die ermittelnde Person besser den Zweck und den Umfang der Dateidaten nachvollziehen, nach denen gesucht wurde.

Um nach SearchQueryInitiatedSharePoint-Überwachungsaufzeichnungen zu suchen, können Sie im Compliance Center im [Überwachungsprotokoll-Suchtool](search-the-audit-log-in-security-and-compliance.md) in der Dropdownliste der **Suchaktivitäten** nach der Aktivität **SharePoint-Suche durchgeführt** suchen.

![Suche nach durchgeführten SharePoint-Suchaktionen im Überwachungsprotokoll-Suchtool](../media/AdvAudit_SearchSharePoint.png)

Sie können auch den Befehl [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell ausführen.

> [!NOTE]
> Sie müssen SearchQueryInitiatedSharePoint für die Anmeldung aktivieren, damit Sie im Überwachungsprotokoll nach diesem Ereignis suchen können. Anweisungen finden Sie unter [Erweiterte Überwachung für Benutzer einrichten](set-up-advanced-audit.md#step-2-enable-crucial-events).

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Zugriff mit hoher Bandbreite auf die Office 365-Verwaltungsaktivitäts-API

Organisationen, die über die Office 365-Verwaltungsaktivitäts-API auf Überwachungsprotokolle zugreifen, waren durch Drosselungsgrenzwerte auf Herausgeberebene eingeschränkt. Dies bedeutete, dass der Grenzwert für einen Herausgeber, der Daten im Namen mehrerer Kunden per Pull abruft, für all diese Kunden zusammen galt.

Mit der Veröffentlichung der erweiterten Überwachung wechseln wir von einem Grenzwert auf Herausgeberebene zu einem Grenzwert auf Mandantenebene. Dadurch erhält jede Organisation ein eigenes, vollständig zugewiesenes Bandbreitenkontingent erhält für den Zugriff auf ihre Überwachungsdaten. Die Bandbreite ist kein statischer, vordefinierter Grenzwert, sondern wird auf der Grundlage einer Kombination von Faktoren angepasst, beispielweise basierend auf der Anzahl der Arbeitsplätze in der Organisation oder der Tatsache, dass E5/A5/G5-Organisationen mehr Bandbreite als Nicht-E5/A5/G5-Organisationen erhalten.

Allen Organisationen ist anfänglich eine Baseline von 2.000-Anforderungen pro Minute zugeordnet. Dieser Wert wird abhängig von der Anzahl der Arbeitsplätze und Lizenzabonnements in einer Organisation dynamisch erhöht. E5/A5/G5-Organisationen erhalten ungefähr doppelt so viel Bandbreite wie Nicht-E5/A5/G5-Organisationen. Zum Schutz des Diensts gibt es auch eine Obergrenze für die maximale Bandbreite.

Weitere Informationen finden Sie im Abschnitt "API-Drosselung" in der [Referenz der Office 365-Verwaltungsaktivitäts-API](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).

## <a name="faqs-for-advanced-audit"></a>Häufig gestellte Fragen (FAQs) zur erweiterten Überwachung

**Benötigt jeder Benutzer eine E5/A5/G5-Lizenz, um von der erweiterten Überwachung profitieren zu können?**

Dem Benutzer muss eine E5/A5/G5-Lizenz zugewiesen werden, um von der erweiterten Überwachung auf Benutzerebene profitieren zu können. Es gibt einige Funktionen, die überprüfen, ob die entsprechende Lizenz vorliegt, bevor dem Benutzer das Feature bereitgestellt wird. Wenn Sie beispielsweise die Überwachungseinträge für einen Benutzer beibehalten möchten, dem keine passende Lizenz zugeordnet ist, die noch mindestens 90 Tage gültig ist, wird eine Fehlermeldung angezeigt.

**Meine Organisation verfügt über ein E5/A5/G5-Abonnement. Muss ich irgendetwas tun, um Zugriff auf die Überwachungsaufzeichnungen zu wichtigen Ereignissen zu erhalten?**

Für berechtigte Kunden und Benutzer, denen eine entsprechende Lizenz zugewiesen ist, gibt es keine Aktion, mit der sie Zugriff auf wichtige Überwachungsereignisse erlangen können.

**Was passiert mit den Überwachungsprotokolldaten meiner Organisation, wenn ich eine 10-Jahres-Richtlinie zur Aufbewahrung von Überwachungsprotokollen erstellt habe, als die Funktion für die allgemeine Verfügbarkeit freigegeben wurde, bevor die erforderliche Zusatzlizenz verfügbar gemacht wurde?**

Alle Überwachungsprotokolldaten, die durch eine 10-Jahres-Richtlinie zur Aufbewahrung von Überwachungsprotokollen abgedeckt sind, die Sie erstellt haben, nachdem die Funktion im letzten Quartal 2020 zur allgemeinen Verfügbarkeit freigegeben wurde, werden 10 Jahre lang aufbewahrt. Dies umfasst 10-Jahres-Richtlinien zur Aufbewahrung von Überwachungsprotokollen, die erstellt wurden, bevor die erforderliche Add-On-Lizenz zum Kauf freigegeben wurde. Da jedoch jetzt die 10-Jahres-Add-On-Lizenz für die Aufbewahrung von Überwachungsprotokollen verfügbar ist, müssen Sie diese Add-On-Lizenzen für alle Benutzer erwerben und zuweisen, deren Überwachungsdaten unter eine 10-Jahres-Richtlinie für die Aufbewahrung von Überwachungsdaten fallen.

**Sind die neuen Ereignisse in der erweiterten Überwachung in der Office 365-Verwaltungsaktivitäts-API verfügbar?**

Ja. Solange Überwachungsaufzeichnungen für Benutzer mit der entsprechenden Lizenz generiert werden, können Sie über die Office 365-Verwaltungsaktivitäts-API auf diese Aufzeichnungen zugreifen.

**Bedeutet eine höhere Bandbreite eine bessere Latenz oder eine höhere SLA?**

Gegenwärtig bietet eine hohe Bandbreite eine bessere Pipeline, insbesondere für Organisationen mit einem hohen Volumen an Überwachungssignalen und signifikanten Verbrauchsmustern. Mehr Bandbreite kann zu geringerer Latenz führen. Es gibt jedoch keinen mit hoher Bandbreite verbundenen SLA. Die Standardlatenzen sind dokumentiert, und diese ändern sich mit der Veröffentlichung der erweiterten Überwachung nicht.
