---
title: Einrichten des Antiphishingschutzes
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Erfahren Sie, wie Sie den Antiphishingschutz einrichten.
ms.openlocfilehash: 8cef8f916a8a3e2b27dd7f76ddecd921d59ca0c4
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422003"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="e8d57-103">Einrichten von Antiphishing</span><span class="sxs-lookup"><span data-stu-id="e8d57-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="e8d57-104">Phishing ist ein bösartiger Angriff, bei dem eine E-Mail so aussieht, als ob sie von einer vertrauten Quelle gesendet wurde, aber sie versucht, Ihre persönlichen Informationen zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="e8d57-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="e8d57-105">Standardmäßig enthält Microsoft 365 einen Antiphishingschutz, Aber Sie können diesen Schutz erhöhen, indem Sie die Einstellungen verfeinern.</span><span class="sxs-lookup"><span data-stu-id="e8d57-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="e8d57-106">Lassen Sie uns einen Blick werfen.</span><span class="sxs-lookup"><span data-stu-id="e8d57-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="e8d57-107">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="e8d57-107">Try it!</span></span>

1. <span data-ttu-id="e8d57-108">Wählen Sie im Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) die Option **Sicherheit,** **Bedrohungsverwaltung,** **Richtlinie** und **dann ATP-Antiphishing aus.**</span><span class="sxs-lookup"><span data-stu-id="e8d57-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="e8d57-109">Wählen **Sie Standardrichtlinie aus,** um sie zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="e8d57-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="e8d57-110">Wählen Sie **im Abschnitt Identitätswechsel** bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="e8d57-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="e8d57-111">Wechseln Sie **zu Domänen hinzufügen, um die** Umschalte zu schützen und auszuwählen, um automatisch die Domänen hinzuzufügen, die Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="e8d57-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="e8d57-112">Wechseln Sie **zu Aktionen,** öffnen Sie die Dropdownliste **Wenn** E-Mails von einem imitierten Benutzer gesendet werden, und wählen Sie die aktion aus, die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="e8d57-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="e8d57-113">Öffnen Sie die Dropdownliste **If email is sent by an impersonated domain,** and choose the action you want.</span><span class="sxs-lookup"><span data-stu-id="e8d57-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="e8d57-114">Wählen **Sie Identitätswechselsicherheitstipps aktivieren aus.**</span><span class="sxs-lookup"><span data-stu-id="e8d57-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="e8d57-115">Wählen Sie aus, ob Benutzern Tipps bereitgestellt werden sollen, wenn das System imitierte Benutzer, Domänen oder ungewöhnliche Zeichen erkennt.</span><span class="sxs-lookup"><span data-stu-id="e8d57-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="e8d57-116">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e8d57-116">Select **Save**.</span></span>
1. <span data-ttu-id="e8d57-117">Wählen **Sie Postfachintelligenz** aus, und überprüfen Sie, ob sie aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e8d57-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="e8d57-118">Dadurch können Ihre E-Mails effizienter sein, indem Sie Nutzungsmuster lernen.</span><span class="sxs-lookup"><span data-stu-id="e8d57-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="e8d57-119">Wählen **Sie Vertrauenswürdige Absender und Domänen hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="e8d57-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="e8d57-120">Hier können Sie E-Mail-Adressen oder Domänen hinzufügen, die nicht als Identitätswechsel klassifiziert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="e8d57-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="e8d57-121">Wählen **Sie Ihre Einstellungen überprüfen** aus, stellen Sie sicher, dass alles korrekt ist, wählen Sie **Speichern** und dann **Schließen aus.**</span><span class="sxs-lookup"><span data-stu-id="e8d57-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="e8d57-122">Ihre Organisation hat jetzt einen besseren Schutz vor Phishingbedrohungen.</span><span class="sxs-lookup"><span data-stu-id="e8d57-122">Your organization now has better protection from phishing threats.</span></span>