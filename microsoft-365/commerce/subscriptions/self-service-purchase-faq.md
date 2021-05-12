---
title: Häufig gestellte Fragen zum Self-Service-Kauf
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
- commerce_ssp
search.appverid:
- MET150
description: Hier finden Sie Antworten auf häufig gestellte Fragen zu Self-Service-Käufen.
ms.date: 09/15/2020
ms.openlocfilehash: 964eca8e94f64fd2f212745abfff0cf25d45bfca
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333194"
---
# <a name="self-service-purchase-faq"></a>Häufig gestellte Fragen zum Self-Service-Kauf

Der Self-Service-Kauf bietet Benutzern die Möglichkeit, neue Technologien auszuprobieren und Lösungen zu entwickeln, die letztendlich von ihren größeren Organisationen profitieren. Zentrale Beschaffung und IT-Teams haben Sichtbarkeit für alle Benutzer, die Self-Service-Einkaufslösungen über das <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center kaufen</a>und bereitstellen. Administratoren können den Self-Service-Kauf auf Produktbasis über PowerShell deaktivieren. Weitere Informationen finden Sie unter [Use AllowSelfServicePurchase for the MS Commerce PowerShell module](allowselfservicepurchase-powershell.md).

Der Self-Service-Kauf ist für Power Platform (Power BI, Power Apps und Power Automate), Project und Visio verfügbar.

> [!NOTE]
> Der Self-Service-Kauf ist in Indien oder für Regierungs- oder Bildungskunden nicht verfügbar. Project und Visio stehen in Brasilien und der Demokratischen Republik Kongo nicht zum Self-Service-Kauf zur Verfügung.

## <a name="making-a-self-service-purchase"></a>Tätigen eines Self-Service-Kaufs

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Wie macht ein Kunde einen Self-Service-Kauf?

Kunden können einen Self-Service-Kauf online über die Produktwebsites oder über In-App-Kaufaufforderungen tätigen. Kunden werden zuerst aufgefordert, eine E-Mail-Adresse ein eingeben, um sicherzustellen, dass sie ein Benutzer in einem vorhandenen Azure Active Directory (AD)-Mandanten sind. Als Nächstes werden sie zur Anmeldung mit ihren Azure AD-Anmeldeinformationen geleitet. Nach der Anmeldung wird der Kunde aufgefordert, auszuwählen, wie viele Abonnements er kaufen möchte, und eine Kreditkartenzahlung zu leisten. Nach Abschluss des Kaufs können sie mit der Nutzung ihres Abonnements beginnen. Der Käufer hat Zugriff auf eine eingeschränkte Ansicht des <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Centers,</a> in dem er anderen Personen in seiner Organisation Lizenzen für das Produkt zuweisen kann.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Welche Zahlungsoptionen gibt es für Self-Service-Käufe?

Derzeit ist die Kreditkarte die einzige verfügbare Zahlungsmethode. Die Zahlung über die Rechnungsstellung wird nicht unterstützt.

### <a name="who-can-buy-through-self-service-purchase"></a>Wer kann über den Self-Service-Kauf kaufen?

Jeder Benutzer mit einem Nicht-Gast-Benutzerkonto in einem verwalteten Azure AD-Mandanten kann einen Self-Service-Kauf tätigen. Der Self-Service-Kauf ist für Mandanten, die Regierung oder Bildungseinrichtungen sind, nicht verfügbar. Wenn dies für Ihre Organisation gilt, ist keine zusätzliche Aktion erforderlich, um den Self-Service-Kauf zu steuern.

Benutzern in Organisationen oder Märkten, die nicht für den Self-Service-Kauf berechtigt sind, wird eine Meldung angezeigt, in der sie aufgefordert werden, sich an ihren IT-Administrator zu wenden.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Können Gastbenutzer über den Self-Service-Kauf kaufen?

