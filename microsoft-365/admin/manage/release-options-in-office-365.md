---
title: Einrichten der Standard- oder Zielversionsoptionen
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Erfahren Sie, wie Sie die Releaseoption für neue Produkt- und Featuresupdates im Microsoft 365 Admin Center einrichten.
ms.openlocfilehash: d3692f2e1cca58fec81f2ad492b9232d5576f99b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579254"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="84fd5-103">Einrichten der Standard- oder Zielversionsoptionen</span><span class="sxs-lookup"><span data-stu-id="84fd5-103">Set up the Standard or Targeted release options</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84fd5-104">Die in diesem Artikel beschriebenen Microsoft 365-Updates gelten für Microsoft 365, SharePoint Online und Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="84fd5-104">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="84fd5-105">Diese Veröffentlichungsoptionen sind gezielte Methoden zum Veröffentlichen von Änderungen an Microsoft 365, können jedoch nicht jederzeit oder für alle Updates garantiert werden.</span><span class="sxs-lookup"><span data-stu-id="84fd5-105">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="84fd5-106">Sie gelten nicht für Microsoft 365-Apps, Skype for Business, Microsoft Teams und verwandte Dienste.</span><span class="sxs-lookup"><span data-stu-id="84fd5-106">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="84fd5-107">Informationen zu Veröffentlichungsoptionen für Microsoft 365 Apps finden Sie unter Übersicht über [Updatekanäle für Microsoft 365 Apps](/deployoffice/overview-update-channels).</span><span class="sxs-lookup"><span data-stu-id="84fd5-107">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="84fd5-108">Mit Microsoft 365 erhalten Sie neue Produktupdates und Features, sobald sie verfügbar werden, anstatt alle paar Jahre kostspielige Updates zu tun.</span><span class="sxs-lookup"><span data-stu-id="84fd5-108">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="84fd5-109">Sie können die Bereitstellung dieser Updates für Ihre Organisation verwalten.</span><span class="sxs-lookup"><span data-stu-id="84fd5-109">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="84fd5-110">Beispielsweise können Sie sich für eine frühe Veröffentlichung (Early Release) registrieren, damit Ihre Organisation die Updates zuerst erhält.</span><span class="sxs-lookup"><span data-stu-id="84fd5-110">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="84fd5-111">Sie können festlegen, dass nur bestimmte Personen die Updates erhalten.</span><span class="sxs-lookup"><span data-stu-id="84fd5-111">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="84fd5-112">Alternativ können Sie beim standardmäßigen Veröffentlichungszeitplan (Standard Release) bleiben und die Updates später erhalten.</span><span class="sxs-lookup"><span data-stu-id="84fd5-112">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="84fd5-113">In diesem Artikel werden die verschiedenen Veröffentlichungsoptionen und ihre Verwendung für Ihre Organisation erläutert.</span><span class="sxs-lookup"><span data-stu-id="84fd5-113">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="84fd5-114">Funktionsweise - Releaseüberprüfung</span><span class="sxs-lookup"><span data-stu-id="84fd5-114">How it works - release validation</span></span>

<span data-ttu-id="84fd5-115">Jede neue Version wird zuerst vom Featureteam getestet und überprüft, dann vom gesamten Microsoft 365-Featureteam, gefolgt von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="84fd5-115">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="84fd5-116">Nach den internen Tests und Überprüfungen besteht der nächste Schritt in der Bereitstellung eines **Targeted Release** ("Gezielte Freigabe", vormals First Release) für Kunden, die die entsprechende Option aktivieren.</span><span class="sxs-lookup"><span data-stu-id="84fd5-116">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="84fd5-117">Bei jedem Release Ring sammelt Microsoft Feedback und führt durch die Überwachung der wichtigsten Nutzungsmetriken weitere Qualitätsprüfungen durch.</span><span class="sxs-lookup"><span data-stu-id="84fd5-117">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="84fd5-118">Diese Reihe von fortschreitenden Überprüfungen wurde eingeführt, um sicherzustellen, dass das weltweite Release so robust wie möglich ist.</span><span class="sxs-lookup"><span data-stu-id="84fd5-118">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="84fd5-119">Die Releases sind in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="84fd5-119">The releases are pictured in the following figure.</span></span> 
  
