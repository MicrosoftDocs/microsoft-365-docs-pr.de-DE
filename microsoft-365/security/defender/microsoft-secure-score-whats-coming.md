---
title: Neuerungen in der Microsoft-Sicherheitsbewertung
description: Beschreibt, welche neuen Änderungen an der Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center vorgenommen werden.
keywords: Microsoft-Sicherheitsbewertung, Sicherheitsbewertung, Office 365-Sicherheitsbewertung, Microsoft-Sicherheitsbewertung, Microsoft 365 Security Center, Verbesserungsmaßnahmen
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 910eb16ad33555ca61875a346b50cea7e63b2220
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338553"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="e8b3e-104">Neuerungen in der Microsoft-Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="e8b3e-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e8b3e-105">Die Microsoft-Sicherheitsbewertung finden Sie https://security.microsoft.com/securescore im [Microsoft 365 Security Center.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="e8b3e-105">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="e8b3e-106">Vorgeschlagene Änderungen</span><span class="sxs-lookup"><span data-stu-id="e8b3e-106">Proposed changes</span></span>

<span data-ttu-id="e8b3e-107">Wir nehmen in naher Zukunft einige Änderungen vor, um [die Microsoft-Sicherheitsbewertung](microsoft-secure-score.md) zu einem besseren Vertreter Ihres Sicherheitsstatus zu machen und die Benutzerfreundlichkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-107">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="e8b3e-108">Ihre Bewertung und die maximal mögliche Bewertung können sich ändern.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-108">Your score and the maximum possible score may change.</span></span>

### <a name="july-2021"></a><span data-ttu-id="e8b3e-109">Juli 2021</span><span class="sxs-lookup"><span data-stu-id="e8b3e-109">July 2021</span></span>

#### <a name="add-improvement-action-related-to-microsoft-teams"></a><span data-ttu-id="e8b3e-110">Hinzufügen von Verbesserungsmaßnahmen im Zusammenhang mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e8b3e-110">Add improvement action related to Microsoft Teams</span></span>

- <span data-ttu-id="e8b3e-111">Einwahlbenutzer am Umgehen eines Besprechungslobbys hindern.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-111">Restrict dial-in users from bypassing a meeting lobby.</span></span>
- <span data-ttu-id="e8b3e-112">Einschränken der Kontrolle externer Teilnehmer in einer Teams Besprechung.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-112">Limit external participants from having control in a Teams meeting.</span></span>
- <span data-ttu-id="e8b3e-113">Einschränken, dass anonyme Benutzer Teams Besprechungen starten.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-113">Restrict anonymous users from starting Teams meetings.</span></span>
- <span data-ttu-id="e8b3e-114">Lobbies müssen für Teams Besprechungen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-114">Require lobbies to be set up for Teams meetings.</span></span>
- <span data-ttu-id="e8b3e-115">Konfigurieren Sie, welche Benutzer in Teams Besprechungen teilnehmen dürfen.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-115">Configure which users are allowed to be present in Teams meetings.</span></span>

