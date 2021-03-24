---
title: Untersuchen von Microsoft Defender for Endpoint-Dateien
description: Verwenden Sie die Untersuchungsoptionen, um Details zu Dateien zu erhalten, die Warnungen, Verhaltensweisen oder Ereignissen zugeordnet sind.
keywords: Untersuchen, Untersuchen, Datei, bösartige Aktivitäten, Angriffsmotivation, tiefe Analyse, detaillierter Analysebericht
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a801b6153cf3f273290721756440cfe974103e92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064568"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="78fa3-104">Untersuchen einer Datei, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="78fa3-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="78fa3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="78fa3-105">**Applies to:**</span></span>
- [<span data-ttu-id="78fa3-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="78fa3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="78fa3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78fa3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="78fa3-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="78fa3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="78fa3-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="78fa3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="78fa3-110">Untersuchen Sie die Details einer Datei, die mit einer bestimmten Warnung, einem bestimmten Verhalten oder einem bestimmten Ereignis verknüpft ist, um festzustellen, ob die Datei schädliche Aktivitäten enthält, die Angriffsmotivation zu identifizieren und den potenziellen Umfang der Verletzung zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="78fa3-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="78fa3-111">Es gibt viele Möglichkeiten, auf die detaillierte Profilseite einer bestimmten Datei zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="78fa3-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="78fa3-112">Sie können z. B. das Suchfeature verwenden, auf einen Link aus der Warnungsprozessstruktur, dem Vorfalldiagramm, der Artefaktzeitachse oder einem ereignis auswählen, das in der Gerätezeitachse aufgeführt **ist.**</span><span class="sxs-lookup"><span data-stu-id="78fa3-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="78fa3-113">Sobald Sie auf der detaillierten Profilseite sind, können Sie zwischen den neuen und alten Seitenlayouts wechseln, indem Sie neue **Dateiseite umschalten.**</span><span class="sxs-lookup"><span data-stu-id="78fa3-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="78fa3-114">Der Rest dieses Artikels beschreibt das neuere Seitenlayout.</span><span class="sxs-lookup"><span data-stu-id="78fa3-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="78fa3-115">Sie können Informationen aus den folgenden Abschnitten in der Dateiansicht erhalten:</span><span class="sxs-lookup"><span data-stu-id="78fa3-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="78fa3-116">Dateidetails, Schadsoftwareerkennung, Dateiprävalenz</span><span class="sxs-lookup"><span data-stu-id="78fa3-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="78fa3-117">Tiefe Analyse</span><span class="sxs-lookup"><span data-stu-id="78fa3-117">Deep analysis</span></span>
- <span data-ttu-id="78fa3-118">Warnungen</span><span class="sxs-lookup"><span data-stu-id="78fa3-118">Alerts</span></span>
- <span data-ttu-id="78fa3-119">Beobachtet in der Organisation</span><span class="sxs-lookup"><span data-stu-id="78fa3-119">Observed in organization</span></span>
- <span data-ttu-id="78fa3-120">Tiefe Analyse</span><span class="sxs-lookup"><span data-stu-id="78fa3-120">Deep analysis</span></span>
- <span data-ttu-id="78fa3-121">Dateinamen</span><span class="sxs-lookup"><span data-stu-id="78fa3-121">File names</span></span>

<span data-ttu-id="78fa3-122">Sie können auf dieser Seite auch Aktionen für eine Datei ergreifen.</span><span class="sxs-lookup"><span data-stu-id="78fa3-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="78fa3-123">Dateiaktionen</span><span class="sxs-lookup"><span data-stu-id="78fa3-123">File actions</span></span>

<span data-ttu-id="78fa3-124">Oben auf der Profilseite oberhalb der Dateiinformationskarten.</span><span class="sxs-lookup"><span data-stu-id="78fa3-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="78fa3-125">Folgende Aktionen können Sie hier ausführen:</span><span class="sxs-lookup"><span data-stu-id="78fa3-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="78fa3-126">Beenden und Isolieren</span><span class="sxs-lookup"><span data-stu-id="78fa3-126">Stop and quarantine</span></span>
- <span data-ttu-id="78fa3-127">Add/Edit Indicator</span><span class="sxs-lookup"><span data-stu-id="78fa3-127">Add/edit indicator</span></span>
- <span data-ttu-id="78fa3-128">Datei herunterladen</span><span class="sxs-lookup"><span data-stu-id="78fa3-128">Download file</span></span>
- <span data-ttu-id="78fa3-129">Konsultieren eines Bedrohungsexperten</span><span class="sxs-lookup"><span data-stu-id="78fa3-129">Consult a threat expert</span></span>
- <span data-ttu-id="78fa3-130">Info-Center</span><span class="sxs-lookup"><span data-stu-id="78fa3-130">Action center</span></span>

<span data-ttu-id="78fa3-131">Weitere Informationen zu diesen Aktionen finden Sie unter [Take response action on a file](respond-file-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="78fa3-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="78fa3-132">Dateidetails, Schadsoftwareerkennung und Dateiprävalenz</span><span class="sxs-lookup"><span data-stu-id="78fa3-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="78fa3-133">Die Dateidetails, Vorfälle, Schadsoftwareerkennung und Dateiprävalenzkarten zeigen verschiedene Attribute zur Datei an.</span><span class="sxs-lookup"><span data-stu-id="78fa3-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="78fa3-134">Es werden Details wie md5 der Datei, das Virus Total Detection Ratio und die Microsoft Defender AV-Erkennung (sofern verfügbar) und die Verbreitung der Datei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78fa3-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="78fa3-135">Die Dateiprävalenzkarte zeigt an, wo die Datei auf Geräten in der Organisation und weltweit angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="78fa3-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="78fa3-136">Unterschiedliche Benutzer sehen möglicherweise abweichende Werte im Abschnitt *Geräte in* der Organisation der Dateiprävalenzkarte.</span><span class="sxs-lookup"><span data-stu-id="78fa3-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="78fa3-137">Dies liegt daran, dass auf der Karte Informationen basierend auf dem RBAC-Bereich angezeigt werden, über den ein Benutzer verfügt.</span><span class="sxs-lookup"><span data-stu-id="78fa3-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="78fa3-138">Wenn einem Benutzer also Sichtbarkeit auf einer bestimmten Gruppe von Geräten gewährt wurde, wird ihm nur die Dateiorganisationsprävalenz auf diesen Geräten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78fa3-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![Abbildung von Dateiinformationen](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="78fa3-140">Warnungen</span><span class="sxs-lookup"><span data-stu-id="78fa3-140">Alerts</span></span>

<span data-ttu-id="78fa3-141">Die **Registerkarte Warnungen** enthält eine Liste der Warnungen, die der Datei zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="78fa3-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="78fa3-142">Diese Liste enthält viele der gleichen Informationen wie die Warnungswarteschlange, mit Ausnahme der Gerätegruppe, falls vorhanden, zu dem das betroffene Gerät gehört.</span><span class="sxs-lookup"><span data-stu-id="78fa3-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="78fa3-143">Sie können auswählen, welche Art von Informationen angezeigt wird, indem Sie **Spalten** in der Symbolleiste oberhalb der Spaltenüberschriften anpassen auswählen.</span><span class="sxs-lookup"><span data-stu-id="78fa3-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![Abbildung von Warnungen im Zusammenhang mit dem Dateiabschnitt](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="78fa3-145">Beobachtet in der Organisation</span><span class="sxs-lookup"><span data-stu-id="78fa3-145">Observed in organization</span></span>

<span data-ttu-id="78fa3-146">Auf **der Registerkarte Beobachtet in der** Organisation können Sie einen Datumsbereich angeben, um zu sehen, welche Geräte mit der Datei beobachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="78fa3-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="78fa3-147">Auf dieser Registerkarte wird eine maximale Anzahl von 100 Geräten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78fa3-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="78fa3-148">Um alle _Geräte_ mit der Datei anzuzeigen, exportieren Sie die Registerkarte in eine CSV-Datei, indem Sie **export** from the action menu above the tab's column headers auswählen.</span><span class="sxs-lookup"><span data-stu-id="78fa3-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![Abbildung des zuletzt beobachteten Geräts mit der Datei](images/atp-observed-machines.png)

<span data-ttu-id="78fa3-150">Verwenden Sie den Schieberegler oder die Bereichsauswahl, um schnell einen Zeitraum anzugeben, den Sie auf Ereignisse überprüfen möchten, die die Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="78fa3-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="78fa3-151">Sie können ein Zeitfenster so klein wie einen einzelnen Tag angeben.</span><span class="sxs-lookup"><span data-stu-id="78fa3-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="78fa3-152">Dadurch können Sie nur Dateien sehen, die zu diesem Zeitpunkt mit dieser IP-Adresse kommuniziert haben, wodurch unnötige Bildlauf- und Suchdateien erheblich reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="78fa3-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="78fa3-153">Tiefe Analyse</span><span class="sxs-lookup"><span data-stu-id="78fa3-153">Deep analysis</span></span>

<span data-ttu-id="78fa3-154">Auf **der** Registerkarte Tiefe Analyse können Sie die Datei für eine tiefe Analyse [übermitteln,](respond-file-alerts.md#deep-analysis)um weitere Details zum Verhalten der Datei sowie zu den Auswirkungen in Ihren Organisationen aufzudecken.</span><span class="sxs-lookup"><span data-stu-id="78fa3-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="78fa3-155">Nachdem Sie die Datei übermittelt haben, wird der Detaillierte Analysebericht auf dieser Registerkarte angezeigt, sobald Ergebnisse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="78fa3-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="78fa3-156">Wenn bei der tiefen Analyse nichts zu finden ist, ist der Bericht leer, und der Ergebnisbereich bleibt leer.</span><span class="sxs-lookup"><span data-stu-id="78fa3-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![Abbildung der Registerkarte "Tiefe Analyse"](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="78fa3-158">Dateinamen</span><span class="sxs-lookup"><span data-stu-id="78fa3-158">File names</span></span>

<span data-ttu-id="78fa3-159">Auf **der Registerkarte** Dateinamen werden alle Namen aufgeführt, die die Datei in Ihren Organisationen verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="78fa3-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![Registerkarte "Bild der Dateinamen"](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="78fa3-161">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="78fa3-161">Related topics</span></span>

- [<span data-ttu-id="78fa3-162">Anzeigen und Organisieren der Microsoft Defender for Endpoint-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="78fa3-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="78fa3-163">Verwalten von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="78fa3-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="78fa3-164">Untersuchen von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="78fa3-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="78fa3-165">Untersuchen von Geräten in der Microsoft Defender for Endpoint Devices-Liste</span><span class="sxs-lookup"><span data-stu-id="78fa3-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="78fa3-166">Untersuchen einer einer Microsoft Defender for Endpoint-Warnung zugeordneten IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="78fa3-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="78fa3-167">Untersuchen einer Domäne, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="78fa3-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="78fa3-168">Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="78fa3-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="78fa3-169">Ausführen von Reaktionsaktionen für eine Datei</span><span class="sxs-lookup"><span data-stu-id="78fa3-169">Take response actions on a file</span></span>](respond-file-alerts.md)
