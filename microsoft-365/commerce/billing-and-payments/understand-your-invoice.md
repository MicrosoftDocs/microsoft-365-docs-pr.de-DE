---
title: Erläuterungen zu Ihrer Rechnung
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre Rechnung für Microsoft Business-Produkte lesen und verstehen können.
keywords: Abrechnungskonten, Unternehmensinformationen, Rechnungen
ms.date: 05/04/2021
ms.openlocfilehash: 64ccf82549bb85ba803693eb3e7c15939940d45c
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635846"
---
# <a name="understand-your-bill-or-invoice"></a>Erläuterungen zu Ihrer Rechnung

Die Rechnung enthält eine Zusammenfassung Ihrer Belastungen und die Zahlungsanweisungen. Sie können im Microsoft 365 Admin Center [Ihre Online-Rechnung anzeigen](#view-your-online-invoice). Sie können Sie auch im PDF-Format (Portable Document Format) herunterladen, um sie mit E-Mail zu versenden.

So zeigen Sie Ihre Rechnung an und drucken sie:

1. Wählen Sie auf der Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Rechnungen und Zahlungen</a>einen Datumsbereich aus. 
2. Wenn Sie eine PDF-Kopie der Rechnung drucken oder speichern möchten, wählen Sie **PDF-Rechnung herunterladen** aus, und drucken Sie dann das PDF.

Weitere Informationen hierzu finden Sie unter [Anzeigen Ihrer Rechnung](view-your-bill-or-invoice.md).

Wenn Sie nur ein Microsoft 365-Abonnement haben, lesen Sie [Erläuterungen zu Ihrer Rechnung für Microsoft 365 für Unternehmen](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Erläuterungen zum Rechnungskopf

Der obere Teil der ersten Seite gibt an, wer für die Zahlung verantwortlich ist, wohin die Rechnung gesendet wird, sowie eine Zusammenfassung der Belastungen.

| Ausdruck | Beschreibung |
| --- | --- |
| Verkauft an: |Das Abrechnungskonto, das den Namen und die Adresse der juristischen Person angibt, welche für die Zahlung verantwortlich ist. Diese Informationen können auf der Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Abrechnungskonto</a> verwaltet werden, wo Sie auch die Kontovereinbarung finden und Rollen und Berechtigungen verwalten können. |
| Rechnungsempfänger |Gibt an, wer die Rechnung erhält. Diese Information kann auf der Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Abrechnungsprofile</a> verwaltet werden. Das Abrechnungsprofil wird auch auf der Online-Rechnungsseite im Abschnitt **Rechnungszusammenfassung** angezeigt. Um mehr über Abrechnungskonten zu erfahren und wie Sie diese verwenden können, um flexiblere Abrechnungsoptionen für Ihre Organisation zu erstellen, gehen Sie zu [Abrechnungsprofile verwalten](manage-billing-profiles.md). |
| Abrechnungsprofil |Der Name des Abrechnungsprofils, das verwendet wird, um Rechnungseigenschaften wie **Rechnungsempfänger**, **Bestellnummer** und Zahlungsbedingungen zu definieren. Diese Information kann auf der Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Abrechnungsprofile</a> verwaltet werden. Weiter Informationen über Abrechnungskonten und wie Sie diese verwenden können, um flexiblere Abrechnungsoptionen für Ihre Organisation zu erstellen, finden Sie unter [Abrechnungsprofile verwalten](manage-billing-profiles.md). |
| Rechnungsnummer |Eine eindeutige, von Microsoft generierte Rechnungsnummer für Nachverfolgungszwecke. |
| Rechnungsdatum |Das Datum, an welchem die Rechnung erstellt wird, normalerweise 5–12 Tage nach dem Ende des Abrechnungszyklus. Sie können Ihr Rechnungsdatum auf der Seite mit den Details des Abrechnungsprofils überprüfen. Belastungen, die zwischen dem Ende der Abrechnungsperiode und dem Rechnungsdatum auftreten, werden in der Rechnung des nächsten Monates aufgeführt, da sie bereits in der nächsten Abrechnungsperiode liegen. Der Abrechnungszeitraum für jede Rechnung ist auf der PDF-Rechnung über der **Abrechnungszusammenfassung** aufgeführt.|
| Zahlungsbedingungen |So bezahlen Sie für Ihre Microsoft-Rechnung. *Netto 30 Tage*: Dies bedeutet, dass Sie die Rechnung gemäß den Anweisungen auf Ihrer Rechnung innerhalb von 30 Tagen nach dem Rechnungsdatum bezahlen. |

## <a name="understand-the-billing-summary"></a>Erläuterungen zur Abrechnungszusammenfassung

Die **Abrechnungszusammenfassung** zeigt die Zusammenfassung der Belastungen seit der letzten Abrechnungsperiode an, allfällige angewendete Gutschriften, Steuern und den fälligen Gesamtbetrag.

| Ausdruck | Beschreibung |
| --- | --- |
| Belastungen|Gesamtzahl der in dieser Abrechnungsperiode gekauften Produkte und deren zugehörige Belastungen und Steuern. Einkäufe sind zusammengefasst, um eine übersichtliche Ansicht Ihrer Abrechnung zu ermöglichen. |
| Gutschriften |Gutschriften, die Sie aus Rücksendungen erhalten haben |
| Angewendete Azure-Gutschriften |Ihre Azure-Gutschriften, die in jeder Abrechnungsperiode automatisch gegen Azure-Belastungen angewendet werden. Wenn Sie keine Azure-Gutschriften haben, dann ist dieses Feld ausgeblendet. Weiter Informationen über Azure-Gutschriften finden Sie unter [Verfolgen des Azure-Guthabens der Microsoft-Kundenvereinbarung](/azure/billing/billing-mca-check-azure-credits-balance). |
| Zwischensumme |Der fällige Betrag vor Steuern |
| Steuern |Die Art und der Betrag der Steuern, die Sie bezahlen müssen, abhängig vom Land in Ihrem Abrechnungsprofil. Wenn Sie keine Steuern bezahlen müssen, dann wird die Steuer auf Ihrer Rechnung nicht angezeigt. |

### <a name="understand-your-charges"></a>Erläuterung zu Ihren Belastungen

Die Seite mit den Belastungen zeigt die Kosten, aufgeschlüsselt nach Produkt. Für Azure-Kunden können die Belastungen nach Rechnungsabschnitt gegliedert sein. Weiter Informationen darüber, wie Rechnungsabschnitte mit Azure-Produkten verwendet werden, finden Sie unter [Rechnungsabschnitte](/azure/billing/billing-mca-overview#invoice-sections) im Bereich [Erste Schritte mit Ihrem Abrechnungskonto der Microsoft-Kundenvereinbarung](/azure/billing/billing-mca-overview). Innerhalb jeder Produktbestellung sind die Kosten nach Dienstfamilie aufgeschlüsselt.

| Ausdruck |Beschreibung |
| --- | --- |
| Einzelpreis | Der effektive Stückpreis des Dienstes (in Abrechnungswährung), der zur Berechnung der Belastung verwendet wird. Dieser Preis ist einzigartig für ein Produkt, eine Servicefamilie, eine Einheit und ein Angebot. |
| Menge | Während des Abrechnungszeitraums gekaufte oder verbrauchte Menge |
| Belastungen/Gutschriften | Nettobetrag der Belastungen nach Anwendung von Gutschriften/Rücksendungen |
| Azure-Gutschrift | Der Betrag von Azure-Gutschriften, der auf Belastungen/Gutschriften angewendet wurde |
| Steuersatz | Steuersatz, abhängig vom Land |
| Steuerbetrag | Steuerbetrag, der für den Kauf belastet wird, basierend auf dem Steuersatz |
| Gesamt | Der fällige Gesamtbetrag für den Kauf |

Die Details zu den Positionen variieren je nach Art des Produkts, für das Sie belastet werden. Für Azure-Produkte wird beispielsweise der angewendete Azure-Gutschriftsbetrag angezeigt. Arbeitsplatz-basierte Produkte zeigen den Einheitspreis und die Anzahl. Die Rechnungsdetails zeigen die gekauften Produkte, die angewendeten Rabatte oder Gutschriften, den Steuersatz und -Betrag und den Gesamtbetrag der Positionen.

> Gesamt = Belastungen – Azure-Gutschrift + Steuern

Der fällige Gesamtbetrag für jede Dienstfamilie wird berechnet, indem die Azure-Gutschriften von den Gutschriften/Belastungen subtrahiert und die Steuern dazu addiert werden:

> Gesamt = Belastungen/Gutschriften – Azure-Gutschrift + Steuern

Wenn Sie Azure-Belastungen auf Ihrer Rechnung finden, zu denen Sie mehr Details erfahren möchten, dann lesen Sie [Die Rechnung Ihrer Microsoft-Kundenvereinbarung überprüfen](/azure/cost-management-billing/understand/review-customer-agreement-bill).

## <a name="understand-the-last-invoice-page"></a>Erläuterungen zur letzten Seite der Rechnung

### <a name="payment-instructions"></a>Zahlungsanweisungen

Am Ende der Rechnung finden Sie die Anweisungen, wie Sie Ihre Rechnung bezahlen sollten. Sie können per Überweisung, Scheck oder online bezahlen.

### <a name="publisher-information"></a>Herausgeberinformationen

Wenn Sie Dienstleistungen von Dritten in Ihrer Rechnung haben, dann finden Sie die Namen und Adressen aller Herausgeber am Ende der Rechnung aufgeführt.

## <a name="view-your-online-invoice"></a>Rechnung online anzeigen

Rechnungen sind online verfügbar. Ein Link zu Ihrer Online-Rechnung ist auf der PDF-Rechnung verfügbar und aus einer E-Mail-Benachrichtigung. Die Online-Rechnung ist erweiterbar und so können Sie die Belastungen auf Ihrer Rechnung und weitere Details zu jeder Position anzeigen. Die Online-Rechnung beinhaltet:

- **Abrechnungsdetails**&mdash;Zusätzliche Informationen inklusive Details über Rabatte und Produktpreise.
- **Online-Bezahlung**&mdash;Sie können aus der Rechnung heraus eine Online-Zahlung machen.
- **Azure-Kostenverwaltung**&mdash; Online-Rechnungen von Azure-Kunden erhalten einen Link zur Azure-Kostenverwaltung.

### <a name="to-view-your-online-invoice"></a>Um Ihre Rechnung online anzuzeigen

1. Gehen Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Rechnungen & Zahlungen</a>.
2. Um die PDF-Version Ihrer Rechnung herunterzuladen, wählen Sie **PDF-Rechnung herunterladen** aus in der Zeile für die Rechnung, die Sie sehen wollen.
3. Um Ihre Online-Rechnung anzusehen, wählen Sie eine Rechnung aus der Liste aus. Sie können das PDF auch über die Detailseite der Rechnung herunterladen.

## <a name="invoice-faq"></a>Rechnung – FAQ

### <a name="when-is-my-invoice-available"></a>Wann ist meine Rechnung verfügbar?

Einige Rechnungen werden innerhalb von 24 Stunden nach dem Kauf generiert. Andere Rechnungen werden am Ende der Abrechnungsperiode generiert und enthalten alle Elemente dieser Periode.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Wie bezahle ich den fälligen Betrag meiner Rechnung?

Die Zahlungsanweisungen hängen von Ihrer Zahlungsmethode ab und werden am Ende der PDF-Rechnung aufgezeigt. Wenn Sie eine Kreditkarte als Zahlungsmethode benutzen, dann wird diese automatisch innerhalb von 10 Tagen nach dem Rechnungsdatum belastet. Wenn Sie Scheck oder Überweisung als Zahlungsmethode benutzen, finden Sie weiter Informationen im Abschnitt **Zahlungsanweisungen** auf dem PDF.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Was ist der Unterschied zwischen „Verkauft an“ und „Rechnung an“?

- **Verkauft an:** Die juristische Person verantwortlich für die Zahlung, und auf der Rechnung angegeben. Die hier zur Verfügung gestellte Adresse wird verwendet, um Ihre Steuerrate zu bestimmen, außer wenn Sie während dem Einkauf eine alternative Lieferadresse angegeben haben. Weitere Informationen finden Sie unter [Steuerinformationen](tax-information.md).
- **Rechnung an:** Die Adresse, an welche die physische Rechnung (falls zutreffend) gesendet wird. Es kann für eine juristische Person mehrere **Rechnung an**-Adressen geben, aber nur eine **Rechnung an**-Adresse pro Abrechnungsprofil.

### <a name="what-are-billed-amount-and-amount-due"></a>Was sind „Abgerechneter Betrag“ und „Fälliger Betrag“?

- **Abgerechneter Betrag:** Der Gesamtbetrag der Käufe, die Sie getätigt haben.
- **Fälliger Betrag:** Der verbleibende Saldo, den Sie schuldig sind.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Was ist der Unterschied zwischen „Dienstzeitraum“ und „Abrechnungszeitraum“?

- **Dienstzeitraum:** Der Zeitraum, für den Ihnen die Nutzung des Diensts in Rechnung gestellt wird.
- **Abrechnungszeitraum:** Der Zeitraum seit dem letzten Rechnungsdatum.

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Warum sehe ich Azure-Vorauszahlungen nicht als Zahlungsmethode?

Azure Prepayment ist nur für berechtigte Azure-Produkte und -Dienste als Zahlungsmethode verfügbar.

## <a name="need-help-contact-support"></a>Benötigen Sie Hilfe? Support kontaktieren

Wenn Sie Fragen haben oder Hilfe mit Ihren Azure-Gutschriften benötigen, dann <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">erstellen Sie beim Azure-Support eine Support-Anforderung</a>.

Wenn Sie Fragen haben oder Hilfe mit Ihrer Rechnung im Microsoft 365 Admin Center benötigen, dann [kontaktieren Sie den Support für Unternehmensprodukte](../../business-video/get-help-support.md).

## <a name="related-content"></a>Verwandte Inhalte

[Verstehen Ihrer Rechnung oder Rechnung für Microsoft 365 Business](understand-your-invoice2.md) (Artikel)\
[Nachverfolgen von Microsoft Customer Agreement Azure Credit Balance](/azure/billing/billing-mca-check-azure-credits-balance) (Artikel)\
[Überprüfen Ihrer Microsoft Customer Agreement Rechnung](/azure/cost-management-billing/understand/review-customer-agreement-bill) (Artikel)\
[Erste Schritte mit Ihrem Abrechnungskonto](/azure/billing/billing-mca-overview) für Microsoft Customer Agreement (Artikel)
