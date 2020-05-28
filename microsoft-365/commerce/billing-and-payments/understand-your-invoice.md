---
title: Ihre Rechnung verstehen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie Ihre Rechnung oder Rechnung für Microsoft Business-Produkte lesen und verstehen.
keywords: Abrechnungskonten, Organisationsinformationen, Rechnungen
ms.openlocfilehash: 17cfba93e8d892081900f6fcefb4504fb553b5bf
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402642"
---
# <a name="understand-your-bill-or-invoice"></a>Ihre Rechnung verstehen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Die Rechnung enthält eine Zusammenfassung ihrer Gebühren und Anweisungen zur Zahlung. Sie können [Ihre Online Rechnung](#view-your-online-invoice) im Microsoft 365 Admin Center anzeigen. Sie können es auch im Portable Document Format (. pdf) herunterladen, um es per e-Mail zu senden.

Wenn Sie nur ein Microsoft 365-Abonnement haben, finden Sie weitere Informationen Untergrund [Legendes zu Ihrer Rechnung oder Rechnung für Microsoft 365 for Business](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Grundlegendes zum Rechnungskopf

Oben auf der ersten Seite wird angegeben, wer für die Zahlung verantwortlich ist, wo die Rechnung gesendet wird, und eine Zusammenfassung der Gebühren.

| Begriff | Beschreibung |
| --- | --- |
| Verkauft an |Das Abrechnungskonto, das den Namen und die Adresse der für die Zahlung verantwortlichen juristischen Person identifiziert. Diese Informationen können auf der Seite " <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Abrechnungskonten</a> " verwaltet werden, auf der Sie die Kontovereinbarung finden und die Rollen und Berechtigungen verwalten können. |
| Rechnung an |Gibt an, wer die Rechnung erhält. Diese Informationen können auf der Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Abrechnungsprofile</a> verwaltet werden. Das Abrechnungsprofil wird auch auf der Seite "Online Rechnung" im Abschnitt " **Rechnungszusammenfassung** " angezeigt. Weitere Informationen zu Abrechnungs Profilen und deren Verwendung zum Erstellen flexiblerer Abrechnungsoptionen für Ihre Organisation finden Sie unter [Manage Billing Profiles](manage-billing-profiles.md). |
| Abrechnungsprofil |Der Name des Abrechnungs Profils, das zum Definieren von Rechnungs Eigenschaften verwendet wird, wie **Bill to**, **PO-Nummer**und Zahlungsbedingungen. Diese Informationen können auf der Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Abrechnungsprofile</a> verwaltet werden. Weitere Informationen zu Abrechnungs Profilen und deren Verwendung zum Erstellen flexiblerer Abrechnungsoptionen für Ihre Organisation finden Sie unter [Manage Billing Profiles](manage-billing-profiles.md). |
| Rechnungsnummer |Eine eindeutige, von Microsoft generierte Rechnungsnummer, die zu Überwachungszwecken verwendet wird. |
| Rechnungsdatum |Das Datum, an dem die Rechnung generiert wird, in der Regel fünf bis zwölf Tage nach dem Ende des Abrechnungszyklus. Sie können Ihr Rechnungsdatum auf der Seite Abrechnungsprofil Details überprüfen. Zuschläge, die zwischen dem Ende des Abrechnungszeitraums und dem Rechnungsdatum auftreten, sind in der Rechnung für den nächsten Monat enthalten, da Sie sich im nächsten Abrechnungszeitraum befinden. Die Anfangs-und Enddaten für die Abrechnungsperiode für jede Rechnung werden in der Rechnungs-PDF-Datei über die **Abrechnungszusammenfassung**aufgeführt.|
| Zahlungsbedingungen |Wie Sie Ihre Microsoft-Rechnung bezahlen. *Net 30 Tage* bedeutet, dass Sie mit den folgenden Anweisungen auf Ihrer Rechnung bezahlen, innerhalb von 30 Tagen nach Rechnungsdatum. |

## <a name="understand-the-billing-summary"></a>Grundlegendes zur Abrechnungszusammenfassung

Die **Abrechnungszusammenfassung** zeigt die Zusammenfassung der Gebühren seit dem vorherigen Abrechnungszeitraum, alle angewandten Guthaben, Steuern und den fälligen Gesamtbetrag an.

| Begriff | Beschreibung |
| --- | --- |
| Gebühren|Die Gesamtzahl der für diesen Abrechnungszeitraum erworbenen Produkte und der zugehörigen Gebühren und steuern. Käufe werden aggregiert, um eine präzise Ansicht Ihrer Rechnung bereitzustellen. |
| Mitwirkende |Guthaben, die Sie von Rücksendungen erhalten haben |
| Zugewiesene Azure-Gutschriften |Ihre Azure-Gutschriften, die automatisch auf Azure angewendet werden, belasten jeden Abrechnungszeitraum. Wenn Sie keine Azure-Gutschriften haben, ist dieses Feld ausgeblendet. Weitere Informationen zu Azure Credits finden Sie unter [Track Microsoft Customer Agreement Azure Credit Balance](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance). |
| Teilergebnis |Der fällige Betrag vor Steuern |
| Steuer |Art und Höhe der Steuer, die Sie zahlen, je nach Land Ihres Abrechnungs Profils. Wenn Sie keine Steuern zahlen müssen, wird auf Ihrer Rechnung keine Steuer angezeigt. |

### <a name="understand-your-charges"></a>Grundlegendes zu ihren Gebühren

Auf den Gebührenseiten werden die Kosten nach Produkt aufgeschlüsselt angezeigt. Für Azure-Kunden können die Gebühren nach dem Abschnitt "Rechnung" organisiert werden. Weitere Informationen zur Verwendung von Rechnungs Abschnitten für Azure-Produkte finden Sie unter [Invoice Sections](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) in [Erste Schritte mit Ihrem Microsoft-Kundenvertrags-Abrechnungskonto](https://docs.microsoft.com/azure/billing/billing-mca-overview). In jedem Produktauftrag werden die Kosten nach Dienst Familie aufgeschlüsselt.

| Begriff |Beschreibung |
| --- | --- |
| VK-Preis | Der effektive VK-Preis des Diensts (in der Preis Währung), der zum Berechnen des Entgelts verwendet wird. Dieser Preis ist für ein Produkt, eine Dienst Familie, ein Messgerät und ein Angebot eindeutig. |
| Menge | Während des Abrechnungszeitraums erworbene oder konsumierte Menge |
| Gebühren/Guthaben | Nettobetrag der Gebühren nach Anwendung von Guthaben/Rückerstattungen |
| Azure-Guthaben | Die Anzahl der Azure Credits, die auf die Gebühren/Gutschriften angewendet werden. |
| Steuersatz | Steuersatz, je nach Land |
| Steuerbetrag | Steuersatz, der auf den Erwerb basierend auf dem Steuersatz angewendet wird |
| Gesamt | Der für den Kauf fällige Gesamtbetrag |

Die Details der Einzelposten variieren je nach dem Typ des Produkts, für das Sie aufgeladen haben. Für Azure-Produkte wird beispielsweise die Menge an angewendeten Azure-Gutschriften angezeigt. Auf Sitz basierten Produkten wird ein VK-Preis und eine Menge angezeigt. Die Rechnungsdetails zeigen die gekauften Produkte, den Rabatt oder Guthaben, die angewendet wurden, den Steuersatz und den Betrag sowie die Gesamtsumme der Posten.

    `Total = Charges - Azure Credit + Tax`

Der Gesamtbetrag, der für jede Dienst Familie fällig ist, wird berechnet, indem Azure Credits von Guthaben/Gebühren subtrahiert werden und Mehrwertsteuer hinzugefügt wird:

    `Total = Charges/Credits - Azure Credit + Tax`

Wenn auf Ihrer Rechnung Azure-Gebühren angezeigt werden, für die Sie weitere Informationen wünschen, lesen Sie [Überprüfen Ihrer Microsoft-Kundenvertrags Rechnung](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill).

## <a name="understand-the-last-invoice-page"></a>Grundlegendes zur letzten Rechnungsseite

### <a name="payment-instructions"></a>Zahlungsanweisungen

Unten auf der Rechnung finden Sie Anweisungen zum Bezahlen Ihrer Rechnung. Sie können per Draht, überprüfen oder Online bezahlen.

### <a name="publisher-information"></a>Herausgeberinformationen

Wenn Sie Drittanbieterdienste in Ihrer Rechnung haben, werden der Name und die Adresse jedes Herausgebers unten in Ihrer Rechnung aufgeführt.

## <a name="view-your-online-invoice"></a>Anzeigen Ihrer Online Rechnung

Rechnungen sind online verfügbar. Ein Link zu Ihrer Online Rechnung steht in Ihrer PDF-Rechnung und in einer e-Mail-Benachrichtigung zur Verfügung. Die Online Rechnung kann erweitert werden, damit Sie die Gebühren auf Ihrer Rechnung anzeigen und weitere Details zu den einzelnen Artikeln sehen können. Die Online Rechnung umfasst Folgendes:

- **Preise Details** &mdash; Weitere Informationen, einschließlich Details zu Rabatten und Produktpreisen.

- **Online Zahlung** &mdash; Sie können festlegen, dass eine Zahlung online über die Rechnung erfolgt.

- **Azure-Kostenverwaltung** &mdash; Für Azure-Kunden enthalten Online Rechnungen einen Link zu Azure Cost Management.

### <a name="to-view-your-online-invoice"></a>So zeigen Sie Ihre Online Rechnung an

1. Gehen Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Rechnungen & Zahlungen</a>.

2. Zum Herunterladen der PDF-Version Ihrer Rechnung wählen Sie **Download Rechnung PDF** in der Zeile für die Rechnung aus, die Sie anzeigen möchten.

3. Um Ihre Online Rechnung anzuzeigen, wählen Sie eine Rechnung aus der Liste aus. Sie können die PDF-Datei auch auf der Seite mit den Rechnungsdetails herunterladen.

## <a name="invoice-faq"></a>Häufig gestellte Fragen zu Rechnungen

### <a name="when-is-my-invoice-available"></a>Wann ist meine Rechnung verfügbar?

Einige Rechnungen werden innerhalb von 24 Stunden nach dem Kauf generiert. Andere Rechnungen werden am Ende des Abrechnungszeitraums generiert und enthalten alle Elemente aus dieser Periode.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Wie bezahle ich den fälligen Betrag auf meiner Rechnung?

Die Zahlungsanweisungen hängen von Ihrer Zahlungsmethode ab und werden unten in der Rechnung PDF angegeben. Wenn es sich bei Ihrer Zahlungsmethode um eine Kreditkarte handelt, wird Sie automatisch innerhalb von 10 Tagen nach Rechnungsdatum aufgeladen. Wenn Ihre Zahlungsmethode durch Scheck oder Überweisung erfolgt, lesen Sie die Informationen unter **Zahlungsanweisungen** in der PDF-Datei.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Was ist der Unterschied zwischen "verkauft an" und "Rechnung an"-Adressen?

- **Verkauft an:** Die für die Zahlung verantwortliche und auf der Rechnung angegebene juristische Person. Die hier angegebene Adresse wird verwendet, um ihren Steuersatz zu ermitteln, es sei denn, Sie möchten während des Kaufs eine Alternative Versandadresse angeben. Weitere Informationen finden Sie unter [Steuerinformationen](tax-information.md).
- **Rechnung an:** Die Adresse, an die die physische Rechnung gesendet wird (falls zutreffend). Es kann mehrere **Rechnungs** Adressen pro juristische Person geben, aber nur eine **Rechnung an die** Adresse pro Abrechnungsprofil.

### <a name="what-are-billed-amount-and-amount-due"></a>Was sind "Rechnungsbetrag" und "Fälliger Betrag?"

- **Abgerechneter Betrag:** Der Gesamtbetrag für den Kauf, den Sie getätigt haben.
- **Fälliger Betrag:** Der verbleibende Saldo für das, was Sie Schulden.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Was ist der Unterschied zwischen "Service period" und "Abrechnungszeitraum?"

- **Dienst Zeitraum:** Der Zeitraum, in dem Sie für die Nutzung des Diensts in Rechnung gestellt werden.
- **Abrechnungszeitraum:** Der Zeitraum seit dem letzten Rechnungsdatum.

### <a name="how-do-i-view-and-print-my-bill"></a>Wie kann ich meine Rechnung anzeigen und drucken?

1. Wählen Sie **auf der**  >  Seite<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Rechnungen & Zahlungen</a> einen Rechnungsdatums Bereich aus.
2. Wenn Sie eine PDF-Kopie der Rechnung drucken oder speichern möchten, wählen Sie **Download Rechnung PDF**aus, und Drucken Sie die PDF-Datei.

Weitere Informationen finden Sie unter [Anzeigen Ihrer Rechnung oder Rechnung](view-your-bill-or-invoice.md).

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Warum wird die Azure-Vorauszahlung nicht als Zahlungsmethode angezeigt?

Azure Prepayment steht als Zahlungsmethode nur für berechtigte Azure-Produkte und-Dienste zur Verfügung.

## <a name="need-help-contact-support"></a>Benötigen Sie Hilfe? Kontaktieren Sie den Support.

Wenn Sie Fragen haben oder Hilfe zu ihren Azure-Gutschriften benötigen, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Erstellen Sie eine Supportanfrage mit Azure-Unterstützung</a>.

Wenn Sie Fragen haben oder Hilfe zu Ihrer Rechnung im Microsoft 365 Admin Center benötigen, [wenden Sie sich an den Support für Business-Produkte](../../admin/contact-support-for-business-products.md).