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
description: Erfahren Sie, wie Sie die Releaseoption für neue Produkt- und Featuresupdates im Microsoft 365 einrichten.
ms.openlocfilehash: 5060e2dc99355d89928ec91c96b7d25e2016c7c4
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593945"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="6b72f-103">Einrichten der Standard- oder Zielversionsoptionen</span><span class="sxs-lookup"><span data-stu-id="6b72f-103">Set up the Standard or Targeted release options</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b72f-104">Die Microsoft 365 in diesem Artikel beschriebenen Updates gelten für Microsoft 365, SharePoint Online und Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6b72f-104">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="6b72f-105">Diese Veröffentlichungsoptionen sind zielgerichtete Methoden, um Änderungen an Microsoft 365 zu veröffentlichen, können jedoch nicht jederzeit oder für alle Updates garantiert werden.</span><span class="sxs-lookup"><span data-stu-id="6b72f-105">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="6b72f-106">Sie gelten nicht für Microsoft 365 Apps, Skype for Business, Microsoft Teams und zugehörige Dienste.</span><span class="sxs-lookup"><span data-stu-id="6b72f-106">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="6b72f-107">Informationen zu Veröffentlichungsoptionen für Microsoft 365 Apps finden Sie [unter Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span><span class="sxs-lookup"><span data-stu-id="6b72f-107">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="6b72f-108">Mit Microsoft 365 erhalten Sie neue Produktupdates und Features, sobald sie verfügbar werden, anstatt alle paar Jahre kostspielige Updates zu tun.</span><span class="sxs-lookup"><span data-stu-id="6b72f-108">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="6b72f-109">Sie können die Bereitstellung dieser Updates für Ihre Organisation verwalten.</span><span class="sxs-lookup"><span data-stu-id="6b72f-109">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="6b72f-110">Beispielsweise können Sie sich für eine frühe Veröffentlichung (Early Release) registrieren, damit Ihre Organisation die Updates zuerst erhält.</span><span class="sxs-lookup"><span data-stu-id="6b72f-110">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="6b72f-111">Sie können festlegen, dass nur bestimmte Personen die Updates erhalten.</span><span class="sxs-lookup"><span data-stu-id="6b72f-111">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="6b72f-112">Alternativ können Sie beim standardmäßigen Veröffentlichungszeitplan (Standard Release) bleiben und die Updates später erhalten.</span><span class="sxs-lookup"><span data-stu-id="6b72f-112">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="6b72f-113">In diesem Artikel werden die verschiedenen Veröffentlichungsoptionen und ihre Verwendung für Ihre Organisation erläutert.</span><span class="sxs-lookup"><span data-stu-id="6b72f-113">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="6b72f-114">Funktionsweise - Releaseüberprüfung</span><span class="sxs-lookup"><span data-stu-id="6b72f-114">How it works - release validation</span></span>

<span data-ttu-id="6b72f-115">Jede neue Version wird zuerst vom Featureteam getestet und überprüft, dann vom gesamten Microsoft 365-Featureteam, gefolgt von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b72f-115">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="6b72f-116">Nach den internen Tests und Überprüfungen besteht der nächste Schritt in der Bereitstellung eines **Targeted Release** ("Gezielte Freigabe", vormals First Release) für Kunden, die die entsprechende Option aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6b72f-116">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="6b72f-117">Bei jedem Release Ring sammelt Microsoft Feedback und führt durch die Überwachung der wichtigsten Nutzungsmetriken weitere Qualitätsprüfungen durch.</span><span class="sxs-lookup"><span data-stu-id="6b72f-117">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="6b72f-118">Diese Reihe von fortschreitenden Überprüfungen wurde eingeführt, um sicherzustellen, dass das weltweite Release so robust wie möglich ist.</span><span class="sxs-lookup"><span data-stu-id="6b72f-118">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="6b72f-119">Die Releases sind in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6b72f-119">The releases are pictured in the following figure.</span></span> 
  
