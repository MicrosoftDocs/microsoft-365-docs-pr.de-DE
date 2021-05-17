---
title: Arbeiten mit dem App-Steuerelement
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917640"
---
# <a name="work-with-app-control"></a><span data-ttu-id="904ba-103">Arbeiten mit dem App-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="904ba-103">Work with app control</span></span>

<span data-ttu-id="904ba-104">Sobald die App-Steuerung in Ihrer Umgebung bereitgestellt wurde, sind sowohl Sie als auch Microsoft Managed Desktop Vorgänge fortlaufend verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="904ba-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="904ba-105">Sie können beispielsweise eine neue App in der Umgebung hinzufügen oder einen vertrauenswürdigen Signer hinzufügen (oder entfernen).</span><span class="sxs-lookup"><span data-stu-id="904ba-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="904ba-106">Zur Verbesserung der Sicherheit sollten alle Apps vor der Veröffentlichung für Benutzer mit Code signiert werden.</span><span class="sxs-lookup"><span data-stu-id="904ba-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="904ba-107">Die Herausgeberdetails einer App enthalten Informationen zum Signier.</span><span class="sxs-lookup"><span data-stu-id="904ba-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="904ba-108">Hinzufügen einer neuen App</span><span class="sxs-lookup"><span data-stu-id="904ba-108">Add a new app</span></span>

