---
title: Microsoft Compliance Configuration Analyzer for Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie Microsoft Compliance Configuration Analyzer verwenden, um mit Microsoft Compliance Manager schnell in Betrieb zu gehen.
ms.openlocfilehash: 272477251efed7ebf13bd2e644869eaf2aad1bc2
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454686"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="c7b15-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c7b15-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="c7b15-104">**In diesem Artikel:** Erfahren Sie, wie Sie das Microsoft Compliance Configure Analyzer-Tool installieren und ausführen, um schnell mit Microsoft Compliance Manger zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="c7b15-105">Übersicht über Microsoft Compliance Configuration Analyzer (MCCA) (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c7b15-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="c7b15-106">Die Microsoft Compliance Configuration Analyzer (MCCA) ist ein Vorschautool, mit dem Sie mit [Microsoft Compliance Manager beginnen können.](compliance-manager.md)</span><span class="sxs-lookup"><span data-stu-id="c7b15-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="c7b15-107">MCCA ist ein PowerShell-basiertes Hilfsprogramm, das die aktuellen Konfigurationen Ihrer Organisation abruft und anhand der von Microsoft 365 empfohlenen bewährten Methoden überprüft.</span><span class="sxs-lookup"><span data-stu-id="c7b15-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="c7b15-108">Diese bewährten Methoden basieren auf einer Reihe von Kontrollen, die wichtige Vorschriften und Standards für Datenschutz und Datenkontrolle enthalten.</span><span class="sxs-lookup"><span data-stu-id="c7b15-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="c7b15-109">MCCA kann Ihnen dabei helfen, schnell zu erkennen, welche Verbesserungsmaßnahmen in Compliance Manger für Ihre aktuelle Microsoft 365-Umgebung gelten.</span><span class="sxs-lookup"><span data-stu-id="c7b15-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="c7b15-110">Jede von MCCA identifizierte Aktion gibt Ihnen Empfehlungen für die Implementierung, mit direkten Links zum Compliance Manager und der entsprechenden Lösung, um Korrekturmaßnahmen zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="c7b15-111">Eine weitere Ressource zum Verständnis von MCCA ist der Besuch der [README-Anweisungen auf GitHub](https://github.com/OfficeDev/MCCA#overview).</span><span class="sxs-lookup"><span data-stu-id="c7b15-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="c7b15-112">Diese Seite enthält detaillierte Informationen zu den Voraussetzungen und enthält vollständige Installationsanweisungen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="c7b15-113">Sie benötigen kein GitHub-Konto, um auf diese Seite zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="c7b15-114">**Verfügbarkeit**: MCCA ist für alle Organisationen mit Office 365- und Microsoft 365-Lizenzen und GCC (US Government Community) moderaten und GCC High-Kunden verfügbar, mit Plänen zur Erweiterung des Diensts für DOD-Kunden.</span><span class="sxs-lookup"><span data-stu-id="c7b15-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate and GCC High customers, with plans underway to expand service to DOD customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="c7b15-115">Installieren von MCCA und Ausführen eines Berichts</span><span class="sxs-lookup"><span data-stu-id="c7b15-115">Install MCCA and run a report</span></span>

<span data-ttu-id="c7b15-116">Sie können das MCCA-Tool mithilfe von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7b15-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="c7b15-117">Nachdem Sie das Tool heruntergeladen und installiert haben, müssen Sie diese Schritte nicht wiederholen, um Berichte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="c7b15-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="c7b15-118">Jedes Mal, wenn Sie MCCA öffnen, werden Sie nach Ihren Anmeldeinformationen gefragt, und es wird ein neuer, aktualisierter Bericht generiert.</span><span class="sxs-lookup"><span data-stu-id="c7b15-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="c7b15-119">Schritt 1: Installieren Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7b15-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="c7b15-120">Zu Beginn benötigen Sie das Exchange Online PowerShell-Modul (v2.0.3 oder höher), das im PowerShell-Katalog verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c7b15-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="c7b15-121">[Installationsanweisungen erhalten](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span><span class="sxs-lookup"><span data-stu-id="c7b15-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="c7b15-122">Schritt 2: Installieren von MCCA</span><span class="sxs-lookup"><span data-stu-id="c7b15-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="c7b15-123">Um MCCA zu installieren, verwenden Sie zunächst PowerShell im Administratormodus.</span><span class="sxs-lookup"><span data-stu-id="c7b15-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="c7b15-124">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c7b15-124">Follow the steps below:</span></span>

1. <span data-ttu-id="c7b15-125">Wählen Sie die Schaltfläche Windows **Start** aus.</span><span class="sxs-lookup"><span data-stu-id="c7b15-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="c7b15-126">Geben **Sie PowerShell** ein, klicken Sie mit der rechten Maustaste **auf Windows PowerShell** und wählen Sie dann Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="c7b15-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="c7b15-127">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c7b15-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="c7b15-128">Schritt 3: Ausführen eines Berichts</span><span class="sxs-lookup"><span data-stu-id="c7b15-128">Step 3: Run a report</span></span>

<span data-ttu-id="c7b15-129">Nach der Installation von MCCA können Sie MCCA ausführen und einen Bericht generieren.</span><span class="sxs-lookup"><span data-stu-id="c7b15-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="c7b15-130">So führen Sie einen Bericht aus:</span><span class="sxs-lookup"><span data-stu-id="c7b15-130">To run a report:</span></span>

1. <span data-ttu-id="c7b15-131">Öffnen von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7b15-131">Open PowerShell</span></span>
2. <span data-ttu-id="c7b15-132">Führen Sie das Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="c7b15-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```

   <span data-ttu-id="c7b15-133">Wenn Sie ein GCC High-Kunde sind, müssen Sie einen zusätzlichen Eingabeparameter angeben, um den Bericht ausführen zu können:</span><span class="sxs-lookup"><span data-stu-id="c7b15-133">If you're a GCC High customer, you'll need to provide an additional input parameter to run the report:</span></span>

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. <span data-ttu-id="c7b15-134">Sobald MCCA ausgeführt wird, wird eine erste Version überprüft und nach Anmeldeinformationen gefragt.</span><span class="sxs-lookup"><span data-stu-id="c7b15-134">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="c7b15-135">Melden Sie sich an der Eingabeaufforderung des Benutzernamens mit Ihrer Microsoft 365-Konto-E-Mail-Adresse an ( zeigen Sie die Zum Erstellen von Berichten berechtigten Rollen[an).](#role-based-reporting)</span><span class="sxs-lookup"><span data-stu-id="c7b15-135">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="c7b15-136">Geben Sie dann Ihr Kennwort an der Kennwortaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="c7b15-136">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="c7b15-137">Der Bericht dauert dann ca. 2 bis 5 Minuten.</span><span class="sxs-lookup"><span data-stu-id="c7b15-137">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="c7b15-138">Wenn sie fertig ist, wird ein Browserfenster geöffnet und Ihr HTML-Bericht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7b15-138">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="c7b15-139">Jedes Mal, wenn Sie das Tool ausführen, werden Ihre Anmeldeinformationen gefragt und ein neuer Bericht generiert.</span><span class="sxs-lookup"><span data-stu-id="c7b15-139">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="c7b15-140">Dieser Bericht wird lokal im folgenden Verzeichnis gespeichert:</span><span class="sxs-lookup"><span data-stu-id="c7b15-140">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="c7b15-141">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="c7b15-141">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="c7b15-142">Sie können auf zuvor generierte Berichte aus diesem Verzeichnis zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-142">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="c7b15-143">Grundlegendes zu Ihrem Bericht</span><span class="sxs-lookup"><span data-stu-id="c7b15-143">Understanding your report</span></span>

<span data-ttu-id="c7b15-144">Ihr Bericht spiegelt Daten basierend auf dem Datum und der Uhrzeit wider, zu der er generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c7b15-144">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="c7b15-145">Der obere Abschnitt enthält Details dazu, wann sie generiert wurde, Ihren Organisationsnamen und die Mandanten-ID.</span><span class="sxs-lookup"><span data-stu-id="c7b15-145">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="c7b15-146">Geolocationbasierte Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="c7b15-146">Geolocation-based reporting</span></span>

<span data-ttu-id="c7b15-147">Der **Abschnitt Note** zeigt, dass Ihr Bericht basierend auf dem geografischen Standort Ihres Mandanten angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="c7b15-147">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="c7b15-148">Die im Tool aufgeführten Empfehlungen sind spezifisch für Ihr Land oder Ihre Region.</span><span class="sxs-lookup"><span data-stu-id="c7b15-148">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="c7b15-149">Ihre Geolocationauswahl wird verwendet, um typen von vertraulichen Informationen (SENSITIVE Information Types, SITs) zu bewerten, die für diese Geolocation relevant sind, und einen Bericht zu generieren, der an Ihrem Land oder Ihrer Region ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="c7b15-149">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="c7b15-150">Wählen Sie Geolocations basierend auf Daten aus, die Sie in Ihrem Mandanten haben.</span><span class="sxs-lookup"><span data-stu-id="c7b15-150">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="c7b15-151">Um die Standortinformationen Ihres Berichts zu ändern, müssen Sie einen Eingabeparameter für geolocation (-Geo) angeben.</span><span class="sxs-lookup"><span data-stu-id="c7b15-151">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="c7b15-152">Sie können entweder einen oder mehrere geolocations auswählen, die für Ihren Mandanten gelten.</span><span class="sxs-lookup"><span data-stu-id="c7b15-152">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="c7b15-153">Führen Sie die folgenden Anweisungen aus, um einen Bericht basierend auf einem bestimmten Speicherort ausführen zu können:</span><span class="sxs-lookup"><span data-stu-id="c7b15-153">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="c7b15-154">Öffnen von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7b15-154">Open PowerShell</span></span>
2. <span data-ttu-id="c7b15-155">Um eine bestimmte Region anzugeben, führen Sie ein Cmdlet mit den Zahlen aus der folgenden Tabelle aus, die dem Land oder der Region entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-155">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="c7b15-156">Geben Sie mehrere Zahlen ein, indem Sie sie durch ein Komma trennen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-156">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="c7b15-157">Mit dem cmdlet unten wird beispielsweise ein angepasster Bericht für Asia-Pacific und Japan ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="c7b15-157">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="c7b15-158">Input</span><span class="sxs-lookup"><span data-stu-id="c7b15-158">Input</span></span> |  <span data-ttu-id="c7b15-159">Land oder Region</span><span class="sxs-lookup"><span data-stu-id="c7b15-159">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="c7b15-160">1 </span><span class="sxs-lookup"><span data-stu-id="c7b15-160">1</span></span> | <span data-ttu-id="c7b15-161">Asien-Pazifik</span><span class="sxs-lookup"><span data-stu-id="c7b15-161">Asia-Pacific</span></span> |
  | <span data-ttu-id="c7b15-162">2 </span><span class="sxs-lookup"><span data-stu-id="c7b15-162">2</span></span> | <span data-ttu-id="c7b15-163">Australien</span><span class="sxs-lookup"><span data-stu-id="c7b15-163">Australia</span></span> |
  | <span data-ttu-id="c7b15-164">3 </span><span class="sxs-lookup"><span data-stu-id="c7b15-164">3</span></span> | <span data-ttu-id="c7b15-165">Kanada</span><span class="sxs-lookup"><span data-stu-id="c7b15-165">Canada</span></span> |
  | <span data-ttu-id="c7b15-166">4 </span><span class="sxs-lookup"><span data-stu-id="c7b15-166">4</span></span> | <span data-ttu-id="c7b15-167">Europa (ohne Frankreich) / Naher Osten /Afrika</span><span class="sxs-lookup"><span data-stu-id="c7b15-167">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="c7b15-168">5 </span><span class="sxs-lookup"><span data-stu-id="c7b15-168">5</span></span> | <span data-ttu-id="c7b15-169">Frankreich</span><span class="sxs-lookup"><span data-stu-id="c7b15-169">France</span></span> |
  | <span data-ttu-id="c7b15-170">6 </span><span class="sxs-lookup"><span data-stu-id="c7b15-170">6</span></span> | <span data-ttu-id="c7b15-171">Indien</span><span class="sxs-lookup"><span data-stu-id="c7b15-171">India</span></span> |
  | <span data-ttu-id="c7b15-172">7 </span><span class="sxs-lookup"><span data-stu-id="c7b15-172">7</span></span> | <span data-ttu-id="c7b15-173">Japan</span><span class="sxs-lookup"><span data-stu-id="c7b15-173">Japan</span></span> |
  | <span data-ttu-id="c7b15-174">8 </span><span class="sxs-lookup"><span data-stu-id="c7b15-174">8</span></span> | <span data-ttu-id="c7b15-175">Korea</span><span class="sxs-lookup"><span data-stu-id="c7b15-175">Korea</span></span> |
  | <span data-ttu-id="c7b15-176">9 </span><span class="sxs-lookup"><span data-stu-id="c7b15-176">9</span></span> | <span data-ttu-id="c7b15-177">Nordamerika (ohne Kanada)</span><span class="sxs-lookup"><span data-stu-id="c7b15-177">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="c7b15-178">10  </span><span class="sxs-lookup"><span data-stu-id="c7b15-178">10</span></span> | <span data-ttu-id="c7b15-179">Südamerika</span><span class="sxs-lookup"><span data-stu-id="c7b15-179">South America</span></span> |
  | <span data-ttu-id="c7b15-180">11</span><span class="sxs-lookup"><span data-stu-id="c7b15-180">11</span></span> | <span data-ttu-id="c7b15-181">Südafrika</span><span class="sxs-lookup"><span data-stu-id="c7b15-181">South Africa</span></span> |
  | <span data-ttu-id="c7b15-182">12 </span><span class="sxs-lookup"><span data-stu-id="c7b15-182">12</span></span> | <span data-ttu-id="c7b15-183">Schweiz</span><span class="sxs-lookup"><span data-stu-id="c7b15-183">Switzerland</span></span> |
  | <span data-ttu-id="c7b15-184">13 </span><span class="sxs-lookup"><span data-stu-id="c7b15-184">13</span></span> | <span data-ttu-id="c7b15-185">Vereinigte Arabische Emirate</span><span class="sxs-lookup"><span data-stu-id="c7b15-185">United Arab Emirates</span></span> |
  | <span data-ttu-id="c7b15-186">14 </span><span class="sxs-lookup"><span data-stu-id="c7b15-186">14</span></span> | <span data-ttu-id="c7b15-187">Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="c7b15-187">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="c7b15-188">Der Bericht enthält immer MCCA unterstützte internationale Typen vertraulicher Informationen wie SWIFT-Code, Kreditkartennummer usw.</span><span class="sxs-lookup"><span data-stu-id="c7b15-188">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="c7b15-189">Rollenbasierte Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="c7b15-189">Role-based reporting</span></span>

<span data-ttu-id="c7b15-190">Ihr Bericht wird auch basierend auf Ihrer Rolle angepasst.</span><span class="sxs-lookup"><span data-stu-id="c7b15-190">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="c7b15-191">Die folgende Tabelle zeigt, welche Rollen Zugriff auf welche Abschnitte des Berichts haben.</span><span class="sxs-lookup"><span data-stu-id="c7b15-191">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="c7b15-192">Andere Rollen in Ihrer Organisation (nicht in der folgenden Tabelle aufgeführt) können das Tool möglicherweise nicht ausführen, oder sie führen das Tool aus und haben eingeschränkten Zugriff auf Informationen im Abschlussbericht.</span><span class="sxs-lookup"><span data-stu-id="c7b15-192">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="c7b15-193">![MCCA – Rollen](../media/compliance-manager-mcca-roles.png "MCCA-Rollen")</span><span class="sxs-lookup"><span data-stu-id="c7b15-193">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="c7b15-194">Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="c7b15-194">Exceptions:</span></span>
1. <span data-ttu-id="c7b15-195">Der Benutzer kann unabhängig vom Abschnitt "Verwenden von IRM für Exchange Online" keinen Bericht für IP generieren.</span><span class="sxs-lookup"><span data-stu-id="c7b15-195">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="c7b15-196">Der Benutzer kann unabhängig vom Abschnitt "Verwenden von IRM für Exchange Online" einen Bericht für IP generieren.</span><span class="sxs-lookup"><span data-stu-id="c7b15-196">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="c7b15-197">Der Benutzer kann unabhängig vom Abschnitt "Enable Communication Compliance in O365" einen Bericht für IP generieren.</span><span class="sxs-lookup"><span data-stu-id="c7b15-197">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="c7b15-198">Der Benutzer kann keinen Bericht für IP generieren, abgesehen vom Abschnitt "Überwachung in Office 365 aktivieren".</span><span class="sxs-lookup"><span data-stu-id="c7b15-198">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="c7b15-199">Der Benutzer kann den Bericht für IP außerhalb des Abschnitts "Überwachung in Office 365 aktivieren" generieren.</span><span class="sxs-lookup"><span data-stu-id="c7b15-199">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="c7b15-200">Abschnitt "Lösungszusammenfassung"</span><span class="sxs-lookup"><span data-stu-id="c7b15-200">Solutions Summary section</span></span>

<span data-ttu-id="c7b15-201">Im **Abschnitt Lösungszusammenfassung** des Berichts finden Sie eine Übersicht über Verbesserungsmaßnahmen, die Ihre Organisation im Compliance Manager ergreifen kann, um Ihre Compliancehaltung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c7b15-201">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="c7b15-202">![MCCA – Lösungszusammenfassung](../media/compliance-manager-mcca-solutions.png "Zusammenfassungsbildschirm für MCCA-Lösungen")</span><span class="sxs-lookup"><span data-stu-id="c7b15-202">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="c7b15-203">MCCA wertet Ihre aktuellen Konfigurationen mit den empfohlenen Verbesserungsmaßnahmen im Compliance Manager aus.</span><span class="sxs-lookup"><span data-stu-id="c7b15-203">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="c7b15-204">Alle Verbesserungsmaßnahmen, die vom MCCA-Tool als aufmerksamkeitserregend identifiziert werden, werden in diesem Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c7b15-204">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="c7b15-205">Neben jeder Microsoft-Lösung befinden sich farblich codierte Felder, die die Anzahl der Elemente angeben, die Verbesserungsmaßnahmen im Compliance-Manager entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-205">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="c7b15-206">Die Aktionen sind in drei Statuszustände aufgeschlüsselt:</span><span class="sxs-lookup"><span data-stu-id="c7b15-206">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="c7b15-207">**OK**: Die Aktionen, die die empfohlenen Bedingungen erfüllen und zurzeit keine Aufmerksamkeit benötigen</span><span class="sxs-lookup"><span data-stu-id="c7b15-207">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="c7b15-208">**Verbesserung**: Aktionen, die Aufmerksamkeit erfordern</span><span class="sxs-lookup"><span data-stu-id="c7b15-208">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="c7b15-209">**Empfehlung**: Aktionen, die keine Aufmerksamkeit erfordern, für die wir jedoch bewährte Methoden empfehlen</span><span class="sxs-lookup"><span data-stu-id="c7b15-209">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="c7b15-210">Wählen Sie ein Feld aus, um Verbesserungen und Empfehlungen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="c7b15-210">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="c7b15-211">**Elemente mit dem Verbesserungsstatus**</span><span class="sxs-lookup"><span data-stu-id="c7b15-211">**Items with the Improvement status**</span></span>

<span data-ttu-id="c7b15-212">Wählen Sie das Dropdown neben der **Bezeichnung Verbesserung** rechts neben der Verbesserungsaktion aus.</span><span class="sxs-lookup"><span data-stu-id="c7b15-212">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="c7b15-213">Sie sehen eine kurze Zusammenfassung und Details zu Ihren aktuellen Einstellungen und den empfohlenen Verbesserungsmaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-213">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="c7b15-214">Die Zusammenfassung enthält direkte Links zum Compliance Manager, die entsprechende Lösung im Microsoft 365 Compliance Center und die entsprechende Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7b15-214">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="c7b15-215">Durch Klicken auf den Link Compliance-Manager erhalten Sie eine gefilterte Ansicht aller Verbesserungsmaßnahmen innerhalb dieser Lösung, die Sie noch nicht implementiert haben.</span><span class="sxs-lookup"><span data-stu-id="c7b15-215">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="c7b15-216">Von dort aus können Sie die Anzahl der Punkte sehen, die Sie erreichen können, um Ihre Compliancebewertung zu [erhöhen,](compliance-score-calculation.md)und die Bewertungen, auf die sie angewendet werden, sowie die anwendbaren Vorschriften und Zertifizierungen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-216">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="c7b15-217">Für DLP gibt es eine Schaltfläche **"Korrekturskript",** mit der Sie ein vorab generiertes PowerShell-Skript basierend auf den empfohlenen Empfehlungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="c7b15-217">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="c7b15-218">Sie können sie direkt in Ihre PowerShell-Konsole kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="c7b15-218">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="c7b15-219">Es erstellt eine DLP-Richtlinie im Testmodus</span><span class="sxs-lookup"><span data-stu-id="c7b15-219">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="c7b15-220">**Elemente mit Empfehlungsstatus**</span><span class="sxs-lookup"><span data-stu-id="c7b15-220">**Items with Recommendation status**</span></span>

<span data-ttu-id="c7b15-221">Wählen Sie das Dropdown neben der **Empfehlungsbezeichnung** rechts neben der Verbesserungsaktion aus.</span><span class="sxs-lookup"><span data-stu-id="c7b15-221">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="c7b15-222">Es wird eine Zusammenfassung der aktuellen Microsoft 365-Umgebung Ihrer Organisation im Zusammenhang mit der Verbesserungsaktion sowie empfohlene bewährte Methoden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7b15-222">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="c7b15-223">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c7b15-223">Resources</span></span>

<span data-ttu-id="c7b15-224">Weitere Informationen zum Installieren, Einrichten und Verwenden von MCCA finden Sie in den [README-Anweisungen](https://github.com/OfficeDev/MCCA#overview) auf GitHub (kein GitHub-Konto erforderlich).</span><span class="sxs-lookup"><span data-stu-id="c7b15-224">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="c7b15-225">Weitere Informationen zu Windows PowerShell finden Sie unter [Verwenden der PowerShell-Dokumentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="c7b15-225">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="c7b15-226">Siehe auch [Starten Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="c7b15-226">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
