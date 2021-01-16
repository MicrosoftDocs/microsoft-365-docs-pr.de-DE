---
title: Erste Schritte mit dem Angriffssimulationstraining
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie mithilfe von Angriffssimulationsschulungen simulierte Phishing- und Kennwortangriffe in ihren Microsoft 365 E5- oder Microsoft Defender für Office 365 Plan 2-Organisationen ausführen.
ms.openlocfilehash: 2c00fb27748887c6b8e2fa1458b10f0c3405eef7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877164"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="15670-103">Erste Schritte mit dem Angriffssimulationstraining</span><span class="sxs-lookup"><span data-stu-id="15670-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="15670-104">Wenn Ihre Organisation über Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2 verfügt, der Funktionen zur Untersuchung und Reaktion auf Bedrohungen [umfasst,](office-365-ti.md)können Sie die Angriffssimulationsschulung im Microsoft Security Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="15670-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="15670-105">Diese simulierten Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein tatsächlicher Angriff auf Ihr Endergebnis ausdingt.</span><span class="sxs-lookup"><span data-stu-id="15670-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="15670-106">Lesen Sie diesen Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="15670-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="15670-107">Das Training zur Angriffssimulation ersetzt die alte Angriffssimulator v1-Erfahrung, die im Angriffssimulator [in Microsoft Defender für Office 365 beschrieben wird.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="15670-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="15670-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="15670-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="15670-109">Um das Microsoft Security Center zu öffnen, wechseln Sie zu <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="15670-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="15670-110">Das Training zur Angriffssimulation ist im **E-Mail- und Zusammenarbeitstraining** \> **zur Angriffssimulation verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="15670-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="15670-111">Öffnen Sie das , um direkt zum Angriffssimulationstraining zu <https://security.microsoft.com/attacksimulator> wechseln.</span><span class="sxs-lookup"><span data-stu-id="15670-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="15670-112">Weitere Informationen zur Verfügbarkeit von Attack Simulation Training in verschiedenen Microsoft 365-Abonnements finden Sie in [der Microsoft Defender für Office 365-Dienstbeschreibung.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="15670-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="15670-113">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen im Security & Compliance Center oder in Azure Active Directory Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="15670-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="15670-114">Insbesondere müssen Sie Mitglied der Organisationsverwaltung, des Sicherheitsadministrators oder einer der folgenden Rollen sein:  </span><span class="sxs-lookup"><span data-stu-id="15670-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="15670-115">**Administratoren des Angriffssimulators:** Erstellen und Verwalten aller Aspekte von Angriffssimulationskampagnen.</span><span class="sxs-lookup"><span data-stu-id="15670-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="15670-116">**Autoren der Angriffssimulatornutzlast:** Erstellen Sie Angriffsnutzlasten, die ein Administrator später initiieren kann.</span><span class="sxs-lookup"><span data-stu-id="15670-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="15670-117">Weitere Informationen finden Sie unter ["Berechtigungen" im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) oder unter ["Informationen zu Administratorrollen".](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="15670-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="15670-118">Es gibt keine entsprechenden PowerShell-Cmdlets für attack simulation training.</span><span class="sxs-lookup"><span data-stu-id="15670-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="15670-119">Angriffssimulations- und Schulungsdaten werden mit anderen Kundendaten für Microsoft 365-Dienste gespeichert.</span><span class="sxs-lookup"><span data-stu-id="15670-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="15670-120">Weitere Informationen finden Sie unter [Microsoft 365-Datenspeicherorte.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="15670-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="15670-121">Die Angriffssimulation ist derzeit nicht in den folgenden Regionen verfügbar: SGP, NOR, UAE, ZAF, GER, BRA und CHE.</span><span class="sxs-lookup"><span data-stu-id="15670-121">Attack simulation is currently not available in the following regions: SGP, NOR, UAE, ZAF, GER, BRA, and CHE.</span></span>

## <a name="simulations"></a><span data-ttu-id="15670-122">Simulationen</span><span class="sxs-lookup"><span data-stu-id="15670-122">Simulations</span></span>

