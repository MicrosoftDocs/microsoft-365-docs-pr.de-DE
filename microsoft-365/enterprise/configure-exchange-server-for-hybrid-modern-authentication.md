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
description: Erfahren Sie, wie Sie eine Exchange Server lokal für die Verwendung der modernen Hybridauthentifizierung (Hybrid Modern Authentication, HMA) konfigurieren und Ihnen eine sicherere Benutzerauthentifizierung und Autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 21ffec620ac3e262679fc0e2385f6f0f1b31933b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362258"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="2966a-103">Lokale Konfiguration von Exchange Server derart, dass die moderne Hybridauthentifizierung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="2966a-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="2966a-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2966a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2966a-105">Die moderne Hybridauthentifizierung (Hybrid Modern Authentication, HMA) ist eine Methode der Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und Autorisierung bietet und für Exchange lokalen Hybridbereitstellungen des Servers verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2966a-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="2966a-106">Fyi</span><span class="sxs-lookup"><span data-stu-id="2966a-106">FYI</span></span>

<span data-ttu-id="2966a-107">Bevor wir beginnen, rufe ich Folgendes auf:</span><span class="sxs-lookup"><span data-stu-id="2966a-107">Before we begin, I call:</span></span>

- <span data-ttu-id="2966a-108">Hybrid Modern Authentication \> HMA</span><span class="sxs-lookup"><span data-stu-id="2966a-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="2966a-109">Exchange lokalen \> EXCH</span><span class="sxs-lookup"><span data-stu-id="2966a-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="2966a-110">\>Exchange Online Exo</span><span class="sxs-lookup"><span data-stu-id="2966a-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="2966a-111">Wenn eine Grafik in diesem Artikel über ein Objekt verfügt, *das "abgeblendet" oder "abgeblendet" ist, bedeutet dies, dass das grau dargestellte Element nicht in der HMA-spezifischen Konfiguration enthalten ist.*</span><span class="sxs-lookup"><span data-stu-id="2966a-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="2966a-112">Aktivieren der modernen Hybridauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="2966a-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="2966a-113">Das Aktivieren von HMA bedeutet:</span><span class="sxs-lookup"><span data-stu-id="2966a-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="2966a-114">Stellen Sie sicher, dass Sie die Prereqs erfüllen, bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="2966a-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="2966a-115">Da viele **Voraussetzungen** sowohl für Skype for Business als auch für Exchange üblich sind, bietet die [moderne Hybridauthentifizierung Übersicht und Voraussetzungen für die Verwendung mit lokalen Skype for Business und Exchange Servern.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2966a-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="2966a-116">Führen Sie dies aus, bevor Sie mit den Schritten in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="2966a-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="2966a-117">Hinzufügen von lokalen Webdienst-URLs als **Dienstprinzipalnamen (Service Principal Names, SPNs)** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2966a-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="2966a-118">Wenn SICH EXCH in einer Hybridumgebung mit **mehreren Mandanten** befindet, müssen diese lokalen Webdienst-URLs als SPNs in Azure AD aller Mandanten hinzugefügt werden, die sich in einer Hybridumgebung mit EXCH befinden.</span><span class="sxs-lookup"><span data-stu-id="2966a-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="2966a-119">Sicherstellen, dass alle virtuellen Verzeichnisse für HMA aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="2966a-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="2966a-120">Überprüfen auf das EvoSTS Auth Server-Objekt</span><span class="sxs-lookup"><span data-stu-id="2966a-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="2966a-121">Aktivieren von HMA in EXCH.</span><span class="sxs-lookup"><span data-stu-id="2966a-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="2966a-122">Unterstützt Ihre Version von Office MA?</span><span class="sxs-lookup"><span data-stu-id="2966a-122">Does your version of Office support MA?</span></span> <span data-ttu-id="2966a-123">Erfahren [Sie, wie moderne Authentifizierung für Office 2013- und Office 2016-Client-Apps funktioniert.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="2966a-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="2966a-124">Stellen Sie sicher, dass alle Voraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="2966a-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="2966a-125">Da viele Voraussetzungen sowohl für Skype for Business als auch für Exchange gelten, überprüfen Sie [die Übersicht über die moderne Hybridauthentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business und Exchange Servern.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2966a-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="2966a-126">Führen Sie dies  *aus, bevor*  Sie mit den Schritten in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="2966a-126">Do this  *before*  you begin any of the steps in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="2966a-127">Outlook Web App und Exchange Systemsteuerung funktioniert nicht mit moderner Hybridauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2966a-127">Outlook Web App and Exchange Control Panel does not work with hybrid Modern Authentication.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="2966a-128">Hinzufügen lokaler Webdienst-URLs als SPNs in Azure AD</span><span class="sxs-lookup"><span data-stu-id="2966a-128">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="2966a-129">Führen Sie die Befehle aus, die Ihre lokalen Webdienst-URLs als Azure AD SPNs zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2966a-129">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="2966a-130">SPNs werden während der Authentifizierung und Autorisierung von Clientcomputern und -geräten verwendet.</span><span class="sxs-lookup"><span data-stu-id="2966a-130">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="2966a-131">Alle URLs, die für die Verbindung von der lokalen Umgebung mit Azure Active Directory (Azure AD) verwendet werden können, müssen in Azure AD registriert werden (dies umfasst sowohl interne als auch externe Namespaces).</span><span class="sxs-lookup"><span data-stu-id="2966a-131">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="2966a-132">Sammeln Sie zunächst alle URLs, die Sie in AAD hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="2966a-132">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="2966a-133">Führen Sie die folgenden Befehle lokal aus:</span><span class="sxs-lookup"><span data-stu-id="2966a-133">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

<span data-ttu-id="2966a-134">Stellen Sie sicher, dass die URLs, mit denen Clients eine Verbindung herstellen können, in AAD als HTTPS-Dienstprinzipalnamen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="2966a-134">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="2966a-135">Wenn SICH EXCH in einer Hybridumgebung mit **mehreren Mandanten** befindet, sollten diese HTTPS-SPNs im AAD aller Mandanten in Hybridbereitstellung mit EXCH hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2966a-135">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="2966a-136">Stellen Sie zunächst mit [diesen Anweisungen](connect-to-microsoft-365-powershell.md)eine Verbindung mit AAD her.</span><span class="sxs-lookup"><span data-stu-id="2966a-136">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="2966a-137">Sie müssen die _Option Verbinden-MsolService_ von dieser Seite verwenden, um den folgenden Befehl verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="2966a-137">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="2966a-138">Geben Sie für ihre Exchange-bezogenen URLs den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="2966a-138">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="2966a-139">Notieren Sie sich die Ausgabe dieses Befehls (und screenshot für einen späteren Vergleich), der eine https://  *autodiscover.yourdomain.com*  und https://  *mail.yourdomain.com* URL enthalten sollte, aber hauptsächlich aus SPNs besteht, die mit 000000002-0000-0ff1-ce00-000000000000/beginnen.</span><span class="sxs-lookup"><span data-stu-id="2966a-139">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="2966a-140">Wenn https:// URLs aus Ihrer lokalen Umgebung fehlen, müssen wir diese spezifischen Datensätze zu dieser Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2966a-140">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="2966a-141">Wenn Ihre internen und externen MAPI/HTTP-, EWS-, ActiveSync-, OAB- und AutoErmittlungseinträge in dieser Liste nicht angezeigt werden, müssen Sie sie mit dem folgenden Befehl hinzufügen (die Beispiel-URLs sind ' `mail.corp.contoso.com` ' und ' `owa.contoso.com` ', aber Sie würden die **Beispiel-URLs durch Ihre eigenen ersetzen):**</span><span class="sxs-lookup"><span data-stu-id="2966a-141">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="2966a-142">Stellen Sie sicher, dass die neuen Datensätze hinzugefügt wurden, indem Sie den Befehl Get-MsolServicePrincipal aus Schritt 2 erneut ausführen und die Ausgabe durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="2966a-142">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="2966a-143">Vergleichen Sie die Liste/den Screenshot von zuvor mit der neuen Liste der SPNs.</span><span class="sxs-lookup"><span data-stu-id="2966a-143">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="2966a-144">Sie können auch einen Screenshot der neuen Liste für Ihre Datensätze erstellen.</span><span class="sxs-lookup"><span data-stu-id="2966a-144">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="2966a-145">Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2966a-145">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="2966a-146">In unserem Beispiel enthält die Liste der SPNs jetzt die spezifischen URLs  `https://mail.corp.contoso.com`  und  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="2966a-146">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="2966a-147">Überprüfen, ob virtuelle Verzeichnisse ordnungsgemäß konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="2966a-147">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="2966a-148">Überprüfen Sie nun, ob OAuth in Exchange für alle virtuellen Verzeichnisse ordnungsgemäß aktiviert ist, Outlook möglicherweise verwenden, indem Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="2966a-148">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="2966a-149">Überprüfen Sie die Ausgabe, um sicherzustellen, dass **OAuth** für jeden dieser VDirs aktiviert ist, es sieht ungefähr wie folgt aus (und das Wichtigste ist "OAuth"):</span><span class="sxs-lookup"><span data-stu-id="2966a-149">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="2966a-150">Wenn OAuth auf einem Server und einem der vier virtuellen Verzeichnisse fehlt, müssen Sie es mit den entsprechenden Befehlen hinzufügen, bevor Sie fortfahren ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)und [Set-AutoDiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="2966a-150">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="2966a-151">Bestätigen, dass das EvoSTS Auth Server-Objekt vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="2966a-151">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="2966a-152">Kehren Sie für diesen letzten Befehl zur lokalen Exchange-Verwaltungsshell zurück.</span><span class="sxs-lookup"><span data-stu-id="2966a-152">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="2966a-153">Jetzt können Sie überprüfen, ob Ihre lokale Umgebung über einen Eintrag für den EvoSTS-Authentifizierungsanbieter verfügt:</span><span class="sxs-lookup"><span data-stu-id="2966a-153">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

<span data-ttu-id="2966a-154">In der Ausgabe sollte ein AuthServer mit dem Namen "EvoSts" und der Status "Enabled" auf "True" festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="2966a-154">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="2966a-155">Wenn dies nicht angezeigt wird, sollten Sie die neueste Version des Hybridkonfigurations-Assistenten herunterladen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="2966a-155">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="2966a-156">Wenn SICH EXCH in einer Hybridumgebung mit **mehreren Mandanten** befindet, sollte die Ausgabe einen AuthServer des Namens "EvoSts - {GUID}" für jeden Mandanten in einer Hybridumgebung mit EXCH anzeigen, und der Status "Enabled" sollte für alle diese AuthServer-Objekte "True" sein.</span><span class="sxs-lookup"><span data-stu-id="2966a-156">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="2966a-157">**Wichtig** Wenn Sie Exchange 2010 in Ihrer Umgebung ausführen, wird der EvoSTS-Authentifizierungsanbieter nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="2966a-157">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="2966a-158">Aktivieren von HMA</span><span class="sxs-lookup"><span data-stu-id="2966a-158">Enable HMA</span></span>

<span data-ttu-id="2966a-159">Führen Sie den folgenden Befehl in der lokalen Exchange Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="2966a-159">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="2966a-160">Wenn die EXCH-Version Exchange 2016 (CU18 oder höher) oder Exchange 2019 (CU7 oder höher) ist und die Hybridbereitstellung mit HCW konfiguriert wurde, die nach September 2020 heruntergeladen wurde, führen Sie den folgenden Befehl in der lokalen Exchange-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="2966a-160">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="2966a-161">Wenn SICH EXCH in einer Hybridumgebung mit **mehreren Mandanten** befindet, sind in EXCH mehrere AuthServer-Objekte mit Domänen vorhanden, die jedem Mandanten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2966a-161">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="2966a-162">Das **IsDefaultAuthorizationEndpoint-Flag** sollte für eines dieser AuthServer-Objekte auf "true" (mithilfe des Cmdlets **"IsDefaultAuthorizationEndpoint")** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2966a-162">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="2966a-163">Dieses Flag kann nicht für alle Authserver-Objekte auf "true" festgelegt werden, und HMA wäre auch aktiviert, wenn eines dieser AuthServer-Objekte **isDefaultAuthorizationEndpoint-Flag** auf "true" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2966a-163">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="2966a-164">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="2966a-164">Verify</span></span>

<span data-ttu-id="2966a-165">Sobald Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen Authentifizierungsfluss.</span><span class="sxs-lookup"><span data-stu-id="2966a-165">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="2966a-166">Beachten Sie, dass das aktivieren von HMA keine erneute Authentifizierung für einen Client auslöst, und es kann eine Weile dauern, bis Exchange die neuen Einstellungen übernimmt.</span><span class="sxs-lookup"><span data-stu-id="2966a-166">Note that just turning on HMA won't trigger a reauthentication for any client, and it might take a while for Exchange to pick up the new settings.</span></span>

<span data-ttu-id="2966a-167">Sie sollten auch die STRG-TASTE gedrückt halten, während Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client klicken (auch im Windows Benachrichtigungsschacht), und klicken Sie auf "Verbindungsstatus".</span><span class="sxs-lookup"><span data-stu-id="2966a-167">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="2966a-168">Suchen Sie nach der SMTP-Adresse des Clients für den "Authn"-Typ \* "Bearer", der das in OAuth verwendete Bearertoken darstellt.</span><span class="sxs-lookup"><span data-stu-id="2966a-168">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="2966a-169">Müssen Sie Skype for Business mit HMA konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="2966a-169">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="2966a-170">Sie benötigen zwei Artikel: einen, in dem [die unterstützten Topologien](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)aufgeführt sind, und einen Artikel, in dem die [Konfiguration beschrieben](configure-skype-for-business-for-hybrid-modern-authentication.md)wird.</span><span class="sxs-lookup"><span data-stu-id="2966a-170">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="2966a-171">Verwenden der modernen Hybridauthentifizierung mit Outlook für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="2966a-171">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="2966a-172">Wenn Sie ein lokaler Kunde sind, der Exchange Server unter TCP 443 verwendet, umgehen Sie die Datenverkehrsverarbeitung für die folgenden IP-Adressbereiche:</span><span class="sxs-lookup"><span data-stu-id="2966a-172">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

<span data-ttu-id="2966a-173">Die Outlook-App für iOS und Android ist die beste Möglichkeit, Microsoft 365 oder Office 365 auf Ihrem mobilen Gerät zu erleben, indem sie Microsoft-Dienste verwendet, um Ihren täglichen Leben und Ihre Arbeit zu suchen, zu planen und zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="2966a-173">The Outlook app for iOS and Android is designed as the best way to experience Microsoft 365 or Office 365 on your mobile device by using Microsoft services to help find, plan, and prioritize your daily life and work.</span></span> <span data-ttu-id="2966a-174">Weitere Informationen finden Sie unter [Verwenden der modernen Hybridauthentifizierung mit Outlook für iOS und Android.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)</span><span class="sxs-lookup"><span data-stu-id="2966a-174">For more information, please refer to [Using hybrid Modern Authentication with Outlook for iOS and Android](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2966a-175">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2966a-175">Related topics</span></span>

[<span data-ttu-id="2966a-176">Konfigurationsanforderungen für die moderne Authentifizierung für den Übergang von Office 365 dedizieren/ITAR zu vNext</span><span class="sxs-lookup"><span data-stu-id="2966a-176">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
