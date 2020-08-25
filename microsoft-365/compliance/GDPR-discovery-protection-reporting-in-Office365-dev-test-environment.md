---
title: Suche, Schutz und Berichterstellung für die DSGVO in der Microsoft 365-Entwicklungs-/Testumgebung
description: Hier erfahren Sie, wie Sie personenbezogene Informationen (PII) im Sinne der DSGVO in Microsoft 365 Entwicklungs-/Testumgebungen konfigurieren und demonstrieren können.
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a8fc24d43899fbac2653bf5ce2f068f1f67972f
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845887"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-devtest-environment"></a><span data-ttu-id="33312-103">Suche, Schutz und Berichterstellung für die DSGVO in der Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="33312-103">GDPR discovery, protection, and reporting in the dev/test environment</span></span>

 <span data-ttu-id="33312-104">**Zusammenfassung:** Veranschaulichung von DSGVO-Funktionen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33312-104">**Summary:** Demonstrate GDPR capabilities in Microsoft 365.</span></span>

<span data-ttu-id="33312-105">In diesem Artikel wird die Konfiguration und Veranschaulichung von Suche, Schutz und Berichterstellung für personenbezogene Informationen (PII) für die EU-Datenschutz-Grundverordnung (DSGVO) in einer Microsoft 365-Entwicklungs-/Testumgebung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="33312-105">This article describes how you configure and demonstrate personally identifiable information (PII) discovery, protection, and reporting for the General Data Protection Regulation (GDPR) in a Microsoft 365 dev/test environment.</span></span>

## <a name="phase-1-create-and-configure-your-trial-microsoft-365-subscription"></a><span data-ttu-id="33312-106">Phase 1: Erstellen und Konfigurieren Ihres Microsoft 365-Testabonnements</span><span class="sxs-lookup"><span data-stu-id="33312-106">Phase 1: Create and configure your trial Microsoft 365 subscription</span></span>

<span data-ttu-id="33312-107">Führen Sie zunächst die Schritte in [Phase 2 des Artikels „Microsoft 365-Entwicklungs-/Testumgebung“](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription) aus.</span><span class="sxs-lookup"><span data-stu-id="33312-107">First, follow the steps in [Phase 2 of the Microsoft 365 dev/test environment](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription) article.</span></span>

<span data-ttu-id="33312-108">Konfigurieren Sie dann mit den folgenden Schritte den eDiscovery-Manager:</span><span class="sxs-lookup"><span data-stu-id="33312-108">Next, use these steps to configure the eDiscovery manager:</span></span>

1. <span data-ttu-id="33312-109">Melden Sie sich mit Ihrem globalen Administratorkonto bei Ihrem Microsoft 365-Testmandanten an.</span><span class="sxs-lookup"><span data-stu-id="33312-109">Sign in to your Microsoft 365 trial tenant with your global administrator account.</span></span>
2. <span data-ttu-id="33312-110">Klicken Sie auf der Microsoft 365-Startseite auf **Sicherheit und Compliance**.</span><span class="sxs-lookup"><span data-stu-id="33312-110">From the Microsoft 365 home page, click **Security & Compliance**.</span></span>
3. <span data-ttu-id="33312-111">Klicken Sie auf der neuen Registerkarte „Sicherheit und Compliance“ auf **Berechtigungen** > **eDiscovery-Manager**.</span><span class="sxs-lookup"><span data-stu-id="33312-111">From the new Security & Compliance tab, click **Permissions** > **eDiscovery Manager**.</span></span>
4. <span data-ttu-id="33312-112">Klicken Sie für eDiscovery-Manager auf **Bearbeiten**, und klicken Sie dann auf **eDiscovery-Manager auswählen**.</span><span class="sxs-lookup"><span data-stu-id="33312-112">Click **Edit** for eDiscovery Manager, and then click **Choose eDiscovery Manager**.</span></span>
5. <span data-ttu-id="33312-113">Klicken Sie auf **+ Hinzufügen**, suchen Sie nach dem Namen Ihres globalen Administratorkontos, und fügen Sie dieses als eDiscovery-Manager hinzu.</span><span class="sxs-lookup"><span data-stu-id="33312-113">Click **+ Add**, search for your global administrator account name and add your global administrator account as an eDiscovery Manager.</span></span>
6. <span data-ttu-id="33312-114">Klicken Sie auf **Fertig** > **Speichern** > **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="33312-114">Click **Done** > **Save** > **Close**.</span></span>

## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a><span data-ttu-id="33312-115">Phase 2: Hinzufügen von personenbezogenen Informationen zu Ihrem Mandanten</span><span class="sxs-lookup"><span data-stu-id="33312-115">Phase 2: Add personally identifiable information to your tenant</span></span>

<span data-ttu-id="33312-116">In dieser Phase erstellen Sie ein Dokument mit PII für eine Reihe von Beispielen für internationale Kontonummern (International Banking Account Numbers, IBANs) und speichern es auf einer SharePoint Online-Website in Ihrer Microsoft 365-Entwicklungs-/Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="33312-116">In this phase, you create a document with PII for a set of example International Banking Account Numbers (IBANs) and store it on a SharePoint Online site in your Microsoft 365 dev/test environment.</span></span>

