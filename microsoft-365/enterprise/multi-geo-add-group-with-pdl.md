---
title: Erstellen einer Microsoft 365 gruppe mit einem bestimmten bevorzugten Datenspeicherort
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Erfahren Sie, wie Sie Microsoft 365 gruppe mit einem angegebenen bevorzugten Datenspeicherort in einer Multi-Geo-Umgebung erstellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41984dc24e0f30e5e7b7eb0f9672c75b6d65388f
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086824"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a><span data-ttu-id="1fe3c-103">Erstellen einer Microsoft 365 gruppe mit einem bestimmten bevorzugten Datenspeicherort</span><span class="sxs-lookup"><span data-stu-id="1fe3c-103">Create a Microsoft 365 Group with a specific preferred data location</span></span>

<span data-ttu-id="1fe3c-104">Wenn Benutzer in einer Multi-Geo-Umgebung eine Microsoft 365 erstellen, wird der bevorzugte Datenspeicherort (PDL) der Gruppe automatisch auf den des Benutzers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location (PDL) is automatically set to that of the user.</span></span> <span data-ttu-id="1fe3c-105">Globale, SharePoint- und Exchange-Administratoren können Gruppen in jeder ausgewählten Region erstellen.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="1fe3c-106">Wenn Sie eine Gruppe mit einem bestimmten PLD erstellen möchten, können Sie dies über das SharePoint Admin Center oder unter Verwendung des Exchange Online New-UnifiedGroup Microsoft PowerShell-Cmdlets vornehmen.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="1fe3c-107">Wenn Sie dies tun, werden das zugewiesene Gruppenpostfach und die SharePoint-Website für die Gruppe der angegebenen Verteilerliste an diesem bestimmten PLD bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="1fe3c-108">Um eine Microsoft 365 gruppe mit der angegebenen PDL zu erstellen, wechseln Sie zum SharePoint Admin Center am geografischen Standort, an dem Sie die Gruppenwebsite erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="1fe3c-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1fe3c-109">For example:</span></span>

<span data-ttu-id="1fe3c-110">Wenn Sie eine Gruppenwebsite an Ihrem Standort in Australien erstellen möchten, wechseln Sie zu https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="1fe3c-111">Wählen Sie **+ Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="1fe3c-112">Führen Sie den Vorgang zum Erstellen einer Gruppenwebsite aus.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="1fe3c-113">Ihre Gruppenwebsite wird an dem geografischen Standort bereitgestellt, der dem SharePoint Admin Center entspricht, von dem aus Sie die Anforderung für die Websiteerstellung initiiert haben.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="1fe3c-114">Verwenden von Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fe3c-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="1fe3c-115">Stellen Sie eine Verbindung zu Exchange Online PowerShell her, und geben Sie den Parameter *-MailBoxRegion* mit dem Code des geografischen Standorts weiter.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="1fe3c-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1fe3c-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Screenshot des New-UnifiedGroup PowerShell cmdlet mit Syntax](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="1fe3c-118">Beachten Sie, dass die Bereitstellung von SharePoint-Gruppenseiten nach Bedarf erfolgt.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="1fe3c-119">Die Seite wird bereitgestellt, wenn ein Gruppenbesitzer oder -mitglied zum ersten Mal auf diese zugreift.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="1fe3c-120">Codes für geografische Standorte</span><span class="sxs-lookup"><span data-stu-id="1fe3c-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="1fe3c-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1fe3c-121">Related topics</span></span>

<span data-ttu-id="1fe3c-122">[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1fe3c-122">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)</span></span>
