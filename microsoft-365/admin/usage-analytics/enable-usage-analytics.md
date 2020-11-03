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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Erfahren Sie, wie Sie mit der Microsoft 365 Usage Analytics-Vorlagen-app in Power BI mit dem Sammeln von Daten für Ihren Mandanten beginnen.
ms.openlocfilehash: 0817e6441540086bf679c6533b1bad2e4087b4b9
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841457"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="2acf7-103">Aktivieren von Microsoft 365-Nutzungsanalysen</span><span class="sxs-lookup"><span data-stu-id="2acf7-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="2acf7-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="2acf7-104">The admin center is changing.</span></span> <span data-ttu-id="2acf7-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="2acf7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="2acf7-106">Microsoft 365-Verwendungsanalyse ist noch nicht für Microsoft 365 US Government Community verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2acf7-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="2acf7-107">Schritte zum Aktivieren von Microsoft 365-Nutzungsanalysen</span><span class="sxs-lookup"><span data-stu-id="2acf7-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="2acf7-108">Für den Einstieg in die Microsoft 365-Verwendungsanalyse müssen Sie zunächst die Daten im Microsoft 365 Admin Center verfügbar machen und dann die Vorlagen-app in Power BI initiieren.</span><span class="sxs-lookup"><span data-stu-id="2acf7-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="2acf7-109">So erhalten Sie Power BI</span><span class="sxs-lookup"><span data-stu-id="2acf7-109">Get Power BI</span></span>

