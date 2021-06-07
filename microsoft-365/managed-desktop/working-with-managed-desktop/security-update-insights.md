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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739797"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="6cbed-103">Informationen zu Windows-Sicherheitsupdates</span><span class="sxs-lookup"><span data-stu-id="6cbed-103">Windows security update insights</span></span>
<span data-ttu-id="6cbed-104">Diese Ansicht bietet eine Übersicht über den Status von Sicherheitsupdates für Ihre Microsoft Managed Desktop Geräte.</span><span class="sxs-lookup"><span data-stu-id="6cbed-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="6cbed-105">Um Nutzungsdaten anzuzeigen, wählen Sie die Registerkarte <strong>Windows Sicherheitsupdates</strong> aus.</span><span class="sxs-lookup"><span data-stu-id="6cbed-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows Bereich für Sicherheitsupdates: Balkendiagramme des Gerätestatus und der Updateversion in der linken Spalte, Aktualisierung des Bereitstellungsfortschritts im Zeitverlauf in der mittleren Spalte und Prozentsatz der aktiven Geräte nach Bereitstellungsgruppe sowie die Anzahl der Tage, die benötigt werden, um das Bereitstellungsziel von 95 % in der rechten Spalte zu erreichen.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="6cbed-107">Gerätestatus</span><span class="sxs-lookup"><span data-stu-id="6cbed-107">Device status</span></span>

<span data-ttu-id="6cbed-108">Damit Geräte durch Windows Update aktualisiert werden können, müssen sie mit dem Internet verbunden sein und nicht mindestens sechs Stunden in den Ruhezustand bleiben, von denen zwei fortlaufend sein müssen.</span><span class="sxs-lookup"><span data-stu-id="6cbed-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="6cbed-109">Obwohl es möglich ist, dass ein Gerät, das diese Anforderungen nicht erfüllt, aktualisiert wird, haben Geräte, die diese Anforderungen erfüllen, die höchste Wahrscheinlichkeit, aktualisiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="6cbed-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="6cbed-110">Wir kategorisieren Geräteaktivitäten im Kontext von Windows Update mit den folgenden Begriffen:</span><span class="sxs-lookup"><span data-stu-id="6cbed-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="6cbed-111"><strong>Aktiv:</strong> Geräte, die die Mindestaktivitätskriterien (sechs Stunden, zwei fortlaufend) für die letzte Sicherheitsupdateversion erfüllt haben und mindestens alle fünf Tage mit Microsoft Intune eingecheckt wurden</span><span class="sxs-lookup"><span data-stu-id="6cbed-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="6cbed-112"><strong>Synchronisiert:</strong> Geräte, die innerhalb der letzten 28 Tage bei Intune eingecheckt haben</span><span class="sxs-lookup"><span data-stu-id="6cbed-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="6cbed-113"><strong>Nicht mehr synchron:</strong> Geräte, die in den letzten 28 Tagen <i>nicht</i> bei Intune eingecheckt wurden</span><span class="sxs-lookup"><span data-stu-id="6cbed-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="6cbed-114">Aktualisieren des Versionsstatus</span><span class="sxs-lookup"><span data-stu-id="6cbed-114">Update version status</span></span>

