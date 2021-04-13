---
title: Konfigurieren von Microsoft Defender Antivirus mit WMI
description: Erfahren Sie, wie Sie Microsoft Defender Antivirus mithilfe von WMI-Skripts konfigurieren und verwalten, um Einstellungen in Microsoft Defender for Endpoint abzurufen, zu ändern und zu aktualisieren.
keywords: wmi, scripts, windows management instrumentation, configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8d24a08ae3b8db710ca1727821690e5c87f056c3
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690532"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="ae874-104">Konfigurieren und Verwalten von Microsoft Defender Antivirus mithilfe von Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="ae874-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ae874-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ae874-105">**Applies to:**</span></span>

- [<span data-ttu-id="ae874-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ae874-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ae874-107">Windows Management Instrumentation (WMI) ist eine Skriptschnittstelle, mit der Sie Einstellungen abrufen, ändern und aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="ae874-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="ae874-108">Weitere Informationen zu WMI finden Sie in der [Microsoft Developer Network System Administration Library](/windows/win32/wmisdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="ae874-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="ae874-109">Microsoft Defender Antivirus verfügt über eine Reihe spezifischer WMI-Klassen, die zum Ausführen der meisten der gleichen Funktionen wie Gruppenrichtlinien und andere Verwaltungstools verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ae874-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="ae874-110">Viele der Klassen sind mit [Defender PowerShell-Cmdlets vergleichbar.](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ae874-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="ae874-111">Die [MSDN Windows Defender WMIv2-Anbieterreferenzbibliothek](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) listet die verfügbaren WMI-Klassen für Microsoft Defender Antivirus auf und enthält Beispielskripts.</span><span class="sxs-lookup"><span data-stu-id="ae874-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="ae874-112">Mit WMI vorgenommene Änderungen wirken sich auf lokale Einstellungen auf dem Endpunkt aus, an dem die Änderungen bereitgestellt oder vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="ae874-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="ae874-113">Dies bedeutet, dass Bereitstellungen von Richtlinien mit Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Microsoft Intune mit WMI vorgenommene Änderungen überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="ae874-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="ae874-114">Sie können [konfigurieren, welche Einstellungen lokal mit](configure-local-policy-overrides-microsoft-defender-antivirus.md)lokalen Richtlinienüberschreibungen überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="ae874-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae874-115">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ae874-115">Related topics</span></span>

- [<span data-ttu-id="ae874-116">Referenzthemen für Verwaltungs- und Konfigurationstools</span><span class="sxs-lookup"><span data-stu-id="ae874-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ae874-117">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="ae874-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)