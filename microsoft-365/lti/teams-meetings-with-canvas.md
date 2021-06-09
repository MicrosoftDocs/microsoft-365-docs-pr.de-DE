---
title: Verwenden Microsoft Teams von Besprechungen mit Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrieren von Microsoft Teams Besprechungen in Canvas
ms.openlocfilehash: 8ccf1c1d45d38fa4a92b556146744a2c17cd5105
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821891"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Verwenden Microsoft Teams von Besprechungen mit Canvas

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft Teams Besprechungen ist eine LTI-App (Learning Tools Interoperability), mit der Lehrkräfte und Schüler problemlos zwischen ihrem Learning Management System (LMS) und Teams navigieren können. Benutzer können direkt in ihrem LMS auf ihre Kursteams zugreifen, die ihrem Kurs zugeordnet sind.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Admin

Bevor Sie die Microsoft Teams Integration in Instructure Canvas verwalten, ist es wichtig, dass die **Azure-App "Microsoft-Teams-Sync-for-Canvas"** von Canvas vom Microsoft Office 365-Administrator Ihrer Bildungseinrichtung in Ihrem Microsoft Azure Mandanten genehmigt wird, bevor Sie das Canvas-Administratorsetup abschließen.

1. Melden Sie sich bei Canvas an.
 
2. Wählen Sie **den** Administratorlink in der globalen Navigation aus, und wählen Sie dann Ihr Konto aus.

3. Wählen Sie in der Administratornavigation den **Link Einstellungen** und dann die Registerkarte **"Integrationen"** aus. 

4. Geben Sie Ihren Microsoft-Mandantennamen und Ihr Anmeldeattribut ein. 

   Das Anmeldeattribut wird verwendet, um den Canvas-Benutzer einem Azure Active Directory Benutzer zuzuordnen. 

5. Wählen Sie nach Abschluss **Einstellungen** aktualisieren aus.

6. Um den Zugriff für die **Azure-App "Microsoft-Teams-Sync-for-Canvas"** von Canvas zu genehmigen, wählen Sie den Link **"Mandantenzugriff gewähren"** aus. Sie werden zum Microsoft Identity Platform Admin Consent-Endpunkt umgeleitet.

   ![Berechtigungen](media/permissions.png)

7. Wählen Sie **Annehmen** aus.
 
8. Aktivieren Sie die Microsoft Teams Synchronisierung, indem Sie die Umschaltfläche aktivieren.

   ![Teams-Synchronisierung](media/teams-sync.png)

## <a name="canvas-admin"></a>Canvas-Administrator

Richten Sie die Microsoft Teams LTI 1.3-Integration ein.

Als Canvas-Administrator müssen Sie die LTI-App Microsoft Teams Besprechungen in Ihrer Umgebung hinzufügen. Notieren Sie sich die LTI-Client-ID für die App.

 - Microsoft Teams Besprechungen – 170000000000703

1. Access **Admin settings**  >  **Apps**.

2. Wählen Sie **+App** aus, um die Teams LTI-Apps hinzuzufügen. 
 
   ![Externe Apps](media/external-apps.png)

3. Wählen Sie **nach Client-ID** für Konfigurationstyp aus.

   ![App hinzufügen](media/add-app.png)

4. Geben Sie die angegebene Client-ID ein, und wählen Sie dann **"Absenden"** aus.
   
   Sie werden den Namen der LTI-App für Microsoft Teams Besprechungen für die Client-ID zur Bestätigung bemerken. 

5. Wählen Sie **Installieren** aus.

   Die LTI-App Microsoft Teams Besprechungen wird der Liste der externen Apps hinzugefügt.
