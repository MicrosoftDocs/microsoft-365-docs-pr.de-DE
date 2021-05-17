---
title: App-Steuerung
description: Verwenden von App-Steuerelementen und -Vertrauensstellungen mit Anwendungen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841303"
---
# <a name="app-control"></a><span data-ttu-id="a55b2-104">App-Steuerung</span><span class="sxs-lookup"><span data-stu-id="a55b2-104">App control</span></span>

<span data-ttu-id="a55b2-105">Die App-Steuerung ist eine optionale Sicherheitspraxis in Microsoft Managed Desktop, die die Ausführung von Code auf Clientgeräten einschränkt.</span><span class="sxs-lookup"><span data-stu-id="a55b2-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="a55b2-106">Dieses Steuerelement verringert das Risiko von Schadsoftware oder bösartigen Skripts, indem nur Code ausgeführt werden darf, der von einer vom Kunden genehmigten Liste von Herausgebern signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a55b2-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="a55b2-107">Dieses Steuerelement bietet zahlreiche Sicherheitsvorteile, zielt jedoch in erster Linie auf den Schutz von Daten und Identität vor clientbasierten Exploits ab.</span><span class="sxs-lookup"><span data-stu-id="a55b2-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="a55b2-108">Microsoft Managed Desktop vereinfacht die Verwaltung von App-Steuerelementrichtlinien, indem eine Basisrichtlinie erstellt wird, die zentrale Produktivitätsszenarien ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a55b2-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="a55b2-109">Sie können die Vertrauensstellung auf andere Signierer erweitern, die für die Apps und Skripts in Ihrer Umgebung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="a55b2-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="a55b2-110">Jede Sicherheitstechnologie erfordert ein Gleichgewicht zwischen Benutzererfahrung, Sicherheit und Kosten.</span><span class="sxs-lookup"><span data-stu-id="a55b2-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="a55b2-111">Die App-Steuerung reduziert die Bedrohung durch schadsoftware in Ihrer Umgebung, es gibt jedoch Folgen für den Benutzer und weitere Aktionen für Ihren IT-Administrator.</span><span class="sxs-lookup"><span data-stu-id="a55b2-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="a55b2-112">**Zusätzliche Sicherheit:**</span><span class="sxs-lookup"><span data-stu-id="a55b2-112">**Additional security:**</span></span>

<span data-ttu-id="a55b2-113">Apps oder Skripts, denen die App-Steuerelementrichtlinie nicht vertraut, können nicht auf Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a55b2-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="a55b2-114">**Ihre zusätzlichen Verantwortlichkeiten:**</span><span class="sxs-lookup"><span data-stu-id="a55b2-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="a55b2-115">Sie sind für das Testen Ihrer Apps verantwortlich, um zu ermitteln, ob sie von der Anwendungssteuerungsrichtlinie blockiert würden.</span><span class="sxs-lookup"><span data-stu-id="a55b2-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="a55b2-116">Wenn eine App blockiert ist (oder wäre), sind Sie dafür verantwortlich, die erforderlichen Signierdetails zu identifizieren und eine Änderung über das Administratorportal anfordern.</span><span class="sxs-lookup"><span data-stu-id="a55b2-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="a55b2-117">**Microsoft Managed Desktop Verantwortlichkeiten:**</span><span class="sxs-lookup"><span data-stu-id="a55b2-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="a55b2-118">Microsoft Managed Desktop verwaltet die Basisrichtlinie, die wichtige Microsoft-Produkte wie M365 Apps, Windows, Teams, OneDrive und so weiter ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a55b2-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="a55b2-119">Microsoft Managed Desktop werden Ihre vertrauenswürdigen Signierer eingefügt und die aktualisierte Richtlinie auf Ihren Geräten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a55b2-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="a55b2-120">Verwalten von Vertrauensstellungen in Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a55b2-120">Managing trust in applications</span></span>

<span data-ttu-id="a55b2-121">Microsoft Managed Desktop eine Basisrichtlinie, die den Kernkomponenten von Microsoft-Technologien vertraut.</span><span class="sxs-lookup"><span data-stu-id="a55b2-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="a55b2-122">Anschließend fügen Sie *Vertrauen* für Ihre eigenen Anwendungen und Skripts hinzu, indem Sie Microsoft Managed Desktop denen Sie bereits vertrauen.</span><span class="sxs-lookup"><span data-stu-id="a55b2-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="a55b2-123">Basisrichtlinie</span><span class="sxs-lookup"><span data-stu-id="a55b2-123">Base policy</span></span>

