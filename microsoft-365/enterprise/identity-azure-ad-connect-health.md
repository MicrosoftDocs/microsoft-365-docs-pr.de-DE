---
title: 'Schritt 8: Überwachen des Synchronisierungsstatus'
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
description: Grundlegendes und Konfiguration von Azure AD Connect Health
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867981"
---
# <a name="step-8-monitor-synchronization-health"></a>Schritt 8: Überwachen des Synchronisierungsstatus

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt installieren Sie einen Azure AD Connect Health-Agenten auf jedem Identitätsserver, um Ihre Identitätsinfrastruktur und die von Azure AD Connect bereitgestellten Synchronisierungsdienste zu überwachen. Die Überwachungsinformationen stehen im Azure AD Connect Health-Portal zur Verfügung. Dort können Sie Warnungen, Informationen zur Leistungsüberwachung, Verwendungsanalysen und andere Informationen anzeigen.

![Komponenten von Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

Die wichtigste Entwurfsentscheidung hinsichtlich der Verwendung von Azure AD Connect Health basiert auf der Art und Weise, wie Sie Azure AD Connect verwenden:

- Wenn Sie die **verwaltete Authentifizierung** verwenden, beginnen Sie mit [Verwenden von Azure AD Connect Health mit Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), um Informationen zur Funktionsweise und Konfiguration von Azure AD Connect Health zu erhalten.
- Wenn Sie nur die Namen der Konten und Gruppen mithilfe der **Verbundauthentifizierung** mit Active Directory-Verbunddiensten (AD FS) synchronisieren, beginnen Sie mit [Verwenden von Azure AD Connect Health mit AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), um Informationen zur Funktionsweise und zur Konfiguration von Azure AD Connect Health zu erhalten.

Wenn Sie diesen Schritt abgeschlossen haben, verfügen Sie über Folgendes:

- Der Azure AD Connect Health-Agent ist auf jedem Ihrer lokalen Identitätsanbieterserver installiert.
- Das Azure AD Connect Health-Portal zeigt den aktuellen Status Ihrer lokalen Infrastruktur und der Synchronisierungsaktivitäten mit dem Azure AD-Mandanten für Ihre Office 365- und EMS-Abonnements.

Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sync-health) für diesen Schritt ansehen.


## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [Vereinfachen der Kennwortaktualisierungen](identity-password-writeback.md) |

