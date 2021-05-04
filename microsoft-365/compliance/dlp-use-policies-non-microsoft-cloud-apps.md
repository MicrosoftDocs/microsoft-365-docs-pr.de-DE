---
title: Verwenden von Richtlinien zur Verhinderung von Datenverlust für Nicht-Microsoft-Cloud-Apps (Vorschau)
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
description: Erfahren Sie, wie Sie dlp-Richtlinien für Nicht-Microsoft-Cloud-Apps verwenden.
ms.openlocfilehash: d4c5170cab01b1ca22701b13c7afbf4f2e0ba7da
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114133"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="be180-103">Verwenden von Richtlinien zur Verhinderung von Datenverlust für Nicht-Microsoft-Cloud-Apps (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="be180-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="be180-104">#A0 (Data Loss Prevention, Verhinderung von Datenverlust) für Nicht-Microsoft-Cloud-Apps sind Teil der Microsoft 365#A1 von Features. Mithilfe dieser Features können Sie vertrauliche Elemente in verschiedenen Diensten Microsoft 365 schützen.</span><span class="sxs-lookup"><span data-stu-id="be180-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="be180-105">Weitere Informationen zu allen Microsoft DLP-Angeboten finden Sie [unter Learn about Data Loss Prevention](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="be180-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="be180-106">Sie können DLP-Richtlinien verwenden, um Nicht-Microsoft-Cloud-Apps zu überwachen und zu erkennen, wenn vertrauliche Elemente über Nicht-Microsoft-Cloud-Apps verwendet und freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be180-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="be180-107">Die Verwendung dieser Richtlinien bietet Ihnen die Sichtbarkeit und Kontrolle, die Sie sicherstellen müssen, dass sie ordnungsgemäß verwendet und geschützt sind, und verhindert riskantes Verhalten, das sie gefährden könnte.</span><span class="sxs-lookup"><span data-stu-id="be180-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="be180-108">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="be180-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="be180-109">SKU/Abonnement-Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="be180-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="be180-110">Bevor Sie mit der Verwendung von DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps beginnen, bestätigen Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und alle Add-Ons.</span><span class="sxs-lookup"><span data-stu-id="be180-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="be180-111">Um auf diese Funktionalität zu zugreifen und diese zu verwenden, benötigen Sie eines der folgenden Abonnements oder Add-Ons:</span><span class="sxs-lookup"><span data-stu-id="be180-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="be180-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="be180-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="be180-113">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="be180-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="be180-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="be180-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="be180-115">Vorbereiten der Cloud App Security Umgebung</span><span class="sxs-lookup"><span data-stu-id="be180-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="be180-116">DLP-Richtlinien für Nicht-Microsoft-Cloud-Apps verwenden Cloud App Security DLP-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="be180-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="be180-117">Um es zu verwenden, sollten Sie Ihre Umgebung Cloud App Security vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="be180-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="be180-118">Anweisungen finden Sie unter [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span><span class="sxs-lookup"><span data-stu-id="be180-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="be180-119">Verbinden einer Nicht-Microsoft-Cloud-App</span><span class="sxs-lookup"><span data-stu-id="be180-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="be180-120">Um eine DLP-Richtlinie mit einer bestimmten Cloud-App zu verwenden, die keine Microsoft-App ist, muss die App mit einer Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="be180-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="be180-121">Diesbezügliche Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="be180-121">For information, see:</span></span>

- [<span data-ttu-id="be180-122">Verbinden Box</span><span class="sxs-lookup"><span data-stu-id="be180-122">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="be180-123">Verbinden Dropbox</span><span class="sxs-lookup"><span data-stu-id="be180-123">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="be180-124">Verbinden G-Suite</span><span class="sxs-lookup"><span data-stu-id="be180-124">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="be180-125">Verbinden Salesforce</span><span class="sxs-lookup"><span data-stu-id="be180-125">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="be180-126">Verbinden Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="be180-126">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="be180-127">Nachdem Sie Ihre Cloud-Apps mit Cloud App Security verbinden, können Sie Microsoft 365 DLP-Richtlinien für sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="be180-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="be180-128">Es ist auch möglich, mithilfe von Microsoft Cloud App Security DLP-Richtlinien für Microsoft-Cloud-Apps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="be180-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="be180-129">Es wird jedoch empfohlen, die Microsoft 365 zum Erstellen und Verwalten von DLP-Richtlinien für Microsoft-Cloud-Apps zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="be180-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="be180-130">Erstellen einer DLP-Richtlinie für eine Nicht-Microsoft-Cloud-App</span><span class="sxs-lookup"><span data-stu-id="be180-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="be180-131">Wenn Sie einen Speicherort für die DLP-Richtlinie auswählen, aktivieren Sie **den Microsoft Cloud App Security** Speicherort.</span><span class="sxs-lookup"><span data-stu-id="be180-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="be180-132">Wählen Sie Instanz auswählen aus, um eine bestimmte App oder Instanz **auszuwählen.**</span><span class="sxs-lookup"><span data-stu-id="be180-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="be180-133">Wenn Sie keine Instanz auswählen, verwendet die Richtlinie alle verbundenen Apps in Ihrem Microsoft Cloud App Security Mandanten.</span><span class="sxs-lookup"><span data-stu-id="be180-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Speicherorte, an die die Richtlinie angewendet werden soll](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US und Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="be180-136">Sie können verschiedene Aktionen für jede unterstützte Nicht-Microsoft-Cloud-App auswählen.</span><span class="sxs-lookup"><span data-stu-id="be180-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="be180-137">Für jede App gibt es verschiedene mögliche Aktionen (abhängig von der Cloud-App-API).</span><span class="sxs-lookup"><span data-stu-id="be180-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Regel erstellen](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="be180-139">Wenn Sie eine Regel in der DLP-Richtlinie erstellen, können Sie eine Aktion für Nicht-Microsoft-Cloud-Apps auswählen.</span><span class="sxs-lookup"><span data-stu-id="be180-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="be180-140">Um Apps von Drittanbietern einzuschränken, wählen Sie Apps von **Drittanbietern einschränken aus.**</span><span class="sxs-lookup"><span data-stu-id="be180-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Einschränken von Drittanbieter-Apps](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="be180-142">Informationen zum Erstellen und Konfigurieren von DLP-Richtlinien finden Sie unter [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="be180-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="be180-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be180-143">See Also</span></span>

- [<span data-ttu-id="be180-144">Erstellen von Tests und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="be180-144">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="be180-145">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="be180-145">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="be180-146">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="be180-146">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)