1. <span data-ttu-id="33312-117">Öffnen Sie Microsoft Word auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="33312-117">On your local computer, open Microsoft Word.</span></span>
2. <span data-ttu-id="33312-118">Fügen Sie die folgende Tabelle in die Word-Datei ein, und speichern Sie sie als „IBANs.docx“ auf Ihrem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="33312-118">Paste the following table in the Word file and save it as 'IBANs.docx' on your local computer.</span></span>

   |<span data-ttu-id="33312-119">Zahl</span><span class="sxs-lookup"><span data-stu-id="33312-119">Number</span></span>|<span data-ttu-id="33312-120">Land</span><span class="sxs-lookup"><span data-stu-id="33312-120">Country</span></span>|<span data-ttu-id="33312-121">Code</span><span class="sxs-lookup"><span data-stu-id="33312-121">Code</span></span>|<span data-ttu-id="33312-122">IBAN</span><span class="sxs-lookup"><span data-stu-id="33312-122">IBAN</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="33312-123">1</span><span class="sxs-lookup"><span data-stu-id="33312-123">1</span></span>|<span data-ttu-id="33312-124">Österreich SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-124">Austria SEPA</span></span>|<span data-ttu-id="33312-125">AT</span><span class="sxs-lookup"><span data-stu-id="33312-125">AT</span></span>|<span data-ttu-id="33312-126">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="33312-126">AT611904300234573201</span></span>|
   |<span data-ttu-id="33312-127">2</span><span class="sxs-lookup"><span data-stu-id="33312-127">2</span></span>|<span data-ttu-id="33312-128">Bulgarien SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-128">Bulgaria SEPA</span></span>|<span data-ttu-id="33312-129">BG</span><span class="sxs-lookup"><span data-stu-id="33312-129">BG</span></span>|<span data-ttu-id="33312-130">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="33312-130">BG80BNBG96611020345678</span></span>|
   |<span data-ttu-id="33312-131">3</span><span class="sxs-lookup"><span data-stu-id="33312-131">3</span></span>|<span data-ttu-id="33312-132">Dänemark SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-132">Denmark SEPA</span></span>|<span data-ttu-id="33312-133">DK</span><span class="sxs-lookup"><span data-stu-id="33312-133">DK</span></span>|<span data-ttu-id="33312-134">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="33312-134">DK5000400440116243</span></span>|
   |<span data-ttu-id="33312-135">4</span><span class="sxs-lookup"><span data-stu-id="33312-135">4</span></span>|<span data-ttu-id="33312-136">Finnland SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-136">Finland SEPA</span></span>|<span data-ttu-id="33312-137">FI</span><span class="sxs-lookup"><span data-stu-id="33312-137">FI</span></span>|<span data-ttu-id="33312-138">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="33312-138">FI2112345600000785</span></span>|
   |<span data-ttu-id="33312-139">5</span><span class="sxs-lookup"><span data-stu-id="33312-139">5</span></span>|<span data-ttu-id="33312-140">Frankreich SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-140">France SEPA</span></span>|<span data-ttu-id="33312-141">FR</span><span class="sxs-lookup"><span data-stu-id="33312-141">FR</span></span>|<span data-ttu-id="33312-142">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="33312-142">FR1420041010050500013M02606</span></span>|
   |<span data-ttu-id="33312-143">6</span><span class="sxs-lookup"><span data-stu-id="33312-143">6</span></span>|<span data-ttu-id="33312-144">Deutschland SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-144">Germany SEPA</span></span>|<span data-ttu-id="33312-145">DE</span><span class="sxs-lookup"><span data-stu-id="33312-145">DE</span></span>|<span data-ttu-id="33312-146">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="33312-146">DE89370400440532013000</span></span>|
   |<span data-ttu-id="33312-147">7</span><span class="sxs-lookup"><span data-stu-id="33312-147">7</span></span>|<span data-ttu-id="33312-148">Griechenland SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-148">Greece SEPA</span></span>|<span data-ttu-id="33312-149">GR</span><span class="sxs-lookup"><span data-stu-id="33312-149">GR</span></span>|<span data-ttu-id="33312-150">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="33312-150">GR1601101250000000012300695</span></span>|
   |<span data-ttu-id="33312-151">8</span><span class="sxs-lookup"><span data-stu-id="33312-151">8</span></span>|<span data-ttu-id="33312-152">Italien SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-152">Italy SEPA</span></span>|<span data-ttu-id="33312-153">IT</span><span class="sxs-lookup"><span data-stu-id="33312-153">IT</span></span>|<span data-ttu-id="33312-154">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="33312-154">GR1601101250000000012300695</span></span>|
   |<span data-ttu-id="33312-155">9</span><span class="sxs-lookup"><span data-stu-id="33312-155">9</span></span>|<span data-ttu-id="33312-156">Niederlande SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-156">Netherlands SEPA</span></span>|<span data-ttu-id="33312-157">NL</span><span class="sxs-lookup"><span data-stu-id="33312-157">NL</span></span>|<span data-ttu-id="33312-158">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="33312-158">NL91ABNA0417164300</span></span>|
   |<span data-ttu-id="33312-159">10</span><span class="sxs-lookup"><span data-stu-id="33312-159">10</span></span>|<span data-ttu-id="33312-160">Polen SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-160">Poland SEPA</span></span>|<span data-ttu-id="33312-161">PL</span><span class="sxs-lookup"><span data-stu-id="33312-161">PL</span></span>|<span data-ttu-id="33312-162">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="33312-162">PL27114020040000300201355387</span></span>|

   <span data-ttu-id="33312-163">Hinweis: Dieser Beispieldatensatz wird von öffentlich verfügbaren Informationen abgeleitet und soll nur für Testzwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33312-163">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

