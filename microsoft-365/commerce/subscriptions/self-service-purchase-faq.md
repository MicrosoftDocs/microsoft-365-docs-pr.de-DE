---
title: FAQ zum Self-Service-Kauf
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: Hier finden Sie Antworten auf häufig gestellte Fragen zu Self-Service-Käufen.
ms.custom: aka.ms/self-service-purchase-faq
ms.openlocfilehash: c7f91b8067aac5baa3c792dac10c1fdadae55fa2
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046156"
---
# <a name="self-service-purchase-faq"></a>FAQ zum Self-Service-Kauf

> [!NOTE]
> Die Informationen in diesem Artikel gelten nur für Microsoft Power Platform-Abonnements (Power BI, Power apps und Power automatisieren).

Self-Service-Käufe sind jetzt für Power Platform in mehreren Ländern und Regionen verfügbar.

## <a name="general"></a>Allgemein

### <a name="what-changes-did-microsoft-announce-around-self-service-purchases-for-the-power-platform-products"></a>Welche Änderungen hat Microsoft rund um Self-Service Purchases für die Power Platform-Produkte angekündigt?

Am 19. November haben wir IT-Administratoren die Möglichkeit geboten, Self-Service-Einkauf auf Produktbasis über PowerShell zu deaktivieren. Informationen zur Verwendung finden Sie unter [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

Um mehr Zeit für die Vorbereitung dieser Änderung bereitzustellen, aktualisieren wir den Start von Self-Service-Kauf Funktionen für Power Platform-Produkte, um mit Power BI am 14. Januar für alle kommerziellen Cloud-Kunden zu beginnen.  

Ab dem 14. Januar 2020 werden Self-Service Purchase-, Subscription-und License Management-Funktionen für Power Platform-Produkte (Power BI, Power apps und Power Automation) für kommerzielle Cloud-Kunden in den Vereinigten Staaten verfügbar sein. Mit Self-Service Purchase können Benutzer neue Technologien ausprobieren und Lösungen entwickeln, die letztlich ihren größeren Organisationen zugute kommen. Diese Funktion steht derzeit nicht für Mandanten in den USA zur Verfügung, die zu diesem Zeitpunkt Regierungs-, gemeinnützige oder Bildungseinrichtungen sind. Zentrale Beschaffungs-und IT-Teams haben eine Sichtbarkeit für alle Benutzer, die Self-Service-Kauf Lösungen über das <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>kaufen und bereitstellen, und können Self-Service-Einkauf pro Produkt über PowerShell deaktivieren.

### <a name="why-is-microsoft-adding-a-self-service-purchase-option-for-the-power-platform-products"></a>Warum wird von Microsoft eine Self-Service-Kaufoption für die Produkte der Power Platform hinzugefügt?

In der heutigen Welt suchen Endbenutzer und Abteilungen zunehmend nach und kaufen Technologielösungen ein. Wir haben zahlreiche Anfragen von diesen Kunden erhalten, um Self-Service-Erwerb von Power Platform-Produkten zu ermöglichen. Wir reagieren auf diese Kundenanforderung und gleichzeitig die Anforderungen von IT-Administratoren, die häufig die Sichtbarkeit und Kontrolle verlieren, wenn Personen innerhalb Ihrer Organisation Lösungen von Drittanbietern ohne Ihr Wissen einführen. Mit der anstehenden Self-Service-Funktion für Power Platform-Produkte haben IT-Administratoren vollständige Sichtbarkeit für alle Self-Service-Käufe innerhalb Ihrer Organisation, und auf Organisationsebene festgelegte Daten Steuerungsrichtlinien werden für Abonnements, die über Self-Service erworben wurden, anfallen. Administratoren können auch vorhandene Lizenzen oder zusätzliche Abonnements von Power Platform-Produkten über vorhandene Vereinbarungen und Preise für Benutzer, die Self-Service-Käufen zugewiesen sind, zuweisen. Nach dem Zuweisen dieser zentral erworbenen Lizenzen können Administratoren dann anfordern, dass die Käufer Ihre vorhandenen Abonnements kündigen. Microsoft untersucht Möglichkeiten zur Vereinfachung und Rationalisierung dieses Prozesses für Administratoren in der Zukunft.

### <a name="which-power-platform-products-are-available-for-self-service-purchase"></a>Welche Power Platform-Produkte stehen für Self-Service-Käufe zur Verfügung?

Microsoft hat Self-Service-Kauf für Power-Plattform (Power BI, Power apps und Power Automation) an Kunden in den Vereinigten Staaten gestartet, wobei in den kommenden Monaten zusätzliche Märkte verfügbar werden. Diese Funktion steht derzeit nicht für Mandanten in den USA zur Verfügung, die zu diesem Zeitpunkt Regierungs-, gemeinnützige oder Bildungseinrichtungen sind.

### <a name="will-self-service-purchase-be-enabled-for-services-beyond-the-power-platform-products"></a>Kann Self-Service-Einkauf für Dienste außerhalb der Power Platform-Produkte aktiviert werden?

Zu diesem Zeitpunkt werden nur die Produkte der Power Platform-Produktfamilie über Self-Service-Käufe angeboten.

## <a name="making-a-self-service-purchase"></a>Erstellen eines Self-Service-Kaufs

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Wie macht ein Kunde einen Self-Service-Kauf?

Kunden können online einen Self-Service-Einkauf über die Websites von Microsoft Power BI, Power apps und Power automatisieren tätigen. Kunden werden zunächst aufgefordert, eine e-Mail-Adresse einzugeben, um sicherzustellen, dass Sie ein Benutzer in einem vorhandenen Azure-Active Directory (AD)-Mandanten sind. Anschließend werden Sie zur Anmeldung mit ihren Azure AD Anmeldeinformationen weitergeleitet. Nachdem Sie sich angemeldet haben, wird der Kunde aufgefordert auszuwählen, wie viele Abonnements er kaufen und Kreditkartenzahlungen bereitstellen soll. Wenn der Kauf abgeschlossen ist, können Sie mit der Verwendung des Abonnements beginnen. Der Käufer kann außerdem auf eine beschränkte Ansicht des <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin Centers</a> zugreifen, in der andere Personen in Ihrer Organisation die Verwendung des Produkts ermöglichen können.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Was sind die Zahlungsoptionen für Self-Service-Käufe?

Derzeit ist Kreditkarte die einzige verfügbare Zahlungsmethode. Die Zahlung über die Fakturierung wird nicht unterstützt.

### <a name="who-can-buy-through-self-service-purchase"></a>Wer kann durch Self-Service-Erwerb kaufen?

Jeder Benutzer mit einem nicht-Gast-Benutzerkonto in einem verwalteten Azure AD Mandanten kaufen kann. Diese Funktion steht derzeit nicht für Mandanten zur Verfügung, die Regierungs-, gemeinnützige oder Bildungseinrichtungen sind. Wenn dies auf Ihre Organisation zutrifft, ist zu diesem Zeitpunkt keine zusätzliche Aktion erforderlich, um den Self-Service-Kauf zu steuern.

Benutzer in Organisationen oder Märkten, für die kein Self-Service-Kauf berechtigt ist, erhalten eine Meldung, in der Sie aufgefordert werden, Ihren IT-Administrator so wie heute zu kontaktieren.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Können Gastbenutzer durch Self-Service-Erwerb kaufen?

Nein, Gastbenutzer können keinen Self-Service-Einkauf in einem Mandanten abschließen, in dem Sie ein Gast sind.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Können Benutzer, die von einem lokalen Active Directory durch Self-Service Purchase kaufen, synchronisiert werden?

Wenn ein Benutzer ein aktives Benutzerkonto in einem berechtigten Azure AD Mandanten hat, kann er einen Self-Service-Kauf abschließen.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Wem können Self-Service-Käufer Lizenzen zuweisen?

Self-Service-Käufer können Benutzern nur Lizenzen in demselben Azure AD Mandanten zuweisen. Der Käufer kann auf eine beschränkte Ansicht des <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a> zugreifen, um Lizenzen zuzuweisen. Sie verfügen nur über eine Sichtbarkeit und können Lizenzen für diese Produkte zuweisen, die Sie über Self-Service Purchase erworben haben, und diese Lizenzen werden nur Benutzern in demselben Azure AD Mandanten zugewiesen werden können.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Wo sieht und verwaltet der Self-Service-Käufer seine Einkäufe?

Self-Service-Käufer können Ihre Einkäufe in der begrenzten Ansicht des <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>verwalten. Käufer können immer das Admin Center von der **Administrator** Kachel im App-Startfeld erhalten, die in alle Microsoft 365-und Dynamics Online-Apps integriert ist. Sie können die getätigten Einkäufe anzeigen, zusätzliche Abonnements für denselben Dienst erwerben und anderen Benutzern in Ihrer Organisation Lizenzen für diese Abonnements zuweisen. Darüber hinaus können Käufer Ihre Rechnung anzeigen und bezahlen, Ihre Zahlungsmethode aktualisieren und Ihr Abonnement kündigen.

**Ansicht des begrenzten Microsoft 365 Admin Center für Self-Service-Käufer:**

![Screenshot des Microsoft 365 admin Centers.](../../media/MACBillingProductsServicesSelfServicePurchaseIW.png)

## <a name="pricing"></a>Preise

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Wie hoch sind die Preise für Self-Service-Käufe?

Die Preise für jedes der Power Platform-Produkte für Self-Service-Käufe werden auf der Microsoft-Website zur Verfügung gestellt und auch als Teil der Checkout-Erfahrung angezeigt, während Sie einen Self-Service-Einkauf tätigen. Diese Preise können von den Preisen abweichen, die eine Organisation zahlt, wenn zentrale Einkäufe oder Preise über einen Partner angeboten werden.

### <a name="who-is-responsible-for-payment"></a>Wer ist für die Zahlung verantwortlich?

Die Person, die das Abonnement über Self-Service Purchase kauft, wird in Rechnung gestellt und ist für die Zahlung basierend auf den Bedingungen und Preisen des Kaufs verantwortlich.

## <a name="admin-capabilities"></a>Administratorfunktionen

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Welche Funktionen hat ein Administrator für Self-Service-Käufe?

Administratoren können alle Self-Service-Käufe anzeigen, die in Ihrer Organisation im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>vorgenommen wurden. Sie können das Produkt, den Käufer Namen, die erworbenen Abonnements, das Ablaufdatum, den Bestellverlauf, den Kaufpreis und die zugewiesenen Benutzer für jeden Self-Service-Kauf anzeigen. Im Power Platform Admin Center können Administratoren auch die Kapazität für Self-Service-Käufe anzeigen. Wenn es für Ihre Organisation erforderlich ist, können Administratoren Self-Service-Einkauf pro Produkt über PowerShell deaktivieren. Administratoren haben die gleiche Datenverwaltung und Zugriffsrichtlinien für Produkte, die über Self-Service Purchase oder zentral erworben wurden.

Administratoren können auch steuern, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können. Weitere Informationen finden Sie unter [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Wie respektiert Microsoft die Datensteuerung und Compliance, indem Self-Service-Käufe aktiviert werden?

Administratoren behalten die Kontrolle darüber, welche Dienste und Produkte in Ihrem Mandanten basierend auf Ihren Anforderungen an die Datensteuerung und Compliance aktiviert werden. Darüber hinaus gelten alle Datenverwaltungsdienste und Zugriffsrichtlinien, die Ihre Organisation aktiviert hat, auf Self-Service-Dienste, die für aktivierte Dienste erworben werden.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Wem gehören die Produktdaten, die aus Self-Service-Käufen erstellt wurden?

Daten, die aus Produkten erstellt wurden, die über Self-Service Purchase erworben wurden, werden von der Organisation besessen und gesteuert.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Wie kann ich die durch Self-Service Purchase getätigten Käufe zentralisieren?

Administratoren können vorhandene Lizenzen zuweisen oder zusätzliche Abonnements von Power Platform-Produkten (Power BI, Power apps und Power Automation) über vorhandene Vereinbarungen und Preise für Benutzer erwerben, die Self-Service-Käufen zugewiesen sind. Nach dem Zuweisen dieser zentral erworbenen Lizenzen können Administratoren dann anfordern, dass die Käufer Ihre vorhandenen Abonnements kündigen. Microsoft untersucht Möglichkeiten zur Vereinfachung und Rationalisierung dieses Prozesses für Administratoren in der Zukunft.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Wo sieht der Administrator Self-Service-Käufe?

Global-und Abrechnungs Administratoren können Abonnements, die im Self-Service-Kauf erworben wurden, bei der **Abrechnung** > **ihrer Produkte** im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a> zusammen mit allen anderen Abonnements anzeigen, die über die zentrale Beschaffung erworben wurden. Sie können die Liste nur auf die Abonnements filtern, die über die zentrale Beschaffung erworben wurden, oder auch Abonnements, die über Self-Service Purchase erworben wurden.

Administratoren können das Produkt, den Käufer Namen, das erworbene Abonnement, das Ablaufdatum, den Bestellverlauf, den Kaufpreis und die zugewiesenen Benutzer sehen.

## <a name="support-and-training"></a>Unterstützung und Schulung

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Wird erwartet, dass kundeneigene IT-Abteilungen oder Partner Produkte unterstützen, die über Self-Service Purchase erworben wurden?

IT-Abteilungen und Partner werden nicht erwartet, dass Sie Unterstützung für Produkte bereitstellen, die über Self-Service Purchase erworben wurden. Microsoft stellt Standardunterstützung für Self-Service-Käufer zur Verfügung.

### <a name="if-a-self-service-purchaser-calls-support-will-they-use-the-customers-premier-support-incidents"></a>Wenn ein Self-Service-Käufer Unterstützung anruft, werden die ersten Supportvorfälle des Kunden verwendet?

Self-Service-Käufer verwenden nicht die Premier-Support-Vorfälle eines Kunden, um Unterstützung für Self-Service-Käufe zu erhalten.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Wie wird erwartet, dass Benutzerschulungen zu den Produkten erhalten, die Sie über Self-Service Purchase kaufen?

Umfassende Schulungen für Benutzer finden Sie auf den Websites Microsoft Power BI, Power apps und Power automatisieren. Die Produkte haben geleitetes lernen, Dokumentation, Beispiele und starke Communities, um Antworten und Tipps direkt von anderen Benutzern zu erhalten.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Was geschieht mit einem Self-Service-Kauf, wenn ein Benutzer die Organisation verlässt?

Gültige Benutzer haben weiterhin den vollständigen Gebrauch des Self-Service-Kaufs für die Dauer des Abonnements erhalten. Das Abonnement bleibt so lange aktiv, bis der Käufer es direkt storniert oder wenn ein Administrator das Abonnement durch den Kundensupport storniert. Administratoren können auch festlegen, dass Benutzern des abgebrochenen Abonnements eine zentral erworbene Lizenz zugewiesen wird.

## <a name="partners"></a>Partner

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Welche Rolle spielen die Partner von Microsoft bei Self-Service-Käufen?

Partner mit Delegierten Administratorrechten können Self-Service-Käufe im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>sehen, genau wie ein Administrator. Partner können zur Unterstützung einer Organisation beitragen, die Produkte zentralisieren möchte, die über Self-Service-Käufe erworben wurden. Darüber hinaus können Partnerlösungen anbieten, um die Funktionen eines Self-Service-Kaufs zu erweitern.

## <a name="country-and-region-availability"></a>Regionale Verfügbarkeit

### <a name="in-which-countries-and-regions-can-i-make-a-self-service-purchase"></a>In welchen Ländern und Regionen kann ich einen Self-Service-Einkauf tätigen?

Self-Service-Käufe sind in den folgenden Ländern und Regionen verfügbar: Afghanistan, Åland-Inseln, Albanien, Algerien, Amerikanisch-Samoa, Andorra, Angola, Anguilla, Antarktis, Antigua und Barbuda, Argentinien, Armenien, Aruba, Australien, Österreich, Aserbaidschan, Bahamas, Bahrain, Bangladesch, Barbados, Belarus, Belgien, Bulgarien, Belize, Benin, Bermuda, Bhutan, Bolivien, Bonaire, Sint Eustatius und Saba, Bosnien und Herzegowina, Botswana, Bouvetinsel Island, Brasilien, britisches indisches Ozean Territorium , Brunei, Burkina Faso, Burundi, Cabo Verde, Kambodscha, Kamerun, Kanada, Cayman Islands, Zentralafrikanischen Republik, Tschad, Chile, China, Weihnachtsinsel, Kokosinseln (Keeling), Kolumbien, Komoren, Kongo, Kongo (DRK), Cook Islands, Costa Rica, Côte d ' Ivoire, Kroatien, Zypern, Curaçao, Tschechische Republik, Dänemark, Dschibuti, Dominica, Dominikanische Republik, Ecuador, Ägypten, El Salvador, Äquatorial Guinea, Eritrea, Estland, Äthiopien, Falkland Islands, Färöer, Fidschi, Finnland, Frankreich, Französisch-Guayana , Französisch-Polynesien, französische südliche Gebiete, Gabun, Gambia, Georgien, Deutschland, Ghana, Gibraltar, Grönland, Griechenland, Grenada, Guadeloupe, Guam, Guatemala, Guernsey, Guinea, Guinea-Bissau, Guyana, Haiti, Heard Island und McDonald Islands, Honduras, Hong Kong SAR, Ungarn, Island, Indonesien, Irak, Irland, Isle of man, Israel, Italien, Jamaika, Japan, Jersey, Jordanien, Kasachstan, Kenia, Kiribati, Korea, Kosovo, Kuwait, Kirgisistan, Laos, Lettland, Libanon, Lesotho, Liberia, Libyen, Liechtenstein, Litauen, Luxemburg , Macau SAR, Madagaskar, Malawi, Malaysia, Malediven, Mali, Malta, Marshallinseln, Martinique, Mauretanien, Mauritius, Mayotte, Mexiko, Mikronesien, Moldawien, Monaco, Mongolei, Montenegro, Montserrat, Marokko, Mosambik, Myanmar, Namibia, Nauru, Nepal, Niederlande, Neukaledonien, Neuseeland, Nicaragua, Niger, Nigeria, Niue, Norfolk Island, Nord Makedonien, Nördliche Marianen, Norwegen, Oman, Pakistan, Palau, Palästinensische Autonomiebehörde, Panama, Papua Neu Guinea, Paraguay, Peru, Philippinen, Pitcairn-Inseln, Polen, Portugal, Puerto Rico , Katar, Réunion, Rumänien, Russland, Ruanda, Saint-Barthélemy, St. Kitts und Nevis, Saint Lucia, Saint Martin, Saint Pierre und Miquelon, Saint Vincent und die Grenadines, Samoa, San Marino, São Tomé und Príncipe, Saudi-Arabien, Senegal, Serbien, Seychellen, Sierra Leone, Singapur, Sint Maarten, Slowakei, Slowenien, Solomon Islands, Somalia, Südafrika, Südgeorgien und südliche Sandwich Inseln, Südsudan, Spanien, Sri Lanka, St. Helena , Ascension, Tristan da Cunha, Suriname, Spitzbergen und Jan Mayen, Swasiland, Schweden, Schweiz, Taiwan, Tadschikistan, Tansania, Thailand, Timor-Leste, Togo, Tokelau, Tonga, Trinidad und Tobago, Tunesien, Türkei, Turkmenistan, Turks-und Caicosinseln, Tuvalu, u.s.-Inseln, US Virgin Islands, Uganda, Ukraine, Vereinigte Arabische Emirate, Vereinigtes Königreich, Vereinigte Staaten, Uruguay, Usbekistan, Vanuatu, Vatikanstadt, Venezuela, Vietnam, Wallis und Futuna, Jemen, Sambia und Simbabwe.