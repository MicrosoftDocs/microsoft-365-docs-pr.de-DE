---
title: Microsoft Defender Antivirus-Kompatibilität mit Defender for Endpoint
description: Erfahren Sie, wie Windows Defender Microsoft Defender for Endpoint funktioniert und wie es funktioniert, wenn ein Antischalwareclient eines Drittanbieters verwendet wird.
keywords: Windows Defender-Kompatibilität, Defender, Microsoft Defender für Endpoint, Defender für Endpunkt, Antivirus, mde
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
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a8dca4a80385fabcdc64a5584474214d05be4a6c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935377"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="bf830-104">Microsoft Defender Antivirus-Kompatibilität mit Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bf830-104">Microsoft Defender Antivirus compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf830-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bf830-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf830-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bf830-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bf830-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf830-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="bf830-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="bf830-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bf830-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bf830-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="bf830-110">Der Microsoft Defender for Endpoint-Agent ist für einige Funktionen wie die Dateiprüfung von Microsoft Defender Antivirus abhängig.</span><span class="sxs-lookup"><span data-stu-id="bf830-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="bf830-111">Defender for Endpoint hält sich nicht an die Microsoft Defender Antivirus-Ausschlusseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="bf830-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="bf830-112">Sie müssen Sicherheitsintelligenzupdates auf den Defender for Endpoint-Geräten konfigurieren, unabhängig davon, ob Microsoft Defender Antivirus die aktive Antischalware ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="bf830-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="bf830-113">Weitere Informationen finden Sie unter [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="bf830-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="bf830-114">Wenn ein integriertes Gerät durch einen Antischalwareclient eines Drittanbieters geschützt ist, wechselt Microsoft Defender Antivirus auf diesem Endpunkt in den passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="bf830-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="bf830-115">Microsoft Defender Antivirus erhält weiterhin Updates, und der *mspeng.exe-Prozess* wird als ausgeführter Dienst aufgeführt, führt jedoch keine Überprüfungen durch und ersetzt nicht den ausgeführten Antischsoftwareclient eines Drittanbieters.</span><span class="sxs-lookup"><span data-stu-id="bf830-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="bf830-116">Die Microsoft Defender Antivirus-Schnittstelle wird deaktiviert, und Benutzer auf dem Gerät können Microsoft Defender Antivirus nicht verwenden, um Bedarfsscans durchzuführen oder die meisten Optionen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bf830-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="bf830-117">Weitere Informationen finden Sie im [Thema zur Kompatibilität von Microsoft Defender Antivirus und Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="bf830-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
