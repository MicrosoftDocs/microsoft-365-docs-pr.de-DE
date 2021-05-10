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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- PPM_jmueller
ms.reviewer: tugu
search.appverid:
- MET150
description: Erfahren Sie mehr über Abrechnungskonten und deren Verwaltung.
ms.date: 03/17/2021
ms.openlocfilehash: ecac005b8b49739cb74efc4ca2fae44667f37bad
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293643"
---
# <a name="manage-billing-accounts"></a>Abrechnungskonten verwalten

Ein Abrechnungskonto wird erstellt, wenn Sie sich registrieren, um Microsoft-Produkte zu testen oder zu kaufen. Sie verwenden Ihr Abrechnungskonto, um Ihre Kontoeinstellungen, Rechnungen, Zahlungsmethoden und Einkäufe zu verwalten. Sie können auf mehrere Abrechnungskonten zugreifen. Beispielsweise haben Sie sich direkt für Microsoft 365 angemeldet, oder Sie haben Zugriff auf die Enterprise Agreement, Microsoft Product & Services Agreement oder Microsoft Customer Agreement. Für jedes dieser Szenarien verfügen Sie über ein separates Abrechnungskonto.

Das Microsoft 365 Admin Center unterstützt derzeit die folgenden Abrechnungskonten:

- Microsoft Online Services: Dieses Abrechnungskonto wird erstellt, wenn Sie sich direkt für ein Microsoft 365 registrieren.
- Microsoft Products & Services Agreement (MPSA)-Programm: Dieses Abrechnungskonto wird erstellt, wenn Ihre Organisation einen MpSA-Volumenlizenzvertrag zum Kauf von Software und Onlinediensten unterzeichnet.
- Microsoft-Kundenvertrag: Dieses Abrechnungskonto wird erstellt, wenn Ihre Organisation mit einem Microsoft-Vertreter, einem autorisierten Partner oder unabhängigen Einkäufen arbeitet.

Die <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Seite Abrechnungskonten</a> bietet eine Ansicht Ihrer kommerziellen Konten bei Microsoft. Standardmäßig verfügt Ihre Organisation über mindestens ein Abrechnungskonto, das einem Vertrag zugeordnet ist, der entweder zum Zeitpunkt eines direkten Kaufs oder über eine Volumenlizenzierungsvereinbarung akzeptiert wird.

## <a name="understand-billing-account-details"></a>Verstehen von Abrechnungskontodetails

Der obere Rand der Detailseite **Abrechnungskonten** ist Ihr Kontoprofil und enthält rechtliche und steuerliche Informationen zu Ihrer Organisation. Sie können Ihr Profil aktualisieren, um Ihre gesetzliche Adresse und Telefonnummer zu ändern. Dieses Konto ist die juristische Person, die für die produkte bezahlt wird, die Sie kaufen.

In der folgenden Tabelle sind die wichtigen Begriffe aufgeführt, die auf der Detailseite **Abrechnungskonten** angezeigt werden.

| Feldname | Beschreibung |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Verkaufte Adresse | Die für die Zahlung zuständige und auf der Rechnung identifizierte juristische Person. Die hier zur Verfügung gestellte Adresse wird verwendet, um Ihre Steuerrate zu bestimmen, außer wenn Sie während dem Einkauf eine alternative Lieferadresse angegeben haben. Weitere Informationen finden Sie unter [Steuerinformationen](billing-and-payments/tax-information.md). |
| Segment | Ein schreibgeschütztes Feld, das das Geschäftssegment Ihrer Organisation (Commercial, Education, Government oder Non-Profit) identifiziert. |
| Kontostatus | Ein schreibgeschütztes Feld, das den Status Ihres kommerziellen Kontos bei Microsoft angibt. |
| Steuer-ID | Wenn Sie sich außerhalb der Vereinigten Staaten befinden, müssen Sie eine Mehrwertsteuer oder ein lokales Äquivalent bereitstellen. Weitere Informationen finden Sie unter [Steuerinformationen](billing-and-payments/tax-information.md). |
| Vereinbarung | Wenn ein Abrechnungskonto entweder über einen direkten Kauf oder eine Volumenlizenzierungsvereinbarung erstellt wird, akzeptiert oder signiert ein Unterzeichnender für die Organisation einen Vertrag, der die Bedingungen & des Kontos umreißt. Falls zutreffend, wird in dieser Ansicht ein Vertragsverlauf aufgeführt. Wenn Sie aktualisierte Bedingungen akzeptieren müssen, wird ein Link für **Genehmigungsvereinbarung** angezeigt. |
| Abrechnungsprofile | Ein Abrechnungsprofil definiert Eigenschaften Ihrer Rechnung, z. B. wer die Rechnung empfängt, wie die Rechnung zugestellt wird, Zahlungsbedingungen und eine Postfachnummer. Zum Verteilen der Abrechnung in Ihrer Organisation können Sie mehrere Abrechnungsprofile erstellen und das entsprechende Abrechnungsprofil zum Zeitpunkt des Kaufs identifizieren. Weitere Informationen zu Abrechnungsprofilen und deren Verwendung zum Erstellen flexiblerer Abrechnungsoptionen für Ihre Organisation finden Sie unter Verstehen von [Abrechnungsprofilen.](billing-and-payments/manage-billing-profiles.md) |

