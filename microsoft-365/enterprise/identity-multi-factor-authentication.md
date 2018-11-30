---
title: 'Schritt 5: Einrichten der mehrstufigen Authentifizierung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren der mehrstufigen Authentifizierung für Benutzerkonten.
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868043"
---
# <a name="step-5-set-up-multi-factor-authentication"></a>Schritt 5: Einrichten der mehrstufigen Authentifizierung

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt richten Sie die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) ein, um eine zweite Sicherheitsebene für Benutzeranmeldungen und Transaktionen hinzuzufügen. MFA erfordert eine zusätzliche Überprüfungsmethode, nachdem Benutzer ihr Kennwort richtig eingegeben haben. Ohne MFA ist das Kennwort die einzige Überprüfungsmethode. Das Problem mit Kennwörtern ist, dass sie häufig von einem Angreifer leicht zu erraten sind oder unbewusst für nicht vertrauenswürdige Parteien freigegeben werden.

Die zweite Sicherheitsebene bei MFA kann Folgendes sein:

- Ein persönliches und vertrauenswürdiges Gerät, das nicht leicht gefälscht oder dupliziert werden kann, z. B. ein Smartphone.
- Ein biometrisches Attribut, z. B. ein Fingerabdruck.

Sie aktivieren MFA und konfigurieren die sekundäre Authentifizierungsmethode auf Benutzerkontobasis. Teilen Sie den Benutzern unbedingt mit, dass MFA aktiviert ist, damit sie die Anforderungen, z. B. obligatorische Verwendung eines Smartphones zum Anmelden, verstehen und sich erfolgreich anmelden können.

Weitere Informationen finden Sie unter [Planen der mehrstufigen Authentifizierung für Office 365-Bereitstellungen](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).

Zum Konfigurieren der mehrstufigen Authentifizierung folgen Sie den Anweisungen unter [Einrichten der mehrstufigen Authentifizierung für Office 365-Benutzer](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).

Sie können MFA mit bedingten Zugriffsrichtlinien anfordern. Sie können beispielsweise eine Richtlinie konfigurieren, die MFA erfordert, wenn die Authentifizierung als mittelmäßig oder hoch riskant eingestuft wird. Weitere Informationen finden Sie unter [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md#require-mfa-based-on-sign-in-risk).

>[!Note]
>In einigen Clientanwendungen, z. B. Microsoft Office 2010 oder früher und Apple Mail, können Sie MFA nicht verwenden. Um diese Apps zu nutzen, müssen Sie „App-Kennwörter“ anstelle Ihres herkömmlichen Kennworts verwenden. Das App-Kennwort ermöglicht der App, MFA zu umgehen und die Arbeit fortzusetzen. Weitere Informationen zu App-Kennwörtern finden Sie unter [Erstellen eines App-Kennworts für Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).
>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-mfa) für diesen Schritt ansehen.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [Schutz vor Kompromittierung von Anmeldeinformationen](identity-azure-ad-identity-protection.md) |

