---
title: Problembehandlung bei Microsoft 365-Verwendungsanalysen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
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
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Hier erfahren Sie, wie Sie Probleme mit der Vorlagen-App für Microsoft 365 Usage Analytics beheben können.
ms.openlocfilehash: a9da79a6d7760f7876de7a6321554545d411f6be
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42244180"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="f20c2-103">Problembehandlung bei Microsoft 365-Verwendungsanalysen</span><span class="sxs-lookup"><span data-stu-id="f20c2-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="f20c2-104">Untersuchen Sie die folgende Liste von Fehlermeldungen, um Hilfe zu den am häufigsten auftretenden Problemen mit Microsoft 365 Usage Analytics zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f20c2-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="f20c2-105">Ihre Anfrage kann nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f20c2-105">We are unable to process your request.</span></span> <span data-ttu-id="f20c2-106">Sie müssen zuerst diese Daten im Microsoft 365 Admin Center abonnieren.</span><span class="sxs-lookup"><span data-stu-id="f20c2-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="f20c2-107">**Fehlercode:** 422</span><span class="sxs-lookup"><span data-stu-id="f20c2-107">**Error Code :** 422</span></span> 
  
 <span data-ttu-id="f20c2-108">**Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f20c2-109">**Ursache:** Bevor Sie eine Verbindung mit der App herstellen können, müssen Sie die Daten im Microsoft 365 Admin Center abonnieren.</span><span class="sxs-lookup"><span data-stu-id="f20c2-109">**Cause:** Before you can connect to the app you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="f20c2-110">Wenn dieser Schritt nicht zuerst ausgeführt wird, können Sie keine Verbindung mit der Vorlagen-App herstellen, auch wenn Sie Ihre Microsoft 365-Mandanten-ID angeben.</span><span class="sxs-lookup"><span data-stu-id="f20c2-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant id.</span></span> 
  
 <span data-ttu-id="f20c2-111">**So beheben Sie diesen Fehler:** Wenn Sie die Daten abonnieren möchten, wechseln Sie zur Verwaltungs \> Konsole **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a> , und suchen Sie die Kachel Microsoft 365 Usage Analytics auf der Hauptseite des Dashboards.</span><span class="sxs-lookup"><span data-stu-id="f20c2-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f20c2-112">Wählen Sie die Schaltfläche **Erste Schritte** aus, und aktivieren Sie dann im Bereich **Berichte** , der geöffnet wird, die Option **Daten für Microsoft 365-Verwendungsanalyse für Power BI verfügbar machen** und **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f20c2-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="f20c2-113">Ihre Daten werden verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f20c2-113">We are processing your data</span></span>

 <span data-ttu-id="f20c2-114">**Die folgende Meldung wird angezeigt:** In der Kachel **Microsoft 365 Usage Analytics** im **Nutzungs** Dashboard im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="f20c2-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="f20c2-115">**Ursache:** Wenn Sie [sich für das Anzeigen von Daten in der Vorlagen-App](enable-usage-analytics.md) aus dem Microsoft 365 Admin Center entscheiden, beginnt das Microsoft 365-System mit der Generierung historischer Verwendungsdaten für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="f20c2-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="f20c2-116">Je nach Größe des Mandanten kann die Zeit für das Ausführen dieses Schritts zwischen 2 und 48 Stunden betragen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="f20c2-117">**So beheben Sie dieses Problem:** Seien Sie nur geduldig, aber wenn sich die Nachricht nicht ändert, wenn Ihre Daten nach 3 Tagen **verfügbar sind** , [wenden Sie sich an Microsoft 365 for Business Support](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="f20c2-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="f20c2-118">Ihre Anfrage kann derzeit nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f20c2-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="f20c2-119">Die Daten werden immer noch für Ihre Organisation vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="f20c2-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="f20c2-120">**Fehlercode:** 423</span><span class="sxs-lookup"><span data-stu-id="f20c2-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="f20c2-121">**Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-121">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f20c2-122">**Ursache:** Wenn Sie [sich für das Anzeigen von Daten in der Vorlagen-App](enable-usage-analytics.md) aus dem Admin Center entscheiden, beginnt das Microsoft 365-System mit der Generierung historischer Verwendungsdaten für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="f20c2-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="f20c2-123">Je nach Größe des Mandanten kann die Zeit für das Ausführen dieses Schritts zwischen 2 und 48 Stunden betragen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-123">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="f20c2-124">**So beheben Sie dieses Problem:** Seien Sie nur geduldig, aber wenn sich die Nachricht nicht ändert, **sind Ihre Daten** sogar 3 Tage seit der Initiierung nicht mehr verfügbar, [wenden Sie sich an den Support von Microsoft 365 for Business](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="f20c2-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="f20c2-125">Die von Ihnen angegebene Mandanten-ID weist nicht das richtige Format auf.</span><span class="sxs-lookup"><span data-stu-id="f20c2-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="f20c2-126">**Fehlercode:** 400</span><span class="sxs-lookup"><span data-stu-id="f20c2-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="f20c2-127">**Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-127">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f20c2-p107">**Ursache:** Die Mandanten-ID ist eine GUID und muss das Format xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx aufweisen. Wenn Sie eine andere Zeichenfolge in das Eingabefeld für den Mandanten eingeben, wird diese Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f20c2-p107">**Cause:** The tenant id is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. If you enter any other string in the tenant input box you will get this error.</span></span> 
  
 <span data-ttu-id="f20c2-130">**So beheben Sie diesen Fehler:** Wechseln Sie zur Admin Center \> - **Berichts** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a> , und suchen Sie die Kachel Microsoft 365 Usage Analytics auf der Hauptseite des Dashboards.</span><span class="sxs-lookup"><span data-stu-id="f20c2-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f20c2-131">Die Mandanten-ID ist auf der Kachel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f20c2-131">The tenant id is listed on the tile.</span></span> <span data-ttu-id="f20c2-132">Sie können es von hier kopieren und in das Dialogfeld zum Herstellen einer Verbindung mit der Vorlagen-App einfügen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="f20c2-133">Die von Ihnen angegebene Mandanten-ID wird von unserem System nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="f20c2-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="f20c2-134">**Fehlercode:** 404</span><span class="sxs-lookup"><span data-stu-id="f20c2-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="f20c2-135">**Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f20c2-136">**Ursache:** Die von Ihnen angegebene Mandanten-ID ist nicht gültig oder nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f20c2-136">**Cause:** The tenant id you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="f20c2-137">**So beheben Sie diesen Fehler:** Wechseln Sie zur Admin Center \> - **Berichts** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a> , und suchen Sie die Kachel Microsoft 365 Usage Analytics auf der Hauptseite des Dashboards.</span><span class="sxs-lookup"><span data-stu-id="f20c2-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f20c2-138">Die Mandanten-ID ist auf der Kachel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f20c2-138">The tenant id is listed on the tile.</span></span> <span data-ttu-id="f20c2-139">Sie können es von hier kopieren und in das Dialogfeld zum Herstellen einer Verbindung mit der Vorlagen-App einfügen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="f20c2-140">Geben Sie Ihre Anmeldeinformationen erneut ein, um sich wieder bei Power BI anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f20c2-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="f20c2-141">Fehlercode: 302</span><span class="sxs-lookup"><span data-stu-id="f20c2-141">Error Code: 302</span></span>
  
 <span data-ttu-id="f20c2-142">**Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f20c2-143">**Ursache:** Der Autorisierungscode ist fehlgeschlagen, und Sie müssen möglicherweise Ihre Anmeldeinformationen erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="f20c2-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="f20c2-144">**Fehlerbehebung:** Melden Sie sich bei Power BI ab und anschließend wieder an.</span><span class="sxs-lookup"><span data-stu-id="f20c2-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="f20c2-145">Sie verfügen nicht über die richtige Autorisierung für den Zugriff auf diese Daten.</span><span class="sxs-lookup"><span data-stu-id="f20c2-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="f20c2-146">Um von diesem Dienst aus auf die Daten zugreifen zu können, müssen Sie entweder ein globaler Administrator oder einer der Produktadministratoren sein.</span><span class="sxs-lookup"><span data-stu-id="f20c2-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="f20c2-147">**Fehlercode:** 403</span><span class="sxs-lookup"><span data-stu-id="f20c2-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="f20c2-148">**Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f20c2-149">**Ursache:** Der Autorisierungscode ist fehlgeschlagen, da der Benutzer, der versucht hat, eine Verbindung mit der Vorlagen-App herzustellen, nicht über die richtige Berechtigungsstufe für den Zugriff auf diese Daten verfügt.</span><span class="sxs-lookup"><span data-stu-id="f20c2-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="f20c2-150">**So beheben Sie diesen Fehler:** Geben Sie die Anmeldeinformationen eines Benutzers an, der entweder **globaler Administrator**, **Exchange-Administrator**, **Skype for Business Administrator**, **SharePoint-Administrator**, **globaler Leser** oder **berichtsleser** ist, um eine Verbindung mit der Vorlagen-App herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f20c2-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="f20c2-151">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f20c2-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="f20c2-152">Fehler beim Aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f20c2-152">Refresh failed</span></span>

 <span data-ttu-id="f20c2-153">**Anzeigeort dieser Meldung:** E-Mail von Power BI oder Fehlerstatus im Aktualisierungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="f20c2-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="f20c2-154">**Ursache:** Manchmal werden die Anmeldeinformationen des Benutzers, der mit der Vorlagen-App verbunden ist, zurückgesetzt und in den Verbindungseinstellungen der Vorlagen-APP nicht aktualisiert, wodurch der Benutzer Fehler bei der Aktualisierung von Fehlern sehen kann.</span><span class="sxs-lookup"><span data-stu-id="f20c2-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="f20c2-155">**So beheben Sie diesen Fehler:** Suchen Sie in Power BI nach dem DataSet, das der Microsoft 365 Usage Analytics-Vorlagen-App entspricht, wählen Sie **Aktualisierung planen** aus, und geben Sie Ihre Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="f20c2-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="f20c2-156">Wenn dies nicht funktioniert, löschen Sie den Cache, und erstellen Sie die Vorlagen-APP neu.</span><span class="sxs-lookup"><span data-stu-id="f20c2-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
