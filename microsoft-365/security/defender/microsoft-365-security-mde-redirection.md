---
title: Umleiten von Konten von Microsoft Defender für Endpunkt zu Microsoft 365 Defender
description: So leiten Sie Konten und Sitzungen vom Defender für Endpunkt an Microsoft 365 Defender um.
keywords: Microsoft 365 Defender, Erste Schritte mit Microsoft 365 Defender, Security Center-Umleitung
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
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842566"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a><span data-ttu-id="c9b18-104">Umleiten von Konten von Microsoft Defender für Endpunkt zu Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9b18-104">Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c9b18-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c9b18-105">**Applies to:**</span></span>
- <span data-ttu-id="c9b18-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9b18-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="c9b18-107">Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c9b18-107">Defender for Endpoint</span></span>

<span data-ttu-id="c9b18-108">In Übereinstimmung mit dem domänenübergreifenden Ansatz von Microsoft für den Bedrohungsschutz mit SIEM und erweiterter Erkennung und Reaktion (Extended Detection and Response, XDR) haben wir Microsoft Defender Advanced Threat Protection als Microsoft Defender für Endpunkt umbenennen und in einem einzigen integrierten Portal – Microsoft 365 Defender – vereinheitlicht.</span><span class="sxs-lookup"><span data-stu-id="c9b18-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - Microsoft 365 Defender.</span></span>

