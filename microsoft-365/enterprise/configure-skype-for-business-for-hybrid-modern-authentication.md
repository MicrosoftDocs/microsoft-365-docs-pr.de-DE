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
description: In diesem Artikel erfahren Sie, wie Sie Skype for Business lokal für die Verwendung der Hybriden modernen Authentifizierung (HMA) konfigurieren und Ihnen eine sicherere Benutzerauthentifizierung und-Autorisierung bieten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695014"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="863c4-103">Lokale Konfiguration von Skype for Business derart, dass die moderne Hybridauthentifizierung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="863c4-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="863c4-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="863c4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="863c4-105">Die moderne Authentifizierung ist eine Methode zur Identitätsverwaltung, die eine sicherere Benutzerauthentifizierung und-Autorisierung bietet und für Skype for Business lokalen Server und lokale Exchange-Server-und Split-Domain-Skype for Business Hybriden verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="863c4-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>
  
 <span data-ttu-id="863c4-106">**Wichtiger Hinweis** Möchten Sie mehr über die moderne Authentifizierung (MA) erfahren und warum Sie Sie in Ihrem Unternehmen oder Ihrer Organisation verwenden möchten?</span><span class="sxs-lookup"><span data-stu-id="863c4-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="863c4-107">In [diesem Dokument](hybrid-modern-auth-overview.md) finden Sie eine Übersicht.</span><span class="sxs-lookup"><span data-stu-id="863c4-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="863c4-108">Wenn Sie wissen möchten, welche Skype for Business Topologien mit MA unterstützt werden, ist dies hier dokumentiert!</span><span class="sxs-lookup"><span data-stu-id="863c4-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>
  
 <span data-ttu-id="863c4-109">**Bevor wir beginnen**, verwende ich diese Begriffe:</span><span class="sxs-lookup"><span data-stu-id="863c4-109">**Before we begin**, I use these terms:</span></span>
  
- <span data-ttu-id="863c4-110">Moderne Authentifizierung (MA)</span><span class="sxs-lookup"><span data-stu-id="863c4-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="863c4-111">Hybride moderne Authentifizierung (HMA)</span><span class="sxs-lookup"><span data-stu-id="863c4-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="863c4-112">Exchange lokal (Kurs)</span><span class="sxs-lookup"><span data-stu-id="863c4-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="863c4-113">Exchange Online (Exo)</span><span class="sxs-lookup"><span data-stu-id="863c4-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="863c4-114">Skype for Business lokal (SFB)</span><span class="sxs-lookup"><span data-stu-id="863c4-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="863c4-115">Skype for Business Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="863c4-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="863c4-116">Wenn eine Grafik in diesem Artikel ein abgeblendetes oder abgeblendetes Objekt enthält, bedeutet dies, dass das in Grau dargestellte Element **nicht** in der MA-spezifischen Konfiguration enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="863c4-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>
  
## <a name="read-the-summary"></a><span data-ttu-id="863c4-117">Lesen Sie die Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="863c4-117">Read the summary</span></span>

<span data-ttu-id="863c4-118">In dieser Zusammenfassung wird der Prozess in Schritte unterteilt, die andernfalls während der Ausführung verloren gehen können, und eignet sich gut für eine allgemeine Prüfliste, um die Position im Prozess nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="863c4-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>
  
