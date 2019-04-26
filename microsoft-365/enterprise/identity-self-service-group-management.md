---
title: 'Schritt 6: Verwenden von Gruppen zur einfacheren Verwaltung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zum Verständnis und zur Konfiguration der Self-Service-Gruppenverwaltung in Azure AD.
ms.openlocfilehash: 9400e99ced45370600d1d5dcee4388ddef4250fe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283523"
---
# <a name="step-6-use-groups-for-easier-management"></a>Schritt 6: Verwenden von Gruppen zur einfacheren Verwaltung

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt identifizieren Sie Azure Active Directory(Azure AD)-Gruppen, die von Gruppenbesitzern anstelle von IT-Administratoren verwaltet werden können. Diese Funktion, bekannt als *Self-Service-Gruppenverwaltung*, ermöglicht es Gruppenbesitzern, denen keine Administratorrolle zugewiesen ist, Sicherheitsgruppen zu erstellen und zu verwalten. 

Benutzer können die Mitgliedschaft in einer Sicherheitsgruppe anfordern, und die Anforderung wird an den Gruppenbesitzer gesendet, statt an den IT-Administrator. So kann die tägliche Kontrolle über Gruppenmitgliedschaften an die Team-, Projekt- oder Unternehmensbesitzer delegiert werden, die die geschäftliche Verwendung für die Gruppe verstehen und die Mitgliedschaften verwalten können.

>[!Note]
>Self-Service-Gruppenverwaltung ist nur für Azure AD-Sicherheitsgruppen und Office 365-Gruppen aktiviert. Sie ist nicht für E-Mail-aktivierte Gruppen, Verteilerlisten oder andere Gruppen verfügbar, die aus den lokalen Active Directory Domain Services (AD DS) synchronisiert wurden.
>

Weitere Informationen finden Sie in den [Anweisungen zum Konfigurieren einer Azure AD-Gruppe für Self-Service-Verwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-self-service-groups) für diesen Abschnitt ansehen.

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>Einrichten der dynamischen Gruppenmitgliedschaft

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt erstellen Sie eine Reihe von Regeln, die automatisch Benutzerkonten als Mitglieder einer Azure AD-Gruppe hinzufügen oder entfernen. Dies ist als *dynamische Gruppenmitgliedschaft* bekannt. Die Regeln basieren auf Benutzerkontoattributen, wie Abteilung oder Land.

Die Regeln werden wie folgt angewendet:

- Wenn ein neues Benutzerkonto allen Regeln für die Gruppe entspricht, wird es ein Mitglied.
- Wenn ein Benutzerkonto kein Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es allen Regeln für die Gruppe entspricht, wird es ein Mitglied dieser Gruppe.
- Wenn ein Benutzerkonto nicht allen Regeln für die Gruppe entspricht, wird es nicht zur Gruppe hinzugefügt.
- Wenn ein Benutzerkonto Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es nicht mehr allen Regeln für die Gruppe entspricht, wird es als Mitglied der Gruppe entfernt.

Um die dynamische Mitgliedschaft zu verwenden, müssen Sie zuerst die Sätze von Gruppen mit einem gemeinsamen Satz von Benutzerkonto-Attributen bestimmen. Beispielsweise sollten alle Mitglieder der Vertriebsabteilung Teil der Azure AD-Gruppe „Vertrieb“ sein, basierend auf dem Benutzerkonto-Attribut „Abteilung“ = „Vertrieb“.

Lesen Sie die [Anweisungen, um die Regeln für eine dynamische Azure AD-Gruppe zu erstellen und zu konfigurieren](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

Die Ergebnisse dieses Abschnitts sind:

- Ein Satz von Azure AD-Gruppen, die für die dynamische Mitgliedschaft konfiguriert werden können
- Ein Satz von Regeln für jede dynamische Gruppe

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Automatisieren von Lizenzen und Gruppenmitgliedschaften](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-dyn-groups) für diesen Abschnitt ansehen.

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>Einrichten der automatischen Lizenzierung

*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt konfigurieren Sie Sicherheitsgruppen in Azure AD, um automatisch Lizenzen aus einer Gruppe von Abonnements zu allen Mitgliedern der Gruppe zuzuweisen. Dies wird als *gruppenbasierte Lizenzierung* bezeichnet. Wenn ein Benutzerkonto der Gruppe hinzugefügt oder aus ihr entfernt wird, werden die Lizenzen für die Gruppenabonnements dem Benutzerkonto automatisch zugewiesen oder aus ihm entfernt.

Für Microsoft 365 Enterprise konfigurieren Sie Azure AD-Sicherheitsgruppen, um beide Lizenzen zuzuweisen:

- Office 365 Enterprise E3 oder E5
- Enterprise Mobility + Security (EMS) E3 oder E5

Suchen Sie unter Verwendung der Gruppen, die Sie in Schritt 2 identifiziert haben, nach Gruppen, die eine Liste der Konten enthalten, wobei alle Benutzer in dieser Gruppe Office 365- und EMS-Lizenzen haben müssen. Stellen Sie sicher, dass Sie genug Lizenzen für alle Gruppenmitglieder haben. Wenn keine Lizenzen mehr vorhanden sind, werden neuen Benutzern keine Lizenzen zugewiesen, bis Lizenzen verfügbar werden.

>[!Note]
>Sie sollten  nicht die *gruppenbasierte Lizenzierung* für Gruppen konfigurieren, die Azure Business to Business (B2B)-Konten enthalten.
>

Weitere Informationen finden Sie unter [Grundlagen der gruppenbasierten Lizenzierung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Lesen Sie die [Schritte zum Konfigurieren der gruppenbasierten Lizenzierung für eine Azure-Sicherheitsgruppe](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

Die Ergebnisse dieses Abschnitts sind:

- Sie haben identifiziert, welche Sicherheitsgruppen für die gruppenbasierte Lizenzierung geeignet sind.
- Sie haben diese Gruppen für gruppenbasierte Lizenzierung konfiguriert.

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Automatisieren von Lizenzen und Gruppenmitgliedschaften](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-group-license) für diesen Abschnitt ansehen.

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Identitätsinfrastruktur](identity-exit-criteria.md)
