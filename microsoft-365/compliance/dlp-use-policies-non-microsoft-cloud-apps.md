---
title: Verwenden von Richtlinien zur Verhinderung von Datenverlust für Nicht-Microsoft-Cloud-Apps
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps verwenden.
ms.openlocfilehash: 4bda45a6da6b9626391da37eb9a806b3308c5e7f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322317"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps"></a><span data-ttu-id="99530-103">Verwenden von Richtlinien zur Verhinderung von Datenverlust für Nicht-Microsoft-Cloud-Apps</span><span class="sxs-lookup"><span data-stu-id="99530-103">Use data loss prevention policies for non-Microsoft cloud apps</span></span>

<span data-ttu-id="99530-104">Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) für Nicht-Microsoft-Cloud-Apps sind Teil der Microsoft 365 DLP-Suite von Features. Mithilfe dieser Features können Sie vertrauliche Elemente in Microsoft 365 Diensten ermitteln und schützen.</span><span class="sxs-lookup"><span data-stu-id="99530-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="99530-105">Weitere Informationen zu allen Microsoft DLP-Angeboten finden Sie unter ["Verhinderung von Datenverlust".](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="99530-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="99530-106">Sie können DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps verwenden, um zu überwachen und zu erkennen, wann vertrauliche Elemente über Nicht-Microsoft-Cloud-Apps verwendet und freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="99530-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="99530-107">Die Verwendung dieser Richtlinien bietet Ihnen die Sichtbarkeit und Kontrolle, die Sie benötigen, um sicherzustellen, dass sie ordnungsgemäß verwendet und geschützt werden, und es hilft, riskantes Verhalten zu verhindern, das sie beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="99530-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="99530-108">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="99530-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="99530-109">SKU/Abonnement-Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="99530-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="99530-110">Bevor Sie mit der Verwendung von DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps beginnen, bestätigen Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und alle Add-Ons.</span><span class="sxs-lookup"><span data-stu-id="99530-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="99530-111">Um auf diese Funktionalität zugreifen und diese verwenden zu können, benötigen Sie eines der folgenden Abonnements oder Add-Ons:</span><span class="sxs-lookup"><span data-stu-id="99530-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="99530-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="99530-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="99530-113">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="99530-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="99530-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="99530-114">Microsoft 365 E5 Security</span></span>

### <a name="permissions"></a><span data-ttu-id="99530-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="99530-115">Permissions</span></span>
<span data-ttu-id="99530-116">Der Benutzer, der die DLP-Richtlinie erstellt, sollte Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="99530-116">The user who creates the DLP policy should be a:</span></span>
- <span data-ttu-id="99530-117">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="99530-117">Global administrator</span></span>
- <span data-ttu-id="99530-118">Complianceadministrator</span><span class="sxs-lookup"><span data-stu-id="99530-118">Compliance administrator</span></span>
- <span data-ttu-id="99530-119">Compliancedatenadministrator</span><span class="sxs-lookup"><span data-stu-id="99530-119">Compliance data administrator</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="99530-120">Vorbereiten der Cloud App Security Umgebung</span><span class="sxs-lookup"><span data-stu-id="99530-120">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="99530-121">DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps verwenden Cloud App Security DLP-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="99530-121">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="99530-122">Um sie zu verwenden, sollten Sie Ihre Cloud App Security Umgebung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="99530-122">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="99530-123">Anweisungen finden Sie unter [Festlegen der sofortigen Sichtbarkeit, des Schutzes und der Governanceaktionen für Ihre Apps.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)</span><span class="sxs-lookup"><span data-stu-id="99530-123">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="99530-124">Verbinden einer Nicht-Microsoft-Cloud-App</span><span class="sxs-lookup"><span data-stu-id="99530-124">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="99530-125">Damit die DLP-Richtlinie für eine bestimmte Nicht-Microsoft-Cloud-App verwendet werden kann, muss die App mit Cloud App Security verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="99530-125">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="99530-126">Diesbezügliche Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="99530-126">For information, see:</span></span>