1. <span data-ttu-id="863c4-119">Stellen Sie zunächst sicher, dass alle Voraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="863c4-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="863c4-120">Da zahlreiche **Voraussetzungen** sowohl für Skype for Business als auch für Exchange gelten, [Lesen Sie den Übersichtsartikel über die Prüfliste für vorab](hybrid-modern-auth-overview.md)Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="863c4-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="863c4-121">Tun Sie dies,  *bevor*  Sie einen der Schritte in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="863c4-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="863c4-122">Sammeln Sie die HMA-spezifischen Informationen, die Sie in einer Datei oder in OneNote benötigen.</span><span class="sxs-lookup"><span data-stu-id="863c4-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="863c4-123">Aktivieren Sie die moderne Authentifizierung für Exo (sofern Sie noch nicht aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="863c4-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="863c4-124">Aktivieren Sie die moderne Authentifizierung für SFBO (sofern Sie noch nicht aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="863c4-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="863c4-125">Aktivieren Sie die hybride moderne Authentifizierung für Exchange lokal.</span><span class="sxs-lookup"><span data-stu-id="863c4-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="863c4-126">Aktivieren Sie die moderne Hybrid Authentifizierung für Skype for Business lokal.</span><span class="sxs-lookup"><span data-stu-id="863c4-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="863c4-127">Mit diesen Schritten wird MA für SFB, SFBO, Wechsel und Exo aktiviert, also alle Produkte, die an einer HMA-Konfiguration von SFB und SFBO (einschließlich Abhängigkeiten von Wechsel/Exo) teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="863c4-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="863c4-128">In anderen Worten: Wenn Ihre Benutzer in einem beliebigen Teil des Hybrids (Exo + SFBO, Exo + SFB, interSFBO, oder mit dem SFB) erstellt wurden oder Postfächer besitzen, sieht Ihr fertiges Produkt wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="863c4-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>
  
![Eine gemischte 6 Skype for Business-HMA-Topologie hat MA an an allen vier möglichen Standorten.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
<span data-ttu-id="863c4-130">Wie Sie sehen können, gibt es vier unterschiedliche Orte, an denen MA aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="863c4-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="863c4-131">Für eine optimale Benutzererfahrung empfehlen wir Ihnen, MA an allen vier Standorten einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="863c4-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="863c4-132">Wenn Sie den MA nicht an allen diesen Speicherorten aktivieren können, passen Sie die Schritte so an, dass Sie den MA nur an den für Ihre Umgebung erforderlichen Speicherorten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="863c4-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>
  
<span data-ttu-id="863c4-133">Weitere Informationen finden Sie im [Thema zur Unterstützung von Skype for Business mit MA](https://technet.microsoft.com/library/mt803262.aspx) für unterstützte Topologien.</span><span class="sxs-lookup"><span data-stu-id="863c4-133">See the [Supportability topic for Skype for Business with MA](https://technet.microsoft.com/library/mt803262.aspx) for supported topologies.</span></span>
  
 <span data-ttu-id="863c4-134">**Wichtiger Hinweis** Stellen Sie sicher, dass alle Voraussetzungen erfüllt sind, bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="863c4-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="863c4-135">Diese Informationen finden Sie unter [Übersicht über die moderne Hybrid Authentifizierung und Voraussetzungen](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="863c4-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>
  
## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="863c4-136">Sammeln Sie alle HMA-spezifischen Informationen, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="863c4-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="863c4-137">Nachdem Sie die [Voraussetzungen](hybrid-modern-auth-overview.md) für die Verwendung der modernen Authentifizierung überprüft haben (siehe Hinweis oben), sollten Sie eine Datei erstellen, in der die Informationen gespeichert sind, die Sie für die Konfiguration von HMA in den nächsten Schritten benötigen.</span><span class="sxs-lookup"><span data-stu-id="863c4-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="863c4-138">In diesem Artikel verwendete Beispiele:</span><span class="sxs-lookup"><span data-stu-id="863c4-138">Examples used in this article:</span></span>
  
- <span data-ttu-id="863c4-139">**SIP/SMTP-Domäne**</span><span class="sxs-lookup"><span data-stu-id="863c4-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="863c4-140">Ex.</span><span class="sxs-lookup"><span data-stu-id="863c4-140">Ex.</span></span> <span data-ttu-id="863c4-141">contoso.com (ist Verbund mit Office 365)</span><span class="sxs-lookup"><span data-stu-id="863c4-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="863c4-142">**Mandanten-ID**</span><span class="sxs-lookup"><span data-stu-id="863c4-142">**Tenant ID**</span></span>

  - <span data-ttu-id="863c4-143">Die GUID, die den Office 365-Mandanten darstellt (beim Anmelden von contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="863c4-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="863c4-144">**SFB 2015 CU5-Webdienst-URLs**</span><span class="sxs-lookup"><span data-stu-id="863c4-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="863c4-145">Sie benötigen interne und externe Webdienst-URLs für alle bereitgestellten SFB 2015-Pools.</span><span class="sxs-lookup"><span data-stu-id="863c4-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="863c4-146">Um diese zu erhalten, führen Sie Folgendes aus Skype for Business-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="863c4-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="863c4-147">Ex.</span><span class="sxs-lookup"><span data-stu-id="863c4-147">Ex.</span></span> <span data-ttu-id="863c4-148">Internen https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="863c4-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="863c4-149">Ex.</span><span class="sxs-lookup"><span data-stu-id="863c4-149">Ex.</span></span> <span data-ttu-id="863c4-150">Externen https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="863c4-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="863c4-151">Wenn Sie ein Standard Edition-Server verwenden, ist die interne URL leer.</span><span class="sxs-lookup"><span data-stu-id="863c4-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="863c4-152">Verwenden Sie in diesem Fall den Pool-FQDN für die interne URL.</span><span class="sxs-lookup"><span data-stu-id="863c4-152">In this case, use the pool fqdn for the internal URL.</span></span>
  
## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="863c4-153">Aktivieren der modernen Authentifizierung für Exo</span><span class="sxs-lookup"><span data-stu-id="863c4-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="863c4-154">Befolgen Sie die Anweisungen hier: [Exchange Online: Aktivieren des Mandanten für die moderne Authentifizierung.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="863c4-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>
  
## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="863c4-155">Aktivieren der modernen Authentifizierung für SFBO</span><span class="sxs-lookup"><span data-stu-id="863c4-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="863c4-156">Befolgen Sie die Anweisungen hier: [Skype for Business Online: Aktivieren Sie Ihren Mandanten für die moderne Authentifizierung](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span><span class="sxs-lookup"><span data-stu-id="863c4-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="863c4-157">Aktivieren der modernen Hybrid Authentifizierung für Exchange lokal</span><span class="sxs-lookup"><span data-stu-id="863c4-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="863c4-158">Befolgen Sie die Anweisungen hier: [konfigurieren Exchange Server lokal für die Verwendung der modernen Hybrid Authentifizierung](configure-exchange-server-for-hybrid-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="863c4-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="863c4-159">Aktivieren der modernen Hybrid Authentifizierung für Skype for Business lokal</span><span class="sxs-lookup"><span data-stu-id="863c4-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="863c4-160">Hinzufügen von lokalen Webdienst-URLs als SPNs in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="863c4-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="863c4-161">Jetzt müssen Sie Befehle ausführen, um die zuvor gesammelten URLs als Dienst Prinzipale in SFBO hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="863c4-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>
  
 <span data-ttu-id="863c4-162">**Hinweis:** Dienstprinzipalnamen (Service Principal Names, SPNs) identifizieren Webdienste und ordnen Sie einem Sicherheitsprinzipal zu (beispielsweise einem Kontonamen oder einer Gruppe), damit der Dienst im Auftrag eines autorisierten Benutzers agieren kann.</span><span class="sxs-lookup"><span data-stu-id="863c4-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="863c4-163">Für Clients, die sich bei einem Server authentifizieren, werden Informationen verwendet, die in SPNs enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="863c4-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>
  
1. <span data-ttu-id="863c4-164">Stellen Sie zuerst mit [diesen Anweisungen](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)eine Verbindung mit Azure Active Directory (Azure AD) her.</span><span class="sxs-lookup"><span data-stu-id="863c4-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

2. <span data-ttu-id="863c4-165">Führen Sie diesen Befehl lokal aus, um eine Liste der SFB-Webdienst-URLs zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="863c4-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="863c4-166">Beachten Sie, dass die AppPrincipalId mit beginnt `00000004` .</span><span class="sxs-lookup"><span data-stu-id="863c4-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="863c4-167">Dies entspricht Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="863c4-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="863c4-168">Notieren Sie sich (und Screenshot für einen späteren Vergleich) die Ausgabe dieses Befehls, die eine SE-und WS-URL enthalten wird, aber meistens aus SPNs besteht, die mit beginnen `00000004-0000-0ff1-ce00-000000000000/` .</span><span class="sxs-lookup"><span data-stu-id="863c4-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="863c4-169">Wenn die internen **oder** externen SFB-URLs von lokal fehlen (beispielsweise, https://lyncwebint01.contoso.com und https://lyncwebext01.contoso.com) wir müssen diese spezifischen Einträge zu dieser Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="863c4-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="863c4-170">Stellen Sie sicher, dass Sie  *die Beispiel-URLs* unten durch ihre tatsächlichen URLs in den Befehlen hinzufügen ersetzen!</span><span class="sxs-lookup"><span data-stu-id="863c4-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. <span data-ttu-id="863c4-171">Stellen Sie sicher, dass Ihre neuen Datensätze hinzugefügt wurden, indem Sie den Befehl **Get-MsolServicePrincipal** aus Schritt 2 erneut ausführen und die Ausgabe durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="863c4-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="863c4-172">Vergleichen Sie die Liste oder den Screenshot von before mit der neuen Liste mit SPNs.</span><span class="sxs-lookup"><span data-stu-id="863c4-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="863c4-173">Sie können auch die neue Liste für Ihre Datensätze Screenshot.</span><span class="sxs-lookup"><span data-stu-id="863c4-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="863c4-174">Wenn Sie erfolgreich waren, werden die beiden neuen URLs in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="863c4-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="863c4-175">In unserem Beispiel enthält die Liste der SPNs nun die spezifischen URLs https://lyncwebint01.contoso.com und https://lyncwebext01.contoso.com/ .</span><span class="sxs-lookup"><span data-stu-id="863c4-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="863c4-176">Erstellen des EvoSTS-Authentifizierungs Server Objekts</span><span class="sxs-lookup"><span data-stu-id="863c4-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="863c4-177">Führen Sie den folgenden Befehl in der Skype for Business-Verwaltungsshell aus.</span><span class="sxs-lookup"><span data-stu-id="863c4-177">Run the following command in the Skype for Business Management Shell.</span></span>
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="863c4-178">Aktivieren der modernen Hybrid Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="863c4-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="863c4-179">Dies ist der Schritt, bei dem MA tatsächlich aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="863c4-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="863c4-180">Alle vorherigen Schritte können vorzeitig ausgeführt werden, ohne dass der Client Authentifizierungs Fluss geändert wird.</span><span class="sxs-lookup"><span data-stu-id="863c4-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="863c4-181">Wenn Sie den Authentifizierungs Fluss ändern möchten, führen Sie diesen Befehl in der Skype for Business-Verwaltungsshell aus.</span><span class="sxs-lookup"><span data-stu-id="863c4-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="863c4-182">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="863c4-182">Verify</span></span>

<span data-ttu-id="863c4-183">Nachdem Sie HMA aktiviert haben, verwendet die nächste Anmeldung eines Clients den neuen auth-Fluss.</span><span class="sxs-lookup"><span data-stu-id="863c4-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="863c4-184">Beachten Sie, dass durch das Aktivieren von HMA keine erneute Authentifizierung für einen beliebigen Client ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="863c4-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="863c4-185">Die Clients werden basierend auf der Lebensdauer der Authentifizierungstoken und/oder certs, die Sie besitzen, erneut authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="863c4-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="863c4-186">Um zu testen, ob HMA funktioniert, nachdem Sie es aktiviert haben, melden Sie sich bei einem Windows-Client für die Test-SFB an, und klicken Sie auf "Meine Anmeldeinformationen löschen".</span><span class="sxs-lookup"><span data-stu-id="863c4-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="863c4-187">Melden Sie sich erneut an.</span><span class="sxs-lookup"><span data-stu-id="863c4-187">Sign in again.</span></span> <span data-ttu-id="863c4-188">Der Client sollte jetzt den modernen auth-Fluss verwenden, und Ihre Anmeldung enthält nun eine **Office 365** Eingabeaufforderung für ein "Geschäfts-oder Schulkonto", das Sie direkt sehen, bevor der Client den Server kontaktiert und Sie angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="863c4-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>
  
<span data-ttu-id="863c4-189">Sie sollten auch die "Konfigurationsinformationen" für Skype for Business Clients für eine "OAuth Authority" überprüfen.</span><span class="sxs-lookup"><span data-stu-id="863c4-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="863c4-190">Um dies auf dem Clientcomputer zu tun, halten Sie die STRG-Taste gleichzeitig mit der rechten Maustaste auf das Symbol Skype for Business in der Windows-Benachrichtigungsleiste.</span><span class="sxs-lookup"><span data-stu-id="863c4-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="863c4-191">Klicken Sie im angezeigten Menü auf **Konfigurationsinformationen** .</span><span class="sxs-lookup"><span data-stu-id="863c4-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="863c4-192">Suchen Sie im Fenster "Skype for Business Konfigurationsinformationen", das auf dem Desktop angezeigt wird, nach folgendem:</span><span class="sxs-lookup"><span data-stu-id="863c4-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>
  
![Die Konfigurationsinformationen eines Skype for Business Clients mit moderner Authentifizierung zeigen eine lync-und EWS-OAUTH-Autoritäts-URL von an https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
<span data-ttu-id="863c4-194">Sie sollten auch die STRG-Taste gleichzeitig gedrückt halten, indem Sie mit der rechten Maustaste auf das Symbol für den Outlook-Client (auch im Windows-Benachrichtigungs Fach) klicken und auf "Verbindungs Status" klicken.</span><span class="sxs-lookup"><span data-stu-id="863c4-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="863c4-195">Suchen Sie die SMTP-Adresse des Clients anhand eines authn-Typs von "Bearer \* ", der das in OAuth verwendete Bearer-Token darstellt.</span><span class="sxs-lookup"><span data-stu-id="863c4-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="863c4-196">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="863c4-196">Related articles</span></span>

<span data-ttu-id="863c4-197">[Link zurück zur modernen Authentifizierung (Übersicht](hybrid-modern-auth-overview.md)).</span><span class="sxs-lookup"><span data-stu-id="863c4-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>
  
<span data-ttu-id="863c4-198">Müssen Sie wissen, wie Sie die moderne Authentifizierung (Adal) für Ihre Skype for Business Clients verwenden können?</span><span class="sxs-lookup"><span data-stu-id="863c4-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="863c4-199">Wir haben [hier](https://technet.microsoft.com/library/mt710548.aspx)Schritte.</span><span class="sxs-lookup"><span data-stu-id="863c4-199">We've got steps [here](https://technet.microsoft.com/library/mt710548.aspx).</span></span>
