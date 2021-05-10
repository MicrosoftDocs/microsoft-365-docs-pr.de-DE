---
title: Umleiten von Konten von Microsoft Defender für Office 365 zum neuen Microsoft 365 Security Center
description: So umleiten Sie von defender for Office 365 zum Microsoft 365 Security Center.
keywords: Microsoft 365 Security Center, Erste Schritte mit Microsoft 365 Security Center, Sicherheitscenterumleitung
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
ms.openlocfilehash: 40d86f9f3a4896bbe788f0a9894a7e08efe3a690
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301728"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="5d70a-104">Umleiten von Konten von Microsoft Defender für Office 365 zum Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="5d70a-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5d70a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5d70a-105">**Applies to:**</span></span>

- <span data-ttu-id="5d70a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d70a-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="5d70a-107">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5d70a-107">Defender for Office 365</span></span>

<span data-ttu-id="5d70a-108">In diesem Artikel wird erläutert, wie Sie Konten an das Microsoft 365 Security Center weiterleiten, indem sie die automatische Umleitung vom ehemaligen Microsoft Security and Compliance Center (protection.office.com oder securitycenter.microsoft.com) zum Microsoft 365 Security Center (security.microsoft.com) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5d70a-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="5d70a-109">Das erwartet Sie</span><span class="sxs-lookup"><span data-stu-id="5d70a-109">What to expect</span></span>
<span data-ttu-id="5d70a-110">Sobald die automatische Umleitung aktiviert und aktiv ist, werden Benutzer, die auf die sicherheitsbezogenen Funktionen in Office 365 Security and Compliance (protection.office.com) zugreifen, automatisch an das Microsoft 365 Security Center ( ) https://security.microsoft.com) geroutet.</span><span class="sxs-lookup"><span data-stu-id="5d70a-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="5d70a-111">Erfahren Sie mehr über die Geänderten: [Microsoft Defender for Office 365 im Microsoft 365 Security Center](microsoft-365-security-center-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="5d70a-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="5d70a-112">Wenn die automatische Umleitung aktiviert ist, werden Benutzer an Microsoft 365 Security Center geroutet, wenn sie Sicherheitsfunktionen im Office 365 Security and Compliance Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d70a-112">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="5d70a-113">Dazu gehören Funktionen im Abschnitt Bedrohungsverwaltung und das Dashboard und Berichte zur Bedrohungsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="5d70a-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="5d70a-114">Elemente im Office 365 Security and Compliance Center, die nicht mit Sicherheit in Zusammenhang stehen, werden nicht an das Microsoft 365 umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="5d70a-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="5d70a-115">Compliancebezogene Elemente finden Sie im Microsoft 365 Compliance Center, und nachrichtenflussbezogene Elemente finden Sie im Exchange Admin Center.</span><span class="sxs-lookup"><span data-stu-id="5d70a-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="5d70a-116">Alle anderen Funktionen, unabhängig davon, ob es sich um compliancebezogene oder funktionen handelt, die beide unterstützen, sind von der Umleitung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="5d70a-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="5d70a-117">Office 365 sicherheitswarnungen werden sowohl im Microsoft 365 Security Center als auch im Office 365 Security and Compliance Center ohne Umleitung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d70a-117">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="5d70a-118">Einrichten der Portalumleitung</span><span class="sxs-lookup"><span data-stu-id="5d70a-118">Set up portal redirection</span></span>
<span data-ttu-id="5d70a-119">So starten Sie das Routing von Konten Microsoft 365 Sicherheitscenter unter security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="5d70a-119">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="5d70a-120">Stellen Sie sicher, dass Sie ein globaler Administrator sind oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="5d70a-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="5d70a-121">[Melden Sie sich](https://security.microsoft.com/) beim Microsoft 365 an.</span><span class="sxs-lookup"><span data-stu-id="5d70a-121">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="5d70a-122">Navigieren Sie **zu Einstellungen**  >  **E-Mail &-Portal-Umleitung**  >  .</span><span class="sxs-lookup"><span data-stu-id="5d70a-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="5d70a-123">Umschalten der Einstellung Automatische Umleitung auf **Ein**.</span><span class="sxs-lookup"><span data-stu-id="5d70a-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="5d70a-124">Klicken **Sie auf Aktivieren,** um die automatische Umleitung auf das Microsoft 365 anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="5d70a-124">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="5d70a-125">Nachdem die Umleitung aktiviert wurde, werden Konten in aktiven Sitzungen, während diese Einstellung angewendet wird, nicht aus ihrer Sitzung entfernt und erst an das Microsoft 365 Security Center geroutet, nachdem ihre aktuelle Sitzung beendet und sich erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="5d70a-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="5d70a-126">Kann ich wieder auf das frühere Portal zugreifen?</span><span class="sxs-lookup"><span data-stu-id="5d70a-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="5d70a-127">Wenn etwas nicht für Sie funktioniert oder wenn sie nicht über das Microsoft 365 Security Center-Portal abgeschlossen werden können, möchten wir über die Portalfeedbackoption darüber erfahren.</span><span class="sxs-lookup"><span data-stu-id="5d70a-127">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="5d70a-128">Wenn Probleme mit der Umleitung aufgetreten sind, empfehlen wir Ihnen, sich direkt über die private Vorschau an Ihren PM-Kumpel zu wenden oder uns über das Feedback-Übermittlungsformular zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="5d70a-128">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="5d70a-129">So kehren Sie zum vorherigen Portal zurück:</span><span class="sxs-lookup"><span data-stu-id="5d70a-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="5d70a-130">[Melden Sie](https://security.microsoft.com/) sich beim Microsoft 365 sicherheitscenter als globaler Administrator an oder verwenden und konto mit Sicherheitsadministratorberechtigungen in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5d70a-130">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="5d70a-131">Navigieren Sie **zu Einstellungen**  >  **Endpoints**  >  **General**  >  **Portal redirection**.</span><span class="sxs-lookup"><span data-stu-id="5d70a-131">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="5d70a-132">Umschalten der Einstellung Automatische Umleitung auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="5d70a-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="5d70a-133">Klicken **Sie auf &** feedback deaktivieren, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="5d70a-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="5d70a-134">Diese Einstellung kann jederzeit wieder aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5d70a-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="5d70a-135">Nach dem Deaktivieren werden Konten nicht mehr an security.microsoft.com, und Sie haben erneut Zugriff auf das frühere Portal - securitycenter.windows.com oder securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5d70a-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="5d70a-136">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="5d70a-136">Related information</span></span>
- [<span data-ttu-id="5d70a-137">Microsoft 365 Security Center – Übersicht</span><span class="sxs-lookup"><span data-stu-id="5d70a-137">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="5d70a-138">Microsoft Defender für Endpunkt im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="5d70a-138">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="5d70a-139">Microsoft bietet einheitliches SIEM und XDR zur Modernisierung von Sicherheitsvorgängen</span><span class="sxs-lookup"><span data-stu-id="5d70a-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="5d70a-140">XDR- und SIEM-Infografik</span><span class="sxs-lookup"><span data-stu-id="5d70a-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="5d70a-141">Der neue Defender</span><span class="sxs-lookup"><span data-stu-id="5d70a-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="5d70a-142">Informationen Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d70a-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="5d70a-143">Microsoft-Sicherheitsportale und Admin Center</span><span class="sxs-lookup"><span data-stu-id="5d70a-143">Microsoft security portals and admin centers</span></span>](portals.md)
