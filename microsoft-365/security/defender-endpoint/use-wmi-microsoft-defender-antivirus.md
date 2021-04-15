---
title: Konfigurieren von Microsoft Defender Antivirus mit WMI
description: Erfahren Sie, wie Sie Microsoft Defender Antivirus mithilfe von WMI-Skripts konfigurieren und verwalten, um Einstellungen in Microsoft Defender for Endpoint abzurufen, zu ändern und zu aktualisieren.
keywords: wmi, scripts, windows management instrumentation, configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764063"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="9a85f-104">Konfigurieren und Verwalten von Microsoft Defender Antivirus mithilfe von Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="9a85f-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9a85f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9a85f-105">**Applies to:**</span></span>

- [<span data-ttu-id="9a85f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9a85f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9a85f-107">Windows Management Instrumentation (WMI) ist eine Skriptschnittstelle, mit der Sie Einstellungen abrufen, ändern und aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="9a85f-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="9a85f-108">Weitere Informationen zu WMI finden Sie in der [Microsoft Developer Network System Administration Library](/windows/win32/wmisdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="9a85f-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="9a85f-109">Microsoft Defender Antivirus verfügt über eine Reihe spezifischer WMI-Klassen, die zum Ausführen der meisten der gleichen Funktionen wie Gruppenrichtlinien und andere Verwaltungstools verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9a85f-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="9a85f-110">Viele der Klassen sind mit [Defender PowerShell-Cmdlets vergleichbar.](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9a85f-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="9a85f-111">Die [MSDN Windows Defender WMIv2-Anbieterreferenzbibliothek](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) listet die verfügbaren WMI-Klassen für Microsoft Defender Antivirus auf und enthält Beispielskripts.</span><span class="sxs-lookup"><span data-stu-id="9a85f-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="9a85f-112">Mit WMI vorgenommene Änderungen wirken sich auf lokale Einstellungen auf dem Endpunkt aus, an dem die Änderungen bereitgestellt oder vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="9a85f-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="9a85f-113">Dies bedeutet, dass Bereitstellungen von Richtlinien mit Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Microsoft Intune mit WMI vorgenommene Änderungen überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="9a85f-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="9a85f-114">Sie können [konfigurieren, welche Einstellungen lokal mit](configure-local-policy-overrides-microsoft-defender-antivirus.md)lokalen Richtlinienüberschreibungen überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="9a85f-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a85f-115">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9a85f-115">Related topics</span></span>

- [<span data-ttu-id="9a85f-116">Referenzthemen für Verwaltungs- und Konfigurationstools</span><span class="sxs-lookup"><span data-stu-id="9a85f-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9a85f-117">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="9a85f-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)