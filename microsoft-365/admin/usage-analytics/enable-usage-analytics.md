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
description: Erfahren Sie, wie Sie mit dem Sammeln von Daten für Ihren Mandanten mithilfe der Microsoft 365 Usage Analytics-Vorlagen-App in Power BI beginnen.
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114237"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="057eb-103">Aktivieren von Microsoft 365-Nutzungsanalysen</span><span class="sxs-lookup"><span data-stu-id="057eb-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="057eb-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="057eb-104">The admin center is changing.</span></span> <span data-ttu-id="057eb-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="057eb-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="057eb-106">Microsoft 365-Nutzungsanalysen sind für die Microsoft 365 US Government Community noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="057eb-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="057eb-107">Schritte zum Aktivieren der Microsoft 365-Verwendungsanalyse</span><span class="sxs-lookup"><span data-stu-id="057eb-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="057eb-108">Um mit microsoft 365-Nutzungsanalysen zu beginnen, müssen Sie die Daten zuerst im Microsoft 365 Admin Center verfügbar machen und dann die Vorlagen-App in Power BI initiieren.</span><span class="sxs-lookup"><span data-stu-id="057eb-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="057eb-109">So erhalten Sie Power BI</span><span class="sxs-lookup"><span data-stu-id="057eb-109">Get Power BI</span></span>

