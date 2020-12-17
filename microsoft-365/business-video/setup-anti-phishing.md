---
title: Einrichten von Schutz gegen Phishing
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
description: Erfahren Sie, wie Sie Anti-Phishing-Schutz einrichten.
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702235"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="adc12-103">Einrichten von Anti-Phishing</span><span class="sxs-lookup"><span data-stu-id="adc12-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="adc12-104">Phishing ist ein böswilliger Angriff, bei dem eine e-Mail so aussieht, als ob Sie von einer bekannten Quelle gesendet wurde, aber versucht, Ihre persönlichen Informationen zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="adc12-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="adc12-105">Standardmäßig enthält Microsoft 365 einen Schutz vor Phishing, aber Sie können diesen Schutz erweitern, indem Sie die Einstellungen verfeinern.</span><span class="sxs-lookup"><span data-stu-id="adc12-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="adc12-106">Werfen wir einen Blick.</span><span class="sxs-lookup"><span data-stu-id="adc12-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="adc12-107">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="adc12-107">Try it!</span></span>

1. <span data-ttu-id="adc12-108">Wählen Sie im Admin Center unter die [https://admin.microsoft.com](https://admin.microsoft.com) Option **Security**, **Threat Management**, **Policy** und dann **ATP Anti-Phishing** aus.</span><span class="sxs-lookup"><span data-stu-id="adc12-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="adc12-109">Wählen Sie **Standardrichtlinie** aus, um Sie zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="adc12-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="adc12-110">Wählen Sie im Abschnitt **Identitätswechsel** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="adc12-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="adc12-111">Wechseln Sie zu zu **schützende Domänen hinzufügen** , und wählen Sie die Umschaltfläche aus, um automatisch die Domänen einzuschließen, die Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="adc12-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="adc12-112">Wechseln Sie zu **Aktionen**, öffnen Sie die Dropdownliste, **Wenn e-Mails von einem imitierten Benutzer gesendet** werden, und wählen Sie die gewünschte Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="adc12-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="adc12-113">Öffnen Sie die Dropdownliste, **Wenn e-Mails von einer imitierten Domäne gesendet werden** , und wählen Sie die gewünschte Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="adc12-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="adc12-114">Klicken Sie **auf Identitätswechsel-Sicherheitstipps aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="adc12-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="adc12-115">Wählen Sie aus, ob Tipps für Benutzer bereitgestellt werden sollen, wenn das System imitierte Benutzer, Domänen oder ungewöhnliche Zeichen erkennt.</span><span class="sxs-lookup"><span data-stu-id="adc12-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="adc12-116">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="adc12-116">Select **Save**.</span></span>
1. <span data-ttu-id="adc12-117">Wählen Sie **Mailbox Intelligence** aus, und stellen Sie sicher, dass Sie aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="adc12-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="adc12-118">Auf diese Weise können Ihre e-Mails effizienter durch das Erlernen von Verwendungsmustern sein.</span><span class="sxs-lookup"><span data-stu-id="adc12-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="adc12-119">Wählen Sie **vertrauenswürdige Absender und Domänen hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="adc12-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="adc12-120">Hier können Sie e-Mail-Adressen oder Domänen hinzufügen, die nicht als Identitätswechsel klassifiziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="adc12-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="adc12-121">Wählen Sie **Einstellungen überprüfen**, stellen Sie sicher, dass alles richtig ist, wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="adc12-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="adc12-122">Ihre Organisation bietet jetzt besseren Schutz vor Phishing-Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="adc12-122">Your organization now has better protection from phishing threats.</span></span>