---
title: Verwenden Microsoft Teams Klassen mit Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrieren Microsoft Teams Klassen in Canvas
ms.openlocfilehash: 50e4e8ef912a8f19f379bba29b328a5a27358b5c
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256903"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Verwenden Microsoft Teams Klassen mit Canvas

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft Teams Klassen ist eine Learning Tools Interoperability (LTI)-App, die Lehrkräften und Schülern dabei hilft, problemlos zwischen ihrem Learning Management System (LMS) und Teams zu navigieren. Benutzer können direkt in ihrem LMS auf ihre Kursteams zugreifen, die ihrem Kurs zugeordnet sind.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Admin

Bevor Sie die Microsoft Teams Integration in Instructure Canvas verwalten, ist es wichtig, dass die **Azure-App "Microsoft-Teams-Sync-for-Canvas"** von Canvas vom Microsoft Office 365-Administrator Ihrer Bildungseinrichtung in Ihrem Microsoft Azure Mandanten genehmigt wird, bevor Sie das Canvas-Administratorsetup abschließen.

1. Melden Sie sich bei Canvas an.

2. Wählen Sie **den** Administratorlink in der globalen Navigation aus, und wählen Sie dann Ihr Konto aus.

3. Wählen Sie in der Administratornavigation den **Link Einstellungen** und dann die Registerkarte **"Integrationen" aus.**

4. Aktivieren Sie Microsoft Teams Synchronisierung, indem Sie die Umschaltfläche aktivieren.

   ![Teams-Synchronisierung](media/teams-sync.png)

5. Geben Sie Ihren Microsoft-Mandantennamen und Ihr Anmeldeattribut ein.

   Das Anmeldeattribut wird verwendet, um den Canvas-Benutzer einem Azure Active Directory Benutzer zuzuordnen.

6. Wählen Sie nach Abschluss **Einstellungen** aktualisieren aus.

7. Um den Zugriff für die **Azure-App "Microsoft-Teams-Sync-for-Canvas"** von Canvas zu genehmigen, wählen Sie den Link **"Mandantenzugriff gewähren"** aus. Sie werden zum Microsoft Identity Platform Admin Consent-Endpunkt umgeleitet.

   ![Berechtigungen](media/permissions.png)

8. Wählen Sie **Annehmen** aus.

## <a name="canvas-admin"></a>Canvas-Administrator

Richten Sie die Microsoft Teams LTI 1.3-Integration ein.

Als Canvas-Administrator müssen Sie die LTI-App Microsoft Teams Klassen in Ihrer Umgebung hinzufügen. Notieren Sie sich die LTI-Client-ID für die App.

 - Microsoft Teams Klassen – 170000000000570

1. Access **Admin settings**  >  **Apps**.

2. Wählen Sie **+App** aus, um die Teams LTI-Apps hinzuzufügen.

   ![Externe Apps](media/external-apps.png)

3. Wählen Sie **nach Client-ID** für Konfigurationstyp aus.

   ![App hinzufügen](media/add-app.png)

4. Geben Sie die bereitgestellte Client-ID ein, und wählen Sie dann **"Absenden"** aus.

   Sie werden feststellen, dass der Name der Microsoft Teams Klassen LTI-App für die Client-ID zur Bestätigung angegeben wird.

5. Wählen Sie **Installieren** aus.

   Die LTI-App Microsoft Teams Klassen wird der Liste der externen Apps hinzugefügt.
