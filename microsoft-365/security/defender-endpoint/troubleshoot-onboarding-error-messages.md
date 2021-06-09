---
title: Behandeln von Problemen beim Onboarding und Fehlermeldungen
description: Behandeln von Problemen beim Onboarding und Fehlermeldungen beim Abschließen der Einrichtung von Microsoft Defender für Endpunkt.
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
ms.openlocfilehash: b8e15f27ffe4babe730870fb576980c62cb0fd59
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844034"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="ed794-104">Problembehandlung bei Abonnement- und Portalzugriffsproblemen.</span><span class="sxs-lookup"><span data-stu-id="ed794-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ed794-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ed794-105">**Applies to:**</span></span>
- [<span data-ttu-id="ed794-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ed794-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ed794-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed794-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ed794-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="ed794-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ed794-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ed794-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="ed794-110">Auf dieser Seite finden Sie ausführliche Schritte zur Behandlung von Problemen, die beim Einrichten Ihres Microsoft Defender für Endpunkt-Diensts auftreten können.</span><span class="sxs-lookup"><span data-stu-id="ed794-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="ed794-111">Wenn Sie eine Fehlermeldung erhalten, geben Microsoft Defender Security Center eine ausführliche Erläuterung des Problems an, und es werden relevante Links bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ed794-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="ed794-112">Keine Abonnements gefunden</span><span class="sxs-lookup"><span data-stu-id="ed794-112">No subscriptions found</span></span>

<span data-ttu-id="ed794-113">Wenn Sie beim Zugriff auf Microsoft Defender Security Center eine Meldung **"Keine Abonnements gefunden" erhalten,** bedeutet dies, dass die Azure Active Directory (Azure AD), die zum Anmelden des Benutzers beim Portal verwendet wird, nicht über eine Microsoft Defender für Endpunkt-Lizenz verfügt.</span><span class="sxs-lookup"><span data-stu-id="ed794-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="ed794-114">Mögliche Gründe:</span><span class="sxs-lookup"><span data-stu-id="ed794-114">Potential reasons:</span></span>
- <span data-ttu-id="ed794-115">Die Lizenzen für Windows E5 und Office E5 sind separate Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="ed794-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="ed794-116">Die Lizenz wurde erworben, aber nicht für diese Azure AD-Instanz bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ed794-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="ed794-117">Dies kann ein Lizenzbereitstellungsproblem sein.</span><span class="sxs-lookup"><span data-stu-id="ed794-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="ed794-118">Es kann sein, dass Sie die Lizenz versehentlich für eine andere Microsoft Azure AD bereitgestellt haben als die für die Authentifizierung beim Dienst verwendete Lizenz.</span><span class="sxs-lookup"><span data-stu-id="ed794-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="ed794-119">In beiden Fällen sollten Sie sich an den Microsoft-Support unter [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) oder [Volumenlizenzsupport](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)wenden.</span><span class="sxs-lookup"><span data-stu-id="ed794-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![Abbildung der gefundenen Abonnements](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="ed794-121">Ihr Abonnement ist abgelaufen</span><span class="sxs-lookup"><span data-stu-id="ed794-121">Your subscription has expired</span></span>

<span data-ttu-id="ed794-122">Wenn Sie während des Zugriffs auf Microsoft Defender Security Center erhalten, dass **Ihr Abonnement abgelaufen ist,** ist Ihr Onlinedienstabonnement abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="ed794-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="ed794-123">Das Microsoft Defender für Endpunkt-Abonnement hat wie jedes andere Onlinedienstabonnement ein Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="ed794-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="ed794-124">Sie können die Lizenz jederzeit verlängern oder verlängern.</span><span class="sxs-lookup"><span data-stu-id="ed794-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="ed794-125">Beim Zugriff auf das Portal nach dem Ablaufdatum, an dem ein **Abonnement abgelaufen ist,** wird eine Option zum Herunterladen des Offboarding-Pakets für Geräte angezeigt, falls Sie die Lizenz nicht verlängern möchten.</span><span class="sxs-lookup"><span data-stu-id="ed794-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="ed794-126">Aus Sicherheitsgründen läuft das Paket, das für Offboard-Geräte verwendet wird, 30 Tage nach dem Datum ab, an dem es heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ed794-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="ed794-127">Abgelaufene Offboardingpakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="ed794-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="ed794-128">Beim Herunterladen eines Offboardingpakets werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="ed794-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![Abbildung des abgelaufenen Abonnements](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="ed794-130">Sie sind nicht berechtigt, auf das Portal zuzugreifen</span><span class="sxs-lookup"><span data-stu-id="ed794-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="ed794-131">Wenn Sie erhalten, dass **Sie nicht berechtigt sind, auf das Portal zuzugreifen,** beachten Sie, dass Microsoft Defender für Endpunkt ein Sicherheitsüberwachungs-, Vorfalluntersuchungs- und Reaktionsprodukt ist und daher der Zugriff darauf eingeschränkt und vom Benutzer gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="ed794-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="ed794-132">Weitere Informationen finden Sie unter Zuweisen des [**Benutzerzugriffs auf das Portal.**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="ed794-132">For more information, see, [**Assign user access to the portal**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![Abbildung eines nicht autorisierten Zugriffs auf das Portal](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="ed794-134">Daten sind derzeit in einigen Abschnitten des Portals nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ed794-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="ed794-135">Wenn im Portaldashboard und anderen Abschnitten eine Fehlermeldung angezeigt wird, z. B. "Daten sind derzeit nicht verfügbar":</span><span class="sxs-lookup"><span data-stu-id="ed794-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![Abbildung der Daten, die derzeit nicht verfügbar sind](images/atp-data-not-available.png)

<span data-ttu-id="ed794-137">Sie müssen die `securitycenter.windows.com` und alle darunter befindlichen Unterdomänen zulassen.</span><span class="sxs-lookup"><span data-stu-id="ed794-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="ed794-138">Beispiel: `*.securitycenter.windows.com`.</span><span class="sxs-lookup"><span data-stu-id="ed794-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="ed794-139">Probleme bei der Portalkommunikation</span><span class="sxs-lookup"><span data-stu-id="ed794-139">Portal communication issues</span></span>
<span data-ttu-id="ed794-140">Wenn Probleme beim Zugriff auf das Portal, fehlende Daten oder eingeschränkter Zugriff auf Teile des Portals auftreten, müssen Sie überprüfen, ob die folgenden URLs zulässig und für die Kommunikation geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="ed794-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

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



