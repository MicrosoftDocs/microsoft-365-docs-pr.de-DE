---
title: Bild-Tagging in SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Mehr zu Bild-Tagging in SharePoint Syntex
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296096"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="96fd5-103">Bild-Tagging in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="96fd5-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="96fd5-104">Standardmäßig ist Bild-Tagging für Microsoft Office SharePoint Online und OneDrive aktiviert.</span><span class="sxs-lookup"><span data-stu-id="96fd5-104">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="96fd5-105">Bilder, die an einen der beiden Standorte hochgeladen werden, werden automatisch gescannt und, falls verfügbar, werden anwendbare Tags aus einer Liste von 37 Basis-Tags angewendet.</span><span class="sxs-lookup"><span data-stu-id="96fd5-105">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="96fd5-106">Benutzer können Bilder über die Suche finden, indem Sie Bild-Tags durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="96fd5-106">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="96fd5-107">Wenn ein Benutzer ein Bild hochlädt, läuft der Tagging-Prozess automatisch ab.</span><span class="sxs-lookup"><span data-stu-id="96fd5-107">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="96fd5-108">Wenn ein Bild bearbeitet wird, läuft der Tagging-Prozess erneut ab, um die Tags zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="96fd5-108">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="96fd5-109">Benutzer mit Berechtigungen für die Bilddatei können die Tags im Dateiinformationsfenster oder auf der Suchergebnisseite sehen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="96fd5-109">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="96fd5-110">Sobald ein Benutzer die Tags eines Bildes bearbeitet, führt das System keine automatische Markierung mehr für dieses Bild durch, selbst wenn es bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="96fd5-110">Once a user edits an image's tags, the system no longer performs auto-tagging on that image, even if it is edited.</span></span>

<span data-ttu-id="96fd5-111">Wenn Sie Markieren ausschalten, werden Bilder nicht mehr automatisch mit Tags versehen.</span><span class="sxs-lookup"><span data-stu-id="96fd5-111">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="96fd5-112">Vorhandene Tags werden nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="96fd5-112">Existing tags will not be removed.</span></span>

## <a name="configure-image-tagging"></a><span data-ttu-id="96fd5-113">Bild-Tagging konfigurieren</span><span class="sxs-lookup"><span data-stu-id="96fd5-113">Configure image tagging</span></span>

<span data-ttu-id="96fd5-114">Sie können Bild-Tagging im Microsoft 365 Admin Center konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="96fd5-114">You can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="96fd5-115">So schalten Sie die Bild-Tagging-Funktion ein oder aus</span><span class="sxs-lookup"><span data-stu-id="96fd5-115">To turn image tagging on or off</span></span>

1. <span data-ttu-id="96fd5-116">Klicken Sie im Microsoft 365 Admin Center auf **Setup**.</span><span class="sxs-lookup"><span data-stu-id="96fd5-116">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="96fd5-117">Klicken Sie unter **Organisationswissen** auf **Inhaltsverständnis automatisieren**.</span><span class="sxs-lookup"><span data-stu-id="96fd5-117">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="96fd5-118">Klicken Sie auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="96fd5-118">Click **Manage**.</span></span>

4. <span data-ttu-id="96fd5-119">Klicken Sie auf der Registerkarte **Bild-Tagging** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="96fd5-119">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="96fd5-120">Wählen Sie, ob Sie **Basic Tagging** zulassen oder Markieren **ausschalten** möchten.</span><span class="sxs-lookup"><span data-stu-id="96fd5-120">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="96fd5-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="96fd5-121">Click **Save**.</span></span>

    ![Screenshot der Bild-Tagging-Steuerung](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a><span data-ttu-id="96fd5-123">Mehr dazu</span><span class="sxs-lookup"><span data-stu-id="96fd5-123">See also</span></span>

[<span data-ttu-id="96fd5-124">Inhaltsverständnis einrichten</span><span class="sxs-lookup"><span data-stu-id="96fd5-124">Set up content understanding</span></span>](set-up-content-understanding.md)