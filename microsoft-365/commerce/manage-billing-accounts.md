---
title: Abrechnungskonten verwalten
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Erfahren Sie mehr über Abrechnungskonten und deren Verwaltung.
ms.openlocfilehash: 2382396c348fab0b24a269e9678193041ac2c19e
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032633"
---
# <a name="manage-billing-accounts"></a>Abrechnungskonten verwalten

Ein Abrechnungskonto wird erstellt, wenn Sie sich registrieren, um die Produkte von Microsoft zu testen oder zu kaufen. Sie verwenden Ihr Abrechnungskonto, um Ihre Kontoeinstellungen, Rechnungen, Zahlungsmethoden und Einkäufe zu verwalten. Sie können auf mehrere Abrechnungskonten zugreifen. Beispielsweise haben Sie sich direkt für Microsoft 365 angemeldet, oder Sie haben Zugriff auf die Konzernvertrag, den Microsoft Product &-Servicevertrag oder den Microsoft-Kundenvertrag. Für jedes dieser Szenarien verfügen Sie über ein separates Abrechnungskonto.

Das Microsoft 365 Admin Center unterstützt derzeit die folgenden Abrechnungskonten:

- Microsoft Online Services: Dieses Abrechnungskonto wird erstellt, wenn Sie sich direkt für ein Microsoft 365-Abonnement registrieren.
- Microsoft Products & Services Agreement (MPSA)-Programm: Dieses Abrechnungskonto wird erstellt, wenn Ihre Organisation einen Volumenlizenzvertrag für mpSA zum Kauf von Software und Onlinediensten signiert.
- Microsoft-Kundenvertrag: Dieses Abrechnungskonto wird erstellt, wenn Ihre Organisation mit einem Microsoft-Vertreter, einem autorisierten Partner oder unabhängigen Einkäufen zusammenarbeiten.

Die <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Seite "Abrechnungskonten"</a> bietet eine Ansicht Ihrer kommerziellen Konten bei Microsoft. Standardmäßig verfügt Ihre Organisation über mindestens ein Abrechnungskonto, das einem Vertrag zugeordnet ist, der entweder zum Zeitpunkt eines direkten Kaufs oder über eine Volumenlizenzvereinbarung akzeptiert wird.

## <a name="understand-billing-account-details"></a>Verstehen der Details des Abrechnungskontos

Oben auf der Seite **"Abrechnungskontendetails"** befindet sich Ihr Kontoprofil und enthält rechtliche und steuerliche Informationen zu Ihrer Organisation. Sie können Ihr Profil aktualisieren, um Ihre rechtliche Adresse und Telefonnummer zu ändern. Dieses Konto ist die juristische Person, die für die Produkte, die Sie kaufen, bezahlt.

In der folgenden Tabelle sind die wichtigen Begriffe aufgeführt, die auf der Detailseite für **Abrechnungskonten** angezeigt werden.

| Feldname | Beschreibung |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Verkaufte Adresse | Die für die Zahlung zuständige und auf der Rechnung identifizierte Juristische Person. Die hier zur Verfügung gestellte Adresse wird verwendet, um Ihre Steuerrate zu bestimmen, außer wenn Sie während dem Einkauf eine alternative Lieferadresse angegeben haben. Weitere Informationen finden Sie unter [Steuerinformationen](billing-and-payments/tax-information.md). |
| Segment | Ein schreibgeschütztes Feld, das das Geschäftssegment Ihrer Organisation (Commercial, Education, Government oder Non-Profit) identifiziert. |
| Kontostatus | Ein schreibgeschütztes Feld, das den Status Ihres kommerziellen Kontos bei Microsoft angibt. |
| Steuer-ID | Wenn Sie sich außerhalb der VEREINIGTEn Staaten befinden, müssen Sie eine Mehrwertsteuer oder eine lokale Entsprechung bereitstellen. Weitere Informationen finden Sie unter [Steuerinformationen](billing-and-payments/tax-information.md). |
| Vereinbarung | Wenn ein Abrechnungskonto entweder durch einen direkten Kauf oder eine Volumenlizenzvereinbarung erstellt wird, akzeptiert oder signiert ein Signament für die Organisation einen Vertrag, der die Bedingungen des Kontos & beschreibt. Falls zutreffend, wird in dieser Ansicht ein Vertragsverlauf aufgeführt. Wenn Sie aktualisierte Bedingungen akzeptieren müssen, wird ein Link für die **Genehmigungsvereinbarung** angezeigt. |
| Abrechnungsprofile | Ein Abrechnungsprofil definiert die Eigenschaften Ihrer Rechnung, z. B. wer die Rechnung erhält, wie die Rechnung zugestellt wird, Zahlungsbedingungen und eine Bestellungsnummer. Um die Abrechnung in Ihrer Organisation zu verteilen, können Sie mehrere Abrechnungsprofile erstellen und das entsprechende Abrechnungsprofil zum Zeitpunkt des Kaufs identifizieren. Weitere Informationen zu Abrechnungsprofilen und wie Sie diese verwenden können, um flexiblere Abrechnungsoptionen für Ihre Organisation zu erstellen, finden Sie unter Verwalten [von Abrechnungsprofilen.](billing-and-payments/manage-billing-profiles.md) |

