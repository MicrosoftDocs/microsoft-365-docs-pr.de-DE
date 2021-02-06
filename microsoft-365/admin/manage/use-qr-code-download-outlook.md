---
title: Verwenden eines QR-Codes zum Anmelden bei den mobilen Outlook-Apps
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Erfahren Sie, wie Sie einen QR-Code verwenden, um Outlook Mobile zu authentifizieren und herunterzuladen.
ms.openlocfilehash: b9e433e0c7d3f5f3466924b318e242e5ac29181c
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122372"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="8d19f-103">Verwenden eines QR-Codes zum Anmelden bei den mobilen Outlook-Apps</span><span class="sxs-lookup"><span data-stu-id="8d19f-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d19f-104">Dieses Microsoft 365-Feature befindet sich in der öffentlichen Vorschau.</span><span class="sxs-lookup"><span data-stu-id="8d19f-104">This Microsoft 365 feature is in public preview.</span></span> <span data-ttu-id="8d19f-105">Die öffentliche Vorschau bietet frühzeitigen Zugriff auf Microsoft 365-Features.</span><span class="sxs-lookup"><span data-stu-id="8d19f-105">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="8d19f-106">Als Microsoft 365-Administrator können Sie Ihren Benutzern ermöglichen, sich bei Outlook für Android oder einer iOS-App auf ihren mobilen Geräten ohne Eingabe ihres Benutzernamens und Kennworts anmelden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="8d19f-106">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="8d19f-107">Durch das Scannen eines QR-Codes können Benutzer sich sicher authentifizieren und sich bei Outlook Mobile anmelden.</span><span class="sxs-lookup"><span data-stu-id="8d19f-107">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="8d19f-108">In Outlook im Web oder anderen Desktop-Outlook-Anwendungen werden Benutzern möglicherweise Benachrichtigungen angezeigt, die sie darüber informieren, dass sie Outlook auf ihrem mobilen Gerät verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8d19f-108">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="8d19f-109">Diese Benachrichtigungen können vom Administrator mithilfe von Exchange Powershell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="8d19f-109">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="8d19f-110">Wenn sich Benutzer entscheiden, sich selbst eine SMS zu senden, um die App auf ihr mobiles Gerät herunterzuladen, wird auf ihrem Computer ein QR-Code angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8d19f-110">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="8d19f-111">Sie können den QR-Code überprüfen, um sich auf ihrem Smartphone oder Tablet bei Outlook zu anmelden.</span><span class="sxs-lookup"><span data-stu-id="8d19f-111">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="8d19f-112">Dieser QR-Code ist ein kurzlebiges Token, das nur einmal eingelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="8d19f-112">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="8d19f-113">In einigen Fällen müssen sich Die Benutzer auf ihrem Computer erneut authentifizieren, um den QR-Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="8d19f-113">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="8d19f-114">Verwenden von Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d19f-114">Use Exchange PowerShell</span></span>

<span data-ttu-id="8d19f-115">Diese Erfahrung ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8d19f-115">This experience is on by default.</span></span> <span data-ttu-id="8d19f-116">Führen Sie die folgenden Schritte aus, um dieses Feature zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8d19f-116">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="8d19f-117">[Stellen Sie eine Verbindung mit Exchange PowerShell herzustellen.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="8d19f-117">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="8d19f-118">Mithilfe von PowerShell können Sie die Benachrichtigungen deaktivieren, die Ihre Benutzer über die mobilen Outlook-Apps informieren.</span><span class="sxs-lookup"><span data-stu-id="8d19f-118">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="8d19f-119">Dadurch wird auch verhindert, dass der Anmeldefluss für den QR-Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8d19f-119">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="8d19f-120">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8d19f-120">Related topics</span></span>

[<span data-ttu-id="8d19f-121">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="8d19f-121">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
