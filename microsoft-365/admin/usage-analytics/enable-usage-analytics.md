---
title: Aktivieren von Microsoft 365-Nutzungsanalysen
f1.keywords:
- CSH
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Erfahren Sie, wie Sie mit der Microsoft 365 Usage Analytics-Vorlagen-app in Power BI mit dem Sammeln von Daten für Ihren Mandanten beginnen.
ms.openlocfilehash: 3c5e1a35b93b755b92710f0499599d849a6c251c
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262535"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="94b1e-103">Aktivieren von Microsoft 365-Nutzungsanalysen</span><span class="sxs-lookup"><span data-stu-id="94b1e-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="94b1e-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="94b1e-104">The admin center is changing.</span></span> <span data-ttu-id="94b1e-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="94b1e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="94b1e-106">Microsoft 365 Usage Analytics steht auch für Microsoft 365 US Government Community zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="94b1e-106">Microsoft 365 usage analytics is also available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="94b1e-107">Schritte zum Aktivieren von Microsoft 365-Nutzungsanalysen</span><span class="sxs-lookup"><span data-stu-id="94b1e-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="94b1e-108">Für den Einstieg in die Microsoft 365-Verwendungsanalyse müssen Sie zunächst die Daten im Microsoft 365 Admin Center verfügbar machen und dann die Vorlagen-app in Power BI initiieren.</span><span class="sxs-lookup"><span data-stu-id="94b1e-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="94b1e-109">So erhalten Sie Power BI</span><span class="sxs-lookup"><span data-stu-id="94b1e-109">Get Power BI</span></span>

