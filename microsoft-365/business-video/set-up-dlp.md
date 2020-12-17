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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie Richtlinien zur Verhinderung von Datenverlusten verwalten.
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702244"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="c0099-103">Verhindern von Datenverlust mit DLP</span><span class="sxs-lookup"><span data-stu-id="c0099-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="c0099-104">Policies zur Verhinderung von Datenverlusten helfen beim identifizieren und Schützen vertraulicher Informationen Ihres Unternehmens wie Sozialversicherungsnummern oder medizinischen Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="c0099-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="c0099-105">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="c0099-105">Try it!</span></span>

1. <span data-ttu-id="c0099-106">Um zu beginnen, wechseln Sie zum [Admin Center](https://admin.microsoft.com), und wählen Sie **Setup** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="c0099-107">Scrollen Sie nach unten, um die **Verhinderung von Datenverlust einzurichten**, und wählen Sie dann **anzeigen** und dann **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="c0099-108">Zum Bearbeiten einer Richtlinie wählen Sie Sie aus, wählen Sie **Richtlinie bearbeiten** aus, und wählen Sie dann zu ändernde Elemente aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="c0099-109">Wählen Sie beispielsweise **Orte** aus, um zu ändern, was gescannt wird.</span><span class="sxs-lookup"><span data-stu-id="c0099-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="c0099-110">Um die Überprüfung auf Inhalte in Microsoft Teams zu aktivieren, aktivieren Sie die Umschaltfläche in die Position **ein** , und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="c0099-111">Wählen Sie zum Bearbeiten von Richtlinieneinstellungen die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="c0099-112">Sie müssen separate Regeln festlegen, die auf kleine und große Mengen vertraulicher Inhalte angewendet werden, die erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="c0099-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="c0099-113">Erweitern Sie die Regel für geringes Volumen.</span><span class="sxs-lookup"><span data-stu-id="c0099-113">Expand your low volume rule.</span></span> <span data-ttu-id="c0099-114">Klicken Sie auf **Regel bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c0099-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="c0099-115">Überprüfen Sie Ihre Einstellungen, und passen Sie Sie bei Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="c0099-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="c0099-116">Sie können beispielsweise festlegen, dass **der e-Mail-Text angepasst** und **der richtlinientipp Text angepasst** werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0099-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="c0099-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c0099-117">Select **Save**.</span></span>
1. <span data-ttu-id="c0099-118">Wiederholen Sie diese Schritte für die Regel für hohe Lautstärke.</span><span class="sxs-lookup"><span data-stu-id="c0099-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="c0099-119">Klicken Sie auf **Speichern** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="c0099-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="c0099-120">Wählen Sie zum Erstellen einer neuen Richtlinie **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="c0099-121">Sie können eine benutzerdefinierte Richtlinie erstellen oder mit einer Vorlage beginnen.</span><span class="sxs-lookup"><span data-stu-id="c0099-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="c0099-122">Um beispielsweise eine HIPAA-Richtlinie zu erstellen, wählen Sie die Vorlage **Medizin und Integrität** aus, und wählen Sie dann **US-Krankenversicherungsgesetz (HIPAA)** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="c0099-123">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-123">Select **Next**.</span></span>
1. <span data-ttu-id="c0099-124">Geben Sie einen Namen und eine Beschreibung für Ihre Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="c0099-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="c0099-125">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-125">Select **Next**.</span></span>
1. <span data-ttu-id="c0099-126">Wählen Sie die zu überprüfenden Speicherorte aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-126">Choose the locations to scan.</span></span> <span data-ttu-id="c0099-127">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-127">Select **Next**.</span></span>
1. <span data-ttu-id="c0099-128">Wählen Sie den Inhaltstyp aus, den Sie schützen möchten.</span><span class="sxs-lookup"><span data-stu-id="c0099-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="c0099-129">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-129">Select **Next**.</span></span>
1. <span data-ttu-id="c0099-130">Wählen Sie aus, was geschehen soll, wenn vertrauliche Informationen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="c0099-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="c0099-131">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-131">Select **Next**.</span></span>
1. <span data-ttu-id="c0099-132">Passen Sie Ihre Zugriffs-und Außerkraftsetzungs Berechtigungen an.</span><span class="sxs-lookup"><span data-stu-id="c0099-132">Customize your access and override permissions.</span></span> <span data-ttu-id="c0099-133">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-133">Select **Next**.</span></span>
1. <span data-ttu-id="c0099-134">Wählen Sie aus, wann die Richtlinie wirksam werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0099-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="c0099-135">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-135">Select **Next**.</span></span>
1. <span data-ttu-id="c0099-136">Überprüfen Sie Ihre Einstellungen, und wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="c0099-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="c0099-137">Nachdem Ihre Richtlinie wirksam wurde, werden e-Mails, die die beschriebenen vertraulichen Informationen enthalten, blockiert, und der Absender, der versucht hat, diese Informationen zu senden, wird eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0099-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>