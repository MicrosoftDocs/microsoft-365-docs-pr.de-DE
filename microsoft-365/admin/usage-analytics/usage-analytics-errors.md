---
title: Problembehandlung bei Microsoft 365-Verwendungsanalysen
f1.keywords:
- NOCSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Erfahren Sie, wie Sie Probleme mit der Microsoft 365 Usage Analytics-Vorlagen-App behandeln.
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580738"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="275fb-103">Problembehandlung bei Microsoft 365-Verwendungsanalysen</span><span class="sxs-lookup"><span data-stu-id="275fb-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="275fb-104">Sehen Sie sich die folgende Liste von Fehlermeldungen an, um Hilfe zu den häufigsten Problemen mit Microsoft 365-Verwendungsanalysen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="275fb-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="275fb-105">Ihre Anfrage kann nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="275fb-105">We are unable to process your request.</span></span> <span data-ttu-id="275fb-106">Sie müssen diese Daten zuerst über das Microsoft 365 Admin Center abonnieren.</span><span class="sxs-lookup"><span data-stu-id="275fb-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="275fb-107">**Fehlercode:** 422</span><span class="sxs-lookup"><span data-stu-id="275fb-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="275fb-108">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365-Berichterstellungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="275fb-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="275fb-109">**Ursache:** Bevor Sie eine Verbindung mit der App herstellen können, müssen Sie die Daten aus dem Microsoft 365 Admin Center abonnieren.</span><span class="sxs-lookup"><span data-stu-id="275fb-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="275fb-110">Wenn dieser Schritt nicht zuerst durchgeführt wird, können Sie keine Verbindung mit der Vorlagen-App herstellen, auch wenn Sie Ihre Microsoft 365-Mandanten-ID bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="275fb-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="275fb-111">**So beheben Sie diesen Fehler:** Um die Daten zu abonnieren, wechseln Sie zum Admin Center Berichte Nutzung, und suchen Sie die Microsoft 365-Kachel für die Verwendungsanalyse \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> auf der Hauptdashboardseite.</span><span class="sxs-lookup"><span data-stu-id="275fb-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="275fb-112">Wählen Sie **die Schaltfläche Erste**  Schritte aus, und aktivieren Sie dann im Bereich Berichte, der geöffnet wird, die Einstellung Daten für **Microsoft 365-Nutzungsanalyse** für Power BI verfügbar machen und **speichern**.</span><span class="sxs-lookup"><span data-stu-id="275fb-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="275fb-113">Ihre Daten werden verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="275fb-113">We are processing your data</span></span>

 <span data-ttu-id="275fb-114">**Hier sehen Sie diese Meldung:** In der **Kachel Microsoft 365 Usage Analytics** im Verwendungsdashboard im Microsoft 365 Admin Center. </span><span class="sxs-lookup"><span data-stu-id="275fb-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="275fb-115">**Ursache:** Wenn Sie [sich für das](enable-usage-analytics.md) Anzeigen von Daten in der Vorlagen-App aus dem Microsoft 365 Admin Center entscheiden, beginnt das Microsoft 365-System mit der Generierung von verlaufshistorischen Nutzungsdaten für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="275fb-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="275fb-116">Je nach Größe des Mandanten kann die Zeit für das Ausführen dieses Schritts zwischen 2 und 48 Stunden betragen.</span><span class="sxs-lookup"><span data-stu-id="275fb-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="275fb-117">**So beheben Sie dies:** Haben Sie einfach Geduld, aber wenn  die Nachricht nicht in Ihre Daten nach 3 Tagen geändert wird, wenden Sie sich [an Den Microsoft 365 Business-Support.](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="275fb-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="275fb-118">Ihre Anfrage kann derzeit nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="275fb-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="275fb-119">Die Daten werden immer noch für Ihre Organisation vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="275fb-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="275fb-120">**Fehlercode:** 423</span><span class="sxs-lookup"><span data-stu-id="275fb-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="275fb-121">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365-Berichterstellungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="275fb-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="275fb-122">**Ursache:** Wenn Sie [sich für das](enable-usage-analytics.md) Anzeigen von Daten in der Vorlagen-App aus dem Admin Center entscheiden, beginnt das Microsoft 365-System mit der Generierung von verlaufshistorischen Nutzungsdaten für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="275fb-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="275fb-123">Je nach Größe Ihres Mandanten kann dieser Schritt zwischen zwei Stunden und 48 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="275fb-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="275fb-124">**So beheben Sie dies:** Haben Sie einfach Geduld, aber wenn  sich die Nachricht nicht in Ihre Daten ändert, können Sie sich auch 3 Tage nach der Initiierung an [den Microsoft 365 Business-Support wenden.](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="275fb-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="275fb-125">Die von Ihnen angegebene Mandanten-ID weist nicht das richtige Format auf.</span><span class="sxs-lookup"><span data-stu-id="275fb-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="275fb-126">**Fehlercode:** 400</span><span class="sxs-lookup"><span data-stu-id="275fb-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="275fb-127">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365-Berichterstellungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="275fb-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="275fb-128">**Ursache:** Die Mandanten-ID ist eine Guid und muss im Format xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx vorliegen.</span><span class="sxs-lookup"><span data-stu-id="275fb-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="275fb-129">Wenn Sie eine andere Zeichenfolge in das Eingabefeld des Mandanten eingeben, wird dieser Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="275fb-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="275fb-130">**So beheben Sie diesen Fehler:** Wechseln Sie zum Admin Center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage,</a> und suchen Sie die Kachel Microsoft 365-Verwendungsanalyse auf der Hauptdashboardseite.</span><span class="sxs-lookup"><span data-stu-id="275fb-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="275fb-131">Die Mandanten-ID wird auf der Kachel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="275fb-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="275fb-132">Sie können es hier kopieren und in das Dialogfeld einfügen, um eine Verbindung mit der Vorlagen-App zu herstellen.</span><span class="sxs-lookup"><span data-stu-id="275fb-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="275fb-133">Die von Ihnen angegebene Mandanten-ID wird von unserem System nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="275fb-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="275fb-134">**Fehlercode:** 404</span><span class="sxs-lookup"><span data-stu-id="275fb-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="275fb-135">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365-Berichterstellungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="275fb-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="275fb-136">**Ursache:** Die von Ihnen bereitgestellte Mandanten-ID ist ungültig oder nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="275fb-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="275fb-137">**So beheben Sie diesen Fehler:** Wechseln Sie zum Admin Center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage,</a> und suchen Sie die Kachel Microsoft 365-Verwendungsanalyse auf der Hauptdashboardseite.</span><span class="sxs-lookup"><span data-stu-id="275fb-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="275fb-138">Die Mandanten-ID wird auf der Kachel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="275fb-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="275fb-139">Sie können es hier kopieren und in das Dialogfeld einfügen, um eine Verbindung mit der Vorlagen-App zu herstellen.</span><span class="sxs-lookup"><span data-stu-id="275fb-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="275fb-140">Geben Sie Ihre Anmeldeinformationen erneut ein, um sich wieder bei Power BI anzumelden.</span><span class="sxs-lookup"><span data-stu-id="275fb-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="275fb-141">Fehlercode: 302</span><span class="sxs-lookup"><span data-stu-id="275fb-141">Error Code: 302</span></span>
  
 <span data-ttu-id="275fb-142">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365-Berichterstellungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="275fb-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="275fb-143">**Ursache:** Der Autorisierungscode ist fehlgeschlagen, und Sie müssen möglicherweise Ihre Anmeldeinformationen erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="275fb-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="275fb-144">**Fehlerbehebung:** Melden Sie sich bei Power BI ab und anschließend wieder an.</span><span class="sxs-lookup"><span data-stu-id="275fb-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="275fb-145">Sie verfügen nicht über die richtige Autorisierung für den Zugriff auf diese Daten.</span><span class="sxs-lookup"><span data-stu-id="275fb-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="275fb-146">Um von diesem Dienst aus auf die Daten zugreifen zu können, müssen Sie entweder ein globaler Administrator oder einer der Produktadministratoren sein.</span><span class="sxs-lookup"><span data-stu-id="275fb-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="275fb-147">**Fehlercode:** 403</span><span class="sxs-lookup"><span data-stu-id="275fb-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="275fb-148">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365-Berichterstellungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="275fb-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="275fb-149">**Ursache:** Der Autorisierungscode ist fehlgeschlagen, da der Benutzer, der versucht hat, eine Verbindung mit der Vorlagen-App zu herstellen, nicht über die richtige Autorisierungsebene für den Zugriff auf diese Daten verfügt.</span><span class="sxs-lookup"><span data-stu-id="275fb-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="275fb-150">**So beheben Sie diesen Fehler:** Geben Sie die Anmeldeinformationen eines Benutzers an, der entweder globaler **Administrator,** Exchange-Administrator, **Skype for Business-Administrator,** **SharePoint-Administrator,** **globaler** Leser oder **Berichtsleser** ist, um eine Verbindung mit der Vorlagen-App herzustellen. </span><span class="sxs-lookup"><span data-stu-id="275fb-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="275fb-151">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="275fb-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="275fb-152">Fehler beim Aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="275fb-152">Refresh failed</span></span>

 <span data-ttu-id="275fb-153">**Anzeigeort dieser Meldung:** E-Mail von Power BI oder Fehlerstatus im Aktualisierungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="275fb-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="275fb-154">**Ursache:** Manchmal werden die Anmeldeinformationen des Benutzers, der mit der Vorlagen-App verbunden ist, zurückgesetzt und in den Verbindungseinstellungen der Vorlagen-App nicht aktualisiert, sodass dem Benutzer Aktualisierungsfehler angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="275fb-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="275fb-155">**So beheben Sie diesen Fehler:** Suchen Sie in Power BI nach dem Dataset, das der  Microsoft 365 Usage Analytics-Vorlagen-App entspricht, wählen Sie Aktualisierung planen aus, und geben Sie Ihre Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="275fb-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="275fb-156">Wenn dies nicht funktioniert, löschen Sie den Cache, und erstellen Sie die Vorlagen-App neu.</span><span class="sxs-lookup"><span data-stu-id="275fb-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
