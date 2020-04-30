---
title: Informationen zu Ihrer Rechnung
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
ms.custom: ''
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie Ihre Rechnung für Microsoft Business-Produkte lesen und verstehen.
keywords: Abrechnungskonten, Organisationsinformationen, Rechnungen
ms.openlocfilehash: 7b16af7c6ef39743aa8d0a4e927786f64f47c4cd
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942877"
---
# <a name="understand-your-invoice"></a>Informationen zu Ihrer Rechnung

Die Rechnung enthält eine Zusammenfassung ihrer Gebühren und Anweisungen zur Zahlung. Sie können [Ihre Online Rechnung](#view-your-online-invoice) im Microsoft 365 Admin Center anzeigen. Sie können es auch im Portable Document Format (. pdf) herunterladen, um es per e-Mail zu senden.

Wenn Sie nur ein Microsoft 365-Abonnement haben, finden Sie weitere Informationen Untergrund [Legendes zu Ihrer Rechnung für Microsoft 365 for Business](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Grundlegendes zum Rechnungskopf

Oben auf der ersten Seite wird angegeben, wer für die Zahlung verantwortlich ist, wo die Rechnung gesendet wird, und eine Zusammenfassung der Gebühren.

| Begriff | Beschreibung |
| --- | --- |
| Verkauft an |Das Abrechnungskonto, das den Namen und die Adresse der für die Zahlung verantwortlichen juristischen Person identifiziert. Diese Informationen können auf der Seite " <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Abrechnungskonten</a> " verwaltet werden, auf der Sie die Kontovereinbarung finden und die Rollen und Berechtigungen verwalten können. |
| Rechnung an |Gibt an, wer die Rechnung erhält. Diese Informationen können auf der Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Abrechnungsprofile</a> verwaltet werden. Das Abrechnungsprofil wird auch auf der Seite "Online Rechnung" im Abschnitt " **Rechnungszusammenfassung** " angezeigt. Weitere Informationen zu Abrechnungs Profilen und deren Verwendung zum Erstellen flexiblerer Abrechnungsoptionen für Ihre Organisation finden Sie unter [Manage Billing Profiles](manage-billing-profiles.md). |
| Abrechnungsprofil |Der Name des Abrechnungs Profils, das zum Definieren von Rechnungs Eigenschaften verwendet wird, wie Bill to, PO-Nummer und Zahlungsbedingungen. Diese Informationen können auf der Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Abrechnungsprofile</a> verwaltet werden. Weitere Informationen zu Abrechnungs Profilen und deren Verwendung zum Erstellen flexiblerer Abrechnungsoptionen für Ihre Organisation finden Sie unter [Manage Billing Profiles](manage-billing-profiles.md). |
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

Die Details der Einzelposten variieren je nach dem Typ des Produkts, für das Sie aufgeladen haben. Für Azure-Produkte wird beispielsweise die Menge an angewendeten Azure-Gutschriften angezeigt. Auf Sitz basierten Produkten wird ein VK-Preis und eine Menge angezeigt. In den Rechnungsdetails werden die gekauften Produkte, der Rabatt oder die Gutschriften, die angewendet wurden, der Steuersatz und der Betrag sowie die Gesamtsumme der Posten umrissen.

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

- **Online Zahlung** &mdash; Sie können wählen, eine Zahlung online von der Rechnung aus zu tätigen.

- **Azure Cost Management** &mdash; für Azure-Kunden, Online-Rechnungen enthalten einen Link zu Azure Cost Management.

### <a name="to-view-your-online-invoice"></a>So zeigen Sie Ihre Online Rechnung an

1. Gehen Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Rechnungen & Zahlungen</a>.

2. Zum Herunterladen der PDF-Version Ihrer Rechnung wählen Sie **Download Rechnung PDF** in der Zeile für die Rechnung aus, die Sie anzeigen möchten.

3. Um Ihre Online Rechnung anzuzeigen, wählen Sie eine Rechnung aus der Liste aus. Sie können die PDF-Datei auch auf der Seite mit den Rechnungsdetails herunterladen.

## <a name="need-help-contact-support"></a>Benötigen Sie Hilfe? Kontaktieren Sie den Support.

Wenn Sie Fragen haben oder Hilfe zu ihren Azure-Gutschriften benötigen, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Erstellen Sie eine Supportanfrage mit Azure-Unterstützung</a>.

Wenn Sie Fragen haben oder Hilfe zu Ihrer Rechnung im Microsoft 365 Admin Center benötigen, [wenden Sie sich an den Support für Business-Produkte](../../admin/contact-support-for-business-products.md).
