---
title: Konfigurieren von Attack Surface Reduction-Funktionen
description: Verwenden Sie Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell-Cmdlets und Gruppenrichtlinien, um die Verringerung der Angriffsfläche zu konfigurieren.
keywords: asr, Attack Surface Reduction, Windows Defender, Microsoft Defender, Antivirus, AV
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: d2f984e21338e2f9a4ed579cde2d74339031d649
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770961"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="59f4e-104">Konfigurieren von Attack Surface Reduction-Funktionen</span><span class="sxs-lookup"><span data-stu-id="59f4e-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="59f4e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="59f4e-105">**Applies to:**</span></span>
- [<span data-ttu-id="59f4e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="59f4e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="59f4e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59f4e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="59f4e-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="59f4e-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="59f4e-109">[Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="59f4e-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="59f4e-110">Defender für Endpunkt umfasst mehrere Funktionen zur Verringerung der Angriffsfläche.</span><span class="sxs-lookup"><span data-stu-id="59f4e-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="59f4e-111">Weitere Informationen finden Sie unter ["Übersicht über die Funktionen zur Verringerung der Angriffsfläche".](overview-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="59f4e-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="59f4e-112">Führen Sie die folgenden Schritte aus, um die Verringerung der Angriffsfläche in Ihrer Umgebung zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="59f4e-112">To configure attack surface reduction in your environment, follow these steps:</span></span> 

1. <span data-ttu-id="59f4e-113">[Aktivieren Sie die hardwarebasierte Isolation für Microsoft Edge.](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)</span><span class="sxs-lookup"><span data-stu-id="59f4e-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="59f4e-114">Aktivieren Sie die Anwendungssteuerung.</span><span class="sxs-lookup"><span data-stu-id="59f4e-114">Enable application control.</span></span> 

   1. <span data-ttu-id="59f4e-115">Überprüfen Sie die Basisrichtlinien in Windows.</span><span class="sxs-lookup"><span data-stu-id="59f4e-115">Review base policies in Windows.</span></span> <span data-ttu-id="59f4e-116">Siehe [Beispiel für Basisrichtlinien.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)</span><span class="sxs-lookup"><span data-stu-id="59f4e-116">See [example base policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="59f4e-117">Weitere Informationen finden Sie im [Designhandbuch für Anwendungssteuerelemente.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)</span><span class="sxs-lookup"><span data-stu-id="59f4e-117">See the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="59f4e-118">Weitere Informationen finden Sie im [Designhandbuch für Anwendungssteuerelemente.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="59f4e-118">Refer to the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="59f4e-119">[Aktivieren Sie den kontrollierten Ordnerzugriff.](enable-controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="59f4e-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="59f4e-120">[Aktivieren Sie den Netzwerkschutz.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="59f4e-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="59f4e-121">[Aktivieren Des Exploit-Schutzes.](enable-exploit-protection.md)</span><span class="sxs-lookup"><span data-stu-id="59f4e-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="59f4e-122">[Konfigurieren Sie Regeln zur Verringerung der Angriffsfläche.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="59f4e-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="59f4e-123">Richten Sie Ihre Netzwerkfirewall ein.</span><span class="sxs-lookup"><span data-stu-id="59f4e-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="59f4e-124">Erhalten Sie einen Überblick über [Windows Defender Firewall mit erweiterter Sicherheit.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="59f4e-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="59f4e-125">Verwenden Sie die [Windows Defender Firewall Entwurfshandbuchs,](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) um zu entscheiden, wie Sie Ihre Firewallrichtlinien entwerfen möchten.</span><span class="sxs-lookup"><span data-stu-id="59f4e-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="59f4e-126">Verwenden Sie das [Windows Defender Firewall Bereitstellungshandbuch,](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) um die Firewall Ihrer Organisation mit erweiterter Sicherheit einzurichten.</span><span class="sxs-lookup"><span data-stu-id="59f4e-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span> 

> [!TIP]
> <span data-ttu-id="59f4e-127">In den meisten Fällen können Sie beim Konfigurieren von Attack Surface Reduction-Funktionen zwischen verschiedenen Methoden wählen:</span><span class="sxs-lookup"><span data-stu-id="59f4e-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>
> - <span data-ttu-id="59f4e-128">Microsoft Endpoint Manager (die jetzt Microsoft Intune und Microsoft Endpoint Configuration Manager umfasst)</span><span class="sxs-lookup"><span data-stu-id="59f4e-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="59f4e-129">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="59f4e-129">Group Policy</span></span>
> - <span data-ttu-id="59f4e-130">PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="59f4e-130">PowerShell cmdlets</span></span>
