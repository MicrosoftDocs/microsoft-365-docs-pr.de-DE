---
title: Verwenden von Richtlinien zur Verhinderung von Datenverlust für nicht-Microsoft-Cloud-Apps (Vorschau)
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
description: Hier erfahren Sie, wie Sie DLP-Richtlinien für nicht-Microsoft-Cloud-Apps verwenden.
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649656"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="1b55d-103">Verwenden von Richtlinien zur Verhinderung von Datenverlust für nicht-Microsoft-Cloud-Apps (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1b55d-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="1b55d-104">DLP-Richtlinien (Data Loss Prevention) für nicht-Microsoft-Cloud-apps sind Teil der Microsoft 365 DLP-Suite mit Features; Mithilfe dieser Funktionen können Sie vertrauliche Elemente in Microsoft 365-Diensten ermitteln und schützen.</span><span class="sxs-lookup"><span data-stu-id="1b55d-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="1b55d-105">Weitere Informationen zu allen Microsoft DLP-Angeboten finden Sie unter [Übersicht über Verhinderung von Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="1b55d-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="1b55d-106">Sie können DLP-Richtlinien für nicht-Microsoft-Cloud-Apps verwenden, um zu überwachen und zu erkennen, wann vertrauliche Elemente verwendet und über nicht-Microsoft-Cloud-apps freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1b55d-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="1b55d-107">Durch die Verwendung dieser Richtlinien erhalten Sie die Sichtbarkeit und Kontrolle, die Sie benötigen, um sicherzustellen, dass Sie ordnungsgemäß verwendet und geschützt werden, und Sie können riskantes Verhalten verhindern, das Sie gefährden kann.</span><span class="sxs-lookup"><span data-stu-id="1b55d-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1b55d-108">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="1b55d-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="1b55d-109">SKU/Abonnement-Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="1b55d-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="1b55d-110">Bevor Sie mit der Verwendung von DLP-Richtlinien für nicht-Microsoft-Cloud-apps beginnen, müssen Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und alle Add-ons bestätigen.</span><span class="sxs-lookup"><span data-stu-id="1b55d-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="1b55d-111">Für den Zugriff auf und die Verwendung dieser Funktion benötigen Sie eines der folgenden Abonnements oder Add-ons:</span><span class="sxs-lookup"><span data-stu-id="1b55d-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="1b55d-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1b55d-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="1b55d-113">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="1b55d-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="1b55d-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="1b55d-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="1b55d-115">Vorbereiten der Cloud-App-Sicherheitsumgebung</span><span class="sxs-lookup"><span data-stu-id="1b55d-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="1b55d-116">DLP-Richtlinien für nicht-Microsoft-Cloud-Apps verwenden Cloud App Security DLP-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="1b55d-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="1b55d-117">Um Sie zu verwenden, sollten Sie Ihre Cloud-App-Sicherheitsumgebung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="1b55d-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="1b55d-118">Anweisungen finden Sie unter [Festlegen von sofort Sichtbarkeits-, Schutz-und Steuerungsaktionen für Ihre apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span><span class="sxs-lookup"><span data-stu-id="1b55d-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="1b55d-119">Verbinden einer nicht-Microsoft-Cloud-App</span><span class="sxs-lookup"><span data-stu-id="1b55d-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="1b55d-120">Damit die DLP-Richtlinie für eine bestimmte nicht-Microsoft-Cloud-App verwendet werden kann, muss die APP mit der Cloud-App-Sicherheit verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="1b55d-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="1b55d-121">Diesbezügliche Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="1b55d-121">For information, see:</span></span>

- [<span data-ttu-id="1b55d-122">Feld "verbinden"</span><span class="sxs-lookup"><span data-stu-id="1b55d-122">Connect Box</span></span>](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1b55d-123">Dropbox verbinden</span><span class="sxs-lookup"><span data-stu-id="1b55d-123">Connect Dropbox</span></span>](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1b55d-124">Connect G-Suite</span><span class="sxs-lookup"><span data-stu-id="1b55d-124">Connect G-Suite</span></span>](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1b55d-125">Verbinden von Salesforce</span><span class="sxs-lookup"><span data-stu-id="1b55d-125">Connect Salesforce</span></span>](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1b55d-126">Verbinden von Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="1b55d-126">Connect Cisco Webex</span></span>](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="1b55d-127">Nachdem Sie Ihre Cloud-apps mit der Cloud-App-Sicherheit verbunden haben, können Sie Microsoft 365 DLP-Richtlinien für diese erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b55d-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="1b55d-128">Es ist auch möglich, mithilfe von Microsoft Cloud App Security DLP-Richtlinien für Microsoft Cloud-apps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b55d-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="1b55d-129">Es wird jedoch empfohlen, Microsoft 365 zum Erstellen und Verwalten von DLP-Richtlinien in Microsoft Cloud-apps zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b55d-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="1b55d-130">Erstellen einer DLP-Richtlinie für eine nicht von Microsoft erstellte Cloud-App</span><span class="sxs-lookup"><span data-stu-id="1b55d-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="1b55d-131">Wenn Sie einen Speicherort für die DLP-Richtlinie auswählen, aktivieren Sie den **Microsoft Cloud-App-Sicherheits** Speicherort.</span><span class="sxs-lookup"><span data-stu-id="1b55d-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="1b55d-132">Zum Auswählen einer bestimmten app oder Instanz wählen Sie **Instanz auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="1b55d-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="1b55d-133">Wenn Sie keine Instanz auswählen, verwendet die Richtlinie alle verbundenen apps in Ihrem Microsoft Cloud-App-Sicherheits Mandanten.</span><span class="sxs-lookup"><span data-stu-id="1b55d-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Standorte zum Anwenden der Richtlinie](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US und Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="1b55d-136">Sie können verschiedene Aktionen für jede unterstützte nicht-Microsoft-Cloud-App auswählen.</span><span class="sxs-lookup"><span data-stu-id="1b55d-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="1b55d-137">Für jede APP gibt es verschiedene mögliche Aktionen (abhängig von der Cloud-App-API).</span><span class="sxs-lookup"><span data-stu-id="1b55d-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Regel erstellen](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="1b55d-139">Wenn Sie eine Regel in der DLP-Richtlinie erstellen, können Sie eine Aktion für nicht-Microsoft-Cloud-apps auswählen.</span><span class="sxs-lookup"><span data-stu-id="1b55d-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="1b55d-140">Um Drittanbieter-apps einzuschränken, wählen Sie **Apps für Drittanbieter einschränken**aus.</span><span class="sxs-lookup"><span data-stu-id="1b55d-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Einschränken von Drittanbieter-apps](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="1b55d-142">Informationen zum Erstellen und Konfigurieren von DLP-Richtlinien finden Sie unter [Create Test and Tune a DLP Policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="1b55d-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b55d-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b55d-143">See Also</span></span>

- [<span data-ttu-id="1b55d-144">Erstellen von Tests und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="1b55d-144">Create test and tune a DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="1b55d-145">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="1b55d-145">Get started with the default DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="1b55d-146">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="1b55d-146">Create a DLP policy from a template</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
