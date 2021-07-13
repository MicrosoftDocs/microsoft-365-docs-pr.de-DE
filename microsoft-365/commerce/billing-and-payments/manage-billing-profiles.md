---
title: Informationen zu Abrechnungsprofilen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- AdminTemplateSet
search.appverid: MET150
description: Erfahren Sie, wie Abrechnungsprofile Rechnungen unterstützen.
ms.date: 04/02/2021
ms.openlocfilehash: ecea09a9ceea12fa92b92eac3e5a7595b2510042
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394629"
---
# <a name="understand-billing-profiles"></a>Informationen zu Abrechnungsprofilen

Ein Abrechnungsprofil enthält eine Zahlungsmethode, Rechnungsinformationen und andere Rechnungseinstellungen, z. B. Bestellnummer und E-Mail-Rechnungseinstellung. Sie verwenden ein Abrechnungsprofil, um die Produkte zu bezahlen, die Sie von Microsoft kaufen. Ein Abrechnungsprofil wird automatisch erstellt, wenn ein Benutzer einen Self-Service-Kauf vornimmt. Jedes Abrechnungsprofil wird separat in Rechnung gestellte.

> [!NOTE]
>
> Abrechnungsprofile sind für Kunden, die Produkte und Dienste über Microsoft.com oder auf der Seite **"Dienste kaufen"** des Microsoft 365 Admin Center kaufen, nicht verfügbar.

## <a name="what-are-billing-profile-roles"></a>Was sind Die Rollen des Abrechnungsprofils?

Rollen in Abrechnungsprofilen verfügen über Berechtigungen zum Steuern von Einkäufen sowie zum Anzeigen und Verwalten von Rechnungen. Weisen Sie diese Rollen Benutzern zu, die Rechnungen nachverfolgen, organisieren und bezahlen. Beispielsweise Mitglieder des Beschaffungsteams in Ihrer Organisation.

| Rolle                         | Beschreibung                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| Besitzer des Abrechnungsprofils        | Verwalten aller Elemente für ein Abrechnungsprofil                                          |
| Abrechnungsprofilmitwirkender  | Verwalten aller Elemente mit Ausnahme von Berechtigungen in einem Abrechnungsprofil                        |
| Leser des Abrechnungsprofils       | Schreibgeschützte Ansicht aller Elemente in einem Abrechnungsprofil                                |
| Rechnungsmanager              | Anzeigen und Bezahlen von Rechnungen und eine schreibgeschützte Ansicht aller Elemente in einem Abrechnungsprofil  |

## <a name="view-my-billing-profiles"></a>Anzeigen meiner Abrechnungsprofile

> [!NOTE]
>
> Wenn Sie diese Schritte ausführen und die Liste der Abrechnungsprofile leer ist, bedeutet dies, dass Sie kein Abrechnungsprofil haben und dieses Feature nicht verwenden können.

1. Gehen Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Rechnungen & Zahlungen</a>.
2. Wählen Sie die Registerkarte **"Abrechnungsprofil"** und dann ein Abrechnungsprofil aus der Liste aus.

Jedes Abrechnungsprofil enthält die folgenden Informationen:

- **Name und Status** &ndash; des Abrechnungsprofils Der eindeutige Name des Abrechnungsprofils und ob das Abrechnungsprofil aktiv oder für den Kauf deaktiviert ist.
- **Rechnungseinstellungen** &ndash; Währung basierend auf dem Land des Abrechnungskontos, Informationen zur Rechnungshäufigkeit und zum Datum, der Option zum Empfangen von Rechnungen als E-Mail-Anlagen und einem optionalen Feld für die Bestellnummer
- **Zahlungsmethoden** &ndash; Zeigt die primäre und ggf. sicherungsweise Zahlungsmethode für das Profil an.
- **Abrechnungskonto** &ndash; Name des Abrechnungskontos, mit dem das Profil verknüpft ist. Weitere Informationen zu Abrechnungskonten finden Sie unter ["Grundlegendes zu Abrechnungskonten".](../manage-billing-accounts.md)
- **Kontaktinformationen** &ndash; Rechnungsadresse, Kontaktname und E-Mail-Adresse
- Rollen des **Abrechnungsprofils** &ndash; Eine Liste der Personen, denen eine der Rollen für das Abrechnungsprofil zugewiesen ist, um Aufgaben für dieses Profil zu erledigen. Bezahlen Sie beispielsweise Rechnungen, fügen Sie eine Auftragsnummer hinzu, oder ersetzen Sie die Zahlungsmethode, die zum Tätigen von Einkäufen verwendet wird.

> [!NOTE]
>
> Sie können Benutzern in Ihrer Organisation nur Abrechnungsprofilrollen zuweisen.

## <a name="need-help-contact-support"></a>Benötigen Sie Hilfe? Support kontaktieren

Wenn Sie Fragen haben oder Hilfe zu Ihren Azure-Gebühren benötigen, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">erstellen Sie eine Supportanfrage mit Azure-Support.</a>

Wenn Sie Fragen haben oder Hilfe zu Ihrem Abrechnungsprofil in Microsoft 365 Admin Center benötigen, [wenden Sie sich an den Support.](../../business-video/get-help-support.md)

## <a name="related-content"></a>Verwandte Inhalte

[So zahlen Sie für Ihr Abonnement mit einem Abrechnungsprofil](pay-for-subscription-billing-profile.md) (Artikel)\
[Grundlegendes zu Abrechnungskonten](../manage-billing-accounts.md) (Artikel)\
[Verwalten von Zahlungsmethoden](manage-payment-methods.md) (Artikel)
