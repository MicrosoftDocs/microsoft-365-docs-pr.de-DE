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
description: Der Administrator kann sich über die Optionen zum Konfigurieren des Nachrichtenflusses und des Routings in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7cd5bfcc95227c59f645422d4939ea6ff77bee1e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206364"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="f6409-103">Nachrichtenfluss in EOP</span><span class="sxs-lookup"><span data-stu-id="f6409-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f6409-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="f6409-104">**Applies to**</span></span>
- [<span data-ttu-id="f6409-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f6409-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f6409-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="f6409-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f6409-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6409-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f6409-108">In Microsoft 365 Organisationen mit Exchange Online Postfächern oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden alle Nachrichten, die an Ihre Organisation gesendet werden, über EOP übergeben, bevor die Mitarbeiter sie sehen.</span><span class="sxs-lookup"><span data-stu-id="f6409-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="f6409-109">Sie haben Optionen zum Routen von Nachrichten, die EOP zur Verarbeitung übergeben, bevor sie an Ihre Arbeitsboxen geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="f6409-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="f6409-110">Arbeiten mit Nachrichten und Nachrichtenzugangsoptionen</span><span class="sxs-lookup"><span data-stu-id="f6409-110">Working with messages and message access options</span></span>

<span data-ttu-id="f6409-111">EOP bietet Flexibilität bei der Routenführung Ihrer Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f6409-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="f6409-112">In den folgenden Themen werden Schritte im Nachrichtenflussprozess erklärt.</span><span class="sxs-lookup"><span data-stu-id="f6409-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="f6409-113">[Verwenden der verzeichnisbasierten Edgeblockierung zum Ablehnen von Nachrichten, die an ungültige Empfänger gesendet werden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschreibt das Verzeichnisbasierte Edgeblockierungsfeature, mit dem Sie Nachrichten für ungültige Empfänger im Umkreis des Dienstnetzwerks ablehnen können.</span><span class="sxs-lookup"><span data-stu-id="f6409-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="f6409-114">[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschreibt die Verwaltung von Domänen, die mit Ihrem EOP-Dienst verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="f6409-114">[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="f6409-115">Wenn Sie Ihrer Organisation Unterdomänen hinzufügen, können Sie auch diese mit dem EOP-Dienst verwalten.</span><span class="sxs-lookup"><span data-stu-id="f6409-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="f6409-116">Weitere Informationen zu Unterdomänen finden Sie unter Aktivieren des [Nachrichtenflusses](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)für Unterdomänen in Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="f6409-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="f6409-117">[Das Konfigurieren des Nachrichtenflusses mithilfe von Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) führt Connectors ein und zeigt, wie Sie sie zum Anpassen des E-Mail-Routings verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f6409-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="f6409-118">Dazu gehören Szenarien zur Gewährleistung sicherer Kommunikation mit einer Partnerorganisation sowie das Einrichten eines Smarthosts.</span><span class="sxs-lookup"><span data-stu-id="f6409-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="f6409-119">[Erweiterte Filterung für Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschreibt, wie Sie Connectors konfigurieren, wenn Ihre E-Mails vor EOP an einen Dienst oder ein Gerät geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="f6409-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="f6409-120">In eigenständigen EOP-Organisationen müssen Sie einige Konfigurationsschritte ausführen, um sicherzustellen, dass Junk-E-Mails ordnungsgemäß an den Junk-E-Mail-Ordner jedes Benutzers geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="f6409-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="f6409-121">Diese finden Sie unter Konfigurieren eigenständiger EOP zum Senden von Spam an den [Junk-E-Mail-Ordner in Hybridumgebungen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="f6409-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="f6409-122">Wenn Sie Nachrichten nicht in den Junk-E-Mail-Ordner jedes Benutzers verschieben möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Antispamrichtlinien bearbeiten (auch als Inhaltsfilterrichtlinien bekannt).</span><span class="sxs-lookup"><span data-stu-id="f6409-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="f6409-123">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f6409-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="f6409-124">Überprüfen des Nachrichtenflusses</span><span class="sxs-lookup"><span data-stu-id="f6409-124">Verify mail flow</span></span>

<span data-ttu-id="f6409-p106">Weitere Informationen zum Überprüfen des EOP-Setups und der Connectorkonfiguration finden Sie im Abschnitt "Woher wissen Sie, dass diese Aufgabe erfolgreich war?" unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="f6409-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="f6409-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span><span class="sxs-lookup"><span data-stu-id="f6409-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>