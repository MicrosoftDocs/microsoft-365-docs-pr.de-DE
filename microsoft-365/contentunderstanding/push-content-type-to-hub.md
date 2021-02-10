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
ms.openlocfilehash: 22d146b1d376bab134e82ad7d1313cb7881ca45b
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144971"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="3d438-103">Senden von Inhaltstypen per Push auf einen Hub</span><span class="sxs-lookup"><span data-stu-id="3d438-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="3d438-104">Um wichtige Inhaltstypen für SharePoint-Bibliotheken und -Listen durchweg verfügbar zu machen, können Sie sie an die von Ihnen ausgewählten Hubs senden.</span><span class="sxs-lookup"><span data-stu-id="3d438-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="3d438-105">Durch das Senden der Inhaltstypen per Push werden sie automatisch zu allen neuen Listen und Bibliotheken hinzugefügt, die auf den mit dem Hub verknüpften Sites erstellt wurden, sowie zu allen neuen Sites, die dem Hub hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="3d438-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span> <span data-ttu-id="3d438-106">Dieses Feature benötigt eine [SharePoint Syntex](index.md)-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="3d438-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="3d438-107">Damit diese Funktion funktioniert, müssen die geposteten Inhaltstypen bereits veröffentlicht sein.</span><span class="sxs-lookup"><span data-stu-id="3d438-107">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="3d438-108">So übertragen Sie Inhaltstypen auf Hubs</span><span class="sxs-lookup"><span data-stu-id="3d438-108">To push content types to hubs</span></span>

1. <span data-ttu-id="3d438-109">Erweitern Sie im SharePoint Admin Center **Inhaltsdienste**, und wählen Sie dann **Inhaltstyp-Galerie** aus.</span><span class="sxs-lookup"><span data-stu-id="3d438-109">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="3d438-110">Wählen Sie den Inhaltstyp aus, den Sie an Hubs senden möchten.</span><span class="sxs-lookup"><span data-stu-id="3d438-110">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="3d438-111">Wählen Sie in der Befehlsleiste **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="3d438-111">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="3d438-112">Wählen Sie **Hubwebsites auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="3d438-112">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="3d438-113">Wählen Sie die gewünschten Hubwebsites aus, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="3d438-113">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="3d438-114">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="3d438-114">Choose **Save**.</span></span>

<span data-ttu-id="3d438-115">Wenn Sie einen Inhaltstyp zum ersten Mal auf einen vorhandenen Hub und die vorhandenen zugeordneten Sites übertragen, kann es bis zu einer Stunde dauern, bis die Einstellungen auf der Site aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3d438-115">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="3d438-116">Neue Zuordnungen zum Hub erfordern diese Wartezeit nicht und die Einstellungen werden in wenigen Minuten wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="3d438-116">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="3d438-117">Nachdem die Einstellungen aktualisiert wurden, ist der Inhaltstyp mit diesen Einstellungen in wenigen Minuten auf jeder neu mit dem Hub verknüpften Site verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3d438-117">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="3d438-118">Dann wird jeder neu erstellten Liste oder Bibliothek der Inhaltstyp innerhalb weniger Minuten nach der Erstellung automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3d438-118">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="3d438-119">Ein übertragener Inhaltstyp wird einer Dokumentbibliothek nur hinzugefügt, wenn er direkt oder indirekt vom Dokumentinhaltstyp abgeleitet ist, und ein Inhaltstyp wird nur dann zu einer Liste hinzugefügt, wenn er nicht direkt oder indirekt vom Dokumentinhaltstyp abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="3d438-119">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d438-120">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="3d438-120">See also</span></span>
