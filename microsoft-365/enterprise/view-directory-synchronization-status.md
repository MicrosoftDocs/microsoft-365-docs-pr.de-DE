---
title: Anzeigen des Status der Verzeichnissynchronisierung in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: In diesem Artikel erfahren Sie, wie Sie den Status Ihrer Verzeichnissynchronisierung in Office 365 überprüfen können.
ms.openlocfilehash: c77898b58b58c6ae91492debd7ad66f395d80d52
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690626"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="63150-103">Anzeigen des Status der Verzeichnissynchronisierung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63150-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="63150-104">Wenn Sie Ihre lokale Active Directory mit Azure AD durch Synchronisieren Ihrer lokalen Umgebung mit Microsoft 365 integriert haben, können Sie auch den Status der Synchronisierung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="63150-104">If you have integrated your on-premises Active Directory with Azure AD by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="63150-105">Anzeigen des Status der Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="63150-105">View directory synchronization status</span></span>

- <span data-ttu-id="63150-106">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an, und wählen Sie auf der Startseite **Dirsync-Status** aus.</span><span class="sxs-lookup"><span data-stu-id="63150-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="63150-107">Alternativ können Sie zu " **Benutzer** \> **aktive**Benutzer" wechseln und auf der Seite " **aktive Benutzer** " **Weitere** \> **Verzeichnis Synchronisierungen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="63150-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="63150-108">Wählen Sie im Bereich **Verzeichnissynchronisierung** die Option **zu Dirsync-Verwaltung wechseln**aus.</span><span class="sxs-lookup"><span data-stu-id="63150-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="63150-109">Informationen auf der Seite "Verzeichnissynchronisierung verwalten"</span><span class="sxs-lookup"><span data-stu-id="63150-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="63150-110">In der folgenden Tabelle sind die Features aufgeführt, auf denen Sie auf der Seite Informationen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="63150-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="63150-111">Wenn ein Problem mit der Verzeichnissynchronisierung vorliegt, werden die Fehler auch auf dieser Seite aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="63150-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="63150-112">Weitere Informationen zu unterschiedlichen Fehlern, die auftreten können, finden Sie unter [Identifizieren von Verzeichnis Synchronisierungsfehlern in Microsoft 365](identify-directory-synchronization-errors.md).</span><span class="sxs-lookup"><span data-stu-id="63150-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="63150-113">**Aspekt**</span><span class="sxs-lookup"><span data-stu-id="63150-113">**Item**</span></span>|<span data-ttu-id="63150-114">**Zweck**</span><span class="sxs-lookup"><span data-stu-id="63150-114">**What it's for**</span></span>|
|:-----|:-----|
|<span data-ttu-id="63150-115">**Domänen überprüft**</span><span class="sxs-lookup"><span data-stu-id="63150-115">**Domains verified**</span></span> | <span data-ttu-id="63150-116">Die Anzahl der Domänen in Ihrem Microsoft 365-Mandanten, die Sie selbst überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="63150-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="63150-117">**Domänen nicht überprüft**</span><span class="sxs-lookup"><span data-stu-id="63150-117">**Domains not verified**</span></span> | <span data-ttu-id="63150-118">Domänen, die Sie hinzugefügt, aber nicht überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="63150-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="63150-119">**Verzeichnissynchronisierung aktiviert**</span><span class="sxs-lookup"><span data-stu-id="63150-119">**Directory sync enabled**</span></span> |<span data-ttu-id="63150-120">True oder false.</span><span class="sxs-lookup"><span data-stu-id="63150-120">True or False.</span></span> <span data-ttu-id="63150-121">Gibt an, ob die Verzeichnissynchronisierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="63150-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="63150-122">**Neueste Verzeichnissynchronisierung**</span><span class="sxs-lookup"><span data-stu-id="63150-122">**Latest directory sync**</span></span> | <span data-ttu-id="63150-123">Zeitpunkt der letzten Verzeichnissynchronisierung wurde ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="63150-123">Last time directory sync ran.</span></span> <span data-ttu-id="63150-124">Zeigt eine Warnung und einen Link zu einem Tool zur Problembehandlung an, wenn die letzte Synchronisierung vor mehr als drei Tagen stattfand.</span><span class="sxs-lookup"><span data-stu-id="63150-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="63150-125">**Kennwortsynchronisierung aktiviert**</span><span class="sxs-lookup"><span data-stu-id="63150-125">**Password sync enabled**</span></span> | <span data-ttu-id="63150-126">True oder false.</span><span class="sxs-lookup"><span data-stu-id="63150-126">True or False.</span></span> <span data-ttu-id="63150-127">Gibt an, ob eine Kennworthash Synchronisierung zwischen unserem lokalen und Ihrem Microsoft 365-Mandanten vorliegt.</span><span class="sxs-lookup"><span data-stu-id="63150-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="63150-128">**Letzte Kennwortsynchronisierung**</span><span class="sxs-lookup"><span data-stu-id="63150-128">**Last Password Sync**</span></span> | <span data-ttu-id="63150-129">Das letzte Mal, als Password Hash Sync ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="63150-129">Last time password hash sync ran.</span></span> <span data-ttu-id="63150-130">Zeigt eine Warnung und einen Link zu einem Tool zur Problembehandlung an, wenn die letzte Synchronisierung vor mehr als drei Tagen stattfand.</span><span class="sxs-lookup"><span data-stu-id="63150-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="63150-131">**Version des Verzeichnis Synchronisierungs Clients**</span><span class="sxs-lookup"><span data-stu-id="63150-131">**Directory sync client version**</span></span> | <span data-ttu-id="63150-132">Enthält einen Download Link, wenn eine neue Version von Azure AD Connect veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="63150-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="63150-133">**Verzeichnissynchronisierungsdienst Konto**</span><span class="sxs-lookup"><span data-stu-id="63150-133">**Directory sync service account**</span></span> | <span data-ttu-id="63150-134">Zeigt den Namen Ihres Microsoft 365-Verzeichnissynchronisierungsdienst Kontos an.</span><span class="sxs-lookup"><span data-stu-id="63150-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |