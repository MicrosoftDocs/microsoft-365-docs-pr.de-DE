---
title: Einrichten der Standard-oder Targeted Release-Optionen
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Erfahren Sie, wie Sie die Option "Release" für neue Produkt-und Funktionsupdates im Microsoft 365 Admin Center einrichten.
ms.openlocfilehash: 2738cf7af32d2e15b0c2c790a241dabbb1f104bc
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262317"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="841bf-103">Einrichten der Standard-oder Targeted Release-Optionen</span><span class="sxs-lookup"><span data-stu-id="841bf-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="841bf-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="841bf-104">The admin center is changing.</span></span> <span data-ttu-id="841bf-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="841bf-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="841bf-106">Mit Microsoft 365 erhalten Sie neue Produktupdates und-Features, sobald diese verfügbar sind, statt kostspielige Updates alle paar Jahre durchführen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="841bf-106">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="841bf-107">Sie können die Bereitstellung dieser Updates für Ihre Organisation verwalten.</span><span class="sxs-lookup"><span data-stu-id="841bf-107">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="841bf-108">Beispielsweise können Sie sich für eine frühe Veröffentlichung (Early Release) registrieren, damit Ihre Organisation die Updates zuerst erhält.</span><span class="sxs-lookup"><span data-stu-id="841bf-108">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="841bf-109">Sie können festlegen, dass nur bestimmte Personen die Updates erhalten.</span><span class="sxs-lookup"><span data-stu-id="841bf-109">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="841bf-110">Alternativ können Sie beim standardmäßigen Veröffentlichungszeitplan (Standard Release) bleiben und die Updates später erhalten.</span><span class="sxs-lookup"><span data-stu-id="841bf-110">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="841bf-111">In diesem Artikel werden die verschiedenen Veröffentlichungsoptionen und ihre Verwendung für Ihre Organisation erläutert.</span><span class="sxs-lookup"><span data-stu-id="841bf-111">This article explains the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="841bf-112">Die in diesem Artikel beschriebenen Microsoft 365-Updates gelten für Microsoft 365, SharePoint Online und Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="841bf-112">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="841bf-113">Sie gelten nicht für Skype for Business und zugehörige Dienste.</span><span class="sxs-lookup"><span data-stu-id="841bf-113">They do not apply to Skype for Business and related services.</span></span> <span data-ttu-id="841bf-114">Diese Veröffentlichungsoptionen sind gezielte, bestmögliche Methoden zum Freigeben von Änderungen an Microsoft 365, die jedoch nicht zu jedem Zeitpunkt oder für alle Updates garantiert werden können.</span><span class="sxs-lookup"><span data-stu-id="841bf-114">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="841bf-115">Funktionsweise - Releaseüberprüfung</span><span class="sxs-lookup"><span data-stu-id="841bf-115">How it works - release validation</span></span>

<span data-ttu-id="841bf-116">Jede neue Version wird zuerst vom Feature-Team getestet und validiert, dann durch das gesamte Microsoft 365-Feature-Team, gefolgt von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="841bf-116">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="841bf-117">Nach den internen Tests und Überprüfungen besteht der nächste Schritt in der Bereitstellung eines **Targeted Release** ("Gezielte Freigabe", vormals First Release) für Kunden, die die entsprechende Option aktivieren.</span><span class="sxs-lookup"><span data-stu-id="841bf-117">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="841bf-118">Bei jedem Release Ring sammelt Microsoft Feedback und führt durch die Überwachung der wichtigsten Nutzungsmetriken weitere Qualitätsprüfungen durch.</span><span class="sxs-lookup"><span data-stu-id="841bf-118">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="841bf-119">Diese Reihe von fortschreitenden Überprüfungen wurde eingeführt, um sicherzustellen, dass das weltweite Release so robust wie möglich ist.</span><span class="sxs-lookup"><span data-stu-id="841bf-119">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="841bf-120">Die Releases sind in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="841bf-120">The releases are pictured in the following figure.</span></span> 
  
