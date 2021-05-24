---
title: Einrichten von Microsoft Viva Learning (Preview) im Teams Admin Center
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Erfahren Sie, wie Sie Microsoft Viva Learning (Preview) im Teams konfigurieren.
ms.openlocfilehash: e5af676752064738e26f9b934a60973cb9b0200d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625298"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Einrichten von Microsoft Viva Learning (Preview) im Teams Admin Center

> [!NOTE]
> Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das möglicherweise erheblich geändert wird, bevor es kommerziell veröffentlicht wird. 

Der Teams installiert Viva Learning (Preview) und wendet Berechtigungsrichtlinien über das Teams Admin Center an.

1. Für die öffentliche Vorschau müssen Sie zuerst die Updaterichtlinie festlegen. Weitere Informationen finden Sie unter Teams website [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Melden Sie sich beim Teams Admin Center an.

    2. Wählen **Teams**  >  **Updaterichtlinien aus.**

    3. Klicken Sie auf **Hinzufügen**. 

    4. Benennen Sie die Updaterichtlinie, fügen Sie eine Richtlinie hinzu, und aktivieren Sie **Vorschaufeatures anzeigen.**

2. Der Administrator muss benutzer über das Richtlinienupdate benachrichtigen, damit er seinen Build in die öffentliche Vorschau für Teams. 

    1. Der Benutzer muss sein Profilbild auswählen – > Informationen – > Vorschau anzeigen.
   
        ![Obere Navigation in der Teams, die das Benutzerprofil zeigt](../media/learning/learning-app-select-profile-teams.png)
    
    2. Der Benutzer muss die Bedingungen der öffentlichen Vorschau akzeptieren.

        ![Wechseln zum öffentlichen Vorschau-Build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning, follow the process in the next section.

## <a name="manage-settings-for-viva-learning-preview"></a>Verwalten von Einstellungen für Viva Learning (Vorschau)

Sie müssen ein Administrator im Teams Admin Center sein, um diese Aufgaben ausführen zu können.

Führen Sie die folgenden Schritte aus, um Viva Learning (Vorschau) für Benutzer in Ihrer Organisation verfügbar zu machen:

1. Navigieren Sie in der linken Navigation des Teams Admin Center zu **Teams Apps**  >  **verwalten.**

   ![Linke Navigation im Teams Admin Center mit Teams apps und Manage apps.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. Geben Sie **auf** der Seite Apps verwalten im Suchfeld *"Viva learning"* ein, und wählen Sie dann **Viva Learning (Vorschau) aus.**

   ![Verwalten Sie die Seite apps im Teams Admin Center, das das Suchfeld zeigt.](../media/learning/learning-app-teams-manage-apps-page.png)

3. Auf der **Seite "Viva Learning(Preview)"**

   1. Wählen **Sie unter Status** die Option **Zum** Aktivieren von "Viva Learning" (Vorschau) zugelassen aus.

   2. Wechseln Sie **Einstellungen** Registerkarte unter **App-Einstellungen** zum Microsoft 365 Admin Center, um [Lerninhaltsquellen zu konfigurieren.](content-sources-365-admin-center.md)

   ![Lernseite im Teams Admin Center mit Status- und App-Einstellungen.](../media/learning/learning-app-teams-learning-page.png)

4. Wechseln **Sie nach** Verwalten  von App-Einstellungen zu Berechtigungsrichtlinien und **Setuprichtlinien,** um Mitarbeitern, die im Rahmen der Teilnahme Ihrer Organisation an der Vorschau Zugriff auf Viva Learning (Preview) haben sollen, Die Berechtigung zu erteilen.

> [!NOTE]
>  Wenn Sich Ihre Organisation im Rahmen des TEAMS TAP100-Programms in Ring 4.0 befindet, müssen Sie möglicherweise genehmigte Benutzer in Ring 3.0 für den Zugriff auf "Viva Learning" (Vorschau) aktivieren. <br><br>Im Rahmen der Vorschau wird Viva Learning (Preview) in Ring 3.0 veröffentlicht. Wenn Sich Ihre Organisation in Ring 4.0 befindet, wird auf der Seite Apps verwalten kein Viva Learning (Preview) **angezeigt.** Zum Testen der App müssen Sie eine benutzerdefinierte App-Berechtigungsrichtlinie erstellen, sie auf Alle Apps zulassen festlegen und sie genehmigten Benutzern in Ring 3.0 zuweisen.  <br><br>   ![TAP-AppsPermission-Plcy-Seite mit Ausgewählte Apps zulassen.](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>Nächster Schritt

[Konfigurieren von Lerninhaltsquellen für Viva Learning (Vorschau) im Microsoft 365 Admin Center](content-sources-365-admin-center.md)
