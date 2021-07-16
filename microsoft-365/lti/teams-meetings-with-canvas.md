---
title: Verwenden von Microsoft Teams Besprechungen mit Canvas
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
description: Integrieren von Microsoft Teams Besprechungen in Canvas
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454673"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Verwenden von Microsoft Teams Besprechungen mit Canvas

Microsoft Teams Besprechungen ist eine LTI-App (Learning Tools Interoperability), mit der Lehrkräfte und Schüler problemlos zwischen ihrem Learning Management System (LMS) und Teams navigieren können. Benutzer können direkt in ihrem LMS auf ihre Kursteams zugreifen, die ihrem Kurs zugeordnet sind.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Admin

Bevor Sie die Microsoft Teams Integration in Instructure Canvas verwalten, ist es wichtig, dass die **Azure-App "Microsoft-Teams-Sync-for-Canvas"** von Canvas vom Microsoft Office 365-Administrator Ihrer Bildungseinrichtung in Ihrem Microsoft Azure Mandanten genehmigt wird, bevor Sie das Canvas-Administratorsetup abschließen.

1. Melden Sie sich bei Canvas an.

2. Wählen Sie **den** Administratorlink in der globalen Navigation aus, und wählen Sie dann Ihr Konto aus.

3. Wählen Sie in der Administratornavigation den **Link Einstellungen** und dann die Registerkarte **"Integrationen" aus.**

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

 - Microsoft Teams-Besprechungen – 17000000000703

1. Access **Admin settings**  >  **Apps**.

2. Wählen Sie **+App** aus, um die Teams LTI-Apps hinzuzufügen.

   ![Externe Apps](media/external-apps.png)

3. Wählen Sie **nach Client-ID** für Konfigurationstyp aus.

   ![App hinzufügen](media/add-app.png)

4. Geben Sie die bereitgestellte Client-ID ein, und wählen Sie dann **"Absenden"** aus.

   Sie werden den Namen der LTI-App für Microsoft Teams Besprechungen für die Client-ID zur Bestätigung bemerken.

5. Wählen Sie **Installieren** aus.

   Die LTI-App Microsoft Teams Besprechungen wird der Liste der externen Apps hinzugefügt.
   
## <a name="enable-for-canvas-courses"></a>Aktivieren für Canvas-Kurse

Um das LTI innerhalb eines Kurses zu verwenden, muss ein Kursleiter des Canvas-Kurses die Integrationssynchronisierung aktivieren. Jeder Kurs muss von einem Kursleiter aktiviert werden, damit ein entsprechender Teams erstellt werden kann. Es gibt keinen globalen Mechanismus für Teams Erstellung. Dies wurde aus Vorsichtsmaßnahme entwickelt, um zu verhindern, dass unerwünschte Teams erstellt werden.

Bitte lesen Sie die [Dokumentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) ihrer Dozenten, um die LTI für jeden Kurs zu aktivieren und das Integrationssetup zu beenden.
