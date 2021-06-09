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
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="60214-103">Verwenden Microsoft Teams von Besprechungen mit Canvas</span><span class="sxs-lookup"><span data-stu-id="60214-103">Use Microsoft Teams meetings with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60214-104">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="60214-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="60214-105">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="60214-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="60214-106">Microsoft Teams Besprechungen ist eine LTI-App (Learning Tools Interoperability), mit der Lehrkräfte und Schüler problemlos zwischen ihrem Learning Management System (LMS) und Teams navigieren können.</span><span class="sxs-lookup"><span data-stu-id="60214-106">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="60214-107">Benutzer können direkt in ihrem LMS auf ihre Kursteams zugreifen, die ihrem Kurs zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="60214-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="60214-108">Microsoft Office 365 Admin</span><span class="sxs-lookup"><span data-stu-id="60214-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="60214-109">Bevor Sie die Microsoft Teams Integration in Instructure Canvas verwalten, ist es wichtig, dass die **Azure-App "Microsoft-Teams-Sync-for-Canvas"** von Canvas vom Microsoft Office 365-Administrator Ihrer Bildungseinrichtung in Ihrem Microsoft Azure Mandanten genehmigt wird, bevor Sie das Canvas-Administratorsetup abschließen.</span><span class="sxs-lookup"><span data-stu-id="60214-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="60214-110">Melden Sie sich bei Canvas an.</span><span class="sxs-lookup"><span data-stu-id="60214-110">Sign in to Canvas.</span></span>
 
2. <span data-ttu-id="60214-111">Wählen Sie **den** Administratorlink in der globalen Navigation aus, und wählen Sie dann Ihr Konto aus.</span><span class="sxs-lookup"><span data-stu-id="60214-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="60214-112">Wählen Sie in der Administratornavigation den **Link Einstellungen** und dann die Registerkarte **"Integrationen"** aus.</span><span class="sxs-lookup"><span data-stu-id="60214-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span> 

4. <span data-ttu-id="60214-113">Geben Sie Ihren Microsoft-Mandantennamen und Ihr Anmeldeattribut ein.</span><span class="sxs-lookup"><span data-stu-id="60214-113">Enter your Microsoft tenant name and login attribute.</span></span> 

   <span data-ttu-id="60214-114">Das Anmeldeattribut wird verwendet, um den Canvas-Benutzer einem Azure Active Directory Benutzer zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="60214-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span> 

5. <span data-ttu-id="60214-115">Wählen Sie nach Abschluss **Einstellungen** aktualisieren aus.</span><span class="sxs-lookup"><span data-stu-id="60214-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="60214-116">Um den Zugriff für die **Azure-App "Microsoft-Teams-Sync-for-Canvas"** von Canvas zu genehmigen, wählen Sie den Link **"Mandantenzugriff gewähren"** aus.</span><span class="sxs-lookup"><span data-stu-id="60214-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="60214-117">Sie werden zum Microsoft Identity Platform Admin Consent-Endpunkt umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="60214-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![Berechtigungen](media/permissions.png)

7. <span data-ttu-id="60214-119">Wählen Sie **Annehmen** aus.</span><span class="sxs-lookup"><span data-stu-id="60214-119">Select **Accept**.</span></span>
 
8. <span data-ttu-id="60214-120">Aktivieren Sie die Microsoft Teams Synchronisierung, indem Sie die Umschaltfläche aktivieren.</span><span class="sxs-lookup"><span data-stu-id="60214-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![Teams-Synchronisierung](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="60214-122">Canvas-Administrator</span><span class="sxs-lookup"><span data-stu-id="60214-122">Canvas Admin</span></span>

<span data-ttu-id="60214-123">Richten Sie die Microsoft Teams LTI 1.3-Integration ein.</span><span class="sxs-lookup"><span data-stu-id="60214-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="60214-124">Als Canvas-Administrator müssen Sie die LTI-App Microsoft Teams Besprechungen in Ihrer Umgebung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="60214-124">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="60214-125">Notieren Sie sich die LTI-Client-ID für die App.</span><span class="sxs-lookup"><span data-stu-id="60214-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="60214-126">Microsoft Teams Besprechungen – 170000000000703</span><span class="sxs-lookup"><span data-stu-id="60214-126">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="60214-127">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="60214-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="60214-128">Wählen Sie **+App** aus, um die Teams LTI-Apps hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="60214-128">Select **+ App** to add the Teams LTI apps.</span></span> 
 
   ![Externe Apps](media/external-apps.png)

3. <span data-ttu-id="60214-130">Wählen Sie **nach Client-ID** für Konfigurationstyp aus.</span><span class="sxs-lookup"><span data-stu-id="60214-130">Select **By Client ID** for configuration type.</span></span>

   ![App hinzufügen](media/add-app.png)

4. <span data-ttu-id="60214-132">Geben Sie die angegebene Client-ID ein, und wählen Sie dann **"Absenden"** aus.</span><span class="sxs-lookup"><span data-stu-id="60214-132">Enter the Client ID provided, and then select **Submit**.</span></span>
   
   <span data-ttu-id="60214-133">Sie werden den Namen der LTI-App für Microsoft Teams Besprechungen für die Client-ID zur Bestätigung bemerken.</span><span class="sxs-lookup"><span data-stu-id="60214-133">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span> 

5. <span data-ttu-id="60214-134">Wählen Sie **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="60214-134">Select **Install**.</span></span>

   <span data-ttu-id="60214-135">Die LTI-App Microsoft Teams Besprechungen wird der Liste der externen Apps hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="60214-135">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
