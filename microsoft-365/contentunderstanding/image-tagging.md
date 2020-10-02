---
title: Bild-Tagging in SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Mehr zu Bild-Tagging in SharePoint Syntex
ms.openlocfilehash: 7b41422633934593de881bdb0c04f0a845a3fe5f
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321253"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="0210f-103">Bild-Tagging in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0210f-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="0210f-104">Mit Bild-Tagging in SharePoint Syntex können Benutzer Bilder über die Suche finden, indem Sie nach Bild-Tags suchen und Workflows basierend auf Bild-Tags erstellen.</span><span class="sxs-lookup"><span data-stu-id="0210f-104">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="0210f-105">Standardmäßig ist Bild-Tagging für Microsoft Office SharePoint Online und OneDrive aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0210f-105">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="0210f-106">Bilder, die an einen der beiden Standorte hochgeladen werden, werden automatisch gescannt und, falls verfügbar, werden anwendbare Tags aus einer Liste von 37 Basis-Tags angewendet.</span><span class="sxs-lookup"><span data-stu-id="0210f-106">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="0210f-107">Benutzer können Bilder über die Suche finden, indem Sie Bild-Tags durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="0210f-107">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="0210f-108">Wenn ein Benutzer ein Bild hochlädt, läuft der Tagging-Prozess automatisch ab.</span><span class="sxs-lookup"><span data-stu-id="0210f-108">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="0210f-109">Wenn ein Bild bearbeitet wird, läuft der Tagging-Prozess erneut ab, um die Tags zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0210f-109">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="0210f-110">Benutzer mit Berechtigungen für die Bilddatei können die Tags im Dateiinformationsfenster oder auf der Suchergebnisseite sehen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0210f-110">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="0210f-111">Sobald ein Benutzer die Tags eines Bildes bearbeitet, führt das System keine automatische Markierung mehr für dieses Bild durch, selbst wenn es bearbeitet ist.</span><span class="sxs-lookup"><span data-stu-id="0210f-111">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="0210f-112">Wenn Sie den Tagging-Prozess ausschalten, werden Bilder nicht mehr automatisch mit Tags versehen.</span><span class="sxs-lookup"><span data-stu-id="0210f-112">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="0210f-113">Vorhandene Tags werden nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="0210f-113">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="0210f-114">Vom System generierte Tags können sich durch Updates des Bilds oder unserer Tag-Technologie ändern.</span><span class="sxs-lookup"><span data-stu-id="0210f-114">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="0210f-115">Bild-Tagging konfigurieren</span><span class="sxs-lookup"><span data-stu-id="0210f-115">Configure image tagging</span></span>

<span data-ttu-id="0210f-116">Nachdem Sie [SharePoint Syntex eingerichtet haben](set-up-content-understanding.md), können Sie Bild-Tagging im Microsoft 365 Admin Center konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0210f-116">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="0210f-117">So schalten Sie die Bild-Tagging-Funktion ein oder aus</span><span class="sxs-lookup"><span data-stu-id="0210f-117">To turn image tagging on or off</span></span>

1. <span data-ttu-id="0210f-118">Klicken Sie im Microsoft 365 Admin Center auf **Setup**.</span><span class="sxs-lookup"><span data-stu-id="0210f-118">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="0210f-119">Klicken Sie unter **Organisationswissen** auf **Inhaltsverständnis automatisieren**.</span><span class="sxs-lookup"><span data-stu-id="0210f-119">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="0210f-120">Klicken Sie auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="0210f-120">Click **Manage**.</span></span>

4. <span data-ttu-id="0210f-121">Klicken Sie auf der Registerkarte **Bild-Tagging** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0210f-121">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="0210f-122">Wählen Sie, ob Sie **Basic Tagging** zulassen oder Markieren **ausschalten** möchten.</span><span class="sxs-lookup"><span data-stu-id="0210f-122">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="0210f-123">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0210f-123">Click **Save**.</span></span>

    ![Screenshot der Bild-Tagging-Steuerung](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
