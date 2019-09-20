---
title: 'Schritt 7: Konfigurieren der Identitätsgovernance'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Identitätsgovernance für Ihren Azure AD-Mandanten verstehen und konfigurieren.
ms.openlocfilehash: 1c0eab574e5436dd0c88a0b46d1916281bcf0577
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047358"
---
# <a name="step-7-configure-identity-governance"></a>Schritt 7: Konfigurieren der Identitätsgovernance

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Bei der Identitätsgovernance geht es um den Schutz, die Kontrolle und die Überwachung von Zugriffen auf kritische Ressourcen bei gleichzeitiger Sicherstellung der Mitarbeiterproduktivität. Beispielsweise können Sie mit Identitätsgovernance sicherstellen, dass die richtigen Benutzer den richtigen Zugriff auf die richtigen Ressourcen haben, und feststellen, ob sich dieser Zugriff im Laufe der Zeit ändert.

Weitere Informationen über Identitätsgovernance für Azure Active Directory (Azure AD) finden Sie in [diesem Artikel](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Zugriffsüberprüfungen in Azure AD einrichten

*Dies ist optional und gilt nur für die E5-Version von Microsoft 365 Enterprise*

In diesem Schritt richten Sie Azure AD Zugriffsüberprüfungen ein, mit denen Sie den Zugriff eines Benutzers überprüfen können, um sicherzustellen, dass nur die richtigen Personen weiterhin Zugriff haben. Zum Beispiel:

- Wenn ein neuer Mitarbeiter in Ihre Organisation eintritt, müssen Sie sicherstellen, dass er den richtigen Zugriff hat, um produktiv zu sein.
- Wenn dieser Mitarbeiter in andere Teams, Standorte oder Abteilungen wechselt, müssen Sie sicherstellen, dass sein Zugang zu früheren Teams, Standorten oder Abteilungen bei Bedarf entfernt wird.
- Wenn dieser Mitarbeiter oder ein Gast Ihre Organisation verlässt, müssen Sie sicherstellen, dass sein Zugang entfernt wird.

Dies ist besonders wichtig, falls Ihre Organisation Sicherheitsprüfungen unterzogen wird, um festzustellen, ob Benutzerkonten zu viel Zugriff haben. Ein Verstoß gegen branchenspezifische oder regionale Vorschriften kann zu Geldstrafen führen.

Weitere Informationen über Azure AD-Zugriffsüberprüfungen finden Sie in [diesem Artikel](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).

In diesen Artikeln finden Sie Informationen zur Konfiguration verschiedener Arten von Zugriffsüberprüfungen:

- [Gruppen und Apps](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD-Rollen](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure-Ressourcenrollen](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-access-reviews) für diesen Abschnitt ansehen.

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Identitätsinfrastruktur](identity-exit-criteria.md)

