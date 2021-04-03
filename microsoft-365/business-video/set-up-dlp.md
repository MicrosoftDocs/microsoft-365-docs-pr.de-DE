---
title: Verhindern von Datenverlust
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Erfahren Sie, wie Sie die Einrichtung von Richtlinien zur Verhinderung von Datenverlust verwalten.
ms.openlocfilehash: 04dbbcfd39186b8161fb497b72ddb070fbfb7471
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580438"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="84431-103">Verhindern von Datenverlust mit DLP</span><span class="sxs-lookup"><span data-stu-id="84431-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="84431-104">Richtlinien zur Verhinderung von Datenverlust helfen dabei, vertrauliche Informationen Ihres Unternehmens zu identifizieren und zu schützen, z. B. Sozialversicherungsnummern oder Krankenakten.</span><span class="sxs-lookup"><span data-stu-id="84431-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="84431-105">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="84431-105">Try it!</span></span>

1. <span data-ttu-id="84431-106">Wechseln Sie zum Admin [Center,](https://admin.microsoft.com)und wählen Sie **Setup aus.**</span><span class="sxs-lookup"><span data-stu-id="84431-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="84431-107">Scrollen Sie nach **unten, um die Verhinderung von Datenverlust einrichten,** und wählen Sie **dann Ansicht** und dann **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="84431-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="84431-108">Wählen Sie zum Bearbeiten einer Richtlinie die Option Richtlinie bearbeiten **aus,** und wählen Sie dann aus, was geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="84431-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="84431-109">Wählen Sie beispielsweise **Speicherorte aus,** um zu ändern, was gescannt wird.</span><span class="sxs-lookup"><span data-stu-id="84431-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="84431-110">Um die Überprüfung auf Inhalte in Microsoft Teams  zu aktivieren, schalten Sie den Umschalter auf die Ein-Position, und wählen Sie **dann Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="84431-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="84431-111">Wählen Sie Bearbeiten aus, um Richtlinieneinstellungen **zu bearbeiten.**</span><span class="sxs-lookup"><span data-stu-id="84431-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="84431-112">Sie müssen separate Regeln festlegen, die für kleine und große Mengen von erkannten vertraulichen Inhalten gelten.</span><span class="sxs-lookup"><span data-stu-id="84431-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="84431-113">Erweitern Sie Die Regel für niedriges Volumen.</span><span class="sxs-lookup"><span data-stu-id="84431-113">Expand your low volume rule.</span></span> <span data-ttu-id="84431-114">Wählen **Sie Bearbeitungsregel** aus.</span><span class="sxs-lookup"><span data-stu-id="84431-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="84431-115">Überprüfen Sie Ihre Einstellungen, und passen Sie sie bei Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="84431-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="84431-116">Sie können z. B. den **E-Mail-Text** anpassen und **den Richtlinientipptext anpassen auswählen.**</span><span class="sxs-lookup"><span data-stu-id="84431-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="84431-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="84431-117">Select **Save**.</span></span>
1. <span data-ttu-id="84431-118">Wiederholen Sie dies für die Regel mit hohem Volumen.</span><span class="sxs-lookup"><span data-stu-id="84431-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="84431-119">Wählen **Sie Speichern** und dann Schließen **aus.**</span><span class="sxs-lookup"><span data-stu-id="84431-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="84431-120">Wählen Sie Zum Erstellen einer neuen Richtlinie die Option **Richtlinie erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="84431-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="84431-121">Sie können eine benutzerdefinierte Richtlinie erstellen oder mit einer Vorlage beginnen.</span><span class="sxs-lookup"><span data-stu-id="84431-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="84431-122">Wenn Sie beispielsweise eine HIPAA-Richtlinie erstellen möchten, wählen Sie die Vorlage **Medizin** und Gesundheit aus, und wählen Sie dann **U.S. Health Insurance Act (HIPAA) aus.**</span><span class="sxs-lookup"><span data-stu-id="84431-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="84431-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="84431-123">Select **Next**.</span></span>
1. <span data-ttu-id="84431-124">Geben Sie einen Namen und eine Beschreibung für Ihre Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="84431-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="84431-125">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="84431-125">Select **Next**.</span></span>
1. <span data-ttu-id="84431-126">Wählen Sie die zu scannende Speicherorte aus.</span><span class="sxs-lookup"><span data-stu-id="84431-126">Choose the locations to scan.</span></span> <span data-ttu-id="84431-127">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="84431-127">Select **Next**.</span></span>
1. <span data-ttu-id="84431-128">Wählen Sie den Inhaltstyp aus, der geschützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="84431-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="84431-129">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="84431-129">Select **Next**.</span></span>
1. <span data-ttu-id="84431-130">Wählen Sie aus, was passieren soll, wenn vertrauliche Informationen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="84431-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="84431-131">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="84431-131">Select **Next**.</span></span>
1. <span data-ttu-id="84431-132">Passen Sie Ihre Zugriffs- und Außerkraftsetzungsberechtigungen an.</span><span class="sxs-lookup"><span data-stu-id="84431-132">Customize your access and override permissions.</span></span> <span data-ttu-id="84431-133">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="84431-133">Select **Next**.</span></span>
1. <span data-ttu-id="84431-134">Wählen Sie aus, wann die Richtlinie wirksam werden soll.</span><span class="sxs-lookup"><span data-stu-id="84431-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="84431-135">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="84431-135">Select **Next**.</span></span>
1. <span data-ttu-id="84431-136">Überprüfen Sie Ihre Einstellungen, und wählen Sie **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="84431-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="84431-137">Nachdem Ihre Richtlinie wirksam wurde, werden E-Mails mit den beschriebenen vertraulichen Informationen blockiert, und dem Absender, der versucht hat, diese Informationen zu senden, wird eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84431-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>