- [<span data-ttu-id="99530-127">Verbinden Box</span><span class="sxs-lookup"><span data-stu-id="99530-127">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="99530-128">Verbinden Dropbox</span><span class="sxs-lookup"><span data-stu-id="99530-128">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="99530-129">Verbinden G-Suite</span><span class="sxs-lookup"><span data-stu-id="99530-129">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="99530-130">Verbinden Salesforce</span><span class="sxs-lookup"><span data-stu-id="99530-130">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="99530-131">Verbinden Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="99530-131">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="99530-132">Nachdem Sie Ihre Cloud-Apps mit Cloud App Security verbunden haben, können Sie Microsoft 365 DLP-Richtlinien für sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="99530-132">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

> [!NOTE]
> <span data-ttu-id="99530-133">Es ist auch möglich, Microsoft Cloud App Security zum Erstellen von DLP-Richtlinien für Microsoft-Cloud-Apps zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="99530-133">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="99530-134">Es wird jedoch empfohlen, Microsoft 365 zum Erstellen und Verwalten von DLP-Richtlinien für Microsoft-Cloud-Apps zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="99530-134">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="99530-135">Erstellen einer DLP-Richtlinie für eine Nicht-Microsoft-Cloud-App</span><span class="sxs-lookup"><span data-stu-id="99530-135">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="99530-136">Wenn Sie einen Speicherort für die DLP-Richtlinie auswählen, aktivieren Sie den **Microsoft Cloud App Security** Speicherort.</span><span class="sxs-lookup"><span data-stu-id="99530-136">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="99530-137">Um eine bestimmte App oder Instanz auszuwählen, wählen Sie **"Instanz auswählen"** aus.</span><span class="sxs-lookup"><span data-stu-id="99530-137">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="99530-138">Wenn Sie keine Instanz auswählen, verwendet die Richtlinie alle verbundenen Apps in Ihrem Microsoft Cloud App Security Mandanten.</span><span class="sxs-lookup"><span data-stu-id="99530-138">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Speicherorte, an denen die Richtlinie angewendet werden soll](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US und Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="99530-141">Sie können für jede unterstützte Nicht-Microsoft-Cloud-App verschiedene Aktionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="99530-141">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="99530-142">Für jede App gibt es verschiedene mögliche Aktionen (abhängig von der Cloud-App-API).</span><span class="sxs-lookup"><span data-stu-id="99530-142">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Regel erstellen](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="99530-144">Wenn Sie eine Regel in der DLP-Richtlinie erstellen, können Sie eine Aktion für Nicht-Microsoft-Cloud-Apps auswählen.</span><span class="sxs-lookup"><span data-stu-id="99530-144">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="99530-145">Um Drittanbieter-Apps einzuschränken, wählen Sie **"Drittanbieter-Apps einschränken" aus.**</span><span class="sxs-lookup"><span data-stu-id="99530-145">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Einschränken von Drittanbieter-Apps](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> <span data-ttu-id="99530-147">DLP-Richtlinien, die auf Nicht-Microsoft-Apps angewendet werden, verwenden Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="99530-147">DLP policies applied to non-Microsoft apps use Microsoft Cloud App Security.</span></span> <span data-ttu-id="99530-148">Wenn die DLP-Richtlinie für eine Nicht-Microsoft-App erstellt wird, wird dieselbe Richtlinie automatisch in Microsoft Cloud App Security erstellt.</span><span class="sxs-lookup"><span data-stu-id="99530-148">When the DLP policy for a non-Microsoft app is created, the same policy will be automatically created in Microsoft Cloud App Security.</span></span>

<span data-ttu-id="99530-149">Informationen zum Erstellen und Konfigurieren von DLP-Richtlinien finden Sie unter ["Erstellen von Tests und Optimieren einer DLP-Richtlinie".](./create-test-tune-dlp-policy.md)</span><span class="sxs-lookup"><span data-stu-id="99530-149">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="99530-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99530-150">See Also</span></span>

- [<span data-ttu-id="99530-151">Erstellen von Tests und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="99530-151">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md)
- [<span data-ttu-id="99530-152">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="99530-152">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="99530-153">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="99530-153">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md)
