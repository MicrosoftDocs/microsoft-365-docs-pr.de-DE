---
title: 'Schritt 14: Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zum Verständnis und zur Konfiguration der Self-Service-Gruppenverwaltung in Azure AD.
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867888"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a>Schritt 14: Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt werden Sie Azure Active Directory (AD)-Gruppen identifizieren, die von Gruppenbesitzern, statt von IT-Administratoren, verwaltet werden können. Mit diesem als *Self-Service-Gruppenverwaltung* bezeichneten Feature können Gruppenbesitzer, denen keine Administratorrolle zugewiesen ist, Sicherheitsgruppen erstellen und verwalten. 

Benutzer können die Mitgliedschaft in einer Sicherheitsgruppe anfordern, und die Anforderung wird an den Gruppenbesitzer gesendet, statt an den IT-Administrator. So kann die tägliche Kontrolle über Gruppenmitgliedschaften an die Team-, Projekt- oder Unternehmensbesitzer delegiert werden, die die geschäftliche Verwendung für die Gruppe verstehen und die Mitgliedschaften verwalten können.

>[!Note]
>Die Self-Service-Gruppenverwaltung steht nur für Azure AD-Sicherheits- und Office 365-Gruppen zur Verfügung. Sie steht nicht für E-Mail-aktivierte Gruppen, Verteilerlisten oder Gruppen zur Verfügung, die mit lokalem Windows Server Active Directory (AD) synchronisiert wurden.
>

Weitere Informationen finden Sie in den [Anweisungen zum Konfigurieren einer Azure AD-Gruppe für Self-Service-Verwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-self-service-groups) für diesen Schritt ansehen.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [Einrichten der dynamischen Gruppenmitgliedschaft](identity-automatic-group-membership.md) |
