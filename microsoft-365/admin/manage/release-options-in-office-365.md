---
title: Einrichten der Standard oder Targeted Release-Optionen in Office 365
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
ms.openlocfilehash: 2d4940003c791e50926eff46aaf6a299e60fb9aa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252798"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a><span data-ttu-id="1fe17-103">Einrichten der Standard oder Targeted Release-Optionen in Office 365</span><span class="sxs-lookup"><span data-stu-id="1fe17-103">Set up the Standard or Targeted release options in Office 365</span></span>

<span data-ttu-id="1fe17-p101">[] Mit Office 365 erhalten Sie neue Produktupdates und -features, sobald diese verfügbar werden, und müssen nicht alle paar Jahre teure Updates erwerben. Sie können die Bereitstellung dieser Updates für Ihre Organisation verwalten. Beispielsweise können Sie sich für eine frühe Veröffentlichung (Early Release) registrieren, damit Ihre Organisation die Updates zuerst erhält. Sie können festlegen, dass nur bestimmte Personen die Updates erhalten. Alternativ können Sie beim standardmäßigen Veröffentlichungszeitplan (Standard Release) bleiben und die Updates später erhalten. In diesem Artikel werden die verschiedenen Optionen vorgestellt und es wird deren Verwendung für Ihre Organisation erläutert.</span><span class="sxs-lookup"><span data-stu-id="1fe17-p101">With Office 365, you receive new product updates and features as they become available instead of doing costly updates every few years. You can manage how your organization receives these updates. For example, you can sign up for an early release so that your organization receives updates first. You can designate that only certain individuals receive the updates. Or, you can remain on the default release schedule and receive the updates later. This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1fe17-p102">Die in diesem Artikel beschriebenen Office 365-Updates gelten für Office 365, SharePoint Online und Exchange Online. Sie gelten nicht für Skype for Business und zugehörige Dienste. Diese Release-Optionen sind zielgerichtete, nach bestem Bemühen entwickelte Möglichkeiten, Änderungen in Office 365 zu veröffentlichen, sie können aber nicht immer und nicht für alle Updates garantiert werden.</span><span class="sxs-lookup"><span data-stu-id="1fe17-p102">The Office 365 updates described in this article apply to Office 365, SharePoint Online, and Exchange Online. They do not apply to Skype for Business and related services. These release options are targeted, best effort ways to release changes to Office 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="1fe17-113">Funktionsweise - Releaseüberprüfung</span><span class="sxs-lookup"><span data-stu-id="1fe17-113">How it works - release validation</span></span>

<span data-ttu-id="1fe17-114">Jede neue Version wird zuerst vom Feature-Team getestet und validiert, dann durch das gesamte Office 365-Feature-Team, gefolgt von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1fe17-114">Any new release is first tested and validated by the feature team, then by the entire Office 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="1fe17-115">Nach den internen Tests und Überprüfungen besteht der nächste Schritt in der Bereitstellung eines **Targeted Release** ("Gezielte Freigabe", vormals First Release) für Kunden, die die entsprechende Option aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1fe17-115">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="1fe17-116">Bei jedem Release Ring sammelt Microsoft Feedback und führt durch die Überwachung der wichtigsten Nutzungsmetriken weitere Qualitätsprüfungen durch.</span><span class="sxs-lookup"><span data-stu-id="1fe17-116">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="1fe17-117">Diese Reihe von fortschreitenden Überprüfungen wurde eingeführt, um sicherzustellen, dass das weltweite Release so robust wie möglich ist.</span><span class="sxs-lookup"><span data-stu-id="1fe17-117">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="1fe17-118">Die Releases sind in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1fe17-118">The releases are pictured in the following figure.</span></span> 
  
