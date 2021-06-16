---
title: Berechtigungen im Microsoft 365 Defender-Portal
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Administratoren erfahren, wie Sie Berechtigungen im Microsoft 365 Defender-Portal für alle sicherheitsrelevanten Aufgaben verwalten.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4ed1d90bdc6e222d44179a77e9617d05909a4258
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926463"
---
# <a name="permissions-in-the-microsoft-365-defender-portal"></a>Berechtigungen im Microsoft 365 Defender-Portal

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Ihre Organisation muss Sicherheitsszenarien verwalten, die alle Microsoft 365-Dienste umfassen. Und Sie benötigen die Flexibilität, die richtigen Administratorberechtigungen für die richtigen Personen in Ihrer Organisation bereitzustellen.

Das Microsoft 365 Defender-Portal in <https://security.microsoft.com> unterstützt das direkte Verwalten von Berechtigungen für Benutzer, die Sicherheitsaufgaben in Microsoft 365 ausführen. Mithilfe des Microsoft 365 Defender-Portal können Sie Berechtigungen zentral für alle Aufgaben im Zusammenhang mit Sicherheit verwalten.

Zum Verwalten von Berechtigungen wechseln Sie im Microsoft 365 Defender-Portal zu **Berechtigungen und Rollen** oder <https://security.microsoft.com/securitypermissions>. Sie müssen ein **globaler Administrator** oder ein Mitglied der Rollengruppe **Organisationsverwaltung** im Microsoft 365 Defender-Portal sein. Insbesondere ermöglicht die Rolle **Rollenverwaltung** Benutzern das Anzeigen, Erstellen und Ändern von Rollengruppen im Microsoft 365 Defender-Portal. Standardmäßig wird diese Rolle nur der Rollengruppe **Organisationsverwaltung** zugewiesen.

> [!NOTE]
> Informationen zu Berechtigungen im Microsoft 365 Compliance Center finden Sie unter [Berechtigungen im Microsoft 365 Compliance Center](../../compliance/microsoft-365-compliance-center-permissions.md).

## <a name="relationship-of-members-roles-and-role-groups"></a>Beziehung zwischen Mitgliedern, Rollen und Rollengruppen

Die Berechtigungen im Microsoft 365 Defender-Portal basieren auf dem Berechtigungsmodell der rollenbasierten Zugriffssteuerung (Role Based Access Control, RBAC). Das RBAC ist das gleiche Berechtigungsmodell, das von den meisten Microsoft 365-Diensten verwendet wird. Wenn Sie sich also mit der Berechtigungsstruktur in diesen Diensten auskennen, wird Ihnen das Erteilen von Berechtigungen im Microsoft 365 Defender-Portal sehr vertraut sein.

Eine **Rolle** erteilt ihnen die Berechtigungen zum Ausführen einer Reihe von Aufgaben.

Eine **Rollengruppe** besteht aus einer Reihe von Rollen, mit denen Personen ihre Aufgaben im Microsoft 365 Defender-Portal erfüllen können. Die Rollengruppe „Angriffssimulatoradministratoren“ umfasst z. B. die Rolle des Angriffssimulatoradministrators, zum Erstellen und Verwalten aller Aspekte der Schulung zur Angriffssimulation.

Das Microsoft 365 Defender-Portal enthält Standardrollengruppen für die gängigsten Aufgaben und am häufigsten verwendeten Funktionen, die Sie zuweisen müssen. Allgemein empfiehlt es sich, den Standardrollengruppen einzelne Benutzer einfach als **Mitglieder** hinzuzufügen.

