---
title: Konfigurieren Microsoft 365 Lighthouse Portalsicherheit
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Informationen zum Konfigurieren der Portalsicherheit für verwaltete Dienstanbieter (Managed Service Providers, MSPs), die Microsoft 365 Lighthouse verwenden.
ms.openlocfilehash: 1e67903fc6c3dfd4e1949ef8c3e80ad4af12ad5c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395203"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>Konfigurieren Microsoft 365 Lighthouse Portalsicherheit

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nur für Partner verfügbar, die die [Anforderungen](m365-lighthouse-requirements.md)erfüllen. Wenn Ihre Organisation nicht über Microsoft 365 Lighthouse verfügt, lesen Sie ["Registrieren für Microsoft 365 Lighthouse".](m365-lighthouse-sign-up.md)

Der Schutz des Zugriffs auf Kundendaten, wenn ein Verwalteter Dienstanbieter (Managed Service Provider, MSP) Zugriffsberechtigungen an seine Mandanten delegiert hat, ist eine Priorität der Cybersicherheit. Microsoft 365 Lighthouse bietet sowohl erforderliche als auch optionale Funktionen, mit denen Sie Microsoft 365 Lighthouse Portalsicherheit konfigurieren können.

## <a name="set-up-multifactor-authentication-mfa"></a>Einrichten der mehrstufigen Authentifizierung (MFA)

Wie im Blogbeitrag [erwähnt, spielt Ihr Pa$$word keine Rolle:](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)

> "Ihr Kennwort spielt keine Rolle, aber MFA ist dies der Fall. Basierend auf unseren Studien ist Ihr Konto mehr als 99,9 % weniger wahrscheinlich kompromittiert, wenn Sie MFA verwenden."

Wenn Benutzer zum ersten Mal auf Microsoft 365 Lighthouse zugreifen, werden sie aufgefordert, MFA einzurichten, wenn ihr Microsoft 365 Konto noch nicht konfiguriert ist. Benutzer können erst dann auf Microsoft 365 Lighthouse zugreifen, wenn der erforderliche MFA-Einrichtungsschritt abgeschlossen ist. Weitere Informationen zu Authentifizierungsmethoden finden Sie unter [Einrichten ihrer Microsoft 365-Anmeldung für die mehrstufige Authentifizierung.](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)

## <a name="set-up-roles-to-manage-customer-tenants"></a>Einrichten von Rollen zum Verwalten von Kundenmandanten

Der Zugriff auf Kundendaten und -einstellungen in Microsoft 365 Lighthouse ist auf die Administrator-Agent- und Helpdesk-Agent-Rollen aus dem Cloud Solutions Provider (CSP)-Programm beschränkt.

Sie können überprüfen, welche Benutzer im Partnermandanten über die Rollen "Administrator-Agent" und "Helpdesk-Agent" verfügen, indem Sie die Sicherheitsgruppenmitgliedschaften auf der Seite ["Azure AD – Alle Gruppen"](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) überprüfen. Informationen zum Zuweisen von CSP-Programmrollen und anderen Berechtigungen zu Benutzern finden Sie unter [Zuweisen von Rollen und Berechtigungen für Benutzer.](/partner-center/permissions-overview) Wenn Sie als MSP noch nicht über delegierte Zugriffsberechtigungen für Kundenmandanten verfügen, erfahren Sie, wie Sie diese im Artikel "Abrufen von [Berechtigungen zum Verwalten des Diensts oder Abonnements eines Kunden"](/partner-center/customers-revoke-admin-privileges)abrufen können.

In der folgenden Tabelle sind die verschiedenen Microsoft 365 Lighthouse Seiten und die berechtigungen aufgeführt, die zum Anzeigen und Bearbeiten von Kundendaten und -einstellungen für die Administrator-Agent- und Helpdesk-Agent-Rollen erforderlich sind.<br><br>

| Microsoft 365 Lighthouse Seite | Administrator-Agent-Berechtigungen | Helpdesk-Agent-Berechtigungen |
|--|--|--|
| Startseite | <ul><li>Alle  anzeigen</li></ul> | <ul><li>Alle  anzeigen</li></ul> |
| Mandanten | <ul><li>Alle  anzeigen</li><li>Aktualisieren von Kundenkontakten und -websites</li><li>Anzeigen und Anwenden von Bereitstellungsplänen</li></ul> | <ul><li>Alle  anzeigen</li><li>Aktualisieren von Kundenkontakten und -websites</li><li>Anzeigen von Bereitstellungsplänen</li></ul> |
| Benutzer | <ul><li>Alle  anzeigen</li><li>Kennwort zurücksetzen</li><li>Anmeldung blockieren</li><li>MFA aktivieren</li></ul> | <ul><li>Alle  anzeigen</li><li>Kennwort zurücksetzen</li><li>Anmeldung blockieren</li></ul> |
| Geräte | <ul><li>Alle  anzeigen</li></ul> | <ul><li>Alle  anzeigen</li></ul> |
| Risiken | <ul><li>Alle  anzeigen</li><li>Ausführen eines Schnellscans</li><li>Vollständige Überprüfung ausführen</li><li>Gerät neu starten</li><li>Aktualisieren von Antivirus</li></ul> | <ul><li>Alle  anzeigen</li></ul> |
| Basislinien | <ul><li>Alle  anzeigen</li></ul> | <ul><li>Alle  anzeigen</li></ul> |
| Dienststatus | <ul><li>Alle anzeigen*</li></ul> | <ul><li>Alle anzeigen*</li></ul> |