Nein, Gastbenutzer können keinen Self-Service-Kauf in einem Mandanten abschließen, in dem sie Gast sind.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Können Benutzer, die von einem lokalen Active Directory synchronisiert wurden, über den Self-Service-Kauf kaufen?

Wenn ein Benutzer über ein aktives Benutzerkonto in einem berechtigten Azure AD-Mandanten verfügt, kann er einen Self-Service-Kauf abschließen.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Wem können Self-Service-Käufer Lizenzen zuweisen?

Self-Service-Käufer können Benutzern im gleichen Azure AD-Mandanten nur Lizenzen zuweisen. Der Käufer hat Zugriff auf eine eingeschränkte Ansicht des <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Centers</a> zum Zuweisen von Lizenzen. Käufer können den Produkten, die sie über den Self-Service-Kauf erworben haben, Lizenzen zuweisen und diese Lizenzen nur Benutzern im gleichen Azure AD-Mandanten zuweisen.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Wo sieht und verwaltet der Self-Service-Käufer seine Einkäufe?

Self-Service-Käufer können ihre Einkäufe in der eingeschränkten Ansicht des <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Centers verwalten.</a> Käufer können immer über die Kachel **Admin** im App-Startfeld in allen Microsoft 365- und Dynamics-Online-Apps zum Admin Center wechseln. Käufer können die getätigten Einkäufe anzeigen, zusätzliche Abonnements für denselben Dienst erwerben und Lizenzen für diese Abonnements anderen Benutzern in ihrer Organisation zuweisen. Darüber hinaus können Käufer ihre Rechnung anzeigen und bezahlen, ihre Zahlungsmethode aktualisieren und ihr Abonnement kündigen.

## <a name="pricing"></a>Preise

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Wie sind die Preise für Self-Service-Käufe?

Preise für die einzelnen Produkte für den Self-Service-Kauf sind auf der Microsoft-Website verfügbar. Preise werden auch als Teil der Bezahlerfahrung angezeigt, wenn Benutzer einen Self-Service-Kauf tätigen. Diese Preise können sich von den Preisen unterscheiden, die eine Organisation zahlt, wenn sie zentrale Einkäufe tätigen oder preise, die über einen Partner angeboten werden.

### <a name="who-is-responsible-for-payment"></a>Wer ist für die Zahlung verantwortlich?

Die Person, die das Abonnement über den Self-Service-Kauf kauft, ist die Person, die abgerechnet wird und die für die Zahlung auf der Grundlage der Bedingungen und Preise des Kaufs verantwortlich ist.

## <a name="admin-capabilities"></a>Administratorfunktionen

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Welche Funktionen hat ein Administrator für Self-Service-Käufe?

Administratoren können alle in ihrer Organisation getätigten Self-Service-Käufe im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center anzeigen.</a> Sie können das Produkt, den Käufernamen, die erworbenen Abonnements, das Ablaufdatum, den Bestellverlauf, den Einkaufspreis und die zugewiesenen Benutzer für jeden Self-Service-Kauf anzeigen. Im Power Platform Admin Center können Administratoren auch die Kapazität von Self-Service-Käufen anzeigen. Wenn dies für ihre Organisation erforderlich ist, können Administratoren den Self-Service-Kauf auf Produktbasis über PowerShell deaktivieren. Administratoren verfügen über dieselben Datenverwaltungs- und Zugriffsrichtlinien über Produkte, die über den Self-Service-Kauf oder zentral erworben wurden.

