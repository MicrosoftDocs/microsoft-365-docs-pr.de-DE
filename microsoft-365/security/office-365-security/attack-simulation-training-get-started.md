---
title: Erste Schritte mit dem Angriffssimulationstraining
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratoren erfahren, wie Sie mithilfe von Attack Simulationsschulungen simulierte Phishing- und Kennwortangriffe in ihren Microsoft 365 E5- oder Microsoft Defender for Office 365 Plan 2-Organisationen ausführen können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e344153ef433bc13b16136e584ec4da73fcef6a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204089"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="d7dea-103">Erste Schritte mit dem Angriffssimulationstraining</span><span class="sxs-lookup"><span data-stu-id="d7dea-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d7dea-104">Wenn Ihre Organisation über Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2 verfügt, die Funktionen zur Bedrohungsuntersuchung und -reaktion [umfasst,](office-365-ti.md)können Sie das Training zur Angriffssimulation im Microsoft Security Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="d7dea-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="d7dea-105">Diese simulierten Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein tatsächlicher Angriff auf Ihr Endergebnis aus wirkt.</span><span class="sxs-lookup"><span data-stu-id="d7dea-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="d7dea-106">Weitere Informationen finden Sie in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="d7dea-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="d7dea-107">Das Training zur Angriffssimulation ersetzt die alte Angriffssimulator v1-Erfahrung, die unter [Attack Simulator in Microsoft Defender for Office 365 beschrieben wird.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="d7dea-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d7dea-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="d7dea-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d7dea-109">Um das Microsoft Security Center zu öffnen, wechseln Sie zu <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="d7dea-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="d7dea-110">Schulung zur Angriffssimulation finden Sie unter **E-Mail und Zusammenarbeit** \> **Attack simulation training**.</span><span class="sxs-lookup"><span data-stu-id="d7dea-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="d7dea-111">Öffnen Sie , um direkt zu Attack simulation training zu <https://security.microsoft.com/attacksimulator> wechseln.</span><span class="sxs-lookup"><span data-stu-id="d7dea-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="d7dea-112">Weitere Informationen zur Verfügbarkeit von Attack Simulationsschulungen in verschiedenen Microsoft 365-Abonnements finden Sie unter [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="d7dea-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="d7dea-113">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen im Security & Compliance Center oder in Azure Active Directory berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d7dea-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="d7dea-114">Insbesondere müssen Sie Mitglied der Organisationsverwaltung, des Sicherheitsadministrators oder einer der folgenden Rollen sein:  </span><span class="sxs-lookup"><span data-stu-id="d7dea-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="d7dea-115">**Attack Simulator Administrators**: Erstellen und Verwalten aller Aspekte von Angriffssimulationskampagnen.</span><span class="sxs-lookup"><span data-stu-id="d7dea-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="d7dea-116">**Attack Simulator Payload Authors**: Erstellen von Angriffsnutzlasten, die ein Administrator später initiieren kann.</span><span class="sxs-lookup"><span data-stu-id="d7dea-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="d7dea-117">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) oder Informationen zu [Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d7dea-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="d7dea-118">Es gibt keine entsprechenden PowerShell-Cmdlets für attack simulation training.</span><span class="sxs-lookup"><span data-stu-id="d7dea-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="d7dea-119">Angriffssimulations- und Schulungsdaten werden mit anderen Kundendaten für Microsoft 365-Dienste gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d7dea-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="d7dea-120">Weitere Informationen finden Sie unter [Microsoft 365 Data Locations](../../enterprise/o365-data-locations.md).</span><span class="sxs-lookup"><span data-stu-id="d7dea-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="d7dea-121">Die Angriffssimulation ist in den folgenden Regionen verfügbar: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN und KOR.</span><span class="sxs-lookup"><span data-stu-id="d7dea-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

## <a name="simulations"></a><span data-ttu-id="d7dea-122">Simulationen</span><span class="sxs-lookup"><span data-stu-id="d7dea-122">Simulations</span></span>

<span data-ttu-id="d7dea-123">*Phishing* ist ein allgemeiner Begriff für E-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die von legitimen oder vertrauenswürdigen Absendern zu sein scheinen.</span><span class="sxs-lookup"><span data-stu-id="d7dea-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="d7dea-124">*Phishing* ist Teil einer Teilmenge von Techniken, die wir als _Social Engineering klassifizieren._</span><span class="sxs-lookup"><span data-stu-id="d7dea-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="d7dea-125">In Attack simulation training, multiple types of social engineering techniques are available:</span><span class="sxs-lookup"><span data-stu-id="d7dea-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="d7dea-126">**Anmeldeinformationen:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="d7dea-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="d7dea-127">Wenn der Empfänger auf die URL klickt, wird er zu einer Website weitergeleitet, die in der Regel ein Dialogfeld zeigt, in dem der Benutzer nach benutzername und Kennwort gefragt wird.</span><span class="sxs-lookup"><span data-stu-id="d7dea-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="d7dea-128">In der Regel ist die Zielseite so geordnet, dass sie eine bekannte Website repräsentiert, um vertrauen zu können.</span><span class="sxs-lookup"><span data-stu-id="d7dea-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="d7dea-129">**Anlage für** Schadsoftware: Ein Angreifer sendet dem Empfänger eine Nachricht, die eine Anlage enthält.</span><span class="sxs-lookup"><span data-stu-id="d7dea-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="d7dea-130">Wenn der Empfänger die Anlage öffnet, wird beliebiger Code (z. B. ein Makro) auf dem Gerät des Benutzers ausgeführt, um dem Angreifer zu helfen, zusätzlichen Code zu installieren oder sich weiter zu verfestigen.</span><span class="sxs-lookup"><span data-stu-id="d7dea-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="d7dea-131">**Link in attachment**: Dies ist eine Hybridlösung einer Anmeldeinformationsernte.</span><span class="sxs-lookup"><span data-stu-id="d7dea-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="d7dea-132">Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL innerhalb einer Anlage enthält.</span><span class="sxs-lookup"><span data-stu-id="d7dea-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="d7dea-133">Wenn der Empfänger die Anlage öffnet und auf die URL klickt, wird er zu einer Website weitergeleitet, die in der Regel ein Dialogfeld zeigt, in dem der Benutzer nach benutzername und Kennwort gefragt wird.</span><span class="sxs-lookup"><span data-stu-id="d7dea-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="d7dea-134">In der Regel ist die Zielseite so geordnet, dass sie eine bekannte Website repräsentiert, um vertrauen zu können.</span><span class="sxs-lookup"><span data-stu-id="d7dea-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="d7dea-135">**Link zu Schadsoftware:** Ein Angreifer sendet dem Empfänger eine Nachricht, die einen Link zu einer Anlage auf einer bekannten Dateifreigabewebsite enthält (z. B. SharePoint Online oder Dropbox).</span><span class="sxs-lookup"><span data-stu-id="d7dea-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="d7dea-136">Wenn der Empfänger auf die URL klickt, wird die Anlage geöffnet, und beliebiger Code (z. B. ein Makro) wird auf dem Gerät des Benutzers ausgeführt, um dem Angreifer zu helfen, zusätzlichen Code zu installieren oder sich weiter zu verfestigen.</span><span class="sxs-lookup"><span data-stu-id="d7dea-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="d7dea-137">**Drive-by-url:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="d7dea-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="d7dea-138">Wenn der Empfänger auf die URL klickt, wird er zu einer Website weitergeleitet, auf der versucht wird, Hintergrundcode zu ausführen.</span><span class="sxs-lookup"><span data-stu-id="d7dea-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="d7dea-139">Dieser Hintergrundcode versucht, Informationen über den Empfänger zu sammeln oder beliebigen Code auf dem Gerät zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d7dea-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="d7dea-140">In der Regel ist die Zielwebsite eine bekannte Website, die gefährdet wurde, oder ein Klon einer bekannten Website.</span><span class="sxs-lookup"><span data-stu-id="d7dea-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="d7dea-141">Die Vertrautheit mit der Website trägt dazu bei, den Benutzer davon zu überzeugen, dass der Link sicher geklickt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7dea-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="d7dea-142">Diese Technik wird auch als _Wasserungsöffnungsangriff bezeichnet._</span><span class="sxs-lookup"><span data-stu-id="d7dea-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="d7dea-143">Überprüfen Sie die Verfügbarkeit der simulierten Phishing-URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7dea-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="d7dea-144">Wir arbeiten zwar mit vielen ANBIETERN für die URL-Reputation zusammen, um diese Simulations-URLs immer zu erlauben, aber wir verfügen nicht immer über vollständige Abdeckung (z. B. Google Safe Browsing).</span><span class="sxs-lookup"><span data-stu-id="d7dea-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="d7dea-145">Die meisten Anbieter bieten Anleitungen, mit denen Sie bestimmte URLs (z. B. ) immer zulassen <https://support.google.com/chrome/a/answer/7532419> können.</span><span class="sxs-lookup"><span data-stu-id="d7dea-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="d7dea-146">Die URLs, die von attack simulation training verwendet werden, werden in der folgenden Liste beschrieben:</span><span class="sxs-lookup"><span data-stu-id="d7dea-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="d7dea-147">Erstellen einer Simulation</span><span class="sxs-lookup"><span data-stu-id="d7dea-147">Create a simulation</span></span>

<span data-ttu-id="d7dea-148">Schrittweise Anweisungen zum Erstellen und Senden einer neuen Simulation finden Sie unter [Simulate a phishing attack](attack-simulation-training.md).</span><span class="sxs-lookup"><span data-stu-id="d7dea-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="d7dea-149">Erstellen einer Nutzlast</span><span class="sxs-lookup"><span data-stu-id="d7dea-149">Create a payload</span></span>

<span data-ttu-id="d7dea-150">Schrittweise Anweisungen zum Erstellen einer Nutzlast für die Verwendung in einer Simulation finden Sie unter [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="d7dea-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="d7dea-151">Gewinnen von Einblicken</span><span class="sxs-lookup"><span data-stu-id="d7dea-151">Gaining insights</span></span>

<span data-ttu-id="d7dea-152">Schrittweise Anweisungen zum Gewinnen von Einblicken in die Berichterstellung finden Sie unter [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span><span class="sxs-lookup"><span data-stu-id="d7dea-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d7dea-153">Der **Angriffssimulator** verwendet sichere Links in Defender for Office 365, um Klickdaten für die URL in der Nutzlastnachricht, die an zielorientierte Empfänger einer Phishingkampagne gesendet wird, sicher nachverfolgt zu werden, auch wenn die Einstellung Benutzerklicks nicht nachverfolgen unter Richtlinien für sichere Links aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d7dea-153">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>