> [!NOTE]
> Wenn Sie den Namen oder die Adresse des Verkauften  ändern möchten, [](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) aber keinen Link zum Bearbeiten sehen, müssen Sie sich an den Support wenden, um ihn zu ändern.  Anforderungen für eine Änderung des Namens **"Verkauft** an" erfordern eine Bonitätsprüfung. Wenn Sie sich an den Support wenden, können Sie eines der folgenden Dokumente für Microsoft freigeben: 
>
> - Vom Behörden ausgestelltes Dokument oder Registrierungsschreiben
> - Drucken aus der Registrierung des lokalen Unternehmens
>
> Der Support kann bei Namens- und Adressänderungen hilfreich sein, wenn sich nur der Kundenname ändert, die Entität jedoch unverändert bleibt. Die bereitgestellte Dokumentation sollte deutlich zeigen, dass nur der Name der Entität geändert wurde. Wenn die Änderung das Ergebnis einer Transaktion ist, einschließlich des Verkaufs von Geschäftsgeschäften, einer Änderung der Kontrollen oder einer Abspaltung oder "Ausgliederung" eines Kundenpartners, wenden Sie sich bitte an Ihren Microsoft-Verkäufer.

## <a name="shipping-addresses"></a>Versandadressen

In diesem Abschnitt werden die Versandadressen aufgeführt, die Ihrem Abrechnungskonto zugeordnet sind. Wenn Sie einen Kauf tätigen, können Sie diese Adresse verwenden, um zu ermitteln, wo Ihr Kauf versendet oder verwendet wird. Die Versandadresse kann bearbeitet werden. Sie können eine Versandadresse hinzufügen oder die vorhandene Adresse aktualisieren. Diese Adresse wird verwendet, um den Steuersatz für Ihren Kauf zu bestimmen.

## <a name="understand-access-to-billing-accounts"></a>Verstehen des Zugriffs auf Abrechnungskonten

Sie können anderen Personen über Rollen und Berechtigungen Zugriff auf das Abrechnungskonto im Microsoft 365 Admin Center gewähren. Nur ein Abrechnungskontobesitzer kann Zugriff auf ein Abrechnungskonto gewähren. Sie können Benutzern eine der folgenden Rollen zuweisen:

- **Abrechnungskontobesitzer** &mdash; Kann Berechtigungen zuweisen, Konten bearbeiten, Vereinbarungen unterzeichnen und Konten anzeigen.
- **Mitwirkender des Abrechnungskontos** &mdash; Kann Konten bearbeiten, Vereinbarungen unterzeichnen und Konten anzeigen.
- **Abrechnungskontoleser** &mdash; Kann Konten anzeigen.

> [!Note]
> Abrechnungskontorollen gelten nur für Abrechnungskonten und nicht für andere Microsoft 365 Admin Center-Szenarien.

## <a name="related-articles"></a>Verwandte Artikel

[Steuerinformationen](billing-and-payments/tax-information.md)

[Verwalten von Abrechnungsprofilen](billing-and-payments/manage-billing-profiles.md)
