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
ms.openlocfilehash: 3c99f3f22fb0eb13c4f9cab06a4037fe057b6fb4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638207"
---
# <a name="manage-billing-accounts"></a>Abrechnungskonten verwalten

Wenn Sie sich für das Testen oder kaufen von Microsoft-Produkten registrieren, wird ein Abrechnungskonto erstellt. Sie verwenden Ihr Abrechnungskonto, um Ihre Kontoeinstellungen, Rechnungen, Zahlungsmethoden und Käufe zu verwalten. Sie können Zugriff auf mehrere Abrechnungskonten haben. Beispielsweise haben Sie sich für Microsoft 365 direkt angemeldet oder Sie haben Zugriff auf die Enterprise-Vereinbarung des Unternehmens, die Microsoft Product & Services-Vereinbarung oder den Microsoft-Kundenvertrag. Für jedes dieser Szenarien wäre ein separates Abrechnungskonto vorhanden.

Das Microsoft 365 Admin Center unterstützt derzeit die folgenden Arten von Abrechnungskonten:

- Microsoft Online Services-Programm: dieses Abrechnungskonto wird erstellt, wenn Sie sich direkt für ein Microsoft 365-Abonnement registrieren.
- Microsoft Products & Service Agreement (MPSA)-Programm: dieses Abrechnungskonto wird erstellt, wenn Ihre Organisation einen MPSA-Volumenlizenz Vertrag zum Erwerb von Software und Onlinediensten signiert.
- Microsoft-Kundenvereinbarung: dieses Abrechnungskonto wird erstellt, wenn Ihre Organisation mit einem Microsoft-Mitarbeiter, einem autorisierten Partner oder einem Einkauf unabhängig arbeitet.

Auf der Seite " <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Abrechnungskonten</a> " finden Sie eine Übersicht über Ihre geschäftlichen Konten bei Microsoft. Standardmäßig verfügt Ihre Organisation über mindestens ein Abrechnungskonto, das einer Vereinbarung zugeordnet ist, die entweder zum Zeitpunkt des direkten Erwerbs oder über eine Volumenlizenzvereinbarung angenommen wird.

## <a name="understand-billing-account-details"></a>Grundlegendes zu Abrechnungskonto Details

Oben auf der Detailseite für **Abrechnungskonten** ist Ihr Kontoprofil und enthält rechtliche und steuerliche Informationen zu Ihrer Organisation. Sie können Ihr Profil aktualisieren, um ihre rechtliche Adresse und Telefonnummer zu ändern. Dieses Konto ist die juristische Person, die die Produkte bezahlt, die Sie kaufen.

In der folgenden Tabelle sind die wichtigen Begriffe aufgeführt, die auf der Detailseite für **Abrechnungskonten** angezeigt werden.

| Feldname | Beschreibung |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Verkaufte Adresse | Die für die Zahlung verantwortliche und auf der Rechnung angegebene juristische Person. Die hier angegebene Adresse wird verwendet, um ihren Steuersatz zu ermitteln, es sei denn, Sie möchten während des Kaufs eine Alternative Versandadresse angeben. Weitere Informationen finden Sie unter [Steuerinformationen](billing-and-payments/tax-information.md). |
| Segment | Ein schreibgeschütztes Feld, das das Geschäftssegment Ihrer Organisation (kommerziell, Bildung, Verwaltung oder gemeinnützig) identifiziert. |
| Kontostatus | Ein schreibgeschütztes Feld, das den Status Ihres kommerziellen Kontos bei Microsoft angibt. |
| Steuer-ID | Wenn Sie sich außerhalb der USA befinden, müssen Sie eine Mehrwertsteuer oder eine lokale Entsprechung angeben. Weitere Informationen finden Sie unter [Steuerinformationen](billing-and-payments/tax-information.md). |
| Vertrag | Wenn ein Abrechnungskonto entweder über eine Direktbestellung oder eine Volumenlizenzvereinbarung erstellt wird, akzeptiert ein Unterzeichner für die Organisation eine Vereinbarung, die die Bedingungen & Bedingungen des Kontos umreißt. Wenn zutreffend, wird in dieser Ansicht eine Vereinbarungs Historie aufgeführt. Wenn Sie aktualisierte Bedingungen akzeptieren müssen, wird ein Link zur **Genehmigungs Vereinbarung** angezeigt. |
| Abrechnungsprofile | Ein Abrechnungsprofil definiert die Eigenschaften Ihrer Rechnung, zum Beispiel wer die Rechnung erhält, wie die Rechnung zugestellt wird, Zahlungsbedingungen und eine Bestellnummer. Um die Abrechnung in Ihrer Organisation zu verteilen, können Sie mehrere Abrechnungsprofile erstellen und das entsprechende Abrechnungsprofil zum Zeitpunkt des Erwerbs ermitteln. Weitere Informationen zu Abrechnungs Profilen und deren Verwendung zum Erstellen flexiblerer Abrechnungsoptionen für Ihre Organisation finden Sie unter [Verwalten von Abrechnungs Profilen](billing-and-payments/manage-billing-profiles.md). |

