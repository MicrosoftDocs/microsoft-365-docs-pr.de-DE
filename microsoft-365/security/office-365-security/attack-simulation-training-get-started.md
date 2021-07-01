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
description: Administratoren können erfahren, wie Sie mithilfe von Angriffssimulationsschulungen simulierte Phishing- und Kennwortangriffe in ihren Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2-Organisationen ausführen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1fa10d0d29b76d1631dd349d255b6c386557b5b8
ms.sourcegitcommit: 2266c2da090bc9a6dc1e01dea07f26901d20d57b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53222670"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="83a68-103">Erste Schritte mit dem Angriffssimulationstraining</span><span class="sxs-lookup"><span data-stu-id="83a68-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="83a68-104">**Gilt** [für Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="83a68-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="83a68-105">Wenn Ihre Organisation über Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2 verfügt, der Funktionen für [die Untersuchung und Reaktion auf Bedrohungen](office-365-ti.md)umfasst, können Sie die Angriffssimulationsschulung im Microsoft 365 Defender Portal verwenden, um realistische Angriffsszenarien in Ihrer Organisation auszuführen.</span><span class="sxs-lookup"><span data-stu-id="83a68-105">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="83a68-106">Diese simulierten Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein realer Angriff auf Ihre Unterlinie auswirkt.</span><span class="sxs-lookup"><span data-stu-id="83a68-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="83a68-107">Lesen Sie diesen Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="83a68-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="83a68-108">Das Angriffssimulationstraining ersetzt die alte Angriffssimulator-V1-Erfahrung, die im [Angriffssimulator in Microsoft Defender für Office 365](attack-simulator.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="83a68-108">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="83a68-109">Wissenswertes, bevor Sie anfangen</span><span class="sxs-lookup"><span data-stu-id="83a68-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="83a68-110">Um das Microsoft 365 Defender-Portal zu öffnen, gehen Sie zu <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="83a68-110">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="83a68-111">Angriffssimulationsschulungen sind im Angriffssimulationstraining für **E-Mail und Zusammenarbeit** \> verfügbar.</span><span class="sxs-lookup"><span data-stu-id="83a68-111">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="83a68-112">Um direkt zum Angriffssimulationstraining zu wechseln, öffnen Sie <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="83a68-112">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="83a68-113">Weitere Informationen zur Verfügbarkeit von Angriffssimulationsschulungen in verschiedenen Microsoft 365-Abonnements finden Sie unter [Microsoft Defender für Office 365 Dienstbeschreibung.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="83a68-113">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="83a68-114">Ihnen müssen Berechtigungen im Microsoft 365 Defender-Portal oder in Azure Active Directory zugewiesen werden, bevor Sie die Verfahren in diesem Artikel ausführen können.</span><span class="sxs-lookup"><span data-stu-id="83a68-114">You need to be assigned permissions in the Microsoft 365 Defender portal or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="83a68-115">Insbesondere müssen Sie Mitglied der **Organisationsverwaltung,** des **Sicherheitsadministrators** oder einer der folgenden Rollen sein:</span><span class="sxs-lookup"><span data-stu-id="83a68-115">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="83a68-116">Administratoren des **Angriffssimulators:** Erstellen und Verwalten aller Aspekte von Angriffssimulationskampagnen.</span><span class="sxs-lookup"><span data-stu-id="83a68-116">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="83a68-117">Autoren der **Angriffssimulatornutzlast:** Erstellen Sie Angriffsnutzlasten, die ein Administrator später initiieren kann.</span><span class="sxs-lookup"><span data-stu-id="83a68-117">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="83a68-118">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md) oder [über Administratorrollen.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="83a68-118">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="83a68-119">Es gibt keine entsprechenden PowerShell-Cmdlets für Angriffssimulationsschulungen.</span><span class="sxs-lookup"><span data-stu-id="83a68-119">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="83a68-120">Angriffssimulations- und Schulungsdaten werden mit anderen Kundendaten für Microsoft 365-Dienste gespeichert.</span><span class="sxs-lookup"><span data-stu-id="83a68-120">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="83a68-121">Weitere Informationen finden Sie unter [Microsoft 365 Datenspeicherorte.](../../enterprise/o365-data-locations.md)</span><span class="sxs-lookup"><span data-stu-id="83a68-121">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="83a68-122">Die Angriffssimulation ist in den folgenden Regionen verfügbar: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, KOR, BRA, DOPPELKLICK und CHE.</span><span class="sxs-lookup"><span data-stu-id="83a68-122">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, KOR, BRA, LAM and CHE.</span></span>

- <span data-ttu-id="83a68-123">Ab dem 15. Juni 2021 ist das Angriffssimulationstraining in GCC verfügbar.</span><span class="sxs-lookup"><span data-stu-id="83a68-123">As of June 15 2021, Attack simulation training is available in GCC.</span></span> <span data-ttu-id="83a68-124">Wenn Ihre Organisation über Office 365 G5-GCC oder Microsoft Defender für Office 365 (Plan 2) für Behörden verfügt, können Sie die Angriffssimulationsschulung im Microsoft 365 Defender Portal verwenden, um realistische Angriffsszenarien in Ihrer Organisation auszuführen, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="83a68-124">If your organization has Office 365 G5 GCC or Microsoft Defender for Office 365 (Plan 2) for Government, you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization as described in this article.</span></span> <span data-ttu-id="83a68-125">Angriffssimulationsschulungen sind in GCC High- oder DoD-Umgebungen noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="83a68-125">Attack simulation training is not yet available in GCC High or DoD environments.</span></span>

> [!NOTE]
> <span data-ttu-id="83a68-126">Die Angriffssimulationsschulung bietet E3-Kunden eine Teilmenge der Funktionen als Testversion.</span><span class="sxs-lookup"><span data-stu-id="83a68-126">Attack simulation training offers a subset of capabilities to E3 customers as a trial.</span></span> <span data-ttu-id="83a68-127">Das Testangebot enthält die Möglichkeit, eine Credential Harvest-Nutzlast zu verwenden, und die Möglichkeit, "ISA-Phishing" oder "Massenmarktphishing" auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="83a68-127">The trial offering contains the ability to use a Credential Harvest payload and the ability to select 'ISA Phishing' or 'Mass Market Phishing' training experiences.</span></span> <span data-ttu-id="83a68-128">Keine anderen Funktionen sind Teil des E3-Testangebots.</span><span class="sxs-lookup"><span data-stu-id="83a68-128">No other capabilities are part of the E3 trial offering.</span></span>

## <a name="simulations"></a><span data-ttu-id="83a68-129">Simulationen</span><span class="sxs-lookup"><span data-stu-id="83a68-129">Simulations</span></span>

<span data-ttu-id="83a68-130">*Phishing* ist ein allgemeiner Begriff für E-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern stammen.</span><span class="sxs-lookup"><span data-stu-id="83a68-130">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="83a68-131">*Phishing* ist Teil einer Teilmenge von Techniken, die wir als _Social Engineering_ klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="83a68-131">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="83a68-132">Im Angriffssimulationstraining stehen mehrere Arten von Social Engineering-Techniken zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="83a68-132">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="83a68-133">**Sammeln von Anmeldeinformationen:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="83a68-133">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="83a68-134">Wenn der Empfänger auf die URL klickt, wird er zu einer Website weitergeleitet, die in der Regel ein Dialogfeld anzeigt, in dem der Benutzer nach benutzername und kennwort gefragt wird.</span><span class="sxs-lookup"><span data-stu-id="83a68-134">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="83a68-135">In der Regel ist die Zielseite so angeordnet, dass sie eine bekannte Website darstellt, um dem Benutzer vertrauen zu können.</span><span class="sxs-lookup"><span data-stu-id="83a68-135">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="83a68-136">**Antischadsoftwareanlage:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine Anlage enthält.</span><span class="sxs-lookup"><span data-stu-id="83a68-136">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="83a68-137">Wenn der Empfänger die Anlage öffnet, wird beliebiger Code (z. B. ein Makro) auf dem Gerät des Benutzers ausgeführt, um dem Angreifer zu helfen, zusätzlichen Code zu installieren oder sich weiter zu verfangen.</span><span class="sxs-lookup"><span data-stu-id="83a68-137">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="83a68-138">**Link in Anlage:** Dies ist eine Hybridbereitstellung einer Anmeldeinformationsauswahl.</span><span class="sxs-lookup"><span data-stu-id="83a68-138">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="83a68-139">Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL innerhalb einer Anlage enthält.</span><span class="sxs-lookup"><span data-stu-id="83a68-139">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="83a68-140">Wenn der Empfänger die Anlage öffnet und auf die URL klickt, wird er zu einer Website geleitet, die in der Regel ein Dialogfeld anzeigt, in dem der Benutzer nach dem Benutzernamen und Kennwort gefragt wird.</span><span class="sxs-lookup"><span data-stu-id="83a68-140">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="83a68-141">In der Regel ist die Zielseite so angeordnet, dass sie eine bekannte Website darstellt, um dem Benutzer vertrauen zu können.</span><span class="sxs-lookup"><span data-stu-id="83a68-141">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="83a68-142">**Link zu Schadsoftware:** Ein Angreifer sendet dem Empfänger eine Nachricht mit einem Link zu einer Anlage auf einer bekannten Dateifreigabewebsite (z. B. SharePoint Online oder Dropbox).</span><span class="sxs-lookup"><span data-stu-id="83a68-142">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="83a68-143">Wenn der Empfänger auf die URL klickt, wird die Anlage geöffnet, und beliebiger Code (z. B. ein Makro) wird auf dem Gerät des Benutzers ausgeführt, um dem Angreifer zu helfen, zusätzlichen Code zu installieren oder sich weiter zu verfangen.</span><span class="sxs-lookup"><span data-stu-id="83a68-143">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="83a68-144">**Drive-by-URL:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="83a68-144">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="83a68-145">Wenn der Empfänger auf die URL klickt, wird er zu einer Website geleitet, die versucht, Hintergrundcode auszuführen.</span><span class="sxs-lookup"><span data-stu-id="83a68-145">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="83a68-146">Dieser Hintergrundcode versucht, Informationen über den Empfänger zu sammeln oder beliebigen Code auf dem Gerät bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="83a68-146">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="83a68-147">In der Regel ist die Zielwebsite eine bekannte Website, die kompromittiert wurde, oder ein Klon einer bekannten Website.</span><span class="sxs-lookup"><span data-stu-id="83a68-147">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="83a68-148">Wenn Sie mit der Website vertraut sind, können Sie den Benutzer davon überzeugen, dass der Link sicher angeklickt werden kann.</span><span class="sxs-lookup"><span data-stu-id="83a68-148">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="83a68-149">Diese Technik wird auch als _Wasserangriff bezeichnet._</span><span class="sxs-lookup"><span data-stu-id="83a68-149">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="83a68-150">Überprüfen Sie die Verfügbarkeit der simulierten Phishing-URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="83a68-150">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="83a68-151">Während wir mit vielen ANBIETERN für die URL-Zuverlässigkeit zusammenarbeiten, um diese Simulations-URLs immer zuzulassen, verfügen wir nicht immer über eine vollständige Abdeckung (z. B. Google Tresor Browsen).</span><span class="sxs-lookup"><span data-stu-id="83a68-151">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="83a68-152">Die meisten Anbieter bieten Anleitungen, mit denen Sie immer bestimmte URLs zulassen können (z. B. <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="83a68-152">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="83a68-153">Die von der Angriffssimulationsschulung verwendeten URLs werden in der folgenden Liste beschrieben:</span><span class="sxs-lookup"><span data-stu-id="83a68-153">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="83a68-154">Erstellen einer Simulation</span><span class="sxs-lookup"><span data-stu-id="83a68-154">Create a simulation</span></span>

<span data-ttu-id="83a68-155">Schrittweise Anleitungen zum Erstellen und Senden einer neuen Simulation finden Sie unter [Simulieren eines Phishingangriffs.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="83a68-155">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="83a68-156">Erstellen einer Nutzlast</span><span class="sxs-lookup"><span data-stu-id="83a68-156">Create a payload</span></span>

<span data-ttu-id="83a68-157">Schrittweise Anleitungen zum Erstellen einer Nutzlast für die Verwendung innerhalb einer Simulation finden Sie unter [Erstellen einer benutzerdefinierten Nutzlast für Angriffssimulationsschulungen.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="83a68-157">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="83a68-158">Gewinnen von Einblicken</span><span class="sxs-lookup"><span data-stu-id="83a68-158">Gaining insights</span></span>

<span data-ttu-id="83a68-159">Schritt-für-Schritt-Anleitungen zum Gewinnen von Erkenntnissen mit der Berichterstellung finden Sie unter ["Gewinnen von Einblicken durch Angriffssimulationsschulungen".](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="83a68-159">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="83a68-160">Der Angriffssimulator verwendet Tresor Links in Defender für Office 365, um Klickdaten für die URL in der Nutzlastnachricht, die an Zielempfänger einer Phishingkampagne gesendet wird, sicher nachzuverfolgen, auch wenn die Einstellung **"Benutzerklicks nicht nachverfolgen"** in Tresor Links-Richtlinien aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="83a68-160">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>
