---
title: Problembehandlung Microsoft 365 Verwendungsanalysen
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
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293735"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="004fc-103">Problembehandlung Microsoft 365 Verwendungsanalysen</span><span class="sxs-lookup"><span data-stu-id="004fc-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="004fc-104">Sehen Sie sich die folgende Liste von Fehlermeldungen an, um Hilfe zu den häufigsten Problemen mit Microsoft 365 zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="004fc-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="004fc-105">Ihre Anfrage kann nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="004fc-105">We are unable to process your request.</span></span> <span data-ttu-id="004fc-106">Sie müssen diese Daten zuerst über das Microsoft 365 abonnieren.</span><span class="sxs-lookup"><span data-stu-id="004fc-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="004fc-107">**Fehlercode:** 422</span><span class="sxs-lookup"><span data-stu-id="004fc-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="004fc-108">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="004fc-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="004fc-109">**Ursache:** Bevor Sie eine Verbindung mit der App herstellen können, müssen Sie die Daten aus dem Microsoft 365 abonnieren.</span><span class="sxs-lookup"><span data-stu-id="004fc-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="004fc-110">Wenn dieser Schritt nicht zuerst durchgeführt wird, können Sie keine Verbindung mit der Vorlagen-App herstellen, auch wenn Sie Ihre Microsoft 365 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="004fc-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="004fc-111">**So beheben Sie diesen Fehler:** Um die Daten zu abonnieren, wechseln Sie zum Admin Center Reports Usage, und suchen Sie die Kachel Microsoft 365 Verwendungsanalyse auf der \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Hauptdashboardseite.</span><span class="sxs-lookup"><span data-stu-id="004fc-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="004fc-112">Wählen Sie die **Schaltfläche** Erste  Schritte aus, und  aktivieren Sie dann im bereich Berichte, der geöffnet wird, die Einstellung Daten Microsoft 365 Verwendungsanalyse für Power BI verfügbar machen und **speichern**.</span><span class="sxs-lookup"><span data-stu-id="004fc-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="004fc-113">Ihre Daten werden verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="004fc-113">We are processing your data</span></span>

 <span data-ttu-id="004fc-114">**Hier sehen Sie diese Meldung:** In der **Microsoft 365 der Verwendungsanalyse** im Verwendungsdashboard im Microsoft 365 Admin Center. </span><span class="sxs-lookup"><span data-stu-id="004fc-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="004fc-115">**Ursache:** Wenn Sie [sich für das](enable-usage-analytics.md) Anzeigen von Daten in der Vorlagen-App aus dem Microsoft 365 Admin Center entscheiden, beginnt das Microsoft 365 System, historische Nutzungsdaten für Ihre Organisation zu generieren.</span><span class="sxs-lookup"><span data-stu-id="004fc-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="004fc-116">Je nach Größe des Mandanten kann die Zeit für das Ausführen dieses Schritts zwischen 2 und 48 Stunden betragen.</span><span class="sxs-lookup"><span data-stu-id="004fc-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="004fc-117">**So beheben Sie dies:** Haben Sie einfach Geduld, aber wenn  sich die Nachricht nicht in Ihre Daten nach 3 Tagen ändert, wenden Sie sich an Microsoft 365 [business support](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="004fc-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="004fc-p105">Ihre Anfrage kann derzeit nicht bearbeitet werden. Die Daten werden immer noch für Ihre Organisation vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="004fc-p105">We are unable to process your request at this time. We are still preparing the data for your organization</span></span>

 <span data-ttu-id="004fc-120">**Fehlercode:** 423</span><span class="sxs-lookup"><span data-stu-id="004fc-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="004fc-121">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="004fc-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="004fc-122">**Ursache:** Wenn Sie [sich für das](enable-usage-analytics.md) Anzeigen von Daten in der Vorlagen-App aus dem Admin Center entscheiden, beginnt das Microsoft 365, historische Nutzungsdaten für Ihre Organisation zu generieren.</span><span class="sxs-lookup"><span data-stu-id="004fc-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="004fc-123">Je nach Größe Ihres Mandanten kann dieser Schritt zwischen zwei Stunden und 48 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="004fc-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="004fc-124">**So beheben Sie dies:** Haben Sie einfach Geduld, aber wenn  sich die Nachricht nicht in Ihre Daten ändert, können Sie sich auch 3 Tage nach der Initiierung an Microsoft 365 [Business Support wenden.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="004fc-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="004fc-125">Die von Ihnen angegebene Mandanten-ID weist nicht das richtige Format auf.</span><span class="sxs-lookup"><span data-stu-id="004fc-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="004fc-126">**Fehlercode:** 400</span><span class="sxs-lookup"><span data-stu-id="004fc-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="004fc-127">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="004fc-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="004fc-128">**Ursache:** Die Mandanten-ID ist eine Guid und muss im Format xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx vorliegen.</span><span class="sxs-lookup"><span data-stu-id="004fc-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="004fc-129">Wenn Sie eine andere Zeichenfolge in das Eingabefeld des Mandanten eingeben, wird dieser Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="004fc-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="004fc-130">**So beheben Sie diesen Fehler:** Wechseln Sie zum Admin Center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage,</a> und suchen Sie die Kachel Microsoft 365 Verwendungsanalyse auf der Hauptdashboardseite.</span><span class="sxs-lookup"><span data-stu-id="004fc-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="004fc-131">Die Mandanten-ID wird auf der Kachel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="004fc-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="004fc-132">Sie können es hier kopieren und in das Dialogfeld einfügen, um eine Verbindung mit der Vorlagen-App zu herstellen.</span><span class="sxs-lookup"><span data-stu-id="004fc-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="004fc-133">Die von Ihnen angegebene Mandanten-ID wird von unserem System nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="004fc-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="004fc-134">**Fehlercode:** 404</span><span class="sxs-lookup"><span data-stu-id="004fc-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="004fc-135">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="004fc-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="004fc-136">**Ursache:** Die von Ihnen bereitgestellte Mandanten-ID ist ungültig oder nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="004fc-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="004fc-137">**So beheben Sie diesen Fehler:** Wechseln Sie zum Admin Center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage,</a> und suchen Sie die Kachel Microsoft 365 Verwendungsanalyse auf der Hauptdashboardseite.</span><span class="sxs-lookup"><span data-stu-id="004fc-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="004fc-138">Die Mandanten-ID wird auf der Kachel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="004fc-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="004fc-139">Sie können es hier kopieren und in das Dialogfeld einfügen, um eine Verbindung mit der Vorlagen-App zu herstellen.</span><span class="sxs-lookup"><span data-stu-id="004fc-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="004fc-140">Geben Sie Ihre Anmeldeinformationen erneut ein, um sich wieder bei Power BI anzumelden.</span><span class="sxs-lookup"><span data-stu-id="004fc-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="004fc-141">Fehlercode: 302</span><span class="sxs-lookup"><span data-stu-id="004fc-141">Error Code: 302</span></span>
  
 <span data-ttu-id="004fc-142">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="004fc-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="004fc-143">**Ursache:** Der Autorisierungscode ist fehlgeschlagen, und Sie müssen möglicherweise Ihre Anmeldeinformationen erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="004fc-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="004fc-144">**Fehlerbehebung:** Melden Sie sich bei Power BI ab und anschließend wieder an.</span><span class="sxs-lookup"><span data-stu-id="004fc-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="004fc-p110">Sie verfügen nicht über die richtige Autorisierung für den Zugriff auf diese Daten. Um von diesem Dienst aus auf die Daten zugreifen zu können, müssen Sie entweder ein globaler Administrator oder einer der Produktadministratoren sein.</span><span class="sxs-lookup"><span data-stu-id="004fc-p110">You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="004fc-147">**Fehlercode:** 403</span><span class="sxs-lookup"><span data-stu-id="004fc-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="004fc-148">**Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="004fc-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="004fc-149">**Ursache:** Der Autorisierungscode ist fehlgeschlagen, da der Benutzer, der versucht hat, eine Verbindung mit der Vorlagen-App zu herstellen, nicht über die richtige Autorisierungsebene für den Zugriff auf diese Daten verfügt.</span><span class="sxs-lookup"><span data-stu-id="004fc-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="004fc-150">**So beheben Sie diesen Fehler:** Geben Sie die Anmeldeinformationen eines Benutzers an, der entweder ein globaler Administrator **,** **Exchange-Administrator,** **Skype for Business-Administrator,** **SharePoint-Administrator,** globaler Leser oder **Berichtsleser** ist, um eine Verbindung mit der Vorlagen-App herzustellen. </span><span class="sxs-lookup"><span data-stu-id="004fc-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="004fc-151">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="004fc-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="004fc-152">Fehler beim Aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="004fc-152">Refresh failed</span></span>

 <span data-ttu-id="004fc-153">**Anzeigeort dieser Meldung:** E-Mail von Power BI oder Fehlerstatus im Aktualisierungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="004fc-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="004fc-154">**Ursache:** Manchmal werden die Anmeldeinformationen des Benutzers, der mit der Vorlagen-App verbunden ist, zurückgesetzt und in den Verbindungseinstellungen der Vorlagen-App nicht aktualisiert, sodass dem Benutzer Aktualisierungsfehler angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="004fc-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="004fc-155">**So beheben Sie diesen Fehler:** Suchen Power BI dataset entsprechend der Microsoft 365 Usage Analytics-Vorlagen-App, wählen  Sie Aktualisierung planen aus, und geben Sie Ihre Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="004fc-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="004fc-156">Wenn dies nicht funktioniert, löschen Sie den Cache, und erstellen Sie die Vorlagen-App neu.</span><span class="sxs-lookup"><span data-stu-id="004fc-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