3. <span data-ttu-id="33312-164">Geben Sie auf einer neuen Registerkarte in Ihrem Browser Folgendes ein: **https://**\<YourTenantName\>**. SharePoint.com**</span><span class="sxs-lookup"><span data-stu-id="33312-164">In a new tab of your browser, type:  **https://**\<YourTenantName\>**.sharepoint.com**</span></span>
4. <span data-ttu-id="33312-p101">Klicken Sie auf **Dokumente**, um die Dokumentbibliothek für diese Website zu öffnen. Wenn Sie zu einer Tour über neue Listen aufgefordert werden, klicken Sie auf **Weiter**, bis sie abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="33312-p101">Click **Documents** to open the document library for this site. If you're prompted for a new list experience tour, click **Next** until it's finished.</span></span>
5. <span data-ttu-id="33312-167">Klicken Sie auf **Hochladen** > **Dateien**, und wählen Sie die Datei „IBANs.docx“ aus, die Sie in Schritt 2 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="33312-167">Click **Upload** > **Files** and select the IBANs.docx you created in step 2.</span></span>

## <a name="phase-3-demonstrate-data-discovery"></a><span data-ttu-id="33312-168">Phase 3: Veranschaulichen der Datenermittlung</span><span class="sxs-lookup"><span data-stu-id="33312-168">Phase 3: Demonstrate data discovery</span></span>

<span data-ttu-id="33312-169">In dieser Phase veranschaulichen Sie die Suche nach dem in Schritt 2 erstellten und gespeicherten Dokument basierend auf dessen Inhalt (IBANs).</span><span class="sxs-lookup"><span data-stu-id="33312-169">In this phase, you demonstrate search to find the document created and stored in Phase 2, based on its content containing IBANs.</span></span>

1. <span data-ttu-id="33312-170">Klicken Sie auf der Registerkarte „Sicherheit und Compliance“ auf **Start**, und klicken Sie dann auf **Suche und Untersuchung** > **Inhaltssuche**.</span><span class="sxs-lookup"><span data-stu-id="33312-170">From the Security & Compliance tab, click **Home**, and then click **Search & investigation** > **Content search**.</span></span>
2. <span data-ttu-id="33312-171">Erstellen Sie ein neues Suchelement, indem Sie auf **+** klicken.</span><span class="sxs-lookup"><span data-stu-id="33312-171">Create a new search item by clicking on **+**.</span></span>
3. <span data-ttu-id="33312-172">Geben Sie in einem neuen Fenster die folgenden Informationen an: a.</span><span class="sxs-lookup"><span data-stu-id="33312-172">In a new window, provide the following information: a.</span></span> <span data-ttu-id="33312-173">Name: IBAN-Suche b.</span><span class="sxs-lookup"><span data-stu-id="33312-173">Name: IBAN Search b.</span></span> <span data-ttu-id="33312-174">Was sollen wir uns ansehen?: **Geben Sie die Websites an, die wir durchsuchen sollen** (Klicken Sie auf **+**), und geben Sie dann die URL der Website ein: **https://**\<YourTenantName\>**. SharePoint.com/** c.</span><span class="sxs-lookup"><span data-stu-id="33312-174">Where do you want us to look?: **Choose specific sites to search** (click **+**), and then enter the site's URL: **https://**\<YourTenantName\>**.sharepoint.com/** c.</span></span> <span data-ttu-id="33312-175">Klicken Sie auf **Hinzufügen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33312-175">Click **Add**, and then click **OK**.</span></span> <span data-ttu-id="33312-176">Wenn eine Warnung angezeigt wird, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33312-176">If you see a Warning, click **OK**.</span></span>
    <span data-ttu-id="33312-177">d.</span><span class="sxs-lookup"><span data-stu-id="33312-177">d.</span></span> <span data-ttu-id="33312-178">Klicken Sie in einem **neuen Suchfenster** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33312-178">Click **Next** on a **New search** window.</span></span>
    <span data-ttu-id="33312-179">e.</span><span class="sxs-lookup"><span data-stu-id="33312-179">e.</span></span> <span data-ttu-id="33312-180">Geben Sie für **Wonach sollen wir suchen?**: **SensitiveType: „International Banking Account Number (IBAN)“** ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="33312-180">For **What do you want us to look for?**: **SensitiveType:"International Banking Account Number (IBAN)"**, and then click **Search**.</span></span>

4. <span data-ttu-id="33312-181">Stellen Sie sicher, dass mindestens ein Element in den **IBAN-Suchergebnissen** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="33312-181">Make sure you see at least one item listed in the **IBAN Search** results.</span></span>

## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a><span data-ttu-id="33312-182">Phase 4: Erstellen eines benutzerdefinierten vertraulichen Informationstyps über PowerShell</span><span class="sxs-lookup"><span data-stu-id="33312-182">Phase 4: Create a custom sensitive information type via PowerShell</span></span>

<span data-ttu-id="33312-p103">In dieser Phase erstellen Sie einen benutzerdefinierten vertraulichen Informationstyp für die fiktive Contoso Corporation mithilfe von Microsoft PowerShell. Contoso verwendet einer Contoso-Kundennummer (Contoso Customer Number, CCN) zur Identifizierung der einzelnen Kunden in seiner Kundendatenbank. Eine CCN weist die folgende Struktur auf:</span><span class="sxs-lookup"><span data-stu-id="33312-p103">In this phase, you create a custom sensitive information type for the fictional Contoso Corporation using Microsoft PowerShell.  Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following structure:</span></span>

- <span data-ttu-id="33312-186">Zwei Ziffern, die für das Jahr stehen, in dem der Datensatz erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="33312-186">Two digits to represent the year that the record was created.</span></span>
  - <span data-ttu-id="33312-187">Contoso wurde 2002 gegründet, daher wäre der früheste mögliche Wert „02“.</span><span class="sxs-lookup"><span data-stu-id="33312-187">Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span>
- <span data-ttu-id="33312-188">Drei Ziffern, die für die Partneragentur stehen, die den Datensatz erstellt hat</span><span class="sxs-lookup"><span data-stu-id="33312-188">Three digits to represent the partner agency that created the record.</span></span>
  - <span data-ttu-id="33312-189">Mögliche Agenturwerte liegen zwischen 000 bis 999.</span><span class="sxs-lookup"><span data-stu-id="33312-189">Possible agency values range from 000 to 999.</span></span>
- <span data-ttu-id="33312-190">Ein alphabetisches Zeichen, das für die Branche steht</span><span class="sxs-lookup"><span data-stu-id="33312-190">An alphabetic character to represent the line of business.</span></span>
  - <span data-ttu-id="33312-191">Mögliche Werte sind a-z, Groß- und Kleinschreibung soll nicht berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="33312-191">Possible values are a-z and should be case insensitive.</span></span>
- <span data-ttu-id="33312-192">Eine vierstellige Seriennummer</span><span class="sxs-lookup"><span data-stu-id="33312-192">A four-digit serial number.</span></span>
  - <span data-ttu-id="33312-193">Mögliche Werte für Seriennummern liegen zwischen 0000 und 9999.</span><span class="sxs-lookup"><span data-stu-id="33312-193">Possible serial number values range from 0000 to 9999.</span></span>

<span data-ttu-id="33312-p104">Contoso verwendet immer eine CCN beim Verweisen auf Kunden in der internen Korrespondenz, externen Korrespondenz, in Dokumenten und anderen Formularen. Contoso benötigt einen benutzerdefinierten vertraulichen Informationstyp, um die Verwendung von CCNs in Microsoft 365-Inhalt zu ermitteln und so einen möglichen Schutz für die Verwendung dieser personenbezogenen Informationen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="33312-p104">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, and other forms. Contoso needs a custom sensitive item type to detect the use of CCNs in Microsoft 365 content so that they may apply protection to the use of this form of personal identifiable information.</span></span>

1. <span data-ttu-id="33312-196">Befolgen Sie die Anweisungen für die mehrstufige Authentifizierung (MFA) unter [Verbindung mit Security & Compliance Center-PowerShell herstellen](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell), und stellen Sie eine Verbindung mit dem Security & Compliance Center mit UPN des globalen Administratorkontos her.</span><span class="sxs-lookup"><span data-stu-id="33312-196">Use the multi-factor authentication (MFA) connection instructions in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and connect to the Security & Compliance Center with UPN of your global administrator account.</span></span>

2. <span data-ttu-id="33312-197">Führen Sie die folgenden PowerShell-Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="33312-197">Run the following PowerShell commands.</span></span>

   ```powershell
   #Create & start search for sample data
   $searchName = "Sample Customer Information Search"
   $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
   New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
   Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
   $searchName = "Sample Customer Information Search"
   $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
   New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
   Start-ComplianceSearch -Identity $searchName
   ```

3. <span data-ttu-id="33312-198">Führen Sie die folgenden PowerShell-Befehle aus, und kopieren Sie die generierten GUIDs in der Reihenfolge, in der sie aufgelistet sind, in eine offene Instanz von Editor auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="33312-198">Run the following PowerShell commands and copy the generated GUIDs to an open instance of Notepad on your computer in the order in which they are listed.</span></span>

   ```powershell
   #Generate three unique GUIDs
   Write-Host "GUID1 = "([guid]::NewGuid().Guid)
   Write-Host "GUID2 = "([guid]::NewGuid().Guid)
   Write-Host "GUID3 = "([guid]::NewGuid().Guid)
   ```

