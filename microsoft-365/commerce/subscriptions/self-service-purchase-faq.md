---
title: FAQ zum Self-Service-Kauf
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
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: Hier finden Sie Antworten auf häufig gestellte Fragen zu Self-Service-Käufen.
ms.date: 09/15/2020
ms.openlocfilehash: 81143dfe3794bc4f42bea879905bf08750f498b4
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816925"
---
# <a name="self-service-purchase-faq"></a>FAQ zum Self-Service-Kauf

Mit Self-Service Purchase können Benutzer neue Technologien ausprobieren und Lösungen entwickeln, die letztlich ihren größeren Organisationen zugute kommen. Zentrale Beschaffung und IT-Teams haben eine Sichtbarkeit für alle Benutzer, die Self-Service-Kauf Lösungen über das <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>kaufen und bereitstellen. Administratoren können Self-Service-Einkauf pro Produkt über PowerShell deaktivieren. Weitere Informationen finden Sie unter [Verwenden von AllowSelfServicePurchase für das MSCommerce-PowerShell-Modul](allowselfservicepurchase-powershell.md).

Self-Service Purchase steht für Power Platform (Power BI, Power apps und Power Automation), Project und Visio zur Verfügung.

> [!NOTE]
> Self-Service-Erwerb ist in Indien oder für Regierungs-und Bildungskunden nicht verfügbar. Project und Visio stehen nicht für Self-Service-Käufe in Brasilien und der Demokratischen Republik Kongo zur Verfügung.

## <a name="making-a-self-service-purchase"></a>Erstellen eines Self-Service-Kaufs

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Wie macht ein Kunde einen Self-Service-Kauf?

Kunden können einen Self-Service-Kauf online über die Produkt Websites oder über in-App-Kauf Ansagen tätigen. Kunden werden zunächst aufgefordert, eine e-Mail-Adresse einzugeben, um sicherzustellen, dass Sie ein Benutzer in einem vorhandenen Azure-Active Directory (AD)-Mandanten sind. Als nächstes werden Sie zur Anmeldung mit ihren Azure AD Anmeldeinformationen umgeleitet. Nachdem Sie sich angemeldet haben, wird der Kunde aufgefordert auszuwählen, wie viele Abonnements er kaufen möchte, und Kreditkartenzahlungen bereitzustellen. Wenn der Kauf abgeschlossen ist, können Sie mit der Verwendung Ihres Abonnements beginnen. Der Käufer hat Zugriff auf eine beschränkte Ansicht des <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin Centers</a> , in der er anderen Personen in seiner Organisation Lizenzen für das Produkt zuweisen kann.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Was sind die Zahlungsoptionen für Self-Service-Käufe?

Derzeit ist Kreditkarte die einzige verfügbare Zahlungsmethode. Die Zahlung über die Fakturierung wird nicht unterstützt.

### <a name="who-can-buy-through-self-service-purchase"></a>Wer kann durch Self-Service-Erwerb kaufen?

Jeder Benutzer mit einem nicht-Gast-Benutzerkonto in einem verwalteten Azure AD Mandanten kann einen Self-Service-Kauf tätigen. Self-Service-Einkauf steht Mandanten, die Regierungs-oder Bildungseinrichtungen sind, nicht zur Verfügung. Wenn dies auf Ihre Organisation zutrifft, ist keine zusätzliche Aktion erforderlich, um Self-Service-Erwerb zu steuern.

Benutzer in Organisationen oder Märkten, die nicht für Self-Service-Käufe berechtigt sind, erhalten eine Meldung, in der Sie aufgefordert werden, Ihren IT-Administrator zu kontaktieren.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Können Gastbenutzer durch Self-Service-Erwerb kaufen?

Nein, Gastbenutzer können keinen Self-Service-Kauf in einem Mandanten abschließen, in dem Sie ein Gast sind.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Können Benutzer, die von einem lokalen Active Directory durch Self-Service Purchase kaufen, synchronisiert werden?

Wenn ein Benutzer ein aktives Benutzerkonto in einem berechtigten Azure AD Mandanten hat, kann er einen Self-Service-Kauf abschließen.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Wem können Self-Service-Käufer Lizenzen zuweisen?

Self-Service-Käufer können Benutzern nur Lizenzen in demselben Azure AD Mandanten zuweisen. Der Käufer hat Zugriff auf eine beschränkte Ansicht des <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin Centers</a> , um Lizenzen zuzuweisen. Käufer können Lizenzen für diese Produkte zuweisen, die Sie über Self-Service Purchase erworben haben, und können diese Lizenzen nur Benutzern im selben Azure AD Mandanten zuweisen.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Wo sieht und verwaltet der Self-Service-Käufer seine Einkäufe?

Self-Service-Käufer können Ihre Einkäufe in der begrenzten Ansicht des <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>verwalten. Käufer können immer das Admin Center von der **Administrator** Kachel im App-Startfeld erhalten, die in alle Microsoft 365-und Dynamics Online-Apps integriert ist. Käufer können die von Ihnen vorgenommenen Einkäufe anzeigen, zusätzliche Abonnements für denselben Dienst erwerben und anderen Benutzern in Ihrer Organisation Lizenzen für diese Abonnements zuweisen. Darüber hinaus können Käufer Ihre Rechnung anzeigen und bezahlen, Ihre Zahlungsmethode aktualisieren und Ihr Abonnement kündigen.

## <a name="pricing"></a>Preise

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Wie hoch sind die Preise für Self-Service-Käufe?

