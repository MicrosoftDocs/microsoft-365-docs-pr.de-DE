---
title: Gerätenamen
description: Verwalten von Gerätenamen durch Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893890"
---
# <a name="device-names"></a><span data-ttu-id="3d0df-103">Gerätenamen</span><span class="sxs-lookup"><span data-stu-id="3d0df-103">Device names</span></span>

<span data-ttu-id="3d0df-104">Microsoft Managed Desktop verwendet Windows Autopilot, Azure Active Directory und Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="3d0df-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="3d0df-105">Damit diese Dienste nahtlos zusammenarbeiten können, benötigen Geräte konsistente, standardisierte Namen.</span><span class="sxs-lookup"><span data-stu-id="3d0df-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="3d0df-106">Microsoft Managed Desktop wendet ein standardisiertes Namensformat (vom Format *MMD-%RAND11)* an, wenn Geräte registriert sind.</span><span class="sxs-lookup"><span data-stu-id="3d0df-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="3d0df-107">Windows Autopilot weist diese Namen zu.</span><span class="sxs-lookup"><span data-stu-id="3d0df-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="3d0df-108">Weitere Informationen zu Autopilot finden Sie unter [First-run experience with Autopilot und the Enrollment Status Page](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="3d0df-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="3d0df-109">Automatische Namensänderungen</span><span class="sxs-lookup"><span data-stu-id="3d0df-109">Automated name changes</span></span>

<span data-ttu-id="3d0df-110">Wenn ein Gerät später umbenannt wird, wird es von Microsoft Managed Desktop automatisch in einen neuen Namen im standardisierten Format umbenannt.</span><span class="sxs-lookup"><span data-stu-id="3d0df-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="3d0df-111">Dieser Vorgang erfolgt alle vier Stunden.</span><span class="sxs-lookup"><span data-stu-id="3d0df-111">This process occurs every four hours.</span></span> <span data-ttu-id="3d0df-112">Die Namensänderung erfolgt beim nächsten Neustart des Geräts durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3d0df-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d0df-113">Wenn Ihre Umgebung von bestimmten Gerätenamen abhängt (z. B. zur Unterstützung einer bestimmten Netzwerkkonfiguration), sollten Sie optionen untersuchen, um diese Abhängigkeit zu entfernen, bevor Sie sich bei Microsoft Managed Desktop registrieren.</span><span class="sxs-lookup"><span data-stu-id="3d0df-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="3d0df-114">Wenn Sie die Namensabhängigkeit behalten müssen, können Sie eine Anforderung über das [Administratorportal](../working-with-managed-desktop/admin-support.md) senden, um die Umbenennungsfunktion zu deaktivieren und das gewünschte Namensformat zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d0df-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>