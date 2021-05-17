---
title: Verwalten von Apps in Microsoft Managed Desktop
description: Informationen zum Aktualisieren von Business-Apps, die auf Microsoft Managed Desktop-Geräten bereitgestellt werden
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
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="0f22a-104">Verwalten von Branchenanwendungen in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0f22a-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="0f22a-105">Es gibt mehrere Möglichkeiten zum Verwalten von App-Updates für Apps, die Sie in Microsoft Managed Desktop integrierte und auf Ihren Microsoft Managed Desktop-Geräten bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="0f22a-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="0f22a-106">Sie können App-Updates im Microsoft Managed Desktop-Portal oder intune erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f22a-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="0f22a-107">Aktualisieren von Unternehmensanwendungen in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0f22a-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="0f22a-108">**So aktualisieren Sie Ihre Business-Apps im Microsoft Managed Desktop-Portal**</span><span class="sxs-lookup"><span data-stu-id="0f22a-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="0f22a-109">Melden Sie sich beim [Microsoft Managed Desktop Admin-Portal an.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="0f22a-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="0f22a-110">Wählen **Sie unter Inventar** die Option **Apps aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="0f22a-111">Wählen Sie die App aus, die Sie aktualisieren möchten, und wählen Sie dann **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="0f22a-112">Wählen **Sie unter Verwalten** die Option Eigenschaften **aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="0f22a-113">Klicken **Sie auf App-Paketdatei,** und navigieren Sie dann, um eine neue App-Paketdatei hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="0f22a-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="0f22a-114">Wählen **Sie App-Paketdatei aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-114">Select **App package file**.</span></span>
7. <span data-ttu-id="0f22a-115">Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort Ihrer aktualisierten App-Datei.</span><span class="sxs-lookup"><span data-stu-id="0f22a-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="0f22a-116">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="0f22a-116">Select **Open**.</span></span> <span data-ttu-id="0f22a-117">Die App-Informationen werden mit den Paketinformationen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0f22a-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="0f22a-118">Vergewissern Sie **sich, dass die App-Version** das aktualisierte App-Paket widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="0f22a-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="0f22a-119">Die aktualisierte App wird auf den Geräten Ihres Benutzers bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0f22a-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="0f22a-120">Aktualisieren von Business-Apps in Intune</span><span class="sxs-lookup"><span data-stu-id="0f22a-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="0f22a-121">**So aktualisieren Sie Ihre Business-Apps in Intune**</span><span class="sxs-lookup"><span data-stu-id="0f22a-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="0f22a-122">Melden Sie sich beim [Azure-Portal an.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="0f22a-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="0f22a-123">Wählen **Sie Alle Dienste** Intune  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="0f22a-124">Intune befindet sich im **Abschnitt Überwachung + Verwaltung.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="0f22a-125">Wählen **Sie Client-Apps > Apps aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="0f22a-126">Suchen Und wählen Sie Ihre App in der Liste der Apps aus.</span><span class="sxs-lookup"><span data-stu-id="0f22a-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="0f22a-127">Wählen Sie **auf dem Blatt** Übersicht eigenschaften **aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="0f22a-128">Wählen **Sie App-Paketdatei aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-128">Select **App package file**.</span></span>
7. <span data-ttu-id="0f22a-129">Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort Ihrer aktualisierten App-Datei.</span><span class="sxs-lookup"><span data-stu-id="0f22a-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="0f22a-130">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="0f22a-130">Select **Open**.</span></span> <span data-ttu-id="0f22a-131">Die App-Informationen werden mit den Paketinformationen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0f22a-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="0f22a-132">Vergewissern Sie **sich, dass die App-Version** das aktualisierte App-Paket widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="0f22a-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="0f22a-133">Rollback einer App auf eine frühere Version</span><span class="sxs-lookup"><span data-stu-id="0f22a-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="0f22a-134">Wenn bei der Bereitstellung einer neuen Version einer App ein Fehler gefunden wird, können Sie ein Rollback auf eine frühere Version starten.</span><span class="sxs-lookup"><span data-stu-id="0f22a-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="0f22a-135">Der hier beschriebene Prozess gilt für Apps, bei denen der Typ als **Windows MSI Line-of-Business-App oder Windows-App** **(Win 32) aufgeführt** ist – Vorschau</span><span class="sxs-lookup"><span data-stu-id="0f22a-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="0f22a-136">**So erstellen Sie ein Rollback einer Business-Line-of-Business-App auf eine frühere Version**</span><span class="sxs-lookup"><span data-stu-id="0f22a-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="0f22a-137">Melden Sie sich beim [Microsoft Managed Desktop Admin-Portal an.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="0f22a-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="0f22a-138">Wählen **Sie unter Inventar** die Option **Apps aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="0f22a-139">Wählen Sie die App aus, die Sie zum Rollback benötigen, und wählen Sie dann **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="0f22a-140">Wählen **Sie unter Verwalten** die Option Eigenschaften **aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="0f22a-141">Wählen **Sie für Windows MSI-App-Line-of-Business-App-Apps** **App-Informationen** aus, und wählen Sie dann unter **App-Version** ignorieren die Option **Ja aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="0f22a-142">Wählen Sie für Windows-App **(Win 32) die** Vorschau von Apps aus, wählen Sie **App-Informationen** aus, **wählen** Sie Erkennungsregeln aus, und wählen Sie dann Hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="0f22a-143">Wenn eine MSI-Regel vor ist, überprüfen Sie, ob die Überprüfung der **MSI-Produktversion** auf **Nein festgelegt ist.**</span><span class="sxs-lookup"><span data-stu-id="0f22a-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="0f22a-144">[Laden Sie eine frühere Version der App-Quelldatei in](../get-started/deploy-apps.md) das Microsoft Managed Desktop Admin-Portal hoch.</span><span class="sxs-lookup"><span data-stu-id="0f22a-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

