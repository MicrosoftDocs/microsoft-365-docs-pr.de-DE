---
title: Verwalten der Zustimmung von Benutzern zu apps in Microsoft 365
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
description: Erfahren Sie mehr über die Benutzer Zustimmung zu apps und wie Sie Sie aktivieren, damit Drittanbieter-apps auf die Microsoft 365-Informationen von Benutzern zugreifen können.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999571"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="f7a6e-103">Verwalten der Zustimmung von Benutzern zu apps in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f7a6e-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="f7a6e-104">Mit dieser Einstellung wird gesteuert, ob Benutzer diese Zustimmung für apps erteilen können, die OpenID Connect und OAuth 2,0 für die Anmeldung und Anforderungen für den Zugriff auf Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7a6e-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="f7a6e-105">Eine APP kann in ihrer eigenen Organisation erstellt werden oder aus einer anderen Office 365 Organisation oder einem Drittanbieter stammen.</span><span class="sxs-lookup"><span data-stu-id="f7a6e-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="f7a6e-106">Wenn Sie diese Einstellung aktivieren, werden die Benutzer von diesen apps aufgefordert, die Berechtigungen für den Zugriff auf die Daten Ihrer Organisation aufzurufen, und die Benutzer können entscheiden, ob Sie Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="f7a6e-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="f7a6e-107">Wenn Sie diese Einstellung deaktivieren, müssen Administratoren diesen apps zustimmen, bevor Sie von Benutzern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f7a6e-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="f7a6e-108">In diesem Fall sollten Sie einen Administrator-Genehmigungsworkflow im Azure-Portal einrichten, damit Benutzer eine Anforderung zur Genehmigung des Administrators senden können, um eine blockierte APP zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7a6e-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="f7a6e-109">Ein Benutzer kann nur Apps, deren Besitzer er ist, Zugriff auf seine Office 365-Informationen gewähren.</span><span class="sxs-lookup"><span data-stu-id="f7a6e-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="f7a6e-110">Sie können einer App keinen Zugriff auf die Informationen anderer Benutzer gewähren.</span><span class="sxs-lookup"><span data-stu-id="f7a6e-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="f7a6e-111">Aktivieren oder Deaktivieren der Benutzer Zustimmung</span><span class="sxs-lookup"><span data-stu-id="f7a6e-111">Turning user consent on or off</span></span>
<span data-ttu-id="f7a6e-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="f7a6e-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="f7a6e-113">Hier erfahren Sie, wie Sie die Zustimmung von Benutzern zu Apps aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f7a6e-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="f7a6e-114">Wechseln Sie im Admin Center zur Seite **Einstellungen** für \> **Organisationseinstellungen** für  >  [Dienste](https://go.microsoft.com/fwlink/p/?linkid=2053743) , und wählen Sie dann **Benutzer Zustimmung für apps** aus.</span><span class="sxs-lookup"><span data-stu-id="f7a6e-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="f7a6e-115">Wählen Sie auf der Seite **Benutzer Zustimmung für apps** die Option aus, um die Benutzer Zustimmung ein-oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="f7a6e-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="f7a6e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7a6e-116">More info</span></span>
<span data-ttu-id="f7a6e-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="f7a6e-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="f7a6e-118">Informationen zum Konfigurieren ihrer Zustimmungs Einstellungen in Azure Active Directory finden Sie unter [Konfigurieren des Administrator-Genehmigungsworkflows](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span><span class="sxs-lookup"><span data-stu-id="f7a6e-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="f7a6e-119">Informationen zum Verwalten der Benutzer Zustimmung zu apps finden Sie unter [Verwalten der Zustimmung zu Anwendungen und bewerten von Zustimmungs Anforderungen](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span><span class="sxs-lookup"><span data-stu-id="f7a6e-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>