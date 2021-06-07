---
title: Kompatibilität von Antivirenlösungen mit Defender für Endpunkt
description: Erfahren Sie, wie Windows Defender mit Microsoft Defender für Endpunkt funktioniert und wie es funktioniert, wenn ein Antischadsoftwareclient eines Drittanbieters verwendet wird.
keywords: Windows Defender-Kompatibilität, Defender, Microsoft Defender für Endpunkt, Defender für Endpunkt, Antivirus, MDE
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782885"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="0ca48-104">Kompatibilität von Antivirenlösungen mit Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0ca48-104">Antivirus solution compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0ca48-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0ca48-105">**Applies to:**</span></span>
- [<span data-ttu-id="0ca48-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0ca48-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0ca48-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ca48-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="0ca48-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="0ca48-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0ca48-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0ca48-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="0ca48-110">Der Microsoft Defender für Endpunkt-Agent hängt von Microsoft Defender Antivirus für einige Funktionen wie die Dateiüberprüfung ab.</span><span class="sxs-lookup"><span data-stu-id="0ca48-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="0ca48-111">Defender für Endpunkt hält sich nicht an die Einstellungen für Microsoft Defender Antivirus Ausschlüsse.</span><span class="sxs-lookup"><span data-stu-id="0ca48-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="0ca48-112">Sie müssen Security Intelligence-Updates auf den Defender für Endpunkt-Geräten unabhängig davon konfigurieren, ob Microsoft Defender Antivirus die aktive Antischadsoftware ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="0ca48-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="0ca48-113">Weitere Informationen finden Sie unter [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen.](manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0ca48-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="0ca48-114">Wenn ein integriertes Gerät durch einen Antischadsoftwareclient eines Drittanbieters geschützt ist, wechselt Microsoft Defender Antivirus auf diesem Endpunkt in den passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="0ca48-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="0ca48-115">Microsoft Defender Antivirus erhalten weiterhin Updates, und der *mspeng.exe* Prozess wird als ausgeführter Dienst aufgeführt, führt jedoch keine Überprüfungen durch und ersetzt nicht den ausgeführten Antischadsoftwareclient eines Drittanbieters.</span><span class="sxs-lookup"><span data-stu-id="0ca48-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="0ca48-116">Die Microsoft Defender Antivirus Schnittstelle wird deaktiviert, und Benutzer auf dem Gerät können Microsoft Defender Antivirus nicht verwenden, um Scans bei Bedarf durchzuführen oder die meisten Optionen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0ca48-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="0ca48-117">Weitere Informationen finden Sie im [Thema Microsoft Defender Antivirus und Defender für Endpunkt-Kompatibilität.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="0ca48-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](microsoft-defender-antivirus-compatibility.md).</span></span>
