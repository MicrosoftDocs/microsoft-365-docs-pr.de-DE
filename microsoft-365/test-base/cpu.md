---
title: CPU-Regressionsanalyse
description: Grundlegendes zu Regressionsergebnissen und Metriken für die CPU-Auslastung
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322720"
---
# <a name="intelligent-cpu-regression-analysis"></a><span data-ttu-id="d2179-103">Intelligente CPU-Regressionsanalyse</span><span class="sxs-lookup"><span data-stu-id="d2179-103">Intelligent CPU regression analysis</span></span>

<span data-ttu-id="d2179-104">Die CPU-Auslastung kann angeben, ob eine Anwendung von einem Betriebssystemupdate betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="d2179-104">CPU utilization can indicate whether an application is affected by an operating system update.</span></span> 

<span data-ttu-id="d2179-105">Die Testbasis für Microsoft 365 bietet Softwareentwicklern einen Einblick in CPU-Leistungsregressionen, die auftreten, wenn ihre Anwendung unter verschiedenen Versionen eines bevorstehenden Betriebssystemupdates (Windows Betriebssystem) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d2179-105">Test Base for Microsoft 365 provides software developers with an insight into CPU performance regressions which occur when their application is running on different versions of an upcoming Windows Operating System (OS) update.</span></span> 

<span data-ttu-id="d2179-106">Diese CPU-Regressionen ermöglichen Es Entwicklern, Anwendungsprobleme (und potenzielle Fehler) zu erkennen und zu beheben, bevor das Betriebssystemupdate allgemein bereitgestellt wird, wodurch eine schlechte Benutzererfahrung verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="d2179-106">These CPU regressions enable developers to detect and resolve application issues (and potential failures) before the OS update is deployed broadly, thus preventing a bad experience for the end user.</span></span>


### <a name="how-cpu-regression-analysis-works"></a><span data-ttu-id="d2179-107">Funktionsweise der CPU-Regressionsanalyse</span><span class="sxs-lookup"><span data-stu-id="d2179-107">How CPU regression analysis works</span></span> ###

<span data-ttu-id="d2179-108">Als Testbasisbenutzer können Sie die Binärdateien Ihrer Anwendung (in einer einzelnen .zip-Datei) zusammen mit den zugehörigen Testskripts hochladen und die Windows Betriebssystemversion auswählen, mit der Sie Ihre Anwendung im Testbasisportal in Azure testen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2179-108">As a Test Base user, you can upload your application's binaries (in a single .zip file), along with associated test scripts and select the Windows OS version against which you would like to test your application on the Test Base portal on Azure.</span></span> 

<span data-ttu-id="d2179-109">Der Testbasisdienst führt dann die Testskripts aus und führt die **CPU-Regressionsanalyse** aus.</span><span class="sxs-lookup"><span data-stu-id="d2179-109">The Test Base service then runs the test scripts and performs the **CPU Regression Analysis**.</span></span> 

<span data-ttu-id="d2179-110">Der Dienst überprüft, ob die CPU-Auslastung für die Anwendung in der Vorabversion des Updates für das Zielbetriebssystem mit der CPU-Auslastung für die veröffentlichte Version des Betriebssystems in Einklang steht.</span><span class="sxs-lookup"><span data-stu-id="d2179-110">The service checks if the CPU utilization for the application on the pre-release version of the update for the target OS is in line with the CPU utilization for the released version of the OS.</span></span> 

<span data-ttu-id="d2179-111">Die CPU-Auslastung ist kein 100%iger vergleichsähnlicher Vergleich, da die Prozesse, die auf den beiden Versionen des Betriebssystems ausgeführt werden, aufgrund unterschiedlicher Betriebssystemversionen möglicherweise eine genaue Übereinstimmung darstellen. Die von Test Base durchgeführte Analyse kann jedoch zeigen, ob die CPU-Auslastung für Ihre Anwendung von einem bevorstehenden Betriebssystemupdate betroffen ist und welche Prozesse aus vorherigen Testläufen zurückgeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="d2179-111">CPU utilization is not a 100% like-for-like comparison because the processes running on the two versions of the OS may or may not be an exact match due to differing OS versions; however, the analysis performed by Test Base can show you whether CPU utilization for your application is impacted by an upcoming OS update and specifically which processes have regressed from previous test runs.</span></span>

<span data-ttu-id="d2179-112">In der folgenden Momentaufnahme gibt es zwei Betriebssystemversionen, mit denen die CPU-Auslastung für dieselbe Anwendung verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="d2179-112">In the snapshot below, there are two OS releases against which the CPU utilizations are compared for the same application.</span></span> 
-   <span data-ttu-id="d2179-113">Auf der Registerkarte "CPU-Auslastung" werden die oberen und unteren Begrenzungen der Auslastung für beide Versionen jeweils am 90. und 10. Quantil angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2179-113">The CPU utilization tab shows the upper and lower bounds of utilization for both releases at 90th and 10th percentiles respectively.</span></span> 
-   <span data-ttu-id="d2179-114">Die Diagramme zeigen die Zeitreihe der CPU-Auslastung zusammen mit der durchschnittlichen Auslastung.</span><span class="sxs-lookup"><span data-stu-id="d2179-114">The graphs show the time series of CPU utilization along with the average utilization.</span></span> 

