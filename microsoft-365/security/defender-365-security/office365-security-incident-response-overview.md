---
title: Reaktion auf Sicherheitsvorfälle
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Mit dieser Lösung erfahren Sie, wie die häufigsten Cybersicherheitsangriffe in Microsoft 365 aussehen können und wie Sie darauf reagieren.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65ff75253f45ae2d0f051dafe73c6e665f89827a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065192"
---
# <a name="security-incident-response"></a><span data-ttu-id="251ce-103">Reaktion auf Sicherheitsvorfälle</span><span class="sxs-lookup"><span data-stu-id="251ce-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="251ce-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="251ce-104">**Applies to**</span></span>
- [<span data-ttu-id="251ce-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="251ce-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="251ce-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="251ce-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="251ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="251ce-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="251ce-108">**Zusammenfassung:** Mit dieser Lösung erfahren Sie, was die Indikatoren für die häufigsten Cybersicherheitsangriffe in Office 365 sind, wie Sie einen bestimmten Angriff positiv bestätigen und wie Sie darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="251ce-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="251ce-109">Erfahren Sie, wie Sie auf Cyberangriffe reagieren</span><span class="sxs-lookup"><span data-stu-id="251ce-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="251ce-110">Nicht alle Cyberangriffe können vereitelt werden.</span><span class="sxs-lookup"><span data-stu-id="251ce-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="251ce-111">Angreifer suchen ständig nach neuen Schwächen in Ihrer Defensivstrategie, oder sie nutzen alte.</span><span class="sxs-lookup"><span data-stu-id="251ce-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="251ce-112">Wenn Sie wissen, wie Sie einen Angriff erkennen, können Sie schneller darauf reagieren, was die Dauer des Sicherheitsvorfalls verkürzt.</span><span class="sxs-lookup"><span data-stu-id="251ce-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="251ce-113">Diese Artikelreihe hilft Ihnen, zu verstehen, wie ein bestimmter Angriffstyp in Microsoft 365 aussehen könnte, und enthält Schritte, die Sie ergreifen können, um zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="251ce-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="251ce-114">Dies sind kurze Einstiegspunkte zum Verständnis:</span><span class="sxs-lookup"><span data-stu-id="251ce-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="251ce-115">Was der Angriff ist und wie er funktioniert.</span><span class="sxs-lookup"><span data-stu-id="251ce-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="251ce-116">Welche Zeichen, sogenannte Kompromissindikatoren (IOC), zu suchen sind und wie sie zu suchen sind.</span><span class="sxs-lookup"><span data-stu-id="251ce-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="251ce-117">So bestätigen Sie den Angriff positiv.</span><span class="sxs-lookup"><span data-stu-id="251ce-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="251ce-118">Schritte zum Abschneiden des Angriffs und zum besseren Schutz Ihrer Organisation in der Zukunft.</span><span class="sxs-lookup"><span data-stu-id="251ce-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="251ce-119">Links zu detaillierten Informationen zu jedem Angriffstyp.</span><span class="sxs-lookup"><span data-stu-id="251ce-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="251ce-120">Überprüfen Sie hier monatlich, wie weitere Artikel im Laufe der Zeit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="251ce-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="251ce-121">Erkennen und Besen von Artikeln</span><span class="sxs-lookup"><span data-stu-id="251ce-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="251ce-122">Erkennen und Korrigieren von unerlaubter Zustimmung in Office 365</span><span class="sxs-lookup"><span data-stu-id="251ce-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="251ce-123">Erkennen und Korrigieren von Outlook-Regeln und benutzerdefinierten Formularen für Einschleusungsangriffe in Office 365</span><span class="sxs-lookup"><span data-stu-id="251ce-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="251ce-124">Artikel zur Reaktion auf Vorfälle</span><span class="sxs-lookup"><span data-stu-id="251ce-124">Incident response articles</span></span>

- [<span data-ttu-id="251ce-125">Reagieren auf ein angegriffenes E-Mail-Konto in Office 365</span><span class="sxs-lookup"><span data-stu-id="251ce-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="251ce-126">Sichern von Microsoft 365 wie ein Profi für Internetsicherheit</span><span class="sxs-lookup"><span data-stu-id="251ce-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="251ce-127">Ihr Microsoft 365-Abonnement bietet eine Reihe von leistungsfähigen Funktionen für Sicherheit, die Sie zum Schutz Ihrer Daten und Ihrer Benutzer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="251ce-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="251ce-128">Verwenden Sie die Microsoft 365 Security Roadmap – Die wichtigsten Prioritäten für die ersten [30 Tage, 90](security-roadmap.md) Tage und darüber hinaus, um von Microsoft empfohlene bewährte Methoden zum Schützen Ihrer Microsoft 365-Organisation zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="251ce-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="251ce-129">Aufgaben, die in den ersten 30 Tagen ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="251ce-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="251ce-130">Diese sind unmittelbar gültig und haben nur geringe Auswirkungen für die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="251ce-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="251ce-131">Aufgaben, die innerhalb von 90 Tagen ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="251ce-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="251ce-132">Diese nehmen etwas mehr Zeit in Die Planung und Implementierung, verbessern aber ihre Sicherheitslage erheblich.</span><span class="sxs-lookup"><span data-stu-id="251ce-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="251ce-133">Über 90 Tage hinaus.</span><span class="sxs-lookup"><span data-stu-id="251ce-133">Beyond 90 days.</span></span> <span data-ttu-id="251ce-134">Diese Verbesserungen werden in den ersten 90 Tagen Ihrer Arbeit umgesetzt.</span><span class="sxs-lookup"><span data-stu-id="251ce-134">These enhancements build in your first 90 days work.</span></span>
