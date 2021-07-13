---
title: Bereitstellen von Microsoft 365 Lighthouse Basisplänen
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Informationen zum Bereitstellen von Microsoft 365 Lighthouse Basisplänen für verwaltete Dienstanbieter (Managed Service Providers, MSPs), die Microsoft 365 Lighthouse verwenden.
ms.openlocfilehash: f329993443b4bd3003a3e8460d77f9b73ac10fc6
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409104"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a><span data-ttu-id="908e4-103">Bereitstellen von Microsoft 365 Lighthouse Basisplänen</span><span class="sxs-lookup"><span data-stu-id="908e4-103">Deploy Microsoft 365 Lighthouse baselines</span></span> 

> [!NOTE]
> <span data-ttu-id="908e4-104">Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nur für Partner verfügbar, die die [Anforderungen](m365-lighthouse-requirements.md)erfüllen.</span><span class="sxs-lookup"><span data-stu-id="908e4-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="908e4-105">Wenn Ihre Organisation nicht über Microsoft 365 Lighthouse verfügt, lesen Sie ["Registrieren für Microsoft 365 Lighthouse".](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="908e4-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="908e4-106">mit Microsoft 365 Lighthouse Basisplänen können Sie standardmäßige verwaltete Mandantenkonfigurationen bereitstellen, um Mandantenbenutzer, Geräte und Daten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="908e4-106">Microsoft 365 Lighthouse baselines let you deploy standard managed tenant configurations to secure tenant users, devices, and data.</span></span> <span data-ttu-id="908e4-107">Es gibt sechs Standardbasislinienkonfigurationen, die mit Microsoft 365 Lighthouse standardmäßig bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="908e4-107">There are six default baseline configurations that come standard with Microsoft 365 Lighthouse:</span></span>

- <span data-ttu-id="908e4-108">MFA für Administratoren anfordern</span><span class="sxs-lookup"><span data-stu-id="908e4-108">Require MFA for admins</span></span>
- <span data-ttu-id="908e4-109">MFA für Endbenutzer anfordern</span><span class="sxs-lookup"><span data-stu-id="908e4-109">Require MFA for end users</span></span>
- <span data-ttu-id="908e4-110">Blockieren der Legacyauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="908e4-110">Block Legacy Authentication</span></span>
- <span data-ttu-id="908e4-111">Einrichten der Geräteregistrierung in Microsoft Endpoint Manager – Azure AD-Beitritt</span><span class="sxs-lookup"><span data-stu-id="908e4-111">Set up Device Enrollment in Microsoft Endpoint Manager – Azure AD Join</span></span>
- <span data-ttu-id="908e4-112">Konfigurieren der Defender-Antivirenrichtlinie für Windows Geräte</span><span class="sxs-lookup"><span data-stu-id="908e4-112">Configure Defender Anti-virus policy for Windows devices</span></span>
- <span data-ttu-id="908e4-113">Konfigurieren der Compliancerichtlinie für Windows Geräte</span><span class="sxs-lookup"><span data-stu-id="908e4-113">Configure Compliance Policy for Windows devices</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="908e4-114">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="908e4-114">Before you begin</span></span>

<span data-ttu-id="908e4-115">Stellen Sie sicher, dass Sie und Ihre Kundenmandanten die Anforderungen erfüllen, die unter [Anforderungen für Microsoft 365 Lighthouse](m365-lighthouse-requirements.md)aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="908e4-115">Make sure you and your customer tenants meet the requirements listed in [Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).</span></span>

## <a name="learn-more-about-the-default-baseline"></a><span data-ttu-id="908e4-116">Weitere Informationen zur Standardbasislinie</span><span class="sxs-lookup"><span data-stu-id="908e4-116">Learn more about the default baseline</span></span>

<span data-ttu-id="908e4-117">Wählen Sie im linken Navigationsbereich **Baselines** aus, um die Baselines-Seite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="908e4-117">Select **Baselines** from the left navigation pane to open the Baselines page.</span></span> <span data-ttu-id="908e4-118">Sie werden sehen, dass die Standardbasislinie bereits zur Standardmandantengruppe (alle Mandanten) hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="908e4-118">You'll see that the default baseline has already been added to the Default tenant group (all tenants).</span></span> <span data-ttu-id="908e4-119">Wählen Sie zum Anzeigen der Standardbasislinienkonfigurationen die **Baseline anzeigen** aus, um die Standardbasisplanseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="908e4-119">To view the default baseline configurations, select **View baseline** to open the Default baseline page.</span></span> <span data-ttu-id="908e4-120">Die Konfigurationen werden als Bereitstellungsschritte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="908e4-120">The configurations are listed as deployment steps.</span></span> <span data-ttu-id="908e4-121">Wählen Sie einen der Bereitstellungsschritte aus, um Bereitstellungsdetails und Auswirkungen auf die Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="908e4-121">Select any of the deployment steps to view deployment details and user impact.</span></span>

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Screenshot der Standardmäßigen Basisplanseite.>.":::

## <a name="deploy-a-baseline-configuration"></a><span data-ttu-id="908e4-123">Bereitstellen einer Basiskonfiguration</span><span class="sxs-lookup"><span data-stu-id="908e4-123">Deploy a baseline configuration</span></span>  

1. <span data-ttu-id="908e4-124">Wählen Sie auf der linken **Navigationsseite Mandanten** aus, um eine Liste Ihrer integrierten Mandanten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="908e4-124">In the left navigation page, select **Tenants** to view a list of your onboarded tenants.</span></span>

2. <span data-ttu-id="908e4-125">Wählen Sie den Mandanten aus, für den Sie die Basiskonfiguration bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="908e4-125">Select the tenant you want to deploy the baseline configuration to.</span></span>

3. <span data-ttu-id="908e4-126">Wählen Sie die Registerkarte **"Bereitstellungsplan"** aus, um alle Bereitstellungsschritte aus der Basislinie anzuzeigen, die dem Bereitstellungsplan des Mandanten hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="908e4-126">Select the **Deployment plan** tab to see all the deployment steps from the baseline that have been added to the tenant's deployment plan.</span></span>

4. <span data-ttu-id="908e4-127">Wählen Sie einen Bereitstellungsschritt aus, um die Seite "Bereitstellungsschritt" zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="908e4-127">Select a deployment step to open the deployment step page.</span></span>

5. <span data-ttu-id="908e4-128">Wählen Sie **"Übernehmen"** aus, um den ausgewählten Bereitstellungsschritt auf den Mandanten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="908e4-128">Select **Apply** to apply the selected deployment step to the tenant.</span></span> <span data-ttu-id="908e4-129">Wenn der Bereitstellungsschritt "Diese Aktion erfordert einen manuellen Schritt" angibt, müssen Sie den manuellen Schritt abschließen, damit der Bereitstellungsschritt ordnungsgemäß angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="908e4-129">If the deployment step indicates "This action requires a manual step", make sure to complete the manual step so the deployment step is applied correctly.</span></span>

## <a name="related-content"></a><span data-ttu-id="908e4-130">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="908e4-130">Related content</span></span>

<span data-ttu-id="908e4-131">[Übersicht über die Verwendung von Basisplänen zur Bereitstellung standardmäßiger Mandantenkonfigurationen](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="908e4-131">[Overview of using baselines to deploy standard tenant configurations](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (article)</span></span>\
<span data-ttu-id="908e4-132">[faq zu Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="908e4-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>