<span data-ttu-id="94b1e-110">Wenn Sie noch nicht über Power BI verfügen, können Sie [sich für Power BI pro registrieren](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="94b1e-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="94b1e-111">Wählen Sie **kostenlos testen** aus, um sich für eine Testversion anzumelden, oder **kaufen Sie jetzt** , um Power BI pro zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="94b1e-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="94b1e-112">Sie können auch **Produkte** erweitern, um eine Power BI-Version zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="94b1e-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="94b1e-113">Sie benötigen eine Power BI pro-Lizenz zum Installieren, anpassen und Verteilen einer Vorlagen-app.</span><span class="sxs-lookup"><span data-stu-id="94b1e-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="94b1e-114">Weitere Informationen finden Sie unter [Voraussetzungen](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="94b1e-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="94b1e-115">Sie benötigen eine Power BI pro-Lizenz, um Ihre Inhalte freizugeben, und die Personen, mit denen Sie Sie gemeinsam nutzen, oder die Inhalte müssen sich in einem Arbeitsbereich mit einer [Premium-Kapazität](https://docs.microsoft.com/power-bi/service-premium-what-is)befinden.</span><span class="sxs-lookup"><span data-stu-id="94b1e-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="94b1e-116">Aktivieren der Vorlagen-App</span><span class="sxs-lookup"><span data-stu-id="94b1e-116">Enable the template app</span></span>

<span data-ttu-id="94b1e-117">Um die Vorlagen-APP zu aktivieren, müssen Sie entweder **globaler Administrator**, **berichtsleser**, **Exchange-Administrator**, **Skype for Business Administrator**oder **SharePoint-Administrator**sein.</span><span class="sxs-lookup"><span data-stu-id="94b1e-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="94b1e-118">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="94b1e-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="94b1e-119">Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.</span><span class="sxs-lookup"><span data-stu-id="94b1e-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="94b1e-120">Suchen Sie auf der Seite **Nutzung** die **Microsoft 365-Verwendungsanalyse** Karte, und wählen Sie **Erste Schritte**aus.</span><span class="sxs-lookup"><span data-stu-id="94b1e-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="94b1e-121">Legen Sie im Bereich Berichte, der geöffnet wird, für **Power BI den Eintrag Daten für Microsoft 365-Verwendungsanalyse verfügbar machen** **auf** \> **Speichern**fest.</span><span class="sxs-lookup"><span data-stu-id="94b1e-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="94b1e-122">Dadurch wird der Datensammlungsprozess initiiert und in 2 bis 48 Stunden je nach Größe des Mandanten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="94b1e-122">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="94b1e-123">Die Schaltfläche **Gehe zu Power BI** wird aktiviert (nicht mehr grau), wenn die Datenerfassung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="94b1e-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="94b1e-124">Initiieren der Vorlagen-App</span><span class="sxs-lookup"><span data-stu-id="94b1e-124">Initiate the template app</span></span>

<span data-ttu-id="94b1e-125">Um die Vorlagen-APP zu initiieren, müssen Sie entweder **globaler Administrator**, **berichtsleser**, **Exchange-Administrator**, **Skype for Business Administrator**oder **SharePoint-Administrator**sein.</span><span class="sxs-lookup"><span data-stu-id="94b1e-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="94b1e-126">Kopieren Sie die Mandanten-ID, und wählen Sie **zu Power BI wechseln**aus.</span><span class="sxs-lookup"><span data-stu-id="94b1e-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="94b1e-127">Wenn Power BI angezeigt wird, melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="94b1e-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="94b1e-128">Wählen Sie Apps aus dem Navigationsmenü aus, um apps >erhalten.</span><span class="sxs-lookup"><span data-stu-id="94b1e-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="94b1e-129">Geben Sie auf der Registerkarte **apps** in das Suchfeld Microsoft 365 ein, und wählen Sie dann **Microsoft 365 Verwendungsanalyse** \> **Abrufen**aus.</span><span class="sxs-lookup"><span data-stu-id="94b1e-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="94b1e-130">[![Wählen Sie Get it now aus.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="94b1e-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="94b1e-131">Sobald die APP installiert ist.</span><span class="sxs-lookup"><span data-stu-id="94b1e-131">Once the app is installed.</span></span> <span data-ttu-id="94b1e-132">Klicken Sie auf die Kachel, um Sie zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="94b1e-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="94b1e-133">Klicken Sie auf **App durchsuchen** , um die APP mit Beispieldaten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="94b1e-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="94b1e-134">Klicken Sie auf **verbinden** , um die APP mit den Daten Ihrer Organisation zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="94b1e-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="94b1e-135">Geben Sie nach dem Klicken auf **verbinden**im Bildschirm **Connect to Microsoft 365 Usage Analytics** die Mandanten-ID ein, die Sie in Schritt (1) \> **weiter**kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="94b1e-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id you copied in step (1) \> **Next**.</span></span>
    
7. <span data-ttu-id="94b1e-136">Wählen Sie auf dem nächsten Bildschirm **oAuth2** als **Authentifizierungsmethode** \> **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="94b1e-136">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="94b1e-137">Wenn Sie eine andere Authentifizierungsmethode auswählen, tritt bei der Verbindung zur Vorlagen-App ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="94b1e-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="94b1e-139">Nachdem die Vorlagen-App instanziiert wurde, ist das Microsoft 365 Usage Analytics-Dashboard in Power BI im Internet verfügbar.</span><span class="sxs-lookup"><span data-stu-id="94b1e-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="94b1e-140">Das erste Laden des Dashboards dauert zwischen 2 und 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="94b1e-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="94b1e-141">Aggregate auf Mandantenebene sind in allen Berichten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="94b1e-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="94b1e-142">**Details auf Benutzerebene werden erst nach dem 1. oder 15. Tag des Kalendermonats nach der Entscheidung verfügbar**.</span><span class="sxs-lookup"><span data-stu-id="94b1e-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="94b1e-143">Dies wirkt sich auf alle Berichte unter Benutzeraktivität aus (Weitere Tipps zum Anzeigen und Verwenden dieser Berichte finden Sie unter [navigieren und Verwenden der Berichte in Microsoft 365-Verwendungsanalyse](navigate-and-utilize-reports.md) ).</span><span class="sxs-lookup"><span data-stu-id="94b1e-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="94b1e-144">Anonymisieren der gesammelten Daten</span><span class="sxs-lookup"><span data-stu-id="94b1e-144">Make the collected data anonymous</span></span>

<span data-ttu-id="94b1e-145">Sie müssen ein globaler Administrator sein, um die für alle Berichte gesammelten Daten anonymisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="94b1e-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="94b1e-146">Dadurch werden identifizierbare Informationen wie Benutzer-, Gruppen-und Websitenamen in Berichten und in der Vorlagen-App ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="94b1e-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="94b1e-147">Wechseln Sie im Admin Center zu den **Einstellungen** der \> **org**-Einstellungen, und wählen Sie unter **Dienste** die Registerkarte **Berichte**aus.</span><span class="sxs-lookup"><span data-stu-id="94b1e-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="94b1e-148">Wählen Sie **Berichte**aus, und wählen Sie dann **Anonyme Bezeichner anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="94b1e-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="94b1e-149">Diese Einstellung wird sowohl auf die Verwendungsberichte als auch auf die Vorlagen-App angewendet.</span><span class="sxs-lookup"><span data-stu-id="94b1e-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="94b1e-150">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="94b1e-150">Select **Save changes**.</span></span>
