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
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681501"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="a0c25-103">Unterstützung für Versionshinweise zu Doppelbyte-Zeichensätzen (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a0c25-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="a0c25-104">Microsoft 365 Information Protection unterstützt jetzt in der Vorschau Sprachen mit Doppelbyte-Zeichensätzen für:</span><span class="sxs-lookup"><span data-stu-id="a0c25-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="a0c25-105">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="a0c25-105">Chinese (simplified)</span></span>
- <span data-ttu-id="a0c25-106">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="a0c25-106">Chinese (traditional)</span></span>
- <span data-ttu-id="a0c25-107">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="a0c25-107">Korean</span></span>
- <span data-ttu-id="a0c25-108">Japanisch</span><span class="sxs-lookup"><span data-stu-id="a0c25-108">Japanese</span></span>

<span data-ttu-id="a0c25-109">Diese Unterstützung ist für vertrauliche Informationstypen und Stichwort-Wörterbücher verfügbar und wird in den Lösungen Data Loss Prevention, Communications Compliance, Exchange Online, Microsoft Office SharePoint Online, Microsoft OneDrive for Business und Microsoft Teams widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="a0c25-109">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a0c25-110">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="a0c25-110">Known issues</span></span>

- <span data-ttu-id="a0c25-111">Wenn eine an eine E-Mail angehängte Textdatei im UTF-8-Format ohne Byte-Order-Markierung (BOM) vorliegt, wird die E-Mail von der Kommunikationscompliance-Richtlinie nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="a0c25-111">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="a0c25-112">Kommunikationscompliance-Richtlinien können keine Werte erkennen, wenn ein Satz für die Richtlinienbedingung eingegeben wird: "Nachricht enthält eines dieser Wörter".</span><span class="sxs-lookup"><span data-stu-id="a0c25-112">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="a0c25-113">Wenn der in der Richtlinie angegebene Text als Wort geschrieben ist, kann er erkannt werden. Befindet sich der Text jedoch in der Mitte eines Satzes, wird er nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="a0c25-113">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="a0c25-114">Kommunikationscompliance-Richtlinien, die Wörterbücher als Typinformationen angeben, erkennen private Teams-Chats und Teams-Channel-Chats nicht.</span><span class="sxs-lookup"><span data-stu-id="a0c25-114">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="a0c25-115">Die folgenden Bedingungen werden für die Kommunikationscompliance-Richtlinie zum gegenwärtigen Zeitpunkt nicht unterstützt (wir planen, diese Probleme in Zukunft zu beheben):</span><span class="sxs-lookup"><span data-stu-id="a0c25-115">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="a0c25-116">„Nachricht enthält eines dieser Wörter“</span><span class="sxs-lookup"><span data-stu-id="a0c25-116">“Message contains any of these words”</span></span>
  - <span data-ttu-id="a0c25-117">„Nachricht enthält keines dieser Wörter“</span><span class="sxs-lookup"><span data-stu-id="a0c25-117">“Message contains none of these words”</span></span>
  - <span data-ttu-id="a0c25-118">„Anlage enthält eines dieser Wörter“</span><span class="sxs-lookup"><span data-stu-id="a0c25-118">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="a0c25-119">„Anlage enthält eines dieser Wörter“</span><span class="sxs-lookup"><span data-stu-id="a0c25-119">“Attachment contains any of these words”</span></span>

<span data-ttu-id="a0c25-120">Stattdessen empfehlen wir, einen benutzerdefinierten Typ sensibler Informationen (SIT) mit einem Schlüsselwörterbuch zu erstellen, der Muster in Nachrichten und Anhängen erkennt. Der benutzerdefinierte SIT sollte als Bedingung für die Kommunikationscompliance-Richtlinie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0c25-120">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
