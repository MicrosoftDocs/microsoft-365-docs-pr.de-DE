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
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454685"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="13a0d-103">Verwenden Microsoft Teams Klassen mit Canvas</span><span class="sxs-lookup"><span data-stu-id="13a0d-103">Use Microsoft Teams classes with Canvas</span></span>

<span data-ttu-id="13a0d-104">Microsoft Teams Klassen ist eine Learning Tools Interoperability (LTI)-App, die Lehrkräften und Schülern dabei hilft, problemlos zwischen ihrem Learning Management System (LMS) und Teams zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="13a0d-104">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="13a0d-105">Benutzer können direkt in ihrem LMS auf ihre Kursteams zugreifen, die ihrem Kurs zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="13a0d-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="prerequisites-before-deployment"></a><span data-ttu-id="13a0d-106">Voraussetzungen vor der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="13a0d-106">Prerequisites Before Deployment</span></span>

> [!NOTE]
> <span data-ttu-id="13a0d-107">Die aktuelle Klasse Teams LTI unterstützt nur die Synchronisierung von Canvas-Benutzern mit Microsoft Azure Active Directory (AAD) in einem begrenzten Bereich.</span><span class="sxs-lookup"><span data-stu-id="13a0d-107">The current Class Teams LTI only supports syncing Canvas users with Microsoft Azure Active Directory (AAD) in a limited scope.</span></span> 
> - <span data-ttu-id="13a0d-108">Ihr Mandant muss eine genaue Übereinstimmung zwischen einem Canvas-Feld (E-Mail, Benutzer-ID oder SIS-ID) und dem UPN in Microsoft AAD aufweisen.</span><span class="sxs-lookup"><span data-stu-id="13a0d-108">Your tenant must have an exact match between a Canvas field (email, user ID, or SIS ID) and the UPN in Microsoft AAD.</span></span> <span data-ttu-id="13a0d-109">Wir arbeiten daran, die Flexibilität der Synchronisierungsfunktionalität zu erweitern, aber in der Zwischenzeit werden alle Benutzer in Canvas, die keinem UPN in AAD zugeordnet sind, nicht zur Teams Klasse hinzugefügt, die mit Canvas synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="13a0d-109">We are working to expand flexibility to the syncing functionality, but in the meantime, any users in Canvas not matched to a UPN in AAD will not be added to the Teams class synced with Canvas.</span></span> 
> - <span data-ttu-id="13a0d-110">Nur ein einzelner Microsoft-Mandant kann zum Zuordnen von Benutzern zwischen Canvas und Microsoft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13a0d-110">Only a single Microsoft tenant can be used for mapping users between Canvas and Microsoft.</span></span>
> - <span data-ttu-id="13a0d-111">Sie müssen SDS deaktivieren, bevor Sie die Klasse Teams LTI verwenden, um duplizierte Gruppen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="13a0d-111">You will have to turn off SDS before using the Class Teams LTI in order to avoid duplication of groups.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="13a0d-112">Microsoft Office 365 Admin</span><span class="sxs-lookup"><span data-stu-id="13a0d-112">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="13a0d-113">Bevor Sie die Microsoft Teams Integration in Instructure Canvas verwalten, ist es wichtig, dass die **Azure-App "Microsoft-Teams-Sync-for-Canvas"** von Canvas vom Microsoft Office 365-Administrator Ihrer Bildungseinrichtung in Ihrem Microsoft Azure Mandanten genehmigt wird, bevor Sie das Canvas-Administratorsetup abschließen.</span><span class="sxs-lookup"><span data-stu-id="13a0d-113">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="13a0d-114">Melden Sie sich bei Canvas an.</span><span class="sxs-lookup"><span data-stu-id="13a0d-114">Sign in to Canvas.</span></span>

2. <span data-ttu-id="13a0d-115">Wählen Sie **den** Administratorlink in der globalen Navigation aus, und wählen Sie dann Ihr Konto aus.</span><span class="sxs-lookup"><span data-stu-id="13a0d-115">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="13a0d-116">Wählen Sie in der Administratornavigation den **Link Einstellungen** und dann die Registerkarte **"Integrationen" aus.**</span><span class="sxs-lookup"><span data-stu-id="13a0d-116">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="13a0d-117">Aktivieren Sie Microsoft Teams Synchronisierung, indem Sie die Umschaltfläche aktivieren.</span><span class="sxs-lookup"><span data-stu-id="13a0d-117">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![Teams-Synchronisierung](media/teams-sync.png)

5. <span data-ttu-id="13a0d-119">Geben Sie Ihren Microsoft-Mandantennamen und Ihr Anmeldeattribut ein.</span><span class="sxs-lookup"><span data-stu-id="13a0d-119">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="13a0d-120">Das Anmeldeattribut wird verwendet, um den Canvas-Benutzer einem Azure Active Directory Benutzer zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="13a0d-120">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="13a0d-121">Wählen Sie nach Abschluss **Einstellungen** aktualisieren aus.</span><span class="sxs-lookup"><span data-stu-id="13a0d-121">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="13a0d-122">Um den Zugriff für die **Azure-App "Microsoft-Teams-Sync-for-Canvas"** von Canvas zu genehmigen, wählen Sie den Link **"Mandantenzugriff gewähren"** aus.</span><span class="sxs-lookup"><span data-stu-id="13a0d-122">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="13a0d-123">Sie werden zum Microsoft Identity Platform Admin Consent-Endpunkt umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="13a0d-123">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![Berechtigungen](media/permissions.png)

8. <span data-ttu-id="13a0d-125">Wählen Sie **Annehmen** aus.</span><span class="sxs-lookup"><span data-stu-id="13a0d-125">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="13a0d-126">Canvas-Administrator</span><span class="sxs-lookup"><span data-stu-id="13a0d-126">Canvas Admin</span></span>

<span data-ttu-id="13a0d-127">Richten Sie die Microsoft Teams LTI 1.3-Integration ein.</span><span class="sxs-lookup"><span data-stu-id="13a0d-127">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="13a0d-128">Als Canvas-Administrator müssen Sie die LTI-App Microsoft Teams Klassen in Ihrer Umgebung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="13a0d-128">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="13a0d-129">Notieren Sie sich die LTI-Client-ID für die App.</span><span class="sxs-lookup"><span data-stu-id="13a0d-129">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="13a0d-130">Microsoft Teams Klassen – 170000000000570</span><span class="sxs-lookup"><span data-stu-id="13a0d-130">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="13a0d-131">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="13a0d-131">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="13a0d-132">Wählen Sie **+App** aus, um die Teams LTI-Apps hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="13a0d-132">Select **+ App** to add the Teams LTI apps.</span></span>

   ![Externe Apps](media/external-apps.png)

3. <span data-ttu-id="13a0d-134">Wählen Sie **nach Client-ID** für Konfigurationstyp aus.</span><span class="sxs-lookup"><span data-stu-id="13a0d-134">Select **By Client ID** for configuration type.</span></span>

   ![App hinzufügen](media/add-app.png)

4. <span data-ttu-id="13a0d-136">Geben Sie die bereitgestellte Client-ID ein, und wählen Sie dann **"Absenden"** aus.</span><span class="sxs-lookup"><span data-stu-id="13a0d-136">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="13a0d-137">Sie werden feststellen, dass der Name der Microsoft Teams Klassen LTI-App für die Client-ID zur Bestätigung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="13a0d-137">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="13a0d-138">Wählen Sie **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="13a0d-138">Select **Install**.</span></span>

   <span data-ttu-id="13a0d-139">Die LTI-App Microsoft Teams Klassen wird der Liste der externen Apps hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="13a0d-139">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a><span data-ttu-id="13a0d-140">Aktivieren der LTI-App für Canvas-Kurse</span><span class="sxs-lookup"><span data-stu-id="13a0d-140">Enabling the LTI app for Canvas courses</span></span>

<span data-ttu-id="13a0d-141">Um die LTI-App innerhalb eines Kurses zu verwenden, muss ein Kursleiter des Canvas-Kurses die Integrationssynchronisierung aktivieren. Jeder Kurs muss von einem Kursleiter aktiviert werden, damit ein entsprechendes Team erstellt werden kann. Es gibt keinen globalen Mechanismus für die Teams-Erstellung.</span><span class="sxs-lookup"><span data-stu-id="13a0d-141">To use the LTI app within a course, an instructor of the Canvas course must enable integrations sync. Each course must be enabled by an instructor for a corresponding team to be created; there is no global mechanism for teams creation.</span></span> <span data-ttu-id="13a0d-142">Dies dient als Vorsichtsmaßnahme, um zu verhindern, dass unerwünschte Teams erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="13a0d-142">This is designed as a precautionary measure to prevent unwanted teams from being created.</span></span>

<span data-ttu-id="13a0d-143">In der Dokumentation für [Lehrkräfte](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) finden Sie Informationen zum Aktivieren der LTI-App für jeden Kurs und zum Abschließen des Integrationssetups.</span><span class="sxs-lookup"><span data-stu-id="13a0d-143">Refer your instructors to the [educator documentation](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI app for each course and completing the integration setup.</span></span>
