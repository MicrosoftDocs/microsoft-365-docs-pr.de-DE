---
title: Erstellen einer unternehmensweiten Signatur
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Erfahren Sie, wie Sie eine unternehmensweite E-Mail-Signatur erstellen.
ms.openlocfilehash: a1a85826be2a799b56cf3d06b6416778470a116f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578951"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="b8cb0-103">Erstellen einer unternehmensweiten E-Mail-Signatur</span><span class="sxs-lookup"><span data-stu-id="b8cb0-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="b8cb0-104">Eine unternehmensweite E-Mail-Signatur wird in jeder E-Mail angezeigt, die von Personen in Ihrer Organisation gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="b8cb0-105">Sie können es verwenden, um wichtige Details anzuzeigen, z. B. Ihre Unternehmenskontaktinformationen oder einen Haftungsausschluss.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="b8cb0-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="b8cb0-106">Try it!</span></span>

1. <span data-ttu-id="b8cb0-107">Wählen Sie im Microsoft 365 Admin Center die **Option Exchange** aus.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="b8cb0-108">Wählen **Sie Nachrichtenfluss aus.**</span><span class="sxs-lookup"><span data-stu-id="b8cb0-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="b8cb0-109">Wählen **Sie Hinzufügen +** aus, und wählen Sie dann **Haftungsausschlüsse anwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="b8cb0-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="b8cb0-110">Auf der **Seite Neue Regel:**</span><span class="sxs-lookup"><span data-stu-id="b8cb0-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="b8cb0-111">Geben Sie einen Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="b8cb0-112">Wählen Sie **in der Dropdownliste Diese Regel anwenden** auf alle Nachrichten anwenden **aus.**</span><span class="sxs-lookup"><span data-stu-id="b8cb0-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="b8cb0-113">Überprüfen Sie **in der Dropdownliste** Gehen Sie wie folgt vor, ob Der Haftungsausschluss **anfügen** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="b8cb0-114">Wählen Sie rechts auf der Seite Text eingeben **aus,** und geben Sie dann den Text für Ihre E-Mail-Signatur in das Textfeld **Haftungsausschluss** angeben ein.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="b8cb0-115">Sie können das Aussehen Ihrer Signatur verbessern, indem Sie den Text mit HTML formatieren.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="b8cb0-116">Wenn ein Bild in Ihrer Signatur angezeigt werden soll, müssen Sie eine öffentlich verfügbare URL für dieses Bild verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="b8cb0-117">Navigieren Sie zum Bild im Web, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **Bildadresse kopieren aus.**</span><span class="sxs-lookup"><span data-stu-id="b8cb0-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="b8cb0-118">Fügen Sie die Adresse in das Textfeld **Haftungsausschluss** angeben ein.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="b8cb0-119">Wählen **Sie OK** aus, und scrollen Sie dann nach unten.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="b8cb0-120">Um sicherzustellen, dass die Signatur mit verschlüsselten E-Mails funktioniert, fügen Sie eine Ausweichoption hinzu.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="b8cb0-121">Wählen Sie rechts auf der Seite Auswählen **aus,** wählen Sie **Umschließen** aus, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="b8cb0-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="b8cb0-122">Scrollen Sie nach unten, und lassen Sie den Modus auf **Erzwingen** festgelegt, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="b8cb0-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="b8cb0-123">Es wird eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-123">A warning message will appear.</span></span> <span data-ttu-id="b8cb0-124">Wählen **Sie Ja** aus, um die Regel auf alle zukünftigen Nachrichten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="b8cb0-125">Ihre Signatur wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-125">Your signature has been created.</span></span> <span data-ttu-id="b8cb0-126">Wenn Sie Ihre nächste E-Mail senden, wird die gerade erstellte Signatur nicht mehr zu sehen sein, aber die E-Mail-Empfänger sehen sie.</span><span class="sxs-lookup"><span data-stu-id="b8cb0-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>