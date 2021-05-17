---
title: Informationen zu Windows-Sicherheitsupdates
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941441"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="a8b0a-103">Informationen zu Windows-Sicherheitsupdates</span><span class="sxs-lookup"><span data-stu-id="a8b0a-103">Windows security update insights</span></span>
<span data-ttu-id="a8b0a-104">Diese Ansicht bietet eine Übersicht über den Status von Sicherheitsupdates für Ihre Microsoft Managed Desktop Geräte.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="a8b0a-105">Wählen Sie zum Anzeigen von Verwendungsdaten die <strong>Registerkarte Windows Sicherheitsupdates</strong> aus.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows Bereich Sicherheitsupdates: Balkendiagramme des Gerätestatus und der Updateversion in der linken Spalte, Aktualisierung des Bereitstellungsfortschritts im Laufe der Zeit in der Mitte und Prozentsatz der aktiven Geräte nach Bereitstellungsgruppe sowie die Anzahl der Tage, die zum Erreichen des Bereitstellungsziels von 95 % in der rechten Spalte verwendet wurden.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="a8b0a-107">Gerätestatus</span><span class="sxs-lookup"><span data-stu-id="a8b0a-107">Device status</span></span>

<span data-ttu-id="a8b0a-108">Damit Geräte mit Windows Update aktualisiert werden können, müssen sie mit dem Internet verbunden sein und nicht mindestens sechs Stunden lang im Ruhezustand sein, von denen zwei kontinuierlich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="a8b0a-109">Obwohl es möglich ist, dass ein Gerät aktualisiert wird, das diese Anforderungen nicht erfüllt, haben Geräte, die diese Anforderungen erfüllen, die höchste Wahrscheinlichkeit, aktualisiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="a8b0a-110">Wir kategorisieren Geräteaktivitäten im Kontext Windows Update mit den folgenden Begriffen:</span><span class="sxs-lookup"><span data-stu-id="a8b0a-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="a8b0a-111"><strong>Aktiv:</strong> Geräte, die die Mindestaktivitätskriterien (sechs Stunden, zwei fortlaufende) für die neueste Sicherheitsupdateversion erfüllt haben und mindestens alle fünf Tage mit Microsoft Intune eingecheckt haben</span><span class="sxs-lookup"><span data-stu-id="a8b0a-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="a8b0a-112"><strong>Synchronisiert:</strong> Geräte, die in den letzten 28 Tagen mit Intune eingecheckt haben</span><span class="sxs-lookup"><span data-stu-id="a8b0a-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="a8b0a-113"><strong>Nicht synchronisiert:</strong> Geräte, die <i>in den</i> letzten 28 Tagen nicht mit Intune eingecheckt haben</span><span class="sxs-lookup"><span data-stu-id="a8b0a-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="a8b0a-114">Versionsstatus aktualisieren</span><span class="sxs-lookup"><span data-stu-id="a8b0a-114">Update version status</span></span>

<span data-ttu-id="a8b0a-115">Microsoft veröffentlicht Sicherheitsupdates jeden zweiten Dienstag im Monat.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="a8b0a-116">Jede Version fügt wichtige Updates für bekannte Sicherheitsrisiken hinzu.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="a8b0a-117">Microsoft Managed Desktop stellt sicher, dass 95 % der verwalteten Geräte jeden Monat mit dem neuesten verfügbaren Sicherheitsupdate aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="a8b0a-118">Sicherheitsupdates werden manchmal zu anderen Zeiten veröffentlicht, um neue Bedrohungen dringend zu bekämpfen.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="a8b0a-119">Microsoft Managed Desktop stellt diese Updates auf ähnliche Weise zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="a8b0a-120">Wir kategorisieren den Status von Sicherheitsupdateversionen mit den folgenden Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="a8b0a-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="a8b0a-121"><strong>Aktuell:</strong> Geräte, auf den das update ausgeführt wird, das im aktuellen Monat veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="a8b0a-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="a8b0a-122"><strong>Vorheriger:</strong> Geräte mit dem Update, das im Vorherigen Monat veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="a8b0a-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="a8b0a-123"><strong>Älter:</strong> Geräte mit sicherheitsupdates, die vor dem vorherigen Monat veröffentlicht wurden</span><span class="sxs-lookup"><span data-stu-id="a8b0a-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="a8b0a-124">In der Kategorie "Älter" sollten nur wenige Geräte angezeigt werden. Eine große oder wachsende Population weist wahrscheinlich auf ein systemisches Problem hin, das Sie melden sollten, Microsoft Managed Desktop wir untersuchen können. <strong></strong></span><span class="sxs-lookup"><span data-stu-id="a8b0a-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="a8b0a-125">Bereitstellungsfortschritt</span><span class="sxs-lookup"><span data-stu-id="a8b0a-125">Deployment progress</span></span>

<span data-ttu-id="a8b0a-126">Zu Beginn jedes Veröffentlichungszyklus für Sicherheitsupdates erstellt Microsoft Managed Desktop eine Momentaufnahme der Gerätegesamtheit und legt das Bereitstellungsziel auf 95 % dieser Population fest.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="a8b0a-127">Der <strong>Bereich Bereitstellungsfortschritt</strong> zeigt einen verlaufshistorischen Trend, der täglich aktualisiert wird und verfolgt, wie genau die Updatebereitstellung dieses Ziel für jede Version erfüllt.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="a8b0a-128">In diesem Diagramm werden nur Geräte mit dem Status "Aktiv" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="a8b0a-129">Sie können diese Daten für vorherige Aktualisierungszyklen anzeigen, indem Sie das Dropdownmenü oben rechts verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="a8b0a-130">Der in diesem Menü ausgewählte Zeitraum gilt für alle Informationen auf der gesamten Seite.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="a8b0a-131">Der <strong>Bereich Aktualisierte aktive Geräte</strong> nach Bereitstellungsgruppen bietet eine andere Ansicht, indem der Fortschritt der Updateinstallation für jede der Microsoft Managed Desktop angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="a8b0a-132">Der <strong>Bereich Tage bis</strong> zum Erreichen des Zielbereichs zeigt an, wie lange 95 % der Gesamtzahl der Geräte mit dem aktuellen Sicherheitsupdate aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="a8b0a-133">Während der Bereitstellung wird in diesem Bereich <strong>weiterhin</strong> aktualisiert, bis das Ziel von 95 % für das ausgewählte Update erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="a8b0a-134">Bereich "Gerätedetails"</span><span class="sxs-lookup"><span data-stu-id="a8b0a-134">Device details area</span></span>

<span data-ttu-id="a8b0a-135">Im unteren Bereich des Dashboards finden Sie eine Tabelle mit detaillierten Informationen für Ihre Geräte, einschließlich des [Gerätestatus](#device-status) und [des Updateversionsstatus.](#update-version-status)</span><span class="sxs-lookup"><span data-stu-id="a8b0a-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="a8b0a-136">Sie können diese Liste durchsuchen oder nach einem beliebigen aufgelisteten Wert filtern.</span><span class="sxs-lookup"><span data-stu-id="a8b0a-136">You can search this list or filter it by any listed value.</span></span>


![Gerätedetailsetabelle mit Spalten für gerätenamen, zugewiesenen Benutzer, Gerätestatus, Updateversion, Betriebssystemversion und das Datum, an dem das Gerät zuletzt synchronisiert wurde.](../../media/security-update-insights-device-table-sterile.png)
