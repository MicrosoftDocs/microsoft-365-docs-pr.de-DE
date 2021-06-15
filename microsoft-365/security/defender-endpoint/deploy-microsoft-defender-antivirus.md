---
title: Bereitstellen und Aktivieren von Microsoft Defender Antivirus
description: Stellen Sie Microsoft Defender Antivirus zum Schutz Ihrer Endpunkte mit Microsoft Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell-Cmdlets oder WMI bereit.
keywords: bereitstellen, aktivieren, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a847e65adb0402d4c5f98e19424677ccdc1011da
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925743"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="17735-104">Bereitstellen und Aktivieren von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="17735-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="17735-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="17735-105">**Applies to:**</span></span>

- [<span data-ttu-id="17735-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="17735-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="17735-107">Je nach dem verwendeten Verwaltungstool müssen Sie möglicherweise Microsoft Defender Antivirus Schutz explizit aktivieren oder konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="17735-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="17735-108">Anweisungen zum Aktivieren des Schutzes mit Microsoft Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, Active [Directory, Microsoft Azure,](deploy-manage-report-microsoft-defender-antivirus.md#ref2) PowerShell-Cmdlets und Windows-Verwaltungsanweisung (Windows Management Instruction, WMI) finden Sie in der Tabelle unter Bereitstellen, Verwalten und Berichten zu Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="17735-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="17735-109">Einige Szenarien erfordern weitere Anleitungen zur erfolgreichen Bereitstellung oder Konfiguration Microsoft Defender Antivirus Schutzes, z. B. Virtual Desktop Infrastructure (VDI)-Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="17735-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="17735-110">Der verbleibende Artikel in diesem Abschnitt enthält umfassende Ratschläge und bewährte Methoden zum [Einrichten von Microsoft Defender Antivirus auf virtuellen Computern (VMs) in einer VDI- oder RDS-Umgebung (RemoteDesktopdienste).](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="17735-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="17735-111">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="17735-111">Related articles</span></span>

- [<span data-ttu-id="17735-112">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="17735-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="17735-113">Bereitstellen, Verwalten von Updates und Melden von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="17735-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="17735-114">Bereitstellungshandbuch für Microsoft Defender Antivirus in einer VDI-Umgebung (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="17735-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)