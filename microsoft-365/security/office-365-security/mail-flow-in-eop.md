---
title: Nachrichtenfluss in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Der Administrator kann sich über die Optionen zum Konfigurieren des Nachrichtenflusses und Routings in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842494"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="41516-103">Nachrichtenfluss in EOP</span><span class="sxs-lookup"><span data-stu-id="41516-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="41516-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="41516-104">**Applies to**</span></span>
- [<span data-ttu-id="41516-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="41516-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="41516-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="41516-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="41516-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41516-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="41516-108">In Microsoft 365 Organisationen mit Exchange Online Postfächern oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer werden alle nachrichten, die an Ihre Organisation gesendet werden, EOP durchlaufen, bevor ihre Mitarbeiter sie sehen.</span><span class="sxs-lookup"><span data-stu-id="41516-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="41516-109">Sie haben Optionen zum Weiterleiten von Nachrichten, die EOP zur Verarbeitung durchlaufen, bevor sie an die Postfächer Ihrer Mitarbeiter weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="41516-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="41516-110">Arbeiten mit Nachrichten und Nachrichtenzugangsoptionen</span><span class="sxs-lookup"><span data-stu-id="41516-110">Working with messages and message access options</span></span>

<span data-ttu-id="41516-111">EOP bietet Flexibilität bei der Weiterleitung Ihrer Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="41516-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="41516-112">In den folgenden Themen werden Schritte im Nachrichtenflussprozess erklärt.</span><span class="sxs-lookup"><span data-stu-id="41516-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="41516-113">[Verwenden der verzeichnisbasierten Edgeblockierung zum Ablehnen von Nachrichten, die an ungültige Empfänger gesendet werden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschreibt das Feature zum blockieren von verzeichnisbasierten Edges, mit dem Sie Nachrichten für ungültige Empfänger am Dienstnetzwerkperimeter ablehnen können.</span><span class="sxs-lookup"><span data-stu-id="41516-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="41516-114">[Das Anzeigen oder Bearbeiten akzeptierter Domänen in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschreibt, wie Domänen verwaltet werden, die Ihrem EOP-Dienst zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="41516-114">[View or edit accepted domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="41516-115">Wenn Sie Ihrer Organisation Unterdomänen hinzufügen, können Sie auch diese mit dem EOP-Dienst verwalten.</span><span class="sxs-lookup"><span data-stu-id="41516-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="41516-116">Weitere Informationen zu Unterdomänen finden Sie unter Aktivieren des [Nachrichtenflusses für Unterdomänen in Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="41516-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="41516-117">[Beim Konfigurieren des Nachrichtenflusses mithilfe von Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) werden Connectors eingeführt und gezeigt, wie Sie diese zum Anpassen des E-Mail-Routings verwenden können.</span><span class="sxs-lookup"><span data-stu-id="41516-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="41516-118">Dazu gehören Szenarien zur Gewährleistung sicherer Kommunikation mit einer Partnerorganisation sowie das Einrichten eines Smarthosts.</span><span class="sxs-lookup"><span data-stu-id="41516-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="41516-119">[Die erweiterte Filterung für Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschreibt, wie Connectors konfiguriert werden, wenn Ihre E-Mails vor EOP an einen Dienst oder ein Gerät weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="41516-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="41516-120">In Hybridumgebungen, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie im lokalen Exchange Nachrichtenflussregeln zur Übersetzung der EOP-Spamfilterbewertung konfigurieren (auch als Transportregeln bezeichnet), damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann.</span><span class="sxs-lookup"><span data-stu-id="41516-120">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="41516-121">Ausführliche Informationen finden Sie unter [Konfigurieren von EOP zum Verschieben von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span><span class="sxs-lookup"><span data-stu-id="41516-121">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span> <span data-ttu-id="41516-122">Wenn Sie Nachrichten nicht in den Junk-E-Mail-Ordner jedes Benutzers verschieben möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Antispamrichtlinien bearbeiten (auch als Inhaltsfilterrichtlinien bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="41516-122">If you don't  want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="41516-123">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="41516-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="41516-124">Überprüfen des Nachrichtenflusses</span><span class="sxs-lookup"><span data-stu-id="41516-124">Verify mail flow</span></span>

<span data-ttu-id="41516-p106">Weitere Informationen zum Überprüfen des EOP-Setups und der Connectorkonfiguration finden Sie im Abschnitt "Woher wissen Sie, dass diese Aufgabe erfolgreich war?" unter [Einrichten Ihres EOP-Diensts](/exchange/standalone-eop/set-up-your-eop-service).</span><span class="sxs-lookup"><span data-stu-id="41516-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service).</span></span>

<span data-ttu-id="41516-127">[Testen Sie den Nachrichtenfluss, indem Sie Ihre Microsoft 365 Connectors überprüfen,](/exchange/mail-flow-best-practices/test-mail-flow) finden Sie Anweisungen zum Testen, ob der Nachrichtenfluss ordnungsgemäß eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="41516-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
