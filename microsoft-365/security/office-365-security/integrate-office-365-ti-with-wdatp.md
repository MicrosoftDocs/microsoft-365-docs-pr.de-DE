---
title: Integration Office 365 Advanced Threat Protection mit Microsoft Defender Advanced Threat Protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integrieren Sie Office 365 Advanced Threat Protection mit Microsoft Defender Advanced Threat Protection, um detaillierte Informationen zur Bedrohungs Verwaltung zu erhalten.
ms.openlocfilehash: fc2db4c1a3e5b32206ee91cae9f5adbeae4875d4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599132"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="c5d43-103">Integration Office 365 Advanced Threat Protection mit Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c5d43-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="c5d43-104">Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind, können Sie [Office 365 Advanced Threat Protection](office-365-atp.md) und zugehörige Ermittlungs-und Antwortfunktionen mit [Advanced Threat Protection von Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)integrieren.</span><span class="sxs-lookup"><span data-stu-id="c5d43-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="c5d43-105">Dies kann Ihnen helfen, schnell zu verstehen, ob die Computer der Benutzer gefährdet sind, wenn Sie Bedrohungen in Office 365 untersuchen.</span><span class="sxs-lookup"><span data-stu-id="c5d43-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="c5d43-106">Wenn die Integration beispielsweise aktiviert ist, können Sie eine Liste der Computer anzeigen, die von den Empfängern einer erkannten e-Mail-Nachricht verwendet werden, sowie die Anzahl der letzten Warnungen, die diese Computer in Microsoft Defender Advanced Threat Protection haben.</span><span class="sxs-lookup"><span data-stu-id="c5d43-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="c5d43-107">Die folgende Abbildung zeigt die Registerkarte **Geräte** , die angezeigt wird, wenn die Microsoft Defender ATP-Integration aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="c5d43-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![Wenn Microsoft Defender ATP aktiviert ist, können Sie eine Liste der Computer mit Warnungen anzeigen.](../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="c5d43-109">In diesem Beispiel können Sie sehen, dass die Empfänger der e-Mail-Nachricht vier Geräte und eine Warnung besitzen.</span><span class="sxs-lookup"><span data-stu-id="c5d43-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="c5d43-110">Wenn Sie auf den Link für ein Gerät klicken, wird seine Seite im Sicherheits Center von Microsoft Defender geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c5d43-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="c5d43-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5d43-111">Requirements</span></span>

- <span data-ttu-id="c5d43-112">Ihre Organisation muss Office 365 ATP-Plan 2 (oder Office 365 E5) und Microsoft Defender ATP haben.</span><span class="sxs-lookup"><span data-stu-id="c5d43-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="c5d43-113">Sie müssen ein Office 365 globaler Administrator sein oder über eine Sicherheitsadministrator Rolle (beispielsweise Sicherheitsadministrator) verfügen, die [im &amp; Security Compliance Center](https://protection.office.com)zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c5d43-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="c5d43-114">(Siehe [Berechtigungen im Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="c5d43-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="c5d43-115">Sie müssen sowohl im Sicherheits #a0 Compliance Center als auch im Sicherheitscenter von Microsoft Defender Zugriff auf beide [Explorer-(oder Echt Zeit Erkennungen)](threat-explorer.md) haben.</span><span class="sxs-lookup"><span data-stu-id="c5d43-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="c5d43-116">So integrieren Sie Office 365 ATP mit Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="c5d43-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="c5d43-117">Die Integration von Office 365 ATP mit Microsoft Defender ATP wird mithilfe des Security #a0 Compliance Centers und des Sicherheitscenters von Microsoft Defender eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="c5d43-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="c5d43-118">Wechseln Sie als globaler Office 365 Administrator oder Sicherheitsadministrator zu [https://protection.office.com](https://protection.office.com) ihrem geschäftlichen oder Schulkonto, und melden Sie sich für Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="c5d43-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span>
    
2. <span data-ttu-id="c5d43-119">Wählen Sie **Threat Management** \> **Explorer**aus.</span><span class="sxs-lookup"><span data-stu-id="c5d43-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="c5d43-120">![Explorer im Menü "Threat Management"](../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="c5d43-120">![Explorer in Threat Management menu](../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="c5d43-121">Wählen Sie in der oberen rechten Ecke des Bildschirms **Einstellungen für WDATP**aus.</span><span class="sxs-lookup"><span data-stu-id="c5d43-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="c5d43-122">Aktivieren Sie im Dialogfeld Windows Defender ATP Connection die Option Connect to Windows ATP.</span><span class="sxs-lookup"><span data-stu-id="c5d43-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Microsoft Defender ATP-Verbindung](../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="c5d43-124">Aktivieren Sie die Verbindung im Sicherheits Center von Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c5d43-124">Enable the connection in the Microsoft Defender Security Center.</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="c5d43-125">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c5d43-125">Related topics</span></span>

[<span data-ttu-id="c5d43-126">Untersuchung und Reaktion der Office 365 Bedrohung</span><span class="sxs-lookup"><span data-stu-id="c5d43-126">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)
  
[<span data-ttu-id="c5d43-127">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c5d43-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

