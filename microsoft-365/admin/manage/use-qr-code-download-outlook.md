---
title: Verwenden eines QR-Codes zum Anmelden bei Outlook mobilen Apps
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
description: Erfahren Sie, wie Sie einen QR-Code zum Authentifizieren und Herunterladen von Outlook verwenden.
ms.openlocfilehash: 2c1853a6ea1dd1a5d2ad30b975d1dbd23b942040
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635998"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="d3373-103">Verwenden eines QR-Codes zum Anmelden bei Outlook mobilen Apps</span><span class="sxs-lookup"><span data-stu-id="d3373-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3373-104">Dieses Feature ist nur für Organisationen verfügbar, die die gezielte Veröffentlichung im Microsoft 365 aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="d3373-104">This feature is only available to organizations that have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d3373-105">Weitere Informationen zur Funktionsweise der gezielten Veröffentlichung finden Sie unter [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d3373-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="d3373-106">Wir werden in den kommenden Wochen über die öffentliche Vorschau auf weitere Organisationen erweitern.</span><span class="sxs-lookup"><span data-stu-id="d3373-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="d3373-107">Die öffentliche Vorschau bietet frühzeitigen Zugriff auf Microsoft 365 Features.</span><span class="sxs-lookup"><span data-stu-id="d3373-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="d3373-108">Als Microsoft 365 können Sie Ihren Benutzern die Anmeldung bei Outlook für Android oder iOS-App auf ihren mobilen Geräten ermöglichen, ohne ihren Benutzernamen und ihr Kennwort eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="d3373-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="d3373-109">Durch Das Scannen eines QR-Codes können Benutzer sich sicher authentifizieren und sich bei Outlook anmelden.</span><span class="sxs-lookup"><span data-stu-id="d3373-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="d3373-110">In Outlook im Web oder in anderen Desktop-Outlook können Benutzern Benachrichtigungen angezeigt werden, die sie darüber informieren, dass sie Outlook auf ihrem mobilen Gerät verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d3373-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="d3373-111">Diese Benachrichtigungen können vom Administrator mithilfe von powershell Exchange verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d3373-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="d3373-112">Wenn Benutzer sich selbst eine SMS senden, um die App auf ihrem mobilen Gerät herunterzuladen, wird auf ihrem Computer ein QR-Code angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3373-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="d3373-113">Sie können den QR-Code überprüfen, um sich Outlook Smartphone oder Tablet zu melden.</span><span class="sxs-lookup"><span data-stu-id="d3373-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="d3373-114">Dieser QR-Code ist ein kurzlebiges Token, das nur einmal eingelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="d3373-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="d3373-115">In einigen Fällen müssen sich Ihre Benutzer erneut auf ihrem Computer authentifizieren, um den QR-Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d3373-115">In some cases, your users must re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="d3373-116">Verwenden Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3373-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="d3373-117">Diese Funktion ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d3373-117">This feature is on by default.</span></span> <span data-ttu-id="d3373-118">Führen Sie die folgenden Schritte aus, um dieses Feature zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d3373-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="d3373-119">[Verbinden zum Exchange PowerShell .](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="d3373-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="d3373-120">Mit PowerShell können Sie die Benachrichtigungen deaktivieren, die Ihre Benutzer über die Outlook informieren.</span><span class="sxs-lookup"><span data-stu-id="d3373-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="d3373-121">Dadurch wird auch verhindert, dass der QR-Code-Anmeldefluss angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d3373-121">This also prevents the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a><span data-ttu-id="d3373-122">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="d3373-122">Related content</span></span>

<span data-ttu-id="d3373-123">[Einrichten der Standard- oder Zielversionsoptionen](release-options-in-office-365.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="d3373-123">[Set up the Standard or Targeted release options](release-options-in-office-365.md) (article)</span></span>\
<span data-ttu-id="d3373-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="d3373-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (article)</span></span>