Administratoren können auch steuern, ob Benutzer in ihrer Organisation Self-Service-Käufe tätigen können. Weitere Informationen finden Sie unter [Use AllowSelfServicePurchase for the MS Commerce PowerShell module](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Wie respektiert Microsoft die Datensteuerung und Compliance, indem der Self-Service-Kauf aktiviert wird?

Administratoren behalten die Kontrolle darüber, welche Dienste und Produkte in ihrem Mandanten verfügbar sind, basierend auf ihren Anforderungen an Datenkontrolle und Compliance. Alle Datenverwaltungs- und Zugriffsrichtlinien, die Ihre Organisation aktiviert hat, gelten für verfügbare self-service erworbene Dienste.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Wem sind die produktdaten, die aus Self-Service-Käufen erstellt wurden?

Daten, die aus Produkten erstellt werden, die über den Self-Service-Kauf erworben wurden, sind im Besitz der Organisation und werden von der Organisation gesteuert.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Wie zentralisiert ich die Einkäufe, die über den Self-Service-Kauf getätigt werden?

Administratoren können vorhandene Lizenzen zuweisen oder zusätzliche Abonnements von Self-Service-Einkaufsprodukten über vorhandene Vereinbarungen und Preise für Benutzer erwerben, die Self-Service-Käufen zugewiesen sind. Nach dem Zuweisen dieser zentral erworbenen Lizenzen können Administratoren dann anfordern, dass die Käufer ihre vorhandenen Abonnements kündigen.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Wo sieht der Administrator Self-Service-Käufe?

Globale Und Abrechnungsadministratoren können Abonnements anzeigen, die über den Self-Service-Kauf in **Abrechnung** Ihre Produkte  >   im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center erworben wurden.</a> Sie können die Produktliste so filtern, dass nur die Abonnements angezeigt werden, die über die zentrale Beschaffung erworben wurden, oder abonnements, die über den Self-Service-Kauf erworben wurden.

Administratoren können das Produkt, den Käufernamen, das erworbene Abonnement, das Ablaufdatum, den Bestellverlauf, den Einkaufspreis und die zugewiesenen Benutzer sehen.

## <a name="support-and-training"></a>Support und Schulung

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Wird erwartet, dass die IT-Abteilungen oder Partner von Kunden Produkte unterstützen, die über den Self-Service-Kauf erworben wurden?

Es wird nicht erwartet, dass IT-Abteilungen und Partner Unterstützung für Produkte bereitstellen, die über den Self-Service-Kauf erworben wurden. Microsoft bietet Standardunterstützung für Self-Service-Käufer.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Wenn ein Self-Service-Käufer Support anruft, verwendet dies dann den Premier-Support-Vorfall des Kunden?

Self-Service-Käufer verwenden die Premier Supportvorfälle eines Kunden nicht, um Support für ihre Self-Service-Käufe zu erhalten.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Wie wird erwartet, dass Benutzer Schulungen zu den Produkten erhalten, die sie über den Self-Service-Kauf kaufen?

Auf den Produktwebsites werden umfangreiche Schulungen für Benutzer bereitgestellt. Die Produkte verfügen über geführtes Lernen, Dokumentation, Beispiele und starke Communitys, um Antworten und Tipps direkt von anderen Benutzern zu erhalten.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Was geschieht mit einem Self-Service-Kauf, wenn ein Benutzer die Organisation verlässt?

Wenn die Person, die das Self-Service-Kaufprodukt ursprünglich erworben hat, die Organisation verlässt, können gültige Benutzer das Produkt für die Dauer des Abonnements weiterhin vollständig nutzen. Das Abonnement bleibt aktiv, bis der Käufer es direkt gekündigt hat oder ein Administrator die Kündigung des Abonnements über den Kundensupport anfordert. Administratoren können auch benutzer des gekündigten Abonnements eine zentral erworbene Lizenz zuweisen.

## <a name="partners"></a>Partner

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Welche Rolle spielen die Partner von Microsoft bei Self-Service-Käufen?

Partner mit delegierten Verwaltungsrechten können Self-Service-Käufe im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>sehen, genau wie ein Administrator. Partner können eine Organisation unterstützen, die Produkte zentralisieren möchte, die über Self-Service-Käufe erworben wurden. Darüber hinaus können Partner Lösungen anbieten, um die Funktionen eines Self-Service-Kaufs zu erweitern.