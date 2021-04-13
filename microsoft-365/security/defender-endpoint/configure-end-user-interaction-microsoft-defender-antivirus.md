---
title: Konfigurieren der Interaktion von Benutzern mit Microsoft Defender AV
description: Konfigurieren Sie, wie Endbenutzer mit Microsoft Defender AV interagieren, welche Benachrichtigungen angezeigt werden und ob sie Einstellungen außer Kraft setzen können.
keywords: Endpunkt, Benutzer, Interaktion, Benachrichtigungen, Ui-Sperrmodus, Kopflosmodus, Ausblenden der Schnittstelle
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b0a26360e5a84d055ea97034a2d0fbd2bc0d5c09
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690754"
---
# <a name="configure-end-user-interaction-with-microsoft-defender-antivirus"></a><span data-ttu-id="7ebda-104">Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="7ebda-104">Configure end-user interaction with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7ebda-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7ebda-105">**Applies to:**</span></span>

- [<span data-ttu-id="7ebda-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7ebda-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7ebda-107">Sie können konfigurieren, wie Benutzer der Endpunkte in Ihrem Netzwerk mit Microsoft Defender Antivirus interagieren können.</span><span class="sxs-lookup"><span data-stu-id="7ebda-107">You can configure how users of the endpoints on your network can interact with Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="7ebda-108">Dies umfasst, ob die Microsoft Defender Antivirus-Schnittstelle angezeigt wird, welche Benachrichtigungen angezeigt werden und ob die Einstellungen für global bereitgestellte Gruppenrichtlinien lokal überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="7ebda-108">This includes whether they see the Microsoft Defender Antivirus interface, what notifications they see, and if they can locally override globally-deployed Group Policy settings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7ebda-109">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="7ebda-109">In this section</span></span>

<span data-ttu-id="7ebda-110">Thema</span><span class="sxs-lookup"><span data-stu-id="7ebda-110">Topic</span></span> | <span data-ttu-id="7ebda-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ebda-111">Description</span></span> 
---|---
[<span data-ttu-id="7ebda-112">Konfigurieren von Benachrichtigungen, die auf Endpunkten angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="7ebda-112">Configure notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md) | <span data-ttu-id="7ebda-113">Konfigurieren und Anpassen zusätzlicher Benachrichtigungen, angepasster Text für Benachrichtigungen und Benachrichtigungen über Neustarts zur Behebung</span><span class="sxs-lookup"><span data-stu-id="7ebda-113">Configure and customize additional notifications, customized text for notifications, and notifications about reboots for remediation</span></span>
[<span data-ttu-id="7ebda-114">Verhindern, dass Benutzer die Benutzeroberfläche von Microsoft Defender Antivirus sehen oder mit ihr interagieren</span><span class="sxs-lookup"><span data-stu-id="7ebda-114">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="7ebda-115">Ausblenden der Benutzeroberfläche vor Benutzern</span><span class="sxs-lookup"><span data-stu-id="7ebda-115">Hide the user interface from users</span></span>
[<span data-ttu-id="7ebda-116">Verhindern, dass Benutzer Richtlinieneinstellungen lokal ändern</span><span class="sxs-lookup"><span data-stu-id="7ebda-116">Prevent users from locally modifying policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) | <span data-ttu-id="7ebda-117">Verhindern (oder zulassen), dass Benutzer Richtlinieneinstellungen auf ihren einzelnen Endpunkten außer Kraftsetzen</span><span class="sxs-lookup"><span data-stu-id="7ebda-117">Prevent (or allow) users from overriding policy settings on their individual endpoints</span></span>