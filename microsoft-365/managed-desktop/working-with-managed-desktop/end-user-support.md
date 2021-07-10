---
title: Anfordern von Benutzersupport für Microsoft Managed Desktop
description: Wie Benutzer Hilfe zum Dienst und den Geräten erhalten können
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362606"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="167be-104">Hilfe für Benutzer</span><span class="sxs-lookup"><span data-stu-id="167be-104">Getting help for users</span></span>

<span data-ttu-id="167be-105">Wenn Sie den Punkt im [Workflow](../service-description/user-support.md) erreicht haben, an dem Sie erhöhten Gerätezugriff oder eine Eskalation an Microsoft anfordern müssen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="167be-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="167be-106">Diese Supportoptionen sind für Geräte in der Testgruppe nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="167be-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="167be-107">Anforderungen für erhöhte Rechte</span><span class="sxs-lookup"><span data-stu-id="167be-107">Elevation requests</span></span>

<span data-ttu-id="167be-108">Bevor Sie erhöhten Zugriff auf ein Gerät anfordern, sollten Sie überprüfen, welche Aktionen am besten geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="167be-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="167be-109">**Typische Aktionen** sind das, wofür dieser Prozess vorgesehen ist und routinemäßig ausgeführt werden würde, während Probleme mit Microsoft Managed Desktop Geräten behoben werden.</span><span class="sxs-lookup"><span data-stu-id="167be-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="167be-110">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="167be-110">Examples include:</span></span>
    - <span data-ttu-id="167be-111">Erhöhen der integrierten Systemproblembehandlung, der Eingabeaufforderung oder Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="167be-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="167be-112">Problembehandlung bei Branchenanwendungen</span><span class="sxs-lookup"><span data-stu-id="167be-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="167be-113">Verwenden einer Problemumgehung zum Korrigieren eines Problems, das entwurfsbedingt funktionieren sollte (z. B. BitLocker-Aktivierung oder Nichtaktualisierung der Systemzeit)</span><span class="sxs-lookup"><span data-stu-id="167be-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="167be-114">Erhöhen des Geräte-Managers zum Aktualisieren von Treibern, Deinstallieren eines Geräts oder Suchen nach neuen Änderungen</span><span class="sxs-lookup"><span data-stu-id="167be-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="167be-115">**Aktionen, die nicht empfohlen werden, umfassen Folgendes:**</span><span class="sxs-lookup"><span data-stu-id="167be-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="167be-116">Installieren von Software oder Browsern</span><span class="sxs-lookup"><span data-stu-id="167be-116">Installing software or browsers</span></span>
    - <span data-ttu-id="167be-117">Installieren von Treibern außerhalb von Windows-Einstellungen, einschließlich treiber für Peripheriegeräte</span><span class="sxs-lookup"><span data-stu-id="167be-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="167be-118">Installieren .msi oder .exe Dateien</span><span class="sxs-lookup"><span data-stu-id="167be-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="167be-119">Installieren Windows Features</span><span class="sxs-lookup"><span data-stu-id="167be-119">Installing Windows features</span></span>

- <span data-ttu-id="167be-120">**Aktionen, die nicht unterstützt werden, umfassen Folgendes:**</span><span class="sxs-lookup"><span data-stu-id="167be-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="167be-121">Installieren von Software oder Features, die mit Microsoft Managed Desktop Sicherheits- oder Verwaltungsfunktionen oder -vorgängen in Konflikt geraten</span><span class="sxs-lookup"><span data-stu-id="167be-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="167be-122">Deaktivieren eines Windows Features, das für Microsoft Managed Desktop erforderlich ist, z. B. BitLocker</span><span class="sxs-lookup"><span data-stu-id="167be-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="167be-123">Ändern der von Ihrer Organisation verwalteten Einstellungen</span><span class="sxs-lookup"><span data-stu-id="167be-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="167be-124">So fordern Sie erhöhte Rechte an</span><span class="sxs-lookup"><span data-stu-id="167be-124">To request elevation</span></span>

