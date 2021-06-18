---
title: Erstellen von Benachrichtigungen für genaue Datenübereinstimmungsaktivitäten
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie Benachrichtigungen für genaue Datenübereinstimmungsaktivitäten erstellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15aa8f2bda76d56d3e35af8e884193193bb78d40
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007561"
---
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="65a18-103">Erstellen von Benachrichtigungen für genaue Datenübereinstimmungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="65a18-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="65a18-104">Wenn Sie [benutzerdefinierte vertrauliche Informationstypen mit exakter Datenübereinstimmung (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) erstellen, werden im [Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) eine Reihe von Aktivitäten erstellt.</span><span class="sxs-lookup"><span data-stu-id="65a18-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="65a18-105">Mit dem PowerShell-Cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) können Sie Benachrichtigungen erstellen, die Sie über folgende Aktivitäten informieren:</span><span class="sxs-lookup"><span data-stu-id="65a18-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="65a18-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="65a18-106">CreateSchema</span></span>
- <span data-ttu-id="65a18-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="65a18-107">EditSchema</span></span>
- <span data-ttu-id="65a18-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="65a18-108">RemoveSchema</span></span>
- <span data-ttu-id="65a18-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="65a18-109">UploadDataFailed</span></span>
- <span data-ttu-id="65a18-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="65a18-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="65a18-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="65a18-111">Pre-requisites</span></span>

<span data-ttu-id="65a18-112">Das von Ihnen verwendete Konto muss eines der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="65a18-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="65a18-113">ein globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="65a18-113">a global admin</span></span>
- <span data-ttu-id="65a18-114">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="65a18-114">compliance administrator</span></span>
- <span data-ttu-id="65a18-115">Exchange Online-Administrator</span><span class="sxs-lookup"><span data-stu-id="65a18-115">Exchange Online administrator</span></span>

<span data-ttu-id="65a18-116">Weitere Informationen über DLP-Berechtigungen finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="65a18-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="65a18-117">Die EDM-basierte Klassifizierung ist in diesen Abonnements enthalten.</span><span class="sxs-lookup"><span data-stu-id="65a18-117">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="65a18-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="65a18-118">Office 365 E5</span></span>
- <span data-ttu-id="65a18-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="65a18-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="65a18-120">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="65a18-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="65a18-121">Microsoft E5/ A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="65a18-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="65a18-122">Weitere Informationen zur DLP-Lizenzierung finden Sie in den [Microsoft 365-Lizenzierungsrichtlinien für Security & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span><span class="sxs-lookup"><span data-stu-id="65a18-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="65a18-123">Konfigurieren von Benachrichtigungen für EDM-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="65a18-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="65a18-124">Stellen Sie eine Verbindung mit der [Security & Compliance Center PowerShell her](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="65a18-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="65a18-125">Führen Sie das `New-ProtectionAlert` -Cmdlet mit der Aktivität aus, für die Sie die Benachrichtigung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="65a18-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="65a18-126">Wenn Sie beispielsweise benachrichtigt werden möchten, wenn die Aktion **UploadDataCompleted-Aktion** ausgeführt wurde, führen Sie das Folgende aus</span><span class="sxs-lookup"><span data-stu-id="65a18-126">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="65a18-127">für den **UploadDataFailed** können Sie das Folgende ausführen</span><span class="sxs-lookup"><span data-stu-id="65a18-127">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="65a18-128">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="65a18-128">Related articles</span></span>

- [<span data-ttu-id="65a18-129">Erstellen benutzerdefinierter Typen vertraulicher Informationen mit genauer Datenübereinstimmung (EDM)</span><span class="sxs-lookup"><span data-stu-id="65a18-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="65a18-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="65a18-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert?view=exchange-ps)