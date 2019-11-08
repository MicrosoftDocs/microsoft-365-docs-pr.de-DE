---
title: Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Internet
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Eine kurze Beschreibung, was Exchange Online Administratoren tun müssen, um die S/MIME-Einstellungen in Outlook im Internet in Exchange Online anzuzeigen und zu konfigurieren.
ms.openlocfilehash: 408a8f7aed800175e7bae7af73d77f340359c17d
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032440"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="c91d7-103">Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="c91d7-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="c91d7-104">Als Administrator für Exchange Online können Sie Outlook im Internet (früher als Outlook Web App bezeichnet) einrichten, um das Senden und empfangen von S/MIME-geschützten Nachrichten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c91d7-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="c91d7-105">Verwenden Sie die Cmdlets **Get-SmimeConfig** und **SmimeConfig** , um dieses Feature in Exchange Online PowerShell anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c91d7-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="c91d7-106">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="c91d7-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

<span data-ttu-id="c91d7-107">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SmimeConfig](https://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) und [Sets-SmimeConfig](https://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="c91d7-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](https://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="c91d7-108">Überlegungen für Chrome</span><span class="sxs-lookup"><span data-stu-id="c91d7-108">Considerations for Chrome</span></span>

<span data-ttu-id="c91d7-109">Um s/MIME in Outlook im Internet im Webbrowser von Google Chrome zu verwenden, müssen Sie (oder ein anderer Administrator) die Chrom Richtlinie mit dem Namen **ExtensionInstallForcelist** festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung in Chrome zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c91d7-109">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="c91d7-110">Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span><span class="sxs-lookup"><span data-stu-id="c91d7-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="c91d7-111">Beachten Sie, dass die Anwendung dieser Richtlinie Computer mit Domänenbeitritt erfordert, sodass die Verwendung von S/MIME in Chrome effektiv mit der Domäne verbundener Computer erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c91d7-111">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="c91d7-112">Ausführliche Informationen zur **ExtensionInstallForcelist** -Richtlinie finden Sie unter [ExtensionInstallForcelist](https://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="c91d7-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span></span>

<span data-ttu-id="c91d7-113">Dieser Schritt ist eine Voraussetzung für die Verwendung von Chrome; das von Benutzern installierte S/MIME-Steuerelement wird nicht ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c91d7-113">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="c91d7-114">Benutzer werden aufgefordert, das s/MIME-Steuerelement in Outlook im Internet während der ersten Verwendung von s/MIME herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c91d7-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="c91d7-115">Oder können Benutzer proaktiv zu **S/MIME** in Ihren Outlook im Webeinstellungen wechseln, um den Download-Link für das Steuerelement abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c91d7-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="c91d7-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c91d7-116">For more information</span></span>

[<span data-ttu-id="c91d7-117">S/MIME für die Nachrichtensignierung und -verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="c91d7-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
