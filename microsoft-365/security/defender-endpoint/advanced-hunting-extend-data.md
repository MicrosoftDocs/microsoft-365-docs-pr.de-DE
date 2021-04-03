---
title: Erweitern der erweiterten Abdeckung der Suche mit den richtigen Einstellungen
description: Überprüfen der Überwachungseinstellungen auf Windows-Geräten und anderen Einstellungen, um sicherzustellen, dass Sie bei der erweiterten Suche die umfassendsten Daten erhalten
keywords: Erweiterte Suche, Vorfall, Pivot, Entität, Überwachungseinstellungen, Benutzerkontenverwaltung, Verwaltung von Sicherheitsgruppen, Bedrohungssuche, Cyberbedrohungensuche, Suche, Abfrage, Telemetrie, Mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500616"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="4f4ea-104">Erweitern der erweiterten Abdeckung der Suche mit den richtigen Einstellungen</span><span class="sxs-lookup"><span data-stu-id="4f4ea-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4f4ea-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4f4ea-105">**Applies to:**</span></span>
- [<span data-ttu-id="4f4ea-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4f4ea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="4f4ea-107">[Die erweiterte Suche](advanced-hunting-overview.md) basiert auf Daten, die aus der gesamten Organisation kommen.</span><span class="sxs-lookup"><span data-stu-id="4f4ea-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="4f4ea-108">Stellen Sie sicher, dass sie über die richtigen Einstellungen in den entsprechenden Datenquellen verfügen, um möglichst umfassende Daten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4f4ea-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="4f4ea-109">Erweiterte Sicherheitsüberwachung auf Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="4f4ea-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="4f4ea-110">Aktivieren Sie diese erweiterten Überwachungseinstellungen, um sicherzustellen, dass Sie Daten zu Aktivitäten auf Ihren Geräten erhalten, z. B. lokale Kontoverwaltung, lokale Sicherheitsgruppenverwaltung und Diensterstellung.</span><span class="sxs-lookup"><span data-stu-id="4f4ea-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="4f4ea-111">Daten</span><span class="sxs-lookup"><span data-stu-id="4f4ea-111">Data</span></span> | <span data-ttu-id="4f4ea-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f4ea-112">Description</span></span> | <span data-ttu-id="4f4ea-113">Schematabelle</span><span class="sxs-lookup"><span data-stu-id="4f4ea-113">Schema table</span></span> | <span data-ttu-id="4f4ea-114">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4f4ea-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="4f4ea-115">Kontoverwaltung</span><span class="sxs-lookup"><span data-stu-id="4f4ea-115">Account management</span></span> | <span data-ttu-id="4f4ea-116">Ereignisse, die als verschiedene Werte `ActionType` erfasst werden, die lokale Kontoerstellung, Löschung und andere kontobezogene Aktivitäten angeben</span><span class="sxs-lookup"><span data-stu-id="4f4ea-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="4f4ea-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="4f4ea-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="4f4ea-118">– Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Benutzerkontenverwaltung überwachen](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="4f4ea-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="4f4ea-119">- [Erfahren Sie mehr über erweiterte Sicherheits-Überwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="4f4ea-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="4f4ea-120">Verwaltung von Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="4f4ea-120">Security group management</span></span> | <span data-ttu-id="4f4ea-121">Ereignisse, die als verschiedene Werte erfasst `ActionType` werden, die die Erstellung lokaler Sicherheitsgruppen und andere lokale Gruppenverwaltungsaktivitäten angeben</span><span class="sxs-lookup"><span data-stu-id="4f4ea-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="4f4ea-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="4f4ea-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="4f4ea-123">– Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Überwachung der Sicherheitsgruppenverwaltung](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="4f4ea-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="4f4ea-124">- [Erfahren Sie mehr über erweiterte Sicherheits-Überwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="4f4ea-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="4f4ea-125">Dienstinstallation</span><span class="sxs-lookup"><span data-stu-id="4f4ea-125">Service installation</span></span> | <span data-ttu-id="4f4ea-126">Ereignisse, die mit dem Wert `ActionType` erfasst `ServiceInstalled` werden und angeben, dass ein Dienst erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="4f4ea-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="4f4ea-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="4f4ea-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="4f4ea-128">– Bereitstellen einer erweiterten Sicherheits-Überwachungsrichtlinie: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="4f4ea-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="4f4ea-129">- [Erfahren Sie mehr über erweiterte Sicherheits-Überwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="4f4ea-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="4f4ea-130">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4f4ea-130">Related topics</span></span>

- [<span data-ttu-id="4f4ea-131">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="4f4ea-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4f4ea-132">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="4f4ea-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4f4ea-133">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="4f4ea-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="4f4ea-134">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="4f4ea-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="4f4ea-135">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="4f4ea-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="4f4ea-136">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="4f4ea-136">Custom detections overview</span></span>](overview-custom-detections.md)
