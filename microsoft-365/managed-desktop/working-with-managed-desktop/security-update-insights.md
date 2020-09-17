---
title: Informationen zu Windows-Sicherheitsupdates
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 772d1d52e977a067ff9bc3517de9cb2ae6c8c9a3
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950367"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="be48a-103">Informationen zu Windows-Sicherheitsupdates</span><span class="sxs-lookup"><span data-stu-id="be48a-103">Windows security update insights</span></span>
<span data-ttu-id="be48a-104">Diese Ansicht bietet eine Übersicht über den Status von Sicherheitsupdates für Ihre von Microsoft verwalteten Desktop Geräte.</span><span class="sxs-lookup"><span data-stu-id="be48a-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="be48a-105">Um Verwendungsdaten anzuzeigen, wählen Sie die Registerkarte <strong>Windows-Sicherheitsupdates</strong> aus.</span><span class="sxs-lookup"><span data-stu-id="be48a-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows-Sicherheitsupdate Bereich: Balkendiagramme des Gerätestatus und der Update Version in der linken Spalte, Aktualisierungs Bereitstellungsfortschritt im Zeitverlauf in der mittleren Spalte und Prozentsatz aktiver Geräte nach Bereitstellungsgruppe sowie die Anzahl der Tage, die zum Erreichen des Bereitstellungsziels "95%" in der rechten Spalte verwendet wurden.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="be48a-107">Gerätestatus</span><span class="sxs-lookup"><span data-stu-id="be48a-107">Device status</span></span>

<span data-ttu-id="be48a-108">Für Geräte, die von Windows Update aktualisiert werden sollen, müssen Sie mit dem Internet verbunden sein und nicht über einen Ruhezustand für mindestens sechs Stunden verfügen, von denen zwei kontinuierlich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="be48a-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="be48a-109">Solange ein Gerät angeschlossen ist und kein Ruhezustand ist, wird es als "verwendet" betrachtet.</span><span class="sxs-lookup"><span data-stu-id="be48a-109">As long as a device is connected and not hibernating, it's considered to be "in use."</span></span> <span data-ttu-id="be48a-110">Obwohl es möglich ist, dass ein Gerät, das diese Anforderungen nicht erfüllt, aktualisiert wird, haben Geräte, die diese erfüllen, die höchste Wahrscheinlichkeit, dass Sie aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="be48a-110">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="be48a-111">Die Geräteaktivität wird im Kontext von Windows Update mit den folgenden Begriffen kategorisiert:</span><span class="sxs-lookup"><span data-stu-id="be48a-111">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="be48a-112"><strong>Aktiv:</strong> Geräte, die die minimalen Verwendungskriterien (sechs Stunden, zwei kontinuierlich) für die neueste Version des Sicherheitsupdates erfüllt haben und mindestens alle fünf Tage mit Microsoft InTune eingecheckt wurden</span><span class="sxs-lookup"><span data-stu-id="be48a-112"><strong>Active:</strong> Devices that have met the minimum usage criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="be48a-113"><strong>Synchronisiert:</strong> Geräte, die innerhalb der letzten 28 Tage mit InTune eingecheckt haben</span><span class="sxs-lookup"><span data-stu-id="be48a-113"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="be48a-114"><strong>Nicht synchron:</strong> Geräte, die in den letzten 28 Tagen <i>nicht</i> mit InTune eingecheckt haben</span><span class="sxs-lookup"><span data-stu-id="be48a-114"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="be48a-115">Aktualisieren des Versionsstatus</span><span class="sxs-lookup"><span data-stu-id="be48a-115">Update version status</span></span>

