---
title: Problembehandlung bei Onboardingproblemen und Fehlermeldungen
description: Behandeln von Problemen und Fehlermeldungen beim Onboarding während des Setups von Microsoft Defender for Endpoint.
keywords: Problembehandlung, Problembehandlung, Azure Active Directory, Onboarding, Fehlermeldung, Fehlermeldungen, Microsoft Defender für Endpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 63981d985140858cbbda54a10dc94b30f28131e5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064855"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="e3d60-104">Problembehandlung bei Abonnement- und Portalzugriffsproblemen</span><span class="sxs-lookup"><span data-stu-id="e3d60-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e3d60-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e3d60-105">**Applies to:**</span></span>
- [<span data-ttu-id="e3d60-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e3d60-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e3d60-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3d60-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e3d60-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e3d60-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e3d60-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e3d60-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="e3d60-110">Diese Seite enthält detaillierte Schritte zur Problembehandlung, die beim Einrichten Ihres Microsoft Defender for Endpoint-Diensts auftreten können.</span><span class="sxs-lookup"><span data-stu-id="e3d60-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="e3d60-111">Wenn Sie eine Fehlermeldung erhalten, bietet Microsoft Defender Security Center eine ausführliche Erläuterung dazu, was das Problem ist, und relevante Links werden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e3d60-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="e3d60-112">Keine Abonnements gefunden</span><span class="sxs-lookup"><span data-stu-id="e3d60-112">No subscriptions found</span></span>

<span data-ttu-id="e3d60-113">Wenn Sie beim Zugriff auf Microsoft  Defender Security Center eine Meldung "Keine Abonnements gefunden" erhalten, bedeutet dies, dass das Azure Active Directory (Azure AD), das zum Anmelden des Benutzers beim Portal verwendet wird, keine Microsoft Defender for Endpoint-Lizenz besitzt.</span><span class="sxs-lookup"><span data-stu-id="e3d60-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="e3d60-114">Mögliche Gründe:</span><span class="sxs-lookup"><span data-stu-id="e3d60-114">Potential reasons:</span></span>
- <span data-ttu-id="e3d60-115">Die Lizenzen für Windows E5 und Office E5 sind separate Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="e3d60-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="e3d60-116">Die Lizenz wurde erworben, aber nicht für diese Azure AD-Instanz bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e3d60-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="e3d60-117">Dies kann ein Problem mit der Lizenzbereitstellung sein.</span><span class="sxs-lookup"><span data-stu-id="e3d60-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="e3d60-118">Es könnte sein, dass Sie versehentlich die Lizenz für ein anderes Microsoft Azure AD bereitgestellt haben als die, die für die Authentifizierung im Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e3d60-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="e3d60-119">In beiden Fällen sollten Sie sich an den Microsoft-Support unter [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) oder Volume license support [wenden.](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)</span><span class="sxs-lookup"><span data-stu-id="e3d60-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![Abbildung der nicht gefundenen Abonnements](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="e3d60-121">Ihr Abonnement ist abgelaufen</span><span class="sxs-lookup"><span data-stu-id="e3d60-121">Your subscription has expired</span></span>

<span data-ttu-id="e3d60-122">Wenn Sie beim Zugriff auf Microsoft  Defender Security Center eine Nachricht erhalten, dass Ihr Abonnement abgelaufen ist, ist Ihr Onlinedienstabonnement abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="e3d60-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="e3d60-123">Microsoft Defender for Endpoint-Abonnement hat wie jedes andere Onlinedienstabonnement ein Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="e3d60-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="e3d60-124">Sie können die Lizenz jederzeit verlängern oder erweitern.</span><span class="sxs-lookup"><span data-stu-id="e3d60-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="e3d60-125">Wenn Sie nach ablaufendem  Ablaufdatum auf das Portal zugreifen, wird einer Nachricht, die Ihr Abonnement abgelaufen ist, eine Option zum Herunterladen des Geräte-Offboarding-Pakets angezeigt, falls Sie die Lizenz nicht verlängern möchten.</span><span class="sxs-lookup"><span data-stu-id="e3d60-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="e3d60-126">Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab.</span><span class="sxs-lookup"><span data-stu-id="e3d60-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="e3d60-127">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="e3d60-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="e3d60-128">Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="e3d60-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![Abbildung des abgelaufenen Abonnements](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="e3d60-130">Sie sind nicht autorisiert, auf das Portal zu zugreifen</span><span class="sxs-lookup"><span data-stu-id="e3d60-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="e3d60-131">Wenn Sie ein Produkt erhalten, das Sie nicht autorisiert haben, auf das Portal zu **zugreifen,** beachten Sie, dass Microsoft Defender for Endpoint ein Produkt für die Sicherheitsüberwachung, Die Untersuchung von Vorfällen und Reaktionen ist und daher der Zugriff darauf vom Benutzer eingeschränkt und gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="e3d60-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="e3d60-132">Weitere Informationen finden Sie unter [**Zuweisen von Benutzerzugriff auf das Portal**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="e3d60-132">For more information, see, [**Assign user access to the portal**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![Bild des nicht autorisierten Zugriffsportals](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="e3d60-134">Daten sind derzeit in einigen Abschnitten des Portals nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="e3d60-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="e3d60-135">Wenn im Portaldashboard und in anderen Abschnitten eine Fehlermeldung angezeigt wird, z. B. "Daten sind derzeit nicht verfügbar":</span><span class="sxs-lookup"><span data-stu-id="e3d60-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![Bild der Daten ist derzeit nicht verfügbar](images/atp-data-not-available.png)

<span data-ttu-id="e3d60-137">Sie müssen die und alle Untergeordneten Domänen unter `securitycenter.windows.com` ihr zulassen.</span><span class="sxs-lookup"><span data-stu-id="e3d60-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="e3d60-138">Beispiel: `*.securitycenter.windows.com`.</span><span class="sxs-lookup"><span data-stu-id="e3d60-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="e3d60-139">Probleme mit der Portalkommunikation</span><span class="sxs-lookup"><span data-stu-id="e3d60-139">Portal communication issues</span></span>
<span data-ttu-id="e3d60-140">Wenn Probleme beim Zugriff auf das Portal, fehlende Daten oder eingeschränkter Zugriff auf Teile des Portals auftreten, müssen Sie überprüfen, ob die folgenden URLs für die Kommunikation zulässig und geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="e3d60-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



