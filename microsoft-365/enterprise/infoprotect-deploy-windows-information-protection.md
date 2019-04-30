---
title: 'Schritt 4: Konfigurieren von Windows Information Protection'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Bereitstellen von Windows Information Protection in Microsoft 365.
ms.openlocfilehash: ca706d49053bbc100a633afb74c7c978de2e4c5c
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353101"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="424b7-103">Schritt 4: Konfigurieren von Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="424b7-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="424b7-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="424b7-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="424b7-105">Da immer mehr persönliche Geräte für Arbeitszwecke verwendet werden, steigt das Risiko, dass Apps und Geräte private Unternehmensdaten preisgeben.</span><span class="sxs-lookup"><span data-stu-id="424b7-105">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="424b7-106">Ein Mitarbeiter sendet beispielsweise versehentlich ein Bild eines Marketingplans für ein künftiges Produkt an eine Website für soziale Medien oder speichert eine Datei mit vertraulichen Informationen in seinem öffentlichen Cloudspeicher.</span><span class="sxs-lookup"><span data-stu-id="424b7-106">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="424b7-107">Windows Information Protection (WIP) bietet Schutz vor dieser Art von Datenlecks auf Windows 10-Geräten.</span><span class="sxs-lookup"><span data-stu-id="424b7-107">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="424b7-108">Weitere Informationen finden Sie unter [Schutz Ihrer Unternehmensdaten mit WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="424b7-108">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="424b7-109">In Microsoft 365 Enterprise ist WIP eine Kombination von Windows 10 Enterprise und Microsoft Intune, das in Enterprise Mobility + Security (EMS) in Ihrem Abonnement enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="424b7-109">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with Enterprise Mobility + Security (EMS) in your subscription.</span></span> 

<span data-ttu-id="424b7-110">Gehen Sie folgendermaßen vor, um WIP in Ihrer Organisation mit Microsoft 365 Enterprise bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="424b7-110">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="424b7-111">Registrieren Sie Ihre Windows-Geräte in Intune.</span><span class="sxs-lookup"><span data-stu-id="424b7-111">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="424b7-112">Sie hätten dies in [Phase 5: Verwaltung mobiler Geräte](mobility-infrastructure.md) tun sollen.</span><span class="sxs-lookup"><span data-stu-id="424b7-112">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="424b7-113">Erstellen Sie eine [Intune-Richtlinie für WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="424b7-113">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="424b7-114">Stellen Sie sicher, dass Sie Liste mit geschützten Apps ausgefüllt haben.</span><span class="sxs-lookup"><span data-stu-id="424b7-114">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="424b7-115">Wählen Sie Ihre WIP-Schutzebene aus.</span><span class="sxs-lookup"><span data-stu-id="424b7-115">Choose your WIP protection level.</span></span>

<span data-ttu-id="424b7-116">Sie können WIP auch mit [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm) verwenden.</span><span class="sxs-lookup"><span data-stu-id="424b7-116">You can also use WIP with [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="424b7-117">Weitere Informationen finden Sie unter [Bewährte Methoden für WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).</span><span class="sxs-lookup"><span data-stu-id="424b7-117">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="424b7-118">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step4) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="424b7-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="424b7-119">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="424b7-119">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="424b7-120">Konfigurieren der Verhinderung von Datenverlust in Office 365</span><span class="sxs-lookup"><span data-stu-id="424b7-120">Office 365 Data Loss Prevention (DLP)</span></span>](infoprotect-data-loss-prevention.md)|