4. <span data-ttu-id="33312-199">Öffnen Sie auf dem lokalen Computer eine weitere Instanz von Editor, und fügen Sie den folgenden Inhalt ein:</span><span class="sxs-lookup"><span data-stu-id="33312-199">On your local computer, open another instance of Notepad and paste in the following content:</span></span>

   ```text
   <?xml version="1.0" encoding="utf-8"?>
   <RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
   <RulePack id="GUID1">
   <Version major="1" minor="0" build="0" revision="0" />
   <Publisher id="GUID2" />
   <Details defaultLangCode="en">
   <LocalizedDetails langcode="en">
   <PublisherName>Contoso Ltd.</PublisherName>
   <Name>Contoso Rule Package</Name>
   <Description>Defines Contoso's custom set of classification rules</Description>
   </LocalizedDetails>
   </Details>
   </RulePack>
   <Rules>
   <!-- Contoso Customer Number (CCN) -->
   <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
   <IdMatch idRef="Regex_contoso_ccn" />
   <Match idRef="Keyword_contoso_ccn" />
   <Match idRef="Regex_eu_date" />
   </Pattern>
   </Entity>
   <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
   <Keyword id="Keyword_contoso_ccn">
   <Group matchStyle="word">
   <Term caseSensitive="false">customer number</Term>
   <Term caseSensitive="false">customer no</Term>
   <Term caseSensitive="false">customer #</Term>
   <Term caseSensitive="false">customer#</Term>
   <Term caseSensitive="false">Contoso customer</Term>
   </Group>
   </Keyword>
   <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
   <LocalizedStrings>
   <Resource idRef="GUID3">
   <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
   <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
   </Resource>
   </LocalizedStrings>
   </Rules>
   </RulePackage>
   ```

5. <span data-ttu-id="33312-200">Ersetzen Sie die Werte von GUID1, GUID2 und GUID3 im XML-Text von Schritt 4 durch deren Werte aus Schritt 3, und speichern Sie dann die Inhalte mit dem Namen „ContosoCCN.xml“ auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="33312-200">Replace the values of GUID1, GUID2, and GUID3 in the XML text of step 4 with their values from step 3, and then save the contents on your local computer with the name ContosoCCN.xml.</span></span>

6. <span data-ttu-id="33312-201">Geben Sie den Pfad zur Datei „ContosoCCN.xml“ ein, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="33312-201">Fill in the path to your ContosoCCN.xml file and run the following commands.</span></span>

   ```powershell
   #Create new Sensitive Information Type
   $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
   ```

7. <span data-ttu-id="33312-p105">Klicken Sie auf der Registerkarte „Sicherheit und Compliance“ auf **Klassifizierungen** > **Typen vertraulicher Informationen**. Die Contoso-Kundennummer (CCN) sollte in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="33312-p105">From the Security & Compliance tab, click **Classifications** > **Sensitive information types**. You should see the Contoso Customer Number (CCN) in the list.</span></span>

## <a name="phase-5-demonstrate-data-protection"></a><span data-ttu-id="33312-204">Phase 5: Veranschaulichen des Datenschutzes</span><span class="sxs-lookup"><span data-stu-id="33312-204">Phase 5: Demonstrate data protection</span></span>

<span data-ttu-id="33312-205">Zum Schutz von personenbezogenen Informationen in Microsoft 365 gehören Funktionen zur Verhinderung von Datenverlust (Data Loss Prevention, DLP).</span><span class="sxs-lookup"><span data-stu-id="33312-205">Protection of personal information in Microsoft 365 includes using data loss prevention (DLP) capabilities.</span></span>  <span data-ttu-id="33312-206">Mit DLP-Richtlinien können Sie vertrauliche Informationen in Microsoft 365 automatisch schützen.</span><span class="sxs-lookup"><span data-stu-id="33312-206">With DLP policies, you can automatically protect sensitive information across Microsoft 365.</span></span>

<span data-ttu-id="33312-p107">Es gibt mehrere Methoden zum Anwenden des Schutzes. Die Aufklärung und Bewusstseinsbildung in Bezug auf Daten von EU-Bürgern, die in Ihrer Umgebung gespeichert werden, sowie den Umgang von Mitarbeitern mit diesen stellen eine Ebene des Informationsschutzes unter Verwendung von DLP von Office 365 dar.</span><span class="sxs-lookup"><span data-stu-id="33312-p107">There are multiple ways you can apply the protection. Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Office 365 DLP.</span></span>

<span data-ttu-id="33312-209">In dieser Phase erstellen Sie eine neue DLP-Richtlinie und veranschaulichen, wie sie auf die Datei „IBANs.docx“ angewendet wird, die Sie in Phase 2 in SharePoint Online gespeichert haben, und wie sie angewendet wird, wenn Sie versuchen, eine E-Mail mit IBANs zu versenden.</span><span class="sxs-lookup"><span data-stu-id="33312-209">In this phase, you create a new DLP policy and demonstrate how it gets applied to the IBANs.docx file you stored in SharePoint Online in Phase 2 and when you attempt to send an email containing IBANs.</span></span>

