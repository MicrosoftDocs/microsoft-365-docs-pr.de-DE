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
ms.openlocfilehash: 9efe6ba6704b0e1633973d157c38827221316bbd
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430447"
---
# <a name="work-with-app-control"></a><span data-ttu-id="b697d-103">Arbeiten mit dem App-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b697d-103">Work with app control</span></span>

<span data-ttu-id="b697d-104">Sobald die APP-Steuerung in Ihrer Umgebung bereitgestellt wurde, haben sowohl Sie als auch Microsoft Managed Desktop-Vorgänge fortlaufende Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="b697d-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="b697d-105">Beispielsweise können Sie eine neue app in der Umgebung hinzufügen oder einen vertrauenswürdigen Signaturer hinzufügen (oder entfernen).</span><span class="sxs-lookup"><span data-stu-id="b697d-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="b697d-106">Um die Sicherheit zu verbessern, sollten alle apps Code signiert sein, bevor Sie Sie an Endbenutzer freigeben.</span><span class="sxs-lookup"><span data-stu-id="b697d-106">To improve security, all apps should be code-signed before you release them to end users.</span></span> <span data-ttu-id="b697d-107">Die Herausgeber Details einer App enthalten Informationen zur signiererin.</span><span class="sxs-lookup"><span data-stu-id="b697d-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="b697d-108">Hinzufügen einer neuen App</span><span class="sxs-lookup"><span data-stu-id="b697d-108">Add a new app</span></span>

