---
title: Dienste für Nichtkunden, die E-Mails an Microsoft 365 senden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Damit Benutzer das Vertrauen in der Verwendung von E-Mails nicht verlieren, hat Microsoft verschiedene Richtlinien und Technologien zum Schutz von Benutzern eingeführt.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903799"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="79e87-103">Dienste für Nichtkunden, die E-Mails an Microsoft 365 senden</span><span class="sxs-lookup"><span data-stu-id="79e87-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="79e87-104">E-Mail-Missbrauch, Junk-E-Mails und betrügerische E-Mails (Phishing) belasten weiterhin das gesamte E-Mail-Ökosystem.</span><span class="sxs-lookup"><span data-stu-id="79e87-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="79e87-105">Um das Vertrauen der Benutzer in die Verwendung von E-Mails zu erhalten, hat Microsoft verschiedene Richtlinien und Technologien zum Schutz unserer Benutzer entwickelt.</span><span class="sxs-lookup"><span data-stu-id="79e87-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="79e87-106">Allerdings weiß Microsoft, dass seriösen E-Mails nicht negativ beeinträchtigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="79e87-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="79e87-107">Aus diesem Grund haben wir eine Reihe von Diensten eingerichtet, mit deren Hilfe Absender ihre Fähigkeit verbessern können, E-Mails an Microsoft 365-Benutzer zu senden, indem sie ihre Sendere reputation proaktiv verwalten.</span><span class="sxs-lookup"><span data-stu-id="79e87-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="79e87-108">Diese Übersicht enthält Informationen zu Vorteilen, die wir Ihrer Organisation bieten, auch wenn Sie kein Kunde sind.</span><span class="sxs-lookup"><span data-stu-id="79e87-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="79e87-109">Absenderlösungen</span><span class="sxs-lookup"><span data-stu-id="79e87-109">Sender solutions</span></span>

****

|<span data-ttu-id="79e87-110">Dienst</span><span class="sxs-lookup"><span data-stu-id="79e87-110">Service</span></span>|<span data-ttu-id="79e87-111">Vorteile</span><span class="sxs-lookup"><span data-stu-id="79e87-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="79e87-112">Onlinehilfeinhalt</span><span class="sxs-lookup"><span data-stu-id="79e87-112">This online help content</span></span>|<span data-ttu-id="79e87-113">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="79e87-113">Provides:</span></span> <ul><li><span data-ttu-id="79e87-114">Ein Ausgangspunkt für alle Fragen im Zusammenhang mit der Bereitstellung von Kommunikationen an EOP-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="79e87-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="79e87-115">Enthält eine einfache Onlineanleitung mit unseren Richtlinien und Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="79e87-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="79e87-116">Eine Übersicht über die Junk-E-Mail-Filter und Authentifizierungstechnologien, die von Microsoft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79e87-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="79e87-117">Microsoft-Support</span><span class="sxs-lookup"><span data-stu-id="79e87-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="79e87-118">Stellt Selbsthilfe und Weiterleitungssupport für Zustellungsprobleme bereit.</span><span class="sxs-lookup"><span data-stu-id="79e87-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="79e87-119">Antispam-IP-Listenportal</span><span class="sxs-lookup"><span data-stu-id="79e87-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="79e87-p102">Ein Tool zum Übermitteln von Anforderungen zum Entfernen von IP-Adressen aus einer Liste. Vor dem Absenden dieser Anforderung hat der Absender die Verantwortung, sicherzustellen, dass alle weiteren E-Mails, die von der fraglichen IP-Adresse ausgehen, weder beleidigend noch böswillig sind.</span><span class="sxs-lookup"><span data-stu-id="79e87-p102">A tool to submit IP delist request. Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="79e87-122">Missbrauchs- und Spammeldung für Junk-E-Mails aus Exchange Online</span><span class="sxs-lookup"><span data-stu-id="79e87-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="79e87-123">Verhindert, dass Spam und andere unerwünschte E-Mails von Exchange Online gesendet werden und das Internet und Ihr E-Mail-System überladen.</span><span class="sxs-lookup"><span data-stu-id="79e87-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="79e87-124">Microsoft-Support</span><span class="sxs-lookup"><span data-stu-id="79e87-124">Microsoft support</span></span>

