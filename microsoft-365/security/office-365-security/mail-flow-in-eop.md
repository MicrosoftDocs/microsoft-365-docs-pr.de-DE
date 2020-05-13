---
title: Nachrichtenfluss in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Der Administrator kann Informationen zu den Optionen zum Konfigurieren von Nachrichtenfluss und Routing in Exchange Online Protection (EoP) erhalten.
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208330"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="b26d5-103">Nachrichtenfluss in EOP</span><span class="sxs-lookup"><span data-stu-id="b26d5-103">Mail flow in EOP</span></span>

<span data-ttu-id="b26d5-104">In Microsoft 365-Organisationen mit Exchange Online Postfächern oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer werden alle an Ihre Organisation gesendeten Nachrichten über EoP geleitet, bevor Ihre Mitarbeiter Sie sehen.</span><span class="sxs-lookup"><span data-stu-id="b26d5-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="b26d5-105">Sie haben Optionen zum Weiterleiten von Nachrichten, die EoP zur Verarbeitung übergeben, bevor Sie an die Postfächer der Arbeitskraft weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b26d5-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="b26d5-106">Arbeiten mit Nachrichten und Nachrichtenzugangsoptionen</span><span class="sxs-lookup"><span data-stu-id="b26d5-106">Working with messages and message access options</span></span>

<span data-ttu-id="b26d5-107">EoP bietet Flexibilität bei der Weiterleitung Ihrer Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b26d5-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="b26d5-108">In den folgenden Themen werden Schritte im Nachrichtenflussprozess erklärt.</span><span class="sxs-lookup"><span data-stu-id="b26d5-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="b26d5-109">[Verwenden der verzeichnisbasierten Edge-Blockierung zum ablehnen von Nachrichten, die an ungültige Empfänger gesendet wurden](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschreibt das Feature für die verzeichnisbasierte Edge-Blockierung, mit dem Sie Nachrichten für ungültige Empfänger im Dienst Netzwerkumkreis ablehnen können.</span><span class="sxs-lookup"><span data-stu-id="b26d5-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="b26d5-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschreibt die Verwaltung von Domänen, die mit Ihrem EOP-Dienst verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b26d5-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="b26d5-111">Wenn Sie Ihrer Organisation Unterdomänen hinzufügen, können Sie auch diese mit dem EOP-Dienst verwalten.</span><span class="sxs-lookup"><span data-stu-id="b26d5-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="b26d5-112">Weitere Informationen zu Unterdomänen finden Sie unter [Aktivieren des Nachrichtenflusses für Unterdomänen in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="b26d5-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="b26d5-113">[Konfigurieren des Nachrichtenflusses mit Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) stellt Connectors vor und zeigt, wie Sie das e-Mail-Routing anpassen können.</span><span class="sxs-lookup"><span data-stu-id="b26d5-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="b26d5-114">Dazu gehören Szenarien zur Gewährleistung sicherer Kommunikation mit einer Partnerorganisation sowie das Einrichten eines Smarthosts.</span><span class="sxs-lookup"><span data-stu-id="b26d5-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="b26d5-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschreibt, wie Connectors konfiguriert werden, wenn Ihre e-Mails vor EoP an einen Dienst oder ein Gerät weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b26d5-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="b26d5-116">In eigenständigen EoP-Organisationen müssen Sie eine Reihe von Konfigurationsschritten ausführen, um sicherzustellen, dass Junk-e-Mails ordnungsgemäß an den Junk-e-Mail-Ordner jedes Benutzers weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b26d5-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="b26d5-117">Diese werden in [Konfigurieren von eigenständigen EoP zur Zustellung von Spam an den Junk-e-Mail-Ordner in Hybrid Umgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b26d5-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="b26d5-118">Wenn Sie keine Nachrichten in den Junk-e-Mail-Ordner der einzelnen Benutzer übertragen möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Anti-Spam-Richtlinien (auch bekannt als Inhaltsfilter-Richtlinien) bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b26d5-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="b26d5-119">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b26d5-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="b26d5-120">Überprüfen des Nachrichtenflusses</span><span class="sxs-lookup"><span data-stu-id="b26d5-120">Verify mail flow</span></span>

<span data-ttu-id="b26d5-p106">Weitere Informationen zum Überprüfen des EOP-Setups und der Connectorkonfiguration finden Sie im Abschnitt "Woher wissen Sie, dass diese Aufgabe erfolgreich war?" unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="b26d5-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="b26d5-123">[Testen des Nachrichtenflusses durch Validieren der Microsoft 365-Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) enthält Anweisungen zum Testen, ob der Nachrichtenfluss ordnungsgemäß eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="b26d5-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