<span data-ttu-id="057eb-110">Wenn Sie noch nicht über Power BI verfügen, können Sie sich [für Power BI Pro registrieren.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="057eb-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="057eb-111">Wählen **Sie "Kostenlos testen"** aus, um sich für eine Testversion zu registrieren, oder kaufen **Sie jetzt,** um Power BI Pro zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="057eb-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="057eb-112">Sie können auch **Produkte** erweitern, um eine Power BI-Version zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="057eb-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="057eb-113">Sie benötigen eine Power BI Pro-Lizenz, um eine Vorlagen-App zu installieren, anzupassen und zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="057eb-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="057eb-114">Weitere Informationen finden Sie unter ["Voraussetzungen".](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="057eb-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="057eb-115">Um Ihre Daten zu teilen, benötigen Sie und die Personen, für die Sie die Daten freigeben, eine Power BI Pro-Lizenz, oder die Inhalte müssen sich in einem Arbeitsbereich in einem [Power BI -Premium-Dienst befinden.](https://docs.microsoft.com/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="057eb-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="057eb-116">Aktivieren der Vorlagen-App</span><span class="sxs-lookup"><span data-stu-id="057eb-116">Enable the template app</span></span>

<span data-ttu-id="057eb-117">Um die Vorlagen-App zu aktivieren, müssen Sie ein globaler **Administrator sein.**</span><span class="sxs-lookup"><span data-stu-id="057eb-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="057eb-118">Weitere [Informationen finden Sie unter "Administratorrollen".](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="057eb-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="057eb-119">Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.</span><span class="sxs-lookup"><span data-stu-id="057eb-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="057eb-120">Suchen Sie **auf der Seite** "Verwendung" die Microsoft **365-Verwendungsanalysekarte,** und wählen Sie **"Erste Schritte" aus.**</span><span class="sxs-lookup"><span data-stu-id="057eb-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="057eb-121">Legen Sie im bereich "Berichte", der geöffnet wird, "Daten für **Microsoft 365-Nutzungsanalysen** für Power BI verfügbar machen" auf **"On** \> **Save" fest.**</span><span class="sxs-lookup"><span data-stu-id="057eb-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="057eb-122">Der Datensammlungsprozess wird je nach Größe Ihres Mandanten in zwei bis 48 Stunden abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="057eb-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="057eb-123">Die **Schaltfläche "Zu Power BI wechseln"** wird nach Abschluss der Datensammlung aktiviert (nicht mehr grau).</span><span class="sxs-lookup"><span data-stu-id="057eb-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="057eb-124">Starten der Vorlagen-App</span><span class="sxs-lookup"><span data-stu-id="057eb-124">Start the template app</span></span>

<span data-ttu-id="057eb-125">Zum Starten der Vorlagen-App müssen Sie entweder globaler **Administrator,** Berichtsleser, Exchange-Administrator, **Skype for Business-Administrator** oder  **SharePoint-Administrator sein.**</span><span class="sxs-lookup"><span data-stu-id="057eb-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="057eb-126">Kopieren Sie die Mandanten-ID, und wählen **Sie "Zu Power BI wechseln" aus.**</span><span class="sxs-lookup"><span data-stu-id="057eb-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="057eb-127">Wenn Power BI angezeigt wird, melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="057eb-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="057eb-128">Wählen Sie **dann Apps aus** dem -> **Navigationsmenü** aus.</span><span class="sxs-lookup"><span data-stu-id="057eb-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="057eb-129">Geben Sie **auf der** Registerkarte "Apps" Microsoft 365 in das Suchfeld ein, und wählen Sie dann **"Microsoft 365-Verwendungsanalyse** jetzt \> **herunterladen" aus.**</span><span class="sxs-lookup"><span data-stu-id="057eb-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="057eb-130">[![Auswählen von "Jetzt erhalten"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="057eb-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="057eb-131">Sobald die App installiert ist.</span><span class="sxs-lookup"><span data-stu-id="057eb-131">Once the app is installed.</span></span> <span data-ttu-id="057eb-132">Wählen Sie die Kachel aus, um sie zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="057eb-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="057eb-133">Wählen **Sie "App durchsuchen"** aus, um die App mit Beispieldaten anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="057eb-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="057eb-134">Wählen **Sie "Verbinden"** aus, um die App mit den Daten Ihrer Organisation zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="057eb-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="057eb-135">Wählen **Sie "Verbinden"** auf dem Bildschirm "Mit **Microsoft 365-Verwendungsanalyse** verbinden" aus, geben Sie dann die Mandanten-ID (ohne Bindestriche) ein, die Sie in Schritt (1) kopiert haben, und wählen Sie **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="057eb-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="057eb-136">Wählen Sie auf dem nächsten Bildschirm **OAuth2** als **Authentifizierungsmethode** \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="057eb-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="057eb-137">Wenn Sie eine andere Authentifizierungsmethode auswählen, kann die Verbindung mit der Vorlagen-App nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="057eb-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Auswählen des Microsoft-Kontos als Authentifizierungsmethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="057eb-139">Nachdem die Vorlagen-App instanziiert wurde, ist das Microsoft 365-Dashboard für die Verwendungsanalyse in Power BI im Web verfügbar.</span><span class="sxs-lookup"><span data-stu-id="057eb-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="057eb-140">Das anfängliche Laden des Dashboards dauert zwischen 2 und 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="057eb-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="057eb-141">Aggregate auf Mandantenebene sind nach der Opt-in-Option in allen Berichten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="057eb-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="057eb-142">Details auf Benutzerebene werden erst gegen den 5. des nächsten Kalendermonats nach **der Opt-in-Option verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="057eb-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="057eb-143">Dies wirkt sich auf alle Berichte unter "Benutzeraktivität" aus (Tipps zum Anzeigen und Verwenden dieser Berichte finden Sie in den Berichten [in der Microsoft 365-Verwendungsanalyse](navigate-and-utilize-reports.md) unter "Navigieren".</span><span class="sxs-lookup"><span data-stu-id="057eb-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="057eb-144">Anonymisieren der gesammelten Daten</span><span class="sxs-lookup"><span data-stu-id="057eb-144">Make the collected data anonymous</span></span>

<span data-ttu-id="057eb-145">Sie müssen ein globaler Administrator sein, um die für alle Berichte gesammelten Daten anonymisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="057eb-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="057eb-146">Dadurch werden identifizierbare Informationen wie Benutzer-, Gruppen- und Websitenamen in Berichten und in der Vorlagen-App ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="057eb-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="057eb-147">Wechseln Sie im Admin  Center zur Einstellungsorganisationseinstellungen, und wählen Sie unter \>  **"Dienste"** die Option **"Berichte" aus.**</span><span class="sxs-lookup"><span data-stu-id="057eb-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="057eb-148">Wählen Sie **"Berichte"** und dann **"Anonyme Bezeichner anzeigen" aus.**</span><span class="sxs-lookup"><span data-stu-id="057eb-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="057eb-149">Diese Einstellung wird sowohl auf die Verwendungsberichte als auch auf die Vorlagen-App angewendet.</span><span class="sxs-lookup"><span data-stu-id="057eb-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="057eb-150">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="057eb-150">Select **Save changes**.</span></span>
