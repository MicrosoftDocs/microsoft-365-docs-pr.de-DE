---
title: 'Schritt 4: Konfigurieren von Windows Information Protection'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Bereitstellen von Windows Information Protection in Microsoft 365.
ms.openlocfilehash: c7b76ef28d41810d6e9e45e98adb7a94cf8ae2f4
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005722"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="fd824-103">Schritt 4: Konfigurieren von Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="fd824-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="fd824-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fd824-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Phase 6: Schutz von Daten](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="fd824-106">Da immer mehr persönliche Geräte für Arbeitszwecke verwendet werden, steigt das Risiko, dass Apps und Geräte private Unternehmensdaten preisgeben.</span><span class="sxs-lookup"><span data-stu-id="fd824-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="fd824-107">Ein Mitarbeiter sendet beispielsweise versehentlich ein Bild eines Marketingplans für ein künftiges Produkt an eine Website für soziale Medien oder speichert eine Datei mit vertraulichen Informationen in seinem öffentlichen Cloudspeicher.</span><span class="sxs-lookup"><span data-stu-id="fd824-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="fd824-108">Windows Information Protection (WIP) bietet Schutz vor dieser Art von Datenlecks auf Windows 10-Geräten.</span><span class="sxs-lookup"><span data-stu-id="fd824-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="fd824-109">Weitere Informationen finden Sie unter [Schutz Ihrer Unternehmensdaten mit WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="fd824-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="fd824-110">In Microsoft 365 Enterprise ist WIP eine Kombination von Windows 10 Enterprise und Microsoft Intune, das in Ihrem Abonnement enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="fd824-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="fd824-111">Gehen Sie folgendermaßen vor, um WIP in Ihrer Organisation mit Microsoft 365 Enterprise bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="fd824-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="fd824-112">Registrieren Sie Ihre Windows-Geräte in Intune.</span><span class="sxs-lookup"><span data-stu-id="fd824-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="fd824-113">Sie hätten dies in [Phase 5: Verwaltung mobiler Geräte](mobility-infrastructure.md) tun sollen.</span><span class="sxs-lookup"><span data-stu-id="fd824-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>

2. <span data-ttu-id="fd824-114">Erstellen Sie eine [Intune-Richtlinie für WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="fd824-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>

   -    <span data-ttu-id="fd824-115">Stellen Sie sicher, dass Sie Liste mit geschützten Apps ausgefüllt haben.</span><span class="sxs-lookup"><span data-stu-id="fd824-115">Ensure that you have filled out your Protected apps list.</span></span>
  
   - <span data-ttu-id="fd824-116">Wählen Sie Ihre WIP-Schutzebene aus.</span><span class="sxs-lookup"><span data-stu-id="fd824-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="fd824-117">Sie können WIP auch mit dem [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr) verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd824-117">You can also use WIP with [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr).</span></span> 

<span data-ttu-id="fd824-118">Weitere Informationen finden Sie unter [Bewährte Methoden für WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).</span><span class="sxs-lookup"><span data-stu-id="fd824-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="fd824-119">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step4) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="fd824-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="fd824-120">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="fd824-120">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="fd824-122">Konfigurieren der Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="fd824-122">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