![Freigeben von Gültigkeits Prüfungs Ringen für Office 365](../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="1fe17-120">Für wichtige Updates werden Office-Kunden zunächst durch die [Microsoft 365-Roadmap](https://products.office.com/business/office-365-roadmap)benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="1fe17-120">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="1fe17-121">Wenn ein Update dem Rollout näher kommt, wird es über das [Office 365 Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="1fe17-121">As an update gets closer to rolling out, it is communicated through your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="1fe17-122">Sie benötigen ein Office 365-oder Azure AD Konto, um über das [Admin Center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)auf Ihr Nachrichtencenter zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1fe17-122">You need an Office 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="1fe17-123">Office 365 Home Plan Benutzer verfügen nicht über ein Admin Center.</span><span class="sxs-lookup"><span data-stu-id="1fe17-123">Office 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="1fe17-124">Standard Release</span><span class="sxs-lookup"><span data-stu-id="1fe17-124">Standard release</span></span>

<span data-ttu-id="1fe17-125">Dies ist die Standardoption, bei der Sie und Ihre Benutzer die neuesten Updates erhalten, wenn Sie allgemein für alle Kunden freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1fe17-125">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="1fe17-126">Eine bewährte Methode besteht darin, die Mehrzahl der Benutzer in der **gezielten** Version von **Standard Version** und IT-Experten und Hauptbenutzern zu belassen, um neue Features auszuwerten und Teams zur Unterstützung von Geschäftsbenutzern und Führungskräften vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="1fe17-126">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1fe17-127">Wenn Sie von "Targeted Release" zurück zu "Standard Release" wechseln, verlieren Ihre Benutzer möglicherweise Zugriff auf die Features, die noch nicht im Standard Release-Programm freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="1fe17-127">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="1fe17-128">Zielrelease</span><span class="sxs-lookup"><span data-stu-id="1fe17-128">Targeted release</span></span>

<span data-ttu-id="1fe17-p106">Mit dieser Option gehören Sie und Ihre Benutzer zu den ersten Personen, die die neuesten Updates erhalten, und können durch Ihr frühes Feedback bei der weiteren Gestaltung des Produkts helfen. Sie können wählen, ob einzelne Personen oder die gesamte Organisation die Aktualisierungen frühzeitig erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="1fe17-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1fe17-p107">Große oder komplexe Updates können länger dauern als andere, sodass keine Benutzer beeinträchtigt werden. Es gibt keine Garantie für den genauen Freigabetermin einer Version.</span><span class="sxs-lookup"><span data-stu-id="1fe17-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="1fe17-133">Targeted Release für die gesamte Organisation</span><span class="sxs-lookup"><span data-stu-id="1fe17-133">Targeted release for entire organization</span></span>

<span data-ttu-id="1fe17-134">Wenn Sie [die Option "Release" im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, erhalten alle Ihre Benutzer die gezielte Veröffentlichungs Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="1fe17-134">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="1fe17-135">Für Organisationen mit mehr als 300 Benutzern empfehlen wir die Verwendung eines Testabonnements für diese Option.</span><span class="sxs-lookup"><span data-stu-id="1fe17-135">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="1fe17-136">Wenden Sie für Informationen zum Testabonnement an Ihren Microsoft-Kontakt.</span><span class="sxs-lookup"><span data-stu-id="1fe17-136">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="1fe17-137">Gezielte Freigabe für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="1fe17-137">Targeted release for selected users</span></span>

<span data-ttu-id="1fe17-138">Wenn Sie [die Option Release im Admin Center](#set-up-the-release-option-in-the-admin-center) für diese Option einrichten, können Sie bestimmte Benutzer (in der Regel Hauptbenutzer) definieren, um frühzeitigen Zugriff auf Features und Funktionen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1fe17-138">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="1fe17-139">Vorteile der gezielten Freigabe</span><span class="sxs-lookup"><span data-stu-id="1fe17-139">Benefits of Targeted release</span></span>

<span data-ttu-id="1fe17-140">In der gezielten Freigabe können Administratoren die Manager bzw. anderen Benutzer ändern, die für Office 365-Updates zur Vorbereitung auf die anstehenden Änderungen verantwortlich sind und folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="1fe17-140">Targeted release allows admins, change managers, or anyone else responsible for Office 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="1fe17-141">Neue Updates testen und überprüfen, bevor diese für alle Benutzer in der Organisation freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1fe17-141">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="1fe17-142">Benutzerbenachrichtigung und -dokumentation vorbereiten, bevor die Updates weltweit veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="1fe17-142">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="1fe17-143">Das interne Helpdesk auf anstehende Änderungen vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="1fe17-143">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="1fe17-144">Compliance- und Sicherheitsüberprüfungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="1fe17-144">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="1fe17-145">Featuresteuerelemente verwenden (sofern zutreffend), um die Veröffentlichung von Updates für Endbenutzer zu steuern.</span><span class="sxs-lookup"><span data-stu-id="1fe17-145">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="1fe17-146">Einrichten der Option "Version" im Admin Center</span><span class="sxs-lookup"><span data-stu-id="1fe17-146">Set up the release option in the admin center</span></span>

<span data-ttu-id="1fe17-p109">Sie können wie folgt ändern, wie Ihre Organisation Office 365-Updates erhält. Sie müssen ein globaler Administrator in Office 365 sein, um sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="1fe17-p109">You can change how your organization receives Office 365 updates by following these steps. You have to be a global admin in Office 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1fe17-p110">Es kann bis zu 24 Stunden dauern, bis die Änderungen in Office 365 wirksam werden. Wenn Sie sich bei "Targeted Release" abmelden, nachdem Sie es zuvor aktiviert hatten, verlieren Ihre Benutzer möglicherweise Zugriff auf Features, deren geplanter Freigabetermin noch nicht erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="1fe17-p110">It can take up to 24 hours for the below changes to take effect in Office 365. If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="1fe17-151">Wechseln Sie im Admin Center zur**Einstellung** **Einstellungen** > , und wählen Sie auf der Registerkarte **Organisationsprofil** die Option **Freigabeeinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="1fe17-151">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="1fe17-152">Um die Zielversion zu deaktivieren, wählen Sie **Standard Version**aus, und wählen Sie dann **Änderungen speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="1fe17-152">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="1fe17-153">Um die gezielte Freigabe für alle Benutzer in Ihrer Organisation zu aktivieren, wählen Sie **Targeted Release for everyone**aus, und wählen Sie dann **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="1fe17-153">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="1fe17-154">Um eine gezielte Freigabe für einige Personen in Ihrer Organisation zu aktivieren, wählen Sie **Targeted Release für ausgewählte Benutzer**aus, und wählen Sie dann **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="1fe17-154">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="1fe17-155">Wählen **Sie Benutzer auswählen** aus, um Benutzer nacheinander hinzuzufügen, oder **Laden Sie Benutzer** zum Massen hinzufügen ein.</span><span class="sxs-lookup"><span data-stu-id="1fe17-155">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="1fe17-156">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="1fe17-156">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="1fe17-157">Abrufen der gezielten Version von Office</span><span class="sxs-lookup"><span data-stu-id="1fe17-157">Get the Targeted release version of Office</span></span>

<span data-ttu-id="1fe17-p111">Zum Installieren einer Targeted Release-Version von Office[ gehen Sie wie hier beschrieben vor ](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). Damit erhalten Sie frühzeitigen Zugriff auf die neuen Features von Office 2016 für Windows-Desktops.</span><span class="sxs-lookup"><span data-stu-id="1fe17-p111">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="1fe17-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1fe17-160">Learn more</span></span>

<span data-ttu-id="1fe17-161">Erfahren Sie, wie Sie [Nachrichten](https://docs.microsoft.com/office365/admin/manage/message-center) in Ihrem [Office 365 Nachrichtencenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) verwalten, um Benachrichtigungen über bevorstehende Office 365 Updates und-Versionen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1fe17-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Office 365 updates and releases.</span></span>