<span data-ttu-id="2acf7-110">Wenn Sie noch nicht über Power BI verfügen, können Sie [sich für Power BI pro registrieren](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="2acf7-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="2acf7-111">Wählen Sie **kostenlos testen** aus, um sich für eine Testversion anzumelden, oder **kaufen Sie jetzt** , um Power BI pro zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2acf7-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="2acf7-112">Sie können auch **Produkte** erweitern, um eine Power BI-Version zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="2acf7-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="2acf7-113">Sie benötigen eine Power BI pro-Lizenz zum Installieren, anpassen und Verteilen einer Vorlagen-app.</span><span class="sxs-lookup"><span data-stu-id="2acf7-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="2acf7-114">Weitere Informationen finden Sie unter [Voraussetzungen](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="2acf7-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="2acf7-115">Um Ihre Daten freizugeben, benötigen Sie und die Personen, mit denen Sie die Daten teilen, eine Power BI pro-Lizenz, oder der Inhalt muss sich in einem Arbeitsbereich in einem [Power BI Premium-Dienst](https://docs.microsoft.com/power-bi/service-premium-what-is)befinden.</span><span class="sxs-lookup"><span data-stu-id="2acf7-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="2acf7-116">Aktivieren der Vorlagen-App</span><span class="sxs-lookup"><span data-stu-id="2acf7-116">Enable the template app</span></span>

<span data-ttu-id="2acf7-117">Um die Vorlagen-APP zu aktivieren, müssen Sie eine der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="2acf7-117">To enable the template app, you have to be one of the following:</span></span> 
- <span data-ttu-id="2acf7-118">**Globaler Administrator**</span><span class="sxs-lookup"><span data-stu-id="2acf7-118">**Global administrator**</span></span>
- <span data-ttu-id="2acf7-119">**Berichtsleser**</span><span class="sxs-lookup"><span data-stu-id="2acf7-119">**Report reader**</span></span>
- <span data-ttu-id="2acf7-120">**Exchange-Administrator**</span><span class="sxs-lookup"><span data-stu-id="2acf7-120">**Exchange administrator**</span></span>
- <span data-ttu-id="2acf7-121">**Skype for Business Administrator**</span><span class="sxs-lookup"><span data-stu-id="2acf7-121">**Skype for Business administrator**</span></span>
- <span data-ttu-id="2acf7-122">**SharePoint-Administrator**</span><span class="sxs-lookup"><span data-stu-id="2acf7-122">**SharePoint administrator**</span></span> 
  
<span data-ttu-id="2acf7-123">Weitere Informationen finden Sie unter Informationen [zu Administratorrollen](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="2acf7-123">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="2acf7-124">Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.</span><span class="sxs-lookup"><span data-stu-id="2acf7-124">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="2acf7-125">Suchen Sie auf der Seite **Nutzung** die **Microsoft 365-Verwendungsanalyse** Karte, und wählen Sie **Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="2acf7-125">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started** .</span></span>
    
3. <span data-ttu-id="2acf7-126">Legen Sie im Bereich Berichte, der geöffnet wird, für **Power BI den Eintrag Daten für Microsoft 365-Verwendungsanalyse verfügbar machen** **auf** \> **Speichern** fest.</span><span class="sxs-lookup"><span data-stu-id="2acf7-126">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save** .</span></span> 
  
<span data-ttu-id="2acf7-127">Der Datensammlungsprozess wird in Abhängigkeit von der Größe des Mandanten in zwei bis 48 Stunden abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2acf7-127">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="2acf7-128">Die Schaltfläche **Gehe zu Power BI** wird aktiviert (nicht mehr grau), wenn die Datenerfassung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2acf7-128">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="2acf7-129">Starten der Vorlagen-App</span><span class="sxs-lookup"><span data-stu-id="2acf7-129">Start the template app</span></span>

<span data-ttu-id="2acf7-130">Um die Vorlagen-APP zu starten, müssen Sie entweder **globaler Administrator** , **berichtsleser** , **Exchange-Administrator** , **Skype for Business Administrator** oder **SharePoint-Administrator** sein.</span><span class="sxs-lookup"><span data-stu-id="2acf7-130">To start the template app, you have to be either a **global administrator** , **report reader** , **Exchange administrator** , **Skype for Business administrator** , or **SharePoint administrator** .</span></span> 
  
1. <span data-ttu-id="2acf7-131">Kopieren Sie die Mandanten-ID, und wählen Sie **zu Power BI wechseln** aus.</span><span class="sxs-lookup"><span data-stu-id="2acf7-131">Copy the tenant ID and select **Go to Power BI** .</span></span>
    
2.  <span data-ttu-id="2acf7-132">Wenn Power BI angezeigt wird, melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="2acf7-132">When you get to Power BI, sign in.</span></span> <span data-ttu-id="2acf7-133">**Wählen Sie dann apps** -> **Get apps** aus dem Navigationsmenü aus.</span><span class="sxs-lookup"><span data-stu-id="2acf7-133">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="2acf7-134">Geben Sie auf der Registerkarte **apps** in das Suchfeld Microsoft 365 ein, und wählen Sie dann **Microsoft 365 Verwendungsanalyse** \> **Abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="2acf7-134">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now** .</span></span>

    <span data-ttu-id="2acf7-135">[![Wählen Sie Get it now aus.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="2acf7-135">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="2acf7-136">Sobald die APP installiert ist.</span><span class="sxs-lookup"><span data-stu-id="2acf7-136">Once the app is installed.</span></span> <span data-ttu-id="2acf7-137">Wählen Sie die Kachel aus, um Sie zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2acf7-137">Select the tile to open it.</span></span>

5.  <span data-ttu-id="2acf7-138">Wählen Sie **App erkunden** aus, um die APP mit Beispieldaten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2acf7-138">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="2acf7-139">Wählen Sie **Connect** aus, um die APP mit den Daten Ihrer Organisation zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="2acf7-139">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="2acf7-140">Klicken Sie auf der Seite **Connect to Microsoft 365 Usage Analytics** auf **verbinden** , und geben Sie dann die Mandanten-ID (ohne Bindestriche) ein, die Sie in Schritt (1) kopiert haben, und wählen Sie **weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="2acf7-140">Choose **Connect** , on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next** .</span></span>
    
7. <span data-ttu-id="2acf7-141">Wählen Sie auf dem nächsten Bildschirm **OAuth2** als **Authentifizierungsmethode** \> **Anmelden** aus.</span><span class="sxs-lookup"><span data-stu-id="2acf7-141">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in** .</span></span> <span data-ttu-id="2acf7-142">Wenn Sie eine andere Authentifizierungsmethode auswählen, tritt bei der Verbindung zur Vorlagen-App ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="2acf7-142">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Auswählen von Microsoft-Konto als Authentifizierungsmethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="2acf7-144">Nachdem die Vorlagen-App instanziiert wurde, steht das Microsoft 365-Dashboard für die Verwendungsanalyse in Power BI im Internet zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2acf7-144">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="2acf7-145">Das erste Laden des Dashboards dauert zwischen 2 und 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="2acf7-145">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="2acf7-146">Aggregate auf Mandantenebene sind in allen Berichten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2acf7-146">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="2acf7-147">**Details auf Benutzerebene werden erst nach dem 1. oder 15. Tag des Kalendermonats nach der Entscheidung verfügbar** .</span><span class="sxs-lookup"><span data-stu-id="2acf7-147">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in** .</span></span> <span data-ttu-id="2acf7-148">Dies wirkt sich auf alle Berichte unter Benutzeraktivität aus.</span><span class="sxs-lookup"><span data-stu-id="2acf7-148">This will impact all reports under User Activity.</span></span> <span data-ttu-id="2acf7-149">Tipps zum Anzeigen und Verwenden dieser Berichte finden Sie unter [navigieren und Verwenden der Berichte in Microsoft 365-Verwendungsanalyse](navigate-and-utilize-reports.md) .</span><span class="sxs-lookup"><span data-stu-id="2acf7-149">See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports.</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="2acf7-150">Anonymisieren der gesammelten Daten</span><span class="sxs-lookup"><span data-stu-id="2acf7-150">Make the collected data anonymous</span></span>

<span data-ttu-id="2acf7-151">Sie müssen ein globaler Administrator sein, um die für alle Berichte gesammelten Daten anonymisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="2acf7-151">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="2acf7-152">Dadurch werden identifizierbare Informationen wie Benutzer-, Gruppen-und Websitenamen in Berichten und in der Vorlagen-App ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="2acf7-152">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="2acf7-153">Wechseln Sie im Admin Center zu den **Einstellungen** der \> **org** -Einstellungen, und wählen Sie unter **Dienste** die Registerkarte **Berichte** aus.</span><span class="sxs-lookup"><span data-stu-id="2acf7-153">In the admin center, go to the **Settings** \> **Org Settings** , and under **Services** tab, choose **Reports** .</span></span>
    
2. <span data-ttu-id="2acf7-154">Wählen Sie **Berichte** aus, und wählen Sie dann **Anonyme Bezeichner anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="2acf7-154">Select **Reports** , and then choose to **Display anonymous identifiers** .</span></span> <span data-ttu-id="2acf7-155">Diese Einstellung wird sowohl auf die Verwendungsberichte als auch auf die Vorlagen-App angewendet.</span><span class="sxs-lookup"><span data-stu-id="2acf7-155">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="2acf7-156">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="2acf7-156">Select **Save changes** .</span></span>
