---
title: Verwalten der Zustimmung des Benutzers zu Apps in Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Erfahren Sie mehr über die Zustimmung des Benutzers zu Apps und darüber, wie Sie sie aktivieren, damit Apps von Drittanbietern auf die Benutzerinformationen Microsoft 365 können.
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914558"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="f320e-103">Verwalten der Zustimmung des Benutzers zu Apps in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f320e-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="f320e-104">Diese Einstellung steuert, ob Benutzer apps, die OpenID Verbinden und OAuth 2.0 für die Anmeldung und Anforderungen für den Zugriff auf Daten verwenden, diese Zustimmung erteilen können.</span><span class="sxs-lookup"><span data-stu-id="f320e-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="f320e-105">Eine App kann in Ihrer eigenen Organisation erstellt werden, oder sie kann von einer anderen organisation Office 365 oder von einem Drittanbieter stammen.</span><span class="sxs-lookup"><span data-stu-id="f320e-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="f320e-106">Wenn Sie diese Einstellung aktivieren, bitten diese Apps Benutzer um Die Berechtigung für den Zugriff auf die Daten Ihrer Organisation, und Benutzer können auswählen, ob sie zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="f320e-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="f320e-107">Wenn Sie diese Einstellung deaktivieren, müssen Administratoren diesen Apps zustimmen, bevor Benutzer sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f320e-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="f320e-108">In diesem Fall sollten Sie einen Administrator-Zustimmungsworkflow im Azure-Portal einrichten, damit Benutzer eine Administratorgenehmigungsanforderung senden können, um blockierte Apps zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f320e-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="f320e-109">Ein Benutzer kann nur Apps, deren Besitzer er ist, Zugriff auf seine Office 365-Informationen gewähren.</span><span class="sxs-lookup"><span data-stu-id="f320e-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="f320e-110">Sie können einer App keinen Zugriff auf die Informationen anderer Benutzer gewähren.</span><span class="sxs-lookup"><span data-stu-id="f320e-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="f320e-111">Aktivieren oder Deaktivieren der Zustimmung des Benutzers</span><span class="sxs-lookup"><span data-stu-id="f320e-111">Turning user consent on or off</span></span>
<span data-ttu-id="f320e-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="f320e-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="f320e-113">Hier erfahren Sie, wie Sie die Zustimmung des Benutzers zu Apps aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f320e-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="f320e-114">Wechseln Sie im Admin Center zur Seite **Einstellungen** Organisationseinstellungen Dienste, und wählen Sie dann \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) **Benutzer-Zustimmung zu Apps aus.**</span><span class="sxs-lookup"><span data-stu-id="f320e-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="f320e-115">Wählen Sie **auf der** Seite Benutzer-Zustimmung zu Apps die Option aus, um die Zustimmung des Benutzers ein- oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="f320e-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="f320e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f320e-116">More info</span></span>
<span data-ttu-id="f320e-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="f320e-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="f320e-118">Informationen zum Konfigurieren Ihrer Zustimmungseinstellungen in Azure Active Directory finden Sie unter [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span><span class="sxs-lookup"><span data-stu-id="f320e-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="f320e-119">Weitere Informationen zum Verwalten der Zustimmung des Benutzers zu Apps finden Sie unter [Managing consent to applications und evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests).</span><span class="sxs-lookup"><span data-stu-id="f320e-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests).</span></span>