---
title: Senden von Inhaltstypen per Push auf einen Hub
description: Lernen wie Inhaltstypen per Push auf einen Hub gesendet wird
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
ms.openlocfilehash: d64dd5ab49d371df075f1044024c12fbf78e265c
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087607"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="2f372-103">Senden von Inhaltstypen per Push auf einen Hub</span><span class="sxs-lookup"><span data-stu-id="2f372-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="2f372-104">Um wichtige Inhaltstypen für SharePoint-Bibliotheken und -Listen durchweg verfügbar zu machen, können Sie sie an die von Ihnen ausgewählten Hubs senden.</span><span class="sxs-lookup"><span data-stu-id="2f372-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="2f372-105">Dadurch werden sie automatisch zu allen neuen Listen und Bibliotheken hinzugefügt, die auf den mit dem Hub verknüpften Sites erstellt wurden, sowie zu allen neuen Sites, die dem Hub hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="2f372-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="2f372-106">Damit diese Funktion funktioniert, müssen die geposteten Inhaltstypen bereits veröffentlicht sein.</span><span class="sxs-lookup"><span data-stu-id="2f372-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="2f372-107">So übertragen Sie Inhaltstypen auf Hubs</span><span class="sxs-lookup"><span data-stu-id="2f372-107">To push content types to hubs</span></span>

1. <span data-ttu-id="2f372-108">Erweitern Sie im SharePoint Admin Center **Inhaltsdienste**, und klicken Sie dann auf **Inhaltstyp-Galerie**.</span><span class="sxs-lookup"><span data-stu-id="2f372-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="2f372-109">Klicken Sie auf den Inhaltstyp, den Sie an Hubs senden möchten.</span><span class="sxs-lookup"><span data-stu-id="2f372-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="2f372-110">Klicken Sie in der Befehlsleiste auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2f372-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="2f372-111">Klicken Sie auf **Hub-Sites auswählen**.</span><span class="sxs-lookup"><span data-stu-id="2f372-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="2f372-112">Wählen Sie die gewünschten Hub-Sites aus und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f372-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="2f372-113">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2f372-113">Click **Save**.</span></span>

<span data-ttu-id="2f372-114">Wenn Sie einen Inhaltstyp zum ersten Mal auf einen vorhandenen Hub und die vorhandenen zugeordneten Sites übertragen, kann es bis zu einer Stunde dauern, bis die Einstellungen auf der Site aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2f372-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="2f372-115">Neue Zuordnungen zum Hub erfordern diese Wartezeit nicht und die Einstellungen werden in wenigen Minuten wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="2f372-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="2f372-116">Sobald dies konfiguriert ist, ist der Inhaltstyp mit diesen Einstellungen in wenigen Minuten auf jeder neu mit dem Hub verknüpften Site verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2f372-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="2f372-117">Sobald eine neue Liste oder Bibliothek erstellt wurde, wird der Inhaltstyp innerhalb weniger Minuten nach der Erstellung automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2f372-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="2f372-118">Ein übertragener Inhaltstyp wird einer Dokumentbibliothek nur hinzugefügt, wenn er direkt oder indirekt vom Dokumentinhaltstyp abgeleitet ist, und ein Inhaltstyp wird nur dann zu einer Liste hinzugefügt, wenn er nicht direkt oder indirekt vom Dokumentinhaltstyp abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="2f372-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f372-119">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="2f372-119">See also</span></span>



  






