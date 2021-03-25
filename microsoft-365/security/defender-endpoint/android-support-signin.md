---
title: Behandeln von Problemen mit Microsoft Defender ATP für Android
description: Problembehandlung für Microsoft Defender ATP für Android
keywords: microsoft, defender, atp, android, cloud, connectivity, communication
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 444541c85f8f4416288dcebf4bbee2c65a33d3d2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164869"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="b7c56-104">Problembehandlung bei Microsoft Defender for Endpoint für Android</span><span class="sxs-lookup"><span data-stu-id="b7c56-104">Troubleshooting issues on Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7c56-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b7c56-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7c56-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b7c56-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b7c56-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7c56-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b7c56-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b7c56-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b7c56-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b7c56-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="b7c56-110">Beim Onboarding eines Geräts werden möglicherweise Anmeldeprobleme angezeigt, nachdem die App installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b7c56-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="b7c56-111">Während des Onboardings können Anmeldeprobleme auftreten, nachdem die App auf Ihrem Gerät installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b7c56-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="b7c56-112">Dieser Artikel enthält Lösungen zur Lösung der Anmeldeprobleme.</span><span class="sxs-lookup"><span data-stu-id="b7c56-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="b7c56-113">Anmeldung fehlgeschlagen – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="b7c56-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="b7c56-114">**Anmeldefehler: Unerwarteter** *Fehler, versuchen Sie es später*</span><span class="sxs-lookup"><span data-stu-id="b7c56-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Image of sign in failed error Unerwarteter Fehler](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="b7c56-116">**Nachricht:**</span><span class="sxs-lookup"><span data-stu-id="b7c56-116">**Message:**</span></span>

<span data-ttu-id="b7c56-117">Unerwarteter Fehler, versuchen Sie es später</span><span class="sxs-lookup"><span data-stu-id="b7c56-117">Unexpected error, try later</span></span>

<span data-ttu-id="b7c56-118">**Ursache:**</span><span class="sxs-lookup"><span data-stu-id="b7c56-118">**Cause:**</span></span>

<span data-ttu-id="b7c56-119">Auf Ihrem Gerät ist eine ältere Version der "Microsoft Authenticator"-App installiert.</span><span class="sxs-lookup"><span data-stu-id="b7c56-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="b7c56-120">**Lösung:**</span><span class="sxs-lookup"><span data-stu-id="b7c56-120">**Solution:**</span></span>

<span data-ttu-id="b7c56-121">Installieren Sie die neueste Version und [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) aus dem Google Play Store, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="b7c56-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="b7c56-122">Anmelden fehlgeschlagen – ungültige Lizenz</span><span class="sxs-lookup"><span data-stu-id="b7c56-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="b7c56-123">**Fehlgeschlagene Anmeldung:** *Ungültige Lizenz, wenden Sie sich an den Administrator*</span><span class="sxs-lookup"><span data-stu-id="b7c56-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Image of sign in failed please contact administrator](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="b7c56-125">**Nachricht:** *Ungültige Lizenz, wenden Sie sich an den Administrator.*</span><span class="sxs-lookup"><span data-stu-id="b7c56-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="b7c56-126">**Ursache:**</span><span class="sxs-lookup"><span data-stu-id="b7c56-126">**Cause:**</span></span>

<span data-ttu-id="b7c56-127">Ihnen ist keine Microsoft 365-Lizenz zugewiesen, oder Ihre Organisation verfügt nicht über eine Lizenz für Microsoft 365 Enterprise-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="b7c56-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="b7c56-128">**Lösung:**</span><span class="sxs-lookup"><span data-stu-id="b7c56-128">**Solution:**</span></span>

<span data-ttu-id="b7c56-129">Weitere Informationen erhalten Sie von Ihrem Administrator.</span><span class="sxs-lookup"><span data-stu-id="b7c56-129">Contact your administrator for help.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="b7c56-130">Phishingseiten werden auf einigen OEM-Geräten nicht blockiert</span><span class="sxs-lookup"><span data-stu-id="b7c56-130">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="b7c56-131">**Gilt für:** Nur bestimmte OEMs</span><span class="sxs-lookup"><span data-stu-id="b7c56-131">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="b7c56-132">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="b7c56-132">**Xiaomi**</span></span>

<span data-ttu-id="b7c56-133">Phishing und schädliche Webbedrohungen, die von Defender for Endpoint für Android erkannt werden, werden auf einigen Xiaomi-Geräten nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="b7c56-133">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="b7c56-134">Die folgenden Funktionen funktionieren auf diesen Geräten nicht.</span><span class="sxs-lookup"><span data-stu-id="b7c56-134">The following functionality doesn't work on these devices.</span></span>

![Abbildung der als unsicher gemeldeten Website](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="b7c56-136">**Ursache:**</span><span class="sxs-lookup"><span data-stu-id="b7c56-136">**Cause:**</span></span>

<span data-ttu-id="b7c56-137">Die Geräte von Xiaomi enthalten ein neues Berechtigungsmodell.</span><span class="sxs-lookup"><span data-stu-id="b7c56-137">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="b7c56-138">Dadurch wird verhindert, dass Defender for Endpoint für Android Popupfenster angezeigt wird, während es im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7c56-138">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="b7c56-139">Berechtigung für Die Geräte von Xiaomi: "Popupfenster anzeigen, während sie im Hintergrund ausgeführt werden."</span><span class="sxs-lookup"><span data-stu-id="b7c56-139">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Abbildung der Popupeinstellung](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="b7c56-141">**Lösung:**</span><span class="sxs-lookup"><span data-stu-id="b7c56-141">**Solution:**</span></span>

<span data-ttu-id="b7c56-142">Aktivieren Sie die erforderliche Berechtigung auf Xiaomi-Geräten.</span><span class="sxs-lookup"><span data-stu-id="b7c56-142">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="b7c56-143">Anzeigen von Popupfenstern während der Ausführung im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="b7c56-143">Display pop-up windows while running in the background.</span></span>