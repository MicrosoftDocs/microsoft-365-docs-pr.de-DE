---
title: Dienste für Nicht-Kunden, die E-Mails an Office 365 senden
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/2/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Damit Benutzer das Vertrauen in der Verwendung von E-Mails nicht verlieren, hat Microsoft verschiedene Richtlinien und Technologien zum Schutz von Benutzern eingeführt.
ms.openlocfilehash: 9e7985aed7c0b5b5c14c64d49e70ec6c731cb8b9
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032792"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a><span data-ttu-id="dd516-103">Dienste für Nicht-Kunden, die E-Mails an Office 365 senden</span><span class="sxs-lookup"><span data-stu-id="dd516-103">Services for non-customers sending mail to Office 365</span></span>

<span data-ttu-id="dd516-p101">E-Mail-Missbrauch, Junk-E-Mails und betrügerische E-Mails (Phishing) belasten weiterhin das gesamte E-Mail-Ökosystem. Damit Benutzer das Vertrauen in der Verwendung von E-Mails nicht verlieren, hat Microsoft verschiedene Richtlinien und Technologien zum Schutz von Benutzern eingeführt. Allerdings weiß Microsoft, dass seriösen E-Mails nicht negativ beeinträchtigt werden sollten. Daher haben wir eine Reihe von Diensten zusammengestellt, die Absendern dabei helfen, den E-Mail-Versand an Office 365-Benutzer durch proaktives Verwalten ihres Senderufs zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="dd516-p101">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem. To help maintain user trust in the use of email, Microsoft has put in place various policies and technologies to help protect our users. However, Microsoft understands that legitimate email should not be negatively affected. Therefore, we have established a suite of services to help senders improve their ability to deliver email to Office 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="dd516-108">Diese Übersicht enthält Informationen zu Vorteilen, die wir Ihrer Organisation bereitstellen, auch wenn kein Office 365-Kunde sind.</span><span class="sxs-lookup"><span data-stu-id="dd516-108">This overview provides information about benefits we provide to your organization even if you aren't an Office 365 customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="dd516-109">Absenderlösungen</span><span class="sxs-lookup"><span data-stu-id="dd516-109">Sender solutions</span></span>

