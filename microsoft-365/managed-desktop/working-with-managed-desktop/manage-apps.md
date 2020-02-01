---
title: Verwalten von apps in Microsoft Managed Desktop
description: Informationen zum Aktualisieren von Branchen-apps, die auf Microsoft Managed Desktop-Geräten bereitgestellt werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600682"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="542ed-104">Verwalten von Branchenanwendungen in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="542ed-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="542ed-105">Es gibt verschiedene Möglichkeiten, APP-Updates für apps zu verwalten, die Sie auf dem Microsoft Managed Desktop installiert und auf Ihren verwalteten Microsoft-Desktop-Geräten bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="542ed-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="542ed-106">Sie können APP-Updates in Microsoft Managed Desktop Portal oder InTune vornehmen.</span><span class="sxs-lookup"><span data-stu-id="542ed-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="542ed-107">Aktualisieren von Branchenanwendungen in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="542ed-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="542ed-108">**So aktualisieren Sie Ihre Branchen-apps im Microsoft Managed Desktop Portal**</span><span class="sxs-lookup"><span data-stu-id="542ed-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="542ed-109">Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="542ed-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="542ed-110">Wählen Sie unter **Inventar**die Option **apps**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="542ed-111">Wählen Sie die APP aus, die Sie aktualisieren möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="542ed-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="542ed-112">Wählen Sie unter **Verwalten**die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="542ed-113">Klicken Sie auf **App-Paketdatei**und dann auf Durchsuchen, um eine neue APP-Paketdatei hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="542ed-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="542ed-114">Wählen Sie **App-Paketdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-114">Select **App package file**.</span></span>
7. <span data-ttu-id="542ed-115">Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort der aktualisierten App-Datei.</span><span class="sxs-lookup"><span data-stu-id="542ed-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="542ed-116">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="542ed-116">Select **Open**.</span></span> <span data-ttu-id="542ed-117">Die APP-Informationen werden mit den Paketinformationen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="542ed-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="542ed-118">Stellen Sie sicher, dass die **App-Version** das aktualisierte APP-Paket widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="542ed-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="542ed-119">Die aktualisierte APP wird auf den Geräten Ihrer Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="542ed-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="542ed-120">Aktualisieren von Branchenanwendungen in InTune</span><span class="sxs-lookup"><span data-stu-id="542ed-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="542ed-121">**So aktualisieren Sie Ihre Branchen-apps in InTune**</span><span class="sxs-lookup"><span data-stu-id="542ed-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="542ed-122">Melden Sie sich beim [Azure-Portal](https://portal.azure.com)an.</span><span class="sxs-lookup"><span data-stu-id="542ed-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="542ed-123">Wählen Sie **alle Dienste** > **InTune**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="542ed-124">InTune befindet sich im Abschnitt **Überwachung + Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="542ed-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="542ed-125">Wählen Sie **Client apps #a0 apps**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="542ed-126">Suchen Sie Ihre APP in der Liste der apps, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="542ed-127">Wählen Sie im Blatt **Übersicht** die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="542ed-128">Wählen Sie **App-Paketdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-128">Select **App package file**.</span></span>
7. <span data-ttu-id="542ed-129">Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort der aktualisierten App-Datei.</span><span class="sxs-lookup"><span data-stu-id="542ed-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="542ed-130">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="542ed-130">Select **Open**.</span></span> <span data-ttu-id="542ed-131">Die APP-Informationen werden mit den Paketinformationen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="542ed-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="542ed-132">Stellen Sie sicher, dass die **App-Version** das aktualisierte APP-Paket widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="542ed-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="542ed-133">Wiederherstellen einer APP auf eine frühere Version</span><span class="sxs-lookup"><span data-stu-id="542ed-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="542ed-134">Wenn beim Bereitstelleneiner neuen Version einer APP ein Fehler festgestellt wurde, können Sie auf eine frühere Version zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="542ed-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="542ed-135">Der hier dargestellte Vorgang gilt für apps, bei denen Type als **Windows-MSI** -Branchen-APP oder **Windows-app (Win 32) – Vorschau** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="542ed-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="542ed-136">**So setzen Sie eine Branchen-App auf eine frühere Version zurück**</span><span class="sxs-lookup"><span data-stu-id="542ed-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="542ed-137">Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="542ed-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="542ed-138">Wählen Sie unter **Inventar**die Option **apps**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="542ed-139">Wählen Sie die APP aus, die Sie für ein Rollback ausführen möchten, und wählen Sie dann **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="542ed-140">Wählen Sie unter **Verwalten**die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="542ed-141">Wählen Sie für **Windows-MSI-App-** Apps die Option **app-Informationen**aus, und wählen Sie dann unter APP- **Version ignorieren**die Option **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="542ed-142">Für **Windows-app (Win 32) – Vorschau** von apps, wählen Sie **app-Informationen**aus, wählen Sie **Erkennungsregeln**aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="542ed-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="542ed-143">Wenn eine MSI-Regel vorhanden ist, stellen Sie sicher, dass die **MSI-Produkt Versionsüberprüfung** auf **Nein**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="542ed-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="542ed-144">[Laden Sie eine frühere Version der APP-Quelldatei in das](../get-started/deploy-apps.md) Verwaltungsportal von Microsoft Managed Desktop hoch.</span><span class="sxs-lookup"><span data-stu-id="542ed-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

