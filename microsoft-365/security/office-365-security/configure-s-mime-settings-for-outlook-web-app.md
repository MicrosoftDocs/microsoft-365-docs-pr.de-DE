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
description: Eine kurze Beschreibung der Notwendigkeit von Exchange Online-Administratoren zum Anzeigen und Konfigurieren der S/MIME-Einstellungen in Outlook im Web in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eacc6a264682474054d0d3546b831039bee9a0c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203940"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="621aa-103">Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="621aa-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="621aa-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="621aa-104">**Applies to**</span></span>
- [<span data-ttu-id="621aa-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="621aa-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="621aa-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="621aa-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="621aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="621aa-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="621aa-108">Als Administrator für Exchange Online können Sie Outlook im Web (früher als Outlook Web App bezeichnet) einrichten, um das Senden und Empfangen von S/MIME-geschützten Nachrichten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="621aa-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="621aa-109">Verwenden Sie **die Cmdlets Get-SmimeConfig** und **Set-SmimeConfig,** um dieses Feature in Exchange Online PowerShell zu anzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="621aa-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="621aa-110">Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="621aa-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="621aa-111">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) und [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="621aa-111">For detailed syntax and parameter information, see [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="621aa-112">Überlegungen zu neuen Microsoft Edge (chromium-basiert)</span><span class="sxs-lookup"><span data-stu-id="621aa-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="621aa-113">Um S/MIME in Outlook im Web im neuen [Microsoft Edge-Webbrowser](https://www.microsoft.com/windows/microsoft-edge) zu verwenden, müssen Sie (oder ein anderer Administrator) die Microsoft Edge-Browserrichtlinie **namens ExtensionInstallForcelist** festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung im neuen Microsoft Edge zu installieren.</span><span class="sxs-lookup"><span data-stu-id="621aa-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="621aa-114">Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="621aa-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="621aa-115">Und beachten Sie, dass für die Anwendung dieser Richtlinie Geräte erforderlich sind, die der Domäne oder Azure AD beigetreten sind. Daher erfordert die Verwendung von S/MIME im neuen Microsoft Edge-Browser effektiv Geräte, die der Domäne oder Azure AD beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="621aa-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="621aa-116">Weitere Informationen zur **ExtensionInstallForcelist-Richtlinie** finden Sie unter [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="621aa-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="621aa-117">Dieser Schritt ist eine Voraussetzung für die Verwendung des neuen Microsoft Edge; Es ersetzt nicht das von Benutzern installierte S/MIME-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="621aa-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="621aa-118">Benutzer werden aufgefordert, das S/MIME-Steuerelement während der ersten Verwendung von S/MIME in Outlook im Web herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="621aa-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="621aa-119">Oder Benutzer können proaktiv zu **S/MIME** in ihren Outlook on the Web-Einstellungen wechseln, um den Downloadlink für das Steuerelement zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="621aa-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="621aa-120">Überlegungen zu Chrome</span><span class="sxs-lookup"><span data-stu-id="621aa-120">Considerations for Chrome</span></span>

<span data-ttu-id="621aa-121">Um S/MIME in Outlook im Web im Google Chrome-Webbrowser zu verwenden, müssen Sie (oder ein anderer Administrator) die Chromium-Richtlinie namens **ExtensionInstallForcelist** festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung in Chrome zu installieren.</span><span class="sxs-lookup"><span data-stu-id="621aa-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="621aa-122">Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="621aa-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="621aa-123">Beachten Sie außerdem, dass für die Anwendung dieser Richtlinie Computer mit Domänen verbunden sind, sodass die Verwendung von S/MIME in Chrome effektiv Computer erfordert, die der Domäne beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="621aa-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="621aa-124">Weitere Informationen zur **ExtensionInstallForcelist-Richtlinie** finden Sie unter [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="621aa-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="621aa-125">Dieser Schritt ist eine Voraussetzung für die Verwendung von Chrome. Es ersetzt nicht das von Benutzern installierte S/MIME-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="621aa-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="621aa-126">Benutzer werden aufgefordert, das S/MIME-Steuerelement während der ersten Verwendung von S/MIME in Outlook im Web herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="621aa-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="621aa-127">Oder Benutzer können proaktiv zu **S/MIME** in ihren Outlook on the Web-Einstellungen wechseln, um den Downloadlink für das Steuerelement zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="621aa-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="621aa-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="621aa-128">For more information</span></span>

[<span data-ttu-id="621aa-129">S/MIME für die Nachrichtensignierung und -verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="621aa-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)