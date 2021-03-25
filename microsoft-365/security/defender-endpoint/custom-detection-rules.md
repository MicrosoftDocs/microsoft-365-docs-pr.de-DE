---
title: Erstellen von benutzerdefinierten Erkennungsregeln in Microsoft Defender ATP
ms.reviewer: ''
description: Erfahren Sie, wie Sie benutzerdefinierte Erkennungsregeln basierend auf erweiterten Suchabfragen erstellen.
keywords: Benutzerdefinierte Erkennungen, erstellen, verwalten, Warnungen, bearbeiten, bei Bedarf ausführen, Häufigkeit, Intervall, Erkennungsregeln, erweiterte Suche, Suche, Abfrage, Reaktionsaktionen, Mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: fc4c15d2e391176ed0b4420c13fb865674da0361
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163587"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="efe55-104">Erstellen von benutzerdefinierten Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="efe55-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="efe55-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="efe55-105">**Applies to:**</span></span>
- [<span data-ttu-id="efe55-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="efe55-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="efe55-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="efe55-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="efe55-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="efe55-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="efe55-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="efe55-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="efe55-110">Mit benutzerdefinierten [](advanced-hunting-overview.md) Erkennungsregeln, die aus erweiterten Suchabfragen erstellt wurden, können Sie verschiedene Ereignisse und Systemzustände proaktiv überwachen, einschließlich mutmaßlicher Verletzungsaktivitäten und falsch konfigurierter Geräte.</span><span class="sxs-lookup"><span data-stu-id="efe55-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="efe55-111">Sie können festlegen, dass sie in regelmäßigen Intervallen ausgeführt werden, Warnungen generieren und Reaktionsaktionen ausführen, wenn Übereinstimmungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="efe55-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="efe55-112">In diesem Artikel erfahren Sie, wie Sie neue benutzerdefinierte Erkennungsregeln erstellen.</span><span class="sxs-lookup"><span data-stu-id="efe55-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="efe55-113">Weitere [Informationen finden Sie unter Anzeigen und Verwalten vorhandener Regeln.](custom-detections-manage.md)</span><span class="sxs-lookup"><span data-stu-id="efe55-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="efe55-114">Zum Erstellen oder Verwalten von benutzerdefinierten Erkennungen muss [Ihre Rolle](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) über die Berechtigung zum Verwalten **von Sicherheitseinstellungen** verfügen.</span><span class="sxs-lookup"><span data-stu-id="efe55-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="efe55-115">1. Bereiten Sie die Abfrage vor.</span><span class="sxs-lookup"><span data-stu-id="efe55-115">1. Prepare the query.</span></span>

<span data-ttu-id="efe55-116">Wechseln Sie im Microsoft Defender Security Center zu **Erweiterte Suche,** und wählen Sie eine vorhandene Abfrage aus, oder erstellen Sie eine neue Abfrage.</span><span class="sxs-lookup"><span data-stu-id="efe55-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="efe55-117">Wenn Sie eine neue Abfrage verwenden, führen Sie die Abfrage aus, um Fehler zu identifizieren und mögliche Ergebnisse zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="efe55-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="efe55-118">Damit der Dienst nicht zu viele Warnungen zurücksent, ist jede Regel auf die Generierung von nur 100 Warnungen beschränkt, wenn sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="efe55-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="efe55-119">Bevor Sie eine Regel erstellen, optimieren Sie Ihre Abfrage, um Warnungen für normale, täglich ausgeführte Aktivitäten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="efe55-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="efe55-120">Erforderliche Spalten in den Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="efe55-120">Required columns in the query results</span></span>

<span data-ttu-id="efe55-121">Um eine Abfrage für eine benutzerdefinierte Erkennungsregel zu verwenden, muss die Abfrage die folgenden Spalten zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="efe55-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="efe55-122">Einfache Abfragen, z. B. solche, die den Operator or nicht zum Anpassen oder Aggregieren von Ergebnissen verwenden, geben in der Regel `project` `summarize` diese allgemeinen Spalten zurück.</span><span class="sxs-lookup"><span data-stu-id="efe55-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="efe55-123">Es gibt verschiedene Möglichkeiten, um sicherzustellen, dass komplexere Abfragen diese Spalten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="efe55-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="efe55-124">Wenn Sie es z. B. vorziehen, nach zu aggregieren und zu zählen, können Sie sie trotzdem zurückgeben und aus dem neuesten Ereignis mit den `DeviceId` `Timestamp` einzelnen Geräten `ReportId` abrufen.</span><span class="sxs-lookup"><span data-stu-id="efe55-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="efe55-125">Die folgende Beispielabfrage zählt die Anzahl eindeutiger Geräte ( ) mit Antivirenerkennungen und verwendet diese, um nur die Geräte mit mehr als fünf Erkennungen `DeviceId` zu finden.</span><span class="sxs-lookup"><span data-stu-id="efe55-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="efe55-126">Zum Zurückgeben der neuesten `Timestamp` und der entsprechenden wird der Operator mit der Funktion `ReportId` `summarize` `arg_max` verwendet.</span><span class="sxs-lookup"><span data-stu-id="efe55-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="efe55-127">Legen Sie für eine bessere Abfrageleistung einen Zeitfilter fest, der der vorgesehenen Ausführungshäufigkeit für die Regel entspricht.</span><span class="sxs-lookup"><span data-stu-id="efe55-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="efe55-128">Da die am wenigsten häufige Ausführung alle 24 Stunden ist, werden alle neuen Daten durch die Filterung für den letzten Tag verdeckt.</span><span class="sxs-lookup"><span data-stu-id="efe55-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="efe55-129">2. Erstellen Sie eine neue Regel, und geben Sie Warnungsdetails an.</span><span class="sxs-lookup"><span data-stu-id="efe55-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="efe55-130">Wählen Sie mit der Abfrage  im Abfrage-Editor Erkennungsregel erstellen aus, und geben Sie die folgenden Warnungsdetails an:</span><span class="sxs-lookup"><span data-stu-id="efe55-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="efe55-131">**Erkennungsname**– Name der Erkennungsregel</span><span class="sxs-lookup"><span data-stu-id="efe55-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="efe55-132">**Häufigkeit**– Intervall zum Ausführen der Abfrage und Ausführen von Aktionen.</span><span class="sxs-lookup"><span data-stu-id="efe55-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="efe55-133">Weitere Anleitungen finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="efe55-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="efe55-134">**Warnungstitel**– Titel, der mit von der Regel ausgelösten Warnungen angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="efe55-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="efe55-135">**Schweregrad**– potenzielles Risiko der durch die Regel identifizierten Komponente oder Aktivität.</span><span class="sxs-lookup"><span data-stu-id="efe55-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="efe55-136">Informationen zu Warnungsschweregraden</span><span class="sxs-lookup"><span data-stu-id="efe55-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="efe55-137">**Kategorie**– Typ der Bedrohungskomponente oder -aktivität, falls welche.</span><span class="sxs-lookup"><span data-stu-id="efe55-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="efe55-138">Informationen zu Warnungskategorien</span><span class="sxs-lookup"><span data-stu-id="efe55-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="efe55-139">**MITRE ATT&CK-Techniken**– eine oder mehrere Angriffstechniken, die von der Regel identifiziert werden, wie im MITRE ATT&CK-Framework dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="efe55-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="efe55-140">Dieser Abschnitt ist nicht mit bestimmten Warnungskategorien wie Schadsoftware, Ransomware, verdächtigen Aktivitäten und unerwünschter Software verfügbar.</span><span class="sxs-lookup"><span data-stu-id="efe55-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="efe55-141">**Beschreibung**– weitere Informationen zu der durch die Regel identifizierten Komponente oder Aktivität</span><span class="sxs-lookup"><span data-stu-id="efe55-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="efe55-142">**Empfohlene Aktionen**– zusätzliche Aktionen, die Reaktionshelfer als Reaktion auf eine Warnung ausführen können</span><span class="sxs-lookup"><span data-stu-id="efe55-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="efe55-143">Weitere Informationen zur Anzeige von Warnungsdetails finden Sie [in der Warnungswarteschlange](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="efe55-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="efe55-144">Regelhäufigkeit</span><span class="sxs-lookup"><span data-stu-id="efe55-144">Rule frequency</span></span>

<span data-ttu-id="efe55-145">Beim Speichern wird sofort eine neue benutzerdefinierte Erkennungsregel ausgeführt und auf Übereinstimmungen aus den letzten 30 Tagen der Daten überprüft.</span><span class="sxs-lookup"><span data-stu-id="efe55-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="efe55-146">Die Regel wird dann in festen Intervallen und Nachschlagedauern basierend auf der von Ihnen festgelegten Häufigkeit erneut ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="efe55-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="efe55-147">**Alle 24 Stunden**– wird alle 24 Stunden ausgeführt und überprüft Daten aus den letzten 30 Tagen</span><span class="sxs-lookup"><span data-stu-id="efe55-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="efe55-148">**Alle 12 Stunden**– wird alle 12 Stunden ausgeführt und überprüft Daten aus den letzten 24 Stunden</span><span class="sxs-lookup"><span data-stu-id="efe55-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="efe55-149">**Alle 3 Stunden**– wird alle 3 Stunden ausgeführt und überprüft Daten aus den letzten 6 Stunden</span><span class="sxs-lookup"><span data-stu-id="efe55-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="efe55-150">**Jede Stunde**– wird stündlich ausgeführt und überprüft Daten aus den letzten 2 Stunden</span><span class="sxs-lookup"><span data-stu-id="efe55-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efe55-151">Beim Ändern einer Abfrage, die bereits als benutzerdefinierte Erkennung geplant ist, hat die nächste sofortige Ausführung ein Lookbackfenster von 30 Tagen, genau so, als würde eine neue Abfrage erstellt.</span><span class="sxs-lookup"><span data-stu-id="efe55-151">When changing a query that is already scheduled as a Custom Detection, it's next immediate execution will have a lookback window of 30 days, exactly as if a new query was being created.</span></span> <span data-ttu-id="efe55-152">Änderungen an einer großen Anzahl von Abfragen und mit Zeitfiltern, die über der standardmäßigen Nachschlagedauer für die ausgewählte Häufigkeit liegen, können sich auf den Gesamtkontingentverbrauch der erweiterten Suche auswirken und dazu führt, dass das tägliche Kontingent ausgeschöpft wird.</span><span class="sxs-lookup"><span data-stu-id="efe55-152">Changes to a large number of queries, and with time filters higher than the default lookback duration for the selected frequency, might have an impact in the overall quota consumption of Advanced Hunting and resulting in exhausting the daily quota.</span></span>

> [!TIP]
> <span data-ttu-id="efe55-153">Match the time filters in your query with the lookback duration.</span><span class="sxs-lookup"><span data-stu-id="efe55-153">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="efe55-154">Ergebnisse außerhalb der Lookbackdauer werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="efe55-154">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="efe55-155">Wählen Sie die Häufigkeit aus, die mit der Überwachungshäufigkeit der Erkennungen zusammen passt, und berücksichtigen Sie die Kapazität Ihrer Organisation, auf die Warnungen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="efe55-155">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="efe55-156">3. Wählen Sie die betroffenen Entitäten aus.</span><span class="sxs-lookup"><span data-stu-id="efe55-156">3. Choose the impacted entities.</span></span>

<span data-ttu-id="efe55-157">Identifizieren Sie die Spalten in den Abfrageergebnissen, in denen Sie erwarten, dass sie die haupt betroffene oder betroffene Entität finden.</span><span class="sxs-lookup"><span data-stu-id="efe55-157">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="efe55-158">Eine Abfrage kann z. B. Geräte- und Benutzer-IDs zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="efe55-158">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="efe55-159">Die Identifizierung, welche dieser Spalten die hauptsprallte Entität darstellen, hilft dem Dienst, relevante Warnungen zu aggregieren, Vorfälle zu korrelieren und Zielreaktionsaktionen zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="efe55-159">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="efe55-160">Sie können für jeden Entitätstyp nur eine Spalte auswählen.</span><span class="sxs-lookup"><span data-stu-id="efe55-160">You can select only one column for each entity type.</span></span> <span data-ttu-id="efe55-161">Spalten, die von Ihrer Abfrage nicht zurückgegeben werden, können nicht ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="efe55-161">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="efe55-162">4. Geben Sie Aktionen an.</span><span class="sxs-lookup"><span data-stu-id="efe55-162">4. Specify actions.</span></span>

<span data-ttu-id="efe55-163">Ihre benutzerdefinierte Erkennungsregel kann automatisch Aktionen für Dateien oder Geräte ausführen, die von der Abfrage zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="efe55-163">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="efe55-164">Aktionen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="efe55-164">Actions on devices</span></span>

<span data-ttu-id="efe55-165">Diese Aktionen werden auf Geräte in der `DeviceId` Spalte der Abfrageergebnisse angewendet:</span><span class="sxs-lookup"><span data-stu-id="efe55-165">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="efe55-166">**Gerät isolieren**– wendet die vollständige Netzwerkisolation an und verhindert, dass das Gerät eine Verbindung mit einer Anwendung oder einem Dienst herstellen kann, mit Ausnahme des Defender for Endpoint-Diensts.</span><span class="sxs-lookup"><span data-stu-id="efe55-166">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="efe55-167">Weitere Informationen zur Geräteisolation</span><span class="sxs-lookup"><span data-stu-id="efe55-167">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="efe55-168">**Untersuchungspaket sammeln**– Sammelt Geräteinformationen in einer ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="efe55-168">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="efe55-169">Weitere Informationen zum Untersuchungspaket</span><span class="sxs-lookup"><span data-stu-id="efe55-169">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="efe55-170">**Ausführen eines Antivirenscans**– führt eine vollständige Microsoft Defender Antivirus-Überprüfung auf dem Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="efe55-170">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="efe55-171">**Initiieren der** Untersuchung – startet [eine automatisierte Untersuchung](automated-investigations.md) auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="efe55-171">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="efe55-172">**Einschränken der App-Ausführung**– legt Einschränkungen auf dem Gerät fest, damit nur Dateien ausgeführt werden können, die mit einem von Microsoft ausgestellten Zertifikat signiert sind.</span><span class="sxs-lookup"><span data-stu-id="efe55-172">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="efe55-173">Weitere Informationen zum Einschränken der App-Ausführung</span><span class="sxs-lookup"><span data-stu-id="efe55-173">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="efe55-174">Aktionen für Dateien</span><span class="sxs-lookup"><span data-stu-id="efe55-174">Actions on files</span></span>

<span data-ttu-id="efe55-175">Diese Aktionen werden auf Dateien in der Spalte oder in `SHA1` `InitiatingProcessSHA1` den Abfrageergebnissen angewendet:</span><span class="sxs-lookup"><span data-stu-id="efe55-175">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="efe55-176">**Zulassen/Blockieren**– fügt die [](manage-indicators.md) Datei automatisch zu Ihrer benutzerdefinierten Indikatorliste hinzu, sodass sie immer ausgeführt oder blockiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="efe55-176">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="efe55-177">Sie können den Umfang dieser Aktion so festlegen, dass sie nur für ausgewählte Gerätegruppen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="efe55-177">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="efe55-178">Dieser Bereich ist unabhängig vom Bereich der Regel.</span><span class="sxs-lookup"><span data-stu-id="efe55-178">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="efe55-179">**Quarantänedatei**– löscht die Datei vom aktuellen Speicherort und platziert eine Kopie in Quarantäne.</span><span class="sxs-lookup"><span data-stu-id="efe55-179">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="efe55-180">Aktionen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="efe55-180">Actions on users</span></span>

- <span data-ttu-id="efe55-181">**Benutzer als gefährdet kennzeichnen**– legt die Risikostufe des Benutzers in Azure Active Directory auf "hoch" fest und löst die entsprechenden Identitätsschutzrichtlinien [aus.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)</span><span class="sxs-lookup"><span data-stu-id="efe55-181">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="efe55-182">5. Festlegen des Regelbereichs.</span><span class="sxs-lookup"><span data-stu-id="efe55-182">5. Set the rule scope.</span></span>

<span data-ttu-id="efe55-183">Legen Sie den Bereich fest, um anzugeben, welche Geräte von der Regel abgedeckt werden:</span><span class="sxs-lookup"><span data-stu-id="efe55-183">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="efe55-184">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="efe55-184">All devices</span></span>
- <span data-ttu-id="efe55-185">Bestimmte Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="efe55-185">Specific device groups</span></span>

<span data-ttu-id="efe55-186">Nur Daten von Geräten im Bereich werden abgefragt.</span><span class="sxs-lookup"><span data-stu-id="efe55-186">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="efe55-187">Außerdem werden Aktionen nur auf diesen Geräten ergriffen.</span><span class="sxs-lookup"><span data-stu-id="efe55-187">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="efe55-188">6. Überprüfen und aktivieren Sie die Regel.</span><span class="sxs-lookup"><span data-stu-id="efe55-188">6. Review and turn on the rule.</span></span>

<span data-ttu-id="efe55-189">Nachdem Sie die Regel überprüft haben, wählen **Sie Erstellen aus,** um sie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="efe55-189">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="efe55-190">Die benutzerdefinierte Erkennungsregel wird sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="efe55-190">The custom detection rule immediately runs.</span></span> <span data-ttu-id="efe55-191">Es wird basierend auf der konfigurierten Häufigkeit erneut ausgeführt, um nach Übereinstimmungen zu suchen, Warnungen zu generieren und Reaktionsaktionen zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="efe55-191">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="efe55-192">Sie können [benutzerdefinierte Erkennungsregeln](custom-detections-manage.md)anzeigen und verwalten, ihre vorherigen Läufe überprüfen und die ausgelösten Warnungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="efe55-192">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="efe55-193">Sie können auch eine Regel bei Bedarf ausführen und ändern.</span><span class="sxs-lookup"><span data-stu-id="efe55-193">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="efe55-194">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="efe55-194">Related topics</span></span>

- [<span data-ttu-id="efe55-195">Anzeigen und Verwalten von benutzerdefinierten Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="efe55-195">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="efe55-196">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="efe55-196">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="efe55-197">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="efe55-197">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="efe55-198">Erlernen der Abfragesprache für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="efe55-198">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="efe55-199">Anzeigen und Organisieren von Warnungen</span><span class="sxs-lookup"><span data-stu-id="efe55-199">View and organize alerts</span></span>](alerts-queue.md)
