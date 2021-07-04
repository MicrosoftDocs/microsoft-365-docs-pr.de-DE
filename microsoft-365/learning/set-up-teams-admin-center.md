---
title: Einrichten von Microsoft Viva Learning (Vorschau) im Teams Admin Center
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Erfahren Sie, wie Sie Microsoft Viva Learning (Vorschau) im Teams Admin Center konfigurieren.
ms.openlocfilehash: 99e63210e8f8c10e3721c35fb69df7880c7e1929
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290219"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Einrichten von Microsoft Viva Learning (Vorschau) im Teams Admin Center

> [!NOTE]
> Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das vor der kommerziellen Veröffentlichung erheblich geändert werden kann. 

Der Teams-Administrator muss bestimmte Schritte ausführen, um Viva Learning (Vorschau) für seine Benutzer im Mandanten zu aktivieren. Diese Schritte variieren je nach Aktivierung des Mandanten: [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) oder [ *Private Preview* (oder Beta).](set-up-teams-admin-center.md#private-preview-tenants)

## <a name="public-preview-tenants"></a>Öffentliche Vorschaumandanten

### <a name="administrator-steps-for-public-preview-tenants"></a>Administratorschritte für Öffentliche Vorschaumandanten

Da viva Learning (Vorschau) noch nicht allgemein verfügbar ist, sind bestimmte Schritte erforderlich, um die Features zu aktivieren und Berechtigungen für bestimmte Benutzer oder Gruppen festzulegen. 

1. Aktivieren Sie public Preview-Features für Viva Learning (Vorschau)-Benutzer.

    a. Ändern Sie Teams Updaterichtlinie, um Public Preview-Features zu aktivieren. Siehe [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).

    b. Aktivieren Sie die Updaterichtlinie für Benutzer oder Gruppen, die Viva Learning (Vorschau) testen. Siehe [Zuweisen von Richtlinien zu Benutzern und Gruppen.](/microsoftteams/assign-policies-users-and-groups)

2. Ändern Sie die App-Berechtigungsrichtlinie für Benutzer von Viva Learning (Vorschau).

    a. Sofern sie nicht aktuell Teil der globalen Richtlinie ist, lassen Sie alle Microsoft-Apps in der App-Berechtigungsrichtlinie zu. Weitere Informationen finden [Sie unter Verwalten von App-Berechtigungsrichtlinien in Microsoft Teams.](/microsoftteams/teams-app-permission-policies) 

    b. Aktivieren Sie die App-Berechtigungsrichtlinie für Benutzer oder Gruppen, die Viva Learning (Vorschau) testen. Siehe [Zuweisen von Richtlinien zu Benutzern und Gruppen.](/microsoftteams/assign-policies-users-and-groups)

3. Benachrichtigen Sie Benutzer, die Viva Learning (Vorschau) testen werden, [ihren Buildclient für Teams in die öffentliche Vorschau zu wechseln.](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)

> [!IMPORTANT]
> Für Öffentliche Vorschau-Mandanten wird Viva Learning (Vorschau) erst in der endgültigen Produktversion in **verwalteten Apps** im Teams Admin Center angezeigt. Aktivierte Benutzer der öffentlichen Vorschau können Viva Learning (Vorschau) jedoch im Teams App Store finden und verwenden, sobald die richtigen Richtlinien und Berechtigungen eingerichtet wurden.

### <a name="user-steps-for-public-preview-tenants"></a>Benutzerschritte für Öffentliche Vorschaumandanten

Benutzer, die für öffentliche Vorschautests aktiviert wurden – durch Aktivieren der [zuvor beschriebenen Richtlinien](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) – müssen in ihrem Teams Client [zur öffentlichen Vorschau wechseln.](/microsoftteams/public-preview-doc-updates#enable-public-preview)

1. Benutzer müssen ihr Profilbild > **Informationen**  >  **zur öffentlichen Vorschau** auswählen.

    ![Obere Navigation in der Teams-Anwendung, die das Profil des Benutzers anzeigt](../media/learning/learning-app-select-profile-teams.png)

2. Benutzer müssen die Allgemeinen Geschäftsbedingungen für die öffentliche Vorschau akzeptieren.

    ![Wechseln zum öffentlichen Vorschaubuild](../media/learning/learning-app-switch-to-public-preview.png)

3. Benutzer finden Viva Learning (Vorschau) jetzt im Teams App Store und beginnen mit der Verwendung.

## <a name="private-preview-tenants"></a>Private Preview-Mandanten

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a>Administratorschritte für Private Preview-Mandanten (oder Beta-Mandanten)

Für Private Preview-Mandanten gibt es keine zusätzlichen Richtlinien, die aktiviert werden müssen. Viva Learning (Vorschau) muss jedoch für Benutzer in Ihrer Organisation zur Verfügung gestellt werden.

1. Wechseln Sie in der linken Navigationsleiste des Teams Admin Centers zu **Teams Apps** Verwalten  >  **von Apps.**

   ![Linksnavigation im Teams Admin Center mit Teams Abschnitt "Apps verwalten".](../media/learning/learning-app-teams-manage-apps-nav.png)

2. Geben Sie auf der Seite **"Apps verwalten"** im Suchfeld *Viva Learning* ein, und wählen Sie dann **Viva Learning (Vorschau)** aus.

   ![Seite "Apps verwalten" im Teams Admin Center, auf der das Suchfeld angezeigt wird.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   ![Learning Seite im Teams Admin Center, auf der der Abschnitt "Status- und App-Einstellungen" angezeigt wird.](../media/learning/learning-app-teams-learning-page.png)

<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a>Nächster Schritt

[Konfigurieren von Lerninhaltsquellen für Viva Learning (Vorschau) im Microsoft 365 Admin Center](content-sources-365-admin-center.md)
