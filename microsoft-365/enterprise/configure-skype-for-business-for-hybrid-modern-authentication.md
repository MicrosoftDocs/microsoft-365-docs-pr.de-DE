---
title: Lokale Konfiguration von Skype for Business derart, dass die moderne Hybridauthentifizierung verwendet wird
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie Skype for Business lokal für die Verwendung der modernen Hybridauthentifizierung (Hybrid Modern Authentication, HMA) konfigurieren und Ihnen eine sicherere Benutzerauthentifizierung und Autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9695815d0a085931b10f7f64b9fca2e997af9077
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286057"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="304e7-103">Lokale Konfiguration von Skype for Business derart, dass die moderne Hybridauthentifizierung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="304e7-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="304e7-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="304e7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="304e7-105">Moderne Authentifizierung ist eine Methode der Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und Autorisierung bietet, für Skype for Business lokalen Server und Exchange lokalen Server sowie für hybride hybride Skype for Business geteilte Domänen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="304e7-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>

 <span data-ttu-id="304e7-106">**Wichtig** Möchten Sie mehr über die moderne Authentifizierung (MA) erfahren und warum Sie es vielleicht vorziehen, sie in Ihrem Unternehmen oder Ihrer Organisation zu verwenden?</span><span class="sxs-lookup"><span data-stu-id="304e7-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="304e7-107">In [diesem Dokument](hybrid-modern-auth-overview.md) finden Sie eine Übersicht.</span><span class="sxs-lookup"><span data-stu-id="304e7-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="304e7-108">Wenn Sie wissen müssen, welche Skype for Business Topologien mit MA unterstützt werden, ist dies hier dokumentiert!</span><span class="sxs-lookup"><span data-stu-id="304e7-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>

 <span data-ttu-id="304e7-109">**Bevor wir beginnen,** verwende ich die folgenden Begriffe:</span><span class="sxs-lookup"><span data-stu-id="304e7-109">**Before we begin**, I use these terms:</span></span>

- <span data-ttu-id="304e7-110">Moderne Authentifizierung (MA)</span><span class="sxs-lookup"><span data-stu-id="304e7-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="304e7-111">Moderne Hybridauthentifizierung (Hybrid Modern Authentication, HMA)</span><span class="sxs-lookup"><span data-stu-id="304e7-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="304e7-112">Exchange lokal (EXCH)</span><span class="sxs-lookup"><span data-stu-id="304e7-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="304e7-113">Exchange Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="304e7-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="304e7-114">Skype for Business lokal (SFB)</span><span class="sxs-lookup"><span data-stu-id="304e7-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="304e7-115">Skype for Business Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="304e7-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="304e7-116">Wenn eine Grafik in diesem Artikel ein Ausgegrautes oder abgeblendetes Objekt aufweist, bedeutet dies, dass das grau dargestellte Element nicht in der MA-spezifischen Konfiguration enthalten **ist.**</span><span class="sxs-lookup"><span data-stu-id="304e7-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>

## <a name="read-the-summary"></a><span data-ttu-id="304e7-117">Zusammenfassung lesen</span><span class="sxs-lookup"><span data-stu-id="304e7-117">Read the summary</span></span>

<span data-ttu-id="304e7-118">Diese Zusammenfassung unterteilt den Prozess in Schritte, die andernfalls während der Ausführung verloren gehen könnten, und eignet sich für eine allgemeine Prüfliste, um nachzuverfolgen, wo Sie sich im Prozess befinden.</span><span class="sxs-lookup"><span data-stu-id="304e7-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>

