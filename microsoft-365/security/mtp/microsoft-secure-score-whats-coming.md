---
title: Was kommt mit Microsoft Secure Score
description: Beschreibt, welche neuen Änderungen an Microsoft Secure Score im Microsoft 365 Security Center vorgenommen werden.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, Microsoft 365 Security Center, Improvement Actions
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779248"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="6527e-104">Was kommt mit Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="6527e-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6527e-105">Wir nehmen in naher Zukunft einige Änderungen vor, um [Microsoft Secure Score](microsoft-secure-score.md) zu einem besseren Vertreter ihrer Sicherheitsposition zu machen und die Benutzerfreundlichkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="6527e-105">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="6527e-106">Ihre Punktzahl und die maximal mögliche Punktzahl können sich ändern.</span><span class="sxs-lookup"><span data-stu-id="6527e-106">Your score and the maximum possible score may change.</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="6527e-107">Vorgeschlagene Änderungen</span><span class="sxs-lookup"><span data-stu-id="6527e-107">Proposed changes</span></span>

### <a name="november-2020"></a><span data-ttu-id="6527e-108">November 2020</span><span class="sxs-lookup"><span data-stu-id="6527e-108">November 2020</span></span>

<span data-ttu-id="6527e-109">Das Entfernen der Möglichkeit, ServiceNow-Tickets über Secure Score zu erstellen, erhalten Sie, indem Sie **> ServiceNow freigeben** .</span><span class="sxs-lookup"><span data-stu-id="6527e-109">Removing the ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** .</span></span>

- <span data-ttu-id="6527e-110">Der Vorschauzeitraum für den ServiceNow-Konnektor wird enden.</span><span class="sxs-lookup"><span data-stu-id="6527e-110">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="6527e-111">Diese Funktion ist Ende 2020 nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6527e-111">This capability will no longer available by the end of 2020.</span></span> <span data-ttu-id="6527e-112">Vielen Dank für Ihr Feedback und den weiteren Support, während wir die nächsten Schritte bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6527e-112">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="6527e-113">Hinzufügen von 18 Verbesserungs Aktionen im Zusammenhang mit Microsoft Defender für Endpoint (zuvor Microsoft Defender ATP):</span><span class="sxs-lookup"><span data-stu-id="6527e-113">Adding 18 improvement actions related to Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

<span data-ttu-id="6527e-114">Empfehlungen zur Angriffsflächen Reduzierung (ASR):</span><span class="sxs-lookup"><span data-stu-id="6527e-114">Attack Surface Reduction (ASR) related recommendations:</span></span>
- <span data-ttu-id="6527e-115">Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren</span><span class="sxs-lookup"><span data-stu-id="6527e-115">Block executable content from email client and webmail</span></span>
- <span data-ttu-id="6527e-116">Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern</span><span class="sxs-lookup"><span data-stu-id="6527e-116">Block all Office applications from creating child processes</span></span>
- <span data-ttu-id="6527e-117">Office-Anwendungen am Erstellen ausführbarer Inhalte hindern</span><span class="sxs-lookup"><span data-stu-id="6527e-117">Block Office applications from creating executable content</span></span>
- <span data-ttu-id="6527e-118">Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern</span><span class="sxs-lookup"><span data-stu-id="6527e-118">Block Office applications from injecting code into other processes</span></span>
- <span data-ttu-id="6527e-119">JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern</span><span class="sxs-lookup"><span data-stu-id="6527e-119">Block JavaScript or VBScript from launching downloaded executable content</span></span>
- <span data-ttu-id="6527e-120">Ausführung potenziell verborgener Skripts blockieren</span><span class="sxs-lookup"><span data-stu-id="6527e-120">Block execution of potentially obfuscated scripts</span></span>
- <span data-ttu-id="6527e-121">Win32-API-Aufrufe von Office-Makros blockieren</span><span class="sxs-lookup"><span data-stu-id="6527e-121">Block Win32 API calls from Office macros</span></span>
- <span data-ttu-id="6527e-122">Ausführbare Dateien an der Ausführung hindern, außer sie erfüllen ein Verbreitungs-, Alters- oder vertrauenswürdige Listen-Kriterium</span><span class="sxs-lookup"><span data-stu-id="6527e-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
- <span data-ttu-id="6527e-123">Erweiterten Schutz vor Ransomware verwenden</span><span class="sxs-lookup"><span data-stu-id="6527e-123">Use advanced protection against ransomware</span></span>
- <span data-ttu-id="6527e-124">Diebstahl von Anmeldeinformationen aus dem Subsystem für die lokale Sicherheitsautorität (lsass.exe) blockieren</span><span class="sxs-lookup"><span data-stu-id="6527e-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
- <span data-ttu-id="6527e-125">Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren</span><span class="sxs-lookup"><span data-stu-id="6527e-125">Block process creations originating from PSExec and WMI commands</span></span>
- <span data-ttu-id="6527e-126">Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren</span><span class="sxs-lookup"><span data-stu-id="6527e-126">Block untrusted and unsigned processes that run from USB</span></span>
- <span data-ttu-id="6527e-127">Office-Kommunikationsanwendung am Erstellen von untergeordneten Prozessen hindern</span><span class="sxs-lookup"><span data-stu-id="6527e-127">Block Office communication application from creating child processes</span></span>
- <span data-ttu-id="6527e-128">Adobe Reader am Erstellen von untergeordneten Prozessen hindern</span><span class="sxs-lookup"><span data-stu-id="6527e-128">Block Adobe Reader from creating child processes</span></span>
- <span data-ttu-id="6527e-129">Persistenz durch WMI-Ereignisabonnement blockieren</span><span class="sxs-lookup"><span data-stu-id="6527e-129">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="6527e-130">Empfehlungen zu Diensten:</span><span class="sxs-lookup"><span data-stu-id="6527e-130">Services related recommendations:</span></span>
- <span data-ttu-id="6527e-131">Unzitierten Dienstpfad für Windows-Dienste reparieren</span><span class="sxs-lookup"><span data-stu-id="6527e-131">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="6527e-132">Ändern des ausführbaren Pfads des Diensts in einen allgemeinen geschützten Speicherort</span><span class="sxs-lookup"><span data-stu-id="6527e-132">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="6527e-133">Ändern des Dienstkontos, um das zwischengespeicherte Kennwort in der Windows-Registrierung zu vermeiden</span><span class="sxs-lookup"><span data-stu-id="6527e-133">Change service account to avoid cached password in windows registry</span></span>

## <a name="related-resources"></a><span data-ttu-id="6527e-134">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6527e-134">Related resources</span></span>

- [<span data-ttu-id="6527e-135">Microsoft Secure Score (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="6527e-135">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="6527e-136">Zugreifen auf Ihren Sicherheitsstatus</span><span class="sxs-lookup"><span data-stu-id="6527e-136">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="6527e-137">Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele</span><span class="sxs-lookup"><span data-stu-id="6527e-137">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="6527e-138">Neuigkeiten</span><span class="sxs-lookup"><span data-stu-id="6527e-138">What's new</span></span>](microsoft-secure-score-whats-new.md)