![Freigabeüberprüfungsringe für Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="84fd5-121">Bei wichtigen Updates werden Kunden zunächst über die [Microsoft 365 Roadmap benachrichtigt.](https://products.office.com/business/office-365-roadmap)</span><span class="sxs-lookup"><span data-stu-id="84fd5-121">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="84fd5-122">Wenn ein Update näher an das Roll-out heranrückt, wird es über Ihr [Microsoft 365 Message Center kommuniziert.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="84fd5-122">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="84fd5-123">Sie benötigen ein Microsoft 365- oder Azure AD-Konto, um über das Admin Center auf Ihr Nachrichtencenter [zu zugreifen.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="84fd5-123">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="84fd5-124">Microsoft 365-Homeplanbenutzer verfügen nicht über ein Admin Center.</span><span class="sxs-lookup"><span data-stu-id="84fd5-124">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="84fd5-125">Standard Release</span><span class="sxs-lookup"><span data-stu-id="84fd5-125">Standard release</span></span>

<span data-ttu-id="84fd5-126">Dies ist die Standardoption, bei der Sie und Ihre Benutzer die neuesten Updates erhalten, wenn sie allgemein für alle Kunden veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="84fd5-126">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="84fd5-127">Eine bewährte Methode ist es, die Mehrzahl der Benutzer in **standard** release und IT Pros und Power Users in **targeted release** zu lassen, um neue Features auszuwerten und Teams auf die Unterstützung von Geschäftsbenutzern und Führungskräften vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="84fd5-127">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="84fd5-128">Wenn Sie von "Targeted Release" zurück zu "Standard Release" wechseln, verlieren Ihre Benutzer möglicherweise Zugriff auf die Features, die noch nicht im Standard Release-Programm freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="84fd5-128">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="84fd5-129">Zielrelease</span><span class="sxs-lookup"><span data-stu-id="84fd5-129">Targeted release</span></span>

<span data-ttu-id="84fd5-p106">Mit dieser Option gehören Sie und Ihre Benutzer zu den ersten Personen, die die neuesten Updates erhalten, und können durch Ihr frühes Feedback bei der weiteren Gestaltung des Produkts helfen. Sie können wählen, ob einzelne Personen oder die gesamte Organisation die Aktualisierungen frühzeitig erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="84fd5-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="84fd5-p107">Große oder komplexe Updates können länger dauern als andere, sodass keine Benutzer beeinträchtigt werden. Es gibt keine Garantie für den genauen Freigabetermin einer Version.</span><span class="sxs-lookup"><span data-stu-id="84fd5-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="84fd5-134">Targeted Release für die gesamte Organisation</span><span class="sxs-lookup"><span data-stu-id="84fd5-134">Targeted release for entire organization</span></span>

<span data-ttu-id="84fd5-135">Wenn Sie [die Veröffentlichungsoption im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, erhalten alle Benutzer die Benutzererfahrung für die gezielte Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="84fd5-135">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="84fd5-136">Für Organisationen mit mehr als 300 Benutzern empfehlen wir die Verwendung eines Testabonnements für diese Option.</span><span class="sxs-lookup"><span data-stu-id="84fd5-136">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="84fd5-137">Wenden Sie für Informationen zum Testabonnement an Ihren Microsoft-Kontakt.</span><span class="sxs-lookup"><span data-stu-id="84fd5-137">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="84fd5-138">Gezielte Freigabe für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="84fd5-138">Targeted release for selected users</span></span>

<span data-ttu-id="84fd5-139">Wenn Sie [die Veröffentlichungsoption im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, können Sie bestimmte Benutzer , in der Regel Power Users, definieren, um frühzeitigen Zugriff auf Features und Funktionen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="84fd5-139">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="84fd5-140">Vorteile der gezielten Freigabe</span><span class="sxs-lookup"><span data-stu-id="84fd5-140">Benefits of Targeted release</span></span>

<span data-ttu-id="84fd5-141">Mit der gezielten Veröffentlichung können Administratoren, Änderungsmanager oder andere Personen, die für Microsoft 365-Updates verantwortlich sind, die anstehenden Änderungen vorbereiten, indem sie ihnen dies ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="84fd5-141">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="84fd5-142">Neue Updates testen und überprüfen, bevor diese für alle Benutzer in der Organisation freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="84fd5-142">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="84fd5-143">Benutzerbenachrichtigung und -dokumentation vorbereiten, bevor die Updates weltweit veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="84fd5-143">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="84fd5-144">Das interne Helpdesk auf anstehende Änderungen vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="84fd5-144">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="84fd5-145">Compliance- und Sicherheitsüberprüfungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="84fd5-145">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="84fd5-146">Featuresteuerelemente verwenden (sofern zutreffend), um die Veröffentlichung von Updates für Endbenutzer zu steuern.</span><span class="sxs-lookup"><span data-stu-id="84fd5-146">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="84fd5-147">Einrichten der Veröffentlichungsoption im Admin Center</span><span class="sxs-lookup"><span data-stu-id="84fd5-147">Set up the release option in the admin center</span></span>

<span data-ttu-id="84fd5-148">Sie können ändern, wie Ihre Organisation Microsoft 365-Updates empfängt, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="84fd5-148">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="84fd5-149">Sie müssen ein globaler Administrator in Microsoft 365 sein, um sich dafür zu entscheiden.</span><span class="sxs-lookup"><span data-stu-id="84fd5-149">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="84fd5-150">Es kann bis zu 24 Stunden dauern, bis die folgenden Änderungen in Microsoft 365 wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="84fd5-150">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="84fd5-151">Wenn Sie sich bei "Targeted Release" abmelden, nachdem Sie es zuvor aktiviert hatten, verlieren Ihre Benutzer möglicherweise Zugriff auf Features, deren geplanter Freigabetermin noch nicht erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="84fd5-151">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="84fd5-152">Wechseln Sie im Admin Center zur Einstellung Einstellung der Organisationseinstellungen, und wählen Sie unter der Registerkarte Organisationsprofil die Option  >   **Freigabeeinstellungen aus.** </span><span class="sxs-lookup"><span data-stu-id="84fd5-152">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="84fd5-153">Zum Deaktivieren der gezielten Veröffentlichung wählen Sie **Standardversion** aus, und wählen Sie **dann Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="84fd5-153">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="84fd5-154">Um die gezielte Veröffentlichung für alle Benutzer in Ihrer Organisation zu aktivieren, wählen Sie **Zielversion** für alle und dann **Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="84fd5-154">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="84fd5-155">Um die gezielte Veröffentlichung für einige Personen in Ihrer Organisation zu aktivieren, wählen Sie **Gezielte** Freigabe für ausgewählte Benutzer aus, und wählen Sie **dann Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="84fd5-155">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="84fd5-156">Wählen **Sie Benutzer** auswählen aus, um Benutzer gleichzeitig hinzuzufügen, oder **Laden** Sie Benutzer hoch, um sie in Massen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="84fd5-156">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="84fd5-157">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="84fd5-157">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="84fd5-158">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="84fd5-158">Learn more</span></span>

<span data-ttu-id="84fd5-159">Erfahren Sie, wie [Sie Nachrichten](/office365/admin/manage/message-center) in [Ihrem Microsoft 365 Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) verwalten, um Benachrichtigungen über anstehende Microsoft 365-Updates und -Versionen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="84fd5-159">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-articles"></a><span data-ttu-id="84fd5-160">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="84fd5-160">Related Articles</span></span>

[<span data-ttu-id="84fd5-161">Office Insider</span><span class="sxs-lookup"><span data-stu-id="84fd5-161">Office Insider</span></span>](https://insider.office.com/join/windows)