1. <span data-ttu-id="304e7-119">Stellen Sie zunächst sicher, dass alle Voraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="304e7-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="304e7-120">Da viele Voraussetzungen sowohl für Skype for Business als auch für Exchange gelten, finden Sie im **Übersichtsartikel** [Ihre Vorabprüfliste.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="304e7-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="304e7-121">Führen Sie dies  *aus, bevor*  Sie mit den Schritten in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="304e7-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="304e7-122">Sammeln Sie die HMA-spezifischen Informationen, die Sie in einer Datei oder OneNote benötigen.</span><span class="sxs-lookup"><span data-stu-id="304e7-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="304e7-123">Aktivieren Sie die moderne Authentifizierung für EXO (wenn sie noch nicht aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="304e7-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="304e7-124">Aktivieren Sie die moderne Authentifizierung für SFBO (wenn sie noch nicht aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="304e7-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="304e7-125">Aktivieren Sie die moderne Hybridauthentifizierung für Exchange lokal.</span><span class="sxs-lookup"><span data-stu-id="304e7-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="304e7-126">Aktivieren Sie die moderne Hybridauthentifizierung für Skype for Business lokal.</span><span class="sxs-lookup"><span data-stu-id="304e7-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="304e7-127">In diesen Schritten wird MA für SFB, SFBO, EXCH und EXO aktiviert, d. h. alle Produkte, die an einer HMA-Konfiguration von SFB und SFBO teilnehmen können (einschließlich Abhängigkeiten von EXCH/EXO).</span><span class="sxs-lookup"><span data-stu-id="304e7-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="304e7-128">Anders ausgedrückt: Wenn Ihre Benutzer in postfächern verwaltet werden bzw. in einem Teil der Hybridbereitstellung erstellt wurden (EXO + SFBO, EXO + SFB, EXCH + SFBO oder EXCH + SFB), sieht Das Fertigprodukt wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="304e7-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>

![In einer gemischten 6-Skype für die HMA-Topologie für Unternehmen ist ma an allen vier möglichen Standorten aktiviert.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

<span data-ttu-id="304e7-130">Wie Sie sehen können, gibt es vier verschiedene Stellen zum Aktivieren von MA!</span><span class="sxs-lookup"><span data-stu-id="304e7-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="304e7-131">Um eine optimale Benutzererfahrung zu erzielen, empfehlen wir, ma an allen vier Speicherorten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="304e7-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="304e7-132">Wenn Sie MA an all diesen Speicherorten nicht aktivieren können, passen Sie die Schritte so an, dass Sie MA nur an den Speicherorten aktivieren, die für Ihre Umgebung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="304e7-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>

<span data-ttu-id="304e7-133">Informationen zu unterstützten Topologien finden Sie im [Thema "Supportability" für Skype for Business mit MA.](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)</span><span class="sxs-lookup"><span data-stu-id="304e7-133">See the [Supportability topic for Skype for Business with MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) for supported topologies.</span></span>

 <span data-ttu-id="304e7-134">**Wichtig** Vergewissern Sie sich, dass alle Voraussetzungen erfüllt sind, bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="304e7-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="304e7-135">Sie finden diese Informationen in der Übersicht über die [moderne Hybridauthentifizierung und den voraussetzungen.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="304e7-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>

## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="304e7-136">Sammeln aller HMA-spezifischen Informationen, die Sie benötigen</span><span class="sxs-lookup"><span data-stu-id="304e7-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="304e7-137">Nachdem Sie überprüft haben, ob sie die Voraussetzungen für die Verwendung der [modernen](hybrid-modern-auth-overview.md) Authentifizierung erfüllen (siehe Hinweis oben), sollten Sie eine Datei erstellen, die die Informationen enthält, die Sie für die Konfiguration von HMA in den nächsten Schritten benötigen.</span><span class="sxs-lookup"><span data-stu-id="304e7-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="304e7-138">In diesem Artikel verwendete Beispiele:</span><span class="sxs-lookup"><span data-stu-id="304e7-138">Examples used in this article:</span></span>

- <span data-ttu-id="304e7-139">**SIP-/SMTP-Domäne**</span><span class="sxs-lookup"><span data-stu-id="304e7-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="304e7-140">Ex.</span><span class="sxs-lookup"><span data-stu-id="304e7-140">Ex.</span></span> <span data-ttu-id="304e7-141">contoso.com (ist mit Office 365 verbunden)</span><span class="sxs-lookup"><span data-stu-id="304e7-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="304e7-142">**Mandanten-ID**</span><span class="sxs-lookup"><span data-stu-id="304e7-142">**Tenant ID**</span></span>

  - <span data-ttu-id="304e7-143">Die GUID, die Ihren Office 365 Mandanten darstellt (bei der Anmeldung von contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="304e7-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="304e7-144">**SFB 2015 CU5-Webdienst-URLs**</span><span class="sxs-lookup"><span data-stu-id="304e7-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="304e7-145">Sie benötigen interne und externe Webdienst-URLs für alle bereitgestellten SfB 2015-Pools.</span><span class="sxs-lookup"><span data-stu-id="304e7-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="304e7-146">Führen Sie die folgenden Schritte aus Skype for Business Verwaltungsshell aus, um diese abzurufen:</span><span class="sxs-lookup"><span data-stu-id="304e7-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="304e7-147">Ex.</span><span class="sxs-lookup"><span data-stu-id="304e7-147">Ex.</span></span> <span data-ttu-id="304e7-148">Interne: https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="304e7-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="304e7-149">Ex.</span><span class="sxs-lookup"><span data-stu-id="304e7-149">Ex.</span></span> <span data-ttu-id="304e7-150">Externen: https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="304e7-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="304e7-151">Wenn Sie einen Standard Edition Server verwenden, ist die interne URL leer.</span><span class="sxs-lookup"><span data-stu-id="304e7-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="304e7-152">Verwenden Sie in diesem Fall den Pool-Fqdn für die interne URL.</span><span class="sxs-lookup"><span data-stu-id="304e7-152">In this case, use the pool fqdn for the internal URL.</span></span>

## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="304e7-153">Aktivieren der modernen Authentifizierung für EXO</span><span class="sxs-lookup"><span data-stu-id="304e7-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="304e7-154">Folgen Sie den Anweisungen hier: [Exchange Online: So aktivieren Sie Ihren Mandanten für die moderne Authentifizierung.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="304e7-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>

## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="304e7-155">Aktivieren der modernen Authentifizierung für SFBO</span><span class="sxs-lookup"><span data-stu-id="304e7-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="304e7-156">Folgen Sie den Anweisungen hier: [Skype for Business Online: Aktivieren Ihres Mandanten für die moderne Authentifizierung.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="304e7-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="304e7-157">Aktivieren der modernen Hybridauthentifizierung für Exchange lokal</span><span class="sxs-lookup"><span data-stu-id="304e7-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="304e7-158">Folgen Sie den Anweisungen hier: So konfigurieren Sie Exchange Server lokal für die Verwendung der [modernen Hybridauthentifizierung.](configure-exchange-server-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="304e7-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="304e7-159">Aktivieren der modernen Hybridauthentifizierung für Skype for Business lokal</span><span class="sxs-lookup"><span data-stu-id="304e7-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="304e7-160">Hinzufügen lokaler Webdienst-URLs als SPNs in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="304e7-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="304e7-161">Jetzt müssen Sie Befehle ausführen, um die URLs (die zuvor erfasst wurden) als Dienstprinzipale in SFBO hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="304e7-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>

 <span data-ttu-id="304e7-162">**Hinweis** Dienstprinzipalnamen (SPNs) identifizieren Webdienste und ordnen sie einem Sicherheitsprinzipal zu (z. B. einem Kontonamen oder einer Gruppe), damit der Dienst im Namen eines autorisierten Benutzers handeln kann.</span><span class="sxs-lookup"><span data-stu-id="304e7-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="304e7-163">Clients, die sich bei einem Server authentifizieren, verwenden Informationen, die in SPNs enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="304e7-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>

1. <span data-ttu-id="304e7-164">Stellen Sie zunächst mit diesen Anweisungen eine Verbindung mit Azure Active Directory (Azure AD) [her.](/powershell/azure/active-directory/overview)</span><span class="sxs-lookup"><span data-stu-id="304e7-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](/powershell/azure/active-directory/overview).</span></span>

2. <span data-ttu-id="304e7-165">Führen Sie diesen Befehl lokal aus, um eine Liste der SFB-Webdienst-URLs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="304e7-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="304e7-166">Beachten Sie, dass die AppPrincipalId `00000004` mit .</span><span class="sxs-lookup"><span data-stu-id="304e7-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="304e7-167">Dies entspricht Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="304e7-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="304e7-168">Notieren Sie sich die Ausgabe dieses Befehls (und screenshot für einen späteren Vergleich), der eine SE und eine WS-URL enthält, aber hauptsächlich aus SPNs besteht, die mit `00000004-0000-0ff1-ce00-000000000000/` .</span><span class="sxs-lookup"><span data-stu-id="304e7-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="304e7-169">Wenn die internen **oder** externen SFB-URLs aus der lokalen Umgebung fehlen (z. B. https://lyncwebint01.contoso.com müssen wir diese https://lyncwebext01.contoso.com) spezifischen Datensätze zu dieser Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="304e7-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="304e7-170">Ersetzen Sie unbedingt die unten aufgeführten  *Beispiel-URLs* durch Ihre tatsächlichen URLs in den Add-Befehlen!</span><span class="sxs-lookup"><span data-stu-id="304e7-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>

```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. <span data-ttu-id="304e7-171">Stellen Sie sicher, dass die neuen Datensätze hinzugefügt wurden, indem Sie den Befehl **"Get-MsolServicePrincipal"** aus Schritt 2 erneut ausführen und die Ausgabe durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="304e7-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="304e7-172">Vergleichen Sie die Zuvor-Liste oder den Screenshot mit der neuen Liste der SPNs.</span><span class="sxs-lookup"><span data-stu-id="304e7-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="304e7-173">Sie können auch die neue Liste für Ihre Datensätze screenshots.</span><span class="sxs-lookup"><span data-stu-id="304e7-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="304e7-174">Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="304e7-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="304e7-175">In unserem Beispiel enthält die Liste der SPNs jetzt die spezifischen URLs https://lyncwebint01.contoso.com und https://lyncwebext01.contoso.com/ .</span><span class="sxs-lookup"><span data-stu-id="304e7-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="304e7-176">Erstellen des EvoSTS Auth Server-Objekts</span><span class="sxs-lookup"><span data-stu-id="304e7-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="304e7-177">Führen Sie den folgenden Befehl in der Skype for Business-Verwaltungsshell aus.</span><span class="sxs-lookup"><span data-stu-id="304e7-177">Run the following command in the Skype for Business Management Shell.</span></span>

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="304e7-178">Aktivieren der modernen Hybridauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="304e7-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="304e7-179">Dies ist der Schritt, in dem MA tatsächlich aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="304e7-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="304e7-180">Alle vorherigen Schritte können vorab ausgeführt werden, ohne den Clientauthentifizierungsfluss zu ändern.</span><span class="sxs-lookup"><span data-stu-id="304e7-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="304e7-181">Wenn Sie bereit sind, den Authentifizierungsfluss zu ändern, führen Sie diesen Befehl in der Skype for Business Verwaltungsshell aus.</span><span class="sxs-lookup"><span data-stu-id="304e7-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="304e7-182">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="304e7-182">Verify</span></span>

<span data-ttu-id="304e7-183">Sobald Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen Authentifizierungsfluss.</span><span class="sxs-lookup"><span data-stu-id="304e7-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="304e7-184">Beachten Sie, dass das aktivieren von HMA keine erneute Authentifizierung für einen Client auslöst.</span><span class="sxs-lookup"><span data-stu-id="304e7-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="304e7-185">Die Clients authentifizieren sich basierend auf der Lebensdauer der Authentifizierungstoken und/oder Zertifikate, über die sie verfügen.</span><span class="sxs-lookup"><span data-stu-id="304e7-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="304e7-186">Um zu testen, ob HMA funktioniert, nachdem Sie es aktiviert haben, melden Sie sich von einem SFB-Testclient Windows ab, und klicken Sie auf "Meine Anmeldeinformationen löschen".</span><span class="sxs-lookup"><span data-stu-id="304e7-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="304e7-187">Melden Sie sich erneut an.</span><span class="sxs-lookup"><span data-stu-id="304e7-187">Sign in again.</span></span> <span data-ttu-id="304e7-188">Der Client sollte jetzt den Modern Auth-Fluss verwenden, und Ihre Anmeldung enthält jetzt eine **Office 365** Eingabeaufforderung für ein Geschäfts-, Schul- oder Unikonto, die direkt vor dem Kontakt des Clients mit dem Server angezeigt wird und Sie anmeldet.</span><span class="sxs-lookup"><span data-stu-id="304e7-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>

<span data-ttu-id="304e7-189">Sie sollten auch die "Konfigurationsinformationen" für Skype for Business Clients auf "OAuth Authority" überprüfen.</span><span class="sxs-lookup"><span data-stu-id="304e7-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="304e7-190">Halten Sie dazu auf ihrem Clientcomputer die STRG-TASTE gedrückt, während Sie im Windows Benachrichtigungsschacht mit der rechten Maustaste auf das Skype for Business-Symbol klicken.</span><span class="sxs-lookup"><span data-stu-id="304e7-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="304e7-191">Klicken Sie im angezeigten Menü auf **"Konfigurationsinformationen".**</span><span class="sxs-lookup"><span data-stu-id="304e7-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="304e7-192">Suchen Sie im Fenster "Skype for Business Konfigurationsinformationen", das auf dem Desktop angezeigt wird, nach Folgendem:</span><span class="sxs-lookup"><span data-stu-id="304e7-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>

![Die Konfigurationsinformationen eines Skype for Business-Clients mit moderner Authentifizierung zeigen die URL einer Lync- und EWS-OAUTH-Autorität von https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)

<span data-ttu-id="304e7-194">Sie sollten auch die STRG-TASTE gedrückt halten, während Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client klicken (auch im Windows Benachrichtigungsschacht), und klicken Sie auf "Verbindungsstatus".</span><span class="sxs-lookup"><span data-stu-id="304e7-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="304e7-195">Suchen Sie nach der SMTP-Adresse des Clients für den AuthN-Typ \* "Bearer", der das in OAuth verwendete Bearertoken darstellt.</span><span class="sxs-lookup"><span data-stu-id="304e7-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

## <a name="related-articles"></a><span data-ttu-id="304e7-196">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="304e7-196">Related articles</span></span>

<span data-ttu-id="304e7-197">[Link zurück zur Übersicht über die moderne Authentifizierung.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="304e7-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>

<span data-ttu-id="304e7-198">Müssen Sie wissen, wie Sie die moderne Authentifizierung (Modern Authentication, ADAL) für Ihre Skype for Business-Clients verwenden?</span><span class="sxs-lookup"><span data-stu-id="304e7-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="304e7-199">Wir haben [hier](./hybrid-modern-auth-overview.md)Schritte.</span><span class="sxs-lookup"><span data-stu-id="304e7-199">We've got steps [here](./hybrid-modern-auth-overview.md).</span></span>