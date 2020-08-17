---
title: Microsoft 365 Compliance-Unterstützung für Versionshinweise zu Doppelbyte-Zeichensätzen (Vorschau)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Versionshinweise zur Unterstützung von Doppelbyte-Zeichensätzen.
ms.openlocfilehash: 13bac873f2ba18bc166451ea73ec0d569fb30f68
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695251"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="70a90-103">Unterstützung für Versionshinweise zu Doppelbyte-Zeichensätzen (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="70a90-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="70a90-104">Microsoft 365 Information Protection unterstützt jetzt in der Vorschau Sprachen mit Doppelbyte-Zeichensätzen für:</span><span class="sxs-lookup"><span data-stu-id="70a90-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="70a90-105">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="70a90-105">Chinese (simplified)</span></span>
- <span data-ttu-id="70a90-106">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="70a90-106">Chinese (traditional)</span></span>
- <span data-ttu-id="70a90-107">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="70a90-107">Korean</span></span>
- <span data-ttu-id="70a90-108">Japanisch</span><span class="sxs-lookup"><span data-stu-id="70a90-108">Japanese</span></span>

<span data-ttu-id="70a90-109">Diese Vorschau ist nur in der kommerziellen Cloud verfügbar, und die Einführung ist beschränkt auf:</span><span class="sxs-lookup"><span data-stu-id="70a90-109">This preview is only in the commercial cloud and the rollout is limited to:</span></span>

- <span data-ttu-id="70a90-110">Japan</span><span class="sxs-lookup"><span data-stu-id="70a90-110">Japan</span></span>
- <span data-ttu-id="70a90-111">Korea</span><span class="sxs-lookup"><span data-stu-id="70a90-111">Korea</span></span>
- <span data-ttu-id="70a90-112">China</span><span class="sxs-lookup"><span data-stu-id="70a90-112">China</span></span>
- <span data-ttu-id="70a90-113">Hongkong (SAR)</span><span class="sxs-lookup"><span data-stu-id="70a90-113">Hong Kong</span></span>
- <span data-ttu-id="70a90-114">Macau (SAR)</span><span class="sxs-lookup"><span data-stu-id="70a90-114">Macau</span></span>
- <span data-ttu-id="70a90-115">Taiwan</span><span class="sxs-lookup"><span data-stu-id="70a90-115">Taiwan</span></span>

<span data-ttu-id="70a90-116">Diese Unterstützung ist für vertrauliche Informationstypen und Stichwort-Wörterbücher verfügbar und wird in den Lösungen Data Loss Prevention, Communications Compliance, Exchange Online, Microsoft Office SharePoint Online, Microsoft OneDrive for Business und Microsoft Teams widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="70a90-116">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="70a90-117">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="70a90-117">Known issues</span></span>

- <span data-ttu-id="70a90-118">Wenn eine an eine E-Mail angehängte Textdatei im UTF-8-Format ohne Byte-Order-Markierung (BOM) vorliegt, wird die E-Mail von der Kommunikationscompliance-Richtlinie nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="70a90-118">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="70a90-119">Kommunikationscompliance-Richtlinien können keine Werte erkennen, wenn ein Satz für die Richtlinienbedingung eingegeben wird: "Nachricht enthält eines dieser Wörter".</span><span class="sxs-lookup"><span data-stu-id="70a90-119">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="70a90-120">Wenn der in der Richtlinie angegebene Text als Wort geschrieben ist, kann er erkannt werden. Befindet sich der Text jedoch in der Mitte eines Satzes, wird er nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="70a90-120">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="70a90-121">Kommunikationscompliance-Richtlinien, die Wörterbücher als Typinformationen angeben, erkennen private Teams-Chats und Teams-Channel-Chats nicht.</span><span class="sxs-lookup"><span data-stu-id="70a90-121">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="70a90-122">Die folgenden Bedingungen werden für die Kommunikationscompliance-Richtlinie zum gegenwärtigen Zeitpunkt nicht unterstützt (wir planen, diese Probleme in Zukunft zu beheben):</span><span class="sxs-lookup"><span data-stu-id="70a90-122">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="70a90-123">„Nachricht enthält eines dieser Wörter“</span><span class="sxs-lookup"><span data-stu-id="70a90-123">“Message contains any of these words”</span></span>
  - <span data-ttu-id="70a90-124">„Nachricht enthält keines dieser Wörter“</span><span class="sxs-lookup"><span data-stu-id="70a90-124">“Message contains none of these words”</span></span>
  - <span data-ttu-id="70a90-125">„Anlage enthält eines dieser Wörter“</span><span class="sxs-lookup"><span data-stu-id="70a90-125">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="70a90-126">„Anlage enthält eines dieser Wörter“</span><span class="sxs-lookup"><span data-stu-id="70a90-126">“Attachment contains any of these words”</span></span>

<span data-ttu-id="70a90-127">Stattdessen empfehlen wir, einen benutzerdefinierten Typ sensibler Informationen (SIT) mit einem Schlüsselwörterbuch zu erstellen, der Muster in Nachrichten und Anhängen erkennt. Der benutzerdefinierte SIT sollte als Bedingung für die Kommunikationscompliance-Richtlinie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="70a90-127">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
