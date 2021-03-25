---
title: Umleiten von Konten von Microsoft Defender für Endpunkt zum Microsoft 365 Security Center
description: So leiten Sie Konten und Sitzungen vom Defender for Endpoint zum Microsoft 365 Security Center um.
keywords: Microsoft 365 Security Center, Erste Schritte mit dem Microsoft 365 Security Center, Sicherheitscenterumleitung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c993977e0f052a7dc2e7827ff5bdefacee19ac2d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064647"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a><span data-ttu-id="18d9b-104">Umleiten von Konten von Microsoft Defender für Endpunkt zum Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="18d9b-104">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="18d9b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="18d9b-105">**Applies to:**</span></span>
- <span data-ttu-id="18d9b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18d9b-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="18d9b-107">Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="18d9b-107">Defender for Endpoint</span></span>

<span data-ttu-id="18d9b-108">In Übereinstimmung mit dem domänenübergreifenden Ansatz von Microsoft für den Bedrohungsschutz mit SIEM und extended detection and response (XDR) haben wir Microsoft Defender Advanced Threat Protection als Microsoft Defender for Endpoint umbenannt und in einem einzigen integrierten Portal – dem Microsoft 365 Security Center – vereinheitlicht.</span><span class="sxs-lookup"><span data-stu-id="18d9b-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - the Microsoft 365 security center.</span></span>

<span data-ttu-id="18d9b-109">In diesem Handbuch wird erläutert, wie Konten an das Microsoft 365 Security Center geleitet werden, indem die automatische Umleitung vom ehemaligen Microsoft Defender for Endpoint-Portal (securitycenter.windows.com oder securitycenter.microsoft.com) zum Microsoft 365 Security Center-Portal (security.microsoft.com) aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="18d9b-109">This guide explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to the Microsoft 365 security center portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="18d9b-110">Microsoft Defender für Endpunkt im Microsoft 365 Security Center unterstützt [das Gewähren von Zugriff auf verwaltete Sicherheitsdienstanbieter (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in der gleichen Weise, wie der Zugriff [im Microsoft Defender Security Center gewährt wird](./mssp-access.md).</span><span class="sxs-lookup"><span data-stu-id="18d9b-110">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="18d9b-111">Das erwartet Sie</span><span class="sxs-lookup"><span data-stu-id="18d9b-111">What to expect</span></span>
<span data-ttu-id="18d9b-112">Sobald die automatische Umleitung aktiviert ist, werden Konten, die auf das frühere Microsoft Defender for Endpoint-Portal unter securitycenter.windows.com oder securitycenter.microsoft.com zugreifen, automatisch an das Microsoft 365 Security Center-Portal unter security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="18d9b-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to the Microsoft 365 security center portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="18d9b-113">Erfahren Sie mehr über die Geänderten: [Microsoft Defender for Endpoint im Microsoft 365 Security Center](microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="18d9b-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in the Microsoft 365 security center](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="18d9b-114">Dies umfasst die Umleitung für den direkten Zugriff auf das ehemalige Portal über den Browser, einschließlich Links, die auf das frühere securitycenter.windows.com-Portal zeigen – z. B. Links in E-Mail-Benachrichtigungen und Links, die von SIEM-API-Aufrufen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="18d9b-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="18d9b-115">Externe Links von E-Mail-Benachrichtigungen oder SIEM-APIs enthalten derzeit Links zu beiden Portalen.</span><span class="sxs-lookup"><span data-stu-id="18d9b-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="18d9b-116">Sobald die Umleitung aktiviert ist, verweisen beide Links auf das Microsoft 365 Security Center, bis der alte Link schließlich entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="18d9b-116">Once redirection is enabled, both links will point to the Microsoft 365 security center until the old link is eventually removed.</span></span> <span data-ttu-id="18d9b-117">Wir empfehlen Ihnen, den neuen Link zu übernehmen, der auf das Microsoft 365 Security Center verweisen soll.</span><span class="sxs-lookup"><span data-stu-id="18d9b-117">We encourage you to adopt the new link pointing to the Microsoft 365 security center.</span></span>

<span data-ttu-id="18d9b-118">Weitere Informationen zu Links und Routing finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="18d9b-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="18d9b-119">SIEM-API-Routing</span><span class="sxs-lookup"><span data-stu-id="18d9b-119">SIEM API routing</span></span>

|<span data-ttu-id="18d9b-120">**Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="18d9b-120">**Property**</span></span>  |<span data-ttu-id="18d9b-121">**Ziel, wenn die Umleitung DEAKTIVIERT ist**</span><span class="sxs-lookup"><span data-stu-id="18d9b-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="18d9b-122">**Ziel, wenn die Umleitung EIN ist**</span><span class="sxs-lookup"><span data-stu-id="18d9b-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="18d9b-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="18d9b-123">LinkToWDATP</span></span> | <span data-ttu-id="18d9b-124">Warnungsseite in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="18d9b-125">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="18d9b-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="18d9b-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="18d9b-127">Seite "Vorfall" in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="18d9b-128">Seite "Vorfall" in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="18d9b-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="18d9b-129">LinkToMTP</span></span> | <span data-ttu-id="18d9b-130">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="18d9b-131">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="18d9b-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="18d9b-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="18d9b-133">Seite "Vorfall" in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="18d9b-134">Seite "Vorfall" in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="18d9b-135">E-Mail-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="18d9b-135">Email alert notifications</span></span>

|<span data-ttu-id="18d9b-136">**Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="18d9b-136">**Property**</span></span>  |<span data-ttu-id="18d9b-137">**Ziel, wenn die Umleitung DEAKTIVIERT ist**</span><span class="sxs-lookup"><span data-stu-id="18d9b-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="18d9b-138">**Ziel, wenn die Umleitung EIN ist**</span><span class="sxs-lookup"><span data-stu-id="18d9b-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="18d9b-139">Warnungsseite</span><span class="sxs-lookup"><span data-stu-id="18d9b-139">Alert page</span></span>  | <span data-ttu-id="18d9b-140">Warnungsseite in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="18d9b-141">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="18d9b-142">Seite "Vorfälle"</span><span class="sxs-lookup"><span data-stu-id="18d9b-142">Incident page</span></span>  |<span data-ttu-id="18d9b-143">Seite "Vorfall" in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="18d9b-144">Seite "Vorfall" in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="18d9b-145">Warnungsseite im Security Center-Portal</span><span class="sxs-lookup"><span data-stu-id="18d9b-145">Alert page in security center portal</span></span> | <span data-ttu-id="18d9b-146">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="18d9b-147">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="18d9b-148">Seite "Vorfall" im Security Center-Portal</span><span class="sxs-lookup"><span data-stu-id="18d9b-148">Incident page in security center portal</span></span> | <span data-ttu-id="18d9b-149">Seite "Vorfall" in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="18d9b-150">Seite "Vorfall" in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9b-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="18d9b-151">Wann wird dies wirksam?</span><span class="sxs-lookup"><span data-stu-id="18d9b-151">When does this take effect?</span></span> 
<span data-ttu-id="18d9b-152">Sobald diese Option aktiviert ist, kann dieses Update für einige Konten fast sofort wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="18d9b-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="18d9b-153">Die Umleitung kann jedoch länger dauern, bis sie auf jedes Konto in Ihrer Organisation übergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="18d9b-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="18d9b-154">Konten in aktiven Sitzungen, während diese Einstellung angewendet wird, werden nicht aus ihrer Sitzung entfernt und nur an das Microsoft 365 Security Center geroutet, nachdem ihre aktuelle Sitzung beendet und sich erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="18d9b-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="18d9b-155">Einrichten der Portalumleitung</span><span class="sxs-lookup"><span data-stu-id="18d9b-155">Set up portal redirection</span></span>
<span data-ttu-id="18d9b-156">So starten Sie das Routing von Konten an das Microsoft 365 Security Center:</span><span class="sxs-lookup"><span data-stu-id="18d9b-156">To start routing accounts to the Microsoft 365 security center:</span></span>
1. <span data-ttu-id="18d9b-157">Stellen Sie sicher, dass Sie ein globaler Administrator sind oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="18d9b-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="18d9b-158">[Melden Sie sich](https://security.microsoft.com/) beim Microsoft 365 Security Center an.</span><span class="sxs-lookup"><span data-stu-id="18d9b-158">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>

3. <span data-ttu-id="18d9b-159">Navigieren Sie zu **Einstellungen**  >    >  **Endpunkte Allgemeine**  >  **Portalumleitung,** oder [klicken Sie hier](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="18d9b-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="18d9b-160">Umschalten der Einstellung Automatische Umleitung auf **Ein**.</span><span class="sxs-lookup"><span data-stu-id="18d9b-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="18d9b-161">Klicken **Sie auf Aktivieren,** um die automatische Umleitung auf das Microsoft 365 Security Center-Portal anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="18d9b-161">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

>[!IMPORTANT]
><span data-ttu-id="18d9b-162">Wenn Sie diese Einstellung aktivieren, werden aktive Benutzersitzungen nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="18d9b-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="18d9b-163">Konten, die sich in einer aktiven Sitzung befinden, während diese Einstellung angewendet wird, werden nur an das Microsoft 365 Security Center geleitet, nachdem sie ihre aktuelle Sitzung beendet und sich erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="18d9b-163">Accounts who are in an active session while this setting is applied will only be directed to the Microsoft 365 security center after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="18d9b-164">Sie müssen ein globaler Administrator sein oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen, um diese Einstellung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="18d9b-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="18d9b-165">Kann ich wieder auf das frühere Portal zugreifen?</span><span class="sxs-lookup"><span data-stu-id="18d9b-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="18d9b-166">Wenn etwas nicht für Sie funktioniert oder wenn sie nicht über das Microsoft 365 Security Center-Portal abgeschlossen werden können, möchten wir darüber erfahren.</span><span class="sxs-lookup"><span data-stu-id="18d9b-166">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it.</span></span> <span data-ttu-id="18d9b-167">Wenn Probleme mit der Umleitung aufgetreten sind, empfehlen wir Ihnen, uns dies mithilfe des Feedback-Übermittlungsformulars zu sagen.</span><span class="sxs-lookup"><span data-stu-id="18d9b-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="18d9b-168">So kehren Sie zum früheren Microsoft Defender for Endpoint-Portal zurück:</span><span class="sxs-lookup"><span data-stu-id="18d9b-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="18d9b-169">[Melden Sie](https://security.microsoft.com/) sich beim Microsoft 365 Security Center als globaler Administrator an oder verwenden Und Konto mit Sicherheitsadministratorberechtigungen in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="18d9b-169">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="18d9b-170">Navigieren Sie zu **Einstellungen**  >    >  **Endpunkte Allgemeine**  >  **Portalumleitung,** [oder öffnen Sie die Seite hier](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="18d9b-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="18d9b-171">Umschalten der Einstellung Automatische Umleitung auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="18d9b-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="18d9b-172">Klicken **Sie auf &** feedback deaktivieren, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="18d9b-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="18d9b-173">Diese Einstellung kann jederzeit wieder aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="18d9b-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="18d9b-174">Nach dem Deaktivieren werden Konten nicht mehr an security.microsoft.com, und Sie haben erneut Zugriff auf das frühere Portal - securitycenter.windows.com oder securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="18d9b-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="18d9b-175">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="18d9b-175">Related information</span></span>
- [<span data-ttu-id="18d9b-176">Microsoft 365 Security Center – Übersicht</span><span class="sxs-lookup"><span data-stu-id="18d9b-176">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="18d9b-177">Microsoft Defender für Endpunkt im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="18d9b-177">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="18d9b-178">Microsoft bietet einheitliches SIEM und XDR zur Modernisierung von Sicherheitsvorgängen</span><span class="sxs-lookup"><span data-stu-id="18d9b-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="18d9b-179">XDR- und SIEM-Infografik</span><span class="sxs-lookup"><span data-stu-id="18d9b-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="18d9b-180">Der neue Defender</span><span class="sxs-lookup"><span data-stu-id="18d9b-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="18d9b-181">Informationen zu Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18d9b-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="18d9b-182">Microsoft-Sicherheitsportale und Admin Center</span><span class="sxs-lookup"><span data-stu-id="18d9b-182">Microsoft security portals and admin centers</span></span>](portals.md)