#### <a name="add-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="e8b3e-116">Hinzufügen von Verbesserungsmaßnahmen im Zusammenhang mit Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e8b3e-116">Add improvement action related to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="e8b3e-117">Korrigieren der Microsoft Defender für Endpunkt-Sensordatensammlung für macOS</span><span class="sxs-lookup"><span data-stu-id="e8b3e-117">Fix Microsoft Defender for Endpoint sensor data collection for macOS</span></span>
- <span data-ttu-id="e8b3e-118">Beheben der beeinträchtigten Kommunikation von Microsoft Defender für Endpunkt für macOS</span><span class="sxs-lookup"><span data-stu-id="e8b3e-118">Fix Microsoft Defender for Endpoint impaired communications for macOS</span></span>
- <span data-ttu-id="e8b3e-119">Festlegen der mindesten Kennwortlänge auf 15 oder mehr Zeichen in macOS</span><span class="sxs-lookup"><span data-stu-id="e8b3e-119">Set minimum password length to 15 or more characters in macOS</span></span>
- <span data-ttu-id="e8b3e-120">Festlegen von "Kennwortverlauf erzwingen" auf "24 oder mehr Kennwörter" in macOS</span><span class="sxs-lookup"><span data-stu-id="e8b3e-120">Set 'Enforce password history' to '24 or more password(s)' in macOS</span></span>
- <span data-ttu-id="e8b3e-121">Legen Sie "Maximales Kennwortalter" in macOS auf "90 oder weniger Tage, aber nicht 0" fest.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-121">Set 'Maximum password age' to '90 or fewer days, but not 0' in macOS</span></span>
- <span data-ttu-id="e8b3e-122">Festlegen des Kontosperrschwellenwerts auf 5 oder niedriger in macOS</span><span class="sxs-lookup"><span data-stu-id="e8b3e-122">Set account lockout threshold to 5 or lower in macOS</span></span>
- <span data-ttu-id="e8b3e-123">Aktivieren der Firewall unter macOS</span><span class="sxs-lookup"><span data-stu-id="e8b3e-123">Turn on Firewall on macOS</span></span>
- <span data-ttu-id="e8b3e-124">Aktivieren von "Gate keep"</span><span class="sxs-lookup"><span data-stu-id="e8b3e-124">Enable Gatekeeper</span></span>
- <span data-ttu-id="e8b3e-125">Aktivieren von Systemintegritätsschutz (SIP)</span><span class="sxs-lookup"><span data-stu-id="e8b3e-125">Enable System Integrity Protection (SIP)</span></span>
- <span data-ttu-id="e8b3e-126">Aktivieren der FileVault-Datenträgerverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e8b3e-126">Enable FileVault Disk Encryption</span></span>
- <span data-ttu-id="e8b3e-127">Festlegen, dass der Bildschirm gesperrt wird, wenn Bildschirmschoner in macOS gestartet wird</span><span class="sxs-lookup"><span data-stu-id="e8b3e-127">Set screen to lock when screensaver starts in macOS</span></span>
- <span data-ttu-id="e8b3e-128">Stellen Sie sicher, dass bildschirmschoner so eingestellt ist, dass er in 20 Minuten oder weniger in macOS gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-128">Ensure screensaver is set to start in 20 minutes or less in macOS</span></span>
- <span data-ttu-id="e8b3e-129">Sichere Startordner</span><span class="sxs-lookup"><span data-stu-id="e8b3e-129">Secure Home Folders</span></span>
- <span data-ttu-id="e8b3e-130">Aktivieren Microsoft Defender Antivirus Echtzeitschutz für macOS</span><span class="sxs-lookup"><span data-stu-id="e8b3e-130">Turn on Microsoft Defender Antivirus real-time protection for macOS</span></span>
- <span data-ttu-id="e8b3e-131">Aktivieren Microsoft Defender Antivirus PUA-Schutzes im Blockierungsmodus für macOS</span><span class="sxs-lookup"><span data-stu-id="e8b3e-131">Turn on Microsoft Defender Antivirus PUA protection in block mode for macOS</span></span>
- <span data-ttu-id="e8b3e-132">Aktivieren Microsoft Defender Antivirus über die Cloud bereitgestellten Schutzes für macOS</span><span class="sxs-lookup"><span data-stu-id="e8b3e-132">Enable Microsoft Defender Antivirus cloud-delivered protection for macOS</span></span>
- <span data-ttu-id="e8b3e-133">Aktualisieren Microsoft Defender Antivirus Definitionen für macOS</span><span class="sxs-lookup"><span data-stu-id="e8b3e-133">Update Microsoft Defender Antivirus definitions for macOS</span></span>
- <span data-ttu-id="e8b3e-134">Korrigieren der Microsoft Defender für Endpunkt-Sensordatensammlung für Linux</span><span class="sxs-lookup"><span data-stu-id="e8b3e-134">Fix Microsoft Defender for Endpoint sensor data collection for Linux</span></span>
- <span data-ttu-id="e8b3e-135">Beheben der beeinträchtigten Kommunikation von Microsoft Defender für Endpunkt für Linux</span><span class="sxs-lookup"><span data-stu-id="e8b3e-135">Fix Microsoft Defender for Endpoint impaired communications for Linux</span></span>
- <span data-ttu-id="e8b3e-136">Konten für uneingeschränkten Zugriff</span><span class="sxs-lookup"><span data-stu-id="e8b3e-136">Unrestricted Access Accounts</span></span>
- <span data-ttu-id="e8b3e-137">Aktivieren Microsoft Defender Antivirus Echtzeitschutz für Linux</span><span class="sxs-lookup"><span data-stu-id="e8b3e-137">Turn on Microsoft Defender Antivirus real-time protection for Linux</span></span>
- <span data-ttu-id="e8b3e-138">Aktivieren Microsoft Defender Antivirus PUA-Schutzes im Blockierungsmodus für Linux</span><span class="sxs-lookup"><span data-stu-id="e8b3e-138">Turn on Microsoft Defender Antivirus PUA protection in block mode for Linux</span></span>
- <span data-ttu-id="e8b3e-139">Aktivieren Microsoft Defender Antivirus über die Cloud bereitgestellten Schutzes für Linux</span><span class="sxs-lookup"><span data-stu-id="e8b3e-139">Enable Microsoft Defender Antivirus cloud-delivered protection for Linux</span></span>
- <span data-ttu-id="e8b3e-140">Aktualisieren Microsoft Defender Antivirus Definitionen für Linux</span><span class="sxs-lookup"><span data-stu-id="e8b3e-140">Update Microsoft Defender Antivirus definitions for Linux</span></span>



## <a name="related-resources"></a><span data-ttu-id="e8b3e-141">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e8b3e-141">Related resources</span></span>

- [<span data-ttu-id="e8b3e-142">Übersicht über die Microsoft-Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="e8b3e-142">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="e8b3e-143">Zugreifen auf Ihren Sicherheitsstatus</span><span class="sxs-lookup"><span data-stu-id="e8b3e-143">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="e8b3e-144">Nachverfolgen des Microsoft-Verlaufs der Sicherheitsbewertung und Erreichen der Ziele</span><span class="sxs-lookup"><span data-stu-id="e8b3e-144">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="e8b3e-145">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="e8b3e-145">What's new</span></span>](microsoft-secure-score-whats-new.md)
