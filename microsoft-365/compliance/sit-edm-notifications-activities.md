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
ms.openlocfilehash: da00c43ae9ba5b129129027df16f49ef80b8757d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288167"
---
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="13fff-103">Erstellen von Benachrichtigungen für genaue Datenübereinstimmungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="13fff-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="13fff-104">Wenn Sie [benutzerdefinierte vertrauliche Informationstypen mit exakter Datenübereinstimmung (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) erstellen, werden im [Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) eine Reihe von Aktivitäten erstellt.</span><span class="sxs-lookup"><span data-stu-id="13fff-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="13fff-105">Mit dem PowerShell-Cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) können Sie Benachrichtigungen erstellen, die Sie über folgende Aktivitäten informieren:</span><span class="sxs-lookup"><span data-stu-id="13fff-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="13fff-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="13fff-106">CreateSchema</span></span>
- <span data-ttu-id="13fff-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="13fff-107">EditSchema</span></span>
- <span data-ttu-id="13fff-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="13fff-108">RemoveSchema</span></span>
- <span data-ttu-id="13fff-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="13fff-109">UploadDataFailed</span></span>
- <span data-ttu-id="13fff-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="13fff-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="13fff-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="13fff-111">Pre-requisites</span></span>

<span data-ttu-id="13fff-112">Das von Ihnen verwendete Konto muss eines der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="13fff-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="13fff-113">ein globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="13fff-113">a global admin</span></span>
- <span data-ttu-id="13fff-114">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="13fff-114">compliance administrator</span></span>
- <span data-ttu-id="13fff-115">Exchange Online-Administrator</span><span class="sxs-lookup"><span data-stu-id="13fff-115">Exchange Online administrator</span></span>

<span data-ttu-id="13fff-116">Weitere Informationen über DLP-Berechtigungen finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="13fff-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="13fff-117">Die EDM-basierte Klassifizierung ist in diesen Abonnements enthalten.</span><span class="sxs-lookup"><span data-stu-id="13fff-117">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="13fff-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="13fff-118">Office 365 E5</span></span>
- <span data-ttu-id="13fff-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="13fff-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="13fff-120">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="13fff-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="13fff-121">Microsoft E5/ A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="13fff-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="13fff-122">Weitere Informationen zur DLP-Lizenzierung finden Sie in den [Microsoft 365-Lizenzierungsrichtlinien für Security & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span><span class="sxs-lookup"><span data-stu-id="13fff-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="13fff-123">Konfigurieren von Benachrichtigungen für EDM-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="13fff-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="13fff-124">Stellen Sie eine Verbindung mit der [Security & Compliance Center PowerShell her](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="13fff-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell)</span></span> 

2. <span data-ttu-id="13fff-125">Führen Sie das `New-ProtectionAlert` -Cmdlet mit der Aktivität aus, für die Sie die Benachrichtigung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="13fff-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="13fff-126">Wenn Sie beispielsweise benachrichtigt werden möchten, wenn die Aktion **UploadDataCompleted-Aktion** ausgeführt wurde, führen Sie das Folgende aus</span><span class="sxs-lookup"><span data-stu-id="13fff-126">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="13fff-127">für den **UploadDataFailed** können Sie das Folgende ausführen</span><span class="sxs-lookup"><span data-stu-id="13fff-127">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="13fff-128">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="13fff-128">Related articles</span></span>

- [<span data-ttu-id="13fff-129">Erstellen benutzerdefinierter Typen vertraulicher Informationen mit genauer Datenübereinstimmung (EDM)</span><span class="sxs-lookup"><span data-stu-id="13fff-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="13fff-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="13fff-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert)