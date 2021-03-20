---
title: Verwalten der Microsoft 365 Identity Governance
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Erfahren Sie mehr über die Verwendung von Microsoft 365 Identity Governance-Features.
ms.openlocfilehash: 6a97ca24c609724a2cab93feec9e90f25d3361e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910954"
---
# <a name="manage-microsoft-365-identity-governance"></a>Verwalten der Microsoft 365 Identity Governance

Bei der Identitätsgovernance geht es um den Schutz, die Kontrolle und die Überwachung von Zugriffen auf kritische Ressourcen bei gleichzeitiger Sicherstellung der Mitarbeiterproduktivität. Beispielsweise können Sie mit Identitätsgovernance sicherstellen, dass die richtigen Benutzer den richtigen Zugriff auf die richtigen Ressourcen haben, und feststellen, ob sich dieser Zugriff im Laufe der Zeit ändert.

Weitere Informationen finden Sie in dieser [Übersicht über die Identitätsverwaltung für Azure Active Directory (Azure AD).](/azure/active-directory/governance/identity-governance-overview)

## <a name="set-up-azure-ad-access-reviews"></a>Einrichten von Azure AD-Zugriffsüberprüfungen

Mit Azure AD-Zugriffsüberprüfungen können Sie den Zugriff eines Benutzers überprüfen, um sicherzustellen, dass nur die richtigen Personen weiterhin Zugriff haben. Zum Beispiel:

- Wenn ein neuer Mitarbeiter in Ihre Organisation eintritt, müssen Sie sicherstellen, dass er den richtigen Zugriff hat, um produktiv zu sein.
- Wenn dieser Mitarbeiter in andere Teams, Standorte oder Abteilungen wechselt, müssen Sie sicherstellen, dass sein Zugang zu früheren Teams, Standorten oder Abteilungen bei Bedarf entfernt wird.
- Wenn dieser Mitarbeiter oder ein Gast Ihre Organisation verlässt, müssen Sie sicherstellen, dass sein Zugang entfernt wird.

Dies ist besonders wichtig, falls Ihre Organisation Sicherheitsprüfungen unterzogen wird, um festzustellen, ob Benutzerkonten zu viel Zugriff haben. Ein Verstoß gegen branchenspezifische oder regionale Vorschriften kann zu Geldstrafen führen.

Weitere Informationen finden Sie in der [Übersicht über Zugriffsüberprüfungen](/azure/active-directory/governance/access-reviews-overview).

In diesen Artikeln finden Sie Informationen zur Konfiguration verschiedener Arten von Zugriffsüberprüfungen:

- [Gruppen und Apps](/azure/active-directory/governance/create-access-review)
- [Azure AD-Rollen](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure-Ressourcenrollen](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Einrichten der Azure AD-Berechtigungsverwaltung

Wiht Azure AD-Berechtigungsverwaltung, können Sie den Identitäts- und Zugriffslebenszyklus im großen Maßstab verwalten, indem Sie Zugriffsanforderungsworkflows, Zugriffszuweisungen, Überprüfungen und Ablauf automatisieren.

Ihre Mitarbeiter benötigen Zugriff auf verschiedene Gruppen, Anwendungen und Websites, um ihre Aufgabe ausführen zu können. Die Verwaltung dieses Zugriffs kann schwierig sein, da sich die Anforderungen ändern, neue Anwendungen hinzugefügt werden oder Benutzer zusätzliche Zugriffsrechte benötigen. Wenn Sie mit anderen Organisationen zusammenarbeiten, wissen Sie möglicherweise nicht, wer in der anderen Organisation Zugriff auf die Ressourcen Ihrer Organisation benötigt, und externe Benutzer wissen nicht, welche Anwendungen, Gruppen oder Websites Ihre Organisation verwendet.

Die Azure AD-Berechtigungsverwaltung kann Ihnen dabei helfen, den Zugriff auf Gruppen, Anwendungen und SharePoint-Websites für interne und externe Benutzer effizienter zu verwalten.
 
Weitere Informationen finden Sie in [der Übersicht über die Azure AD-Berechtigungsverwaltung](/azure/active-directory/governance/entitlement-management-overview).