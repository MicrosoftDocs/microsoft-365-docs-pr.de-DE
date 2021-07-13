---
title: Aktivieren von Microsoft 365-Nutzungsanalysen
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Erfahren Sie, wie Sie mit dem Sammeln von Daten für Ihren Mandanten beginnen, indem Sie die Vorlagen-App Microsoft 365 Usage Analytics in Power BI verwenden.
ms.openlocfilehash: c0e39a307ee75c661e0f91fcbbcfeae3d95c7257
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394749"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="5ba74-103">Aktivieren von Microsoft 365-Nutzungsanalysen</span><span class="sxs-lookup"><span data-stu-id="5ba74-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="5ba74-104">Microsoft 365 Nutzungsanalyse ist für Microsoft 365 US Government Community noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5ba74-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5ba74-105">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="5ba74-105">Before you begin</span></span>

<span data-ttu-id="5ba74-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 Admin Center, then initiate the template app in Power BI.</span><span class="sxs-lookup"><span data-stu-id="5ba74-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>

## <a name="get-power-bi"></a><span data-ttu-id="5ba74-107">So erhalten Sie Power BI</span><span class="sxs-lookup"><span data-stu-id="5ba74-107">Get Power BI</span></span>

<span data-ttu-id="5ba74-108">Wenn Sie noch nicht über Power BI verfügen, können Sie [sich für Power BI Pro registrieren.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="5ba74-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="5ba74-109">Wählen Sie **"Kostenlos testen"** aus, um sich für eine Testversion zu registrieren, oder **"Jetzt kaufen",** um Power BI Pro zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5ba74-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>


<span data-ttu-id="5ba74-110">Sie können auch **Produkte** erweitern, um eine Power BI-Version zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="5ba74-110">You can also expand **Products** to buy a version of Power BI.</span></span>

> [!NOTE]
> <span data-ttu-id="5ba74-111">Sie benötigen eine Power BI Pro Lizenz zum Installieren, Anpassen und Verteilen einer Vorlagen-App.</span><span class="sxs-lookup"><span data-stu-id="5ba74-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="5ba74-112">Weitere Informationen finden Sie unter ["Voraussetzungen".](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="5ba74-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="5ba74-113">Um Ihre Daten freizugeben, benötigen Sie und die Personen, mit denen Sie die Daten teilen, eine Power BI Pro Lizenz, oder der Inhalt muss sich in einem Arbeitsbereich in einem [Power BI Premiumdienst](/power-bi/service-premium-what-is)befinden.</span><span class="sxs-lookup"><span data-stu-id="5ba74-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span>

## <a name="enable-the-template-app"></a><span data-ttu-id="5ba74-114">Aktivieren der Vorlagen-App</span><span class="sxs-lookup"><span data-stu-id="5ba74-114">Enable the template app</span></span>

<span data-ttu-id="5ba74-115">Um die Vorlagen-App zu aktivieren, müssen Sie ein **globaler Administrator** sein.</span><span class="sxs-lookup"><span data-stu-id="5ba74-115">To enable the template app, you have to be a **Global administrator**.</span></span>

<span data-ttu-id="5ba74-116">Weitere Informationen finden Sie [unter "Administratorrollen".](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5ba74-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span>

1. <span data-ttu-id="5ba74-117">Wechseln Sie im Admin Center zur Registerkarte **Einstellungen** \> **Organisationseinstellungen** \> **für Dienste.**</span><span class="sxs-lookup"><span data-stu-id="5ba74-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span>

2. <span data-ttu-id="5ba74-118">Wählen Sie auf der Registerkarte **"Dienste"** die Option  **"Berichte"** aus.</span><span class="sxs-lookup"><span data-stu-id="5ba74-118">On the **Services** tab, select  **Reports**.</span></span>

3. <span data-ttu-id="5ba74-119">Legen Sie im daraufhin geöffneten Berichtsbereich **"Berichtsdaten verfügbar machen" für Microsoft 365 Nutzungsanalyse für Power BI** **auf "Beim** \> **Speichern"** fest.</span><span class="sxs-lookup"><span data-stu-id="5ba74-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span>

<span data-ttu-id="5ba74-120">Der Datensammlungsprozess wird in zwei bis 48 Stunden abgeschlossen, abhängig von der Größe Ihres Mandanten.</span><span class="sxs-lookup"><span data-stu-id="5ba74-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="5ba74-121">Die Schaltfläche **"Zu Power BI** wechseln" wird aktiviert (nicht mehr grau), wenn die Datensammlung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5ba74-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span>

## <a name="start-the-template-app"></a><span data-ttu-id="5ba74-122">Starten der Vorlagen-App</span><span class="sxs-lookup"><span data-stu-id="5ba74-122">Start the template app</span></span>

<span data-ttu-id="5ba74-123">Um die Vorlagen-App zu starten, müssen Sie entweder **ein globaler Administrator,** **ein Berichtsleser,** **Exchange Administrator,** **Skype for Business Administrator** oder **SharePoint Administrator** sein.</span><span class="sxs-lookup"><span data-stu-id="5ba74-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span>

1. <span data-ttu-id="5ba74-124">Kopieren Sie die Mandanten-ID, und wählen Sie **"Zu Power BI** wechseln" aus.</span><span class="sxs-lookup"><span data-stu-id="5ba74-124">Copy the tenant ID and select **Go to Power BI**.</span></span>

2. <span data-ttu-id="5ba74-125">Wenn Power BI angezeigt wird, melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="5ba74-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="5ba74-126">Wählen **Sie** dann Apps -> **aus** dem Navigationsmenü aus.</span><span class="sxs-lookup"><span data-stu-id="5ba74-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>

3. <span data-ttu-id="5ba74-127">Geben Sie auf der Registerkarte **"Apps"** Microsoft 365 in das Suchfeld ein, und wählen Sie dann **Microsoft 365 Nutzungsanalyse** abrufen \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="5ba74-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="5ba74-128">[![Wählen Sie "Jetzt abrufen" aus.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="5ba74-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>

4. <span data-ttu-id="5ba74-129">Sobald die App installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5ba74-129">Once the app is installed.</span></span> <span data-ttu-id="5ba74-130">Wählen Sie die Kachel aus, um sie zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5ba74-130">Select the tile to open it.</span></span>

5. <span data-ttu-id="5ba74-131">Wählen Sie **"App erkunden"** aus, um die App mit Beispieldaten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ba74-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="5ba74-132">Wählen Sie **Verbinden** aus, um die App mit den Daten Ihrer Organisation zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="5ba74-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6. <span data-ttu-id="5ba74-133">Wählen Sie im Verbinden **Verbinden** aus, um den Bildschirm für die **Nutzungsanalyse zu Microsoft 365,** geben Sie dann die Mandanten-ID (ohne Gedankenstriche) ein, die Sie in Schritt (1) kopiert haben, und wählen Sie **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="5ba74-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>

7. <span data-ttu-id="5ba74-134">Wählen Sie auf dem nächsten Bildschirm **OAuth2** als **Authentifizierungsmethode** \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="5ba74-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="5ba74-135">Wenn Sie eine andere Authentifizierungsmethode auswählen, schlägt die Verbindung mit der Vorlagen-App fehl.</span><span class="sxs-lookup"><span data-stu-id="5ba74-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>

    ![Auswählen eines Microsoft-Kontos als Authentifizierungsmethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. <span data-ttu-id="5ba74-137&quot;>Nachdem die Vorlagen-App instanziiert wurde, ist das Dashboard für die Nutzungsanalyse Microsoft 365 in Power BI im Web verfügbar.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5ba74-137&quot;>After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id=&quot;5ba74-138&quot;>Das erste Laden des Dashboards dauert zwischen 2 und 30 Minuten.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5ba74-138&quot;>The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>

<span data-ttu-id=&quot;5ba74-139&quot;>Aggregate auf Mandantenebene sind nach der Anmeldung in allen Berichten verfügbar.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5ba74-139&quot;>Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id=&quot;5ba74-140&quot;>**Details auf Benutzerebene werden erst am 5. des nächsten Kalendermonats verfügbar sein, nachdem Sie sich angemeldet haben.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5ba74-140&quot;>**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id=&quot;5ba74-141&quot;>Dies wirkt sich auf alle Berichte unter &quot;Benutzeraktivität&quot; aus (Tipps zum Anzeigen und Verwenden dieser Berichte finden Sie [unter &quot;Navigieren und Verwenden der Berichte in Microsoft 365 Nutzungsanalyse").](navigate-and-utilize-reports.md)</span><span class="sxs-lookup"><span data-stu-id="5ba74-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>

## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="5ba74-142">Anonymisieren der gesammelten Daten</span><span class="sxs-lookup"><span data-stu-id="5ba74-142">Make the collected data anonymous</span></span>

<span data-ttu-id="5ba74-143">Sie müssen ein globaler Administrator sein, um die für alle Berichte gesammelten Daten anonymisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="5ba74-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="5ba74-144">Dadurch werden identifizierbare Informationen wie Benutzer-, Gruppen- und Websitenamen in Berichten und in der Vorlagen-App ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="5ba74-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>

1. <span data-ttu-id="5ba74-145">Wechseln Sie im Admin Center zum **Einstellungen** \> **Org Einstellungen,** und wählen Sie unter **"Dienste"** die Option **"Berichte"** aus.</span><span class="sxs-lookup"><span data-stu-id="5ba74-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>

2. <span data-ttu-id="5ba74-146">Wählen Sie **"Berichte"** und dann **"Anonyme Bezeichner anzeigen" aus.**</span><span class="sxs-lookup"><span data-stu-id="5ba74-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="5ba74-147">Diese Einstellung wird sowohl auf die Verwendungsberichte als auch auf die Vorlagen-App angewendet.</span><span class="sxs-lookup"><span data-stu-id="5ba74-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>

3. <span data-ttu-id="5ba74-148">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="5ba74-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="5ba74-149">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="5ba74-149">Related content</span></span>

<span data-ttu-id="5ba74-150">[Informationen zu Nutzungsanalysen](usage-analytics.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="5ba74-150">[About usage analytics](usage-analytics.md) (article)</span></span>\
<span data-ttu-id="5ba74-151">[Abrufen der neuesten Version der Nutzungsanalyse](get-the-latest-version-of-usage-analytics.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="5ba74-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="5ba74-152">[Navigieren und Nutzen der Berichte in Microsoft 365 Nutzungsanalyse](navigate-and-utilize-reports.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="5ba74-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>