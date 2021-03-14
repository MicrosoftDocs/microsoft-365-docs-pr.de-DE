---
title: Erstellen von Benachrichtigungen für exakte Datenübereinstimmungsaktivitäten (Vorschau)
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
ms.openlocfilehash: a537cffe253fa20cf6838ddf3fd9a51ec440fe76
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766693"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a><span data-ttu-id="aaf89-103">Erstellen von Benachrichtigungen für exakte Datenübereinstimmungsaktivitäten (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="aaf89-103">Create notifications for exact data match activities (preview)</span></span>

<span data-ttu-id="aaf89-104">Wenn Sie [benutzerdefinierte vertrauliche Informationstypen mit exakter Datenübereinstimmung (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) erstellen, werden im [Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) eine Reihe von Aktivitäten erstellt.</span><span class="sxs-lookup"><span data-stu-id="aaf89-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="aaf89-105">Mit dem PowerShell-Cmdlet [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) können Sie Benachrichtigungen erstellen, die Sie über folgende Aktivitäten informieren:</span><span class="sxs-lookup"><span data-stu-id="aaf89-105">You can use the [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="aaf89-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="aaf89-106">CreateSchema</span></span>
- <span data-ttu-id="aaf89-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="aaf89-107">EditSchema</span></span>
- <span data-ttu-id="aaf89-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="aaf89-108">RemoveSchema</span></span>
- <span data-ttu-id="aaf89-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="aaf89-109">UploadDataFailed</span></span>
- <span data-ttu-id="aaf89-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="aaf89-110">UploadDataCompleted</span></span>

> [!NOTE]
> <span data-ttu-id="aaf89-111">Die Möglichkeit, Benachrichtigungen für EDM-Aktivitäten zu erstellen, ist nur für die World Wide- und GCC-Clouds verfügbar.</span><span class="sxs-lookup"><span data-stu-id="aaf89-111">The ability to create notifications for EDM activities is only available for the World Wide and GCC clouds only.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="aaf89-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="aaf89-112">Pre-requisites</span></span>

<span data-ttu-id="aaf89-113">Das von Ihnen verwendete Konto muss eines der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="aaf89-113">The account you use must be one of the following:</span></span>

- <span data-ttu-id="aaf89-114">ein globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="aaf89-114">a global admin</span></span>
- <span data-ttu-id="aaf89-115">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="aaf89-115">compliance administrator</span></span>
- <span data-ttu-id="aaf89-116">Exchange Online-Administrator</span><span class="sxs-lookup"><span data-stu-id="aaf89-116">Exchange Online administrator</span></span>

<span data-ttu-id="aaf89-117">Weitere Informationen über DLP-Berechtigungen finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="aaf89-117">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="aaf89-118">Die EDM-basierte Klassifizierung ist in diesen Abonnements enthalten.</span><span class="sxs-lookup"><span data-stu-id="aaf89-118">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="aaf89-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="aaf89-119">Office 365 E5</span></span>
- <span data-ttu-id="aaf89-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="aaf89-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="aaf89-121">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="aaf89-121">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="aaf89-122">Microsoft E5/ A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="aaf89-122">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="aaf89-123">Weitere Informationen zur DLP-Lizenzierung finden Sie in den [Microsoft 365-Lizenzierungsrichtlinien für Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span><span class="sxs-lookup"><span data-stu-id="aaf89-123">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="aaf89-124">Konfigurieren von Benachrichtigungen für EDM-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="aaf89-124">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="aaf89-125">Stellen Sie eine Verbindung mit der [Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="aaf89-125">Connect to the [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="aaf89-126">Führen Sie das `New-ProtectionAlert` -Cmdlet mit der Aktivität aus, für die Sie die Benachrichtigung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="aaf89-126">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="aaf89-127">Wenn Sie beispielsweise benachrichtigt werden möchten, wenn die Aktion **UploadDataCompleted-Aktion** ausgeführt wurde, führen Sie das Folgende aus</span><span class="sxs-lookup"><span data-stu-id="aaf89-127">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="aaf89-128">für den **UploadDataFailed** können Sie das Folgende ausführen</span><span class="sxs-lookup"><span data-stu-id="aaf89-128">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="aaf89-129">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="aaf89-129">Related articles</span></span>

- [<span data-ttu-id="aaf89-130">Erstellen benutzerdefinierter Typen vertraulicher Informationen mit genauer Datenübereinstimmung (EDM)</span><span class="sxs-lookup"><span data-stu-id="aaf89-130">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="aaf89-131">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="aaf89-131">New-ProtectionAlert</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) 