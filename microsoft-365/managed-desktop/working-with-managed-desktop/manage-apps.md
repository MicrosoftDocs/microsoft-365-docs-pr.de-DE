---
title: Verwalten von Apps in Microsoft Managed Desktop
description: Informationen zum Aktualisieren von Branchen-Apps, die auf Microsoft Managed Desktop Geräten bereitgestellt werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: b016d8458b4b4cc9f6b684d3b8a3c0a1e1322fef
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925407"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="d5316-104">Verwalten von Branchenanwendungen in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d5316-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="d5316-105">Es gibt verschiedene Möglichkeiten zum Verwalten von App-Updates für Apps, die Sie in Microsoft Managed Desktop integriert und auf Ihren Microsoft Managed Desktop Geräten bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="d5316-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d5316-106">Sie können App-Updates in Microsoft Managed Desktop Portal oder Intune vornehmen.</span><span class="sxs-lookup"><span data-stu-id="d5316-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="d5316-107">Aktualisieren von Branchen-Apps in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d5316-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="d5316-108">**So aktualisieren Sie Ihre Branchen-Apps im Microsoft Managed Desktop Portal**</span><span class="sxs-lookup"><span data-stu-id="d5316-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="d5316-109">Melden Sie sich bei [Microsoft Managed Desktop Admin-Portal](https://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="d5316-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="d5316-110">Wählen Sie unter **"Inventar"** die Option **"Apps"** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="d5316-111">Wählen Sie die App aus, die Sie aktualisieren möchten, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="d5316-112">Wählen Sie unter **"Verwalten"** die Option **"Eigenschaften"** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="d5316-113">Klicken Sie auf **"App-Paketdatei",** und navigieren Sie dann zum Hochladen einer neuen App-Paketdatei.</span><span class="sxs-lookup"><span data-stu-id="d5316-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="d5316-114">Wählen Sie **die App-Paketdatei** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-114">Select **App package file**.</span></span>
7. <span data-ttu-id="d5316-115">Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort Ihrer aktualisierten App-Datei.</span><span class="sxs-lookup"><span data-stu-id="d5316-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="d5316-116">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="d5316-116">Select **Open**.</span></span> <span data-ttu-id="d5316-117">Die App-Informationen werden mit den Paketinformationen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d5316-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="d5316-118">Stellen Sie sicher, dass die **App-Version** das aktualisierte App-Paket widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="d5316-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="d5316-119">Die aktualisierte App wird auf den Geräten Des Benutzers bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d5316-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="d5316-120">Aktualisieren von Branchen-Apps in Intune</span><span class="sxs-lookup"><span data-stu-id="d5316-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="d5316-121">**So aktualisieren Sie Ihre Branchen-Apps in Intune**</span><span class="sxs-lookup"><span data-stu-id="d5316-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="d5316-122">Melden Sie sich beim [Azure-Portal](https://portal.azure.com)an.</span><span class="sxs-lookup"><span data-stu-id="d5316-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="d5316-123">Wählen Sie **"Alle Dienste**  >  **Intune"** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="d5316-124">Intune befindet sich im Abschnitt **"Überwachung + Verwaltung".**</span><span class="sxs-lookup"><span data-stu-id="d5316-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="d5316-125">Wählen Sie **Client-Apps > Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="d5316-126">Suchen und wählen Sie Ihre App in der Liste der Apps aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="d5316-127">Wählen Sie im Blatt **"Übersicht"** die Option **"Eigenschaften"** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="d5316-128">Wählen Sie **die App-Paketdatei** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-128">Select **App package file**.</span></span>
7. <span data-ttu-id="d5316-129">Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort Ihrer aktualisierten App-Datei.</span><span class="sxs-lookup"><span data-stu-id="d5316-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="d5316-130">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="d5316-130">Select **Open**.</span></span> <span data-ttu-id="d5316-131">Die App-Informationen werden mit den Paketinformationen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d5316-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="d5316-132">Stellen Sie sicher, dass die **App-Version** das aktualisierte App-Paket widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="d5316-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="d5316-133">Zurücksetzen einer App auf eine frühere Version</span><span class="sxs-lookup"><span data-stu-id="d5316-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="d5316-134">Wenn beim Bereitstellen einer neuen Version einer App ein Fehler gefunden wird, können Sie ein Rollback auf eine frühere Version ausführen.</span><span class="sxs-lookup"><span data-stu-id="d5316-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="d5316-135">Der hier beschriebene Prozess gilt für Apps, bei denen der Typ als **Windows MSI-Branchen-App** oder **Windows-App (Win 32)** aufgeführt ist – Vorschau</span><span class="sxs-lookup"><span data-stu-id="d5316-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="d5316-136">**So führen Sie ein Rollback einer Branchen-App auf eine frühere Version aus**</span><span class="sxs-lookup"><span data-stu-id="d5316-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="d5316-137">Melden Sie sich bei [Microsoft Managed Desktop Admin-Portal](https://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="d5316-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="d5316-138">Wählen Sie unter **"Inventar"** die Option **"Apps"** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="d5316-139">Wählen Sie die App aus, die Sie zurücksetzen müssen, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="d5316-140">Wählen Sie unter **"Verwalten"** die Option **"Eigenschaften"** aus.</span><span class="sxs-lookup"><span data-stu-id="d5316-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="d5316-141">For **Windows MSI line-of-business app** apps, select App **information,** and then under **Ignore app version**, select **Yes**.</span><span class="sxs-lookup"><span data-stu-id="d5316-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="d5316-142">For **Windows app (Win 32) - preview** apps, select App **information,** select **Detection rules,** and then select **Add**.</span><span class="sxs-lookup"><span data-stu-id="d5316-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="d5316-143">Wenn eine MSI-Regel vorhanden ist, überprüfen Sie, ob die **MSI-Produktversionsprüfung** auf **"Nein"** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d5316-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="d5316-144">[Hochladen eine frühere Version der App-Quelldatei](../get-started/deploy-apps.md) an Microsoft Managed Desktop Verwaltungsportal an.</span><span class="sxs-lookup"><span data-stu-id="d5316-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

