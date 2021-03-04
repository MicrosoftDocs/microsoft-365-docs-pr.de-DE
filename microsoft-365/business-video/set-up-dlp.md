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
ms.openlocfilehash: 54cd508ef0b0cfcf8b71dc86a4903f77a5354c36
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422063"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="fd31b-103">Verhindern von Datenverlust mit DLP</span><span class="sxs-lookup"><span data-stu-id="fd31b-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="fd31b-104">Richtlinien zur Verhinderung von Datenverlust helfen dabei, vertrauliche Informationen Ihres Unternehmens zu identifizieren und zu schützen, z. B. Sozialversicherungsnummern oder Krankenakten.</span><span class="sxs-lookup"><span data-stu-id="fd31b-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="fd31b-105">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="fd31b-105">Try it!</span></span>

1. <span data-ttu-id="fd31b-106">Wechseln Sie zum Admin [Center,](https://admin.microsoft.com)und wählen Sie **Setup aus.**</span><span class="sxs-lookup"><span data-stu-id="fd31b-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="fd31b-107">Scrollen Sie nach **unten, um die Verhinderung von Datenverlust einrichten,** und wählen Sie **dann Ansicht** und dann **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="fd31b-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="fd31b-108">Wählen Sie zum Bearbeiten einer Richtlinie die Option Richtlinie bearbeiten **aus,** und wählen Sie dann aus, was geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd31b-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="fd31b-109">Wählen Sie beispielsweise **Speicherorte aus,** um zu ändern, was gescannt wird.</span><span class="sxs-lookup"><span data-stu-id="fd31b-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="fd31b-110">Um die Überprüfung auf Inhalte in Microsoft Teams  zu aktivieren, schalten Sie den Umschalter auf die Ein-Position, und wählen Sie **dann Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="fd31b-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="fd31b-111">Wählen Sie Bearbeiten aus, um Richtlinieneinstellungen **zu bearbeiten.**</span><span class="sxs-lookup"><span data-stu-id="fd31b-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="fd31b-112">Sie müssen separate Regeln festlegen, die für kleine und große Mengen von erkannten vertraulichen Inhalten gelten.</span><span class="sxs-lookup"><span data-stu-id="fd31b-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="fd31b-113">Erweitern Sie Die Regel für niedriges Volumen.</span><span class="sxs-lookup"><span data-stu-id="fd31b-113">Expand your low volume rule.</span></span> <span data-ttu-id="fd31b-114">Wählen **Sie Bearbeitungsregel** aus.</span><span class="sxs-lookup"><span data-stu-id="fd31b-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="fd31b-115">Überprüfen Sie Ihre Einstellungen, und passen Sie sie bei Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="fd31b-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="fd31b-116">Sie können z. B. den **E-Mail-Text** anpassen und **den Richtlinientipptext anpassen auswählen.**</span><span class="sxs-lookup"><span data-stu-id="fd31b-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="fd31b-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fd31b-117">Select **Save**.</span></span>
1. <span data-ttu-id="fd31b-118">Wiederholen Sie dies für die Regel mit hohem Volumen.</span><span class="sxs-lookup"><span data-stu-id="fd31b-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="fd31b-119">Wählen **Sie Speichern** und dann Schließen **aus.**</span><span class="sxs-lookup"><span data-stu-id="fd31b-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="fd31b-120">Wählen Sie Zum Erstellen einer neuen Richtlinie die Option **Richtlinie erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="fd31b-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="fd31b-121">Sie können eine benutzerdefinierte Richtlinie erstellen oder mit einer Vorlage beginnen.</span><span class="sxs-lookup"><span data-stu-id="fd31b-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="fd31b-122">Wenn Sie beispielsweise eine HIPAA-Richtlinie erstellen möchten, wählen Sie die Vorlage **Medizin** und Gesundheit aus, und wählen Sie dann **U.S. Health Insurance Act (HIPAA) aus.**</span><span class="sxs-lookup"><span data-stu-id="fd31b-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="fd31b-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fd31b-123">Select **Next**.</span></span>
1. <span data-ttu-id="fd31b-124">Geben Sie einen Namen und eine Beschreibung für Ihre Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="fd31b-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="fd31b-125">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fd31b-125">Select **Next**.</span></span>
1. <span data-ttu-id="fd31b-126">Wählen Sie die zu scannende Speicherorte aus.</span><span class="sxs-lookup"><span data-stu-id="fd31b-126">Choose the locations to scan.</span></span> <span data-ttu-id="fd31b-127">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fd31b-127">Select **Next**.</span></span>
1. <span data-ttu-id="fd31b-128">Wählen Sie den Inhaltstyp aus, der geschützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd31b-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="fd31b-129">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fd31b-129">Select **Next**.</span></span>
1. <span data-ttu-id="fd31b-130">Wählen Sie aus, was passieren soll, wenn vertrauliche Informationen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="fd31b-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="fd31b-131">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fd31b-131">Select **Next**.</span></span>
1. <span data-ttu-id="fd31b-132">Passen Sie Ihre Zugriffs- und Außerkraftsetzungsberechtigungen an.</span><span class="sxs-lookup"><span data-stu-id="fd31b-132">Customize your access and override permissions.</span></span> <span data-ttu-id="fd31b-133">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fd31b-133">Select **Next**.</span></span>
1. <span data-ttu-id="fd31b-134">Wählen Sie aus, wann die Richtlinie wirksam werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd31b-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="fd31b-135">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fd31b-135">Select **Next**.</span></span>
1. <span data-ttu-id="fd31b-136">Überprüfen Sie Ihre Einstellungen, und wählen Sie **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="fd31b-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="fd31b-137">Nachdem Ihre Richtlinie wirksam wurde, werden E-Mails mit den beschriebenen vertraulichen Informationen blockiert, und dem Absender, der versucht hat, diese Informationen zu senden, wird eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd31b-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>