---
title: Verwenden der Interoperabilität mit OneDrive Learning Tools
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
description: Erstellen und Bewerten von Aufgaben, Erstellen und Kuratieren von Kursinhalten und Zusammenarbeit an Dateien in Echtzeit mit der neuen OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256984"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="4a6f7-103">Verwenden Microsoft OneDrive LTI mit Canvas</span><span class="sxs-lookup"><span data-stu-id="4a6f7-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a6f7-104">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4a6f7-105">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="4a6f7-106">Integration in Canvas</span><span class="sxs-lookup"><span data-stu-id="4a6f7-106">Integrate with Canvas</span></span>

<span data-ttu-id="4a6f7-107">Die Person, die diese Integration durchführt, sollte ein Administrator von Canvas und ein Administrator des Microsoft 365 Mandanten sein.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="4a6f7-108">Melden Sie sich mit dem Mandantenadministratorkonto beim Microsoft Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="4a6f7-109">Der Azure-Mandantenadministrator sollte auch über die Rolle "Gruppenadministrator" verfügen.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![Gruppenadministrator hervorgehoben](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="4a6f7-111">Melden Sie sich beim Microsoft [OneDrive LTI-Portal](https://odltiappnl.azurewebsites.net/admin)an.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="4a6f7-112">Akzeptieren Sie die Berechtigungen, um die Anmeldung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-112">Accept the permissions to complete the sign-in.</span></span>

    ![Berechtigungen akzeptieren](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="4a6f7-114">Wählen **Sie "LTI-Mandant hinzufügen"** aus.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-114">Select **Add LTI Tenant**.</span></span>

     ![LTI-Mandant hinzufügen](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="4a6f7-116">Wählen Sie in der Dropdownliste **LTI Consumer Platform** als **Canvas** aus.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="4a6f7-117">Wählen Sie **"Canvas-Basis-URL"** und dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![Canvas auswählen und Basis-URL hinzufügen](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="4a6f7-119">Auf dem nächsten Bildschirm werden Felder angezeigt, die für Sie vertraulich sind.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="4a6f7-120">Wählen Sie **"Weiter"** aus ??</span><span class="sxs-lookup"><span data-stu-id="4a6f7-120">Select **Next** from ??</span></span> <span data-ttu-id="4a6f7-121">den Link für resend the email auswählen.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-121">page.</span></span> <span data-ttu-id="4a6f7-122">KÖNNEN PRÜFER HIER DIE LEERE AUSFÜLLEN?</span><span class="sxs-lookup"><span data-stu-id="4a6f7-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="4a6f7-123">Klicken Sie auf dem Bildschirm auf **"Weiter",** auf dem Informationen angezeigt werden, die Für Sie vertraulich sind.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="4a6f7-124">Der letzte Bildschirm des Azure-Portals zeigt die nächsten Schritte zum Hinzufügen Ihrer Canvas-Instanz.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="4a6f7-125">Kopieren Sie die Entwicklerschlüssel von diesem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="4a6f7-126">Sie werden beim Erstellen der Canvas-Instanz verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="4a6f7-127">Hinzufügen der Canvas-Instanz</span><span class="sxs-lookup"><span data-stu-id="4a6f7-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="4a6f7-128">Deaktivieren Sie in Ihrer Canvas-Instanz die Option **"Admin**  >  **Developer Keys".**</span><span class="sxs-lookup"><span data-stu-id="4a6f7-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="4a6f7-129">Wählen Sie **LTI-Schlüssel** in der Dropdownliste auf **"Entwicklerschlüssel" aus.**</span><span class="sxs-lookup"><span data-stu-id="4a6f7-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![Abrufen der LTI-Entwicklerschlüssel](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="4a6f7-131">Fügen Sie die Entwicklerschlüssel hier ein.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-131">Paste the developer keys here.</span></span>

     ![Einfügen der Entwicklerschlüssel](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="4a6f7-133">Der Schlüssel wird im **AUS-Modus** erstellt.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-133">The key gets created in **OFF** mode</span></span>

   ![Die erstellten Entwicklerschlüssel im Aus-Modus](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="4a6f7-135">Kopieren Sie den hervorgehobenen Text.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="4a6f7-136">Dies dient als Client-ID im Microsoft OneDrive LTI-Portal.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="4a6f7-137">Fügen Sie den Text in das **Feld "Client-ID"** in Microsoft OneDrive LTI-Portal ein, und wählen Sie dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="4a6f7-138">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-138">Select **Save**.</span></span>

7. <span data-ttu-id="4a6f7-139">Zeigen Sie die Einstellungen an, indem Sie **"LTI-Mandanten anzeigen"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="4a6f7-139">View the settings by selecting **View LTI Tenants**.</span></span>
