---
title: Umleiten von Konten aus Office 365 Security and Compliance Center zum neuen Microsoft 365 Defender
description: Umleiten von Defender für Office 365 zu Microsoft 365 Defender.
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842518"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a><span data-ttu-id="4ceb9-104">Umleiten von Konten aus Office 365 Security and Compliance Center zu Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ceb9-104">Redirecting accounts from Office 365 Security and Compliance Center to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4ceb9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4ceb9-105">**Applies to:**</span></span>

- <span data-ttu-id="4ceb9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ceb9-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="4ceb9-107">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4ceb9-107">Defender for Office 365</span></span>

<span data-ttu-id="4ceb9-108">In diesem Artikel wird erläutert, wie Sie Konten an Microsoft 365 Defender weiterleiten, indem Sie die automatische Umleitung vom früheren Office 365 Security and Compliance Center (protection.office.com) zu Microsoft 365 Defender (security.microsoft.com) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-108">This article explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Office 365 Security and Compliance Center (protection.office.com), to Microsoft 365 Defender (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="4ceb9-109">Das erwartet Sie</span><span class="sxs-lookup"><span data-stu-id="4ceb9-109">What to expect</span></span>
<span data-ttu-id="4ceb9-110">Sobald die automatische Umleitung aktiviert und aktiv ist, werden Benutzer, die auf die sicherheitsrelevanten Funktionen in Office 365 Security and Compliance (protection.office.com) zugreifen, automatisch an Microsoft 365 Defender ( https://security.microsoft.com) weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to Microsoft 365 Defender (https://security.microsoft.com).</span></span>  

<span data-ttu-id="4ceb9-111">Erfahren Sie mehr über die Änderungen: [Microsoft Defender für Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="4ceb9-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="4ceb9-112">Wenn die automatische Umleitung aktiviert ist, werden Benutzer zu Microsoft 365 Defender weitergeleitet, wenn sie Sicherheitsfunktionen im Office 365 Security and Compliance Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-112">With automatic redirection turned on, users will be routed to Microsoft 365 Defender when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="4ceb9-113">Dazu gehören Funktionen im Abschnitt "Bedrohungsverwaltung" und im Dashboard und den Berichten zur Bedrohungsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="4ceb9-114">Elemente im Office 365 Security and Compliance Center, die nicht mit der Sicherheit in Zusammenhang stehen, werden nicht an Microsoft 365 Defender umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to Microsoft 365 Defender.</span></span>

<span data-ttu-id="4ceb9-115">Compliance-bezogene Elemente finden Sie im Microsoft 365 Compliance Center, und nachrichtenflussbezogene Elemente finden Sie im Exchange Admin Center.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="4ceb9-116">Alle anderen Funktionen, sei es Compliance-bezogene Funktionen oder Funktionen, die beide dienste, sind von der Umleitung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="4ceb9-117">Office 365 Sicherheitswarnungen werden sowohl in Microsoft 365 Defender als auch im Office 365 Security and Compliance Center ohne Umleitung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-117">Office 365 security alerts appear in both Microsoft 365 Defender and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="4ceb9-118">Einrichten der Portalumleitung</span><span class="sxs-lookup"><span data-stu-id="4ceb9-118">Set up portal redirection</span></span>
<span data-ttu-id="4ceb9-119">So starten Sie das Routing von Konten an Microsoft 365 Defender bei security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="4ceb9-119">To start routing accounts to Microsoft 365 Defender at security.microsoft.com:</span></span>

1. <span data-ttu-id="4ceb9-120">Stellen Sie sicher, dass Sie ein globaler Administrator sind oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="4ceb9-121">[Melden Sie sich bei](https://security.microsoft.com/) Microsoft 365 Defender an.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-121">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>
3. <span data-ttu-id="4ceb9-122">Navigieren Sie zu **Einstellungen** Umleitung des  >  **E-Mail-&-Portals** für die  >  Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="4ceb9-123">Umschalten der Einstellung für die automatische Umleitung auf **"Ein".**</span><span class="sxs-lookup"><span data-stu-id="4ceb9-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="4ceb9-124">Klicken Sie auf **"Aktivieren",** um die automatische Umleitung auf Microsoft 365 Defender anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-124">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

> [!NOTE]
> <span data-ttu-id="4ceb9-125">Nachdem die Umleitung aktiviert wurde, werden Konten in aktiven Sitzungen, während diese Einstellung angewendet wird, nicht aus ihrer Sitzung ausgeleitet und nur an Microsoft 365 Defender weitergeleitet, nachdem sie ihre aktuelle Sitzung beendet und sich erneut angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="4ceb9-126">Kann ich zum früheren Portal zurückkehren?</span><span class="sxs-lookup"><span data-stu-id="4ceb9-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="4ceb9-127">Wenn etwas nicht für Sie funktioniert oder wenn Sie etwas nicht über Microsoft 365 Defender abschließen können, möchten wir uns über die Feedbackoption des Portals darüber informieren.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-127">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="4ceb9-128">Wenn Bei der Umleitung Probleme aufgetreten sind, teilen Sie uns dies bitte mit.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="4ceb9-129">So kehren Sie zum früheren Portal zurück:</span><span class="sxs-lookup"><span data-stu-id="4ceb9-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="4ceb9-130">[Melden Sie sich bei](https://security.microsoft.com/) Microsoft 365 Defender als globaler Administrator oder mithilfe von Sicherheitsadministratorberechtigungen in Azure Active Directory an.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-130">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="4ceb9-131">Navigieren Sie zu **Einstellungen** Umleitung des  >  **E-Mail-&-Portals** für die  >  Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="4ceb9-132">Schalten Sie die Einstellung für die automatische Umleitung auf **"Aus" um.**</span><span class="sxs-lookup"><span data-stu-id="4ceb9-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="4ceb9-133">Klicken Sie auf **"Deaktivieren** & Feedback teilen", wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="4ceb9-134">Diese Einstellung kann jederzeit wieder aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="4ceb9-135">Nach der Deaktivierung werden Konten nicht mehr an security.microsoft.com weitergeleitet, und Sie haben wieder Zugriff auf das frühere Portal – securitycenter.windows.com oder securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4ceb9-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal—securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="4ceb9-136">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="4ceb9-136">Related information</span></span>
- [<span data-ttu-id="4ceb9-137">Microsoft 365 Übersicht über Defender</span><span class="sxs-lookup"><span data-stu-id="4ceb9-137">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="4ceb9-138">Microsoft Defender für Endpunkt in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ceb9-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="4ceb9-139">Microsoft bietet einheitliche SIEM- und XDR-Lösungen zur Modernisierung von Sicherheitsvorgängen</span><span class="sxs-lookup"><span data-stu-id="4ceb9-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="4ceb9-140">XDR im Vergleich zu SIEM-Infografik</span><span class="sxs-lookup"><span data-stu-id="4ceb9-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="4ceb9-141">Der neue Defender</span><span class="sxs-lookup"><span data-stu-id="4ceb9-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="4ceb9-142">Informationen zu Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ceb9-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="4ceb9-143">Microsoft-Sicherheitsportale und Admin Center</span><span class="sxs-lookup"><span data-stu-id="4ceb9-143">Microsoft security portals and admin centers</span></span>](portals.md)
