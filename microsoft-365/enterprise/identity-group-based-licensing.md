---
title: 'Schritt 12: Einrichten der automatischen Lizenzierung'
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
description: Verstehen und konfigurieren Sie die gruppenbasierte Lizenzierung für Azure AD-Gruppen.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867541"
---
# <a name="step-12-set-up-automatic-licensing"></a>Schritt 12: Einrichten der automatischen Lizenzierung

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt konfigurieren Sie Sicherheitsgruppen in Azure AD, um automatisch Lizenzen aus einem Satz von Abonnements zu allen Mitgliedern der Gruppe zuzuweisen. Dies wird als *gruppenbasierte Lizenzierung* bezeichnet. Wenn ein Benutzerkonto zur Gruppe hinzugefügt oder aus ihr entfernt wird, werden die Lizenzen für die Abonnements der Gruppe automatisch zugewiesen oder aus dem Benutzerkonto entfernt.

Für Microsoft 365 Enterprise konfigurieren Sie Azure AD-Sicherheitsgruppen, um beide Lizenzen zuzuweisen:

- Office 365 Enterprise E3 oder E5
- Enterprise Mobility + Security (EMS) E3 oder E5

Suchen Sie unter Verwendung der Gruppen, die Sie in Schritt 2 identifiziert haben, nach Gruppen, die eine Liste der Konten enthalten, wobei alle Benutzer in dieser Gruppe Office 365- und EMS-Lizenzen haben müssen. Stellen Sie sicher, dass Sie genug Lizenzen für alle Gruppenmitglieder haben. Wenn keine Lizenzen mehr vorhanden sind, werden neuen Benutzern keine Lizenzen zugewiesen, bis Lizenzen verfügbar werden.

>[!Note]
>Sie sollten  nicht die *gruppenbasierte Lizenzierung* für Gruppen konfigurieren, die Azure Business to Business (B2B)-Konten enthalten.
>

Weitere Informationen finden Sie unter [Grundlagen der gruppenbasierten Lizenzierung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Lesen Sie die [Schritte zum Konfigurieren der gruppenbasierten Lizenzierung für eine Azure-Sicherheitsgruppe](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

Die Ergebnisse dieses Schritts sind:

- Sie haben identifiziert, welche Sicherheitsgruppen für die gruppenbasierte Lizenzierung geeignet sind.
- Sie haben diese Gruppen für gruppenbasierte Lizenzierung konfiguriert.

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Automatisieren von Lizenzen und Gruppenmitgliedschaften](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-group-license) für diesen Schritt ansehen.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [Überwachen der Mandanten- und Anmeldeaktivität](identity-azure-ad-access-usage-reporting.md) |

