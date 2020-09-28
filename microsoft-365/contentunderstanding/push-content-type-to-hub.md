---
title: Pushen von Inhaltstypen an einen Hub
description: Informationen zum Pushen von Inhaltstypen an einen Hub
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a852207bfd1a2a7643ce8895a533371d194954cf
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296099"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="4c5e7-103">Pushen von Inhaltstypen an einen Hub</span><span class="sxs-lookup"><span data-stu-id="4c5e7-103">Push content types to a hub</span></span>

<span data-ttu-id="4c5e7-104">Damit SharePoint-Bibliotheken und-Listen wichtige Inhaltstypen konsistenter verfügbar gemacht werden, können Sie Sie an die ausgewählten Hubs weitergeben.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="4c5e7-105">Dadurch werden Sie automatisch neuen Listen und Bibliotheken hinzugefügt, die auf den dem Hub zugeordneten Websites erstellt wurden, sowie auf alle neuen Websites, die dem Hub hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="4c5e7-106">Damit dieses Feature funktioniert, müssen die gepushten Inhaltstypen bereits veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="4c5e7-107">So verschieben Sie Inhaltstypen in Hubs</span><span class="sxs-lookup"><span data-stu-id="4c5e7-107">To push content types to hubs</span></span>

1. <span data-ttu-id="4c5e7-108">Erweitern Sie im SharePoint Admin Center die Option **Inhaltsdienste**, und klicken Sie dann auf **Inhaltstypkatalog**.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="4c5e7-109">Klicken Sie auf den Inhaltstyp, den Sie in Hubs verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="4c5e7-110">Klicken Sie in der Befehlsleiste auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="4c5e7-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="4c5e7-111">Klicken Sie auf **Hub-Standorte auswählen**.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="4c5e7-112">Wählen Sie die gewünschten Hub-Standorte aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="4c5e7-113">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-113">Click **Save**.</span></span>

<span data-ttu-id="4c5e7-114">Wenn ein Inhaltstyp an einen vorhandenen Hub & seinen vorhandenen verbundenen Standorten zum ersten Mal übertragen wird, kann es bis zu einer Stunde dauern, bis der Hub oder die zugehörigen Standorte besucht werden, damit die Einstellungen am Standort aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="4c5e7-115">Für alle neuen Zuordnungen zum Hub ist diese Wartezeit nicht erforderlich, und die Einstellungen werden in einigen Minuten wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="4c5e7-116">Sobald dieser konfiguriert ist, wird der Inhaltstyp mit diesen Einstellungen in ein paar Minuten in jedem neu zugeordneten Standort mit dem Hub zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="4c5e7-117">Sobald eine neue Liste oder Bibliothek erstellt wurde, wird der Inhaltstyp innerhalb weniger Minuten nach der Erstellung automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="4c5e7-118">Ein gepushten Inhaltstyp wird nur dann zu einer Dokumentbibliothek hinzugefügt, wenn er direkt oder indirekt aus dem Dokumentinhaltstyp abgeleitet wird und ein Inhaltstyp nur einer Liste hinzugefügt wird, wenn er nicht direkt oder indirekt vom Dokumentinhaltstyp abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="4c5e7-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c5e7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c5e7-119">See also</span></span>



  






