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
ms.openlocfilehash: 49d2e2bbf7d1c19bb4c282920008a0ca9a34188d
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862395"
---
# <a name="advanced-audit-in-microsoft-365"></a>Erweiterte Überwachung in Microsoft 365

Die [einheitliche Überwachungsfunktionen](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 bieten Organisationen Einblick in viele Arten von überwachten Aktivitäten über viele verschiedene Dienste in Microsoft 365 hinweg. In diesem Release fügen wir der erweiterten Überwachung in Microsoft 365 nun neue Überwachungsfunktionen hinzu, die Ihre Organisation bei forensischen und Complianceuntersuchungen unterstützen können.

> [!NOTE]
> Die erweiterte Überwachung ist für Organisationen mit einem Office 365- oder Microsoft 365 Enterprise E5-Abonnement verfügbar. Darüber hinaus kann Benutzern ein Microsoft 365 E5 Compliance-Add-On-Abonnement zugewiesen werden, wenn für die erweiterte Überwachung eine Lizenzierung pro Benutzer erforderlich ist, wie dies bei der langfristigen Aufbewahrung von Überwachungsprotokollen und hochwertigen Überwachungsereignissen der Fall ist.

In diesem Artikel finden Sie eine Übersicht über diese erweiterten Überwachungsfunktionen.

## <a name="long-term-retention-of-audit-logs"></a>Langfristige Aufbewahrung von Überwachungsprotokollen

Die erweiterte Überwachung bewahrt alle Exchange-, SharePoint- und Azure Active Directory-Überwachungsdatensätze für ein Jahr auf. Dies geschieht durch eine standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle, die jeden Überwachungsdatensatz ein Jahr lang aufbewahrt, der den Wert von **Exchange**, **SharePoint** oder **AzureActiveDirectory** für die Eigenschaft **Workload** aufweist (die den Dienst anzeigt, in dem die Aktivität aufgetreten ist). Dies kann bei laufenden forensischen oder Complianceuntersuchungen helfen. Weitere Informationen hierzu finden Sie im Abschnitt "Standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle" in [Verwalten von Aufbewahrungsrichtlinien für Überwachungsprotokolle](audit-log-retention-policies.md#default-audit-log-retention-policy).

## <a name="audit-log-retention-policies"></a>Aufbewahrungsrichtlinien für Überwachungsprotokolle

Alle Überwachungsdatensätze, die in anderen Diensten generiert wurden, die nicht unter die Standardaufbewahrungsrichtlinie für Überwachungsprotokolle fallen (im vorherigen Abschnitt beschrieben), werden für 90 Tage aufbewahrt. Jetzt können Sie jedoch benutzerdefinierte Aufbewahrungsrichtlinien für Überwachungsprotokolle erstellen, um andere Überwachungsdatensätze bis zu ein Jahr lang aufzubewahren. Sie können eine Richtlinie erstellen, um Überwachungsdatensätze auf der Grundlage eines oder mehrerer der folgenden Kriterien aufzubewahren:

- Der Microsoft 365-Dienst, in dem die überwachten Aktivitäten ausgeführt werden

- Bestimmte überwachte Aktivitäten

- Der Benutzer, der eine überwachte Aktivität ausführt

Sie können auch festlegen, wie lange Überwachungsdatensätze, die der Richtlinie entsprechen, aufbewahrt werden, und eine Prioritätsstufe angeben, damit bestimmte Richtlinien Vorrang vor anderen Richtlinien haben. Beachten Sie außerdem, dass jede benutzerdefinierte Aufbewahrungsrichtlinie für Überwachungsprotokolle Vorrang vor der Standardaufbewahrungsrichtlinie für Überwachungsprotokolle hat, wenn Sie für einige oder alle Benutzer in Ihrer Organisation Exchange-, SharePoint- oder Azure Active Directory-Überwachungsdatensätze für weniger als ein Jahr lang aufbewahren möchten. Weitere Informationen finden Sie unter [Verwalten der Aufbewahrungsrichtlinien für Überwachungsprotokolle](audit-log-retention-policies.md).

## <a name="high-value-audit-events"></a>Hochwertige Überwachungsereignisse

Hochwertige sicherheits- und compliancebezogene Überwachungsereignisse sind Ereignisse, die Ihnen bei der Untersuchung möglicher Verstöße oder bei anderen forensischen Untersuchungen helfen können. Das erste solche hochwertige Ereignis, das wir veröffentlichen, ist das Postfachüberwachungsereignis *MailItemsAccessed*. Dieses Ereignis wird ausgelöst, wenn E-Mail-Protokolle und -Clients auf E-Mail-Daten zugreifen. Das MailItemsAccessed-Ereignis kann Ermittlern dabei helfen, Datenverstöße zu erkennen und den Umfang der Nachrichten zu ermitteln, die möglicherweise kompromittiert wurden. Wenn ein Angreifer Zugriff auf E-Mail-Nachrichten erlangt hat, wird das MailItemsAccessed-Ereignis ausgelöst, selbst wenn kein explizites Zeichen dafür vorliegt, dass diese tatsächlich gelesen wurden (mit anderen Worten: Die Art des Zugriffs, z. B. über Bindung oder Synchronisierung, wird im Überwachungsdatensatz erfasst).

Die neue MailItemsAccessed-Postfachaktion ersetzt "MessageBind" in der Postfachüberwachungsprotokollierung in Exchange Online und bietet folgende Verbesserungen:

- "MessageBind" war nur für den AuditAdmin-Benutzer-Anmeldetyp konfigurierbar und galt nicht für Aktionen von Stellvertretungen oder Besitzern. "MailItemsAccessed" gilt für alle Anmeldetypen.

- "MessageBind" betraf nur den Zugriff durch einen E-Mail-Client. Es galt nicht für Synchronisierungsaktivitäten. MailItemsAccessed-Ereignisse werden sowohl durch Bindungs als auch Synchronisierungszugriffstypen ausgelöst.

- MessageBind-Aktionen löste beim mehrfachen Zugriff auf dieselbe E-Mail-Nachricht mehrere Überwachungsdatensätze aus und führte dadurch zu überfüllten Überwachungsprotokollen. Im Gegensatz dazu werden MailItemsAccessed-Ereignisse in weniger Überwachungsdatensätzen aggregiert.

Weitere Informationen zur Postfachüberwachungsprotokollierung finden Sie unter [Verwalten der Postfachüberwachungs](enable-mailbox-auditing.md).

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Zugriff mit hoher Bandbreite auf die Office 365-Verwaltungsaktivitäts-API

Organisationen, die über die Office 365-Verwaltungsaktivitäts-API auf Überwachungsprotokolle zugreifen, waren durch Drosselungsgrenzwerte auf Herausgeberebene eingeschränkt. Dies bedeutete, dass der Grenzwert für einen Herausgeber, der Daten im Namen mehrerer Kunden per Pull abruft, für all diese Kunden zusammen galt.

Mit der Veröffentlichung der erweiterten Überwachung wechseln wir von einem Grenzwert auf Herausgeberebene zu einem Grenzwert auf Mandantenebene. Dadurch erhält jede Organisation ein eigenes, vollständig zugewiesenes Bandbreitenkontingent erhält für den Zugriff auf ihre Überwachungsdaten. Die Bandbreite ist kein statischer, vordefinierter Grenzwert, sondern wird auf der Grundlage einer Kombination von Faktoren angepasst, beispielweise basierend auf der Anzahl der Arbeitsplätze in der Organisation oder der Tatsache, dass E5-Organisationen mehr Bandbreite als Nicht-E5-Organisationen erhalten.

Allen Organisationen ist anfänglich eine Baseline von 2.000-Anforderungen pro Minute zugeordnet. Dieser Wert wird abhängig von der Anzahl der Arbeitsplätze und Lizenzabonnements in einer Organisation dynamisch erhöht. E5-Organisationen erhalten ungefähr doppelt so viel Bandbreite wie Nicht-E5-Organisationen. Zum Schutz des Diensts gibt es auch eine Obergrenze für die maximale Bandbreite.

Weitere Informationen finden Sie im Abschnitt "API-Drosselung" in der [Referenz der Office 365-Verwaltungsaktivitäts-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).
