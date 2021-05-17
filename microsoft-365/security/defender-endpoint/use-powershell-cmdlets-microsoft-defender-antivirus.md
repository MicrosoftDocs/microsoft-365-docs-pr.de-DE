---
title: Konfigurieren und Ausführen von Microsoft Defender AV mithilfe von PowerShell-Cmdlets
description: In Windows 10 können Sie PowerShell-Cmdlets zum Ausführen von Scans, Aktualisieren der Sicherheitsintelligenz und Ändern von Einstellungen in Microsoft Defender Antivirus.
keywords: Scan, Befehlszeile, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765299"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="ebaa7-104">Verwenden von PowerShell-Cmdlets zum Konfigurieren und Verwalten von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="ebaa7-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ebaa7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ebaa7-105">**Applies to:**</span></span>

- [<span data-ttu-id="ebaa7-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ebaa7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ebaa7-107">Sie können PowerShell verwenden, um verschiedene Funktionen in Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="ebaa7-108">Ähnlich wie die Eingabeaufforderung oder Befehlszeile ist PowerShell eine aufgabenbasierte Befehlszeilenshell und Skriptsprache, die speziell für die Systemverwaltung entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="ebaa7-109">Weitere Informationen dazu finden Sie im [PowerShell-Hub auf MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="ebaa7-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="ebaa7-110">Eine Liste der Cmdlets mit ihren Funktionen und verfügbaren Parametern finden Sie im [Thema Defender-Cmdlets.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="ebaa7-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="ebaa7-111">PowerShell-Cmdlets sind am nützlichsten in Windows Serverumgebungen, die nicht auf einer grafischen Benutzeroberfläche (GUI) zum Konfigurieren von Software angewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="ebaa7-112">PowerShell-Cmdlets sollten nicht als Ersatz für eine vollständige Netzwerkrichtlinienverwaltungsinfrastruktur verwendet werden, z. B. [Microsoft Endpoint Configuration Manager](/configmgr) [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gruppenrichtlinienverwaltungskonsole oder [Microsoft Defender Antivirus AdMX-Vorlagen](https://www.microsoft.com/download/101445)für Gruppenrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="ebaa7-113">Mit PowerShell vorgenommene Änderungen wirken sich auf lokale Einstellungen auf dem Endpunkt aus, an dem die Änderungen bereitgestellt oder vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="ebaa7-114">Dies bedeutet, dass Bereitstellungen von Richtlinien mit Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Microsoft Intune änderungen überschreiben können, die mit PowerShell vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="ebaa7-115">Sie können [konfigurieren, welche Einstellungen lokal mit](configure-local-policy-overrides-microsoft-defender-antivirus.md)lokalen Richtlinienüberschreibungen überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="ebaa7-116">PowerShell wird in der Regel unter dem Ordner `%SystemRoot%\system32\WindowsPowerShell` installiert.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="ebaa7-117">Verwenden Microsoft Defender Antivirus PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ebaa7-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="ebaa7-118">Geben Sie Windows in der Suchleiste **powershell ein.**</span><span class="sxs-lookup"><span data-stu-id="ebaa7-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="ebaa7-119">Wählen **Windows PowerShell** aus den Ergebnissen aus, um die Schnittstelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="ebaa7-120">Geben Sie den Befehl PowerShell und alle Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="ebaa7-121">Möglicherweise müssen Sie PowerShell im Administratormodus öffnen.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="ebaa7-122">Klicken Sie im Menü Start mit der rechten Maustaste auf das Element, klicken Sie auf Als Administrator **ausführen,** und klicken Sie an der Berechtigungsaufforderung **auf** Ja.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="ebaa7-123">Geben Sie folgendes ein, um die Onlinehilfe für eines der Cmdlets zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="ebaa7-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="ebaa7-124">Lassen Sie den `-online` Parameter weg, um lokal zwischengespeicherte Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ebaa7-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ebaa7-125">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ebaa7-125">Related topics</span></span>

- [<span data-ttu-id="ebaa7-126">Referenzthemen für Verwaltungs- und Konfigurationstools</span><span class="sxs-lookup"><span data-stu-id="ebaa7-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ebaa7-127">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="ebaa7-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="ebaa7-128">Microsoft Defender Antivirus Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ebaa7-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)