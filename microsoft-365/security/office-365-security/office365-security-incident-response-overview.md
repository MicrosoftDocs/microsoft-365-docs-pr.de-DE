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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: In dieser Lösung erfahren Sie, wie die häufigsten Cyber-Angriffe in Microsoft 365 Aussehen und wie Sie darauf reagieren können.
ms.openlocfilehash: 4c5713a0689dae07fe5300c04754d77912f53976
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634508"
---
# <a name="security-incident-response"></a><span data-ttu-id="78e39-103">Reaktion auf Sicherheitsvorfälle</span><span class="sxs-lookup"><span data-stu-id="78e39-103">Security Incident Response</span></span>

 <span data-ttu-id="78e39-104">**Zusammenfassung:** In dieser Lösung erfahren Sie, welche Indikatoren für die häufigsten Cyber-Angriffe in Office 365 gelten, wie Sie einen bestimmten Angriff positiv bestätigen und wie Sie darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="78e39-104">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="overview"></a><span data-ttu-id="78e39-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="78e39-105">Overview</span></span>

<span data-ttu-id="78e39-106">Nicht alle Cyberangriffe können vereitelt werden.</span><span class="sxs-lookup"><span data-stu-id="78e39-106">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="78e39-107">Angreifer suchen ständig nach neuen Schwächen in ihrer Defensiv Strategie, oder Sie nutzen alte.</span><span class="sxs-lookup"><span data-stu-id="78e39-107">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="78e39-108">Wenn Sie wissen, wie ein Angriff erkannt werden kann, können Sie schneller darauf reagieren, wodurch die Dauer des Sicherheitsvorfalls verkürzt wird.</span><span class="sxs-lookup"><span data-stu-id="78e39-108">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="78e39-109">Diese Artikelreihe hilft Ihnen zu verstehen, welche Art von Angriff in Microsoft 365 möglicherweise aussieht, und gibt Ihnen die Schritte, die Sie ergreifen können, um zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="78e39-109">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="78e39-110">Sie sind schnelle Einstiegspunkte für das Verständnis:</span><span class="sxs-lookup"><span data-stu-id="78e39-110">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="78e39-111">Was der Angriff ist und wie er funktioniert.</span><span class="sxs-lookup"><span data-stu-id="78e39-111">What the attack is and how it works.</span></span>

- <span data-ttu-id="78e39-112">Welche Zeichen, die als Indikatoren für Kompromisse (IOC) bezeichnet werden, zu suchen und wie Sie gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="78e39-112">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="78e39-113">Wie der Angriff positiv bestätigt wird.</span><span class="sxs-lookup"><span data-stu-id="78e39-113">How to positively confirm the attack.</span></span>

- <span data-ttu-id="78e39-114">Schritte zum Abschneiden des Angriffs und zum besseren Schutz Ihrer Organisation in der Zukunft.</span><span class="sxs-lookup"><span data-stu-id="78e39-114">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="78e39-115">Enthält Links zu detaillierten Informationen zu den einzelnen Angriffstypen.</span><span class="sxs-lookup"><span data-stu-id="78e39-115">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="78e39-116">Überprüfen Sie hier monatlich, da weitere Artikel im Laufe der Zeit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="78e39-116">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="78e39-117">Erkennen und korrigieren von Artikeln</span><span class="sxs-lookup"><span data-stu-id="78e39-117">Detect and remediate articles</span></span>

- [<span data-ttu-id="78e39-118">Erkennen und Korrigieren von unerlaubter Zustimmung in Office 365</span><span class="sxs-lookup"><span data-stu-id="78e39-118">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="78e39-119">Erkennen und Korrigieren von Outlook-Regeln und benutzerdefinierten Formularen für Einschleusungsangriffe in Office 365</span><span class="sxs-lookup"><span data-stu-id="78e39-119">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="78e39-120">Vorfall Antwort Artikel</span><span class="sxs-lookup"><span data-stu-id="78e39-120">Incident response articles</span></span>

- [<span data-ttu-id="78e39-121">Reagieren auf ein angegriffenes E-Mail-Konto in Office 365</span><span class="sxs-lookup"><span data-stu-id="78e39-121">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="78e39-122">Sicherer Microsoft 365 wie ein Cyber pro</span><span class="sxs-lookup"><span data-stu-id="78e39-122">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="78e39-123">Ihr Microsoft 365-Abonnement verfügt über eine leistungsstarke Reihe von Sicherheitsfunktionen, die Sie zum Schutz Ihrer Daten und ihrer Benutzer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="78e39-123">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="78e39-124">Verwenden Sie die [Microsoft 365-Sicherheits-Roadmap – die wichtigsten Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](security-roadmap.md) , um die von Microsoft empfohlenen bewährten Methoden zum Sichern Ihrer Microsoft 365-Organisation zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="78e39-124">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="78e39-125">Aufgaben, die in den ersten 30 Tagen ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="78e39-125">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="78e39-126">Diese sind unmittelbar gültig und haben nur geringe Auswirkungen für die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="78e39-126">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="78e39-127">Aufgaben, die innerhalb von 90 Tagen ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="78e39-127">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="78e39-128">Diese benötigen ein wenig mehr Zeit, um ihre Sicherheitslage zu planen und zu implementieren, jedoch erheblich zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="78e39-128">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="78e39-129">Über 90 Tage hinaus.</span><span class="sxs-lookup"><span data-stu-id="78e39-129">Beyond 90 days.</span></span> <span data-ttu-id="78e39-130">Diese Verbesserungen werden in den ersten 90 Tagen Ihrer Arbeit umgesetzt.</span><span class="sxs-lookup"><span data-stu-id="78e39-130">These enhancements build in your first 90 days work.</span></span>