<span data-ttu-id="6cbed-115">Microsoft veröffentlicht sicherheitsrelevante Updates jeden zweiten Dienstag des Monats.</span><span class="sxs-lookup"><span data-stu-id="6cbed-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="6cbed-116">Jede Version fügt wichtige Updates für bekannte Sicherheitsrisiken hinzu.</span><span class="sxs-lookup"><span data-stu-id="6cbed-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="6cbed-117">Microsoft Managed Desktop stellt sicher, dass 95 % der verwalteten Geräte jeden Monat mit dem neuesten verfügbaren Sicherheitsupdate aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6cbed-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="6cbed-118">Sicherheitsupdates werden manchmal zu anderen Zeiten veröffentlicht, um neue Bedrohungen dringend zu beheben.</span><span class="sxs-lookup"><span data-stu-id="6cbed-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="6cbed-119">Microsoft Managed Desktop stellt diese Updates auf ähnliche Weise bereit.</span><span class="sxs-lookup"><span data-stu-id="6cbed-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="6cbed-120">Wir kategorisieren den Status von Sicherheitsupdateversionen mit den folgenden Begriffen:</span><span class="sxs-lookup"><span data-stu-id="6cbed-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="6cbed-121"><strong>Aktuell:</strong> Geräte, auf denen das im aktuellen Monat veröffentlichte Update ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="6cbed-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="6cbed-122"><strong>Zurück:</strong> Geräte, auf denen das Update ausgeführt wird, das im vorherigen Monat veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="6cbed-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="6cbed-123"><strong>Älter:</strong> Geräte, auf denen ein Sicherheitsupdate ausgeführt wird, das vor dem vorherigen Monat veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="6cbed-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="6cbed-124">Sie sollten einige Geräte in der <strong>älteren</strong> Kategorie sehen – eine große oder wachsende Population deutet wahrscheinlich auf ein erhebliches Problem hin, das Sie an Microsoft Managed Desktop melden sollten, damit wir untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="6cbed-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="6cbed-125">Bereitstellungsfortschritt</span><span class="sxs-lookup"><span data-stu-id="6cbed-125">Deployment progress</span></span>

<span data-ttu-id="6cbed-126">Zu Beginn jedes Sicherheitsupdate-Veröffentlichungszyklus erstellt Microsoft Managed Desktop eine Momentaufnahme der Geräteanzahl und legt das Bereitstellungsziel auf 95 % dieser Population fest.</span><span class="sxs-lookup"><span data-stu-id="6cbed-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="6cbed-127">Der <strong>Bereich "Bereitstellungsfortschritt"</strong> zeigt einen historischen Trend, der täglich aktualisiert wird, und verfolgt, wie eng die Updatebereitstellung dieses Ziel für jede Version erreicht.</span><span class="sxs-lookup"><span data-stu-id="6cbed-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="6cbed-128">Dieses Diagramm zeigt nur Geräte mit dem Status "Aktiv".</span><span class="sxs-lookup"><span data-stu-id="6cbed-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="6cbed-129">Sie können diese Daten für vorherige Updatezyklen anzeigen, indem Sie das Dropdownmenü oben rechts verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cbed-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="6cbed-130">Der in diesem Menü ausgewählte Zeitraum gilt für alle Informationen auf der gesamten Seite.</span><span class="sxs-lookup"><span data-stu-id="6cbed-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="6cbed-131">Der Bereich <strong>"Aktualisierte aktive Geräte nach Bereitstellungsgruppen"</strong> bietet eine andere Ansicht, indem der Fortschritt der Updateinstallation für jede der Microsoft Managed Desktop Bereitstellungsgruppen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6cbed-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="6cbed-132">In den <strong>Tagen bis zum Erreichen</strong> des Zielbereichs wird angezeigt, wie lange es gedauert hat, bis 95 % der Gesamtzahl der Geräte mit dem aktuellen Sicherheitsupdate aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6cbed-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="6cbed-133">Während der Bereitstellung wird in diesem Bereich weiterhin <strong>aktualisiert,</strong> bis das Ziel von 95 % für das ausgewählte Update erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="6cbed-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="6cbed-134">Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="6cbed-134">Device details area</span></span>

<span data-ttu-id="6cbed-135">Am unteren Rand des Dashboards finden Sie eine Tabelle mit detaillierten Informationen zu Ihren Geräten, einschließlich des [Gerätestatus](#device-status) und des [Updateversionsstatus.](#update-version-status)</span><span class="sxs-lookup"><span data-stu-id="6cbed-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="6cbed-136">Sie können diese Liste durchsuchen oder nach einem beliebigen aufgelisteten Wert filtern.</span><span class="sxs-lookup"><span data-stu-id="6cbed-136">You can search this list or filter it by any listed value.</span></span>


![Tabelle mit Gerätedetails mit Spalten für Gerätename, zugewiesener Benutzer, Gerätestatus, Updateversion, Betriebssystemversion und datum der letzten Synchronisierung des Geräts.](../../media/security-update-insights-device-table-sterile.png)