<span data-ttu-id="b697d-109">Führen Sie die folgenden Schritte aus, um eine neue APP hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="b697d-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="b697d-110">Fügen Sie die APP zu [Microsoft InTune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)hinzu.</span><span class="sxs-lookup"><span data-stu-id="b697d-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="b697d-111">Stellen Sie die APP auf einem beliebigen Gerät im Test-Ring bereit.</span><span class="sxs-lookup"><span data-stu-id="b697d-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="b697d-112">Testen Sie Ihre APP gemäß ihren Standardgeschäftsprozessen.</span><span class="sxs-lookup"><span data-stu-id="b697d-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="b697d-113">Überprüfen Sie die Ereignisanzeige unter **Application and Services Logs\Microsoft\Windows\AppLocker**, und suchen Sie nach **8003** -oder **8006** -Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="b697d-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="b697d-114">Diese Ereignisse deuten darauf hin, dass die APP blockiert würde.</span><span class="sxs-lookup"><span data-stu-id="b697d-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="b697d-115">Weitere Informationen zu allen APP locker-Ereignissen und deren Bedeutung finden Sie unter [Verwenden der Ereignisanzeige mit AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="b697d-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="b697d-116">Wenn Sie eines der folgenden Ereignisse finden, öffnen Sie eine Signaturer-Anforderung mit Microsoft Managed Desktop Operations.</span><span class="sxs-lookup"><span data-stu-id="b697d-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="b697d-117">Hinzufügen (oder entfernen) einer vertrauenswürdigen signierenden</span><span class="sxs-lookup"><span data-stu-id="b697d-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="b697d-118">Wenn Sie eine Signaturgeber Anforderung öffnen, müssen Sie zuerst einige wichtige Publisher-Details angeben.</span><span class="sxs-lookup"><span data-stu-id="b697d-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="b697d-119">Führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b697d-119">Then follow these steps:</span></span>

1. <span data-ttu-id="b697d-120">[Sammeln Sie Herausgeber Details](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="b697d-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="b697d-121">Öffnen Sie ein Ticket mit Microsoft Managed Desktop Operations, um die Signaturer-Regel anzufordern, und schließen Sie die folgenden Details ein:</span><span class="sxs-lookup"><span data-stu-id="b697d-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="b697d-122">Anwendungsname</span><span class="sxs-lookup"><span data-stu-id="b697d-122">Application name</span></span> 
    - <span data-ttu-id="b697d-123">Anwendungsversion</span><span class="sxs-lookup"><span data-stu-id="b697d-123">Application version</span></span> 
    - <span data-ttu-id="b697d-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b697d-124">Description</span></span> 
    - <span data-ttu-id="b697d-125">Change Type ("hinzufügen" oder "entfernen")</span><span class="sxs-lookup"><span data-stu-id="b697d-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="b697d-126">Publisher-Details (Beispiel: "O = <publisher name> , L = <location> , S = State, C = Country")</span><span class="sxs-lookup"><span data-stu-id="b697d-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="b697d-127">Wenn Sie die Vertrauensstellung für eine APP entfernen möchten, führen Sie die gleichen Schritte aus, legen Sie jedoch **Change Type** auf *Remove*fest.</span><span class="sxs-lookup"><span data-stu-id="b697d-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="b697d-128">Durch Vorgänge werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt, die auf diesen Zeitplan folgen:</span><span class="sxs-lookup"><span data-stu-id="b697d-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="b697d-129">Bereitstellungsgruppe</span><span class="sxs-lookup"><span data-stu-id="b697d-129">Deployment group</span></span>  |<span data-ttu-id="b697d-130">Richtlinientyp</span><span class="sxs-lookup"><span data-stu-id="b697d-130">Policy type</span></span>  |<span data-ttu-id="b697d-131">Timing</span><span class="sxs-lookup"><span data-stu-id="b697d-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b697d-132">Testen</span><span class="sxs-lookup"><span data-stu-id="b697d-132">Test</span></span>     |  <span data-ttu-id="b697d-133">Überwachung</span><span class="sxs-lookup"><span data-stu-id="b697d-133">Audit</span></span>       |  <span data-ttu-id="b697d-134">Tag 0</span><span class="sxs-lookup"><span data-stu-id="b697d-134">Day 0</span></span>       |
|<span data-ttu-id="b697d-135">Erster</span><span class="sxs-lookup"><span data-stu-id="b697d-135">First</span></span>     | <span data-ttu-id="b697d-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="b697d-136">Enforced</span></span>        | <span data-ttu-id="b697d-137">Tag 1</span><span class="sxs-lookup"><span data-stu-id="b697d-137">Day 1</span></span>        |
|<span data-ttu-id="b697d-138">Schnell</span><span class="sxs-lookup"><span data-stu-id="b697d-138">Fast</span></span>     | <span data-ttu-id="b697d-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="b697d-139">Enforced</span></span>        |  <span data-ttu-id="b697d-140">Tag 2</span><span class="sxs-lookup"><span data-stu-id="b697d-140">Day 2</span></span>       |
|<span data-ttu-id="b697d-141">Allgemein</span><span class="sxs-lookup"><span data-stu-id="b697d-141">Broad</span></span>     | <span data-ttu-id="b697d-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="b697d-142">Enforced</span></span>        |  <span data-ttu-id="b697d-143">Tag 3</span><span class="sxs-lookup"><span data-stu-id="b697d-143">Day 3</span></span>       |


<span data-ttu-id="b697d-144">Sie können die Bereitstellung jederzeit während des Rollouts anhalten oder ein Rollback ausführen.</span><span class="sxs-lookup"><span data-stu-id="b697d-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="b697d-145">Öffnen Sie dazu eine andere Dienstanforderung mit Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="b697d-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="b697d-146">Wenn Sie die Veröffentlichung einer Signaturregel anhalten, muss die Regel entweder zurückgesetzt oder abgeschlossen werden, bevor ein anderes Rollout gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b697d-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="b697d-147">Sammeln von Herausgeber Details</span><span class="sxs-lookup"><span data-stu-id="b697d-147">Gather publisher details</span></span>

<span data-ttu-id="b697d-148">Führen Sie die folgenden Schritte aus, um auf die Herausgeberdaten für eine APP zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="b697d-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="b697d-149">Suchen Sie ein Microsoft Managed Desktop-Gerät im testring, auf dem eine Überwachungsmodus-Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b697d-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="b697d-150">Versuchen Sie, die APP auf dem Gerät zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b697d-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="b697d-151">Öffnen Sie die Ereignisanzeige auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="b697d-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="b697d-152">Navigieren Sie in der Ereignisanzeige zu **Anwendungs-und Dienst Logs\Microsoft\Windows**, und wählen Sie dann **AppLocker**aus.</span><span class="sxs-lookup"><span data-stu-id="b697d-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="b697d-153">Suchen Sie nach einem beliebigen **8003** -oder **8006** -Ereignis, und kopieren Sie dann Informationen aus dem Ereignis:</span><span class="sxs-lookup"><span data-stu-id="b697d-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="b697d-154">Anwendungsname</span><span class="sxs-lookup"><span data-stu-id="b697d-154">Application name</span></span> 
    - <span data-ttu-id="b697d-155">Anwendungsversion</span><span class="sxs-lookup"><span data-stu-id="b697d-155">Application version</span></span> 
    - <span data-ttu-id="b697d-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b697d-156">Description</span></span> 
    - <span data-ttu-id="b697d-157">Publisher-Details (Beispiel: "O = <publisher name> , L = <location> , S = State, C = Country")</span><span class="sxs-lookup"><span data-stu-id="b697d-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
