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
description: Erfahren Sie, wie Sie eine Exchange Server für die Verwendung der hybriden modernen Authentifizierung (Hybrid Modern Authentication, HMA) konfigurieren und Ihnen eine sicherere Benutzerauthentifizierung und -autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2ae7a09387b62abc9e8c74f4a38c2fe8750bab19
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244551"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="fba9c-103">Lokale Konfiguration von Exchange Server derart, dass die moderne Hybridauthentifizierung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="fba9c-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="fba9c-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fba9c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fba9c-105">Die hybride moderne Authentifizierung (Hybrid Modern Authentication, HMA) ist eine Methode der Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und -autorisierung bietet und für lokale Exchange server verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fba9c-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="fba9c-106">FYI</span><span class="sxs-lookup"><span data-stu-id="fba9c-106">FYI</span></span>

<span data-ttu-id="fba9c-107">Bevor wir beginnen, rufe ich auf:</span><span class="sxs-lookup"><span data-stu-id="fba9c-107">Before we begin, I call:</span></span>

- <span data-ttu-id="fba9c-108">HMA für moderne \> Hybridauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="fba9c-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="fba9c-109">Exchange lokalen \> EXCH</span><span class="sxs-lookup"><span data-stu-id="fba9c-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="fba9c-110">\>Exchange Online EXO</span><span class="sxs-lookup"><span data-stu-id="fba9c-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="fba9c-111">Wenn eine Grafik in diesem Artikel außerdem über ein Objekt verfügt, das "ausgegraut" oder "abgeblendet" ist, bedeutet dies, dass das in Grau angezeigte Element nicht in der *HMA-spezifischen* Konfiguration enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="fba9c-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="fba9c-112">Aktivieren der modernen Hybridauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="fba9c-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="fba9c-113">Das Aktivieren von HMA bedeutet:</span><span class="sxs-lookup"><span data-stu-id="fba9c-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="fba9c-114">Stellen Sie sicher, dass Sie die Anforderungen erfüllen, bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="fba9c-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="fba9c-115">Da viele **Voraussetzungen** sowohl für Skype for Business als auch für Exchange gemeinsam sind, bietet die Übersicht über die moderne Hybridauthentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business- und [Exchange Servern.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fba9c-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="fba9c-116">Gehen Sie dazu vor, bevor Sie mit den Schritten in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="fba9c-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="fba9c-117">Hinzufügen von lokalen Webdienst-URLs als **Dienstprinzipalnamen (Service Principal Names, SPNs)** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fba9c-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="fba9c-118">Für den Fall, dass SICH EXCH in einer Hybridbereitstellung mit mehreren Mandanten **befindet,** müssen diese lokalen Webdienst-URLs als SPNs in Azure AD aller Mandanten hinzugefügt werden, die sich in hybrider Verbindung mit EXCH befinden.</span><span class="sxs-lookup"><span data-stu-id="fba9c-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="fba9c-119">Sicherstellen, dass alle virtuellen Verzeichnisse für HMA aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="fba9c-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="fba9c-120">Suchen nach dem EvoSTS Auth Server-Objekt</span><span class="sxs-lookup"><span data-stu-id="fba9c-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="fba9c-121">Aktivieren von HMA in EXCH.</span><span class="sxs-lookup"><span data-stu-id="fba9c-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="fba9c-122">Unterstützt Ihre Version von Office MA?</span><span class="sxs-lookup"><span data-stu-id="fba9c-122">Does your version of Office support MA?</span></span> <span data-ttu-id="fba9c-123">Weitere Informationen finden Sie unter Funktionsweise der [modernen Authentifizierung für Office 2013 und Office 2016-Client-Apps](modern-auth-for-office-2013-and-2016.md).</span><span class="sxs-lookup"><span data-stu-id="fba9c-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="fba9c-124">Stellen Sie sicher, dass alle Voraussetzungen erfüllt sind</span><span class="sxs-lookup"><span data-stu-id="fba9c-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="fba9c-125">Da viele Voraussetzungen sowohl für Skype for Business als auch für Exchange üblich sind, überprüfen Sie die Übersicht über die moderne Hybridauthentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business- und [Exchange Servern.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fba9c-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="fba9c-126">Gehen Sie  *dazu vor,*  bevor Sie mit den Schritten in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="fba9c-126">Do this  *before*  you begin any of the steps in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="fba9c-127">Outlook Web App und Exchange Systemsteuerung funktioniert nicht mit moderner Hybridauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fba9c-127">Outlook Web App and Exchange Control Panel does not work with hybrid Modern Authentication.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="fba9c-128">Hinzufügen von lokalen Webdienst-URLs als SPNs in Azure AD</span><span class="sxs-lookup"><span data-stu-id="fba9c-128">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="fba9c-129">Führen Sie die Befehle aus, die Ihre lokalen Webdienst-URLs als Azure AD SPNs zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fba9c-129">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="fba9c-130">SPNs werden von Clientcomputern und Geräten während der Authentifizierung und Autorisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="fba9c-130">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="fba9c-131">Alle URLs, die zum Herstellen einer Verbindung zwischen lokalen und Azure Active Directory (Azure AD) verwendet werden können, müssen in Azure AD registriert sein (dies umfasst sowohl interne als auch externe Namespaces).</span><span class="sxs-lookup"><span data-stu-id="fba9c-131">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="fba9c-132">Sammeln Sie zunächst alle URLs, die Sie in AAD hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="fba9c-132">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="fba9c-133">Führen Sie die folgenden Befehle lokal aus:</span><span class="sxs-lookup"><span data-stu-id="fba9c-133">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

<span data-ttu-id="fba9c-134">Stellen Sie sicher, dass die URLs-Clients, mit der eine Verbindung hergestellt werden kann, als HTTPS-Dienstprinzipalnamen in AAD aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fba9c-134">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="fba9c-135">Falls EXCH mit mehreren Mandanten hybrid ist, sollten diese HTTPS-SPNs im AAD aller Mandanten in Hybrid mit EXCH hinzugefügt werden. </span><span class="sxs-lookup"><span data-stu-id="fba9c-135">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="fba9c-136">Stellen Sie zunächst eine Verbindung mit AAD mit [diesen Anweisungen auf.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="fba9c-136">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="fba9c-137">Sie müssen die Option _Verbinden-MsolService_ auf dieser Seite verwenden, um den folgenden Befehl verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="fba9c-137">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="fba9c-138">Geben Sie für Exchange-bezogene URLs den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="fba9c-138">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="fba9c-139">Notieren Sie sich (und screenshot für einen späteren Vergleich) die Ausgabe dieses Befehls, der eine  *https://-autodiscover.yourdomain.com-*  und  *https://-mail.yourdomain.com-URL* enthalten sollte, aber hauptsächlich aus SPNs besteht, die mit 000000002-0000-0ff1-ce00-00000000000 beginnen.</span><span class="sxs-lookup"><span data-stu-id="fba9c-139">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="fba9c-140">Wenn keine https:// urLs aus Ihrer lokalen Website vorhanden sind, müssen wir diese bestimmten Datensätze dieser Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fba9c-140">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="fba9c-141">Wenn Ihre internen und externen MAPI/HTTP-, EWS-, ActiveSync-, OAB- und AutoErmittlungseinträge in dieser Liste nicht angezeigt werden, müssen Sie sie mithilfe des folgenden Befehls hinzufügen (die Beispiel-URLs sind ' und ' ', Aber Sie würden die Beispiel-URLs durch Ihre eigenen `mail.corp.contoso.com` `owa.contoso.com` ersetzen): </span><span class="sxs-lookup"><span data-stu-id="fba9c-141">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="fba9c-142">Überprüfen Sie, ob Ihre neuen Datensätze hinzugefügt wurden, indem Sie den befehl Get-MsolServicePrincipal Schritt 2 erneut ausführen und die Ausgabe durchschauen.</span><span class="sxs-lookup"><span data-stu-id="fba9c-142">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="fba9c-143">Vergleichen Sie die Liste/den Screenshot von vorher mit der neuen Liste der SPNs.</span><span class="sxs-lookup"><span data-stu-id="fba9c-143">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="fba9c-144">Sie können auch einen Screenshot der neuen Liste für Ihre Datensätze erstellen.</span><span class="sxs-lookup"><span data-stu-id="fba9c-144">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="fba9c-145">Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fba9c-145">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="fba9c-146">In unserem Beispiel enthält die Liste der SPNs nun die spezifischen URLs  `https://mail.corp.contoso.com`  und  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="fba9c-146">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="fba9c-147">Überprüfen, ob virtuelle Verzeichnisse ordnungsgemäß konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="fba9c-147">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="fba9c-148">Überprüfen Sie nun, ob OAuth in Exchange für alle virtuellen Verzeichnisse ordnungsgemäß aktiviert ist, Outlook die folgenden Befehle verwenden können:</span><span class="sxs-lookup"><span data-stu-id="fba9c-148">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="fba9c-149">Überprüfen Sie die Ausgabe, um sicherzustellen, dass **OAuth** für jedes dieser VDirs aktiviert ist. Es sieht so aus (und das Wichtigste, was Sie sehen sollten, ist "OAuth"):</span><span class="sxs-lookup"><span data-stu-id="fba9c-149">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="fba9c-150">Wenn OAuth auf einem Server und einem der vier virtuellen Verzeichnisse fehlt, müssen Sie es mit den entsprechenden Befehlen hinzufügen, bevor Sie fortfahren ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)und [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="fba9c-150">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="fba9c-151">Bestätigen, dass das EvoSTS Auth Server-Objekt vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="fba9c-151">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="fba9c-152">Kehren Sie zum lokalen Exchange Verwaltungsshell für diesen letzten Befehl zurück.</span><span class="sxs-lookup"><span data-stu-id="fba9c-152">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="fba9c-153">Jetzt können Sie überprüfen, ob Ihr lokales Konto über einen Eintrag für den evoSTS-Authentifizierungsanbieter verfügt:</span><span class="sxs-lookup"><span data-stu-id="fba9c-153">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="fba9c-154">Ihre Ausgabe sollte einen AuthServer des Namens "EvoSts" anzeigen, und der Status "Enabled" sollte True sein.</span><span class="sxs-lookup"><span data-stu-id="fba9c-154">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="fba9c-155">Wenn dies nicht angezeigt wird, sollten Sie die neueste Version des Assistenten für die Hybridkonfiguration herunterladen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="fba9c-155">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="fba9c-156">Für den Fall, dass SICH EXCH in einer Hybridbereitstellung mit mehreren Mandanten **befindet,** sollte ihre Ausgabe einen AuthServer des Namens "EvoSts" anzeigen - {GUID} für jeden Mandanten in Hybrid mit EXCH und der Status "Enabled" sollte für alle diese AuthServer-Objekte True sein.</span><span class="sxs-lookup"><span data-stu-id="fba9c-156">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="fba9c-157">**Wichtig** Wenn Sie 2010 Exchange 2010 ausführen, wird der Authentifizierungsanbieter von EvoSTS nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="fba9c-157">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="fba9c-158">Aktivieren von HMA</span><span class="sxs-lookup"><span data-stu-id="fba9c-158">Enable HMA</span></span>

<span data-ttu-id="fba9c-159">Führen Sie den folgenden Befehl in der lokalen Exchange Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="fba9c-159">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="fba9c-160">Wenn die EXCH-Version Exchange 2016 (CU18 oder höher) oder Exchange 2019 (CU7 oder höher) und die Hybridversion mit HCW konfiguriert wurde, die nach September 2020 heruntergeladen wurde, führen Sie den folgenden Befehl in der lokalen Exchange-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="fba9c-160">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="fba9c-161">Für den Fall, dass SICH EXCH in einer Hybridbereitstellung mit mehreren Mandanten **befindet,** sind mehrere AuthServer-Objekte in EXCH vorhanden, deren Domänen jedem Mandanten entsprechend sind.</span><span class="sxs-lookup"><span data-stu-id="fba9c-161">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="fba9c-162">Das **IsDefaultAuthorizationEndpoint-Flag** sollte für jedes dieser AuthServer-Objekte auf true (mithilfe des **IsDefaultAuthorizationEndpoint-Cmdlets)** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fba9c-162">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="fba9c-163">Dieses Flag kann nicht für alle Authserver-Objekte auf true festgelegt werden, und HMA wäre auch dann aktiviert, wenn das **IsDefaultAuthorizationEndpoint-Flag** dieses AuthServer-Objekts auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fba9c-163">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="fba9c-164">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="fba9c-164">Verify</span></span>

<span data-ttu-id="fba9c-165">Sobald Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen Authentifizierungsfluss.</span><span class="sxs-lookup"><span data-stu-id="fba9c-165">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="fba9c-166">Beachten Sie, dass nur das Aktivieren von HMA keine erneute Authentifizierung für einen Client auslöst.</span><span class="sxs-lookup"><span data-stu-id="fba9c-166">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="fba9c-167">Die Clients authentifizieren sich basierend auf der Lebensdauer der Authentifizierungstoken und/oder -zerts, die sie haben.</span><span class="sxs-lookup"><span data-stu-id="fba9c-167">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="fba9c-168">Sie sollten auch die STRG-TASTE gedrückt halten, während Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client klicken (auch im Windows-Benachrichtigungsfach) und auf "Verbindungsstatus" klicken.</span><span class="sxs-lookup"><span data-stu-id="fba9c-168">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="fba9c-169">Suchen Sie nach der SMTP-Adresse des Clients für einen "Authn"-Typ von "Bearer", der das in OAuth verwendete \* Bearertoken darstellt.</span><span class="sxs-lookup"><span data-stu-id="fba9c-169">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="fba9c-170">Müssen Sie Skype for Business HMA konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="fba9c-170">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="fba9c-171">Sie benötigen zwei Artikel: einen Artikel, der unterstützte [Topologien](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)auflistet, und einen Artikel, in dem die Konfiguration [veranschaulicht wird.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="fba9c-171">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="fba9c-172">Verwenden der modernen Hybridauthentifizierung mit Outlook für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="fba9c-172">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="fba9c-173">Wenn Sie ein lokaler Kunde sind, der einen Exchange TCP 443 verwendet, umgehen Sie die Datenverkehrsverarbeitung für die folgenden IP-Adressbereiche:</span><span class="sxs-lookup"><span data-stu-id="fba9c-173">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```
52.125.128.0/20
52.127.96.0/23
```

<span data-ttu-id="fba9c-174">Die Outlook-App für iOS und Android ist die beste Möglichkeit, Microsoft 365 oder Office 365 auf Ihrem mobilen Gerät mithilfe von Microsoft-Dienste zu finden, zu planen und zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="fba9c-174">The Outlook app for iOS and Android is designed as the best way to experience Microsoft 365 or Office 365 on your mobile device by using Microsoft services to help find, plan, and prioritize your daily life and work.</span></span> <span data-ttu-id="fba9c-175">Weitere Informationen finden Sie unter [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="fba9c-175">For more information, please refer to [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fba9c-176">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fba9c-176">Related topics</span></span>

[<span data-ttu-id="fba9c-177">Konfigurationsanforderungen für die moderne Authentifizierung für den Übergang von Office 365 dedizierten/ITAR zu vNext</span><span class="sxs-lookup"><span data-stu-id="fba9c-177">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
