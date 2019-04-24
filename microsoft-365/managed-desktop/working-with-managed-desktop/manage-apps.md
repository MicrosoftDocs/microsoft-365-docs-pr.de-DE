---
title: Verwalten von apps in Microsoft Managed Desktop
description: Informationen zum Aktualisieren von Branchen-apps, die auf Microsoft Managed Desktop-Geräten bereitgestellt werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: ce2765ef2ab176dc5d9a1d41db7e26549b007d79
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285945"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="21e72-104">Verwalten von Branchen-apps in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="21e72-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="21e72-105">Es gibt verschiedene Möglichkeiten, APP-Updates für apps zu verwalten, die Sie auf Microsoft Managed Desktop und auf Ihren von Microsoft verwalteten Desktop-Geräten bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="21e72-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="21e72-106">Sie können APP-Updates in Microsoft Managed Desktop Portal oder InTune vornehmen.</span><span class="sxs-lookup"><span data-stu-id="21e72-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="21e72-107">Aktualisieren von Branchen-apps in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="21e72-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="21e72-108">**So aktualisieren Sie Ihre Branchen-apps in Microsoft Managed Desktop Portal**</span><span class="sxs-lookup"><span data-stu-id="21e72-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="21e72-109">Melden Sie sich beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="21e72-109">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="21e72-110">Wählen Sie unter **Inventar**die Option **apps**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="21e72-111">Wählen Sie die APP aus, die Sie aktualisieren möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="21e72-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="21e72-112">Wählen Sie unter **Verwalten**die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="21e72-113">Klicken Sie auf **App-Paketdatei**, und navigieren Sie, um eine neue APP-Paketdatei hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="21e72-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="21e72-114">Wählen Sie **App-Paketdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-114">Select **App package file**.</span></span>
7. <span data-ttu-id="21e72-115">Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort der aktualisierten App-Datei.</span><span class="sxs-lookup"><span data-stu-id="21e72-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="21e72-116">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="21e72-116">Select **Open**.</span></span> <span data-ttu-id="21e72-117">Die APP-Informationen werden mit den Paketinformationen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="21e72-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="21e72-118">Stellen Sie sicher, dass die **App-Version** das aktualisierte APP-Paket widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="21e72-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="21e72-119">Die aktualisierte APP wird auf den Geräten der Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="21e72-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="21e72-120">Aktualisieren von Branchen-apps in InTune</span><span class="sxs-lookup"><span data-stu-id="21e72-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="21e72-121">**So aktualisieren Sie Ihre Branchen-apps in InTune**</span><span class="sxs-lookup"><span data-stu-id="21e72-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="21e72-122">Melden Sie sich beim [Azure-Portal](https://azure.portal.com)an.</span><span class="sxs-lookup"><span data-stu-id="21e72-122">Sign in to [Azure portal](https://azure.portal.com).</span></span>
2. <span data-ttu-id="21e72-123">Wählen Sie **alle Dienste** > **InTune**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="21e72-124">InTune befindet sich im Abschnitt **Monitoring + Management** .</span><span class="sxs-lookup"><span data-stu-id="21e72-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="21e72-125">Wählen Sie **Client apps _GT_ apps**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="21e72-126">Suchen und wählen Sie Ihre APP in der Liste der Apps aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="21e72-127">Wählen Sie im Blatt **Übersicht** die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="21e72-128">Wählen Sie **App-Paketdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-128">Select **App package file**.</span></span>
7. <span data-ttu-id="21e72-129">Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort der aktualisierten App-Datei.</span><span class="sxs-lookup"><span data-stu-id="21e72-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="21e72-130">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="21e72-130">Select **Open**.</span></span> <span data-ttu-id="21e72-131">Die APP-Informationen werden mit den Paketinformationen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="21e72-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="21e72-132">Stellen Sie sicher, dass die **App-Version** das aktualisierte APP-Paket widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="21e72-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="21e72-133">Zurücksetzen einer APP auf eine frühere Version</span><span class="sxs-lookup"><span data-stu-id="21e72-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="21e72-134">Wenn bei der Bereitstellung einer neuen Version einer APP ein Fehler gefunden wird, können Sie einen Rollback zu einer früheren Version ausführen.</span><span class="sxs-lookup"><span data-stu-id="21e72-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="21e72-135">Der hier beschriebene Prozess gilt für apps, bei denen der Typ als **Windows-MSI** -Branchen-APP oder **Windows-app (Win 32)-Vorschau** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="21e72-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="21e72-136">**So führen Sie ein Rollback für eine Branchen-App auf eine frühere Version aus**</span><span class="sxs-lookup"><span data-stu-id="21e72-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="21e72-137">Melden Sie sich beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="21e72-137">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="21e72-138">Wählen Sie unter **Inventar**die Option **apps**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="21e72-139">Wählen Sie die APP aus, die Sie zurücksetzen müssen, und wählen Sie dann **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="21e72-140">Wählen Sie unter **Verwalten**die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="21e72-141">Wählen Sie **app-Informationen**für **Windows-MSI-App-** Apps aus, und wählen Sie dann unter **App-Version ignorieren**die Option **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="21e72-142">Wählen Sie für **Windows-app (Win 32)-Vorschau** Apps die Option **app-Informationen**aus, wählen Sie **Erkennungsregeln**aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="21e72-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="21e72-143">Wenn eine MSI-Regel vorhanden ist, stellen Sie sicher, dass die **MSI-Produkt Versionsüberprüfung** auf **Nein**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="21e72-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="21e72-144">[Laden Sie eine frühere Version der APP-Quelldatei in das](../get-started/deploy-apps.md) Microsoft Managed Desktop Admin Portal hoch.</span><span class="sxs-lookup"><span data-stu-id="21e72-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