<span data-ttu-id="be48a-116">Microsoft veröffentlicht jeden zweiten Dienstag im Monat Sicherheitsupdates.</span><span class="sxs-lookup"><span data-stu-id="be48a-116">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="be48a-117">In jeder Version werden wichtige Updates für bekannte Sicherheitsrisiken hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be48a-117">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="be48a-118">Microsoft Managed Desktop stellt sicher, dass 95% der verwalteten Geräte monatlich mit dem neuesten verfügbaren Sicherheitsupdate aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="be48a-118">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="be48a-119">Manchmal werden Sicherheitsupdates zu anderen Zeiten veröffentlicht, um neue Bedrohungen dringend zu beheben.</span><span class="sxs-lookup"><span data-stu-id="be48a-119">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="be48a-120">Microsoft Managed Desktop stellt diese Updates auf ähnliche Weise bereit.</span><span class="sxs-lookup"><span data-stu-id="be48a-120">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="be48a-121">Der Status von Sicherheitsupdate Versionen wird mit den folgenden Begriffen kategorisiert:</span><span class="sxs-lookup"><span data-stu-id="be48a-121">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="be48a-122"><strong>Aktuell:</strong> Geräte, die das im aktuellen Monat veröffentlichte Update durchführen</span><span class="sxs-lookup"><span data-stu-id="be48a-122"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="be48a-123"><strong>Zurück:</strong> Geräte, die das Update durchführen, das im vorherigen Monat veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="be48a-123"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="be48a-124"><strong>Älter:</strong> Geräte, auf denen ein Sicherheitsupdate vor dem vorherigen Monat veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="be48a-124"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="be48a-125">Es sollten nur wenige Geräte in der <strong>älteren</strong> Kategorie angezeigt werden – eine große oder wachsende Population deutet wahrscheinlich auf ein systemisches Problem hin, das Sie an Microsoft Managed Desktop melden sollten, damit wir dies untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="be48a-125">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="be48a-126">Bereitstellungsfortschritt</span><span class="sxs-lookup"><span data-stu-id="be48a-126">Deployment progress</span></span>

<span data-ttu-id="be48a-127">Zu Beginn jedes Sicherheitsupdate-Veröffentlichungszyklus nimmt Microsoft Managed Desktop eine Momentaufnahme der Geräte Auffüllung vor und legt sein Bereitstellungsziel auf 95% dieser Auffüllung fest.</span><span class="sxs-lookup"><span data-stu-id="be48a-127">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="be48a-128">Im Bereich <strong>Bereitstellungsfortschritt</strong> wird ein historischer Trend angezeigt, der täglich aktualisiert wird und nachverfolgen kann, wie eng die Updatebereitstellung dieses Ziel für jede Version erfüllt.</span><span class="sxs-lookup"><span data-stu-id="be48a-128">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="be48a-129">In diesem Diagramm werden nur Geräte mit aktivem Status angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be48a-129">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="be48a-130">Sie können diese Daten für frühere Aktualisierungszyklen anzeigen, indem Sie das Dropdownmenü in der oberen rechten Ecke verwenden.</span><span class="sxs-lookup"><span data-stu-id="be48a-130">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="be48a-131">Der Zeitraum, den Sie in diesem Menü auswählen, gilt für alle Informationen auf der gesamten Seite.</span><span class="sxs-lookup"><span data-stu-id="be48a-131">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="be48a-132">Der Bereich " <strong>aktualisierte aktive Geräte nach Bereitstellungsgruppe</strong> " bietet eine andere Ansicht, indem der Fortschritt der Updateinstallation für jede der Microsoft Managed Desktop-Bereitstellungsgruppen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="be48a-132">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="be48a-133">Der <strong>Zielbereich "Tage zum erreichen</strong> " zeigt an, wie lange es dauerte, bis 95% der Gesamtzahl der Geräte mit dem aktuellen Sicherheitsupdate aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="be48a-133">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="be48a-134">Während der Bereitstellung wird in diesem Bereich <strong>noch aktualisiert</strong> , bis das 95%-Ziel für das ausgewählte Update erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="be48a-134">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="be48a-135">Geräte Detailbereich</span><span class="sxs-lookup"><span data-stu-id="be48a-135">Device details area</span></span>

<span data-ttu-id="be48a-136">Im unteren Bereich des Dashboards finden Sie eine Tabelle mit detaillierten Informationen zu Ihren Geräten, einschließlich des [Gerätestatus](#device-status) und des [Status der Update Version](#update-version-status).</span><span class="sxs-lookup"><span data-stu-id="be48a-136">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="be48a-137">Sie können diese Liste durchsuchen oder nach einem beliebigen angegebenen Wert filtern.</span><span class="sxs-lookup"><span data-stu-id="be48a-137">You can search this list or filter it by any listed value.</span></span>


![Geräte Detailtabelle mit Spalten für Gerätename, zugewiesener Benutzer, Gerätestatus, Update Version, Betriebssystemversion und Datum, an dem das Gerät zuletzt synchronisiert wurde.](../../media/security-update-insights-device-table-sterile.png)
