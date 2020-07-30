---
title: Erweiterte Jagd Abdeckung mit den richtigen Einstellungen erweitern
description: Überprüfen Sie die Überwachungseinstellungen auf Windows-Geräten und anderen Einstellungen, um sicherzustellen, dass Sie die umfassendsten Daten in Advanced Hunting abrufen können.
keywords: Erweiterte Jagd, Vorfall, Pivot, Entität, Überwachungseinstellungen, Benutzerkontenverwaltung, Sicherheitsgruppenverwaltung, Bedrohungs Suche, Cyber Threat Hunting, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 9c1b9c1853d80d818d97084e2668d3b12b6da0e6
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503216"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="81f62-104">Erweiterte Jagd Abdeckung mit den richtigen Einstellungen erweitern</span><span class="sxs-lookup"><span data-stu-id="81f62-104">Extend advanced hunting coverage with the right settings</span></span>

<span data-ttu-id="81f62-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="81f62-105">**Applies to:**</span></span>
- <span data-ttu-id="81f62-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="81f62-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="81f62-107">Die [Erweiterte Suche](advanced-hunting-overview.md) basiert auf Daten, die aus verschiedenen Quellen stammen, einschließlich Ihrer Geräte, Ihrer Office 365 Arbeitsbereiche, Azure AD und Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="81f62-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from various sources, including your devices, your Office 365 workspaces, Azure AD, and Azure ATP.</span></span> <span data-ttu-id="81f62-108">Um die umfassendsten Daten zu erhalten, stellen Sie sicher, dass Sie über die richtigen Einstellungen in den entsprechenden Datenquellen verfügen.</span><span class="sxs-lookup"><span data-stu-id="81f62-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="81f62-109">Erweiterte Sicherheitsüberwachung auf Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="81f62-109">Advanced security auditing on Windows devices</span></span>
<span data-ttu-id="81f62-110">Aktivieren Sie diese erweiterten Überwachungseinstellungen, um sicherzustellen, dass Sie Daten zu Aktivitäten auf Ihren Geräten abrufen, einschließlich der lokalen Kontoverwaltung, der Verwaltung lokaler Sicherheitsgruppen und der Erstellung von Diensten.</span><span class="sxs-lookup"><span data-stu-id="81f62-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

