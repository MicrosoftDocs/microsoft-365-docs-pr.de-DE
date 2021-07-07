---
title: Häufig gestellte Fragen zur Testbasis
description: Häufig gestellte Fragen überprüfen
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322926"
---
# <a name="test-base-faq"></a><span data-ttu-id="78284-103">Häufig gestellte Fragen zur Testbasis</span><span class="sxs-lookup"><span data-stu-id="78284-103">Test Base FAQ</span></span>

<span data-ttu-id="78284-104">**F: Wie übermitteln wir unsere Pakete an das Testbasisteam?**</span><span class="sxs-lookup"><span data-stu-id="78284-104">**Q: How do we submit our packages to Test Base team?**</span></span>

<span data-ttu-id="78284-105">**A:** Übermitteln Sie Ihre Pakete direkt an die Testbasisumgebung über unser Self-Serve-Portal.</span><span class="sxs-lookup"><span data-stu-id="78284-105">**A:** Submit your packages directly to the Test Base environment using our self-serve portal.</span></span>

<span data-ttu-id="78284-106">Um Ihr Anwendungspaket zu übermitteln, navigieren Sie zum [Azure-Portal,](https://www.aka.ms/testbaseportal "Homepage der Testbasis") und laden Sie einen gezippten Ordner mit den Binärdateien, Abhängigkeiten und Testskripts Ihrer Anwendung über das Dashboard des Self-Serve-Testbasisportals hoch.</span><span class="sxs-lookup"><span data-stu-id="78284-106">To submit your application package, navigate to the [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") and upload a zipped folder containing your application's binaries, dependencies, and test scripts via the self-serve Test Base portal dashboard.</span></span> 

<span data-ttu-id="78284-107">Weitere Informationen finden Sie im Onboarding-Benutzerhandbuch, oder wenden Sie sich an unser Team, um Unterstützung und weitere Informationen zu <testbasepreview@microsoft.com> erhalten.</span><span class="sxs-lookup"><span data-stu-id="78284-107">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="78284-108">**F: Was sind Out-of-Box (OOB)-Tests?**</span><span class="sxs-lookup"><span data-stu-id="78284-108">**Q: What are Out-of-box (OOB) tests?**</span></span>

<span data-ttu-id="78284-109">**A:** Out-of-Box (OOB)-Tests sind standardisiert, Standardtestläufe, bei denen Anwendungspakete installiert, gestartet und 30 Mal geschlossen und dann deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="78284-109">**A:** Out-of-box (OOB) tests are standardized, default test runs where application packages are installed, launched and closed thirty (30) times, and then uninstalled.</span></span> 

<span data-ttu-id="78284-110">Die für Test Base erstellten Pakete verfügen über die folgenden Testskripts: Installieren, Starten, Schließen und optional das Deinstallationsskript.</span><span class="sxs-lookup"><span data-stu-id="78284-110">The packages created for Test Base will have the following test scripts: install, launch, close, and optionally the uninstall script.</span></span> 

<span data-ttu-id="78284-111">Die Out-of-Box (OOB)-Tests bieten Ihnen standardisierte Telemetriedaten für Ihre Anwendung, die sie in Windows Builds vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="78284-111">The Out-of-box (OOB) tests provide you with standardized telemetry on your application to compare across Windows builds.</span></span>

<span data-ttu-id="78284-112">**F: Können tests außerhalb der Out-of-Box-Tests (Installieren, Starten, Schließen, Deinstallieren von Testskripts) eingereicht werden?**</span><span class="sxs-lookup"><span data-stu-id="78284-112">**Q: Can we submit tests outside of the Out-of-box tests (install, launch, close, uninstall test scripts)?**</span></span>

<span data-ttu-id="78284-113">**A:** Ja, Kunden können Anwendungspakete für **Funktionstests** auch über das Dashboard des Self-Serve-Portals hochladen.</span><span class="sxs-lookup"><span data-stu-id="78284-113">**A:** Yes, customers can also upload application packages for **functional tests** via the self-serve portal dashboard.</span></span>
<span data-ttu-id="78284-114">**Funktionstests** sind Tests, mit denen Kunden ihre Skripts ausführen können, um benutzerdefinierte Funktionen für ihre Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="78284-114">**Functional tests** are tests that enable customers execute their scripts to run custom functionality on their application.</span></span>


## <a name="testing"></a><span data-ttu-id="78284-115">Testen</span><span class="sxs-lookup"><span data-stu-id="78284-115">Testing</span></span>

<span data-ttu-id="78284-116">**F: Unterstützen Sie Funktionstests?**</span><span class="sxs-lookup"><span data-stu-id="78284-116">**Q: Do you support functional tests?**</span></span>

<span data-ttu-id="78284-117">**A:** Ja, Test Base unterstützt Funktionstests.</span><span class="sxs-lookup"><span data-stu-id="78284-117">**A:** Yes, Test Base supports functional tests.</span></span> <span data-ttu-id="78284-118">Funktionstests sind Tests, die es unseren Kunden ermöglichen, ihre Skripts auszuführen, um benutzerdefinierte Funktionen für ihre Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="78284-118">Functional tests are tests that enable our customers execute their scripts to run custom functionality on their application.</span></span> 

<span data-ttu-id="78284-119">Um Ihr Anwendungspaket für Funktionstests zu übermitteln, laden Sie einfach den gezippten Ordner mit den Binärdateien, Abhängigkeiten und Testskripts Ihrer Anwendung über unser Self-Serve-Portaldashboard hoch.</span><span class="sxs-lookup"><span data-stu-id="78284-119">To submit your application package for functional testing, simply upload the zipped folder containing your application's binaries, dependencies, and test scripts via our self-serve portal dashboard.</span></span> 

<span data-ttu-id="78284-120">Weitere Informationen finden Sie im Onboarding-Benutzerhandbuch, oder wenden Sie sich an unser Team, um Unterstützung und weitere Informationen zu <testbasepreview@microsoft.com> erhalten.</span><span class="sxs-lookup"><span data-stu-id="78284-120">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="78284-121">**F: Wie behandelt test Base unsere Testdaten?**</span><span class="sxs-lookup"><span data-stu-id="78284-121">**Q: How does Test Base handle our test data?**</span></span>

<span data-ttu-id="78284-122">**A:** Test Base sammelt und verwaltet Ihre Testdaten sicher in der Azure-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="78284-122">**A:** Test Base securely collects and manages your test data on the Azure environment.</span></span> 

<span data-ttu-id="78284-123">**F: Kann die Testbasis unsere automatisierten Tests unterstützen?**</span><span class="sxs-lookup"><span data-stu-id="78284-123">**Q: Can Test Base support our automated tests?**</span></span>

<span data-ttu-id="78284-124">Ja, Test Base unterstützt automatisierte Tests, aber aufgrund von Dienstfunktionen unterstützen wir derzeit keine manuellen Tests.</span><span class="sxs-lookup"><span data-stu-id="78284-124">Yes, Test Base supports automated tests however, we do not support manual tests at this time due to service capabilities.</span></span>

<span data-ttu-id="78284-125">**F: Welche Sprachen und Frameworks automatisierter Tests werden unterstützt?**</span><span class="sxs-lookup"><span data-stu-id="78284-125">**Q: What languages and frameworks of automated tests do you support?**</span></span>

<span data-ttu-id="78284-126">**A:** Wir unterstützen alle Sprachen und Frameworks.</span><span class="sxs-lookup"><span data-stu-id="78284-126">**A:** We support all languages and frameworks.</span></span> <span data-ttu-id="78284-127">Wir rufen alle Skripts über PowerShell auf.</span><span class="sxs-lookup"><span data-stu-id="78284-127">We invoke all scripts through PowerShell.</span></span> 

<span data-ttu-id="78284-128">Sie müssen auch die abhängigen Binärdateien des erforderlichen Frameworks bereitstellen (hochladen).</span><span class="sxs-lookup"><span data-stu-id="78284-128">You will also need to provide (upload) the dependent binaries of the required framework.</span></span>

<span data-ttu-id="78284-129">**F: Wie bald liefert Testbasis Testergebnisse?**</span><span class="sxs-lookup"><span data-stu-id="78284-129">**Q: How soon does Test Base provide test results?**</span></span>

<span data-ttu-id="78284-130">**A:** Für jeden Test, den wir für die Vorabversionen ausführen, stellen wir innerhalb von 48 Stunden Ergebnisse auf Ihrem [Azure Portal-Dashboard](https://www.aka.ms/testbaseportal "Homepage der Testbasis") bereit.</span><span class="sxs-lookup"><span data-stu-id="78284-130">**A:** For each test that we run against the pre-release builds, we will provide results within 48 hours on your [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") dashboard.</span></span>

<span data-ttu-id="78284-131">**F: Können Sie nach der Installation neu starten?**</span><span class="sxs-lookup"><span data-stu-id="78284-131">**Q: Can you reboot after install?**</span></span>

<span data-ttu-id="78284-132">**A:** Ja, unser Prozess unterstützt den Neustart nach der Installation.</span><span class="sxs-lookup"><span data-stu-id="78284-132">**A:** Yes, our process supports rebooting after installation.</span></span> <span data-ttu-id="78284-133">Achten Sie darauf, diese Option in der Dropdownliste "Optionale Einstellungen" auszuwählen, wenn Sie Ihre **Aufgaben** im Onboardingportal festlegen.</span><span class="sxs-lookup"><span data-stu-id="78284-133">Be sure to select this option from the “Optional settings” drop list when setting your **Tasks** on the onboarding portal.</span></span>

<span data-ttu-id="78284-134">Für Out-of-Box (OOB)-Tests können Sie angeben, ob für das Installationsskript ein Neustart erforderlich _ist._</span><span class="sxs-lookup"><span data-stu-id="78284-134">For Out-of-box (OOB) tests, you can specify whether a reboot is needed for the _Install script._</span></span>

![Bild "Neustart"](Media/reboot.png)

<span data-ttu-id="78284-136">Bei Funktionstests können Sie angeben, ob für jedes hinzugefügte Skript ein Neustart erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="78284-136">While for functional tests, you can specify whether a reboot is required for each script that is added.</span></span>

![Auswählen von Funktionstests](Media/functionalreboot.png)

<span data-ttu-id="78284-138">**F: Welche Windows Versionen unterstützen Sie?**</span><span class="sxs-lookup"><span data-stu-id="78284-138">**Q: What Windows versions do you support?**</span></span>

<span data-ttu-id="78284-139">**A:** Derzeit unterstützen wir Windows 10 Clients, Windows Server 2016, Windows Server 2016 Core-Version, Windows Server 2019 und Windows Server 2019 Core-Version.</span><span class="sxs-lookup"><span data-stu-id="78284-139">**A:** We currently support Windows 10 clients, Windows Server 2016, Windows Server 2016 Core version, Windows Server 2019, and Windows Server 2019 Core version.</span></span>

<span data-ttu-id="78284-140">**F: Was ist der Unterschied zwischen Sicherheitsupdatetests und Funktionsupdatetests?**</span><span class="sxs-lookup"><span data-stu-id="78284-140">**Q: What is the difference between Security Update tests and Feature Update tests?**</span></span>

<span data-ttu-id="78284-141">**A:** Bei Sicherheitsupdatetests testen wir die **<ins>monatlichen Pre-Release-Sicherheitsupdates</ins>** auf Windows, die darauf ausgerichtet sind, unsere Benutzer immer sicher und geschützt zu halten.</span><span class="sxs-lookup"><span data-stu-id="78284-141">**A:** For Security update tests, we test against the **<ins>monthly pre-release security updates</ins>** on Windows which are focused on keeping our users always secure and protected.</span></span> <span data-ttu-id="78284-142">Für die Featureupdatetests testen wir die **<ins>zweijährlichen Vorabversionsfeatureupdates,</ins>** mit denen neue Features und Funktionen für Windows eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="78284-142">For the Feature update tests, we test against the **<ins>bi-annual pre-release feature updates</ins>** which introduces new features and capabilities on Windows.</span></span>

## <a name="debugging-options"></a><span data-ttu-id="78284-143">Debugoptionen</span><span class="sxs-lookup"><span data-stu-id="78284-143">Debugging options</span></span>

<span data-ttu-id="78284-144">**F: Erhalten wir Zugriff auf die virtuellen Computer (VMs) bei Fehlern? Was teilt testbasis?**</span><span class="sxs-lookup"><span data-stu-id="78284-144">**Q: Do we get access to the Virtual Machines (VMs) in case of failures? What does Test Base share?**</span></span>

<span data-ttu-id="78284-145">**A:** Damit der Dienst kompatibel ist und die Vorabversionsupdates sicher sind, hat nur Microsoft Zugriff auf die virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="78284-145">**A:** For the service to be compliant and the pre-release updates be secure, only Microsoft has access to the VMs.</span></span> <span data-ttu-id="78284-146">Kunden können jedoch Testergebnisse und andere Testmetriken auf ihrem Portal-Dashboard anzeigen, einschließlich Crash- und Hang-Signalen, Zuverlässigkeitsmetriken, Arbeitsspeicher- und CPU-Auslastung usw. Außerdem generieren und stellen wir Protokolle von Testläufen auf dem Dashboard zum Herunterladen und zur weiteren Analyse bereit.</span><span class="sxs-lookup"><span data-stu-id="78284-146">However, customers can view test results and other test metrics on their portal dashboard, including crash and hang signals, reliability metrics, memory and CPU utilization etc. We also generate and provide logs of test runs on the dashboard for download and further analysis.</span></span> 

<span data-ttu-id="78284-147">Wir können bei Bedarf auch Speicherabbilder für das Absturzdebugging bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="78284-147">We can also provide memory dumps for crash debugging as needed.</span></span>

<span data-ttu-id="78284-148">**F: Was sind die nächsten Schritte, um diese Probleme zu beheben, wenn während der Tests Probleme gefunden werden?**</span><span class="sxs-lookup"><span data-stu-id="78284-148">**Q: If there are issues found during the testing, what are the next steps to resolve these issues?**</span></span>

<span data-ttu-id="78284-149">**A:** Das Testbasisteam führt einen anfänglichen Selektierungsprozess durch, um die Ursache des Fehlers zu ermitteln. Je nach unseren Ergebnissen werden wir dann zum Debuggen an den Kunden oder interne Teams in Microsoft weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="78284-149">**A:** The Test Base team will perform an initial triage process to determine the root cause of the error, and then depending on our findings, we will route to the customer or internal teams within Microsoft for debugging.</span></span> 

<span data-ttu-id="78284-150">Wir arbeiten bei der gemeinsamen Behebung von Problemen immer eng mit unseren Kunden zusammen.</span><span class="sxs-lookup"><span data-stu-id="78284-150">We always work closely with our customers in joint remediation to resolve any issues.</span></span> 

<span data-ttu-id="78284-151">**F: Hält Microsoft die Veröffentlichung des Sicherheitspatches bereit, bis das Problem behoben ist? Welche alternativen Auflösungen sind verfügbar?**</span><span class="sxs-lookup"><span data-stu-id="78284-151">**Q: Does Microsoft hold the release of the security patch until the issue is resolved? What alternate resolutions are available?**</span></span>

<span data-ttu-id="78284-152">**A:** Das Ziel von Test Base besteht darin, sicherzustellen, dass unsere gemeinsamen Endbenutzer keine Probleme haben.</span><span class="sxs-lookup"><span data-stu-id="78284-152">**A:** The goal of Test Base is to ensure our joint end customers do not face any issues.</span></span> <span data-ttu-id="78284-153">Wir werden hart mit Softwareanbietern zusammenarbeiten, um Probleme vor der Veröffentlichung zu beheben, aber für den Fall, dass die Korrektur nicht machbar ist, haben wir andere Lösungen wie Shims und Blöcke.</span><span class="sxs-lookup"><span data-stu-id="78284-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span></span>

## <a name="miscellaneous"></a><span data-ttu-id="78284-154">Sonstiges</span><span class="sxs-lookup"><span data-stu-id="78284-154">Miscellaneous</span></span>

<span data-ttu-id="78284-155">**F: Wie funktioniert der Dienst mit einem lokalen Server?**</span><span class="sxs-lookup"><span data-stu-id="78284-155">**Q: How will the service work with an on-prem server?**</span></span>

<span data-ttu-id="78284-156">**A:** Wir bieten derzeit keine Unterstützung für lokale Server.</span><span class="sxs-lookup"><span data-stu-id="78284-156">**A:** We currently do not provide support for on-prem servers.</span></span> <span data-ttu-id="78284-157">Wenn der Server jedoch den HTTP-Endpunkt verfügbar macht, können wir eine Verbindung über das Internet herstellen.</span><span class="sxs-lookup"><span data-stu-id="78284-157">However, if the server is exposing HTTP endpoint, we can connect to it over the internet.</span></span>

<span data-ttu-id="78284-158">**F: Wer hostet die virtuellen Computer?**</span><span class="sxs-lookup"><span data-stu-id="78284-158">**Q: Who hosts the VMs?**</span></span>

<span data-ttu-id="78284-159">**A:** Microsoft stellt den virtuellen Computer für diesen Dienst bereit und übernimmt dabei die Last des Kunden.</span><span class="sxs-lookup"><span data-stu-id="78284-159">**A:** Microsoft provisions the VM for this service, taking the load of doing so from the customer.</span></span>

<span data-ttu-id="78284-160">**F: Unterstützt dieser Dienst Web-, Mobil- oder Desktopanwendungen?**</span><span class="sxs-lookup"><span data-stu-id="78284-160">**Q: Does this service support web, mobile, or desktop applications?**</span></span>

<span data-ttu-id="78284-161">**A:** Derzeit liegt unser Fokus auf Desktopanwendungen, wir haben jedoch pläne, Webanwendungen in der Zukunft zu integrieren, aber wir unterstützen derzeit keine mobilen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="78284-161">**A:** Currently, our focus is on desktop applications, however, we have plans to onboard web applications in the future, but we do not support mobile applications at this time.</span></span>

<span data-ttu-id="78284-162">**F: Was ist der Unterschied zwischen Test Base und INTUNEP?**</span><span class="sxs-lookup"><span data-stu-id="78284-162">**Q: What is the difference between Test Base and SUVP?**</span></span>

<span data-ttu-id="78284-163">**A:** Der größte Unterschied zwischen Test Base und WILLP besteht darin, dass unsere Partner ihre Anwendungen in die Testbasis-Azure-Umgebung integrieren, um die Überprüfung anhand von Vorabversionsupdates durchzuführen, anstatt die Tests selbst durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="78284-163">**A:** The biggest difference between Test Base and SUVP is that our partners onboard their applications onto the Test Base Azure environment for validation runs against pre-release updates instead of carrying out the tests themselves.</span></span> 

<span data-ttu-id="78284-164">Zusätzlich zum Testen von Sicherheitsupdates vor der Veröffentlichung unterstützen wir Tests von Vorabversionsfeatureupdates auf unserer Plattform.</span><span class="sxs-lookup"><span data-stu-id="78284-164">In addition to pre-release security updates testing, we support pre-release feature updates testing on our platform.</span></span> <span data-ttu-id="78284-165">Wir haben viele andere Arten von Updates und Betriebssystemtests auf unserer Roadmap.</span><span class="sxs-lookup"><span data-stu-id="78284-165">We have many other types of updates and OS testing on our roadmap.</span></span>

<span data-ttu-id="78284-166">**F: Gibt es Kosten, die mit dem Dienst verbunden sind?**</span><span class="sxs-lookup"><span data-stu-id="78284-166">**Q: Is there a cost associated with the service?**</span></span>

<span data-ttu-id="78284-167">**A:** Der Testbasisdienst steht Benutzern bis zur allgemeinen Verfügbarkeit (Ga) kostenlos zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="78284-167">**A:** The Test Base service will be free to users until General Availability (GA).</span></span> <span data-ttu-id="78284-168">Zu diesem Zeitpunkt werden wir eine Kostenstruktur ankündigen, die für alle Kunden wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="78284-168">At that time, we will announce a cost structure that will be in effect for all customers.</span></span> 

<span data-ttu-id="78284-169">**F: Wie kann ich Feedback zur Testbasis geben?**</span><span class="sxs-lookup"><span data-stu-id="78284-169">**Q: How can I provide feedback about Test Base?**</span></span>

<span data-ttu-id="78284-170">**A:** Um Ihr Feedback zur Testbasis zu teilen, wählen Sie das **Feedbacksymbol** unten links im Portal aus.</span><span class="sxs-lookup"><span data-stu-id="78284-170">**A:** To share your feedback about Test Base, select the **Feedback** icon at the bottom left of the portal.</span></span> <span data-ttu-id="78284-171">Fügen Sie einen Screenshot in Ihre Übermittlung ein, damit Microsoft Ihr Feedback besser verstehen kann.</span><span class="sxs-lookup"><span data-stu-id="78284-171">Include a screenshot with your submission to help Microsoft better understand your feedback.</span></span> 

<span data-ttu-id="78284-172">Sie können auch Produktvorschläge übermitteln und andere Ideen auf der Website <testbasepreview@microsoft.com> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="78284-172">You can also submit product suggestions and upvote other ideas at <testbasepreview@microsoft.com>.</span></span>
