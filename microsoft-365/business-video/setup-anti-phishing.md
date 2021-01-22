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
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie den Antiphishingschutz einrichten.
ms.openlocfilehash: bcb6b8bac316b4b74c505656cb9a93e7a87e0830
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927874"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="8b794-103">Einrichten von Antiphishing</span><span class="sxs-lookup"><span data-stu-id="8b794-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="8b794-104">Phishing ist ein böswilliger Angriff, bei dem eine E-Mail so aussieht, als wäre sie von einer vertrauten Quelle gesendet worden, aber es wird versucht, Ihre persönlichen Informationen zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="8b794-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="8b794-105">Standardmäßig enthält Microsoft 365 antiphishingschutz, Sie können diesen Schutz jedoch erhöhen, indem Sie die Einstellungen optimieren.</span><span class="sxs-lookup"><span data-stu-id="8b794-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="8b794-106">Werfen wir einen Blick darauf.</span><span class="sxs-lookup"><span data-stu-id="8b794-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="8b794-107">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="8b794-107">Try it!</span></span>

1. <span data-ttu-id="8b794-108">Wählen Sie im Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) **"Sicherheit",** **"Bedrohungsverwaltung",** **"Richtlinie"** und dann **"ATP-Antiphishing" aus.**</span><span class="sxs-lookup"><span data-stu-id="8b794-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="8b794-109">Wählen Sie **die Standardrichtlinie aus,** um sie zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="8b794-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="8b794-110">Wählen Sie **im Abschnitt "Identitätswechsel"** die Option **"Bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="8b794-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="8b794-111">Wechseln Sie **zu "Domänen hinzufügen", um sie** zu schützen, und wählen Sie die Umschaltschalte aus, um automatisch die Domänen hinzuzufügen, die Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="8b794-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="8b794-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user,** and choose the action you want.</span><span class="sxs-lookup"><span data-stu-id="8b794-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="8b794-113">Öffnen Sie die **Dropdownliste, wenn E-Mails von einer imitierten** Domäne gesendet werden, und wählen Sie die Aktion aus, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8b794-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="8b794-114">Wählen **Sie Sicherheitstipps zum Aktivieren des Identitätswechsels aus.**</span><span class="sxs-lookup"><span data-stu-id="8b794-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="8b794-115">Wählen Sie aus, ob Benutzern Tipps bereitgestellt werden sollen, wenn das System imitierte Benutzer, Domänen oder ungewöhnliche Zeichen erkennt.</span><span class="sxs-lookup"><span data-stu-id="8b794-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="8b794-116">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8b794-116">Select **Save**.</span></span>
1. <span data-ttu-id="8b794-117">Wählen **Sie "Postfachintelligenz"** aus, und stellen Sie sicher, dass sie aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8b794-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="8b794-118">Dadurch können Ihre E-Mails effizienter sein, indem Sie Nutzungsmuster erlernen.</span><span class="sxs-lookup"><span data-stu-id="8b794-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="8b794-119">Wählen **Sie "Vertrauenswürdige Absender und Domänen hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="8b794-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="8b794-120">Hier können Sie E-Mail-Adressen oder Domänen hinzufügen, die nicht als Identitätswechsel klassifiziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8b794-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="8b794-121">Choose **Review your settings,** make sure everything is correct, select **Save**, then **Close**.</span><span class="sxs-lookup"><span data-stu-id="8b794-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="8b794-122">Ihre Organisation bietet jetzt besseren Schutz vor Phishing-Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="8b794-122">Your organization now has better protection from phishing threats.</span></span>