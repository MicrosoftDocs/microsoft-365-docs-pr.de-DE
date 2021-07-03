---
title: Verwenden sie einen QR-Code, um sich bei den Outlook mobilen Apps anzumelden.
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
description: Erfahren Sie, wie Sie mithilfe eines QR-Codes Outlook Mobilgerät authentifizieren und herunterladen können.
ms.openlocfilehash: a403fbbed90229300e707653062c552104c47d97
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286705"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="a079e-103">Verwenden sie einen QR-Code, um sich bei den Outlook mobilen Apps anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a079e-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a079e-104">Dieses Feature ist nur für Organisationen verfügbar, die targeted Release im Microsoft 365 Admin Center aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="a079e-104">This feature is only available to organizations that have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a079e-105">Informationen zur Aktivierung der gezielten Version und weitere Informationen zur Funktionsweise finden Sie unter ["Einrichten der Standard- oder Targeted Release-Optionen".](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="a079e-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="a079e-106">Wir werden in den kommenden Wochen über die öffentliche Vorschau auf weitere Organisationen erweitern.</span><span class="sxs-lookup"><span data-stu-id="a079e-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="a079e-107">Die öffentliche Vorschau bietet frühzeitigen Zugriff auf Microsoft 365 Features.</span><span class="sxs-lookup"><span data-stu-id="a079e-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="a079e-108">Als Microsoft 365-Administrator können Sie Ihren Benutzern die Anmeldung bei Outlook für Android oder die iOS-App auf ihren mobilen Geräten ermöglichen, ohne ihren Benutzernamen und ihr Kennwort eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="a079e-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="a079e-109">Durch Scannen eines QR-Codes können Sich Benutzer sicher authentifizieren und sich bei Outlook Mobilgerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="a079e-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="a079e-110">In Outlook im Web oder anderen Desktop-Outlook-Anwendungen werden Benutzern möglicherweise Benachrichtigungen angezeigt, die sie darüber informieren, dass sie Outlook auf ihrem mobilen Gerät verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a079e-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="a079e-111">Diese Benachrichtigungen können vom Administrator mit Exchange PowerShell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a079e-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="a079e-112">Wenn Benutzer sich selbst eine SMS senden, um die App auf ihrem mobilen Gerät herunterzuladen, wird ein QR-Code auf ihrem Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a079e-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="a079e-113">Sie können den QR-Code scannen, um sich auf ihrem Smartphone oder Tablet bei Outlook anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a079e-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="a079e-114">Dieser QR-Code ist ein kurzlebiges Token, das nur einmal eingelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="a079e-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="a079e-115">In einigen Fällen müssen sich Die Benutzer auf ihrem Computer erneut authentifizieren, um den QR-Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a079e-115">In some cases, your users must re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="a079e-116">Verwenden von Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a079e-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="a079e-117">Diese Funktion ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a079e-117">This feature is on by default.</span></span> <span data-ttu-id="a079e-118">Führen Sie die folgenden Schritte aus, um dieses Feature zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a079e-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="a079e-119">[Verbinden zu Exchange PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="a079e-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="a079e-120">Mithilfe von PowerShell können Sie die Benachrichtigungen deaktivieren, die Ihre Benutzer über die Outlook mobilen Apps informieren.</span><span class="sxs-lookup"><span data-stu-id="a079e-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="a079e-121">Dadurch wird auch verhindert, dass der QR-Code-Anmeldefluss angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a079e-121">This also prevents the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a><span data-ttu-id="a079e-122">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="a079e-122">Related content</span></span>

<span data-ttu-id="a079e-123">[Einrichten der Standard- oder Targeted Release-Optionen](release-options-in-office-365.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="a079e-123">[Set up the Standard or Targeted release options](release-options-in-office-365.md) (article)</span></span>\
<span data-ttu-id="a079e-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="a079e-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (article)</span></span>