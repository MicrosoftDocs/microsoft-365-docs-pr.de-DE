---
title: Verhindern von Datenverlust
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Richtlinien zur Verhinderung von Datenverlust verwalten.
ms.openlocfilehash: e963cf85fee887b6e91c6e54b00aaa9e5174e3b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927958"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="24028-103">Verhindern von Datenverlusten mit DLP</span><span class="sxs-lookup"><span data-stu-id="24028-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="24028-104">Richtlinien zur Verhinderung von Datenverlust helfen dabei, vertrauliche Informationen Ihres Unternehmens zu identifizieren und zu schützen, z. B. Sozialversicherungsnummern oder Krankenakten.</span><span class="sxs-lookup"><span data-stu-id="24028-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="24028-105">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="24028-105">Try it!</span></span>

1. <span data-ttu-id="24028-106">To get started, go to the [admin center,](https://admin.microsoft.com)and select **Setup**.</span><span class="sxs-lookup"><span data-stu-id="24028-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="24028-107">Scrollen Sie nach unten zu **"Verhinderung von Datenverlust einrichten",** und wählen Sie dann **"Ansicht"** und dann **"Verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="24028-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="24028-108">Um eine Richtlinie zu bearbeiten, wählen Sie sie aus, **wählen** Sie "Richtlinie bearbeiten" und dann aus, was Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="24028-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="24028-109">Wählen Sie beispielsweise **"Speicherorte"** aus, um zu ändern, was gescannt wird.</span><span class="sxs-lookup"><span data-stu-id="24028-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="24028-110">Um die Überprüfung auf Inhalte in Microsoft Teams  zu aktivieren, schalten Sie den Umschalter auf die Ein-Position, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="24028-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="24028-111">Um Richtlinieneinstellungen zu bearbeiten, wählen Sie **"Bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="24028-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="24028-112">Sie müssen separate Regeln festlegen, die für kleine und große Mengen von erkannten vertraulichen Inhalten gelten.</span><span class="sxs-lookup"><span data-stu-id="24028-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="24028-113">Erweitern Sie die Regel für geringes Volumen.</span><span class="sxs-lookup"><span data-stu-id="24028-113">Expand your low volume rule.</span></span> <span data-ttu-id="24028-114">Choose **Edit rule**.</span><span class="sxs-lookup"><span data-stu-id="24028-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="24028-115">Überprüfen Sie Ihre Einstellungen, und passen Sie sie nach Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="24028-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="24028-116">Sie können z.  B. den E-Mail-Text anpassen und **den Richtlinientipptext anpassen.**</span><span class="sxs-lookup"><span data-stu-id="24028-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="24028-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="24028-117">Select **Save**.</span></span>
1. <span data-ttu-id="24028-118">Wiederholen Sie dies für die Regel für hohe Lautstärke.</span><span class="sxs-lookup"><span data-stu-id="24028-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="24028-119">Wählen Sie **"Speichern"** und dann **"Schließen" aus.**</span><span class="sxs-lookup"><span data-stu-id="24028-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="24028-120">Wählen Sie zum Erstellen einer neuen Richtlinie die Option **"Richtlinie erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="24028-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="24028-121">Sie können eine benutzerdefinierte Richtlinie erstellen oder mit einer Vorlage beginnen.</span><span class="sxs-lookup"><span data-stu-id="24028-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="24028-122">Um beispielsweise eine HIPAA-Richtlinie zu erstellen, wählen Sie die Vorlage "Medical **and health"** und dann den **U.S. Health Insurance Act (HIPAA) aus.**</span><span class="sxs-lookup"><span data-stu-id="24028-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="24028-123">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="24028-123">Select **Next**.</span></span>
1. <span data-ttu-id="24028-124">Geben Sie einen Namen und eine Beschreibung für Ihre Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="24028-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="24028-125">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="24028-125">Select **Next**.</span></span>
1. <span data-ttu-id="24028-126">Wählen Sie die zu überprüfende Speicherorte aus.</span><span class="sxs-lookup"><span data-stu-id="24028-126">Choose the locations to scan.</span></span> <span data-ttu-id="24028-127">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="24028-127">Select **Next**.</span></span>
1. <span data-ttu-id="24028-128">Wählen Sie den Inhaltstyp aus, der geschützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="24028-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="24028-129">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="24028-129">Select **Next**.</span></span>
1. <span data-ttu-id="24028-130">Wählen Sie aus, was passieren soll, wenn vertrauliche Informationen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="24028-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="24028-131">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="24028-131">Select **Next**.</span></span>
1. <span data-ttu-id="24028-132">Passen Sie Ihren Zugriff an, und überschreiben Sie Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="24028-132">Customize your access and override permissions.</span></span> <span data-ttu-id="24028-133">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="24028-133">Select **Next**.</span></span>
1. <span data-ttu-id="24028-134">Wählen Sie aus, wann die Richtlinie wirksam werden soll.</span><span class="sxs-lookup"><span data-stu-id="24028-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="24028-135">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="24028-135">Select **Next**.</span></span>
1. <span data-ttu-id="24028-136">Überprüfen Sie Ihre Einstellungen, und wählen Sie **"Erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="24028-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="24028-137">Nachdem Ihre Richtlinie wirksam wurde, werden E-Mails mit den beschriebenen vertraulichen Informationen blockiert, und dem Absender, der versucht hat, diese Informationen zu senden, wird eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24028-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>