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
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 89c03a70da364bd4b945debc64de02255dec15e1
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975715"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="2792d-103">Senden von Inhaltstypen per Push auf einen Hub</span><span class="sxs-lookup"><span data-stu-id="2792d-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="2792d-104">Um wichtige Inhaltstypen für SharePoint-Bibliotheken und -Listen durchweg verfügbar zu machen, können Sie sie an die von Ihnen ausgewählten Hubs senden.</span><span class="sxs-lookup"><span data-stu-id="2792d-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="2792d-105">Durch das Senden der Inhaltstypen per Push werden sie automatisch zu allen neuen Listen und Bibliotheken hinzugefügt, die auf den mit dem Hub verknüpften Sites erstellt wurden, sowie zu allen neuen Sites, die dem Hub hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="2792d-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="2792d-106">Damit diese Funktion funktioniert, müssen die geposteten Inhaltstypen bereits veröffentlicht sein.</span><span class="sxs-lookup"><span data-stu-id="2792d-106">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="2792d-107">So übertragen Sie Inhaltstypen auf Hubs</span><span class="sxs-lookup"><span data-stu-id="2792d-107">To push content types to hubs</span></span>

1. <span data-ttu-id="2792d-108">Erweitern Sie im SharePoint Admin Center **Inhaltsdienste**, und wählen Sie dann **Inhaltstyp-Galerie** aus.</span><span class="sxs-lookup"><span data-stu-id="2792d-108">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="2792d-109">Wählen Sie den Inhaltstyp aus, den Sie an Hubs senden möchten.</span><span class="sxs-lookup"><span data-stu-id="2792d-109">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="2792d-110">Wählen Sie in der Befehlsleiste **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="2792d-110">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="2792d-111">Wählen Sie **Hubwebsites auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="2792d-111">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="2792d-112">Wählen Sie die gewünschten Hubwebsites aus, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="2792d-112">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="2792d-113">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="2792d-113">Choose **Save**.</span></span>

<span data-ttu-id="2792d-114">Wenn Sie einen Inhaltstyp zum ersten Mal auf einen vorhandenen Hub und die vorhandenen zugeordneten Sites übertragen, kann es bis zu einer Stunde dauern, bis die Einstellungen auf der Site aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2792d-114">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="2792d-115">Neue Zuordnungen zum Hub erfordern diese Wartezeit nicht und die Einstellungen werden in wenigen Minuten wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="2792d-115">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="2792d-116">Nachdem die Einstellungen aktualisiert wurden, ist der Inhaltstyp mit diesen Einstellungen in wenigen Minuten auf jeder neu mit dem Hub verknüpften Site verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2792d-116">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="2792d-117">Dann wird jeder neu erstellten Liste oder Bibliothek der Inhaltstyp innerhalb weniger Minuten nach der Erstellung automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2792d-117">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="2792d-118">Ein übertragener Inhaltstyp wird einer Dokumentbibliothek nur hinzugefügt, wenn er direkt oder indirekt vom Dokumentinhaltstyp abgeleitet ist, und ein Inhaltstyp wird nur dann zu einer Liste hinzugefügt, wenn er nicht direkt oder indirekt vom Dokumentinhaltstyp abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="2792d-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="2792d-119">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="2792d-119">See also</span></span>