1. <span data-ttu-id="33312-210">Klicken Sie auf der Registerkarte „Sicherheit und Compliance“ im Browser auf **Start**.</span><span class="sxs-lookup"><span data-stu-id="33312-210">From the Security & Compliance tab of your browser, click **Home**.</span></span>
2. <span data-ttu-id="33312-211">Klicken Sie auf **Verhinderung von Datenverlust** > **Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="33312-211">Click **Data loss prevention** > **Policy**.</span></span>
3. <span data-ttu-id="33312-212">Klicken Sie auf **+ Erstellen einer Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="33312-212">Click **+ Create a policy**.</span></span>
4. <span data-ttu-id="33312-213">Klicken Sie in **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert** > **Benutzerdefinierte Richtlinie** > **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33312-213">In **Start with a template or create a custom policy**, click **Custom** > **Custom policy** > **Next**.</span></span>
5. <span data-ttu-id="33312-p108">Geben Sie in **Richtlinie benennen** die folgenden Details an, und klicken Sie dann auf **Weiter**: a. Name: **PII-Richtlinie für EU-Bürger** b. Beschreibung: **Schützen der personenbezogenen Informationen von EU-Bürgern**</span><span class="sxs-lookup"><span data-stu-id="33312-p108">In **Name your policy**, provide the following details and then click **Next**:  a. Name: **EU Citizen PII Policy** b. Description: **Protect the personally identifiable information of European citizens**</span></span>
6. <span data-ttu-id="33312-p109">Wählen Sie in **Speicherorte auswählen** die Option **Alle Speicherorte in Microsoft 365** aus. Damit werden Inhalte in Exchange-E-Mails sowie OneDrive- und SharePoint-Dokumenten einbezogen. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33312-p109">In **Choose locations**, select **All locations in Microsoft 365**. This will include content in Exchange email and OneDrive and SharePoint documents. And then click **Next**.</span></span>
7. <span data-ttu-id="33312-220">Klicken Sie in **Anpassen des zu schützenden Inhaltstyps** auf **Nach Inhalten suchen, die Folgendes enthalten:**, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="33312-220">In **Customize the type of content you want to protect**, click **Find content that contains:** and then click **Edit**.</span></span>
8. <span data-ttu-id="33312-221">Klicken Sie in **Auswählen des zu schützenden Inhaltstyps** auf **Hinzufügen** > **Typen vertraulicher Informationen**.</span><span class="sxs-lookup"><span data-stu-id="33312-221">In **Choose the types of content to protect**, click **Add** > **Sensitive info types**.</span></span>
9. <span data-ttu-id="33312-222">Klicken Sie in **Typen vertraulicher Informationen** auf **+ Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="33312-222">In **Sensitive info types**, click **+ Add**.</span></span>
10. <span data-ttu-id="33312-223">Suchen Sie in **Typen vertraulicher Informationen** nach **IBAN**, aktivieren Sie das Kontrollkästchen für **International Banking Account Number (IBAN)**, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="33312-223">In **Sensitive info types**, search for **IBAN**, select the check box for **International Banking Account Number (IBAN)**, and then click **Add**.</span></span>
11. <span data-ttu-id="33312-224">Vergewissern Sie sich, dass **International Banking Account Number (IBAN)** als Typ vertraulicher hinzugefügt wurde, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="33312-224">Confirm that the **International Banking Account Number (IBAN)** sensitive information type was added, and then click **Done**.</span></span>
12. <span data-ttu-id="33312-225">Vergewissern Sie sich in **Inhalt enthält**, dass die Typen vertraulicher Informationen hinzugefügt wurden, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="33312-225">In **Content contains**, confirm that the sensitive information types were added and then click **Save**.</span></span>
13. <span data-ttu-id="33312-226">Stellen Sie in **Anpassen des zu schützenden Inhaltstyps** sicher, dass **Nach Inhalten suchen, die Folgendes enthalten:** die **internationale Bankkontonummer (IBAN)** enthält, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33312-226">In **Customize the type of content you want to protect**, confirm  **Find content that contains:** contains the **International Banking Account Number (IBAN)**, and then click **Next**.</span></span>
14. <span data-ttu-id="33312-227">Ändern Sie in **Erkennen, wenn Inhalte, die freigegeben werden, Folgendes enthalten:** den Wert von **10** in **1**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33312-227">In **Detect when content that's being shared contains:**, change the value from **10** to **1**, and then click **Next**.</span></span>
15. <span data-ttu-id="33312-228">Wählen Sie in **Möchten Sie die Richtlinie aktivieren oder sie zuerst ausprobieren?** die folgenden Einstellungen aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33312-228">In **Do you want to turn on the policy or test things out first?**, choose the following settings, and then click **Next**.</span></span>
    <span data-ttu-id="33312-229">a.</span><span class="sxs-lookup"><span data-stu-id="33312-229">a.</span></span> <span data-ttu-id="33312-230">Wählen Sie die Option für **Ich möchte sie zuerst testen** aus b.</span><span class="sxs-lookup"><span data-stu-id="33312-230">Select the option for **I'd like to test it out first** b.</span></span> <span data-ttu-id="33312-231">Aktivieren Sie das Kontrollkästchen für **Richtlinientipps im Testmodus anzeigen**</span><span class="sxs-lookup"><span data-stu-id="33312-231">Select the check box for **Show policy tips while in test mode**</span></span>
