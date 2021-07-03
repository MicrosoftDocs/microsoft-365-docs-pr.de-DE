---
title: Hinzufügen und Überprüfen von Administrator-Kontakten im Administratorportal
description: Teilen Sie uns mit, wer für jeden Fokusbereich kontaktiert werden soll.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ba4f1b0e4b2e00334dbffb4bf0aa9edb1b8c5622
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286921"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Hinzufügen und Überprüfen von Administrator-Kontakten im Administratorportal

Es gibt verschiedene Möglichkeiten, wie Microsoft Managed Desktop Dienst mit Kunden kommuniziert. Um die Kommunikation zu optimieren und sicherzustellen, dass wir die richtigen Personen überprüfen, müssen Sie eine Reihe von Administratorkontakten bereitstellen. Microsoft Managed Desktop IT-Vorgänge wenden sich an diese Personen, um Hilfe bei der Behandlung von Problemen für Ihren Mandanten zu erhalten.

> [!IMPORTANT]
> Möglicherweise haben Sie diese Kontakte bereits im Verwaltungsportal hinzugefügt. Wenn dies der Fall ist, nehmen Sie sich einen Moment Zeit, um zu überprüfen, ob die Kontaktliste korrekt ist, da Microsoft Managed Desktop in der Lage sein **muss,** sie zu erreichen, wenn ein schwerwiegender Vorfall auftritt.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory Zugriff für Microsoft Managed Desktop-Verwaltungsportal

Microsoft Managed Desktop Das Verwaltungsportal erfordert, dass Personen, die auf das Portal zugreifen, über eine der folgenden Azure Active Directory (AD)-Rollen verfügen:

- Globaler Administrator
- Intune-Dienstadministrator
- Globaler Leser
- Dienstsupportadministrator

Der globale Administrator muss der globale Administrator sein, der Ihre Organisation in Microsoft Managed Desktop registriert. Alle fünf Rollen haben den gleichen Zugriff innerhalb des Verwaltungsportals, um Aufgaben zu initiieren und anzuzeigen. Weitere Informationen zum Zuweisen dieser Rollen in Azure AD finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

## <a name="admin-contact-areas-of-focus"></a>Admin-Kontaktbereiche im Fokus

Administratorkontakte sollten die beste Person oder Gruppe sein, die Fragen beantworten und Entscheidungen für verschiedene Schwerpunktbereiche treffen kann. **Microsoft Managed Desktop Vorgänge wenden sich an diese Administratorkontakte, um Fragen zu Supportanfragen zu erhalten, die vom Kunden eingereicht wurden.** Diese Administratorkontakte erhalten Benachrichtigungen für Supportanfragen und neue Nachrichten. Zu diesen Bereichen gehören:

Fokusbereich | Für Fragen zu
--- | ---
App-Verpackung | Problembehandlung beim Packen von Apps
Geräte | Geräteintegrität, Problembehandlung bei Microsoft Managed Desktop Geräten
Sicherheit | Behandeln von Sicherheitsproblemen mit Microsoft Managed Desktop Geräten
IT-Helpdesk | in Fällen, in denen unsere Supportmitarbeiter Benutzertickets außerhalb von Microsoft Managed Desktop Supportbereichen übergeben 
Andere | Für Probleme, die nicht von anderen Bereichen abgedeckt werden

**Jeder, den Sie für diese Kontakte auswählen, muss über das Wissen und die Autorität verfügen, entscheidungen für Ihre Microsoft Managed Desktop Umgebung zu treffen.** Wenn Sie Ihre Microsoft Managed Desktop Umgebung integrieren, werden Sie aufgefordert, Kontakte für Ihr lokales Helpdesk und Die Sicherheit hinzuzufügen. 

Administratorkontakte sind erforderlich, wenn Sie [eine Supportanfrage senden.](../service-description/support.md) Sie benötigen einen Administratorkontakt für den Fokusbereich der Supportanfrage.

**So fügen Sie Administratorkontakte hinzu**

1. Melden Sie sich bei [Microsoft Endpoint Manager](https://endpoint.microsoft.com)an.

2. Suchen Sie unter **Mandantenverwaltung** nach dem **Abschnitt Microsoft Managed Desktop,** und wählen Sie dann **Administratorkontakte** aus.

3. Klicken Sie auf **Hinzufügen**.

4. Wählen Sie einen **Fokusbereich aus,** und geben Sie die Informationen für den Kontakt ein. 

    ![die Liste der Schwerpunktbereiche, z. B. "Andere", "Apps" und "Sicherheit".](../../media/areaoffocus.png)

5. Wiederholen Sie dies für jeden Fokusbereich.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte für die ersten Schritte mit Microsoft Managed Desktop

1. Hinzufügen und Überprüfen von Administratorkontakten im Verwaltungsportal (dieses Thema)
2. [Bedingten Zugriff anpassen](conditional-access.md)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. [Installieren des Intune Company Portals auf Geräten](company-portal.md)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Richten Sie Microsoft Managed Desktop-Geräte ein](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. [Stellen Sie Anwendungen auf Geräten bereit](deploy-apps.md)