<span data-ttu-id="79e87-125">Microsoft bietet mehrere Supportoptionen für Personen, die Probleme beim Senden von E-Mails an Microsoft 365-Empfänger haben.</span><span class="sxs-lookup"><span data-stu-id="79e87-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="79e87-126">Wir empfehlen, dass Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="79e87-126">We recommend that you:</span></span>

- <span data-ttu-id="79e87-127">Folgen Sie den Anweisungen in allen Unzustellbarkeitsberichten, die Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="79e87-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="79e87-128">Sehen Sie sich die am häufigsten auftretenden Probleme an, die für Nicht-Kunden in [Problembehandlung für E-Mail-Nachrichten, die an Office 365 gesendet werden](troubleshooting-mail-sent-to-office-365.md) auftreten.</span><span class="sxs-lookup"><span data-stu-id="79e87-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="79e87-129">Verwenden Sie [das Microsoft 365-Listendelist-Portal,](https://sender.office.com) um eine Anforderung zu senden, damit Ihre IP aus der Liste blockierter Absender entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="79e87-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="79e87-130">Lesen Sie die [Microsoft-Communityforen](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="79e87-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="79e87-131">Wenden Sie sich an den Kunden, den Sie mit einer anderen Methode per E-Mail kontaktieren möchten, und bitten Sie ihn, sich an den Microsoft-Support zu wenden und in Ihrem Namen ein Supportticket zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="79e87-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="79e87-132">In einigen Fällen muss der Microsoft-Support aus rechtlichen Gründen direkt mit dem Absender kommunizieren, dem der gesperrte die IP-Adressraum gehört.</span><span class="sxs-lookup"><span data-stu-id="79e87-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="79e87-133">Allerdings können Nicht-Kunden in der Regel keine Supporttickets öffnen.</span><span class="sxs-lookup"><span data-stu-id="79e87-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="79e87-134">Weitere Informationen zum technischen Microsoft-Support für Office 365 finden Sie unter [Support](/office365/servicedescriptions/office-365-platform-service-description/support).</span><span class="sxs-lookup"><span data-stu-id="79e87-134">For more information about Microsoft Technical support for Office 365, see [Support](/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="79e87-135">Antispam-IP-Listenportal</span><span class="sxs-lookup"><span data-stu-id="79e87-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="79e87-136">Dies ist ein Self-Service-Portal, mit dem Sie sich selbst aus der Liste blockierter Absender von Microsoft 365 entfernen können.</span><span class="sxs-lookup"><span data-stu-id="79e87-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="79e87-137">Verwenden Sie dieses Portal, wenn Sie eine Fehlermeldung erhalten, wenn Sie versuchen, eine E-Mail an einen Empfänger zu senden, dessen E-Mail-Adresse sich in Microsoft 365 befindet und Sie nicht denken, dass Sie dies sein sollten.</span><span class="sxs-lookup"><span data-stu-id="79e87-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="79e87-138">Weitere Informationen finden Sie unter [Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender zu entfernen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="79e87-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="79e87-139">Missbrauchs- und Spammeldung für Junk-E-Mails aus Exchange Online</span><span class="sxs-lookup"><span data-stu-id="79e87-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="79e87-140">Manchmal wird Microsoft365 von Drittanbietern verwendet, um Junk-E-Mails zu senden, und dies unter Verstoß gegen unsere Nutzungsbedingungen und Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="79e87-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="79e87-141">Wenn Sie Junk-E-Mails von Office 365 erhalten, können Sie diese Nachrichten an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="79e87-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="79e87-142">Anweisungen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="79e87-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>