> [!NOTE]
> Wenn Sie den **verkauften** Namen oder die Adresse ändern möchten, jedoch keinen **Bearbeitungs** Link sehen, müssen Sie sich an den  [Support wenden](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) , um ihn zu ändern. Für Anforderungen für eine Änderung **an einem verkauften** Namen ist eine Bonitätsprüfung erforderlich. Wenn Sie sich an den Support wenden, müssen Sie eines der folgenden Dokumente vorbereiten:
>
> - Externes Ankündigungs Dokument, das eine Änderung des Firmennamens oder der Unternehmensstruktur angibt
> - Behördlich ausgestelltes Dokument oder Registrierungs schreiben
> - Drucken aus der Registrierung des lokalen Unternehmens
>
> Die Unterstützung kann bei Namen-und Adressänderungen helfen, wenn sich nur der Kundenname ändert, aber die Entität bleibt unverändert. In der bereitgestellten Dokumentation sollte eindeutig angegeben werden, dass nur der Name der Entität geändert wurde. Wenn die Änderung im Zusammenhang mit einer Transaktion wie einem Geschäftsverkauf oder einer Veräußerung oder einem "Spin-off" eines Kunden Partners besteht, wenden Sie sich an Ihren Microsoft-Verkäufer.

## <a name="shipping-addresses"></a>Versandadressen

In diesem Abschnitt werden die Versandadressen aufgelistet, die Ihrem Abrechnungskonto zugeordnet sind. Wenn Sie einen Einkauf tätigen, können Sie diese Adresse verwenden, um zu ermitteln, wo Ihr Kauf ausgeliefert oder verwendet wird. Die Versandadresse kann bearbeitet werden. Sie können eine Lieferadresse hinzufügen oder die vorhandene Adresse aktualisieren. Diese Adresse wird verwendet, um den Steuersatz für Ihren Einkauf zu ermitteln.

## <a name="understand-access-to-billing-accounts"></a>Grundlegendes zum Zugriff auf Abrechnungskonten

Sie können anderen Benutzern den Zugriff auf das Abrechnungskonto im Microsoft 365 Admin Center über Rollen und Berechtigungen ermöglichen. Nur ein Abrechnungskonto Besitzer kann Zugriff auf ein Abrechnungskonto gewähren. Sie können Benutzern eine der folgenden Rollen zuweisen:

- **Abrechnungskonto Besitzer** &mdash; Kann Berechtigungen zuweisen, Konten bearbeiten, Vereinbarungen abschliessen und Konten anzeigen.
- **Abrechnungskonto Mitwirkender** &mdash; Kann Konten bearbeiten, Vereinbarungen Signieren und Konten anzeigen.
- **Konto Leser** &mdash; für Abrechnungskonten Kann Konten anzeigen.

> [!Note]
> Abrechnungskonto Rollen gelten nur für Abrechnungskonten und gelten nicht für andere Microsoft 365 Admin Center-Szenarien.

## <a name="related-articles"></a>Verwandte Artikel

[Steuerinformationen](billing-and-payments/tax-information.md)

[Verwalten von Abrechnungsprofilen](billing-and-payments/manage-billing-profiles.md)