![Diagramm mit dem Verhältnis von Rollengruppen zu Rollen und Elementen](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-microsoft-365-defender-portal"></a>Rollen und Rollengruppen im Microsoft 365 Defender-Portal

Die folgenden Arten von Rollen und Rollengruppen sind im Microsoft 365 Defender-Portal unter **Berechtigungen und Rollen** verfügbar:

- **Azure AD-Rollen**: Sie können die Rollen und zugewiesenen Benutzer anzeigen, sie aber nicht direkt im Microsoft 365 Defender-Portal verwalten. Azure AD-Rollen sind zentrale Rollen, die Berechtigungen für **alle** Microsoft 365-Dienste zuweisen.

- **Rollen für E-Mails und Zusammenarbeit**: Hierbei handelt es sich um dieselben Rollengruppen, die im Security & Compliance Center zur Verfügung stehen, Sie können sie aber direkt im Microsoft 365 Defender-Portal verwalten. Die hier zugewiesenen Berechtigungen gelten speziell für das Microsoft 365 Defender-Portal, das Microsoft 365 Compliance Center sowie das Security & Compliance Center und umfassen nicht alle Berechtigungen, die in anderen Microsoft 365-Workloads erforderlich sind.

![Seite „Berechtigungen und Rollen“ im Microsoft 365 Defender-Portal](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-microsoft-365-defender-portal"></a>Azure AD-Rollen im Microsoft 365 Defender-Portal

Wenn Sie zu **Rollen für E-Mails und Zusammenarbeit** \> **Berechtigungen und Rollen** \> **Azure AD-Rollen** \> **Rollen** (oder direkt zu <https://security.microsoft.com/aadpermissions>) wechseln, werden die Azure AD-Rollen angezeigt, die in diesem Abschnitt beschrieben werden.

Wenn Sie eine Rolle auswählen, wird ein Detailflyout mit der Beschreibung der Rolle und den Benutzerzuweisungen angezeigt. Um diese Zuweisungen aber zu verwalten, müssen Sie im Detailflyout auf **Mitglieder in Azure AD verwalten** klicken.

![Verknüpfung zum Verwalten von Standardbenutzerberechtigungen in Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

Weitere Informationen finden Sie unter [Anzeigen und Zuweisen von Administratorrollen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

<br>

****

|Rolle|Beschreibung|
|---|---|
|**Globaler Administrator**|Zugriff auf alle Verwaltungsfunktionen in allen Microsoft 365-Diensten. Nur globale Administratoren können weitere Administratorrollen zuweisen. Weitere Informationen finden Sie unter [Globaler Administrator/Unternehmensadministrator](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Compliancedatenadministrator**|Verfolgen Sie die Daten Ihrer Organisation in Microsoft 365 nach, stellen Sie sicher, dass sie geschützt sind, und erhalten Sie Einblicke in alle Probleme, um Risiken zu minimieren. Weitere Informationen finden Sie unter [Compliancedatenadministrator](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Complianceadministrator**|Tragen Sie dazu bei, dass Ihre Organisation alle behördlichen Bestimmungen einhält und eDiscovery-Fälle verwalten sowie Richtlinien zur Datengovernance über Microsoft 365-Standorte, -Identitäten und -Apps hinweg aufrechterhalten kann. Weitere Informationen finden Sie unter [Complianceadministrator](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Sicherheitsoperator**|Zeigen Sie aktive Bedrohungen für Ihre Microsoft 365-Benutzer, -Geräte und -Inhalte an und untersuchen und reagieren Sie auf sie. Weitere Informationen finden Sie unter [Sicherheitsoperator](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Benutzer mit Leseberechtigung für Sicherheitsfunktionen**|Zeigen Sie aktive Bedrohungen für Ihre Microsoft 365-Benutzer, -Geräte und -Inhalte an und untersuchen Sie diese; Sie besitzen jedoch (im Gegensatz zum Sicherheitsoperator) keine Berechtigung dazu, dagegen Maßnahmen zu ergreifen. Weitere Informationen finden Sie unter [Benutzer mit Leseberechtigung für Sicherheitsfunktionen](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Sicherheitsadministrator**|Steuern Sie die Gesamtsicherheit Ihres Unternehmens, indem Sie Sicherheitsrichtlinien verwalten, Sicherheitsanalysen und Berichte zu Microsoft 365-Produkten überprüfen und im Hinblick auf Bedrohungen immer auf dem neuesten Stand bleiben. Weitere Informationen finden Sie unter [Sicherheitsadministrator](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Globaler Leser**|Die Version mit reiner Leseberechtigung der Rolle **globaler Administrator**. Zeigen Sie alle Einstellungen und Verwaltungsinformationen in Microsoft 365 an. Weitere Informationen finden Sie unter [Globaler Leser](/azure/active-directory/roles/permissions-reference#global-reader).|
|**Angriffssimulationsadministrator**|Erstellen und verwalten Sie alle Aspekte einer [Angriffssimulation](attack-simulation-training.md): Erstellung und Einführung/Planung einer Simulation sowie Überprüfung der Ergebnisse von Simulationen. Weitere Informationen finden Sie unter [Angriffssimulationsadministrator](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).|
|**Angriffsnutzlastautor**|Erstellen Sie Angriffsnutzlasten, ohne sie tatsächlich zu starten oder zu planen. Weitere Informationen finden Sie unter [Angriffsnutzlastautor](/azure/active-directory/roles/permissions-reference#attack-payload-author).|
|

### <a name="email--collaboration-roles-in-the-microsoft-365-defender-portal"></a>E-Mail- und Zusammenarbeitsrollen im Microsoft 365 Defender-Portal

Wenn Sie zu **Rollen für E-Mails und Zusammenarbeit** \> **Berechtigungen und Rollen** \> **Rollen für E-Mails und Zusammenarbeit** \> **Rollen** (oder direkt zu <https://security.microsoft.com/emailandcollabpermissions>) wechseln, werden die gleichen Rollengruppen wie im Security & Compliance Center angezeigt.

Vollständige Informationen zu diesen Rollengruppen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

#### <a name="modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal"></a>E-Mail- und Zusammenarbeitsrollen-Mitgliedschaft im Microsoft 365 Defender-Portal ändern

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Rollen für E-Mails und Zusammenarbeit** \> **Berechtigungen und Rollen** \> **Rollen für E-Mails und Zusammenarbeit** \> **Rollen**.

2. Wählen Sie auf der sich öffnenden Seite **Berechtigungen** die Rollengruppe, die Sie ändern möchten, aus der Liste aus. Sie können auf die Spaltenüberschrift **Name** klicken, um die Liste nach Namen zu sortieren, oder Sie können auf **Suchen** ![Symbol „Suchen2](../../media/m365-cc-sc-search-icon.png) klicken, um die Rollengruppe zu suchen.

3. Klicken Sie im angezeigten Flyout der Rollengruppendetails im Abschnitt **Mitglieder** auf **Bearbeiten**.

4. Führen Sie in der angezeigten Seite **Mitglieder auswählen/bearbeiten** einen der folgenden Schritte aus:
   - Wenn keine Rollengruppenmitglieder vorhanden sind, klicken Sie auf **Mitglieder auswählen**.
   - Wenn Rollengruppenmitglieder vorhanden sind, klicken Sie auf **Bearbeiten**.

5. Führen Sie im angezeigten Flyout **Mitglieder auswählen** einen der folgenden Schritte aus:

   - Klicken Sie auf **Hinzufügen**. Wählen Sie in der nun angezeigten Liste der Benutzer einen oder mehrere Benutzer aus. Sie können auch auf **Suchen** ![Symbol „Suchen“](../../media/m365-cc-sc-search-icon.png) klicken, um Benutzer zu suchen und auszuwählen.

     Wenn Sie die Benutzer ausgewählt haben, die hinzugefügt werden sollen, klicken Sie auf **Hinzufügen**.

   - Klicken Sie auf **Entfernen**. Aktivieren Sie eines oder mehrere der vorhandenen Mitglieder. Sie können auch auf **Suchen** ![Symbol „Suchen“](../../media/m365-cc-sc-search-icon.png) klicken, um Mitglieder zu suchen und auszuwählen.

     Wenn Sie die Benutzer ausgewählt haben, die entfernt werden sollen, klicken Sie auf **Entfernen**.

6. Zurück im Flyout **Mitglieder auswählen** klicken Sie auf **Fertig**.

7. Zurück auf der Seite **Mitglieder bearbeiten/auswählen**, klicken Sie auf **Speichern**.

8. Zurück auf dem Flyout für Rollengruppendetails klicken Sie auf **Fertig**.