Die Preise für die einzelnen Produkte für Self-Service-Käufe stehen auf der Microsoft-Website zur Verfügung. Preise werden auch als Teil der Checkout-Erfahrung angezeigt, wenn Benutzer einen Self-Service-Einkauf tätigen. Diese Preise können von den Preisen abweichen, die eine Organisation zahlt, wenn zentrale Einkäufe oder Preise über einen Partner angeboten werden.

### <a name="who-is-responsible-for-payment"></a>Wer ist für die Zahlung verantwortlich?

Die Person, die das Abonnement über Self-Service Purchase kauft, ist die Person, die in Rechnung gestellt wird und die für die Zahlung verantwortlich ist, basierend auf den Bedingungen und Preisen des Kaufs.

## <a name="admin-capabilities"></a>Administratorfunktionen

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Welche Funktionen hat ein Administrator für Self-Service-Käufe?

Administratoren können alle Self-Service-Käufe anzeigen, die in Ihrer Organisation im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>vorgenommen wurden. Sie können das Produkt, den Käufer Namen, die erworbenen Abonnements, das Ablaufdatum, den Bestellverlauf, den Kaufpreis und die zugewiesenen Benutzer für jeden Self-Service-Kauf anzeigen. Im Power Platform Admin Center können Administratoren auch die Kapazität für Self-Service-Käufe anzeigen. Wenn es für Ihre Organisation erforderlich ist, können Administratoren Self-Service-Einkauf pro Produkt über PowerShell deaktivieren. Administratoren haben die gleiche Datenverwaltung und Zugriffsrichtlinien für Produkte, die über Self-Service Purchase oder zentral erworben wurden.

Administratoren können auch steuern, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können. Weitere Informationen finden Sie unter [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Wie respektiert Microsoft die Datensteuerung und Compliance, indem Self-Service-Käufe aktiviert werden?

Administratoren behalten die Kontrolle darüber, welche Dienste und Produkte in Ihrem Mandanten verfügbar sind, basierend auf den Anforderungen Ihrer Datensteuerung und Compliance. Alle Datenverwaltungsdienste und Zugriffsrichtlinien, die Ihre Organisation aktiviert hat, gelten für verfügbare Self-Service-bezogene Dienste.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Wem gehören die Produktdaten, die aus Self-Service-Käufen erstellt wurden?

Daten, die aus Produkten erstellt wurden, die über Self-Service Purchase erworben wurden, werden von der Organisation besessen und gesteuert.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Wie kann ich die durch Self-Service Purchase getätigten Käufe zentralisieren?

Administratoren können vorhandene Lizenzen zuweisen oder zusätzliche Abonnements von Self-Service-Kauf Produkten über vorhandene Vereinbarungen und Preise für Benutzer kaufen, die Self-Service-Käufen zugewiesen sind. Nach dem Zuweisen dieser zentral erworbenen Lizenzen können Administratoren dann anfordern, dass die Käufer Ihre vorhandenen Abonnements kündigen.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Wo sieht der Administrator Self-Service-Käufe?

Global-und Abrechnungs Administratoren können Abonnements, die im Self-Service-Kauf erworben wurden, bei der **Abrechnung**  >  **ihrer Produkte** im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>anzeigen. Sie können die Liste "Produkte" filtern, um nur die Abonnements anzuzeigen, die über die zentrale Beschaffung erworben wurden, oder um Abonnements einzuschließen, die über Self-Service Purchase erworben wurden.

Administratoren können das Produkt, den Käufer Namen, das erworbene Abonnement, das Ablaufdatum, den Bestellverlauf, den Kaufpreis und die zugewiesenen Benutzer sehen.

## <a name="support-and-training"></a>Unterstützung und Schulung

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Wird erwartet, dass kundeneigene IT-Abteilungen oder Partner Produkte unterstützen, die über Self-Service Purchase erworben wurden?

IT-Abteilungen und Partner werden nicht erwartet, dass Sie Unterstützung für Produkte bereitstellen, die über Self-Service Purchase erworben wurden. Microsoft bietet Standardunterstützung für Self-Service-Käufer.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Wenn ein Self-Service-Käufer Unterstützung anruft, verwendet dies die Premier-Supportvorfälle des Kunden?

Self-Service-Käufer verwenden nicht die Premier-Support-Vorfälle eines Kunden, um Unterstützung für Self-Service-Käufe zu erhalten.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Wie wird erwartet, dass Benutzerschulungen zu den Produkten erhalten, die Sie über Self-Service Purchase kaufen?

Eine umfangreiche Schulung für Benutzer finden Sie auf den Produkt Websites. Die Produkte haben geleitetes lernen, Dokumentation, Beispiele und starke Communities, um Antworten und Tipps direkt von anderen Benutzern zu erhalten.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Was geschieht mit einem Self-Service-Kauf, wenn ein Benutzer die Organisation verlässt?

Wenn die Person, die das Self-Service-Kauf Produkt ursprünglich erworben hat, die Organisation verlässt, haben gültige Benutzer weiterhin die volle Nutzung des Produkts für die Dauer des Abonnements. Das Abonnement bleibt aktiv, bis der Käufer es direkt storniert oder ein Administrator die Löschung des Abonnements über den Kundensupport anfordert. Administratoren können auch festlegen, dass Benutzern des abgebrochenen Abonnements eine zentral erworbene Lizenz zugewiesen wird.

## <a name="partners"></a>Partner

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Welche Rolle spielen die Partner von Microsoft bei Self-Service-Käufen?

Partner mit Delegierten Administratorrechten können Self-Service-Käufe im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>sehen, genau wie ein Administrator. Partner können zur Unterstützung einer Organisation beitragen, die Produkte zentralisieren möchte, die über Self-Service-Käufe erworben wurden. Darüber hinaus können Partnerlösungen anbieten, um die Funktionen eines Self-Service-Kaufs zu erweitern.