<span data-ttu-id="15670-123">*Phishing* ist ein allgemeiner Begriff für E-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die von legitimen oder vertrauenswürdigen Absendern zu sein scheinen.</span><span class="sxs-lookup"><span data-stu-id="15670-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="15670-124">*Phishing* ist Teil einer Teilmenge von Techniken, die wir als _Social Engineering klassifizieren._</span><span class="sxs-lookup"><span data-stu-id="15670-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="15670-125">Im Training zur Angriffssimulation sind mehrere Arten von Social -Engineering-Techniken verfügbar:</span><span class="sxs-lookup"><span data-stu-id="15670-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="15670-126">**Datenergreifung** mit Anmeldeinformationen: Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="15670-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="15670-127">Wenn der Empfänger auf die URL klickt, wird er zu einer Website weitergeleitet, in der in der Regel ein Dialogfeld angezeigt wird, in dem der Benutzer nach benutzername und Kennwort gefragt wird.</span><span class="sxs-lookup"><span data-stu-id="15670-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="15670-128">In der Regel ist die Zielseite so umdeutend, dass sie eine bekannte Website repräsentiert, um eine Vertrauensstellung für den Benutzer zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="15670-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="15670-129">**Schadsoftwareanlage:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine Anlage enthält.</span><span class="sxs-lookup"><span data-stu-id="15670-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="15670-130">Wenn der Empfänger die Anlage öffnet, wird beliebiger Code (z. B. ein Makro) auf dem Gerät des Benutzers ausgeführt, um dem Angreifer zu helfen, zusätzlichen Code zu installieren oder sich weiter zu verangreifen.</span><span class="sxs-lookup"><span data-stu-id="15670-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="15670-131">**Link in Anlage:** Dies ist eine Hybridbereitstellung einer Anmeldeinformationsernte.</span><span class="sxs-lookup"><span data-stu-id="15670-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="15670-132">Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL innerhalb einer Anlage enthält.</span><span class="sxs-lookup"><span data-stu-id="15670-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="15670-133">Wenn der Empfänger die Anlage öffnet und auf die URL klickt, wird er zu einer Website weitergeleitet, in der normalerweise ein Dialogfeld angezeigt wird, in dem der Benutzer nach benutzername und Kennwort gefragt wird.</span><span class="sxs-lookup"><span data-stu-id="15670-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="15670-134">In der Regel ist die Zielseite so umdeutend, dass sie eine bekannte Website repräsentiert, um eine Vertrauensstellung für den Benutzer zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="15670-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="15670-135">**Link zu Schadsoftware:** Ein Angreifer sendet dem Empfänger eine Nachricht, die einen Link zu einer Anlage auf einer bekannten Dateifreigabewebsite enthält (z. B. SharePoint Online oder Dropbox).</span><span class="sxs-lookup"><span data-stu-id="15670-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="15670-136">Wenn der Empfänger auf die URL klickt, wird die Anlage geöffnet, und auf dem Gerät des Benutzers wird beliebiger Code (z. B. ein Makro) ausgeführt, damit der Angreifer zusätzlichen Code installieren oder sich weiter verfestigen kann.</span><span class="sxs-lookup"><span data-stu-id="15670-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="15670-137">**Laufwerk-nach-URL:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="15670-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="15670-138">Wenn der Empfänger auf die URL klickt, wird er zu einer Website weitergeleitet, die versucht, Hintergrundcode ausführen.</span><span class="sxs-lookup"><span data-stu-id="15670-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="15670-139">Dieser Hintergrundcode versucht, Informationen über den Empfänger zu sammeln oder beliebigen Code auf dem Gerät zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="15670-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="15670-140">In der Regel ist die Zielwebsite eine bekannte Website, die gefährdet wurde, oder ein Klon einer bekannten Website.</span><span class="sxs-lookup"><span data-stu-id="15670-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="15670-141">Die Vertrautheit mit der Website trägt dazu bei, den Benutzer davon zu überzeugen, dass der Link sicher angeklickt werden kann.</span><span class="sxs-lookup"><span data-stu-id="15670-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="15670-142">Diese Technik wird auch als _Grubenangriff bezeichnet._</span><span class="sxs-lookup"><span data-stu-id="15670-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="15670-143">Überprüfen Sie die Verfügbarkeit der simulierten Phishing-URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="15670-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="15670-144">Wir arbeiten zwar mit vielen Anbietern von URL-Reputation zusammen, um diese Simulations-URLs immer zu erlauben, aber wir verfügen nicht immer über vollständige Abdeckung (z. B. Google Safe Browsing).</span><span class="sxs-lookup"><span data-stu-id="15670-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="15670-145">Die meisten Anbieter bieten Anleitungen, mit denen Sie immer bestimmte URLs zulassen können (z. B. <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="15670-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="15670-146">Die URLs, die von der Attack Simulation Training verwendet werden, werden in der folgenden Liste beschrieben:</span><span class="sxs-lookup"><span data-stu-id="15670-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="15670-147">Erstellen einer Simulation</span><span class="sxs-lookup"><span data-stu-id="15670-147">Create a simulation</span></span>

<span data-ttu-id="15670-148">Schritt-für-Schritt-Anleitungen zum Erstellen und Senden einer neuen Simulation finden Sie unter [Simulieren eines Phishingangriffs.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="15670-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="15670-149">Erstellen einer Nutzlast</span><span class="sxs-lookup"><span data-stu-id="15670-149">Create a payload</span></span>

<span data-ttu-id="15670-150">Schrittweise Anweisungen zum Erstellen einer Nutzlast für die Verwendung innerhalb einer Simulation finden Sie unter Erstellen einer benutzerdefinierten Nutzlast für [attack simulation training](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="15670-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="15670-151">Gewinnen von Einblicken</span><span class="sxs-lookup"><span data-stu-id="15670-151">Gaining insights</span></span>

<span data-ttu-id="15670-152">Schritt-für-Schritt-Anleitungen zum Gewinnen von Einblicken in die Berichterstellung finden Sie unter ["Einblicke durch Attack Simulation Training".](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="15670-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>