1. <span data-ttu-id="167be-125">Wechseln Sie zum [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) Portal, und melden Sie sich mit Ihren Azure Active Directory-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="167be-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="167be-126">Wählen Sie **"Neue Rechteerweiterungsanforderung"** aus.</span><span class="sxs-lookup"><span data-stu-id="167be-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="167be-127">Geben Sie diese Details an:</span><span class="sxs-lookup"><span data-stu-id="167be-127">Provide these details:</span></span>
    - <span data-ttu-id="167be-128">**Supportticket-ID** von Ihrem eigenen Support-Ticketingsystem.</span><span class="sxs-lookup"><span data-stu-id="167be-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="167be-129">**Gerätename:** Geben Sie die Seriennummer des Geräts ein, und wählen Sie dann das Gerät aus dem Menü aus.</span><span class="sxs-lookup"><span data-stu-id="167be-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="167be-130">**Kategorie:** Wählen Sie die Kategorie aus, die am besten zu Ihrem Problem passt.</span><span class="sxs-lookup"><span data-stu-id="167be-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="167be-131">Wenn keine Option geschlossen zu sein scheint, wählen Sie **"Andere"** aus, und geben Sie weitere Informationen in den Feldern **"Titel"** und **"Plan der Aktion"** ein.</span><span class="sxs-lookup"><span data-stu-id="167be-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="167be-132">Es empfiehlt sich, nach Möglichkeit eine Kategorie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="167be-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="167be-133">**Unterkategorie:** Wählen Sie diejenige aus, die am besten zu dem Problem passt.</span><span class="sxs-lookup"><span data-stu-id="167be-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="167be-134">Wenn keine Option geschlossen zu sein scheint, wählen Sie **Andere** aus, und geben Sie unter **"Titel"** eine kurze Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="167be-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="167be-135">Geben Sie **im Aktionsplan** die Schritte zur Problembehandlung an, die Sie nach Erteilung der Rechteerweiterung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="167be-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="167be-136">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="167be-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="167be-137">Eskalationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="167be-137">Escalation requests</span></span>


<span data-ttu-id="167be-138">Wenn Sie ein Problem an Microsoft [eskalieren](../service-description/user-support.md#escalation-portal) müssen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="167be-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="167be-139">Wechseln Sie zum [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) Portal, und melden Sie sich mit Ihren Azure Active Directory-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="167be-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="167be-140">Wählen Sie **Eskalationsanforderungen aus,** und wählen Sie dann **neue Eskalationsanforderung** aus.</span><span class="sxs-lookup"><span data-stu-id="167be-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="167be-141">Geben Sie diese Details an:</span><span class="sxs-lookup"><span data-stu-id="167be-141">Provide these details:</span></span>
    - <span data-ttu-id="167be-142">**Kategorie:** Wählen Sie die Kategorie aus, die am besten zu Ihrem Problem passt.</span><span class="sxs-lookup"><span data-stu-id="167be-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="167be-143">**Titel:** Geben Sie eine sehr kurze Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="167be-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="167be-144">**Beschreibung:** Fügen Sie alle zusätzlichen Details hinzu, die unserem Team helfen könnten, das Problem zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="167be-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="167be-145">Wenn Sie Dateien anfügen müssen, können Sie dies tun, indem Sie nach der Übermittlung zur Anforderung zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="167be-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="167be-146">**Primäre Kontaktinformationen:** Geben Sie Informationen dazu an, wie Sie die Hauptperson kontaktieren, die für die Arbeit mit unserem Team verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="167be-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="167be-147">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="167be-147">Select **Submit**.</span></span>
5. <span data-ttu-id="167be-148">Besuchen Sie das Ticket im selben Portal erneut, um mit unserem Team zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="167be-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="167be-149">Nur Probleme mit Schweregrad C können über diesen Pfad eskaliert werden.</span><span class="sxs-lookup"><span data-stu-id="167be-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="167be-150">Wenden Sie sich bei anderen Problemen an Ihren IT-Administrator, um die Anforderung über das Verwaltungsportal zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="167be-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>