|<span data-ttu-id="dd516-110">**Dienst**</span><span class="sxs-lookup"><span data-stu-id="dd516-110">**Service**</span></span>|<span data-ttu-id="dd516-111">**Vorteile**</span><span class="sxs-lookup"><span data-stu-id="dd516-111">**Benefits**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd516-112">Onlinehilfeinhalt</span><span class="sxs-lookup"><span data-stu-id="dd516-112">This online help content</span></span>| <span data-ttu-id="dd516-113">Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="dd516-113">Provides:</span></span>  <br/>  <span data-ttu-id="dd516-114">Ausgangspunkt für alle Fragen im Zusammenhang mit der Bereitstellung von Kommunikation für EOP-Benutzer</span><span class="sxs-lookup"><span data-stu-id="dd516-114">A starting point for any questions related to delivering communications to EOP users</span></span>  <br/>  <span data-ttu-id="dd516-115">Enthält einen einfachen Onlineleitfaden mit unseren Richtlinien und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd516-115">Includes a simple online guide with our policies and requirements</span></span>  <br/>  <span data-ttu-id="dd516-116">Eine Übersicht über die Filter für Junk-E-Mails und Authentifizierungstechnologien, die von Microsoft eingesetzt werden</span><span class="sxs-lookup"><span data-stu-id="dd516-116">An overview of the junk email filters and authentication technologies employed by Microsoft</span></span>|
|[<span data-ttu-id="dd516-117">Microsoft-Support</span><span class="sxs-lookup"><span data-stu-id="dd516-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="dd516-118">Stellt Selbsthilfe und Weiterleitungssupport für Zustellungsprobleme bereit.</span><span class="sxs-lookup"><span data-stu-id="dd516-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="dd516-119">Office 365-Anti-Spam-IP-Delist-Portal</span><span class="sxs-lookup"><span data-stu-id="dd516-119">Office 365 Anti-Spam IP Delist Portal</span></span>](#office-365-anti-spam-ip-delist-portal)|<span data-ttu-id="dd516-p102">Ein Tool zum Übermitteln von Anforderungen zum Entfernen von IP-Adressen aus einer Liste. Vor dem Absenden dieser Anforderung hat der Absender die Verantwortung, sicherzustellen, dass alle weiteren E-Mails, die von der fraglichen IP-Adresse ausgehen, weder beleidigend noch böswillig sind.</span><span class="sxs-lookup"><span data-stu-id="dd516-p102">A tool to submit IP delist request. Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="dd516-122">Missbrauchs- und Spammeldung für Junk-E-Mails aus Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dd516-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="dd516-123">Verhindert, dass Spam und andere unerwünschte E-Mails von Exchange Online gesendet werden und das Internet und Ihr E-Mail-System überfrachten.</span><span class="sxs-lookup"><span data-stu-id="dd516-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the Internet and your mail system.</span></span>|

## <a name="microsoft-support"></a><span data-ttu-id="dd516-124">Microsoft-Support</span><span class="sxs-lookup"><span data-stu-id="dd516-124">Microsoft support</span></span>

<span data-ttu-id="dd516-p103">Microsoft bietet verschiedene Supportoptionen für Personen an, die Probleme beim Senden von E-Mails an Office 365-Postfächer haben. Wir empfehlen, dass Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="dd516-p103">Microsoft offers several support options for people having trouble sending mail to Office 365 inboxes. We recommend that you:</span></span>

- <span data-ttu-id="dd516-127">Folgen Sie den Anweisungen in allen Unzustellbarkeitsberichten, die Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="dd516-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="dd516-128">Sehen Sie sich die am häufigsten auftretenden Probleme an, die für Nicht-Kunden in [Problembehandlung für E-Mail-Nachrichten, die an Office 365 gesendet werden](troubleshooting-mail-sent-to-office-365.md) auftreten.</span><span class="sxs-lookup"><span data-stu-id="dd516-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="dd516-129">Verwenden Sie das [Office 365-Delist-Portal](https://sender.office.com) für eine Anforderung, um Ihre IP-Adresse aus der Liste der blockierten Absender zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="dd516-129">Use the [Office 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="dd516-130">Lesen Sie die [Microsoft-Communityforen](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="dd516-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="dd516-p104">Wenden Sie sich unter Verwendung einer anderen Methode an den Office 365-Kunden, an den Sie E-Mails senden möchten, und bitten Sie ihn, den Microsoft-Support zu kontaktieren und ein Supportticket in Ihrem Auftrag zu öffnen. In einigen Fällen muss der Microsoft-Support aus rechtlichen Gründen direkt mit dem Absender kommunizieren, dem der gesperrte die IP-Adressraum gehört. Allerdings können Nicht-Kunden in der Regel keine Supporttickets öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd516-p104">Contact the Office 365 customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf. In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked. However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="dd516-134">Weitere Informationen zum technischen Microsoft-Support für Office 365 finden Sie unter [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span><span class="sxs-lookup"><span data-stu-id="dd516-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="office-365-anti-spam-ip-delist-portal"></a><span data-ttu-id="dd516-135">Office 365-Anti-Spam-IP-Delist-Portal</span><span class="sxs-lookup"><span data-stu-id="dd516-135">Office 365 Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="dd516-p105">Hierbei handelt es sich um ein Self-Service-Portal, das Sie verwenden können, um sich selbst aus der Liste der blockierten Absender von Office 365 zu entfernen. Verwenden Sie dieses Portal, wenn Sie eine Fehlermeldung erhalten, wenn Sie versuchen, eine E-Mail an einen Empfänger zu senden, dessen E-Mail-Adresse sich in Office 365 befindet, und Sie der Meinung sind, dass keine Fehlermeldung auftreten sollte. Weitere Informationen finden Sie unter [Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender von Office 365 zu entfernen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="dd516-p105">This is a self-service portal you can use to remove yourself from the Office 365 blocked senders list. Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Office 365 and you don't think you should be. For more information, see [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="dd516-139">Missbrauchs- und Spammeldung für Junk-E-Mails aus Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dd516-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="dd516-140">Manchmal wird Office 365 von Drittanbietern zum Senden von Junk-E-Mails entgegen den allgemeinen Geschäftsbedingungen und Nutzungsrichtlinien verwendet.</span><span class="sxs-lookup"><span data-stu-id="dd516-140">Sometimes Office 365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="dd516-141">Wenn Sie eine Junk-e-Mail von Office 365 erhalten, können Sie diese Nachrichten an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="dd516-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="dd516-142">Anweisungen finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="dd516-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
