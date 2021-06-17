---
title: Konfigurieren der Funktionen zur Verringerung der Angriffsfläche
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
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984448"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="bc6fb-104">Konfigurieren der Funktionen zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="bc6fb-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="bc6fb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bc6fb-105">**Applies to:**</span></span>

- [<span data-ttu-id="bc6fb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bc6fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bc6fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc6fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="bc6fb-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="bc6fb-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="bc6fb-109">[Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="bc6fb-110">Defender für Endpunkt umfasst mehrere Funktionen zur Verringerung der Angriffsfläche.</span><span class="sxs-lookup"><span data-stu-id="bc6fb-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="bc6fb-111">Weitere Informationen finden Sie unter ["Übersicht über die Funktionen zur Verringerung der Angriffsfläche".](overview-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="bc6fb-112">Führen Sie die folgenden Schritte aus, um die Verringerung der Angriffsfläche in Ihrer Umgebung zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="bc6fb-112">To configure attack surface reduction in your environment, follow these steps:</span></span>

1. <span data-ttu-id="bc6fb-113">[Aktivieren Sie die hardwarebasierte Isolation für Microsoft Edge.](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="bc6fb-114">Aktivieren Sie die Anwendungssteuerung.</span><span class="sxs-lookup"><span data-stu-id="bc6fb-114">Enable application control.</span></span>

   1. <span data-ttu-id="bc6fb-115">Überprüfen Sie die Basisrichtlinien in Windows.</span><span class="sxs-lookup"><span data-stu-id="bc6fb-115">Review base policies in Windows.</span></span> <span data-ttu-id="bc6fb-116">Siehe [Beispiel für Basisrichtlinien.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-116">See [Example Base Policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="bc6fb-117">Weitere Informationen finden Sie im [Entwurfshandbuch für Windows Defender Anwendungssteuerung.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-117">See the [Windows Defender Application Control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="bc6fb-118">Weitere Informationen finden Sie unter [Deploying Windows Defender Application Control (WDAC)-Richtlinien.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-118">Refer to [Deploying Windows Defender Application Control (WDAC) policies](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="bc6fb-119">[Aktivieren Sie den kontrollierten Ordnerzugriff.](enable-controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="bc6fb-120">[Aktivieren Sie den Netzwerkschutz.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="bc6fb-121">[Aktivieren Des Exploit-Schutzes.](enable-exploit-protection.md)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="bc6fb-122">[Konfigurieren Sie Regeln zur Verringerung der Angriffsfläche.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="bc6fb-123">Richten Sie Ihre Netzwerkfirewall ein.</span><span class="sxs-lookup"><span data-stu-id="bc6fb-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="bc6fb-124">Hier erhalten Sie eine Übersicht über [Windows Defender Firewall mit erweiterter Sicherheit.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="bc6fb-125">Verwenden Sie die [Windows Defender Firewall-Entwurfshandbuchs,](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) um zu entscheiden, wie Sie Ihre Firewallrichtlinien entwerfen möchten.</span><span class="sxs-lookup"><span data-stu-id="bc6fb-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="bc6fb-126">Verwenden Sie das [Windows Defender Firewall-Bereitstellungshandbuch,](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) um die Firewall Ihrer Organisation mit erweiterter Sicherheit einzurichten.</span><span class="sxs-lookup"><span data-stu-id="bc6fb-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span>

> [!TIP]
> <span data-ttu-id="bc6fb-127">In den meisten Fällen können Sie beim Konfigurieren von Attack Surface Reduction-Funktionen zwischen verschiedenen Methoden wählen:</span><span class="sxs-lookup"><span data-stu-id="bc6fb-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>

> - <span data-ttu-id="bc6fb-128">Microsoft Endpoint Manager (die jetzt Microsoft Intune und Microsoft Endpoint Configuration Manager umfasst)</span><span class="sxs-lookup"><span data-stu-id="bc6fb-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="bc6fb-129">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="bc6fb-129">Group Policy</span></span>
> - <span data-ttu-id="bc6fb-130">PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="bc6fb-130">PowerShell cmdlets</span></span>