![Freigabeüberprüfungsringe für Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="6b72f-121">Bei wichtigen Updates werden Kunden zunächst von der Microsoft 365 [benachrichtigt.](https://products.office.com/business/office-365-roadmap)</span><span class="sxs-lookup"><span data-stu-id="6b72f-121">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="6b72f-122">Wenn ein Update näher an das Roll-out heranrückt, wird es über Ihr Microsoft 365 [Message Center kommuniziert.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="6b72f-122">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="6b72f-123">Sie benötigen ein Microsoft 365 oder Azure AD-Konto, um über das Admin Center auf Ihr Nachrichtencenter [zu zugreifen.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="6b72f-123">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="6b72f-124">Microsoft 365 Heimplanbenutzer verfügen nicht über ein Admin Center.</span><span class="sxs-lookup"><span data-stu-id="6b72f-124">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="6b72f-125">Standard Release</span><span class="sxs-lookup"><span data-stu-id="6b72f-125">Standard release</span></span>

<span data-ttu-id="6b72f-126">Dies ist die Standardoption, bei der Sie und Ihre Benutzer die neuesten Updates erhalten, wenn sie allgemein für alle Kunden veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="6b72f-126">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="6b72f-127">Eine bewährte Methode ist es, die Mehrzahl der Benutzer in **standard** release und IT Pros und Power Users in **targeted release** zu lassen, um neue Features auszuwerten und Teams auf die Unterstützung von Geschäftsbenutzern und Führungskräften vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="6b72f-127">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6b72f-128">Wenn Sie von "Targeted Release" zurück zu "Standard Release" wechseln, verlieren Ihre Benutzer möglicherweise Zugriff auf die Features, die noch nicht im Standard Release-Programm freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="6b72f-128">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="6b72f-129">Zielrelease</span><span class="sxs-lookup"><span data-stu-id="6b72f-129">Targeted release</span></span>

<span data-ttu-id="6b72f-p106">Mit dieser Option gehören Sie und Ihre Benutzer zu den ersten Personen, die die neuesten Updates erhalten, und können durch Ihr frühes Feedback bei der weiteren Gestaltung des Produkts helfen. Sie können wählen, ob einzelne Personen oder die gesamte Organisation die Aktualisierungen frühzeitig erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="6b72f-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6b72f-p107">Große oder komplexe Updates können länger dauern als andere, sodass keine Benutzer beeinträchtigt werden. Es gibt keine Garantie für den genauen Freigabetermin einer Version.</span><span class="sxs-lookup"><span data-stu-id="6b72f-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="6b72f-134">Targeted Release für die gesamte Organisation</span><span class="sxs-lookup"><span data-stu-id="6b72f-134">Targeted release for entire organization</span></span>

<span data-ttu-id="6b72f-135">Wenn Sie [die Veröffentlichungsoption im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, erhalten alle Benutzer die Benutzererfahrung für die gezielte Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="6b72f-135">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="6b72f-136">Für Organisationen mit mehr als 300 Benutzern empfehlen wir die Verwendung eines Testabonnements für diese Option.</span><span class="sxs-lookup"><span data-stu-id="6b72f-136">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="6b72f-137">Wenden Sie für Informationen zum Testabonnement an Ihren Microsoft-Kontakt.</span><span class="sxs-lookup"><span data-stu-id="6b72f-137">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="6b72f-138">Gezielte Freigabe für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="6b72f-138">Targeted release for selected users</span></span>

<span data-ttu-id="6b72f-139">Wenn Sie [die Veröffentlichungsoption im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, können Sie bestimmte Benutzer , in der Regel Power Users, definieren, um frühzeitigen Zugriff auf Features und Funktionen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6b72f-139">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="6b72f-140">Vorteile der gezielten Freigabe</span><span class="sxs-lookup"><span data-stu-id="6b72f-140">Benefits of Targeted release</span></span>

<span data-ttu-id="6b72f-141">Mit der gezielten Veröffentlichung können Administratoren, Änderungsmanager oder andere Personen, die für Microsoft 365 updates verantwortlich sind, die anstehenden Änderungen vorbereiten, indem sie ihnen dies ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="6b72f-141">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="6b72f-142">Neue Updates testen und überprüfen, bevor diese für alle Benutzer in der Organisation freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6b72f-142">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="6b72f-143">Benutzerbenachrichtigung und -dokumentation vorbereiten, bevor die Updates weltweit veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="6b72f-143">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="6b72f-144">Das interne Helpdesk auf anstehende Änderungen vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="6b72f-144">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="6b72f-145">Compliance- und Sicherheitsüberprüfungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="6b72f-145">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="6b72f-146">Featuresteuerelemente verwenden (sofern zutreffend), um die Veröffentlichung von Updates für Endbenutzer zu steuern.</span><span class="sxs-lookup"><span data-stu-id="6b72f-146">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="6b72f-147">Einrichten der Veröffentlichungsoption im Admin Center</span><span class="sxs-lookup"><span data-stu-id="6b72f-147">Set up the release option in the admin center</span></span>

<span data-ttu-id="6b72f-148">Sie können ändern, wie Ihre Organisation Microsoft 365 erhält, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="6b72f-148">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="6b72f-149">Sie müssen ein globaler Administrator sein, Microsoft 365 sich dafür entscheiden können.</span><span class="sxs-lookup"><span data-stu-id="6b72f-149">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6b72f-150">Es kann bis zu 24 Stunden dauern, bis die folgenden Änderungen in der Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6b72f-150">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="6b72f-151">Wenn Sie sich bei "Targeted Release" abmelden, nachdem Sie es zuvor aktiviert hatten, verlieren Ihre Benutzer möglicherweise Zugriff auf Features, deren geplanter Freigabetermin noch nicht erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="6b72f-151">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="6b72f-152">Wechseln Sie im Admin Center zur Einstellung **Einstellungen**  >  **Organisationseinstellungen,** und wählen Sie auf der Registerkarte Organisationsprofil die Option  **Freigabeeinstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="6b72f-152">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="6b72f-153">Zum Deaktivieren der gezielten Veröffentlichung wählen Sie **Standardversion** aus, und wählen Sie **dann Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="6b72f-153">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="6b72f-154">Um die gezielte Veröffentlichung für alle Benutzer in Ihrer Organisation zu aktivieren, wählen Sie **Zielversion** für alle und dann **Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="6b72f-154">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="6b72f-155">Um die gezielte Veröffentlichung für einige Personen in Ihrer Organisation zu aktivieren, wählen Sie **Gezielte** Freigabe für ausgewählte Benutzer aus, und wählen Sie **dann Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="6b72f-155">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="6b72f-156">Wählen **Sie Benutzer** auswählen aus, um Benutzer eins nach dem **anderen** hinzuzufügen, oder Hochladen Benutzer zum Massen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6b72f-156">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="6b72f-157">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="6b72f-157">When you're done adding users, select **Save changes**.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="6b72f-158">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6b72f-158">Next steps</span></span>

<span data-ttu-id="6b72f-159">Erfahren Sie, [wie Sie](/office365/admin/manage/message-center) Nachrichten in Ihrem [Microsoft 365 Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) verwalten, um Benachrichtigungen über bevorstehende Microsoft 365 und Veröffentlichungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6b72f-159">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-content"></a><span data-ttu-id="6b72f-160">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="6b72f-160">Related content</span></span>

<span data-ttu-id="6b72f-161">[Teilnehmen am Office Insider Program](https://insider.office.com/join/windows) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6b72f-161">[Join the Office Insider Program](https://insider.office.com/join/windows) (article)</span></span>
