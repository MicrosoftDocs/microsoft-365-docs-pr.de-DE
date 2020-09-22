---
title: Senden von e-Mails an Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f9d4b5b6-8f4c-44df-9b06-2f9b3058ca20
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie als externer Absender die Möglichkeit zur Zustellung von e-Mails an Benutzer in Microsoft 365 verbessern können. Erfahren Sie auch, wie Junk-e-Mails & Phishing-versuchen als externer Benutzer gemeldet werden.
ms.openlocfilehash: 0c0a981d12fa5b8159789a69597f83eb15d9b194
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196797"
---
# <a name="sending-mail-to-microsoft-365"></a><span data-ttu-id="cad30-104">Senden von e-Mails an Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cad30-104">Sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cad30-105">Diese Artikel helfen externen Absendern, ihre Reputation zu verbessern und die Möglichkeit zu erhöhen, e-Mails an Benutzer in Microsoft 365 zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="cad30-105">These articles help external senders improve their reputation and increase their ability to deliver email to users in Microsoft 365.</span></span> <span data-ttu-id="cad30-106">Sie stellen außerdem einige Informationen dazu bereit, wie Sie Junk-e-Mails und Phishing-Versuche melden können, selbst wenn Sie kein Microsoft 365-Benutzer sind.</span><span class="sxs-lookup"><span data-stu-id="cad30-106">They also provide some information about how you can report junk email and phishing attempts even if you aren't a Microsoft 365 user yourself.</span></span>

<span data-ttu-id="cad30-107">Wenn Sie kein Kunde sind, aber versuchen, e-Mails an eine Person in der Person zu senden, sind Sie an der richtigen Stelle.</span><span class="sxs-lookup"><span data-stu-id="cad30-107">If you are not a customer, but are trying to send mail to someone in who is, you are in the right place.</span></span> <span data-ttu-id="cad30-108">Wenn Sie Administrator sind und Hilfe bei der Bekämpfung von Spam benötigen, ist dies nicht der richtige Abschnitt für Sie.</span><span class="sxs-lookup"><span data-stu-id="cad30-108">If you are an administrator and you need help fighting spam, this is not the right section for you.</span></span> <span data-ttu-id="cad30-109">Wechseln Sie stattdessen zu [Anti-Spam and Anti-Malware Protection in Microsoft 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="cad30-109">Instead, go to [Anti-spam and anti-malware protection in Microsoft 365](anti-spam-and-anti-malware-protection.md).</span></span>

****

|<span data-ttu-id="cad30-110">Inhalt</span><span class="sxs-lookup"><span data-stu-id="cad30-110">For information about...</span></span>|<span data-ttu-id="cad30-111">Sieh...</span><span class="sxs-lookup"><span data-stu-id="cad30-111">See...</span></span>|
|---|---|
|<span data-ttu-id="cad30-112">Dienste, die wir Administratoren von e-Mail-Systemen zur Verfügung stellen, die einzelne und Massen-e-Mails an Kunden senden.</span><span class="sxs-lookup"><span data-stu-id="cad30-112">Services we provide to administrators of email systems that are sending individual and bulk email to customers.</span></span>|[<span data-ttu-id="cad30-113">Dienste für Nicht-Kunden, die E-Mails an Office 365 senden</span><span class="sxs-lookup"><span data-stu-id="cad30-113">Services for non-customers sending mail to Office 365</span></span>](services-for-non-customers.md)|
|<span data-ttu-id="cad30-114">Beheben von Problemen beim erreichen von Kunden in Microsoft 365 per e-Mail.</span><span class="sxs-lookup"><span data-stu-id="cad30-114">How to fix problems reaching customers in Microsoft 365 through email.</span></span> <span data-ttu-id="cad30-115">Bewährte Methoden für das Senden von Massen-e-Mails an Microsoft 365-Empfänger.</span><span class="sxs-lookup"><span data-stu-id="cad30-115">Best practices for sending bulk mail to Microsoft 365 recipients.</span></span>|[<span data-ttu-id="cad30-116">Problembehandlung für E-Mail-Nachrichten, die an Office 365 gesendet werden</span><span class="sxs-lookup"><span data-stu-id="cad30-116">Troubleshooting mail sent to Office 365</span></span>](troubleshooting-mail-sent-to-office-365.md)|
|<span data-ttu-id="cad30-117">Wie Microsoft 365 verhindert, dass Junk-e-Mails, einschließlich Phishing-und Spoofing-e-Mails, an unsere Kunden gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cad30-117">How Microsoft 365 prevents junk email, including phishing and spoofing email, from being sent to our customers.</span></span>|[<span data-ttu-id="cad30-118">Anti-Spam-Schutz in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cad30-118">Anti-spam protection in Microsoft 365</span></span>](anti-spam-protection.md)|
|<span data-ttu-id="cad30-119">Wie Sie, ein Administrator, der e-Mails an Microsoft 365-Kunden sendet, verhindern, dass e-Mails durch Einhaltung unserer Anti-Spam-Richtlinien blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="cad30-119">How you, an administrator sending email to Microsoft 365 customers, can avoid having email blocked by adhering to our anti-spam policies.</span></span> <span data-ttu-id="cad30-120">Hierbei handelt es sich um die rechtliche Aspekte, die Sie kennen müssen.</span><span class="sxs-lookup"><span data-stu-id="cad30-120">This is the legal stuff you need to know.</span></span>|[<span data-ttu-id="cad30-121">Referenz: Richtlinien, Methoden und Anleitungen</span><span class="sxs-lookup"><span data-stu-id="cad30-121">Reference: Policies, practices, and guidelines</span></span>](reference-policies-practices-and-guidelines.md)|
|
