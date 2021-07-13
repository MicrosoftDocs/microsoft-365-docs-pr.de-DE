---
title: Verwalten der Benutzerzustimmung für Apps in Microsoft 365
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Erfahren Sie mehr über die Zustimmung der Benutzer zu Apps und wie Sie sie aktivieren können, um Drittanbieter-Apps den Zugriff auf Microsoft 365 Informationen von Benutzern zu ermöglichen.
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391231"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="4e715-103">Verwalten der Benutzerzustimmung für Apps in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e715-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="4e715-104">Mit dieser Einstellung wird gesteuert, ob Benutzer apps zustimmen können, die OpenID Verbinden und OAuth 2.0 für die Anmeldung und Anforderungen für den Zugriff auf Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e715-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="4e715-105">Eine App kann innerhalb Ihrer eigenen Organisation erstellt werden, oder sie kann von einer anderen Office 365 Organisation oder einem Drittanbieter stammen.</span><span class="sxs-lookup"><span data-stu-id="4e715-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="4e715-106">Wenn Sie diese Einstellung aktivieren, werden die Benutzer von diesen Apps um die Berechtigung für den Zugriff auf die Daten Ihrer Organisation gebeten, und Benutzer können auswählen, ob sie dies zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="4e715-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="4e715-107">Wenn Sie diese Einstellung deaktivieren, müssen Administratoren diesen Apps zustimmen, bevor Benutzer sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4e715-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="4e715-108">In diesem Fall sollten Sie einen Administratorzustimmungsworkflow im Azure-Portal einrichten, damit Benutzer eine Anforderung zur Administratorgenehmigung senden können, um blockierte Apps zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e715-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="4e715-109">Ein Benutzer kann nur Apps, deren Besitzer er ist, Zugriff auf seine Office 365-Informationen gewähren.</span><span class="sxs-lookup"><span data-stu-id="4e715-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="4e715-110">Sie können einer App keinen Zugriff auf die Informationen anderer Benutzer gewähren.</span><span class="sxs-lookup"><span data-stu-id="4e715-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="4e715-111">Aktivieren oder Deaktivieren der Zustimmung des Benutzers</span><span class="sxs-lookup"><span data-stu-id="4e715-111">Turning user consent on or off</span></span>

<span data-ttu-id="4e715-112">Hier erfahren Sie, wie Sie die Benutzerzustimmung für Apps aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4e715-112">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="4e715-113">Wechseln Sie im Admin Center zur Seite **Einstellungen** Dienste für \> **Organisationseinstellungen,**  >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) und wählen Sie dann die Zustimmung des Benutzers **zu Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="4e715-113">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="4e715-114">Wählen Sie auf der Seite **"Benutzerzustimmung für Apps"** die Option zum Aktivieren oder Deaktivieren der Benutzerzustimmung aus.</span><span class="sxs-lookup"><span data-stu-id="4e715-114">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="related-content"></a><span data-ttu-id="4e715-115">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="4e715-115">Related content</span></span> 

<span data-ttu-id="4e715-116">[Konfigurieren des Workflows für die Administratorzustimmung](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="4e715-116">[Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (article)</span></span>\
<span data-ttu-id="4e715-117">[Verwalten der Zustimmung zu Anwendungen und Auswerten von Zustimmungsanforderungen](/azure/active-directory/manage-apps/manage-consent-requests) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="4e715-117">[Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests) (article)</span></span>