<span data-ttu-id="904ba-109">Führen Sie die folgenden Schritte aus, um eine neue App hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="904ba-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="904ba-110">Fügen Sie die App zu [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="904ba-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="904ba-111">Stellen Sie die App auf einem beliebigen Gerät im Testring aus.</span><span class="sxs-lookup"><span data-stu-id="904ba-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="904ba-112">Testen Sie Ihre App gemäß Ihren Standardgeschäftsprozessen.</span><span class="sxs-lookup"><span data-stu-id="904ba-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="904ba-113">Überprüfen Sie die Ereignisanzeige unter Anwendungs- und **Dienstprotokolle\Microsoft\Windows\AppLocker,** und suchen Sie nach **8003-** oder **8006-Ereignissen.**</span><span class="sxs-lookup"><span data-stu-id="904ba-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="904ba-114">Diese Ereignisse deuten darauf hin, dass die App blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="904ba-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="904ba-115">Weitere Informationen zu allen App Locker-Ereignissen und deren Bedeutung finden Sie unter [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="904ba-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="904ba-116">Wenn Sie eines dieser Ereignisse finden, öffnen Sie eine Signieranforderung mit Microsoft Managed Desktop Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="904ba-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="904ba-117">Hinzufügen (oder Entfernen) eines vertrauenswürdigen Signers</span><span class="sxs-lookup"><span data-stu-id="904ba-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="904ba-118">Wenn Sie eine Signieranforderung öffnen, müssen Sie zunächst einige wichtige Herausgeberdetails bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="904ba-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="904ba-119">Führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="904ba-119">Then follow these steps:</span></span>

1. <span data-ttu-id="904ba-120">[Sammeln von Herausgeberdetails](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="904ba-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="904ba-121">Öffnen Sie ein Ticket mit Microsoft Managed Desktop Vorgängen, um die Signierregel an fordern und die folgenden Details enthalten:</span><span class="sxs-lookup"><span data-stu-id="904ba-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="904ba-122">Name der Anwendung</span><span class="sxs-lookup"><span data-stu-id="904ba-122">Application name</span></span> 
    - <span data-ttu-id="904ba-123">Anwendungsversion</span><span class="sxs-lookup"><span data-stu-id="904ba-123">Application version</span></span> 
    - <span data-ttu-id="904ba-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="904ba-124">Description</span></span> 
    - <span data-ttu-id="904ba-125">Änderungstyp ("hinzufügen" oder "entfernen")</span><span class="sxs-lookup"><span data-stu-id="904ba-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="904ba-126">Publisher (z. B.: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="904ba-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="904ba-127">Führen Sie die gleichen Schritte aus, um die Vertrauensstellung für eine App zu entfernen, legen Sie **jedoch Den Änderungstyp** auf *entfernen festgelegt.*</span><span class="sxs-lookup"><span data-stu-id="904ba-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="904ba-128">Im Anschluss an diesen Zeitplan werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="904ba-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="904ba-129">Bereitstellungsgruppe</span><span class="sxs-lookup"><span data-stu-id="904ba-129">Deployment group</span></span>  |<span data-ttu-id="904ba-130">Richtlinientyp</span><span class="sxs-lookup"><span data-stu-id="904ba-130">Policy type</span></span>  |<span data-ttu-id="904ba-131">Timing</span><span class="sxs-lookup"><span data-stu-id="904ba-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="904ba-132">Testen</span><span class="sxs-lookup"><span data-stu-id="904ba-132">Test</span></span>     |  <span data-ttu-id="904ba-133">Überwachung</span><span class="sxs-lookup"><span data-stu-id="904ba-133">Audit</span></span>       |  <span data-ttu-id="904ba-134">Tag 0</span><span class="sxs-lookup"><span data-stu-id="904ba-134">Day 0</span></span>       |
|<span data-ttu-id="904ba-135">Erster</span><span class="sxs-lookup"><span data-stu-id="904ba-135">First</span></span>     | <span data-ttu-id="904ba-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="904ba-136">Enforced</span></span>        | <span data-ttu-id="904ba-137">Tag 1</span><span class="sxs-lookup"><span data-stu-id="904ba-137">Day 1</span></span>        |
|<span data-ttu-id="904ba-138">Schnell</span><span class="sxs-lookup"><span data-stu-id="904ba-138">Fast</span></span>     | <span data-ttu-id="904ba-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="904ba-139">Enforced</span></span>        |  <span data-ttu-id="904ba-140">Tag 2</span><span class="sxs-lookup"><span data-stu-id="904ba-140">Day 2</span></span>       |
|<span data-ttu-id="904ba-141">Allgemein</span><span class="sxs-lookup"><span data-stu-id="904ba-141">Broad</span></span>     | <span data-ttu-id="904ba-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="904ba-142">Enforced</span></span>        |  <span data-ttu-id="904ba-143">Tag 3</span><span class="sxs-lookup"><span data-stu-id="904ba-143">Day 3</span></span>       |


<span data-ttu-id="904ba-144">Sie können die Bereitstellung während des Rollouts jederzeit anhalten oder ein Rollback vornehmen.</span><span class="sxs-lookup"><span data-stu-id="904ba-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="904ba-145">Öffnen Sie dazu eine weitere Dienstanforderung mit Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="904ba-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="904ba-146">Wenn Sie die Veröffentlichung einer Signierregel anhalten, muss diese Regel entweder zurückgesetzt oder abgeschlossen werden, bevor ein weiteres Rollout gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="904ba-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="904ba-147">Sammeln von Herausgeberdetails</span><span class="sxs-lookup"><span data-stu-id="904ba-147">Gather publisher details</span></span>

<span data-ttu-id="904ba-148">Führen Sie die folgenden Schritte aus, um auf die Herausgeberdaten für eine App zu zugreifen:</span><span class="sxs-lookup"><span data-stu-id="904ba-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="904ba-149">Suchen Sie Microsoft Managed Desktop Gerät im Testring, auf das eine Überwachungsmodusrichtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="904ba-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="904ba-150">Versuchen Sie, die App auf dem Gerät zu installieren.</span><span class="sxs-lookup"><span data-stu-id="904ba-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="904ba-151">Öffnen Sie die Ereignisanzeige auf diesem Gerät.</span><span class="sxs-lookup"><span data-stu-id="904ba-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="904ba-152">Navigieren Sie in der Ereignisanzeige zu Anwendungs- und **Dienstprotokolle\Microsoft\Windows**, und wählen Sie **dann AppLocker aus.**</span><span class="sxs-lookup"><span data-stu-id="904ba-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="904ba-153">Suchen Sie **nach einem 8003-** oder **8006-Ereignis,** und kopieren Sie dann Informationen aus dem Ereignis:</span><span class="sxs-lookup"><span data-stu-id="904ba-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="904ba-154">Name der Anwendung</span><span class="sxs-lookup"><span data-stu-id="904ba-154">Application name</span></span> 
    - <span data-ttu-id="904ba-155">Anwendungsversion</span><span class="sxs-lookup"><span data-stu-id="904ba-155">Application version</span></span> 
    - <span data-ttu-id="904ba-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="904ba-156">Description</span></span> 
    - <span data-ttu-id="904ba-157">Publisher (z. B. "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="904ba-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>