---
title: 'Phase 2: Identität'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung der Identitätsinfrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867964"
---
# <a name="phase-2-identity"></a>Phase 2: Identität

![](./media/deploy-foundation-infrastructure/identity_icon.png)

In Microsoft 365 Enterprise ebnet eine sorgfältig geplante und ausgeführte Identitätsinfrastruktur den Weg für stärkere Sicherheit und Zugriff auf Produktivitätsarbeitslasten und die zugehörigen Daten nur für authentifizierte Benutzer und Geräte.

>[!Note]
>Wenn Sie bereits eine Identitätsinfrastruktur bereitgestellt haben, lesen Sie bitte den Artikel [Identitätsbeendigungskriterien](identity-exit-criteria.md) um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>Planen und Bereitstellen Ihrer Microsoft 365 Enterprise-Identitätsinfrastruktur 

Verwenden Sie die folgenden Schritte zum Planen und Bereitstellen der neuen Identitätsinfrastruktur in der Cloud. Sie können diese Schritte auch zum Anpassen Ihrer vorhandenen lokalen oder Hybrididentitätsinfrastruktur für die Verwendung mit Microsoft 365 Enterprise verwenden. 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Planen von Benutzern und Gruppen](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [Schützen von globalen Administratorkonten](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [Einrichten von globalen Administratoren bei Bedarf](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [Vereinfachen der Kennwortzurücksetzung](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [Einrichten der mehrstufigen Authentifizierung](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [Schutz vor Kompromittierung von Anmeldeinformationen](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [Synchronisieren von Verzeichnissen](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [Überwachen des Synchronisierungsstatus](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [Vereinfachen der Kennwortaktualisierungen](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [Vereinfachen der Benutzeranmeldung](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [Anpassen der Office 365-Anmeldeseite](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [Einrichten der automatischen Lizenzierung](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [Überwachen der Mandanten- und Anmeldeaktivität](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [Einrichten der dynamischen Gruppenmitgliedschaft](identity-automatic-group-membership.md) |

Wenn Sie diese Schritte abgeschlossen haben, wechseln Sie zu [Beendigungskriterien](identity-exit-criteria.md) für diese Phase, um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.

## <a name="identity-and-device-access-recommendations"></a>Empfehlungen für den Identitäts- und Gerätezugriff

Microsoft bietet eine Reihe von Empfehlungen für den [Identitäts- und Gerätezugriff](microsoft-365-policies-configurations.md), um sicherzustellen, dass eine sichere und produktive Mitarbeiter. Verwenden Sie für Identität die Standardeinstellungen und Empfehlungen in den folgenden Artikeln zusammen mit den Schritten in dieser Phase:

- [Voraussetzungen](identity-access-prerequisites.md)
- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Erfahren Sie anhand der folgenden Ressourcen, wie IT-Experten bei Microsoft die Identitätsfunktionen von Microsoft 365 Enterprise geplant und bereitgestellt haben:

- [Verwalten von Benutzeridentitäten und sicherer Zugriff bei Microsoft](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [Erhöhter Zugriff dank Azure AD Privileged Identity Management](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber multinationales, repräsentatives Unternehmen [eine hybride Identitätsinfrastruktur bereitgestellt hat](contoso-identity.md) (für Microsoft 365-Clouddienste).

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Planen von Benutzern und Gruppen](identity-plan-users-groups.md) |
