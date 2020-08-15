---
title: Lokale Konfiguration von Exchange Server derart, dass die moderne Hybridauthentifizierung verwendet wird
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Sie eine lokale Exchange Server für die Verwendung der Hybriden modernen Authentifizierung (HMA) konfigurieren und Ihnen eine sicherere Benutzerauthentifizierung und-Autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 291c7c220fb4ee56db2a42409d5b81724de5da32
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690249"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="d2b31-103">Lokale Konfiguration von Exchange Server derart, dass die moderne Hybridauthentifizierung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="d2b31-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="d2b31-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d2b31-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d2b31-105">Bei der Hybriden modernen Authentifizierung (HMA) handelt es sich um eine Methode zur Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und-Autorisierung bietet und für lokale Exchange Server-hybridbereitstellungen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d2b31-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>
  
## <a name="fyi"></a><span data-ttu-id="d2b31-106">FYI</span><span class="sxs-lookup"><span data-stu-id="d2b31-106">FYI</span></span>

<span data-ttu-id="d2b31-107">Bevor wir beginnen, rufe ich Folgendes auf:</span><span class="sxs-lookup"><span data-stu-id="d2b31-107">Before we begin, I call:</span></span>
  
- <span data-ttu-id="d2b31-108">Hybride moderne Authentifizierung \> HMA</span><span class="sxs-lookup"><span data-stu-id="d2b31-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="d2b31-109">Lokaler Exchange-Austausch \></span><span class="sxs-lookup"><span data-stu-id="d2b31-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="d2b31-110">Exchange Online \> Exo</span><span class="sxs-lookup"><span data-stu-id="d2b31-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="d2b31-111">*Wenn eine Grafik in diesem Artikel ein Objekt enthält, das "abgeblendet" oder "abgeblendet" ist, bedeutet das, dass das in Grau dargestellte Element nicht in HMA-spezifischer Konfiguration enthalten ist* .</span><span class="sxs-lookup"><span data-stu-id="d2b31-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration* .</span></span>
  
## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="d2b31-112">Aktivieren der modernen Hybrid Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d2b31-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="d2b31-113">HMA aktivieren bedeutet:</span><span class="sxs-lookup"><span data-stu-id="d2b31-113">Turning HMA on means:</span></span>
  
1. <span data-ttu-id="d2b31-114">Sicherstellen, dass Sie die Voraussetzungen erfüllen, bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="d2b31-115">Da viele **Voraussetzungen** sowohl für Skype for Business als auch für Exchange, die [hybride moderne Authentifizierungs Übersicht und die Voraussetzungen für die Verwendung mit lokalen Skype for Business-und Exchange-Servern](hybrid-modern-auth-overview.md)gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="d2b31-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="d2b31-116">Tun Sie dies, bevor Sie einen der Schritte in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="d2b31-117">Hinzufügen von lokalen Webdienst-URLs als **Dienstprinzipalnamen (Service Principal Names, SPNs)** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d2b31-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="d2b31-118">Sicherstellen, dass alle virtuellen Verzeichnisse für HMA aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="d2b31-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="d2b31-119">Überprüfen des EvoSTS-Authentifizierungs Server Objekts</span><span class="sxs-lookup"><span data-stu-id="d2b31-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="d2b31-120">Aktivieren von HMA in "interaktives".</span><span class="sxs-lookup"><span data-stu-id="d2b31-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="d2b31-121">**Hinweis:** Unterstützt Ihre Office-Version MA?</span><span class="sxs-lookup"><span data-stu-id="d2b31-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="d2b31-122">Erfahren Sie [, wie die moderne Authentifizierung für Office 2013-und Office 2016-Client-apps funktioniert](modern-auth-for-office-2013-and-2016.md).</span><span class="sxs-lookup"><span data-stu-id="d2b31-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>
  
## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="d2b31-123">Stellen Sie sicher, dass alle Voraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="d2b31-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="d2b31-124">Da viele Voraussetzungen sowohl für Skype for Business als auch für Exchange gelten, überprüfen Sie die Übersicht über die [moderne Hybrid Authentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business-und Exchange-Servern](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d2b31-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="d2b31-125">Tun Sie dies,  *bevor*  Sie einen der Schritte in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-125">Do this  *before*  you begin any of the steps in this article.</span></span>
  
## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="d2b31-126">Hinzufügen von lokalen Webdienst-URLs als SPNs in Azure AD</span><span class="sxs-lookup"><span data-stu-id="d2b31-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="d2b31-127">Führen Sie die Befehle aus, die ihre lokalen Webdienst-URLs als Azure AD SPNs zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="d2b31-128">SPNs werden von Clientcomputern und-Geräten während der Authentifizierung und Autorisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d2b31-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="d2b31-129">Alle URLs, die möglicherweise zum Herstellen einer Verbindung zwischen lokalen und Azure-Active Directory (Azure AD) verwendet werden, müssen in Azure AD registriert sein (Dies umfasst sowohl interne als auch externe Namespaces).</span><span class="sxs-lookup"><span data-stu-id="d2b31-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>
  
<span data-ttu-id="d2b31-130">Sammeln Sie zunächst alle URLs, die Sie in Aad hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="d2b31-131">Führen Sie diese Befehle lokal aus:</span><span class="sxs-lookup"><span data-stu-id="d2b31-131">Run these commands on-premises:</span></span>
  
```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```
    
<span data-ttu-id="d2b31-132">Stellen Sie sicher, dass die URLs, mit denen Clients eine Verbindung herstellen können, als HTTPS-Dienstprinzipalnamen in Aad aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d2b31-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>
  
1. <span data-ttu-id="d2b31-133">Stellen Sie zuerst eine Verbindung mit Aad mit [diesen Anweisungen](connect-to-microsoft-365-powershell.md)her.</span><span class="sxs-lookup"><span data-stu-id="d2b31-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

 <span data-ttu-id="d2b31-134">**Hinweis:** Sie müssen die Option _Connect-MsolService_ von dieser Seite verwenden, um den folgenden Befehl verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="d2b31-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="d2b31-135">Geben Sie für Ihre Exchange-bezogenen URLs den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="d2b31-135">For your Exchange related URLs, type the following command:</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
```

<span data-ttu-id="d2b31-136">Notieren Sie sich (und Screenshot für einen späteren Vergleich) die Ausgabe dieses Befehls, die eine https://  *autodiscover.yourdomain.com*  -und https://-  *Mail.yourdomain.com* -URL enthalten sollte, aber meistens aus SPNs besteht, die mit 00000002-0000-0ff1-ce00-000000000000/beginnen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="d2b31-137">Wenn es https://-URLs von Ihrem Lokal gibt, die fehlen, müssen Sie diese spezifischen Einträge zu dieser Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-137">If there are https:// URLs from your on-premises that are missing we will need to add those specific records to this list.</span></span>
  
3. <span data-ttu-id="d2b31-138">Wenn Ihre internen und externen MAPI/http-, EWS-, ActiveSync-, OAB-und autodiscover-Datensätze in dieser Liste nicht angezeigt werden, müssen Sie Sie mithilfe des folgenden Befehls hinzufügen (die Beispiel-URLs sind " `mail.corp.contoso.com` und" `owa.contoso.com` , aber Sie **ersetzen die Beispiel-URLs durch eigene** ):</span><span class="sxs-lookup"><span data-stu-id="d2b31-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own** ):</span></span> <br/>
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
$x.ServicePrincipalnames.Add("https://owa.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. <span data-ttu-id="d2b31-139">Stellen Sie sicher, dass Ihre neuen Datensätze hinzugefügt wurden, indem Sie den Befehl Get-MsolServicePrincipal aus Schritt 2 erneut ausführen und die Ausgabe durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="d2b31-140">Vergleichen Sie die Liste/Screenshot von vor mit der neuen Liste von SPNs (Sie können auch die neue Liste für Ihre Datensätze Screenshot).</span><span class="sxs-lookup"><span data-stu-id="d2b31-140">Compare the list / screenshot from before to the new list of SPNs (you may also screenshot the new list for your records).</span></span> <span data-ttu-id="d2b31-141">Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2b31-141">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="d2b31-142">In unserem Beispiel enthält die Liste der SPNs nun die spezifischen URLs  `https://mail.corp.contoso.com`  und  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="d2b31-142">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span> 
  
## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="d2b31-143">Überprüfen der ordnungsgemäßen Konfiguration virtueller Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="d2b31-143">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="d2b31-144">Überprüfen Sie nun, ob OAuth in Exchange in allen virtuellen Verzeichnissen, die Outlook möglicherweise verwendet, ordnungsgemäß aktiviert ist, indem Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="d2b31-144">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth* 
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="d2b31-145">Überprüfen Sie die Ausgabe, um sicherzustellen, dass **OAuth** auf jedem dieser VDirs aktiviert ist, es sieht in etwa wie folgt aus (und der wichtigste Aspekt ist "OAuth"):</span><span class="sxs-lookup"><span data-stu-id="d2b31-145">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```
  
<span data-ttu-id="d2b31-146">Wenn OAuth auf einem beliebigen Server und einem der vier virtuellen Verzeichnisse fehlt, müssen Sie es mithilfe der entsprechenden Befehle hinzufügen, bevor Sie fortfahren ([festlegen-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps), [festlegen-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps), [setOABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps)und [AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps)).</span><span class="sxs-lookup"><span data-stu-id="d2b31-146">If OAuth is missing from any server and any of the four virtual directories then you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps)).</span></span>
  
## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="d2b31-147">Bestätigen, dass das EvoSTS-Authentifizierungs Server Objekt vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="d2b31-147">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="d2b31-148">Kehren Sie zu dem lokalen Exchange-Verwaltungsshell für diesen letzten Befehl zurück.</span><span class="sxs-lookup"><span data-stu-id="d2b31-148">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="d2b31-149">Jetzt können Sie überprüfen, ob Ihr lokal über einen Eintrag für den evoSTS-Authentifizierungsanbieter verfügt:</span><span class="sxs-lookup"><span data-stu-id="d2b31-149">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>
  
```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="d2b31-150">Ihre Ausgabe sollte eine AuthServer des Namens EvoSts und der Status "Enabled" sollte true aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-150">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="d2b31-151">Wenn dies nicht angezeigt wird, sollten Sie die neueste Version des Assistenten für die Hybrid Konfiguration herunterladen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-151">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>
  
 <span data-ttu-id="d2b31-152">**Wichtiger Hinweis** Wenn Sie Exchange 2010 in Ihrer Umgebung durchführen, wird der EvoSTS-Authentifizierungsanbieter nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="d2b31-152">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span> 
  
## <a name="enable-hma"></a><span data-ttu-id="d2b31-153">HMA aktivieren</span><span class="sxs-lookup"><span data-stu-id="d2b31-153">Enable HMA</span></span>

<span data-ttu-id="d2b31-154">Führen Sie den folgenden Befehl in der lokalen Exchange-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="d2b31-154">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true  
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="d2b31-155">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="d2b31-155">Verify</span></span>

<span data-ttu-id="d2b31-156">Nachdem Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen auth-Fluss.</span><span class="sxs-lookup"><span data-stu-id="d2b31-156">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="d2b31-157">Beachten Sie, dass durch das Aktivieren von HMA keine erneute Authentifizierung für einen beliebigen Client ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="d2b31-157">Note that just turning on HMA won't trigger a re-authentication for any client.</span></span> <span data-ttu-id="d2b31-158">Die Clients authentifizieren sich erneut basierend auf der Lebensdauer der Authentifizierungstoken und/oder certs, die Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="d2b31-158">The clients re-authenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="d2b31-159">Sie sollten auch die STRG-Taste gleichzeitig gedrückt halten, indem Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client (auch im Windows-Benachrichtigungs Fach) klicken und auf "Verbindungs Status" klicken.</span><span class="sxs-lookup"><span data-stu-id="d2b31-159">You should also hold down the CTRL key at the same time you right click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="d2b31-160">Suchen Sie die SMTP-Adresse des Clients anhand eines "authn"-Typs von "Bearer \* ", der das in OAuth verwendete Bearer-Token darstellt.</span><span class="sxs-lookup"><span data-stu-id="d2b31-160">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
 <span data-ttu-id="d2b31-161">**Hinweis:** Sie müssen Skype for Business mit HMA konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="d2b31-161">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="d2b31-162">Sie benötigen zwei Artikel: eine, die [Unterstützte Topologien](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)auflistet, und eine, die zeigt, [wie Sie die Konfiguration durchführen](configure-skype-for-business-for-hybrid-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d2b31-162">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>
 
## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="d2b31-163">Verwenden der modernen Hybridauthentifizierung mit Outlook für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="d2b31-163">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="d2b31-164">Wenn Sie ein lokaler Kunde sind und Exchange Server auf TCP 443 verwenden, können Sie die folgenden IP-Bereiche in der Whitelist lesen:  </span><span class="sxs-lookup"><span data-stu-id="d2b31-164">If you are an on-premises customer using Exchange server on TCP 443, please whitelist the following IP ranges:  </span></span><BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR>

## <a name="related-topics"></a><span data-ttu-id="d2b31-165">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d2b31-165">Related topics</span></span>

[<span data-ttu-id="d2b31-166">Moderne Authentifizierungs Konfigurationsanforderungen für den Übergang von Office 365 dedizierten/ITAR zu vNext</span><span class="sxs-lookup"><span data-stu-id="d2b31-166">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
