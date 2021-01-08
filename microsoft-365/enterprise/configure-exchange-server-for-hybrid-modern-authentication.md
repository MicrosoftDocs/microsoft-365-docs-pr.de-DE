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
description: Erfahren Sie, wie Sie eine Exchange Server A0 für die Verwendung der hybriden modernen Authentifizierung (Hybrid Modern Authentication, HMA) konfigurieren und ihnen eine sicherere Benutzerauthentifizierung und Autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780284"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="e971b-103">Lokale Konfiguration von Exchange Server derart, dass die moderne Hybridauthentifizierung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e971b-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="e971b-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e971b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e971b-105">Die hybride moderne Authentifizierung (Hybrid Modern Authentication, HMA) ist eine Methode der Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und Autorisierung bietet und für lokale Hybridbereitstellungen von Exchange Server verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e971b-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="e971b-106">FYI</span><span class="sxs-lookup"><span data-stu-id="e971b-106">FYI</span></span>

<span data-ttu-id="e971b-107">Bevor wir beginnen, rufe ich auf:</span><span class="sxs-lookup"><span data-stu-id="e971b-107">Before we begin, I call:</span></span>

- <span data-ttu-id="e971b-108">HMA für moderne \> Hybridauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="e971b-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="e971b-109">Exchange (lokales \> EXCH)</span><span class="sxs-lookup"><span data-stu-id="e971b-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="e971b-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="e971b-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="e971b-111">Wenn eine Grafik in diesem Artikel außerdem über ein Objekt verfügt, das abgeblendet oder abgeblendet ist, bedeutet dies, dass das in Grau dargestellte Element nicht in der *HMA-spezifischen* Konfiguration enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e971b-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="e971b-112">Aktivieren der modernen Hybridauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="e971b-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="e971b-113">Das Aktivieren von HMA bedeutet:</span><span class="sxs-lookup"><span data-stu-id="e971b-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="e971b-114">Stellen Sie sicher, dass Sie die Vorqs erfüllen, bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="e971b-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="e971b-115">Da viele **Voraussetzungen** für Skype for Business und Exchange gelten, bietet die moderne Hybridauthentifizierung eine Übersicht und Voraussetzungen für die Verwendung mit lokalen Skype for Business- und [Exchange-Servern.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e971b-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="e971b-116">Gehen Sie dazu vor, bevor Sie mit den Schritten in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="e971b-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="e971b-117">Hinzufügen von lokalen Webdienst-URLs als **Dienstprinzipalnamen (SERVICE Principal Names, SPNs)** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e971b-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="e971b-118">Sicherstellen, dass alle virtuellen Verzeichnisse für HMA aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="e971b-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="e971b-119">Suchen nach dem Objekt "EvoSTS Auth Server"</span><span class="sxs-lookup"><span data-stu-id="e971b-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="e971b-120">Aktivieren von HMA in EXCH.</span><span class="sxs-lookup"><span data-stu-id="e971b-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="e971b-121">**Hinweis** Unterstützt Ihre Version von Office MA?</span><span class="sxs-lookup"><span data-stu-id="e971b-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="e971b-122">Erfahren [Sie, wie die moderne Authentifizierung für Office 2013- und Office 2016-Client-Apps funktioniert.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="e971b-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="e971b-123">Stellen Sie sicher, dass alle Voraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="e971b-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="e971b-124">Da viele Voraussetzungen sowohl für Skype for Business als auch für Exchange gelten, lesen Sie die Übersicht über die moderne Hybridauthentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business- und [Exchange-Servern.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e971b-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="e971b-125">Gehen Sie  *dazu vor,*  bevor Sie mit den Schritten in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="e971b-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="e971b-126">Hinzufügen von lokalen Webdienst-URLs als SPNs in Azure AD</span><span class="sxs-lookup"><span data-stu-id="e971b-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="e971b-127">Führen Sie die Befehle aus, die Ihre lokalen Webdienst-URLs als Azure AD-SPNs zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e971b-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="e971b-128">SPNs werden von Clientcomputern und Geräten während der Authentifizierung und Autorisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e971b-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="e971b-129">Alle URLs, die verwendet werden können, um eine Verbindung von einer lokalen mit Azure Active Directory (Azure AD) herzustellen, müssen in Azure AD registriert sein (dies umfasst sowohl interne als auch externe Namespaces).</span><span class="sxs-lookup"><span data-stu-id="e971b-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="e971b-130">Erfassen Sie zunächst alle URLs, die Sie in AAD hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="e971b-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="e971b-131">Führen Sie die folgenden Befehle lokal aus:</span><span class="sxs-lookup"><span data-stu-id="e971b-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="e971b-132">Stellen Sie sicher, dass die URLs, mit der clients eine Verbindung herstellen können, in AAD als NAMEN des HTTPS-Dienstprinzipal aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e971b-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="e971b-133">Stellen Sie zunächst mit den folgenden Anweisungen eine Verbindung mit AAD [herzustellen.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="e971b-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="e971b-134">**Hinweis** Sie müssen die Option _"Connect-MsolService"_ auf dieser Seite verwenden, um den folgenden Befehl verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="e971b-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="e971b-135">Geben Sie für Ihre Exchange-bezogenen URLs den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e971b-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="e971b-136">Notieren Sie sich die Ausgabe dieses Befehls (und screenshot zum späteren Vergleich), der eine https://  *autodiscover.yourdomain.com-*  und https://  *mail.yourdomain.com-URL* enthalten sollte, aber hauptsächlich aus SPNs besteht, die mit 000000002-0000-0ff1-ce00-00000000000 beginnen.</span><span class="sxs-lookup"><span data-stu-id="e971b-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="e971b-137">Wenn keine https:// aus Ihrer lokalen Website vorhanden sind, müssen wir diese bestimmten Datensätze zu dieser Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e971b-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="e971b-138">Wenn Ihre internen und externen MAPI/HTTP-, EWS-, ActiveSync-, OAB- und AutoErmittlungseinträge in dieser Liste nicht angezeigt werden, müssen Sie sie mithilfe des folgenden Befehls hinzufügen (die Beispiel-URLs sind ' und ' ', aber Sie würden die Beispiel-URLs durch Ihre eigenen `mail.corp.contoso.com` `owa.contoso.com` ersetzen): </span><span class="sxs-lookup"><span data-stu-id="e971b-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="e971b-139">Überprüfen Sie, ob Ihre neuen Datensätze hinzugefügt wurden, indem Sie Get-MsolServicePrincipal aus Schritt 2 erneut ausführen und die Ausgabe überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e971b-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="e971b-140">Vergleichen Sie die Liste/den Screenshot von vorn mit der neuen Liste der SPNs.</span><span class="sxs-lookup"><span data-stu-id="e971b-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="e971b-141">Sie können auch einen Screenshot der neuen Liste für Ihre Datensätze erstellen.</span><span class="sxs-lookup"><span data-stu-id="e971b-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="e971b-142">Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e971b-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="e971b-143">In unserem Beispiel enthält die Liste der SPNs jetzt die spezifischen URLs und  `https://mail.corp.contoso.com`  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="e971b-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="e971b-144">Überprüfen, ob virtuelle Verzeichnisse ordnungsgemäß konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="e971b-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="e971b-145">Überprüfen Sie nun, ob OAuth in Exchange für alle virtuellen Verzeichnisse, die Outlook möglicherweise verwendet, ordnungsgemäß aktiviert ist, indem Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="e971b-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="e971b-146">Überprüfen Sie die Ausgabe, um sicherzustellen, dass **OAuth** auf jedem dieser VDirs aktiviert ist, es sieht in etwa wie dies aus (und der Schlüssel, den Sie betrachten sollten, ist "OAuth"):</span><span class="sxs-lookup"><span data-stu-id="e971b-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="e971b-147">Wenn OAuth auf einem Server und einem der vier virtuellen Verzeichnisse fehlt, müssen Sie es mit den entsprechenden Befehlen hinzufügen, bevor Sie fortfahren ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)und [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="e971b-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="e971b-148">Bestätigen, dass das EvoSTS Auth Server -Objekt vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="e971b-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="e971b-149">Kehren Sie für diesen letzten Befehl zur lokalen Exchange-Verwaltungsshell zurück.</span><span class="sxs-lookup"><span data-stu-id="e971b-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="e971b-150">Jetzt können Sie überprüfen, ob Ihre lokale Organisation über einen Eintrag für den evoSTS-Authentifizierungsanbieter verfügt:</span><span class="sxs-lookup"><span data-stu-id="e971b-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="e971b-151">Ihre Ausgabe sollte einen AuthServer mit dem Namen "EvoSts" anzeigen, und der Status "Enabled" sollte "True" sein.</span><span class="sxs-lookup"><span data-stu-id="e971b-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="e971b-152">Wenn dies nicht angezeigt wird, sollten Sie die neueste Version des Assistenten für die Hybridkonfiguration herunterladen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="e971b-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="e971b-153">**Wichtig** Wenn Sie Exchange 2010 in Ihrer Umgebung ausführen, wird der EvoSTS-Authentifizierungsanbieter nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="e971b-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="e971b-154">Aktivieren von HMA</span><span class="sxs-lookup"><span data-stu-id="e971b-154">Enable HMA</span></span>

<span data-ttu-id="e971b-155">Führen Sie den folgenden Befehl in der lokalen Exchange-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="e971b-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="e971b-156">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="e971b-156">Verify</span></span>

<span data-ttu-id="e971b-157">Nachdem Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen Authentifizierungsfluss.</span><span class="sxs-lookup"><span data-stu-id="e971b-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="e971b-158">Beachten Sie, dass durch das Aktivieren von HMA keine erneute Authentifizierung für einen Client ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e971b-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="e971b-159">Die clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span><span class="sxs-lookup"><span data-stu-id="e971b-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="e971b-160">Sie sollten auch die STRG-TASTE gedrückt halten, wenn Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client klicken (auch im Schacht "Windows-Benachrichtigungen") und auf "Verbindungsstatus" klicken.</span><span class="sxs-lookup"><span data-stu-id="e971b-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="e971b-161">Suchen Sie nach der SMTP-Adresse des Clients im Vergleich zum "Authn"-Typ "Bearer", der das in OAuth verwendete \* Bearertoken darstellt.</span><span class="sxs-lookup"><span data-stu-id="e971b-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="e971b-162">**Hinweis** Müssen Sie Skype for Business mit HMA konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="e971b-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="e971b-163">Sie benötigen zwei Artikel: einen Artikel, in dem unterstützte [Topologien](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)aufgeführt sind, und einen, in dem die Konfiguration [veranschaulicht wird.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="e971b-163">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="e971b-164">Verwenden der modernen Hybridauthentifizierung mit Outlook für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="e971b-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="e971b-165">Wenn Sie ein lokales Kundenkonto sind, das den Exchange Server auf TCP 443 verwendet, umgehen Sie die Datenverkehrsverarbeitung für die folgenden IP-Bereiche:</span><span class="sxs-lookup"><span data-stu-id="e971b-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="e971b-166">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e971b-166">Related topics</span></span>

[<span data-ttu-id="e971b-167">Konfigurationsanforderungen für moderne Authentifizierung für den Übergang von Office 365 dedicated/ITAR zu vNext</span><span class="sxs-lookup"><span data-stu-id="e971b-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