| <span data-ttu-id="81f62-111">Daten</span><span class="sxs-lookup"><span data-stu-id="81f62-111">Data</span></span> | <span data-ttu-id="81f62-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81f62-112">Description</span></span> | <span data-ttu-id="81f62-113">Schema Tabelle</span><span class="sxs-lookup"><span data-stu-id="81f62-113">Schema table</span></span> | <span data-ttu-id="81f62-114">Konfigurieren von</span><span class="sxs-lookup"><span data-stu-id="81f62-114">How to configure</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="81f62-115">Kontoverwaltung</span><span class="sxs-lookup"><span data-stu-id="81f62-115">Account management</span></span> | <span data-ttu-id="81f62-116">Als verschiedene Werte erfasste Ereignisse, die das `ActionType` erstellen, löschen und andere kontobezogene Aktivitäten des lokalen Kontos anzeigen</span><span class="sxs-lookup"><span data-stu-id="81f62-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="81f62-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="81f62-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="81f62-118">– Bereitstelleneiner erweiterten Sicherheitsüberwachungsrichtlinie: über [Wachen der Benutzerkontenverwaltung](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="81f62-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="81f62-119">- [Informationen zu erweiterten Sicherheitsüberwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="81f62-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |
| <span data-ttu-id="81f62-120">Sicherheitsgruppenverwaltung</span><span class="sxs-lookup"><span data-stu-id="81f62-120">Security group management</span></span> | <span data-ttu-id="81f62-121">Als verschiedene Werte erfasste Ereignisse, die die `ActionType` Erstellung lokaler Sicherheitsgruppen und andere Aktivitäten der lokalen Gruppenverwaltung anzeigen</span><span class="sxs-lookup"><span data-stu-id="81f62-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="81f62-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="81f62-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="81f62-123">– Bereitstelleneiner erweiterten Sicherheitsüberwachungsrichtlinie: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="81f62-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="81f62-124">- [Informationen zu erweiterten Sicherheitsüberwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="81f62-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |
| <span data-ttu-id="81f62-125">Dienstinstallation</span><span class="sxs-lookup"><span data-stu-id="81f62-125">Service installation</span></span> | <span data-ttu-id="81f62-126">Mit dem Wert erfasste Ereignisse `ActionType` `ServiceInstalled` , die angeben, dass ein Dienst erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="81f62-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="81f62-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="81f62-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="81f62-128">-Bereitstelleneiner erweiterten Sicherheitsüberwachungsrichtlinie: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="81f62-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="81f62-129">- [Informationen zu erweiterten Sicherheitsüberwachungsrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="81f62-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |

## <a name="azure-atp-sensor-on-the-domain-controller"></a><span data-ttu-id="81f62-130">Azure ATP-Sensor auf dem Domänencontroller</span><span class="sxs-lookup"><span data-stu-id="81f62-130">Azure ATP sensor on the domain controller</span></span>
<span data-ttu-id="81f62-131">Wenn Sie Active Directory lokal betreiben, müssen Sie den Azure ATP-Sensor auf dem Domänencontroller installieren, um Daten für Azure ATP zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="81f62-131">If you're running Active Directory on premises, you need to install the Azure ATP sensor on the domain controller to get data for Azure ATP.</span></span> <span data-ttu-id="81f62-132">Bei der Installation und ordnungsgemäßen Konfiguration werden diese Daten auch in die erweiterte Suche durch Azure ATP übermittelt und bieten ein ganzheitlicheres Bild von Identitätsinformationen und Ereignissen in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="81f62-132">When installed and properly configured, this data also feeds into advanced hunting through Azure ATP and provides a more holistic picture of identity information and events in your network.</span></span> <span data-ttu-id="81f62-133">Mit diesen Daten wird auch die Fähigkeit von Azure ATP erhöht, relevante Warnungen zu generieren, die auch von Advanced Hunting abgedeckt werden.</span><span class="sxs-lookup"><span data-stu-id="81f62-133">This data also enhances the ability of Azure ATP to generate relevant alerts that are also covered by advanced hunting.</span></span> 

| <span data-ttu-id="81f62-134">Daten</span><span class="sxs-lookup"><span data-stu-id="81f62-134">Data</span></span> | <span data-ttu-id="81f62-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81f62-135">Description</span></span> | <span data-ttu-id="81f62-136">Schema Tabelle</span><span class="sxs-lookup"><span data-stu-id="81f62-136">Schema table</span></span> | <span data-ttu-id="81f62-137">Konfigurieren von</span><span class="sxs-lookup"><span data-stu-id="81f62-137">How to configure</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="81f62-138">Domänencontroller</span><span class="sxs-lookup"><span data-stu-id="81f62-138">Domain controller</span></span> | <span data-ttu-id="81f62-139">Daten aus lokalen Active Directory an Azure ATP gesendet, sodass identitätsbezogene Informationen wie Kontodetails, Anmeldeaktivitäten und Active Directory Abfragen erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="81f62-139">Data from on-premises Active Directory sent to Azure ATP, enriching identity-related information, such as account details, logon activity, and Active Directory queries</span></span> | <span data-ttu-id="81f62-140">Mehrere Tabellen, einschließlich [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)und [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="81f62-140">Multiple tables, including [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), and [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)</span></span>  | [<span data-ttu-id="81f62-141">Installieren des Azure ATP-Sensors</span><span class="sxs-lookup"><span data-stu-id="81f62-141">Install the Azure ATP sensor</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)|

## <a name="related-topics"></a><span data-ttu-id="81f62-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="81f62-142">Related topics</span></span>
- [<span data-ttu-id="81f62-143">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="81f62-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="81f62-144">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="81f62-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)