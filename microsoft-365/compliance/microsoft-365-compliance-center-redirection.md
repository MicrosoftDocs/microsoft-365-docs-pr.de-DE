---
title: Umleiten von Benutzern aus dem Office 365 Security and Compliance Center zum Microsoft 365 Compliance Center
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Erfahren Sie mehr über das automatische Umleiten Office 365 Security and Compliance Center-Benutzer an die Microsoft 365 Compliance Center.
ms.collection: M365-security-compliance
ms.openlocfilehash: 62fc302f9f065ac7bb0475a6e72dc240a56a1fe1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339406"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="f24b0-103">Umleiten von Benutzern aus dem Office 365 Security and Compliance Center zum Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f24b0-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="f24b0-104">In diesem Artikel wird erläutert, wie die automatische Umleitung für Benutzer funktioniert, die vom Office 365 Security and Compliance Center (protection.office.com) zum Microsoft 365 Compliance Center (compliance.microsoft.com) auf Compliancelösungen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f24b0-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="f24b0-105">Das erwartet Sie</span><span class="sxs-lookup"><span data-stu-id="f24b0-105">What to expect</span></span>

<span data-ttu-id="f24b0-106">Die automatische Umleitung ist standardmäßig für alle Benutzer aktiviert, die auf die folgenden Compliance-bezogenen Lösungen in Office 365 Security and Compliance (protection.office.com) zugreifen:</span><span class="sxs-lookup"><span data-stu-id="f24b0-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="f24b0-107">Verhinderung von Datenverlust (DLP)</span><span class="sxs-lookup"><span data-stu-id="f24b0-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="f24b0-108">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="f24b0-108">Classification</span></span>
- <span data-ttu-id="f24b0-109">Informationsgovernance</span><span class="sxs-lookup"><span data-stu-id="f24b0-109">Information governance</span></span>
- <span data-ttu-id="f24b0-110">Datensatzverwaltung</span><span class="sxs-lookup"><span data-stu-id="f24b0-110">Records management</span></span>
- <span data-ttu-id="f24b0-111">Kommunikationscompliance (früher "Aufsicht")</span><span class="sxs-lookup"><span data-stu-id="f24b0-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="f24b0-112">Benutzer werden automatisch an die gleichen Compliancelösungen im Microsoft 365 Compliance Center (compliance.microsoft.com) weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="f24b0-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="f24b0-113">Bei anderen Compliancelösungen im Office 365 Security and Compliance Center verwalten Benutzer diese Lösungen weiterhin im Microsoft 365 Compliance Center oder im Office 365 Security and Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="f24b0-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="f24b0-114">Die automatische Umleitung für diese Compliancelösungen wird in Kürze verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="f24b0-114">The automatic redirection for these compliance solutions will be available soon.</span></span>

<span data-ttu-id="f24b0-115">Dieses Feature und die zugehörigen Steuerelemente ermöglichen nicht die automatische Umleitung von Sicherheitsfeatures für Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="f24b0-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f24b0-116">Informationen zum Aktivieren der Umleitung für Sicherheitsfeatures finden Sie unter ["Umleiten von Konten von Microsoft Defender für Office 365 zum Microsoft 365 Security Center".](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)</span><span class="sxs-lookup"><span data-stu-id="f24b0-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="f24b0-117">Kann ich zum früheren Portal zurückkehren?</span><span class="sxs-lookup"><span data-stu-id="f24b0-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="f24b0-118">Wenn etwas nicht für Sie funktioniert oder wenn Sie etwas nicht über das Microsoft 365 Compliance Center-Portal abschließen können, können Sie die automatische Umleitung für alle Benutzer vorübergehend deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f24b0-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f24b0-119">Die Microsoft 365 Compliance Center ist das Ersatzverwaltungsportal für Compliance-Lösungen, die derzeit im Office 365 Security and Compliance Center verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f24b0-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="f24b0-120">Alle Microsoft 365 Compliancelösungen werden ausschließlich im Microsoft 365 Compliance Center verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f24b0-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f24b0-121">Das Deaktivieren der Umleitung zum Microsoft 365 Compliance Center sollte eine kurzfristige Lösung sein.</span><span class="sxs-lookup"><span data-stu-id="f24b0-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.</span></span>

<span data-ttu-id="f24b0-122">Führen Sie die folgenden Schritte aus, um zum Office 365 Security and Compliance Center (protection.microsoft.com) für alle Benutzer zurückzukehren:</span><span class="sxs-lookup"><span data-stu-id="f24b0-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="f24b0-123">Melden Sie sich beim [Microsoft 365 Compliance Center](https://compliance.microsoft.com) als globaler Administrator oder mit einem beliebigen Konto mit Complianceadministratorberechtigungen in Azure Active Directory an.</span><span class="sxs-lookup"><span data-stu-id="f24b0-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="f24b0-124">Navigieren Sie zu **Einstellungen**  >  **Compliance Center-Umleitung.**</span><span class="sxs-lookup"><span data-stu-id="f24b0-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="f24b0-125">Schalten Sie die Einstellung für die automatische Umleitung auf **"Aus" um.**</span><span class="sxs-lookup"><span data-stu-id="f24b0-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="f24b0-126">Wählen Sie **"Deaktivieren" und** "Feedback teilen" aus, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="f24b0-126">Select **Turn off** and share feedback when prompted.</span></span>

<span data-ttu-id="f24b0-127">Nach der Deaktivierung werden die Benutzer nicht mehr an compliance.microsoft.com weitergeleitet und zum Office 365 Security and Compliance Center (protection.microsoft.com) weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="f24b0-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="f24b0-128">Diese Einstellung kann von globalen oder Compliance-Administratoren jederzeit erneut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f24b0-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="f24b0-129">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="f24b0-129">Related information</span></span>

- [<span data-ttu-id="f24b0-130">Übersicht über Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f24b0-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)