> [!NOTE]
> Wenn Sie den **Sold-to-Namen** oder die Adresse ändern  müssen, aber [](../business-video/get-help-support.md) keinen Link Bearbeiten sehen, müssen Sie sich an den Support wenden, um ihn zu ändern. Anforderungen für eine **Namensänderung** für Verkaufte Namen erfordern eine Kreditwürdigkeitsprüfung. Füllen [Sie dieses Formular](https://www.microsoft.com/download/details.aspx?id=102732)aus, und teilen Sie eines der folgenden Dokumente mit Microsoft, wenn Sie sich an den Support wenden:
>
> - Vom Staat ausgestelltes Dokument oder Registrierungsschreiben
> - Ausdrucken der Registrierung des lokalen Unternehmens
>
> Der Support kann bei Namens- und Adressänderungen helfen, bei denen sich nur der Name des Kunden ändert, die Entität jedoch unverändert bleibt. Die bereitgestellte Dokumentation sollte deutlich zeigen, dass sich nur der Name der Entität geändert hat. Wenn die Änderung das Ergebnis einer Transaktion ist, einschließlich des Verkaufs von Unternehmen, einer Änderung von Steuerelementen oder einer Abspaltung oder "Ausgliederung" eines Kundenpartners, wenden Sie sich bitte an Ihren Microsoft Seller.

## <a name="shipping-addresses"></a>Versandadressen

In diesem Abschnitt werden die Versandadressen aufgeführt, die Ihrem Abrechnungskonto zugeordnet sind. Wenn Sie einen Kauf tätigen, können Sie diese Adresse verwenden, um zu ermitteln, wo Ihr Kauf versendet oder verwendet wird. Die Versandadresse kann bearbeitet werden. Sie können eine Versandadresse hinzufügen oder die vorhandene Adresse aktualisieren. Diese Adresse wird verwendet, um den Steuersatz für Ihren Kauf zu bestimmen.

## <a name="understand-access-to-billing-accounts"></a>Verstehen des Zugriffs auf Abrechnungskonten

Sie können anderen Benutzern zugriff auf das Abrechnungskonto im Microsoft 365 Admin Center über Rollen und Berechtigungen gewähren. Nur ein Abrechnungskontobesitzer kann Zugriff auf ein Abrechnungskonto gewähren. Sie können Benutzern eine der folgenden Rollen zuweisen:

- **Besitzer des Abrechnungskontos** &mdash; Kann Berechtigungen zuweisen, Konten bearbeiten, Vereinbarungen signieren und Konten anzeigen.
- **Mitwirkender des Abrechnungskontos** &mdash; Kann Konten bearbeiten, Vereinbarungen unterzeichnen und Konten anzeigen.
- **Abrechnungskontoleser** &mdash; Kann Konten anzeigen.

> [!Note]
> Abrechnungskontorollen gelten nur für Abrechnungskonten und nicht für andere Microsoft 365 Admin Center-Szenarien.

## <a name="related-content"></a>Verwandte Inhalte

[Steuerinformationen](billing-and-payments/tax-information.md) (Artikel) \
[Verstehen von Abrechnungsprofilen](billing-and-payments/manage-billing-profiles.md) (Artikel)