<span data-ttu-id="c9b18-109">In diesem Leitfaden wird erläutert, wie Sie Konten an Microsoft 365 Defender weiterleiten, indem Sie die automatische Umleitung vom früheren Microsoft Defender für Endpunkt-Portal (securitycenter.windows.com oder securitycenter.microsoft.com) zu Microsoft 365 Defender-Portal (security.microsoft.com) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c9b18-109">This guide explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to Microsoft 365 Defender portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="c9b18-110">Microsoft Defender für Endpunkt in Microsoft 365 Defender unterstützt das Gewähren des [Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Providers, MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) auf die gleiche Weise, wie der Zugriff [im Microsoft Defender Security Center gewährt](./mssp-access.md)wird.</span><span class="sxs-lookup"><span data-stu-id="c9b18-110">Microsoft Defender for Endpoint in Microsoft 365 Defender supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="c9b18-111">Das erwartet Sie</span><span class="sxs-lookup"><span data-stu-id="c9b18-111">What to expect</span></span>
<span data-ttu-id="c9b18-112">Sobald die automatische Umleitung aktiviert ist, werden Konten, die auf das frühere Microsoft Defender für Endpunkt-Portal unter securitycenter.windows.com oder securitycenter.microsoft.com zugreifen, automatisch an Microsoft 365 Defender-Portal bei security.microsoft.com weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c9b18-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to Microsoft 365 Defender portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="c9b18-113">Erfahren Sie mehr über die Änderungen: [Microsoft Defender für Endpunkt in Microsoft 365 Defender](microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="c9b18-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="c9b18-114">Dazu gehört die Umleitung für den direkten Zugriff auf das frühere Portal über browser, einschließlich Links, die auf das frühere securitycenter.windows.com-Portal verweisen , z. B. Links in E-Mail-Benachrichtigungen und Links, die von SIEM-API-Aufrufen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c9b18-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="c9b18-115">Externe Links von E-Mail-Benachrichtigungen oder SIEM-APIs enthalten derzeit Links zu beiden Portalen.</span><span class="sxs-lookup"><span data-stu-id="c9b18-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="c9b18-116">Sobald die Umleitung aktiviert ist, zeigen beide Links auf Microsoft 365 Defender, bis der alte Link schließlich entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="c9b18-116">Once redirection is enabled, both links will point to Microsoft 365 Defender until the old link is eventually removed.</span></span> <span data-ttu-id="c9b18-117">Wir empfehlen Ihnen, den neuen Link zu übernehmen, der auf Microsoft 365 Defender verweist.</span><span class="sxs-lookup"><span data-stu-id="c9b18-117">We encourage you to adopt the new link pointing to Microsoft 365 Defender.</span></span>

<span data-ttu-id="c9b18-118">Weitere Informationen zu Links und Routing finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c9b18-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="c9b18-119">SIEM-API-Routing</span><span class="sxs-lookup"><span data-stu-id="c9b18-119">SIEM API routing</span></span>

|<span data-ttu-id="c9b18-120">**Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="c9b18-120">**Property**</span></span>  |<span data-ttu-id="c9b18-121">**Ziel, wenn die Umleitung ausgeschaltet ist**</span><span class="sxs-lookup"><span data-stu-id="c9b18-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="c9b18-122">**Ziel bei aktivierter Umleitung**</span><span class="sxs-lookup"><span data-stu-id="c9b18-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="c9b18-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="c9b18-123">LinkToWDATP</span></span> | <span data-ttu-id="c9b18-124">Warnungsseite in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="c9b18-125">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="c9b18-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="c9b18-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="c9b18-127">Vorfallseite in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="c9b18-128">Vorfallseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="c9b18-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="c9b18-129">LinkToMTP</span></span> | <span data-ttu-id="c9b18-130">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="c9b18-131">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="c9b18-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="c9b18-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="c9b18-133">Vorfallseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="c9b18-134">Vorfallseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="c9b18-135">E-Mail-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="c9b18-135">Email alert notifications</span></span>

|<span data-ttu-id="c9b18-136">**Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="c9b18-136">**Property**</span></span>  |<span data-ttu-id="c9b18-137">**Ziel, wenn die Umleitung ausgeschaltet ist**</span><span class="sxs-lookup"><span data-stu-id="c9b18-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="c9b18-138">**Ziel bei aktivierter Umleitung**</span><span class="sxs-lookup"><span data-stu-id="c9b18-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="c9b18-139">Warnungsseite</span><span class="sxs-lookup"><span data-stu-id="c9b18-139">Alert page</span></span>  | <span data-ttu-id="c9b18-140">Warnungsseite in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="c9b18-141">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="c9b18-142">Vorfallseite</span><span class="sxs-lookup"><span data-stu-id="c9b18-142">Incident page</span></span>  |<span data-ttu-id="c9b18-143">Vorfallseite in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="c9b18-144">Vorfallseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="c9b18-145">Seite "Warnung" im Security Center-Portal</span><span class="sxs-lookup"><span data-stu-id="c9b18-145">Alert page in security center portal</span></span> | <span data-ttu-id="c9b18-146">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="c9b18-147">Warnungsseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="c9b18-148">Vorfallseite im Security Center-Portal</span><span class="sxs-lookup"><span data-stu-id="c9b18-148">Incident page in security center portal</span></span> | <span data-ttu-id="c9b18-149">Vorfallseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="c9b18-150">Vorfallseite in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c9b18-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="c9b18-151">Wann wird dies wirksam?</span><span class="sxs-lookup"><span data-stu-id="c9b18-151">When does this take effect?</span></span> 
<span data-ttu-id="c9b18-152">Nach der Aktivierung kann dieses Update für einige Konten fast sofort wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="c9b18-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="c9b18-153">Die Umleitung kann jedoch länger dauern, bis sie an jedes Konto in Ihrer Organisation verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="c9b18-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="c9b18-154">Konten in aktiven Sitzungen, während diese Einstellung angewendet wird, werden nicht aus ihrer Sitzung ejiziert und nur an Microsoft 365 Defender weitergeleitet, nachdem sie ihre aktuelle Sitzung beendet und sich erneut angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="c9b18-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="c9b18-155">Einrichten der Portalumleitung</span><span class="sxs-lookup"><span data-stu-id="c9b18-155">Set up portal redirection</span></span>
<span data-ttu-id="c9b18-156">So starten Sie das Routing von Konten an Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="c9b18-156">To start routing accounts to Microsoft 365 Defender:</span></span>
1. <span data-ttu-id="c9b18-157">Stellen Sie sicher, dass Sie ein globaler Administrator sind oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="c9b18-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="c9b18-158">[Melden Sie sich bei](https://security.microsoft.com/) Microsoft 365 Defender an.</span><span class="sxs-lookup"><span data-stu-id="c9b18-158">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>

3. <span data-ttu-id="c9b18-159">Navigieren Sie zu **Einstellungen**  >  **Allgemeinen**  >    >  **Endpunktportalumleitung,** oder [klicken Sie hier.](https://security.microsoft.com/preferences2/portal_redirection)</span><span class="sxs-lookup"><span data-stu-id="c9b18-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="c9b18-160">Umschalten der Einstellung für die automatische Umleitung auf **"Ein".**</span><span class="sxs-lookup"><span data-stu-id="c9b18-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="c9b18-161">Klicken Sie auf **"Aktivieren",** um die automatische Umleitung auf Microsoft 365 Defender anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="c9b18-161">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c9b18-162">Wenn Sie diese Einstellung aktivieren, werden aktive Benutzersitzungen nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="c9b18-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="c9b18-163">Konten, die sich während der Anwendung dieser Einstellung in einer aktiven Sitzung befinden, werden nur an Microsoft 365 Defender weitergeleitet, nachdem sie ihre aktuelle Sitzung beendet und sich erneut angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="c9b18-163">Accounts who are in an active session while this setting is applied will only be directed to Microsoft 365 Defender after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="c9b18-164">Sie müssen ein globaler Administrator sein oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen, um diese Einstellung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c9b18-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="c9b18-165">Kann ich zum früheren Portal zurückkehren?</span><span class="sxs-lookup"><span data-stu-id="c9b18-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="c9b18-166">Wenn etwas nicht für Sie funktioniert oder wenn Sie etwas nicht über Microsoft 365 Defender abschließen können, möchten wir uns darüber informieren.</span><span class="sxs-lookup"><span data-stu-id="c9b18-166">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it.</span></span> <span data-ttu-id="c9b18-167">Wenn Bei der Umleitung Probleme aufgetreten sind, empfehlen wir Ihnen, uns dies über das Übermittlungsformular für Feedback mitzuteilen.</span><span class="sxs-lookup"><span data-stu-id="c9b18-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="c9b18-168">So kehren Sie zum früheren Microsoft Defender für Endpunkt-Portal zurück:</span><span class="sxs-lookup"><span data-stu-id="c9b18-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="c9b18-169">[Melden Sie sich bei](https://security.microsoft.com/) Microsoft 365 Defender als globaler Administrator oder mithilfe von Sicherheitsadministratorberechtigungen in Azure Active Directory an.</span><span class="sxs-lookup"><span data-stu-id="c9b18-169">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="c9b18-170">Navigieren Sie zu **Einstellungen**  >  **Allgemeinen**  >    >  **Endpunktportalumleitung,** oder öffnen Sie [die Seite hier.](https://security.microsoft.com/preferences2/portal_redirection)</span><span class="sxs-lookup"><span data-stu-id="c9b18-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="c9b18-171">Schalten Sie die Einstellung für die automatische Umleitung auf **"Aus" um.**</span><span class="sxs-lookup"><span data-stu-id="c9b18-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="c9b18-172">Klicken Sie auf **"Deaktivieren** & Feedback teilen", wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c9b18-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="c9b18-173">Diese Einstellung kann jederzeit wieder aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c9b18-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="c9b18-174">Nach der Deaktivierung werden Konten nicht mehr an security.microsoft.com weitergeleitet, und Sie haben erneut Zugriff auf das frühere Portal – securitycenter.windows.com oder securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c9b18-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="c9b18-175">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="c9b18-175">Related information</span></span>
- [<span data-ttu-id="c9b18-176">Microsoft 365 Übersicht über Defender</span><span class="sxs-lookup"><span data-stu-id="c9b18-176">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="c9b18-177">Microsoft Defender für Endpunkt in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9b18-177">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="c9b18-178">Microsoft bietet einheitliche SIEM- und XDR-Lösungen zur Modernisierung von Sicherheitsvorgängen</span><span class="sxs-lookup"><span data-stu-id="c9b18-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="c9b18-179">XDR im Vergleich zu SIEM-Infografik</span><span class="sxs-lookup"><span data-stu-id="c9b18-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="c9b18-180">Der neue Defender</span><span class="sxs-lookup"><span data-stu-id="c9b18-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="c9b18-181">Informationen zu Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9b18-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="c9b18-182">Microsoft-Sicherheitsportale und Admin Center</span><span class="sxs-lookup"><span data-stu-id="c9b18-182">Microsoft security portals and admin centers</span></span>](portals.md)