<span data-ttu-id="a55b2-124">Microsoft Managed Desktop erstellt und verwaltet in Zusammenarbeit mit Microsoft Cybersecurity-Experten eine Standardrichtlinie, die die meisten über Microsoft Intune bereitgestellten Apps ermöglicht und gleichzeitig gefährliche Aktivitäten wie die Codekompilierung oder Ausführung nicht vertrauenswürdiger Dateien blockiert.</span><span class="sxs-lookup"><span data-stu-id="a55b2-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="a55b2-125">Die Basisrichtlinie verfolgt den folgenden Ansatz zum Einschränken der Softwareausführung:</span><span class="sxs-lookup"><span data-stu-id="a55b2-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="a55b2-126">Von Administratoren ausgeführte Dateien können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a55b2-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="a55b2-127">Dateien an Speicherorten, *die* sich nicht in beschreibbaren Verzeichnissen befinden, können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a55b2-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="a55b2-128">Dateien werden von einem vertrauenswürdigen [Signier signiert.](#signer-requests)</span><span class="sxs-lookup"><span data-stu-id="a55b2-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="a55b2-129">Die meisten von Microsoft signierten Dateien werden ausgeführt, einige werden jedoch blockiert, um aktionen mit hohem Risiko wie die Codekompilierung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="a55b2-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="a55b2-130">Wenn ein anderer Benutzer als ein Administrator einem Gerät eine App oder ein Skript hinzugefügt haben könnte (d. h. es befindet sich in einem benutzerschreibbaren Verzeichnis), wird die Ausführung nicht zugelassen, es sei denn, es wurde bereits ausdrücklich von einem Administrator zugelassen.</span><span class="sxs-lookup"><span data-stu-id="a55b2-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="a55b2-131">Wenn ein Benutzer versucht, Schadsoftware zu installieren, wenn eine Sicherheitslücke in einer App, die der Benutzer ausgeführt hat, versucht, Schadsoftware zu installieren, oder wenn ein Benutzer absichtlich versucht, eine nicht autorisierte App oder ein nicht autorisiertes Skript auszuführen, wird die Ausführung durch unsere Richtlinie beendet.</span><span class="sxs-lookup"><span data-stu-id="a55b2-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="a55b2-132">Signeranforderungen</span><span class="sxs-lookup"><span data-stu-id="a55b2-132">Signer requests</span></span>

<span data-ttu-id="a55b2-133">Sie informieren uns darüber, welche Apps von Softwareherausgebern bereitgestellt werden, denen Sie vertrauen, indem Sie eine *Signieranforderung einreichen.*</span><span class="sxs-lookup"><span data-stu-id="a55b2-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="a55b2-134">Auf diese Weise fügen wir diese Vertrauensinformationen der Basisanwendungssteuerungsrichtlinie hinzu und ermöglichen die Ausführung von Software, die mit dem Zertifikat dieses Herausgebers signiert ist, auf Ihren Geräten.</span><span class="sxs-lookup"><span data-stu-id="a55b2-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="a55b2-135">Überwachungs- und Erzwungene Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a55b2-135">Audit and Enforced policies</span></span>

<span data-ttu-id="a55b2-136">Microsoft Managed Desktop verwendet zwei Microsoft Intune, um die App-Steuerung zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="a55b2-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="a55b2-137">Überwachungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="a55b2-137">Audit policy</span></span>
<span data-ttu-id="a55b2-138">Diese Richtlinie erstellt Protokolle, um zu erfassen, ob eine App oder ein Skript von der Richtlinie Erzwungen blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="a55b2-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="a55b2-139">Überwachungsrichtlinien erzwingen keine Regeln für die App-Kontrolle und dienen zu Testzwecken, um zu ermitteln, ob für eine Anwendung eine Herausgeberfreistellung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a55b2-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="a55b2-140">Es protokolliert Warnungen (8003- oder 8006-Ereignisse) in der Ereignisanzeige, anstatt die Ausführung oder Installation von angegebenen Apps oder Skripts zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="a55b2-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="a55b2-141">Erzwungene Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a55b2-141">Enforced policy</span></span>
<span data-ttu-id="a55b2-142">Diese Richtlinie blockiert die Ausführung nicht vertrauenswürdiger Apps und Skripts und erstellt Protokolle, sobald eine App oder ein Skript blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="a55b2-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="a55b2-143">Erzwungene Richtlinien verhindern, dass Standardbenutzer Apps oder Skripts ausführen, die in beschreibbaren Verzeichnissen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a55b2-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="a55b2-144">Auf Geräten in der Testgruppe wird eine Überwachungsrichtlinie angewendet, damit Sie überprüfen können, ob Anwendungen Probleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="a55b2-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="a55b2-145">Alle anderen Gruppen (First, Fast und Broad) verwenden eine Erzwungene Richtlinie, sodass Benutzer in diesen Gruppen nicht vertrauenswürdige Apps oder Skripts nicht ausführen können.</span><span class="sxs-lookup"><span data-stu-id="a55b2-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