> [!NOTE]
> Um die in der Tabelle mit * markierten Aktionen auszuführen, müssen Benutzer auch die Azure AD-Rolle im Partnermandanten haben, für die die folgende Eigenschaft festgelegt ist: **microsoft.office365.serviceHealth/allEntities/allTasks**. Eine Liste der Azure AD-Rollen finden Sie unter [integrierte Azure AD-Rollen.](/azure/active-directory/roles/permissions-reference)

Angesichts der umfassenden Berechtigungen, die der Administrator-Agent-Rolle zugeordnet sind, empfehlen wir, das Prinzip des [geringsten privilegierten Zugriffs](/azure/active-directory/develop/secure-least-privileged-access) einzuhalten, wenn ein Partnermandantenbenutzer als Administrator-Agent im Vergleich zum Helpdesk-Agent gekennzeichnet wird. Eine Möglichkeit dazu ist das Zuweisen der Helpdesk-Agent-Rolle zu den erforderlichen Partnermandantenbenutzern. Auf diese Weise können sie Kundendaten und -einstellungen anzeigen, aber keine allgemeinen Änderungen vornehmen. Verwenden Sie dann bei Bedarf die Just-in-Time-Zugriffsgenehmigungsfunktionen von Azure AD Privileged Identity Management (PIM), um Benutzern eine zeitlich beschränkte Administrator-Agent-Rolle zuzuweisen.

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Einrichten von Azure AD Privileged Identity Management (PIM)

MSPs können die Anzahl der Personen, die Zugriff auf sichere Informationen oder Ressourcen haben, mithilfe von Azure AD Privileged Identity Management (PIM) minimieren. PIM verringert die Wahrscheinlichkeit, dass eine böswillige Person Zugriff auf Ressourcen oder autorisierte Benutzer erhält, die eine sensible Ressource versehentlich beeinträchtigen. MSPs können Benutzern auch just-in-time privilegierten Zugriff auf Ressourcen gewähren und überwachen, was die festgelegten Benutzer mit ihrem privilegierten Zugriff tun.

> [!NOTE]
> Die Verwendung von Azure AD PIM erfordert eine Azure AD Premium P2-Lizenz im Partnermandanten.

Mit den folgenden Schritten werden Partnermandantenbenutzer mithilfe von Azure AD PIM auf zeitbezogene Administrator-Agent-Rollen erhöht:

1. Erstellen Sie eine rollenzuweisungsfähige Gruppe, wie im Artikel [Erstellen einer Gruppe zum Zuweisen von Rollen in Azure Active Directory](/azure/active-directory/roles/groups-create-eligible)beschrieben.

2. Wechseln Sie zu [Azure AD – Alle Gruppen,](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) und fügen Sie die neue Gruppe als Mitglied der Gruppe "Admin Agents" hinzu.

3. Richten Sie privilegierten Zugriff auf die neue Gruppe ein, wie im Artikel ["Zuweisen berechtigter Besitzer und Mitglieder für Privilegierte Zugriffsgruppen"](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)beschrieben.

Weitere Informationen finden Sie unter [Was ist Privileged Identity Management?](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="other-roles-and-permissions"></a>Andere Rollen und Berechtigungen

In der folgenden Tabelle sind die Partnermandantenrollen und die zugehörigen Berechtigungen aufgeführt.<br><br>

| Partnermandantenrollen | Berechtigungen innerhalb des Partnermandanten |
|--|--|
| Globaler Administrator des Partnermandanten | <ul><li>Registrieren Sie sich für Microsoft 365 Lighthouse im Microsoft 365 Admin Center.</li><li>Akzeptieren Sie partnerbezogene Vertragsänderungen während der Ersten Ausführung.</li><li>Anzeigen von Kundenmandanten auf der Seite "Mandanten".\*</li><li>Aktivieren und Inaktivieren eines Mandanten.\*</li><li>Aktualisieren von Kundenkontakten und -websites.\*</li><li>Erstellen, Aktualisieren und Löschen von Tags.\*</li><li>Zuweisen und Entfernen von Tags aus einem Kundenmandanten.\*</li></ul> |
| Administrator des Partnermandanten mit mindestens einem Mandanten<br> Azure AD-Rolle, die dem folgenden Eigenschaftensatz zugewiesen ist:<br> **microsoft.office365.supportTickets/allEntities/allTasks**<br> (Eine Liste der Azure AD-Rollen finden Sie unter [integrierte Azure AD-Rollen.)](/azure/active-directory/roles/permissions-reference) | <ul><li>Erstellen sie Microsoft 365 Lighthouse Serviceanfragen.</li></ul> |

> [!NOTE]
> Zurzeit muss der globale Administrator die Administrator-Agent-Rolle übernehmen, um die mit * in der Tabelle markierten Aktionen auszuführen.

## <a name="related-content"></a>Verwandte Inhalte

[Übersicht über Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (Artikel)\
[Registrieren für Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (Artikel)\
[faq zu Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (Artikel)