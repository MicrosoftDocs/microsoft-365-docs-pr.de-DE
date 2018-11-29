---
title: 'Schritt 3: Einrichten von globalen Administratoren für den Bedarfsfall'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Privileged Identity Management verstehen und konfigurieren
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867750"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a>Schritt 3: Einrichten von globalen Administratoren für den Bedarfsfall

*Dieser Schritt ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt richten Sie Azure AD Privileged Identitätsmanagement (PIM) ein, um die Zeitspanne zu verringern, in der Ihre globalen Administratorkonten anfällig für Angriffe von böswilligen Benutzern sind. PIM bietet bei Bedarf, just-in-Time Zuweisung der globalen Administratorrolle.  

Ihre globalen Administratorkonten werden zu berechtigten Administratoren anstelle von dauerhaften Administratoren. Die globale Administratorrolle ist inaktiv, bis eine Person sie benötigt. Sie durchlaufen dann einen Aktivierungsprozess, bei dem die globale Administratorrolle für eine bestimmte Zeitspanne zum globalen Administratorkonto hinzugefügt wird. Wenn der Zeitraum abgelaufen ist, entfernt PIM die globale Administratorrolle vom globalen Administratorkonto.

PIM ist zusammen mit Azure Active Directory Premium P2 erhältlich, das in Microsoft 365 Enterprise E5 enthalten ist. Alternativ können Sie für Ihre globalen Administratorkonten einzelne Azure Active Directory Premium P2-Lizenzen erwerben.

Weitere Informationen zum Aktivieren von Azure PIM für Ihren Azure AD-Mandanten und für globale Administratorkonten finden Sie unter der [Schritte zum Konfigurieren von PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Weitere Informationen zum Entwickeln einer Roadmap, um den privilegierten Zugriff vor Cyberangriffen schützt, finden Sie unter [Schützen des privilegierten Zugriffs für hybride Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pim) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [Vereinfachen der Kennwortzurücksetzung](identity-password-reset.md) |