16. <span data-ttu-id="33312-p111">Klicken Sie in **Überprüfen Sie Ihre Einstellungen** auf **Erstellen**, nachdem Sie die Einstellungen überprüft haben. HINWEIS: Nach dem Erstellen einer neuen DLP-Richtlinie dauert es eine Weile, bis diese wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="33312-p111">In **Review your settings**, click **Create** after reviewing the settings. NOTE: After you create a new DLP policy, it will take a while for it to take effect.</span></span>
17. <span data-ttu-id="33312-234">Öffnen Sie auf dem lokalen Computer eine private Instanz des Browsers.</span><span class="sxs-lookup"><span data-stu-id="33312-234">On your local computer, open a private instance of your browser.</span></span>
18. <span data-ttu-id="33312-235">Geben Sie in der Adressleiste **https://**\<YourTenantName\>**.SharePoint.com**, und melden Sie sich mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="33312-235">In the address bar, type **https://**\<YourTenantName\>**.sharepoint.com** and sign in using your global administrator account.</span></span>
19. <span data-ttu-id="33312-236">Klicken Sie auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="33312-236">Click **Documents**.</span></span>
20. <span data-ttu-id="33312-p112">Klicken Sie auf die Datei mit dem Namen „IBANs.docx“. Dann sollte „Richtlinientipp für IBANs.docx“ angezeigt werden. Die Datei „IBANs.docx“ wurde für externe Empfänger freigegeben, und dies verstößt gegen die DLP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="33312-p112">Click the file named 'IBANs.docx'. You should see 'Policy tip for IBANs.docx'.  The IBANs.docx file was shared with external recipients, which violates the DLP policy.</span></span>
21. <span data-ttu-id="33312-240">Geben Sie in der Adressleiste Folgendes ein: `https://outlook.office365.com`</span><span class="sxs-lookup"><span data-stu-id="33312-240">In the address bar, type: `https://outlook.office365.com`</span></span>
22. <span data-ttu-id="33312-241">Klicken Sie auf **Neu** - **E-Mail-Nachricht**, und geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="33312-241">Click **New** - **Email message** and provide the following:</span></span>

    - <span data-ttu-id="33312-242">**An:** \<a personal email address\></span><span class="sxs-lookup"><span data-stu-id="33312-242">**To:** \<a personal email address\></span></span>
    - <span data-ttu-id="33312-243">**Betreff:** DSGVO-Test</span><span class="sxs-lookup"><span data-stu-id="33312-243">**Subject:** GDPR Test</span></span>
    - <span data-ttu-id="33312-244">**Text:** Kopieren Sie die unten gezeigte Tabelle mit Werten, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="33312-244">**Body:** Copy in the table of values shown below.</span></span>

      |<span data-ttu-id="33312-245">Nummer</span><span class="sxs-lookup"><span data-stu-id="33312-245">Number</span></span>|<span data-ttu-id="33312-246">Land</span><span class="sxs-lookup"><span data-stu-id="33312-246">Country</span></span>|<span data-ttu-id="33312-247">Code</span><span class="sxs-lookup"><span data-stu-id="33312-247">Code</span></span>|<span data-ttu-id="33312-248">IBAN</span><span class="sxs-lookup"><span data-stu-id="33312-248">IBAN</span></span>|
      |---|---|---|---|
      |<span data-ttu-id="33312-249">1</span><span class="sxs-lookup"><span data-stu-id="33312-249">1</span></span>|<span data-ttu-id="33312-250">Österreich SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-250">Austria SEPA</span></span>|<span data-ttu-id="33312-251">AT</span><span class="sxs-lookup"><span data-stu-id="33312-251">AT</span></span>|<span data-ttu-id="33312-252">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="33312-252">AT611904300234573201</span></span>|
      |<span data-ttu-id="33312-253">2</span><span class="sxs-lookup"><span data-stu-id="33312-253">2</span></span>|<span data-ttu-id="33312-254">Bulgarien SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-254">Bulgaria SEPA</span></span>|<span data-ttu-id="33312-255">BG</span><span class="sxs-lookup"><span data-stu-id="33312-255">BG</span></span>|<span data-ttu-id="33312-256">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="33312-256">BG80BNBG96611020345678</span></span>|
      |<span data-ttu-id="33312-257">3</span><span class="sxs-lookup"><span data-stu-id="33312-257">3</span></span>|<span data-ttu-id="33312-258">Dänemark SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-258">Denmark SEPA</span></span>|<span data-ttu-id="33312-259">DK</span><span class="sxs-lookup"><span data-stu-id="33312-259">DK</span></span>|<span data-ttu-id="33312-260">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="33312-260">DK5000400440116243</span></span>|
      |<span data-ttu-id="33312-261">4</span><span class="sxs-lookup"><span data-stu-id="33312-261">4</span></span>|<span data-ttu-id="33312-262">Finnland SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-262">Finland SEPA</span></span>|<span data-ttu-id="33312-263">FI</span><span class="sxs-lookup"><span data-stu-id="33312-263">FI</span></span>|<span data-ttu-id="33312-264">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="33312-264">FI2112345600000785</span></span>|
      |<span data-ttu-id="33312-265">5</span><span class="sxs-lookup"><span data-stu-id="33312-265">5</span></span>|<span data-ttu-id="33312-266">Frankreich SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-266">France SEPA</span></span>|<span data-ttu-id="33312-267">FR</span><span class="sxs-lookup"><span data-stu-id="33312-267">FR</span></span>|<span data-ttu-id="33312-268">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="33312-268">FR1420041010050500013M02606</span></span>|
      |<span data-ttu-id="33312-269">6</span><span class="sxs-lookup"><span data-stu-id="33312-269">6</span></span>|<span data-ttu-id="33312-270">Deutschland SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-270">Germany SEPA</span></span>|<span data-ttu-id="33312-271">DE</span><span class="sxs-lookup"><span data-stu-id="33312-271">DE</span></span>|<span data-ttu-id="33312-272">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="33312-272">DE89370400440532013000</span></span>|
      |<span data-ttu-id="33312-273">7</span><span class="sxs-lookup"><span data-stu-id="33312-273">7</span></span>|<span data-ttu-id="33312-274">Griechenland SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-274">Greece SEPA</span></span>|<span data-ttu-id="33312-275">GR</span><span class="sxs-lookup"><span data-stu-id="33312-275">GR</span></span>|<span data-ttu-id="33312-276">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="33312-276">GR1601101250000000012300695</span></span>|
      |<span data-ttu-id="33312-277">8</span><span class="sxs-lookup"><span data-stu-id="33312-277">8</span></span>|<span data-ttu-id="33312-278">Italien SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-278">Italy SEPA</span></span>|<span data-ttu-id="33312-279">IT</span><span class="sxs-lookup"><span data-stu-id="33312-279">IT</span></span>|<span data-ttu-id="33312-280">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="33312-280">GR1601101250000000012300695</span></span>|
      |<span data-ttu-id="33312-281">9</span><span class="sxs-lookup"><span data-stu-id="33312-281">9</span></span>|<span data-ttu-id="33312-282">Niederlande SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-282">Netherlands SEPA</span></span>|<span data-ttu-id="33312-283">NL</span><span class="sxs-lookup"><span data-stu-id="33312-283">NL</span></span>|<span data-ttu-id="33312-284">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="33312-284">NL91ABNA0417164300</span></span>|
      |<span data-ttu-id="33312-285">10</span><span class="sxs-lookup"><span data-stu-id="33312-285">10</span></span>|<span data-ttu-id="33312-286">Polen SEPA</span><span class="sxs-lookup"><span data-stu-id="33312-286">Poland SEPA</span></span>|<span data-ttu-id="33312-287">PL</span><span class="sxs-lookup"><span data-stu-id="33312-287">PL</span></span>|<span data-ttu-id="33312-288">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="33312-288">PL27114020040000300201355387</span></span>|
      |

    <span data-ttu-id="33312-289">Hinweis: Dieser Beispieldatensatz wird von öffentlich verfügbaren Informationen abgeleitet und soll nur für Testzwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33312-289">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

