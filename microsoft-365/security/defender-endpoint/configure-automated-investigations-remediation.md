---
title: Konfigurieren automatisierter Untersuchungs- und Korrekturfunktionen
description: Richten Sie Ihre automatisierten Untersuchungs- und Korrekturfunktionen in Microsoft Defender for Endpoint ein.
keywords: konfigurieren, einrichten, automatisieren, Untersuchung, Erkennung, Warnungen, Korrektur, Antwort
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 23d6c8c87a6cbcc7b8060440ba2c0cae6182767d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274544"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="68d07-104">Konfigurieren automatisierter Untersuchungs- und Korrekturfunktionen in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="68d07-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68d07-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="68d07-105">**Applies to:**</span></span>
- [<span data-ttu-id="68d07-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="68d07-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="68d07-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68d07-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="68d07-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="68d07-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="68d07-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="68d07-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="68d07-110">Wenn Ihre Organisation Microsoft Defender for Endpoint (Defender for [Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/) [verwendet,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) können automatisierte Untersuchungs- und Korrekturfunktionen Ihrem Sicherheitsteam Zeit und Aufwand sparen.</span><span class="sxs-lookup"><span data-stu-id="68d07-110">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="68d07-111">Wie in [diesem Blogbeitrag beschrieben,](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)sind diese Funktionen die idealen Schritte, die ein Sicherheitsanalyst zur Untersuchung und Behebung von Bedrohungen unternimmt.</span><span class="sxs-lookup"><span data-stu-id="68d07-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="68d07-112">[Erfahren Sie mehr über automatisierte Untersuchung und Behebung](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations).</span><span class="sxs-lookup"><span data-stu-id="68d07-112">[Learn more about automated investigation and remediation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="68d07-113">Zum Konfigurieren der automatisierten Untersuchung und Behebung</span><span class="sxs-lookup"><span data-stu-id="68d07-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="68d07-114">[Aktivieren Sie die Features](#turn-on-automated-investigation-and-remediation); und</span><span class="sxs-lookup"><span data-stu-id="68d07-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="68d07-115">[Einrichten von Gerätegruppen](#set-up-device-groups).</span><span class="sxs-lookup"><span data-stu-id="68d07-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="68d07-116">Aktivieren der automatisierten Untersuchung und Korrektur</span><span class="sxs-lookup"><span data-stu-id="68d07-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="68d07-117">Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zum Microsoft Defender Security Center ( ) und [https://securitycenter.windows.com](https://securitycenter.windows.com) melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="68d07-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="68d07-118">Wählen Sie im Navigationsbereich Einstellungen **aus.**</span><span class="sxs-lookup"><span data-stu-id="68d07-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="68d07-119">Wählen Sie **im Abschnitt Allgemein** die Option Erweiterte Features **aus.**</span><span class="sxs-lookup"><span data-stu-id="68d07-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="68d07-120">Aktivieren Sie sowohl **die automatische Untersuchung als** auch die automatische Behebung von **Warnungen.**</span><span class="sxs-lookup"><span data-stu-id="68d07-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="68d07-121">Gerätegruppen einrichten</span><span class="sxs-lookup"><span data-stu-id="68d07-121">Set up device groups</span></span>

1. <span data-ttu-id="68d07-122">Wählen Sie im Microsoft Defender Security Center ( ) auf der Seite [https://securitycenter.windows.com](https://securitycenter.windows.com) **Einstellungen** unter **Berechtigungen** **Gerätegruppen aus.**</span><span class="sxs-lookup"><span data-stu-id="68d07-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="68d07-123">Wählen **Sie + Gerätegruppe hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="68d07-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="68d07-124">Erstellen Sie mindestens eine Gerätegruppe wie folgt:</span><span class="sxs-lookup"><span data-stu-id="68d07-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="68d07-125">Geben Sie einen Namen und eine Beschreibung für die Gerätegruppe an.</span><span class="sxs-lookup"><span data-stu-id="68d07-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="68d07-126">Wählen Sie **in der Liste** Automatisierungsebene eine Ebene aus, z. B. Vollständig – Bedrohungen automatisch **entfernen.**</span><span class="sxs-lookup"><span data-stu-id="68d07-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="68d07-127">Die Automatisierungsebene bestimmt, ob Korrekturaktionen automatisch oder nur nach Genehmigung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="68d07-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="68d07-128">Weitere Informationen finden Sie unter [Automatisierungsebenen in automatisierter Untersuchung und Korrektur](automation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="68d07-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="68d07-129">Verwenden Sie **im Abschnitt** Mitglieder eine oder mehrere Bedingungen zum Identifizieren und Schließen von Geräten.</span><span class="sxs-lookup"><span data-stu-id="68d07-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="68d07-130">Wählen Sie **auf der Registerkarte** Benutzerzugriff die Azure Active [Directory-Gruppen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) aus, die Zugriff auf die zu erstellende Gerätegruppe haben sollen.</span><span class="sxs-lookup"><span data-stu-id="68d07-130">On the **User access** tab, select the [Azure Active Directory groups](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="68d07-131">Wählen **Sie Fertig** aus, wenn Sie die Einrichtung Ihrer Gerätegruppe abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="68d07-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68d07-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="68d07-132">Next steps</span></span>

- [<span data-ttu-id="68d07-133">Besuchen Sie das Aktionscenter, um ausstehende und abgeschlossene Korrekturaktionen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="68d07-133">Visit the Action Center to view pending and completed remediation actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="68d07-134">Überprüfen und Genehmigen ausstehender Aktionen</span><span class="sxs-lookup"><span data-stu-id="68d07-134">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="68d07-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68d07-135">See also</span></span>

- [<span data-ttu-id="68d07-136">Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="68d07-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
