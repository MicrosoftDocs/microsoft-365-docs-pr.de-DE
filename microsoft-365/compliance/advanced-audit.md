---
title: Erweiterte Überwachung in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Die erweiterte Überwachung in Microsoft 365 bietet neue Überwachungsfunktionen, die Ihre Organisation bei forensischen und Complianceuntersuchungen unterstützen.
ms.openlocfilehash: bdde2552d2c5ccd790740e1f9077e5d26391e920
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634543"
---
# <a name="advanced-audit-in-microsoft-365"></a>Erweiterte Überwachung in Microsoft 365

Die [einheitliche Überwachungsfunktionen](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 bieten Organisationen Einblick in viele Arten von überwachten Aktivitäten über viele verschiedene Dienste in Microsoft 365 hinweg. In diesem Release fügen wir der erweiterten Überwachung in Microsoft 365 nun neue Überwachungsfunktionen hinzu, die Ihre Organisation bei forensischen und Complianceuntersuchungen unterstützen können.

> [!NOTE]
> Die erweiterte Überwachung ist für Organisationen mit einem Office 365 E5- oder Microsoft 365 Enterprise E5-Abonnement verfügbar. Darüber hinaus kann Benutzern eine Microsoft 365 E5 Compliance-Add-On-Lizenz zugewiesen werden, wenn für die erweiterte Überwachung eine Lizenzierung pro Benutzer erforderlich ist, wie dies bei der langfristigen Aufbewahrung von Überwachungsprotokollen und für den Zugriff zu wichtigen Ereignissen für Untersuchungen der Fall ist.

In diesem Artikel finden Sie eine Übersicht über diese erweiterten Überwachungsfunktionen.

## <a name="long-term-retention-of-audit-logs"></a>Langfristige Aufbewahrung von Überwachungsprotokollen

Die erweiterte Überwachung bewahrt alle Exchange-, SharePoint- und Azure Active Directory-Überwachungsdatensätze für ein Jahr auf. Dies geschieht durch eine standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle, die jeden Überwachungsdatensatz ein Jahr lang aufbewahrt, der den Wert von **Exchange**, **SharePoint** oder **AzureActiveDirectory** für die Eigenschaft **Workload** aufweist (die den Dienst anzeigt, in dem die Aktivität aufgetreten ist). Dies kann bei laufenden forensischen oder Complianceuntersuchungen helfen. Weitere Informationen hierzu finden Sie im Abschnitt "Standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle" in [Verwalten von Aufbewahrungsrichtlinien für Überwachungsprotokolle](audit-log-retention-policies.md#default-audit-log-retention-policy).

## <a name="audit-log-retention-policies"></a>Aufbewahrungsrichtlinien für Überwachungsprotokolle

Alle Überwachungsdatensätze, die in anderen Diensten generiert wurden, die nicht unter die Standardaufbewahrungsrichtlinie für Überwachungsprotokolle fallen (im vorherigen Abschnitt beschrieben), werden für 90 Tage aufbewahrt. Jetzt können Sie jedoch benutzerdefinierte Aufbewahrungsrichtlinien für Überwachungsprotokolle erstellen, um andere Überwachungsdatensätze bis zu ein Jahr lang aufzubewahren. Sie können eine Richtlinie erstellen, um Überwachungsdatensätze auf der Grundlage eines oder mehrerer der folgenden Kriterien aufzubewahren:

- Der Microsoft 365-Dienst, in dem die überwachten Aktivitäten ausgeführt werden

- Bestimmte überwachte Aktivitäten

- Der Benutzer, der eine überwachte Aktivität ausführt

Sie können auch festlegen, wie lange Überwachungsdatensätze, die der Richtlinie entsprechen, aufbewahrt werden, und eine Prioritätsstufe angeben, damit bestimmte Richtlinien Vorrang vor anderen Richtlinien haben. Beachten Sie außerdem, dass jede benutzerdefinierte Aufbewahrungsrichtlinie für Überwachungsprotokolle Vorrang vor der Standardaufbewahrungsrichtlinie für Überwachungsprotokolle hat, wenn Sie für einige oder alle Benutzer in Ihrer Organisation Exchange-, SharePoint- oder Azure Active Directory-Überwachungsdatensätze für weniger als ein Jahr lang aufbewahren möchten. Weitere Informationen finden Sie unter [Verwalten der Aufbewahrungsrichtlinien für Überwachungsprotokolle](audit-log-retention-policies.md).

## <a name="access-to-crucial-events-for-investigations"></a>Zugriff auf wichtige Ereignisse für Untersuchungen

Hochwertige sicherheits- und compliancebezogene Überwachungsereignisse sind Ereignisse, die Ihnen bei der Untersuchung möglicher Verstöße oder bei anderen forensischen Untersuchungen helfen können. Das erste solche hochwertige Ereignis, das wir veröffentlichen, ist die Postfachüberwachungsaktion *MailItemsAccessed*. Diese Aktion wird ausgelöst, wenn E-Mail-Protokolle und E-Mail-Clients auf E-Mail-Daten zugreifen. Die MailItemsAccessed-Aktion kann Ermittlern dabei helfen, Datenverstöße zu erkennen und den Umfang der Nachrichten zu ermitteln, die möglicherweise kompromittiert wurden. Wenn ein Angreifer Zugriff auf E-Mail-Nachrichten erlangt hat, wird die MailItemsAccessed-Aktion ausgelöst, selbst wenn kein explizites Zeichen dafür vorliegt, dass Nachrichten tatsächlich gelesen wurden (mit anderen Worten: Die Art des Zugriffs, z. B. Bindung oder Synchronisierung, wird im Überwachungsdatensatz erfasst).

Die neue MailItemsAccessed-Postfachaktion ersetzt "MessageBind" in der Postfachüberwachungsprotokollierung in Exchange Online und bietet folgende Verbesserungen:

- "MessageBind" war nur für den AuditAdmin-Benutzer-Anmeldetyp konfigurierbar und galt nicht für Aktionen von Stellvertretungen oder Besitzern. "MailItemsAccessed" gilt für alle Anmeldetypen.

- "MessageBind" betraf nur den Zugriff durch einen E-Mail-Client. Es galt nicht für Synchronisierungsaktivitäten. MailItemsAccessed-Ereignisse werden sowohl durch Bindungs als auch Synchronisierungszugriffstypen ausgelöst.

- MessageBind-Aktionen löste beim mehrfachen Zugriff auf dieselbe E-Mail-Nachricht die Erstellung mehrerer Überwachungsdatensätze aus und führte dadurch zu überfüllten Überwachungsprotokollen. Im Gegensatz dazu werden MailItemsAccessed-Ereignisse in weniger Überwachungsdatensätzen aggregiert.

Informationen zu Überwachungsdatensätzen für MailItemsAccessed-Aktivitäten finden Sie unter [Verwenden der erweiterten Überwachung zur Untersuchung kompromittierter Konten](mailitemsaccessed-forensics-investigations.md).

### <a name="search-for-mailitemsaccessed-audit-records"></a>Suchen nach MailItemsAccessed-Überwachungsdatensätzen

Um nach MailItemsAccessed-Überwachungsdatensätzen zu suchen, können Sie im Office 365 Security & Compliance Center im [Überwachungsprotokoll-Suchtool](search-the-audit-log-in-security-and-compliance.md) in der Dropdownliste der **Exchange-Postfachaktivitäten** nach der Aktivität **MailItemsAccessed** (Postfachelemente, auf die Zugegriffen wurde) suchen.

![Suchen nach MailItemsAccessed-Aktionen im Überwachungsprotokoll-Suchtool](../media/MailItemsAccessedSCC1.png)

Sie können auch die Befehle [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) oder [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) in Exchange Online PowerShell ausführen.

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Zugriff mit hoher Bandbreite auf die Office 365-Verwaltungsaktivitäts-API

Organisationen, die über die Office 365-Verwaltungsaktivitäts-API auf Überwachungsprotokolle zugreifen, waren durch Drosselungsgrenzwerte auf Herausgeberebene eingeschränkt. Dies bedeutete, dass der Grenzwert für einen Herausgeber, der Daten im Namen mehrerer Kunden per Pull abruft, für all diese Kunden zusammen galt.

Mit der Veröffentlichung der erweiterten Überwachung wechseln wir von einem Grenzwert auf Herausgeberebene zu einem Grenzwert auf Mandantenebene. Dadurch erhält jede Organisation ein eigenes, vollständig zugewiesenes Bandbreitenkontingent erhält für den Zugriff auf ihre Überwachungsdaten. Die Bandbreite ist kein statischer, vordefinierter Grenzwert, sondern wird auf der Grundlage einer Kombination von Faktoren angepasst, beispielweise basierend auf der Anzahl der Arbeitsplätze in der Organisation oder der Tatsache, dass E5-Organisationen mehr Bandbreite als Nicht-E5-Organisationen erhalten.

Allen Organisationen ist anfänglich eine Baseline von 2.000-Anforderungen pro Minute zugeordnet. Dieser Wert wird abhängig von der Anzahl der Arbeitsplätze und Lizenzabonnements in einer Organisation dynamisch erhöht. E5-Organisationen erhalten ungefähr doppelt so viel Bandbreite wie Nicht-E5-Organisationen. Zum Schutz des Diensts gibt es auch eine Obergrenze für die maximale Bandbreite.

Weitere Informationen finden Sie im Abschnitt "API-Drosselung" in der [Referenz der Office 365-Verwaltungsaktivitäts-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).

## <a name="faqs-for-advanced-audit"></a>Häufig gestellte Fragen (FAQs) zur erweiterten Überwachung

**Wo kann ich auf die erweiterte Überwachung zugreifen?**

Nach der Einführung der erweiterten Überwachung für Ihre Organisation können Sie Aufbewahrungsrichtlinien für Überwachungsprotokolle erstellen und mithilfe des Überwachungsprotokoll-Suchtools im [Office 365 Security & Compliance Center](https://protection.office.com) nach MailItemsAccessed-Überwachungsdatensätzen suchen. Wir arbeiten daran, die erweiterte Überwachung in den kommenden Wochen im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) bereitzustellen.

**Benötigt jeder Benutzer eine E5-Lizenz, um von der erweiterten Überwachung profitieren zu können?**

Dem Benutzer muss eine E5-Lizenz zugewiesen werden, um von der erweiterten Überwachung auf Benutzerebene profitieren zu können. Es gibt einige Funktionen, die überprüfen, ob die entsprechende Lizenz vorliegt, bevor dem Benutzer das Feature bereitgestellt wird. Wenn Sie beispielsweise die Überwachungseinträge für einen Benutzer beibehalten möchten, dem keine E5-Lizenz zugeordnet ist, die noch mindestens 90 Tage gültig ist, wird eine Fehlermeldung angezeigt.

**Warum wird die erweiterte Überwachung in meiner Organisation nicht angezeigt, obwohl wir über ein E5-Abonnement und Benutzer mit E5-Lizenzen verfügen?**

Es ist möglich, dass Features der erweiterten Überwachung (z. B. die Möglichkeit, Aufbewahrungsrichtlinien für Überwachungsprotokolle und die Protokollierung von MailItemsAccessed-Überwachungsdatensätzen zu erstellen) in Ihrer Organisation nicht verfügbar sind, selbst wenn die korrekte Lizenzierung vorhanden ist. Wenn Ihnen das passiert, liegt es daran, dass das Rollout des Pakets der erweiterten Überwachung für Ihre Organisation noch nicht erfolgt ist. Hierbei handelt es sich um ein vorübergehendes Problem des Lizenzabgleichs, das für die betroffenen Organisationen in den nächsten Wochen gelöst werden sollte. Um dieses Problem zu entschärfen, führen Sie bitte die folgenden Schritte für jeden E5-Benutzer durch:

1. Wählen Sie im Microsoft 365 Admin Center unter **Benutzer > Aktive Benutzer** einen Benutzer aus.

2. Klicken Sie auf der Benutzereigenschaften-Flyoutseite auf **Lizenzen und Apps**.

3. Erweitern Sie den Abschnitt **Apps**, und führen Sie dann eine der folgenden Aktionen aus:

   a. Wenn das Kontrollkästchen **Microsoft 365 – Erweiterte Überwachung** nicht aktiviert ist, aktivieren Sie es, und klicken Sie dann auf **Änderungen speichern**. Überwachungsdatensätze für MailItemsAccessed-Aktionen für diesen Benutzer sollten innerhalb von 24 Stunden durchsuchbar sein.

   b. Wenn das Kontrollkästchen **Microsoft 365 – Erweiterte Überwachung** aktiviert ist, deaktivieren Sie es, und klicken Sie dann auf **Änderungen speichern**. Siehe Schritt 4.

4. Wenn Sie das Kontrollkästchen in Schritt 3 deaktiviert haben, warten Sie 60 Minuten, und wiederholen Sie dann Schritt 3a, um die App "Microsoft 365 – Erweiterte Überwachung" zu aktivieren.

**Was passiert, wenn meine Organisation die private Vorschauversion für die einjährige Aufbewahrung von Überwachungsdatensätze verwendet hat?**

Ihre Aufbewahrungsrichtlinien für Überwachungsprotokolle aus dem Vorschauprogramm bleiben erhalten, solange Sie sie nicht durch benutzerdefinierte Aufbewahrungsrichtlinien für Überwachungsprotokolle außer Kraft setzen und ändern.

**Was geschieht, wenn meine Organisation die Überwachungsprotokolle länger als ein Jahr aufbewahren will?**

Wir untersuchen Optionen, wie und ob wir längere Aufbewahrungsfristen für Überwachungsdatensätze anbieten können. Feedback zu einer längeren Aufbewahrung von Überwachungsdatensätzen können Sie unter [Office 365 User Voice](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187) abgeben.

**Meine Organisation verfügt über ein E5-Abonnement. Muss ich irgendetwas tun, um Zugriff auf den Überwachungsdatensätzen für MailItemsAccessed-Ereignisse zu erhalten?**

Berechtigte Kunden müssen nichts tun, um Zugriff auf MailItemsAccessed-Ereignisse zu erhalten. Wie bereits zuvor in diesem Thema erläutert, verhindern die durch das Problem des Lizenzabgleichs verursachte Latenzzeit jedoch möglicherweise, dass Überwachungsdatensätze für das MailItemsAccessed-Ereignis beim Durchsuchen eines Überwachungsprotokolls zurückgegeben werden. Folgen Sie in diesem Fall den Anweisungen im Abschnitt "Suchen nach MailItemsAccessed-Überwachungsdatensätzen".

**Planen Sie dieses Jahr zusätzliche Ereignisse zu veröffentlichen?**

Ja, wir planen die Veröffentlichung neuer Ereignisse, die für die Untersuchungen in den kommenden Monaten entscheidend sind. Wir werden Informationen über diese neuen Ereignisse in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap) veröffentlichen, sobald wir uns dem Veröffentlichungsdatum nähern.

**Sind die neuen Ereignisse in der erweiterten Überwachung in der Office 365-Verwaltungsaktivitäts-API verfügbar?**

Ja. Solange Überwachungsdatensätze für Benutzer mit der entsprechenden Lizenz generiert werden, können Sie auf diese Datensätze über die Office 365-Verwaltungsaktivitäts-API zugreifen.

**Bedeutet eine höhere Bandbreite eine bessere Latenz oder eine höhere SLA?**

Gegenwärtig bietet eine hohe Bandbreite eine bessere Pipeline, insbesondere für Organisationen mit einem hohen Volumen an Überwachungssignalen und signifikanten Verbrauchsmustern. Dies kann zu einer besseren Latenz führen. Aber es gibt keine SLA, die mit hoher Bandbreite verbunden ist. Die Standardlatenzen sind dokumentiert, und diese ändern sich mit der Veröffentlichung der erweiterten Überwachung nicht.