23. <span data-ttu-id="33312-290">Sie sehen, dass die DLP-Richtlinie erkannt hat, dass der Text der E-Mail IBANs enthält und Ihnen am oberen Rand des Nachrichtenfensters den Richtlinientipp bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="33312-290">You will see that the DLP policy recognized that body of the email contains IBANs and provides you with the policy tip at the top of the message window.</span></span>
24. <span data-ttu-id="33312-291">Schließen Sie die private Instanz des Browsers.</span><span class="sxs-lookup"><span data-stu-id="33312-291">Close the private instance of your browser.</span></span>

## <a name="phase-6-demonstrate-reporting"></a><span data-ttu-id="33312-292">Phase 6: Veranschaulichen der Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="33312-292">Phase 6: Demonstrate reporting</span></span>

<span data-ttu-id="33312-293">In dieser Phase veranschaulichen Sie die Microsoft 365-Berichterstellung basierend auf der in Phase 5 konfigurierten DLP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="33312-293">In this phase, you demonstrate Microsoft 365 reporting based on the DLP policy configured in Phase 5.</span></span>

   1. <span data-ttu-id="33312-294">Klicken Sie auf der Registerkarte „Sicherheit und Compliance“ im Browser auf **Start**.</span><span class="sxs-lookup"><span data-stu-id="33312-294">From the Security & Compliance tab of your browser, click **Home**.</span></span>
   2. <span data-ttu-id="33312-295">Klicken Sie auf **Berichte** > **Dashboard** > **DLP-Richtlinienübereinstimmungen**.</span><span class="sxs-lookup"><span data-stu-id="33312-295">Click **Reports** > **Dashboard** > **DLP policy matches**.</span></span>
   3. <span data-ttu-id="33312-p113">Ihre DLP-Richtlinie trägt zum Identifizieren und Schützen vertraulicher Informationen der Organisation bei. Beispielsweise sehen Sie im Bericht, dass die Richtlinie das Dokuments identifiziert hat, das in SharePoint Online gespeicherte IBANs enthält.</span><span class="sxs-lookup"><span data-stu-id="33312-p113">Your DLP policy helps identify and protect organization's sensitive information. For example, in the report you will see that the policy identified the document that contains IBANs stored in SharePoint Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="33312-298">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33312-298">See Also</span></span>

[<span data-ttu-id="33312-299">Schutz von Informationen in Office 365 für die DSGVO</span><span class="sxs-lookup"><span data-stu-id="33312-299">Office 365 Information Protection for GDPR</span></span>](office-365-information-protection-for-gdpr.md)

[<span data-ttu-id="33312-300">DSGVO für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33312-300">GDPR for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/gdpr?toc=/microsoft-365/enterprise/toc.json)
