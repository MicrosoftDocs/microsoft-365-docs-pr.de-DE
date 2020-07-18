---
title: App-Steuerelement
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e9d33df0ae11d01c8c214fbe0f001a16e8f4908d
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170721"
---
# <a name="app-control"></a><span data-ttu-id="58ab6-103">App-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="58ab6-103">App control</span></span>

<span data-ttu-id="58ab6-104">App-Steuerelement ist eine optionale Sicherheitspraxis in Microsoft Managed Desktop, die die Ausführung von Code auf Clientgeräten einschränkt.</span><span class="sxs-lookup"><span data-stu-id="58ab6-104">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="58ab6-105">Durch dieses Steuerelement wird das Risiko von Schadsoftware oder böswilligen Skripts verringert, da nur Code ausgeführt werden kann, der von einer vom Kunden genehmigten Liste mit Herausgebern signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="58ab6-105">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="58ab6-106">Dieses Steuerelement bietet viele Sicherheitsvorteile, zielt jedoch in erster Linie darauf ab, Daten und Identität vor clientbasierten Exploits zu schützen.</span><span class="sxs-lookup"><span data-stu-id="58ab6-106">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="58ab6-107">Microsoft Managed Desktop vereinfacht die Verwaltung von App-Steuerelement Richtlinien, indem eine Basisrichtlinie erstellt wird, die Kern Produktivitätsszenarien ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="58ab6-107">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="58ab6-108">Sie können die Vertrauensstellung auf zusätzliche Signaturer erweitern, die für die apps und Skripts in Ihrer Umgebung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="58ab6-108">You can extend trust to additional signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="58ab6-109">Jede Sicherheitstechnologie erfordert ein Gleichgewichtzwischen Benutzerfreundlichkeit, Sicherheit und Kosten.</span><span class="sxs-lookup"><span data-stu-id="58ab6-109">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="58ab6-110">Das App-Steuerelement reduziert die Bedrohung durch Schadsoftware in Ihrer Umgebung, es gibt jedoch Konsequenzen für den Endbenutzer und zusätzliche Aktionen für Ihren IT-Administrator.</span><span class="sxs-lookup"><span data-stu-id="58ab6-110">App control reduces the threat of malicious software in your environment, but there are consequences to the end user and additional actions for your IT administrator.</span></span>

<span data-ttu-id="58ab6-111">**Zusätzliche Sicherheit:**</span><span class="sxs-lookup"><span data-stu-id="58ab6-111">**Additional security:**</span></span>

<span data-ttu-id="58ab6-112">Für apps oder Skripts, denen die APP-Steuerelement Richtlinie nicht vertraut, wird die Ausführung auf Geräten blockiert.</span><span class="sxs-lookup"><span data-stu-id="58ab6-112">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="58ab6-113">**Ihre zusätzlichen Aufgaben:**</span><span class="sxs-lookup"><span data-stu-id="58ab6-113">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="58ab6-114">Sie sind für das Testen Ihrer Apps verantwortlich, um zu ermitteln, ob Sie von der anwendungssteuerungsrichtlinie blockiert würden.</span><span class="sxs-lookup"><span data-stu-id="58ab6-114">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="58ab6-115">Wenn eine APP blockiert ist (oder wäre), sind Sie dafür verantwortlich, die erforderlichen Signer-Details zu identifizieren und eine Änderung über das Verwaltungsportal anzufordern.</span><span class="sxs-lookup"><span data-stu-id="58ab6-115">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="58ab6-116">**Aufgaben von Microsoft Managed Desktop:**</span><span class="sxs-lookup"><span data-stu-id="58ab6-116">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="58ab6-117">Microsoft Managed Desktop verwaltet die Basisrichtlinie, die Kernprodukte von Microsoft wie M365-apps, Windows, Teams, OneDrive usw. aktiviert.</span><span class="sxs-lookup"><span data-stu-id="58ab6-117">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="58ab6-118">Microsoft Managed Desktop fügt Ihre vertrauenswürdigen unterzeichnenden ein und stellt die aktualisierte Richtlinie auf Ihren Geräten bereit.</span><span class="sxs-lookup"><span data-stu-id="58ab6-118">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="58ab6-119">Verwalten der Vertrauensstellung in Anwendungen</span><span class="sxs-lookup"><span data-stu-id="58ab6-119">Managing trust in applications</span></span>

<span data-ttu-id="58ab6-120">Microsoft Managed Desktop kuratiert eine Basisrichtlinie, die den Kernkomponenten von Microsoft-Technologien vertraut.</span><span class="sxs-lookup"><span data-stu-id="58ab6-120">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="58ab6-121">Sie fügen dann Vertrauenswürdigkeit für Ihre eigenen Anwendungen und Skripts *hinzu* , indem Sie Microsoft Managed Desktop informieren, dem Sie bereits Vertrauen.</span><span class="sxs-lookup"><span data-stu-id="58ab6-121">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="58ab6-122">Basisrichtlinie</span><span class="sxs-lookup"><span data-stu-id="58ab6-122">Base policy</span></span>

