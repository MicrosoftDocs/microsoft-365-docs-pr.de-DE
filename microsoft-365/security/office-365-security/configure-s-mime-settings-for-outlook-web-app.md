---
title: Konfigurieren von S/MIME-Einstellungen – Exchange Online für Outlook im Web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Eine kurze Beschreibung, was Exchange Online-Administratoren tun müssen, um die S/MIME-Einstellungen in Outlook im Web in Exchange Online anzeigen und konfigurieren zu können.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a81db5ec933f1d0d6e2944103be53c0169dde62f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165679"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="e4d52-103">Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="e4d52-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e4d52-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="e4d52-104">**Applies to**</span></span>
- [<span data-ttu-id="e4d52-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e4d52-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="e4d52-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="e4d52-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="e4d52-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4d52-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="e4d52-108">Als Administrator für Exchange Online können Sie Outlook im Web (früher als Outlook Web App bezeichnet) einrichten, um das Senden und Empfangen von S/MIME-geschützten Nachrichten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e4d52-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="e4d52-109">Verwenden Sie **die Cmdlets "Get-SmimeConfig"** und **"Set-SmimeConfig",** um dieses Feature in Exchange Online PowerShell anzeigen und verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="e4d52-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="e4d52-110">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e4d52-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="e4d52-111">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) und [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="e4d52-111">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="e4d52-112">Überlegungen für das neue Microsoft Edge (Chromium-basiert)</span><span class="sxs-lookup"><span data-stu-id="e4d52-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="e4d52-113">Um S/MIME in Outlook im Web im neuen [Microsoft Edge-Webbrowser](https://www.microsoft.com/windows/microsoft-edge) zu verwenden, müssen Sie (oder ein anderer Administrator) die Microsoft Edge-Browserrichtlinie namens **ExtensionInstallForcelist** so festlegen und konfigurieren, dass die Microsoft S/MIME-Erweiterung im neuen Microsoft Edge installiert wird.</span><span class="sxs-lookup"><span data-stu-id="e4d52-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="e4d52-114">Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="e4d52-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="e4d52-115">Und beachten Sie, dass für die Anwendung dieser Richtlinie Geräte erforderlich sind, die einer Domäne oder Azure AD beigetreten sind, sodass die Verwendung von S/MIME im neuen Microsoft Edge-Browser effektiv geräte erfordert, die einer Domäne oder Azure AD beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="e4d52-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="e4d52-116">Details zur **Richtlinie ExtensionInstallForcelist** finden Sie unter [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="e4d52-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="e4d52-117">Dieser Schritt ist eine Voraussetzung für die Verwendung des neuen Microsoft Edge. Das S/MIME-Steuerelement, das von Benutzern installiert wird, wird nicht ersetzt.</span><span class="sxs-lookup"><span data-stu-id="e4d52-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="e4d52-118">Benutzer werden aufgefordert, das S/MIME-Steuerelement bei der ersten Verwendung von S/MIME in Outlook im Web herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e4d52-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="e4d52-119">Oder Benutzer können proaktiv zu **S/MIME** in ihren Outlook im Web-Einstellungen wechseln, um den Downloadlink für das Steuerelement zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e4d52-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="e4d52-120">Überlegungen zu Chrome</span><span class="sxs-lookup"><span data-stu-id="e4d52-120">Considerations for Chrome</span></span>

<span data-ttu-id="e4d52-121">Um S/MIME in Outlook im Web im Google Chrome-Webbrowser zu verwenden, müssen Sie (oder ein anderer Administrator) die Chromium-Richtlinie namens **ExtensionInstallForcelist** festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung in Chrome zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e4d52-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="e4d52-122">Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="e4d52-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="e4d52-123">Und beachten Sie, dass für die Anwendung dieser Richtlinie Computer erforderlich sind, die der Domäne beigetreten sind. Daher sind für die Verwendung von S/MIME in Chrome effektiv Computer erforderlich, die der Domäne beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="e4d52-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="e4d52-124">Details zur **Richtlinie ExtensionInstallForcelist** finden Sie unter [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="e4d52-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="e4d52-125">Dieser Schritt ist eine Voraussetzung für die Verwendung von Chrome. Das S/MIME-Steuerelement, das von Benutzern installiert wird, wird nicht ersetzt.</span><span class="sxs-lookup"><span data-stu-id="e4d52-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="e4d52-126">Benutzer werden aufgefordert, das S/MIME-Steuerelement bei der ersten Verwendung von S/MIME in Outlook im Web herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e4d52-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="e4d52-127">Oder Benutzer können proaktiv zu **S/MIME** in ihren Outlook im Web-Einstellungen wechseln, um den Downloadlink für das Steuerelement zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e4d52-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="e4d52-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4d52-128">For more information</span></span>

[<span data-ttu-id="e4d52-129">S/MIME für die Nachrichtensignierung und -verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e4d52-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
