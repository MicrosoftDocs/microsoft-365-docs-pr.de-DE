---
title: Konfigurieren von S/MIME-Einstellungen – Exchange Online für Outlook im Internet
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Eine kurze Beschreibung, was Exchange Online Administratoren tun müssen, um die S/MIME-Einstellungen in Outlook im Internet in Exchange Online anzuzeigen und zu konfigurieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe561c3a66cf2e7bdb76aabe10ffc875d85f2d77
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203335"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="79e1c-103">Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="79e1c-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="79e1c-104">Als Administrator für Exchange Online können Sie Outlook im Internet (früher als Outlook Web App bezeichnet) einrichten, um das Senden und empfangen von S/MIME-geschützten Nachrichten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="79e1c-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="79e1c-105">Verwenden Sie die Cmdlets **Get-SmimeConfig** und **SmimeConfig** , um dieses Feature in Exchange Online PowerShell anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="79e1c-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="79e1c-106">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="79e1c-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="79e1c-107">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) und [Sets-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="79e1c-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="79e1c-108">Überlegungen für neue Microsoft Edge (Chrom basiert)</span><span class="sxs-lookup"><span data-stu-id="79e1c-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="79e1c-109">Um s/MIME in Outlook im Internet im neuen [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) -Webbrowser zu verwenden, müssen Sie (oder ein anderer Administrator) die Microsoft-Edge-Browser-Richtlinie " **ExtensionInstallForcelist** " festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung im neuen Microsoft Edge zu installieren.</span><span class="sxs-lookup"><span data-stu-id="79e1c-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="79e1c-110">Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="79e1c-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="79e1c-111">Beachten Sie, dass die Anwendung dieser Richtlinie Domänenbeitritt oder Azure AD verbundene Geräte erfordert, sodass die Verwendung von S/MIME im neuen Microsoft Edge-Browser effektiv Domänen-oder Azure AD verbundene Geräte erfordert.</span><span class="sxs-lookup"><span data-stu-id="79e1c-111">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="79e1c-112">Ausführliche Informationen zur **ExtensionInstallForcelist** -Richtlinie finden Sie unter [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="79e1c-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="79e1c-113">Dieser Schritt ist eine Voraussetzung für die Verwendung von New Microsoft Edge; das von Benutzern installierte S/MIME-Steuerelement wird nicht ersetzt.</span><span class="sxs-lookup"><span data-stu-id="79e1c-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="79e1c-114">Benutzer werden aufgefordert, das s/MIME-Steuerelement in Outlook im Internet während der ersten Verwendung von s/MIME herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="79e1c-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="79e1c-115">Oder können Benutzer proaktiv zu **S/MIME** in Ihren Outlook im Webeinstellungen wechseln, um den Download-Link für das Steuerelement abzurufen.</span><span class="sxs-lookup"><span data-stu-id="79e1c-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="79e1c-116">Überlegungen für Chrome</span><span class="sxs-lookup"><span data-stu-id="79e1c-116">Considerations for Chrome</span></span>

<span data-ttu-id="79e1c-117">Um s/MIME in Outlook im Internet im Webbrowser von Google Chrome zu verwenden, müssen Sie (oder ein anderer Administrator) die Chrom Richtlinie mit dem Namen **ExtensionInstallForcelist** festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung in Chrome zu installieren.</span><span class="sxs-lookup"><span data-stu-id="79e1c-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="79e1c-118">Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="79e1c-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="79e1c-119">Beachten Sie, dass die Anwendung dieser Richtlinie Computer mit Domänenbeitritt erfordert, sodass die Verwendung von S/MIME in Chrome effektiv mit der Domäne verbundener Computer erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="79e1c-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="79e1c-120">Ausführliche Informationen zur **ExtensionInstallForcelist** -Richtlinie finden Sie unter [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="79e1c-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="79e1c-121">Dieser Schritt ist eine Voraussetzung für die Verwendung von Chrome; das von Benutzern installierte S/MIME-Steuerelement wird nicht ersetzt.</span><span class="sxs-lookup"><span data-stu-id="79e1c-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="79e1c-122">Benutzer werden aufgefordert, das s/MIME-Steuerelement in Outlook im Internet während der ersten Verwendung von s/MIME herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="79e1c-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="79e1c-123">Oder können Benutzer proaktiv zu **S/MIME** in Ihren Outlook im Webeinstellungen wechseln, um den Download-Link für das Steuerelement abzurufen.</span><span class="sxs-lookup"><span data-stu-id="79e1c-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="79e1c-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79e1c-124">For more information</span></span>

[<span data-ttu-id="79e1c-125">S/MIME für die Nachrichtensignierung und -verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="79e1c-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