<span data-ttu-id="58ab6-123">Microsoft Managed Desktop erstellt und verwaltet in Zusammenarbeit mit Microsoft Cyber-Experten eine Standardrichtlinie, die die meisten in Microsoft InTune bereitgestellten apps aktiviert, während gefährliche Aktivitäten wie die Codekompilierung oder die Ausführung nicht vertrauenswürdiger Dateien blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="58ab6-123">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="58ab6-124">Die Basisrichtlinie verfolgt die folgende Vorgehensweise zum Einschränken der Softwareausführung:</span><span class="sxs-lookup"><span data-stu-id="58ab6-124">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="58ab6-125">Von Administratoren ausgeführte Dateien können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="58ab6-125">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="58ab6-126">Dateien an Speicherorten, die sich *nicht* in vom Benutzer beschreibbaren Verzeichnissen befinden, dürfen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="58ab6-126">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="58ab6-127">Dateien werden von einem [vertrauenswürdigen Signaturer](#signer-requests)signiert.</span><span class="sxs-lookup"><span data-stu-id="58ab6-127">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="58ab6-128">Die meisten von Microsoft signierten Dateien werden ausgeführt, einige werden jedoch blockiert, um Aktionen wie Codekompilierung mit hohem Risiko zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="58ab6-128">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="58ab6-129">Wenn ein anderer Benutzer als ein Administrator eine APP oder ein Skript einem Gerät hinzugefügt haben könnte (das heißt, es befindet sich in einem Benutzer schreibfähigen Verzeichnis), lässt es sich nicht ausführen, es sei denn, es wurde bereits von einem Administrator ausdrücklich zugelassen.</span><span class="sxs-lookup"><span data-stu-id="58ab6-129">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="58ab6-130">Wenn ein Benutzer versucht, Schadsoftware zu installieren, wenn eine Sicherheitsanfälligkeit in einer APP, die der Benutzer ausführt, versucht, Schadsoftware zu installieren, oder wenn ein Benutzer absichtlich versucht, eine nicht autorisierte APP oder ein unbefugtes Skript auszuführen, wird die Ausführung unserer Richtlinie angehalten.</span><span class="sxs-lookup"><span data-stu-id="58ab6-130">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="58ab6-131">Signer-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58ab6-131">Signer requests</span></span>

<span data-ttu-id="58ab6-132">Sie informieren uns, welche apps von Softwareanbietern bereitgestellt werden, denen Sie Vertrauen, indem Sie eine *Signer-Anforderung*einreichen.</span><span class="sxs-lookup"><span data-stu-id="58ab6-132">You inform us of which apps are provided by software vendors you trust by filing a *signer request*.</span></span> <span data-ttu-id="58ab6-133">Auf diese Weise fügen wir diese Vertrauensinformationen in die Baseline-anwendungssteuerungsrichtlinie ein und erlauben, dass alle mit dem Zertifikat des Herausgebers signierte Software auf Ihren Geräten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="58ab6-133">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="58ab6-134">Überwachen und Erzwingen von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="58ab6-134">Audit and Enforced policies</span></span>

<span data-ttu-id="58ab6-135">Microsoft Managed Desktop verwendet zwei Microsoft InTune-Richtlinien, um die APP-Steuerung bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="58ab6-135">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="58ab6-136">Überwachungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="58ab6-136">Audit policy</span></span>
<span data-ttu-id="58ab6-137">Mit dieser Richtlinie werden Protokolle erstellt, um festzuhalten, ob eine APP oder ein Skript durch die erzwungene Richtlinie blockiert würde.</span><span class="sxs-lookup"><span data-stu-id="58ab6-137">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="58ab6-138">Überwachungsrichtlinien erzwingen keine app-Steuerelement Regeln und dienen zu Testzwecken, um zu ermitteln, ob für eine Anwendung eine Ausnahme Herausgeber erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="58ab6-138">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="58ab6-139">Warnungen (8003-oder 8006-Ereignisse) werden in der Ereignisanzeige protokolliert, anstatt die Ausführung oder Installation bestimmter Apps oder Skripts zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="58ab6-139">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="58ab6-140">Erzwungene Richtlinie</span><span class="sxs-lookup"><span data-stu-id="58ab6-140">Enforced policy</span></span>
<span data-ttu-id="58ab6-141">Durch diese Richtlinie wird verhindert, dass nicht vertrauenswürdige apps und Skripts gestartet werden, und es werden Protokolle erstellt, wenn eine APP oder ein Skript blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="58ab6-141">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="58ab6-142">Erzwungene Richtlinien verhindern, dass Standardbenutzer Apps oder Skripts ausführen können, die in Benutzer schreibbaren Verzeichnissen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="58ab6-142">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="58ab6-143">Für Geräte in der Test Gruppe wird eine Überwachungsrichtlinie angewendet, sodass Sie Sie verwenden können, um zu überprüfen, ob Anwendungen Probleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="58ab6-143">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="58ab6-144">Alle anderen Gruppen (zuerst, schnell und breit) verwenden eine erzwungene Richtlinie, sodass Endbenutzer in diesen Gruppen keine nicht vertrauenswürdigen Apps oder Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="58ab6-144">All other groups (First, Fast, and Broad) use an Enforced policy, so end users in those groups won't be able to run untrusted apps or scripts.</span></span>