![Release-Überprüfungs Ringe für Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="841bf-122">Für wichtige Updates werden Kunden zunächst durch die [Microsoft 365-Roadmap](https://products.office.com/business/office-365-roadmap)benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="841bf-122">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="841bf-123">Wenn ein Update dem Rollout näher kommt, wird es über Ihr [Microsoft 365-Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="841bf-123">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="841bf-124">Sie benötigen ein Microsoft 365-oder Azure AD-Konto, um über das [Admin Center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)auf Ihr Nachrichtencenter zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="841bf-124">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="841bf-125">Microsoft 365 Home Plan Benutzer verfügen nicht über ein Admin Center.</span><span class="sxs-lookup"><span data-stu-id="841bf-125">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="841bf-126">Standard Release</span><span class="sxs-lookup"><span data-stu-id="841bf-126">Standard release</span></span>

<span data-ttu-id="841bf-127">Dies ist die Standardoption, bei der Sie und Ihre Benutzer die neuesten Updates erhalten, wenn Sie allgemein für alle Kunden freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="841bf-127">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="841bf-128">Eine bewährte Methode besteht darin, die Mehrzahl der Benutzer in der **gezielten** Version von **Standard Version** und IT-Experten und Hauptbenutzern zu belassen, um neue Features auszuwerten und Teams zur Unterstützung von Geschäftsbenutzern und Führungskräften vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="841bf-128">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="841bf-129">Wenn Sie von "Targeted Release" zurück zu "Standard Release" wechseln, verlieren Ihre Benutzer möglicherweise Zugriff auf die Features, die noch nicht im Standard Release-Programm freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="841bf-129">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="841bf-130">Zielrelease</span><span class="sxs-lookup"><span data-stu-id="841bf-130">Targeted release</span></span>

<span data-ttu-id="841bf-p107">Mit dieser Option gehören Sie und Ihre Benutzer zu den ersten Personen, die die neuesten Updates erhalten, und können durch Ihr frühes Feedback bei der weiteren Gestaltung des Produkts helfen. Sie können wählen, ob einzelne Personen oder die gesamte Organisation die Aktualisierungen frühzeitig erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="841bf-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="841bf-p108">Große oder komplexe Updates können länger dauern als andere, sodass keine Benutzer beeinträchtigt werden. Es gibt keine Garantie für den genauen Freigabetermin einer Version.</span><span class="sxs-lookup"><span data-stu-id="841bf-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="841bf-135">Targeted Release für die gesamte Organisation</span><span class="sxs-lookup"><span data-stu-id="841bf-135">Targeted release for entire organization</span></span>

<span data-ttu-id="841bf-136">Wenn Sie [die Option "Release" im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, erhalten alle Ihre Benutzer die gezielte Veröffentlichungs Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="841bf-136">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="841bf-137">Für Organisationen mit mehr als 300 Benutzern empfehlen wir die Verwendung eines Testabonnements für diese Option.</span><span class="sxs-lookup"><span data-stu-id="841bf-137">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="841bf-138">Wenden Sie für Informationen zum Testabonnement an Ihren Microsoft-Kontakt.</span><span class="sxs-lookup"><span data-stu-id="841bf-138">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="841bf-139">Gezielte Freigabe für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="841bf-139">Targeted release for selected users</span></span>

<span data-ttu-id="841bf-140">Wenn Sie [die Option Release im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, können Sie bestimmte Benutzer (in der Regel Hauptbenutzer) definieren, um frühzeitigen Zugriff auf Features und Funktionen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="841bf-140">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="841bf-141">Vorteile der gezielten Freigabe</span><span class="sxs-lookup"><span data-stu-id="841bf-141">Benefits of Targeted release</span></span>

<span data-ttu-id="841bf-142">Targeted Release ermöglicht Administratoren, Änderungs Managern oder anderen Verantwortlichen für Microsoft 365-Updates die Vorbereitung auf die bevorstehenden Änderungen, indem Sie Ihnen Folgendes zulässt:</span><span class="sxs-lookup"><span data-stu-id="841bf-142">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="841bf-143">Neue Updates testen und überprüfen, bevor diese für alle Benutzer in der Organisation freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="841bf-143">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="841bf-144">Benutzerbenachrichtigung und -dokumentation vorbereiten, bevor die Updates weltweit veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="841bf-144">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="841bf-145">Das interne Helpdesk auf anstehende Änderungen vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="841bf-145">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="841bf-146">Compliance- und Sicherheitsüberprüfungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="841bf-146">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="841bf-147">Featuresteuerelemente verwenden (sofern zutreffend), um die Veröffentlichung von Updates für Endbenutzer zu steuern.</span><span class="sxs-lookup"><span data-stu-id="841bf-147">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="841bf-148">Einrichten der Option "Version" im Admin Center</span><span class="sxs-lookup"><span data-stu-id="841bf-148">Set up the release option in the admin center</span></span>

<span data-ttu-id="841bf-149">Sie können die Art und Weise ändern, wie Ihre Organisation Microsoft 365-Updates erhält, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="841bf-149">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="841bf-150">Sie müssen ein globaler Administrator in Microsoft 365 sein, um sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="841bf-150">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="841bf-151">Es kann bis zu 24 Stunden dauern, bis die folgenden Änderungen in Microsoft 365 wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="841bf-151">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="841bf-152">Wenn Sie sich bei "Targeted Release" abmelden, nachdem Sie es zuvor aktiviert hatten, verlieren Ihre Benutzer möglicherweise Zugriff auf Features, deren geplanter Freigabetermin noch nicht erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="841bf-152">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="841bf-153">Wechseln Sie im Admin Center zur **Settings**  >  **Einstellung org**(Einstellungen), und wählen Sie auf der Registerkarte **Organisationsprofil** die Option **Freigabeeinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="841bf-153">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="841bf-154">Um die Zielversion zu deaktivieren, wählen Sie **Standard Version**aus, und wählen Sie dann **Änderungen speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="841bf-154">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="841bf-155">Um die gezielte Freigabe für alle Benutzer in Ihrer Organisation zu aktivieren, wählen Sie **Targeted Release for everyone**aus, und wählen Sie dann **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="841bf-155">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="841bf-156">Um eine gezielte Freigabe für einige Personen in Ihrer Organisation zu aktivieren, wählen Sie **Targeted Release für ausgewählte Benutzer**aus, und wählen Sie dann **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="841bf-156">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="841bf-157">Wählen **Sie Benutzer auswählen** aus, um Benutzer nacheinander hinzuzufügen, oder **Laden Sie Benutzer** zum Massen hinzufügen ein.</span><span class="sxs-lookup"><span data-stu-id="841bf-157">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="841bf-158">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="841bf-158">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="841bf-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="841bf-159">Learn more</span></span>

<span data-ttu-id="841bf-160">Erfahren Sie, wie Sie [Nachrichten](https://docs.microsoft.com/office365/admin/manage/message-center) in Ihrem [Microsoft 365-Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) verwalten, um Benachrichtigungen zu bevorstehenden Updates und Versionen von Microsoft 365 zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="841bf-160">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
