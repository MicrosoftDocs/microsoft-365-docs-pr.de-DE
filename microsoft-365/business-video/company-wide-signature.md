---
title: Erstellen einer unternehmensweiten Signatur
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie eine unternehmensweite e-Mail-Signatur erstellen.
ms.openlocfilehash: 64c269abd25cab74ec5b0836975902e46a611c8c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702304"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="c7150-103">Erstellen einer unternehmensweiten e-Mail-Signatur</span><span class="sxs-lookup"><span data-stu-id="c7150-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="c7150-104">Eine unternehmensweite e-Mail-Signatur wird in jeder e-Mail angezeigt, die von Personen in Ihrer Organisation gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7150-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="c7150-105">Sie können damit wichtige Details wie die Kontaktinformationen Ihres Unternehmens oder einen rechtlichen Haftungsausschluss anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c7150-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="c7150-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="c7150-106">Try it!</span></span>

1. <span data-ttu-id="c7150-107">Wählen Sie im Microsoft 365 Admin Center die Option **Exchange** aus.</span><span class="sxs-lookup"><span data-stu-id="c7150-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="c7150-108">Wählen Sie **Nachrichtenfluss** aus.</span><span class="sxs-lookup"><span data-stu-id="c7150-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="c7150-109">Wählen Sie **Add +** aus, und klicken Sie dann auf **Haftungsausschlüsse anwenden**.</span><span class="sxs-lookup"><span data-stu-id="c7150-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="c7150-110">Auf der Seite **neue Regel** :</span><span class="sxs-lookup"><span data-stu-id="c7150-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="c7150-111">Geben Sie einen Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="c7150-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="c7150-112">Wählen Sie in der Dropdownliste **diese Regel anwenden** aus die Option **auf alle Nachrichten anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="c7150-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="c7150-113">Überprüfen Sie in der Dropdownliste **ausführen die folgende** , ob **die Haftungsausschluss anfügen** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c7150-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="c7150-114">Wählen Sie rechts auf der Seite **Text eingeben** aus, und geben Sie im Textfeld **Disclaimer angeben** den Text für Ihre e-Mail-Signatur ein.</span><span class="sxs-lookup"><span data-stu-id="c7150-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="c7150-115">Sie können das Aussehen Ihrer Signatur verbessern, indem Sie den Text mit HTML formatieren.</span><span class="sxs-lookup"><span data-stu-id="c7150-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="c7150-116">Wenn ein Bild in Ihrer Signatur angezeigt werden soll, müssen Sie eine öffentlich verfügbare URL für das Bild verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7150-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="c7150-117">Navigieren Sie zu dem Bild im Internet, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **Bildadresse kopieren** aus.</span><span class="sxs-lookup"><span data-stu-id="c7150-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="c7150-118">Fügen Sie die Adresse in das Textfeld **Haftungsausschluss angeben** ein.</span><span class="sxs-lookup"><span data-stu-id="c7150-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="c7150-119">Wählen Sie **OK** aus, und Scrollen Sie nach unten.</span><span class="sxs-lookup"><span data-stu-id="c7150-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="c7150-120">Um sicherzustellen, dass die Signatur mit verschlüsselten e-Mails funktioniert, fügen Sie eine Fallback-Option hinzu.</span><span class="sxs-lookup"><span data-stu-id="c7150-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="c7150-121">Klicken Sie rechts auf der Seite auf **auswählen**, dann auf **Umbruch**, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="c7150-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="c7150-122">Scrollen Sie nach unten, und lassen Sie den Modus auf **erzwingen** festgelegt, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c7150-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="c7150-123">Eine Warnmeldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7150-123">A warning message will appear.</span></span> <span data-ttu-id="c7150-124">Wählen Sie **Ja** aus, um die Regel auf alle zukünftigen Nachrichten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="c7150-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="c7150-125">Ihre Signatur wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="c7150-125">Your signature has been created.</span></span> <span data-ttu-id="c7150-126">Wenn Sie Ihre nächste e-Mail senden, wird die soeben erstellte Signatur nicht angezeigt, aber die e-Mail-Empfänger werden Sie sehen.</span><span class="sxs-lookup"><span data-stu-id="c7150-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>