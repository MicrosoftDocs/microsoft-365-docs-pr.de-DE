---
title: 'Phase 2: Identität'
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
description: Die Schritte zur Bereitstellung der Identitätsinfrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: 07f95a249912826b80e0654cac4063b3d5763267
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981950"
---
# <a name="phase-2-identity"></a>Phase 2: Identität

![](./media/deploy-foundation-infrastructure/identity_icon.png)

In Microsoft 365 Enterprise ebnet eine sorgfältig geplante und ausgeführte Identitätsinfrastruktur den Weg für stärkere Sicherheit und Zugriff auf Produktivitätsarbeitslasten und die zugehörigen Daten nur für authentifizierte Benutzer und Geräte.

Schauen Sie sich dieses Video an, um eine Übersicht über die Identitätsmodelle und Authentifizierung für Microsoft 365 Enterprise zu erhalten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
>Wenn Sie bereits eine Identitätsinfrastruktur bereitgestellt haben, lesen Sie bitte den Artikel [Identitätsbeendigungskriterien](identity-exit-criteria.md) um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.
>

Informationen zu den Identitätsfeatures jedes Microsoft 365 Enterprise-Plans, zur Rolle von Azure Active Directory (Azure AD), zu lokalen und cloudbasierten Komponenten sowie zu den häufigsten Authentifizierungskonfigurationen finden Sie auf dem [Poster zur Identitätsinfrastruktur](media/identity-infrastructure/M365E-ID-Infra.pdf).

[![Poster zur Identitätsinfrastruktur](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)

Dieses zweiseitige Poster ist eine schnelle Möglichkeit, sich mit den Identitätskonzepten und -konfigurationen für Microsoft 365 Enterprise vertraut zu machen.

Sie können [dieses Poster herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) und in den Formaten "Brief", "Legal" oder "Tabloid" (27,94 x 43,18 cm) ausdrucken.

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>Planen und Bereitstellen Ihrer Microsoft 365 Enterprise-Identitätsinfrastruktur 

Verwenden Sie die folgenden Schritte zum Planen und Bereitstellen der neuen Identitätsinfrastruktur in der Cloud. Sie können diese Schritte auch zum Anpassen Ihrer vorhandenen lokalen oder Hybrididentitätsinfrastruktur für die Verwendung mit Microsoft 365 Enterprise verwenden. 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Planen von Benutzern und Gruppen](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [Sichern Ihrer privilegierten Identitäten](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [Konfigurieren der Hybrididentität](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [Konfigurieren der sicheren Benutzerauthentifizierung](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [Vereinfachen des Zugriffs für Benutzer](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [Verwenden von Gruppen zur einfacheren Verwaltung](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step7.png)| [Konfigurieren der Identitätsgovernance](identity-governance.md) |

Wenn Sie diese Schritte abgeschlossen haben, wechseln Sie zu [Beendigungskriterien](identity-exit-criteria.md) für diese Phase, um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für die Microsoft 365 Enterprise-Identität erfüllen.

## <a name="identity-and-device-access-recommendations"></a>Empfehlungen für den Identitäts- und Gerätezugriff

Microsoft bietet eine Reihe von Empfehlungen für den [Identitäts- und Gerätezugriff](microsoft-365-policies-configurations.md), um sicherzustellen, dass eine sichere und produktive Mitarbeiter. Verwenden Sie für Identität die Standardeinstellungen und Empfehlungen in den folgenden Artikeln zusammen mit den Schritten in dieser Phase:

- [Voraussetzungen](identity-access-prerequisites.md)
- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Erfahren Sie, wie IT-Experten bei Microsoft [Identitäten verwalten und den Zugriff sichern](https://www.microsoft.com/de-DE/itshowcase/deploying-and-managing-microsoft-365#primaryR5).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber multinationales, repräsentatives Unternehmen [eine hybride Identitätsinfrastruktur bereitgestellt hat](contoso-identity.md) (für Microsoft 365-Clouddienste).

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Planen von Benutzern und Gruppen](identity-plan-users-groups.md) |