<span data-ttu-id="d2179-115">Kunden können nun anhand der Funktionalität ermitteln, ob die CPU-Auslastung ihrer Anwendung durch Betriebssystemupdates beeinträchtigt wird und welche Prozesse von der vorherigen Ausführung zurückgeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="d2179-115">Customers can now use the functionality to determine if their application's CPU utilization is impacted by OS updates and specifically which processes have regressed from their previous execution.</span></span>


![CPU-Regressionsanalyse](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a><span data-ttu-id="d2179-117">Relevante Prozessidentifikation</span><span class="sxs-lookup"><span data-stu-id="d2179-117">Relevant Process Identification</span></span> ###

<span data-ttu-id="d2179-118">Hier wird erläutert, wie sie zurückgeleitete Prozesse in der Anwendung identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="d2179-118">Here, we discuss how to identify regressed processes in the application.</span></span> 

<span data-ttu-id="d2179-119">Die Analyse der Leistungsregression erfordert das Nachverfolgen verschiedener Arten von Leistungsindikatoren für jeden Prozess, der während des Testlaufs auf einem virtuellen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d2179-119">Analyzing performance regression requires tracking different kinds of performance counters for every process running on a virtual machine during the test run.</span></span> 

<span data-ttu-id="d2179-120">Bei einer solchen Analyse werden viele Variablen für viele Prozesse für eine bestimmte Anwendung erfasst.</span><span class="sxs-lookup"><span data-stu-id="d2179-120">Such analysis captures a lot of variables for a lot of processes for a given application.</span></span> <span data-ttu-id="d2179-121">Nicht alle Prozesse sind einer Ausführung oder Anwendung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d2179-121">Not all processes are associated with a run or application.</span></span> <span data-ttu-id="d2179-122">Um diese Herausforderung zu umgehen, wird mithilfe der Wahrscheinlichkeits- und Informationsthematik ein Algorithmus zur gegenseitigen Informationsbewertung angewendet, um herauszufinden, welche Prozesse für eine bestimmte Anwendung am relevantesten sind.</span><span class="sxs-lookup"><span data-stu-id="d2179-122">To work around this challenge, a mutual information ranking algorithm using probability and information theory is applied to figure out which processes are most relevant for a given application.</span></span> 

<span data-ttu-id="d2179-123">Eine Anwendung kann als ein Typ diskreter Zufallsvariablen betrachtet werden, während ein Prozess als eine andere Art diskreter Zufallsvariablen betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="d2179-123">An application can be considered one type of discrete random variable while a process is considered another kind of discrete random variable.</span></span> <span data-ttu-id="d2179-124">Die Zuordnung der beiden Zufallsvariablen wird mit bedingten Wahrscheinlichkeiten für die Relevanz gemessen.</span><span class="sxs-lookup"><span data-stu-id="d2179-124">The association of the two random variables is measured using conditional probabilities for relevance.</span></span> 

<span data-ttu-id="d2179-125">Prozesse werden dann in der Reihenfolge ihrer Relevanz für jede Anwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2179-125">Processes are then displayed in the order of their relevance for each application.</span></span> <span data-ttu-id="d2179-126">Sie können auch eine Teilmenge von Prozessen als Favorit verwenden, die standardmäßig zusammen mit relevanten Prozessen für die CPU-Regressionsanalyse überwacht werden können.</span><span class="sxs-lookup"><span data-stu-id="d2179-126">You can also favorite a subset of processes that can be monitored, by default, along with relevant processes for CPU regression analysis.</span></span> <span data-ttu-id="d2179-127">Sobald eine Regression erkannt wurde, können Sie das Windows Performance Analyzer-Toolkit herunterladen und die Gründe für CPU-Leistungsregressionen analysieren.</span><span class="sxs-lookup"><span data-stu-id="d2179-127">Once a regression is detected, you can download the Windows Performance Analyzer toolkit and analyze reasons for CPU performance regressions.</span></span> 

<span data-ttu-id="d2179-128">Die Windows Performance Analyzer verwendet Ereignisablaufverfolgungsprotokoll (Event Trace Log, ETL) als Eingaben, und diese ETL-Dateien sind in den Protokolldateien verfügbar, die für Testläufe im Portal herunterladbar sind.</span><span class="sxs-lookup"><span data-stu-id="d2179-128">The Windows Performance Analyzer takes event trace log (ETL) as inputs and these .etl files are available in the log files downloadable for test runs on the portal.</span></span> <span data-ttu-id="d2179-129">Weitere Informationen zum Debuggen der CPU-Leistung finden Sie in der Dokumentation Windows Performance Analyzer.</span><span class="sxs-lookup"><span data-stu-id="d2179-129">If you would like to know more about debugging CPU performance, see the Windows Performance Analyzer documentation.</span></span>

