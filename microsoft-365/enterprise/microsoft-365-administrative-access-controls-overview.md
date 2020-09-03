---
title: Administrative Zugriffssteuerung in Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Dieser Artikel bietet eine Übersicht über die administrativen Zugriffssteuerungen und die Datenkategorisierung in Microsoft 365.
ms.openlocfilehash: 817a5907566435d021fe78d89b5c9476c04318d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332592"
---
# <a name="administrative-access-controls-in-microsoft-365"></a>Administrative Zugriffssteuerung in Microsoft 365 

Microsoft hat stark in Systeme und Steuerelemente investiert, die die meisten Microsoft 365-Vorgänge automatisieren, während der Zugriff auf Kunden Inhalte durch Microsoft absichtlich eingeschränkt wird. Der Dienst wird von den Menschen verwaltet, und die Software betreibt den Dienst. Auf diese Weise kann Microsoft Microsoft 365 bei der Skalierung verwalten und die Risiken interner Bedrohungen für Kunden Inhalte verwalten.

Standardmäßig verfügen Microsoft-Techniker über Null ständige Administratorrechte und keinen ständigen Zugriff auf Kunden Inhalte in Microsoft 365. Ein Microsoft-Techniker kann für einen begrenzten Zeitraum begrenzten, überwachten und gesicherten Zugriff auf die Inhalte eines Kunden haben. Der Zugriff ist nur für Dienstvorgänge erforderlich und nur, wenn er von einem Mitglied von Microsoft Senior Management genehmigt wurde. Für Kunden Lockbox-lizenzierte Kunden bietet der Kunde Zugriffsgenehmigung für den Inhalt an, der auf Microsoft 365 gehostet wird.

Microsoft stellt Onlinedienste bereit, die mehrere Formen der Cloud-Zustellung verwenden:

- **Öffentliche Clouds:** Enthält mehr mandantenversionen von Microsoft 365, Azure und anderen Diensten, die in Nordamerika, Südamerika, Europa, Asien, Australien usw. gehostet werden.
- **Nationale Clouds:** Umfasst alle souveränen und von Drittanbietern betriebenen Clouds außerhalb der Vereinigten Staaten (mit Ausnahme der zuvor erwähnten), wie Microsoft 365 in China (betrieben von 21Vianet) und Microsoft 365 in Deutschland (betrieben von Microsoft, aber unter einem Modell, bei dem ein deutscher Daten Treuhänder, die Deutsche Telekom, den Zugriff von Microsoft auf Kundendaten und-Systeme steuert und überwacht).
- **Öffentliche Clouds:** Umfasst Microsoft 365-und Azure-Dienste, die für Kunden der US-Regierung verfügbar sind.

Für die Zwecke dieses Artikels umfassen Microsoft 365-Dienste Folgendes:

- [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)
- [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [OneDrive for Business](https://docs.microsoft.com/OneDrive/onedrive)
- [Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a>Microsoft 365-Zugriffssteuerung

Für Zugriffs Steuerungszwecke kategorisiert Microsoft Microsoft 365-Daten als Kundendaten oder andere Datentypen.

### <a name="customer-data"></a>Kundendaten

Kundendaten sind alle Daten, die von oder im Auftrag eines Kunden bei der Verwendung von Microsoft 365-Diensten bereitgestellt werden. Dies sind Kunden Inhalte, die von Microsoft 365-Benutzern direkt erstellt oder hochgeladen wurden, einschließlich:

- E-Mails
- SharePoint Online Inhalt
- Chatnachrichten
- Kalenderelemente
- Dokumente
- Kontakte
- Endbenutzer-identifizierbare Informationen (EUII) (Daten, die für einen Benutzer eindeutig sind oder die mit einem einzelnen Benutzer verknüpft sind, aber keine Kunden Inhalte enthalten)

### <a name="other-types-of-data"></a>Andere Datentypen

Zu den anderen Datentypen gehören:

- **Kontodaten:** Enthält administrative Daten (Informationen, die von Administratoren bei der Registrierung oder beim Kauf von Diensten bereitgestellt werden) und Zahlungsdaten (Informationen zu Zahlungsinstrumenten wie Kreditkartendetails).
- **Organisatorisch identifizierbare Informationen:** Enthält Daten, die zum Identifizieren eines Mandanten, zur Verwendung und nicht zum Verknüpfen mit einem einzelnen Benutzer oder zum Einschließen in Kunden Inhalte verwendet werden.
- **System Metadaten:** Enthält Dienstprotokolle, die Konfigurationseinstellungen, Systemstatus, Microsoft-IP-Adressen und technische Informationen zu Abonnements und Mandanten enthalten.

Microsoft hat Zugriffssteuerungsmechanismen eingerichtet, um sicherzustellen, dass niemand ungenehmigten Zugriff auf Kundendaten oder Zugriffssteuerungsdaten hat. Zugriffssteuerungsdaten verwalten den Zugriff auf andere Daten oder Funktionen in der Umgebung, einschließlich Zugriff auf Kunden Inhalte oder EUII, Microsoft-Kennwörter, Sicherheitszertifikate und andere Authentifizierungs bezogene Daten. Zugriffssteuerungsmechanismen schützen auch den nicht genehmigten physischen, logischen oder Remotezugriff auf die Microsoft 365-Produktionsumgebung.

Microsoft verwendet drei Kategorien von Zugriffssteuerungen für den Betrieb von Microsoft 365:

- Isolierungssteuerungen
- Personalsteuerungen
- Technologiesteuerungen

Wenn diese Steuerelemente kombiniert werden, können Sie böswillige Aktionen in Microsoft 365 verhindern und erkennen. Zusätzlich zu den von Microsoft verwendeten Isolierungs-, Personal-und Technologie Steuerelementen gibt es eine vierte Kategorie von Steuerelementen: die von Kunden implementierten.

Microsoft 365 ermöglicht das Verwalten von Daten auf die gleiche Weise, wie Daten in lokalen Umgebungen verwaltet werden. Die Person, die eine Organisation für Microsoft 365 anmeldet, wird automatisch zu einem globalen Administrator. Der globale Administrator hat Zugriff auf alle Features in Verwaltungs Portalen und kann Folgendes:

- Erstellen oder Bearbeiten von Benutzern
- Zuweisen von Administratorrollen zu anderen Benutzern
- Zurücksetzen von Benutzerkennwörtern
- Verwalten von Benutzerlizenzen
- Verwalten von Domänen
- Genehmigen von Kunden-Lockbox-Anforderungen

Es wird empfohlen, dass jede Organisation mindestens zwei Administratorkonten konfiguriert. Für große Unternehmensorganisationen empfehlen wir spezialisierte Administratorkonten, die unterschiedliche Funktionen bedienen.

Informationen zum Zuweisen von Administratorrollen und-Berechtigungen finden Sie unter [Zuweisen von Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) und [Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="related-links"></a>Links zu verwandten Themen

- [Isolierungssteuerungen](microsoft-365-isolation-controls.md)
- [Personalsteuerungen](microsoft-365-personnel-controls.md)
- [Technologie Steuerelemente](microsoft-365-technology-controls.md)
- [Überwachung und Überprüfung von Zugriffssteuerungen](microsoft-365-monitoring-and-auditing-access-controls.md)
- [Yammer Enterprise-Zugriffssteuerungen](microsoft-365-yammer-enterprise-access-controls.md)
