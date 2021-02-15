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
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242354"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="01957-103">Verwenden eines QR-Codes zum Anmelden bei den mobilen Outlook-Apps</span><span class="sxs-lookup"><span data-stu-id="01957-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01957-104">Dieses Feature ist nur für Organisationen verfügbar, die targeted Release im Microsoft 365 Admin Center aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="01957-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="01957-105">Weitere Informationen zum Aktivieren der zielorientierten Version und zur Funktionsweise finden Sie unter ["Einrichten der Standard- oder Targeted Release-Optionen".](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="01957-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="01957-106">Wir werden in den kommenden Wochen über eine öffentliche Vorschau auf weitere Organisationen erweitern.</span><span class="sxs-lookup"><span data-stu-id="01957-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="01957-107">Die öffentliche Vorschau bietet frühzeitigen Zugriff auf Microsoft 365-Features.</span><span class="sxs-lookup"><span data-stu-id="01957-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="01957-108">Als Microsoft 365-Administrator können Sie Ihren Benutzern ermöglichen, sich bei Outlook für Android oder einer iOS-App auf ihren mobilen Geräten ohne Eingabe ihres Benutzernamens und Kennworts anmelden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="01957-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="01957-109">Durch das Scannen eines QR-Codes können Benutzer sich sicher authentifizieren und sich bei Outlook Mobile anmelden.</span><span class="sxs-lookup"><span data-stu-id="01957-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="01957-110">In Outlook im Web oder anderen Desktop-Outlook-Anwendungen werden Benutzern möglicherweise Benachrichtigungen angezeigt, die sie darüber informieren, dass sie Outlook auf ihrem mobilen Gerät verwenden können.</span><span class="sxs-lookup"><span data-stu-id="01957-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="01957-111">Diese Benachrichtigungen können vom Administrator mithilfe von Exchange Powershell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="01957-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="01957-112">Wenn sich Benutzer entscheiden, sich selbst eine SMS zu senden, um die App auf ihr mobiles Gerät herunterzuladen, wird auf ihrem Computer ein QR-Code angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01957-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="01957-113">Sie können den QR-Code überprüfen, um sich auf ihrem Smartphone oder Tablet bei Outlook zu anmelden.</span><span class="sxs-lookup"><span data-stu-id="01957-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="01957-114">Dieser QR-Code ist ein kurzlebiges Token, das nur einmal eingelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="01957-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="01957-115">In einigen Fällen müssen sich Ihre Benutzer auf ihrem Computer erneut authentifizieren, um den QR-Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="01957-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="01957-116">Verwenden von Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="01957-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="01957-117">Diese Funktion ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="01957-117">This feature is on by default.</span></span> <span data-ttu-id="01957-118">Führen Sie die folgenden Schritte aus, um dieses Feature zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="01957-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="01957-119">[Herstellen einer Verbindung mit Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="01957-119">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="01957-120">Mithilfe von PowerShell können Sie die Benachrichtigungen deaktivieren, die Ihre Benutzer über die mobilen Outlook-Apps informieren.</span><span class="sxs-lookup"><span data-stu-id="01957-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="01957-121">Dadurch wird auch verhindert, dass der Anmeldefluss für den QR-Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="01957-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="01957-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="01957-122">Related topics</span></span>

[<span data-ttu-id="01957-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="01957-123">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
