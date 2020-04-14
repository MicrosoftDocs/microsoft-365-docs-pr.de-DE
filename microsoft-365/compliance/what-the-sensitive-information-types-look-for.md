---
title: Wonach die Typen von vertraulichen Informationen suchen
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Die Verhinderung von Datenverlust (Data Loss &amp; Prevention, DLP) im Office 365 Security Compliance Center umfasst 80 Typen für vertrauliche Informationen, die Sie in ihren DLP-Richtlinien verwenden können. Dieses Thema enthält eine Liste aller dieser vertraulichen Informationstypen und zeigt, was eine DLP-Richtlinie sucht, wenn sie den jeweiligen Typen erkennt.
ms.openlocfilehash: aa3a08961ccad92c9986db16c1d8180d9b0cd17e
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240282"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="48268-104">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="48268-104">What the sensitive information types look for</span></span>

<span data-ttu-id="48268-105">Die Verhinderung von Datenverlust (Data Loss &amp; Prevention, DLP) im Office 365 Security Compliance Center umfasst viele Arten von vertraulichen Informationen, die Sie in ihren DLP-Richtlinien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="48268-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="48268-106">Dieses Thema enthält eine Liste aller dieser vertraulichen Informationstypen und zeigt, was eine DLP-Richtlinie sucht, wenn sie den jeweiligen Typen erkennt.</span><span class="sxs-lookup"><span data-stu-id="48268-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="48268-107">Ein vertraulicher Informationstyp wird durch ein Muster definiert, das durch einen regulären Ausdruck oder eine Funktion identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="48268-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="48268-108">Darüber hinaus können auch belegende Hinweise wie Schlüsselwörter oder Prüfsummen zum Identifizieren eines Typs vertraulicher Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48268-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="48268-109">Beim Auswertungsprozess können auch die Zuverlässigkeitsstufe und die Näherung herangezogen werden.</span><span class="sxs-lookup"><span data-stu-id="48268-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="48268-110">ABA Routing Number (US-Bankleitzahl)</span><span class="sxs-lookup"><span data-stu-id="48268-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-111">Format</span><span class="sxs-lookup"><span data-stu-id="48268-111">Format</span></span>

<span data-ttu-id="48268-112">9 Ziffern in formatiertem oder unformatiertem Muster</span><span class="sxs-lookup"><span data-stu-id="48268-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-113">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-113">Pattern</span></span>

<span data-ttu-id="48268-114">Formatiert</span><span class="sxs-lookup"><span data-stu-id="48268-114">Formatted:</span></span>
- <span data-ttu-id="48268-115">Vier Ziffern, beginnend mit 0, 1, 2, 3, 6, 7 oder 8</span><span class="sxs-lookup"><span data-stu-id="48268-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="48268-116">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-116">A hyphen</span></span>
- <span data-ttu-id="48268-117">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-117">Four digits</span></span>
- <span data-ttu-id="48268-118">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-118">A hyphen</span></span>
- <span data-ttu-id="48268-119">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="48268-119">A digit</span></span>

<span data-ttu-id="48268-120">Unformatiert: 9 aufeinanderfolgende Ziffern, beginnend mit 0, 1, 2, 3, 6, 7 oder 8</span><span class="sxs-lookup"><span data-stu-id="48268-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="48268-121">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-121">Checksum</span></span>

<span data-ttu-id="48268-122">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-123">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-123">Definition</span></span>

<span data-ttu-id="48268-124">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-125">Die Funktion Func_aba_routing findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-126">Ein Schlüsselwort aus Keyword_ABA_Routing wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="48268-127">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="48268-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="48268-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="48268-129">ABA</span><span class="sxs-lookup"><span data-stu-id="48268-129">aba</span></span>
- <span data-ttu-id="48268-130">aba #</span><span class="sxs-lookup"><span data-stu-id="48268-130">aba #</span></span>
- <span data-ttu-id="48268-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="48268-131">aba routing #</span></span>
- <span data-ttu-id="48268-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="48268-132">aba routing number</span></span>
- <span data-ttu-id="48268-133">ABA #</span><span class="sxs-lookup"><span data-stu-id="48268-133">aba#</span></span>
- <span data-ttu-id="48268-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="48268-134">abarouting#</span></span>
- <span data-ttu-id="48268-135">aba number</span><span class="sxs-lookup"><span data-stu-id="48268-135">aba number</span></span>
- <span data-ttu-id="48268-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="48268-136">abaroutingnumber</span></span>
- <span data-ttu-id="48268-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="48268-137">american bank association routing #</span></span>
- <span data-ttu-id="48268-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="48268-138">american bank association routing number</span></span>
- <span data-ttu-id="48268-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="48268-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="48268-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="48268-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="48268-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="48268-141">bank routing number</span></span>
- <span data-ttu-id="48268-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="48268-142">bankrouting#</span></span>
- <span data-ttu-id="48268-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="48268-143">bankroutingnumber</span></span>
- <span data-ttu-id="48268-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="48268-144">routing transit number</span></span>
- <span data-ttu-id="48268-145">RTN</span><span class="sxs-lookup"><span data-stu-id="48268-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="48268-146">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="48268-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-147">Format</span><span class="sxs-lookup"><span data-stu-id="48268-147">Format</span></span>

<span data-ttu-id="48268-148">Acht Ziffern, durch Punkte getrennt</span><span class="sxs-lookup"><span data-stu-id="48268-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-149">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-149">Pattern</span></span>

<span data-ttu-id="48268-150">Acht Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-150">Eight digits:</span></span>
- <span data-ttu-id="48268-151">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-151">Two digits</span></span>
- <span data-ttu-id="48268-152">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="48268-152">A period</span></span>
- <span data-ttu-id="48268-153">Drei Ziffern </span><span class="sxs-lookup"><span data-stu-id="48268-153">Three digits</span></span>
- <span data-ttu-id="48268-154">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="48268-154">A period</span></span>
- <span data-ttu-id="48268-155">Drei Ziffern </span><span class="sxs-lookup"><span data-stu-id="48268-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-156">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-156">Checksum</span></span>

<span data-ttu-id="48268-157">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-158">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-158">Definition</span></span>

<span data-ttu-id="48268-159">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-160">Der reguläre Ausdruck Regex_argentina_national_id findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-161">Ein Schlüsselwort aus Keyword_argentina_national_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-162">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="48268-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="48268-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="48268-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="48268-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="48268-165">Identität</span><span class="sxs-lookup"><span data-stu-id="48268-165">Identity</span></span> 
- <span data-ttu-id="48268-166">Identification National Identity Card</span><span class="sxs-lookup"><span data-stu-id="48268-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="48268-167">DNI</span><span class="sxs-lookup"><span data-stu-id="48268-167">DNI</span></span> 
- <span data-ttu-id="48268-168">Nic-nationales Personenregister</span><span class="sxs-lookup"><span data-stu-id="48268-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="48268-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="48268-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="48268-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="48268-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="48268-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="48268-171">Identidad</span></span> 
- <span data-ttu-id="48268-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="48268-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="48268-173">Australische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="48268-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-174">Format</span><span class="sxs-lookup"><span data-stu-id="48268-174">Format</span></span>

<span data-ttu-id="48268-175">6-10 Stellen mit oder ohne Bankfilialnummer</span><span class="sxs-lookup"><span data-stu-id="48268-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-176">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-176">Pattern</span></span>

<span data-ttu-id="48268-177">Kontonummer hat 6-10 Stellen.</span><span class="sxs-lookup"><span data-stu-id="48268-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="48268-178">Australische Bankleitzahl:</span><span class="sxs-lookup"><span data-stu-id="48268-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="48268-179">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-179">Three digits</span></span> 
- <span data-ttu-id="48268-180">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-180">A hyphen</span></span> 
- <span data-ttu-id="48268-181">Drei Stellen</span><span class="sxs-lookup"><span data-stu-id="48268-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-182">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-182">Checksum</span></span>

<span data-ttu-id="48268-183">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-184">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-184">Definition</span></span>

<span data-ttu-id="48268-185">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-186">Der reguläre Ausdruck Regex_australia_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="48268-187">Ein Schlüsselwort aus Keyword_australia_bank_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="48268-188">Der reguläre Ausdruck Regex_australia_bank_account_number_bsb findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="48268-189">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-190">Der reguläre Ausdruck Regex_australia_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="48268-191">Ein Schlüsselwort aus Keyword_australia_bank_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-192">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="48268-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="48268-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="48268-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="48268-194">swift bank code</span></span>
- <span data-ttu-id="48268-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="48268-195">correspondent bank</span></span>
- <span data-ttu-id="48268-196">base currency</span><span class="sxs-lookup"><span data-stu-id="48268-196">base currency</span></span>
- <span data-ttu-id="48268-197">usa account</span><span class="sxs-lookup"><span data-stu-id="48268-197">usa account</span></span>
- <span data-ttu-id="48268-198">holder address</span><span class="sxs-lookup"><span data-stu-id="48268-198">holder address</span></span>
- <span data-ttu-id="48268-199">bank address</span><span class="sxs-lookup"><span data-stu-id="48268-199">bank address</span></span>
- <span data-ttu-id="48268-200">information account</span><span class="sxs-lookup"><span data-stu-id="48268-200">information account</span></span>
- <span data-ttu-id="48268-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="48268-201">fund transfers</span></span>
- <span data-ttu-id="48268-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="48268-202">bank charges</span></span>
- <span data-ttu-id="48268-203">bank details</span><span class="sxs-lookup"><span data-stu-id="48268-203">bank details</span></span>
- <span data-ttu-id="48268-204">banking information</span><span class="sxs-lookup"><span data-stu-id="48268-204">banking information</span></span>
- <span data-ttu-id="48268-205">full names</span><span class="sxs-lookup"><span data-stu-id="48268-205">full names</span></span>
- <span data-ttu-id="48268-206">IAEO</span><span class="sxs-lookup"><span data-stu-id="48268-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="48268-207">Australische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-208">Format</span><span class="sxs-lookup"><span data-stu-id="48268-208">Format</span></span>

<span data-ttu-id="48268-209">Neun Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-210">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-210">Pattern</span></span>

<span data-ttu-id="48268-211">Neun Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="48268-212">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="48268-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="48268-213">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-213">Two digits</span></span> 
- <span data-ttu-id="48268-214">Fünf Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="48268-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="48268-215">ODER</span><span class="sxs-lookup"><span data-stu-id="48268-215">OR</span></span>

- <span data-ttu-id="48268-216">1-2 optionale Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="48268-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="48268-217">4 bis 9 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-217">4-9 digits</span></span>

<span data-ttu-id="48268-218">ODER</span><span class="sxs-lookup"><span data-stu-id="48268-218">OR</span></span>

- <span data-ttu-id="48268-219">Neun Ziffern oder Buchstaben (Groß-/Kleinschreibung irrelevant)</span><span class="sxs-lookup"><span data-stu-id="48268-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-220">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-220">Checksum</span></span>

<span data-ttu-id="48268-221">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-222">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-222">Definition</span></span>

<span data-ttu-id="48268-223">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-224">Der reguläre Ausdruck Regex_australia_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-225">Ein Schlüsselwort aus Keyword_australia_drivers_license_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="48268-226">Es wurde kein Schlüsselwort aus Keyword_australia_drivers_license_number_exclusions gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-227">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="48268-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="48268-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="48268-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="48268-229">international driving permits</span></span>
- <span data-ttu-id="48268-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="48268-230">australian automobile association</span></span>
- <span data-ttu-id="48268-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="48268-231">international driving permit</span></span>
- <span data-ttu-id="48268-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="48268-232">DriverLicence</span></span>
- <span data-ttu-id="48268-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="48268-233">DriverLicences</span></span>
- <span data-ttu-id="48268-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="48268-234">Driver Lic</span></span>
- <span data-ttu-id="48268-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="48268-235">Driver Licence</span></span>
- <span data-ttu-id="48268-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="48268-236">Driver Licences</span></span>
- <span data-ttu-id="48268-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="48268-237">DriversLic</span></span>
- <span data-ttu-id="48268-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="48268-238">DriversLicence</span></span>
- <span data-ttu-id="48268-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="48268-239">DriversLicences</span></span>
- <span data-ttu-id="48268-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="48268-240">Drivers Lic</span></span>
- <span data-ttu-id="48268-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="48268-241">Drivers Lics</span></span>
- <span data-ttu-id="48268-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="48268-242">Drivers Licence</span></span>
- <span data-ttu-id="48268-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="48268-243">Drivers Licences</span></span>
- <span data-ttu-id="48268-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="48268-244">Driver'Lic</span></span>
- <span data-ttu-id="48268-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="48268-245">Driver'Lics</span></span>
- <span data-ttu-id="48268-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="48268-246">Driver'Licence</span></span>
- <span data-ttu-id="48268-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="48268-247">Driver'Licences</span></span>
- <span data-ttu-id="48268-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="48268-248">Driver' Lic</span></span>
- <span data-ttu-id="48268-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="48268-249">Driver' Lics</span></span>
- <span data-ttu-id="48268-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="48268-250">Driver' Licence</span></span>
- <span data-ttu-id="48268-251">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="48268-251">Driver' Licences</span></span>
- <span data-ttu-id="48268-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="48268-252">Driver'sLic</span></span>
- <span data-ttu-id="48268-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="48268-253">Driver'sLics</span></span>
- <span data-ttu-id="48268-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="48268-254">Driver'sLicence</span></span>
- <span data-ttu-id="48268-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="48268-255">Driver'sLicences</span></span>
- <span data-ttu-id="48268-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="48268-256">Driver's Lic</span></span>
- <span data-ttu-id="48268-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="48268-257">Driver's Lics</span></span>
- <span data-ttu-id="48268-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="48268-258">Driver's Licence</span></span>
- <span data-ttu-id="48268-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="48268-259">Driver's Licences</span></span>
- <span data-ttu-id="48268-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="48268-260">DriverLic#</span></span>
- <span data-ttu-id="48268-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="48268-261">DriverLics#</span></span>
- <span data-ttu-id="48268-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="48268-262">DriverLicence#</span></span>
- <span data-ttu-id="48268-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="48268-263">DriverLicences#</span></span>
- <span data-ttu-id="48268-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-264">Driver Lic#</span></span>
- <span data-ttu-id="48268-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-265">Driver Lics#</span></span>
- <span data-ttu-id="48268-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="48268-266">Driver Licence#</span></span>
- <span data-ttu-id="48268-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="48268-267">Driver Licences#</span></span>
- <span data-ttu-id="48268-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="48268-268">DriversLic#</span></span>
- <span data-ttu-id="48268-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="48268-269">DriversLics#</span></span>
- <span data-ttu-id="48268-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="48268-270">DriversLicence#</span></span>
- <span data-ttu-id="48268-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="48268-271">DriversLicences#</span></span>
- <span data-ttu-id="48268-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-272">Drivers Lic#</span></span>
- <span data-ttu-id="48268-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-273">Drivers Lics#</span></span>
- <span data-ttu-id="48268-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="48268-274">Drivers Licence#</span></span>
- <span data-ttu-id="48268-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="48268-275">Drivers Licences#</span></span>
- <span data-ttu-id="48268-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="48268-276">Driver'Lic#</span></span>
- <span data-ttu-id="48268-277">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="48268-277">Driver'Lics#</span></span>
- <span data-ttu-id="48268-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="48268-278">Driver'Licence#</span></span>
- <span data-ttu-id="48268-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="48268-279">Driver'Licences#</span></span>
- <span data-ttu-id="48268-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-280">Driver' Lic#</span></span>
- <span data-ttu-id="48268-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-281">Driver' Lics#</span></span>
- <span data-ttu-id="48268-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="48268-282">Driver' Licence#</span></span>
- <span data-ttu-id="48268-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="48268-283">Driver' Licences#</span></span>
- <span data-ttu-id="48268-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="48268-284">Driver'sLic#</span></span>
- <span data-ttu-id="48268-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="48268-285">Driver'sLics#</span></span>
- <span data-ttu-id="48268-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="48268-286">Driver'sLicence#</span></span>
- <span data-ttu-id="48268-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="48268-287">Driver'sLicences#</span></span>
- <span data-ttu-id="48268-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-288">Driver's Lic#</span></span>
- <span data-ttu-id="48268-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-289">Driver's Lics#</span></span>
- <span data-ttu-id="48268-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="48268-290">Driver's Licence#</span></span>
- <span data-ttu-id="48268-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="48268-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="48268-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="48268-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="48268-293">aaa</span><span class="sxs-lookup"><span data-stu-id="48268-293">aaa</span></span>
- <span data-ttu-id="48268-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="48268-294">DriverLicense</span></span>
- <span data-ttu-id="48268-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="48268-295">DriverLicenses</span></span>
- <span data-ttu-id="48268-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="48268-296">Driver License</span></span>
- <span data-ttu-id="48268-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-297">Driver Licenses</span></span>
- <span data-ttu-id="48268-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="48268-298">DriversLicense</span></span>
- <span data-ttu-id="48268-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="48268-299">DriversLicenses</span></span>
- <span data-ttu-id="48268-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="48268-300">Drivers License</span></span>
- <span data-ttu-id="48268-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-301">Drivers Licenses</span></span>
- <span data-ttu-id="48268-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="48268-302">Driver'License</span></span>
- <span data-ttu-id="48268-303">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-303">Driver'Licenses</span></span>
- <span data-ttu-id="48268-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="48268-304">Driver' License</span></span>
- <span data-ttu-id="48268-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-305">Driver' Licenses</span></span>
- <span data-ttu-id="48268-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="48268-306">Driver'sLicense</span></span>
- <span data-ttu-id="48268-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="48268-307">Driver'sLicenses</span></span>
- <span data-ttu-id="48268-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="48268-308">Driver's License</span></span>
- <span data-ttu-id="48268-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-309">Driver's Licenses</span></span>
- <span data-ttu-id="48268-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="48268-310">DriverLicense#</span></span>
- <span data-ttu-id="48268-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="48268-311">DriverLicenses#</span></span>
- <span data-ttu-id="48268-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="48268-312">Driver License#</span></span>
- <span data-ttu-id="48268-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-313">Driver Licenses#</span></span>
- <span data-ttu-id="48268-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="48268-314">DriversLicense#</span></span>
- <span data-ttu-id="48268-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="48268-315">DriversLicenses#</span></span>
- <span data-ttu-id="48268-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="48268-316">Drivers License#</span></span>
- <span data-ttu-id="48268-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-317">Drivers Licenses#</span></span>
- <span data-ttu-id="48268-318">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="48268-318">Driver'License#</span></span>
- <span data-ttu-id="48268-319">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="48268-319">Driver'Licenses#</span></span>
- <span data-ttu-id="48268-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="48268-320">Driver' License#</span></span>
- <span data-ttu-id="48268-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-321">Driver' Licenses#</span></span>
- <span data-ttu-id="48268-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="48268-322">Driver'sLicense#</span></span>
- <span data-ttu-id="48268-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="48268-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="48268-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="48268-324">Driver's License#</span></span>
- <span data-ttu-id="48268-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="48268-326">Australische Medical Account-Nummer</span><span class="sxs-lookup"><span data-stu-id="48268-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-327">Format</span><span class="sxs-lookup"><span data-stu-id="48268-327">Format</span></span>

<span data-ttu-id="48268-328">10-11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-329">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-329">Pattern</span></span>

<span data-ttu-id="48268-330">10-11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-330">10-11 digits:</span></span>
- <span data-ttu-id="48268-331">Erste Ziffer im Bereich von 2-6</span><span class="sxs-lookup"><span data-stu-id="48268-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="48268-332">Neunte Ziffer ist eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="48268-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="48268-333">Zehnte Ziffer ist die Ausgabeziffer</span><span class="sxs-lookup"><span data-stu-id="48268-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="48268-334">Elfte Ziffer (optional) ist die Einzelziffer</span><span class="sxs-lookup"><span data-stu-id="48268-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-335">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-335">Checksum</span></span>

<span data-ttu-id="48268-336">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-337">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-337">Definition</span></span>

<span data-ttu-id="48268-338">Eine DLP-Richtlinie ist zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-339">Die Funktion Func_australian_medical_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-340">Ein Schlüsselwort aus Keyword_Australia_Medical_Account_Number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="48268-341">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-341">The checksum passes.</span></span>

<span data-ttu-id="48268-342">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-343">Die Funktion Func_australian_medical_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-344">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-344">The checksum passes.</span></span>

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-345">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="48268-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="48268-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="48268-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="48268-347">bank account details</span></span>
- <span data-ttu-id="48268-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="48268-348">medicare payments</span></span>
- <span data-ttu-id="48268-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="48268-349">mortgage account</span></span>
- <span data-ttu-id="48268-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="48268-350">bank payments</span></span>
- <span data-ttu-id="48268-351">information branch</span><span class="sxs-lookup"><span data-stu-id="48268-351">information branch</span></span>
- <span data-ttu-id="48268-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="48268-352">credit card loan</span></span>
- <span data-ttu-id="48268-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="48268-353">department of human services</span></span>
- <span data-ttu-id="48268-354">local service</span><span class="sxs-lookup"><span data-stu-id="48268-354">local service</span></span>
- <span data-ttu-id="48268-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="48268-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="48268-356">Australische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="48268-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-357">Format</span><span class="sxs-lookup"><span data-stu-id="48268-357">Format</span></span>

<span data-ttu-id="48268-358">Ein Buchstabe gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-359">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-359">Pattern</span></span>

<span data-ttu-id="48268-360">Ein Buchstabe (Groß-/Kleinschreibung irrelevant) gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-361">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-361">Checksum</span></span>

<span data-ttu-id="48268-362">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-363">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-363">Definition</span></span>

<span data-ttu-id="48268-364">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-365">Der reguläre Ausdruck Regex_australia_passport_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-366">Ein Schlüsselwort aus Keyword_passport oder Keyword_australia_passport_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="48268-367">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="48268-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="48268-368">Keyword_passport</span></span>

- <span data-ttu-id="48268-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="48268-369">Passport Number</span></span>
- <span data-ttu-id="48268-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="48268-370">Passport No</span></span>
- <span data-ttu-id="48268-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="48268-371">Passport #</span></span>
- <span data-ttu-id="48268-372">Pass #</span><span class="sxs-lookup"><span data-stu-id="48268-372">Passport#</span></span>
- <span data-ttu-id="48268-373">Passport-Nr</span><span class="sxs-lookup"><span data-stu-id="48268-373">PassportID</span></span>
- <span data-ttu-id="48268-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="48268-374">Passportno</span></span>
- <span data-ttu-id="48268-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="48268-375">passportnumber</span></span>
- <span data-ttu-id="48268-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="48268-376">パスポート</span></span>
- <span data-ttu-id="48268-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="48268-377">パスポート番号</span></span>
- <span data-ttu-id="48268-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="48268-378">パスポートのNum</span></span>
- <span data-ttu-id="48268-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="48268-379">パスポート ＃</span></span> 
- <span data-ttu-id="48268-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="48268-380">Numéro de passeport</span></span>
- <span data-ttu-id="48268-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="48268-381">Passeport n °</span></span>
- <span data-ttu-id="48268-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="48268-382">Passeport Non</span></span>
- <span data-ttu-id="48268-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="48268-383">Passeport #</span></span>
- <span data-ttu-id="48268-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="48268-384">Passeport#</span></span>
- <span data-ttu-id="48268-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="48268-385">PasseportNon</span></span>
- <span data-ttu-id="48268-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="48268-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="48268-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="48268-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="48268-388">Pass</span><span class="sxs-lookup"><span data-stu-id="48268-388">passport</span></span>
- <span data-ttu-id="48268-389">passport details</span><span class="sxs-lookup"><span data-stu-id="48268-389">passport details</span></span>
- <span data-ttu-id="48268-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="48268-390">immigration and citizenship</span></span>
- <span data-ttu-id="48268-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="48268-391">commonwealth of australia</span></span>
- <span data-ttu-id="48268-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="48268-392">department of immigration</span></span>
- <span data-ttu-id="48268-393">residential address</span><span class="sxs-lookup"><span data-stu-id="48268-393">residential address</span></span>
- <span data-ttu-id="48268-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="48268-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="48268-395">Visa</span><span class="sxs-lookup"><span data-stu-id="48268-395">visa</span></span>
- <span data-ttu-id="48268-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="48268-396">national identity card</span></span>
- <span data-ttu-id="48268-397">passport number</span><span class="sxs-lookup"><span data-stu-id="48268-397">passport number</span></span>
- <span data-ttu-id="48268-398">travel document</span><span class="sxs-lookup"><span data-stu-id="48268-398">travel document</span></span>
- <span data-ttu-id="48268-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="48268-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="48268-400">Australische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="48268-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-401">Format</span><span class="sxs-lookup"><span data-stu-id="48268-401">Format</span></span>

<span data-ttu-id="48268-402">8-9 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-403">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-403">Pattern</span></span>

<span data-ttu-id="48268-404">8 bis 9 Ziffern, die in der Regel wie folgt mit Leerzeichen dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="48268-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="48268-405">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-405">Three digits</span></span> 
- <span data-ttu-id="48268-406">Ein optionales Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-406">An optional space</span></span> 
- <span data-ttu-id="48268-407">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-407">Three digits</span></span> 
- <span data-ttu-id="48268-408">Ein optionales Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-408">An optional space</span></span> 
- <span data-ttu-id="48268-409">2 bis 3 Ziffern, wobei die letzte Ziffer eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="48268-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-410">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-410">Checksum</span></span>

<span data-ttu-id="48268-411">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-412">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-412">Definition</span></span>

<span data-ttu-id="48268-413">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-414">Die Funktion Func_australian_tax_file_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-415">Es wurde kein Schlüsselwort aus Keyword_Australia_Tax_File_Number oder Keyword_number_exclusions gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="48268-416">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-417">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="48268-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="48268-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="48268-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="48268-419">australian business number</span></span>
- <span data-ttu-id="48268-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="48268-420">marginal tax rate</span></span>
- <span data-ttu-id="48268-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="48268-421">medicare levy</span></span>
- <span data-ttu-id="48268-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="48268-422">portfolio number</span></span>
- <span data-ttu-id="48268-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="48268-423">service veterans</span></span>
- <span data-ttu-id="48268-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="48268-424">withholding tax</span></span>
- <span data-ttu-id="48268-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="48268-425">individual tax return</span></span>
- <span data-ttu-id="48268-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="48268-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="48268-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="48268-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="48268-428">00000000</span><span class="sxs-lookup"><span data-stu-id="48268-428">00000000</span></span>
- <span data-ttu-id="48268-429">11111111</span><span class="sxs-lookup"><span data-stu-id="48268-429">11111111</span></span>
- <span data-ttu-id="48268-430">22222222</span><span class="sxs-lookup"><span data-stu-id="48268-430">22222222</span></span>
- <span data-ttu-id="48268-431">33333333</span><span class="sxs-lookup"><span data-stu-id="48268-431">33333333</span></span>
- <span data-ttu-id="48268-432">44444444</span><span class="sxs-lookup"><span data-stu-id="48268-432">44444444</span></span>
- <span data-ttu-id="48268-433">55555555</span><span class="sxs-lookup"><span data-stu-id="48268-433">55555555</span></span>
- <span data-ttu-id="48268-434">66666666</span><span class="sxs-lookup"><span data-stu-id="48268-434">66666666</span></span>
- <span data-ttu-id="48268-435">77777777</span><span class="sxs-lookup"><span data-stu-id="48268-435">77777777</span></span>
- <span data-ttu-id="48268-436">88888888</span><span class="sxs-lookup"><span data-stu-id="48268-436">88888888</span></span>
- <span data-ttu-id="48268-437">99999999</span><span class="sxs-lookup"><span data-stu-id="48268-437">99999999</span></span>
- <span data-ttu-id="48268-438">000000000</span><span class="sxs-lookup"><span data-stu-id="48268-438">000000000</span></span>
- <span data-ttu-id="48268-439">111111111</span><span class="sxs-lookup"><span data-stu-id="48268-439">111111111</span></span>
- <span data-ttu-id="48268-440">222222222</span><span class="sxs-lookup"><span data-stu-id="48268-440">222222222</span></span>
- <span data-ttu-id="48268-441">333333333</span><span class="sxs-lookup"><span data-stu-id="48268-441">333333333</span></span>
- <span data-ttu-id="48268-442">444444444</span><span class="sxs-lookup"><span data-stu-id="48268-442">444444444</span></span>
- <span data-ttu-id="48268-443">555555555</span><span class="sxs-lookup"><span data-stu-id="48268-443">555555555</span></span>
- <span data-ttu-id="48268-444">666666666</span><span class="sxs-lookup"><span data-stu-id="48268-444">666666666</span></span>
- <span data-ttu-id="48268-445">777777777</span><span class="sxs-lookup"><span data-stu-id="48268-445">777777777</span></span>
- <span data-ttu-id="48268-446">888888888</span><span class="sxs-lookup"><span data-stu-id="48268-446">888888888</span></span>
- <span data-ttu-id="48268-447">999999999</span><span class="sxs-lookup"><span data-stu-id="48268-447">999999999</span></span>
- <span data-ttu-id="48268-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="48268-448">0000000000</span></span>
- <span data-ttu-id="48268-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="48268-449">1111111111</span></span>
- <span data-ttu-id="48268-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="48268-450">2222222222</span></span>
- <span data-ttu-id="48268-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="48268-451">3333333333</span></span>
- <span data-ttu-id="48268-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="48268-452">4444444444</span></span>
- <span data-ttu-id="48268-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="48268-453">5555555555</span></span>
- <span data-ttu-id="48268-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="48268-454">6666666666</span></span>
- <span data-ttu-id="48268-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="48268-455">7777777777</span></span>
- <span data-ttu-id="48268-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="48268-456">8888888888</span></span>
- <span data-ttu-id="48268-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="48268-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="48268-458">Azure DocumentDB-Authentifizierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="48268-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="48268-459">Format</span><span class="sxs-lookup"><span data-stu-id="48268-459">Format</span></span>

<span data-ttu-id="48268-460">Die Zeichenfolge "DocumentDb" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="48268-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-461">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-461">Pattern</span></span>

- <span data-ttu-id="48268-462">Die Zeichenfolge "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="48268-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="48268-463">Eine beliebige Kombination von zwischen 3-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="48268-464">Ein größer als-Symbol (>), ein Gleichheitszeichen (=), ein Anführungszeichen (") oder ein Apostroph (')</span><span class="sxs-lookup"><span data-stu-id="48268-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="48268-465">Eine beliebige Kombination von 86 unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="48268-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="48268-466">Zwei Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-467">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-467">Checksum</span></span>

<span data-ttu-id="48268-468">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-469">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-469">Definition</span></span>

<span data-ttu-id="48268-470">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-471">Der reguläre Ausdruck CEP_Regex_AzureDocumentDBAuthKey findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-472">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-473">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="48268-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="48268-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="48268-475">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="48268-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="48268-476">contoso</span><span class="sxs-lookup"><span data-stu-id="48268-476">contoso</span></span>
- <span data-ttu-id="48268-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="48268-477">fabrikam</span></span>
- <span data-ttu-id="48268-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="48268-478">northwind</span></span>
- <span data-ttu-id="48268-479">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="48268-479">sandbox</span></span>
- <span data-ttu-id="48268-480">OneBox</span><span class="sxs-lookup"><span data-stu-id="48268-480">onebox</span></span>
- <span data-ttu-id="48268-481">localhost</span><span class="sxs-lookup"><span data-stu-id="48268-481">localhost</span></span>
- <span data-ttu-id="48268-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="48268-482">127.0.0.1</span></span>
- <span data-ttu-id="48268-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="48268-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="48268-484">com</span><span class="sxs-lookup"><span data-stu-id="48268-484">com</span></span>
- <span data-ttu-id="48268-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="48268-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="48268-486">NET</span><span class="sxs-lookup"><span data-stu-id="48268-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="48268-487">Azure IaaS-Datenbankverbindungszeichenfolge und Azure SQL-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="48268-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="48268-488">Format</span><span class="sxs-lookup"><span data-stu-id="48268-488">Format</span></span>

<span data-ttu-id="48268-489">Die Zeichenfolge "Server", "Server" oder "Datenquelle", gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten, einschließlich der Zeichenfolge "cloudapp. Azure" aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="48268-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="48268-490">com "oder" cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="48268-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="48268-491">NET "oder" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="48268-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="48268-492">NET "und die Zeichenfolge" Password "oder" Password "oder" pwd ".</span><span class="sxs-lookup"><span data-stu-id="48268-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-493">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-493">Pattern</span></span>

- <span data-ttu-id="48268-494">Die Zeichenfolge "Server", "Server" oder "Datenquelle"</span><span class="sxs-lookup"><span data-stu-id="48268-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="48268-495">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-496">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-496">An equal sign (=)</span></span>
- <span data-ttu-id="48268-497">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-498">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="48268-499">Die Zeichenfolge "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="48268-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="48268-500">com "," cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="48268-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="48268-501">NET "oder" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="48268-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="48268-502">NET</span><span class="sxs-lookup"><span data-stu-id="48268-502">net"</span></span>
- <span data-ttu-id="48268-503">Eine beliebige Kombination von zwischen 1-300 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="48268-504">Die Zeichenfolge "Password", "Password" oder "pwd"</span><span class="sxs-lookup"><span data-stu-id="48268-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="48268-505">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-506">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-506">An equal sign (=)</span></span>
- <span data-ttu-id="48268-507">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-508">Ein oder mehrere Zeichen, bei denen es sich nicht um ein Semikolon handelt (;), Anführungszeichen (") oder Apostroph (')</span><span class="sxs-lookup"><span data-stu-id="48268-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="48268-509">Ein Semikolon (;), Anführungszeichen (") oder Apostroph (')</span><span class="sxs-lookup"><span data-stu-id="48268-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-510">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-510">Checksum</span></span>

<span data-ttu-id="48268-511">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-512">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-512">Definition</span></span>

<span data-ttu-id="48268-513">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-514">Der reguläre Ausdruck CEP_Regex_AzureConnectionString findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-515">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-516">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="48268-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="48268-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="48268-518">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="48268-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="48268-519">contoso</span><span class="sxs-lookup"><span data-stu-id="48268-519">contoso</span></span>
- <span data-ttu-id="48268-520">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="48268-520">fabrikam</span></span>
- <span data-ttu-id="48268-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="48268-521">northwind</span></span>
- <span data-ttu-id="48268-522">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="48268-522">sandbox</span></span>
- <span data-ttu-id="48268-523">OneBox</span><span class="sxs-lookup"><span data-stu-id="48268-523">onebox</span></span>
- <span data-ttu-id="48268-524">localhost</span><span class="sxs-lookup"><span data-stu-id="48268-524">localhost</span></span>
- <span data-ttu-id="48268-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="48268-525">127.0.0.1</span></span>
- <span data-ttu-id="48268-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="48268-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="48268-527">com</span><span class="sxs-lookup"><span data-stu-id="48268-527">com</span></span>
- <span data-ttu-id="48268-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="48268-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="48268-529">NET</span><span class="sxs-lookup"><span data-stu-id="48268-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="48268-530">Azurey-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="48268-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="48268-531">Format</span><span class="sxs-lookup"><span data-stu-id="48268-531">Format</span></span>

<span data-ttu-id="48268-532">Die Zeichenfolge "Hostname" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten beschrieben sind, einschließlich der Zeichenfolgen "Azure-Devices".</span><span class="sxs-lookup"><span data-stu-id="48268-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="48268-533">NET "und" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="48268-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-534">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-534">Pattern</span></span>

- <span data-ttu-id="48268-535">Die Zeichenfolge "Hostname"</span><span class="sxs-lookup"><span data-stu-id="48268-535">The string "HostName"</span></span>
- <span data-ttu-id="48268-536">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-537">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-537">An equal sign (=)</span></span>
- <span data-ttu-id="48268-538">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-539">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="48268-540">Die Zeichenfolge "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="48268-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="48268-541">NET</span><span class="sxs-lookup"><span data-stu-id="48268-541">net"</span></span>
- <span data-ttu-id="48268-542">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="48268-543">Die Zeichenfolge "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="48268-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="48268-544">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-545">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-545">An equal sign (=)</span></span>
- <span data-ttu-id="48268-546">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-547">Eine beliebige Kombination von 43 unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="48268-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="48268-548">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-549">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-549">Checksum</span></span>

<span data-ttu-id="48268-550">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-551">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-551">Definition</span></span>

<span data-ttu-id="48268-552">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-553">Der reguläre Ausdruck CEP_Regex_AzureIoTConnectionString findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-554">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-555">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="48268-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="48268-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="48268-557">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="48268-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="48268-558">contoso</span><span class="sxs-lookup"><span data-stu-id="48268-558">contoso</span></span>
- <span data-ttu-id="48268-559">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="48268-559">fabrikam</span></span>
- <span data-ttu-id="48268-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="48268-560">northwind</span></span>
- <span data-ttu-id="48268-561">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="48268-561">sandbox</span></span>
- <span data-ttu-id="48268-562">OneBox</span><span class="sxs-lookup"><span data-stu-id="48268-562">onebox</span></span>
- <span data-ttu-id="48268-563">localhost</span><span class="sxs-lookup"><span data-stu-id="48268-563">localhost</span></span>
- <span data-ttu-id="48268-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="48268-564">127.0.0.1</span></span>
- <span data-ttu-id="48268-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="48268-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="48268-566">com</span><span class="sxs-lookup"><span data-stu-id="48268-566">com</span></span>
- <span data-ttu-id="48268-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="48268-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="48268-568">NET</span><span class="sxs-lookup"><span data-stu-id="48268-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="48268-569">Kennwort für Azure-Veröffentlichungseinstellung</span><span class="sxs-lookup"><span data-stu-id="48268-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="48268-570">Format</span><span class="sxs-lookup"><span data-stu-id="48268-570">Format</span></span>

<span data-ttu-id="48268-571">Die Zeichenfolge "benutzerkwt =" gefolgt von einer alphanumerischen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="48268-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-572">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-572">Pattern</span></span>

- <span data-ttu-id="48268-573">Die Zeichenfolge "benutzerkwt ="</span><span class="sxs-lookup"><span data-stu-id="48268-573">The string "userpwd="</span></span>
- <span data-ttu-id="48268-574">Eine beliebige Kombination von 60 Kleinbuchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="48268-575">Ein Anführungszeichen (")</span><span class="sxs-lookup"><span data-stu-id="48268-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-576">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-576">Checksum</span></span>

<span data-ttu-id="48268-577">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-578">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-578">Definition</span></span>

<span data-ttu-id="48268-579">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-580">Der reguläre Ausdruck CEP_Regex_AzurePublishSettingPasswords findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-581">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-582">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="48268-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="48268-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="48268-584">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="48268-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="48268-585">contoso</span><span class="sxs-lookup"><span data-stu-id="48268-585">contoso</span></span>
- <span data-ttu-id="48268-586">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="48268-586">fabrikam</span></span>
- <span data-ttu-id="48268-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="48268-587">northwind</span></span>
- <span data-ttu-id="48268-588">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="48268-588">sandbox</span></span>
- <span data-ttu-id="48268-589">OneBox</span><span class="sxs-lookup"><span data-stu-id="48268-589">onebox</span></span>
- <span data-ttu-id="48268-590">localhost</span><span class="sxs-lookup"><span data-stu-id="48268-590">localhost</span></span>
- <span data-ttu-id="48268-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="48268-591">127.0.0.1</span></span>
- <span data-ttu-id="48268-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="48268-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="48268-593">com</span><span class="sxs-lookup"><span data-stu-id="48268-593">com</span></span>
- <span data-ttu-id="48268-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="48268-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="48268-595">NET</span><span class="sxs-lookup"><span data-stu-id="48268-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="48268-596">Azure-Zeichenfolgen-Cache-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="48268-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="48268-597">Format</span><span class="sxs-lookup"><span data-stu-id="48268-597">Format</span></span>

<span data-ttu-id="48268-598">Die Zeichenfolge "" Codestring. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="48268-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="48268-599">NET ", gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster dargestellt werden, einschließlich der Zeichenfolge" Password "oder" pwd ".</span><span class="sxs-lookup"><span data-stu-id="48268-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-600">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-600">Pattern</span></span>

- <span data-ttu-id="48268-601">Die Zeichenfolge "" Codestring. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="48268-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="48268-602">NET</span><span class="sxs-lookup"><span data-stu-id="48268-602">net"</span></span>
- <span data-ttu-id="48268-603">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="48268-604">Die Zeichenfolge "Password" oder "pwd"</span><span class="sxs-lookup"><span data-stu-id="48268-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="48268-605">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-606">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-606">An equal sign (=)</span></span>
- <span data-ttu-id="48268-607">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-608">Eine beliebige Kombination von 43 Zeichen mit unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="48268-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="48268-609">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-610">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-610">Checksum</span></span>

<span data-ttu-id="48268-611">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-612">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-612">Definition</span></span>

<span data-ttu-id="48268-613">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-614">Der reguläre Ausdruck CEP_Regex_AzureRedisCacheConnectionString findet Inhalte, die mit dem Muster übereinstimmen..</span><span class="sxs-lookup"><span data-stu-id="48268-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="48268-615">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-616">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="48268-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="48268-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="48268-618">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="48268-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="48268-619">contoso</span><span class="sxs-lookup"><span data-stu-id="48268-619">contoso</span></span>
- <span data-ttu-id="48268-620">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="48268-620">fabrikam</span></span>
- <span data-ttu-id="48268-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="48268-621">northwind</span></span>
- <span data-ttu-id="48268-622">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="48268-622">sandbox</span></span>
- <span data-ttu-id="48268-623">OneBox</span><span class="sxs-lookup"><span data-stu-id="48268-623">onebox</span></span>
- <span data-ttu-id="48268-624">localhost</span><span class="sxs-lookup"><span data-stu-id="48268-624">localhost</span></span>
- <span data-ttu-id="48268-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="48268-625">127.0.0.1</span></span>
- <span data-ttu-id="48268-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="48268-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="48268-627">com</span><span class="sxs-lookup"><span data-stu-id="48268-627">com</span></span>
- <span data-ttu-id="48268-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="48268-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="48268-629">NET</span><span class="sxs-lookup"><span data-stu-id="48268-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="48268-630">Azure-SAS</span><span class="sxs-lookup"><span data-stu-id="48268-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="48268-631">Format</span><span class="sxs-lookup"><span data-stu-id="48268-631">Format</span></span>

<span data-ttu-id="48268-632">Die Zeichenfolge "SIG" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="48268-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-633">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-633">Pattern</span></span>

- <span data-ttu-id="48268-634">Die Zeichenfolge "SIG"</span><span class="sxs-lookup"><span data-stu-id="48268-634">The string "sig"</span></span>
- <span data-ttu-id="48268-635">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-636">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-636">An equal sign (=)</span></span>
- <span data-ttu-id="48268-637">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-638">Eine beliebige Kombination von zwischen 43-53 Zeichen, die klein-oder Großbuchstaben, Ziffern oder das Prozentzeichen (%)</span><span class="sxs-lookup"><span data-stu-id="48268-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="48268-639">Die Zeichenfolge "% 3D"</span><span class="sxs-lookup"><span data-stu-id="48268-639">The string "%3d"</span></span>
- <span data-ttu-id="48268-640">Ein beliebiges Zeichen, das kein niedriger oder groß geschriebener Buchstabe, eine Ziffer oder ein Prozentzeichen ist (%)</span><span class="sxs-lookup"><span data-stu-id="48268-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-641">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-641">Checksum</span></span>

<span data-ttu-id="48268-642">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-643">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-643">Definition</span></span>

<span data-ttu-id="48268-644">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-645">Der reguläre Ausdruck CEP_Regex_AzureSAS findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="48268-646">Azure Service Bus-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="48268-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="48268-647">Format</span><span class="sxs-lookup"><span data-stu-id="48268-647">Format</span></span>

<span data-ttu-id="48268-648">Die Zeichenfolge "Endpoint" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten, einschließlich der Zeichenfolgen "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="48268-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="48268-649">NET "und" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="48268-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-650">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-650">Pattern</span></span>

- <span data-ttu-id="48268-651">Die Zeichenfolge "Endpoint"</span><span class="sxs-lookup"><span data-stu-id="48268-651">The string "EndPoint"</span></span>
- <span data-ttu-id="48268-652">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-653">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-653">An equal sign (=)</span></span>
- <span data-ttu-id="48268-654">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-655">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="48268-656">Die Zeichenfolge "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="48268-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="48268-657">NET</span><span class="sxs-lookup"><span data-stu-id="48268-657">net"</span></span>
- <span data-ttu-id="48268-658">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="48268-659">Die Zeichenfolge "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="48268-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="48268-660">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-661">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-661">An equal sign (=)</span></span>
- <span data-ttu-id="48268-662">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-663">Eine beliebige Kombination von 43 Zeichen mit unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="48268-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="48268-664">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-665">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-665">Checksum</span></span>

<span data-ttu-id="48268-666">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-667">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-667">Definition</span></span>

<span data-ttu-id="48268-668">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-669">Der reguläre Ausdruck CEP_Regex_AzureServiceBusConnectionString findet Inhalte, die mit dem Muster übereinstimmen..</span><span class="sxs-lookup"><span data-stu-id="48268-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="48268-670">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-671">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="48268-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="48268-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="48268-673">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="48268-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="48268-674">contoso</span><span class="sxs-lookup"><span data-stu-id="48268-674">contoso</span></span>
- <span data-ttu-id="48268-675">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="48268-675">fabrikam</span></span>
- <span data-ttu-id="48268-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="48268-676">northwind</span></span>
- <span data-ttu-id="48268-677">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="48268-677">sandbox</span></span>
- <span data-ttu-id="48268-678">OneBox</span><span class="sxs-lookup"><span data-stu-id="48268-678">onebox</span></span>
- <span data-ttu-id="48268-679">localhost</span><span class="sxs-lookup"><span data-stu-id="48268-679">localhost</span></span>
- <span data-ttu-id="48268-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="48268-680">127.0.0.1</span></span>
- <span data-ttu-id="48268-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="48268-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="48268-682">com</span><span class="sxs-lookup"><span data-stu-id="48268-682">com</span></span>
- <span data-ttu-id="48268-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="48268-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="48268-684">NET</span><span class="sxs-lookup"><span data-stu-id="48268-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="48268-685">Azure Storage-Kontoschlüssel</span><span class="sxs-lookup"><span data-stu-id="48268-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="48268-686">Format</span><span class="sxs-lookup"><span data-stu-id="48268-686">Format</span></span>

<span data-ttu-id="48268-687">Die Zeichenfolge "DefaultEndpointsProtocol", gefolgt von den Zeichen und Zeichenfolgen, die in dem Muster unten, einschließlich der Zeichenfolge "AccountKey", dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="48268-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-688">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-688">Pattern</span></span>

- <span data-ttu-id="48268-689">Die Zeichenfolge "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="48268-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="48268-690">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-691">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-691">An equal sign (=)</span></span>
- <span data-ttu-id="48268-692">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-693">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="48268-694">Die Zeichenfolge "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="48268-694">The string "AccountKey"</span></span>
- <span data-ttu-id="48268-695">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-696">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-696">An equal sign (=)</span></span>
- <span data-ttu-id="48268-697">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="48268-698">Eine beliebige Kombination von 86 Zeichen mit unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="48268-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="48268-699">Zwei Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-700">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-700">Checksum</span></span>

<span data-ttu-id="48268-701">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-702">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-702">Definition</span></span>

<span data-ttu-id="48268-703">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-704">Der reguläre Ausdruck CEP_Regex_AzureStorageAccountKey findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-705">Der reguläre Ausdruck CEP_AzureEmulatorStorageAccountFilter findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="48268-706">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-707">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="48268-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="48268-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="48268-709">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="48268-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="48268-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="48268-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="48268-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="48268-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="48268-712">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="48268-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="48268-713">contoso</span><span class="sxs-lookup"><span data-stu-id="48268-713">contoso</span></span>
- <span data-ttu-id="48268-714">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="48268-714">fabrikam</span></span>
- <span data-ttu-id="48268-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="48268-715">northwind</span></span>
- <span data-ttu-id="48268-716">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="48268-716">sandbox</span></span>
- <span data-ttu-id="48268-717">OneBox</span><span class="sxs-lookup"><span data-stu-id="48268-717">onebox</span></span>
- <span data-ttu-id="48268-718">localhost</span><span class="sxs-lookup"><span data-stu-id="48268-718">localhost</span></span>
- <span data-ttu-id="48268-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="48268-719">127.0.0.1</span></span>
- <span data-ttu-id="48268-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="48268-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="48268-721">com</span><span class="sxs-lookup"><span data-stu-id="48268-721">com</span></span>
- <span data-ttu-id="48268-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="48268-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="48268-723">NET</span><span class="sxs-lookup"><span data-stu-id="48268-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="48268-724">Azure Storage-Kontoschlüssel (generisch)</span><span class="sxs-lookup"><span data-stu-id="48268-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="48268-725">Format</span><span class="sxs-lookup"><span data-stu-id="48268-725">Format</span></span>

<span data-ttu-id="48268-726">Eine beliebige Kombination von 86 unter-oder Großbuchstaben, Ziffern, den Schrägstrich (/) oder Pluszeichen (+), vorangestellt oder gefolgt von den im Muster unten beschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="48268-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-727">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-727">Pattern</span></span>

- <span data-ttu-id="48268-728">0-1 des größer als-Symbols (>), Apostroph ('), Gleichheitszeichen (=), Anführungszeichen (") oder Nummernzeichen (#)</span><span class="sxs-lookup"><span data-stu-id="48268-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="48268-729">Eine beliebige Kombination von 86 Zeichen mit unter-oder Großbuchstaben, Ziffern, dem Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="48268-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="48268-730">Zwei Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="48268-731">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-731">Checksum</span></span>

<span data-ttu-id="48268-732">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-733">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-733">Definition</span></span>

<span data-ttu-id="48268-734">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-735">Der reguläre Ausdruck CEP_Regex_AzureStorageAccountKeyGeneric findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="48268-736">Belgien – Nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="48268-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-737">Format</span><span class="sxs-lookup"><span data-stu-id="48268-737">Format</span></span>

<span data-ttu-id="48268-738">11 Ziffern plus Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-739">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-739">Pattern</span></span>

<span data-ttu-id="48268-740">11 Ziffern plus Trennzeichen:</span><span class="sxs-lookup"><span data-stu-id="48268-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="48268-741">Sechs Ziffern und zwei Punkte im Format JJ.MM.TT für das Geburtsdatum </span><span class="sxs-lookup"><span data-stu-id="48268-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="48268-742">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-742">A hyphen</span></span> 
- <span data-ttu-id="48268-743">Drei aufeinander folgende Ziffern (ungerade für Männer, gerade für Frauen) </span><span class="sxs-lookup"><span data-stu-id="48268-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="48268-744">Ein Punkt</span><span class="sxs-lookup"><span data-stu-id="48268-744">A period</span></span> 
- <span data-ttu-id="48268-745">Zwei Ziffern als Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="48268-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-746">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-746">Checksum</span></span>

<span data-ttu-id="48268-747">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-748">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-748">Definition</span></span>

<span data-ttu-id="48268-749">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-750">Die Funktion Func_belgium_national_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-751">Ein Schlüsselwort aus Keyword_belgium_national_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="48268-752">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-753">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="48268-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="48268-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="48268-755">Identität</span><span class="sxs-lookup"><span data-stu-id="48268-755">Identity</span></span>
- <span data-ttu-id="48268-756">Registrierung</span><span class="sxs-lookup"><span data-stu-id="48268-756">Registration</span></span>
- <span data-ttu-id="48268-757">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="48268-757">Identification</span></span> 
- <span data-ttu-id="48268-758">ID</span><span class="sxs-lookup"><span data-stu-id="48268-758">ID</span></span> 
- <span data-ttu-id="48268-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="48268-759">Identiteitskaart</span></span>
- <span data-ttu-id="48268-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="48268-760">Registratie nummer</span></span> 
- <span data-ttu-id="48268-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="48268-761">Identificatie nummer</span></span> 
- <span data-ttu-id="48268-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="48268-762">Identiteit</span></span>
- <span data-ttu-id="48268-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="48268-763">Registratie</span></span>
- <span data-ttu-id="48268-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="48268-764">Identificatie</span></span> 
- <span data-ttu-id="48268-765">Carte d ' identité</span><span class="sxs-lookup"><span data-stu-id="48268-765">Carte d'identité</span></span> 
- <span data-ttu-id="48268-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="48268-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="48268-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="48268-767">numéro d'identification</span></span>
- <span data-ttu-id="48268-768">identité</span><span class="sxs-lookup"><span data-stu-id="48268-768">identité</span></span> 
- <span data-ttu-id="48268-769">Inschrift</span><span class="sxs-lookup"><span data-stu-id="48268-769">inscription</span></span> 
- <span data-ttu-id="48268-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="48268-770">Identifikation</span></span>
- <span data-ttu-id="48268-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="48268-771">Identifizierung</span></span>
- <span data-ttu-id="48268-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-772">Identifikationsnummer</span></span>
- <span data-ttu-id="48268-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="48268-773">Personalausweis</span></span>
- <span data-ttu-id="48268-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="48268-774">Registrierung</span></span>
- <span data-ttu-id="48268-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="48268-776">Brazil CPF Number</span><span class="sxs-lookup"><span data-stu-id="48268-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-777">Format</span><span class="sxs-lookup"><span data-stu-id="48268-777">Format</span></span>

<span data-ttu-id="48268-778">11 Ziffern, die eine Prüfziffer umfassen und die formatiert oder unformatiert sein können</span><span class="sxs-lookup"><span data-stu-id="48268-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-779">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-779">Pattern</span></span>

<span data-ttu-id="48268-780">Formatiert</span><span class="sxs-lookup"><span data-stu-id="48268-780">Formatted:</span></span>
- <span data-ttu-id="48268-781">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-781">Three digits</span></span> 
- <span data-ttu-id="48268-782">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="48268-782">A period</span></span> 
- <span data-ttu-id="48268-783">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-783">Three digits</span></span> 
- <span data-ttu-id="48268-784">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="48268-784">A period</span></span> 
- <span data-ttu-id="48268-785">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-785">Three digits</span></span> 
- <span data-ttu-id="48268-786">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-786">A hyphen</span></span> 
- <span data-ttu-id="48268-787">Zwei Ziffern, die Prüfziffern sind</span><span class="sxs-lookup"><span data-stu-id="48268-787">Two digits which are check digits</span></span>

<span data-ttu-id="48268-788">Unformatiert</span><span class="sxs-lookup"><span data-stu-id="48268-788">Unformatted:</span></span>
- <span data-ttu-id="48268-789">11 Ziffern, wobei die letzten beiden Ziffern Prüfziffern sind</span><span class="sxs-lookup"><span data-stu-id="48268-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-790">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-790">Checksum</span></span>

<span data-ttu-id="48268-791">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-792">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-792">Definition</span></span>

<span data-ttu-id="48268-793">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-794">Die Funktion Func_brazil_cpf sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-795">Ein Schlüsselwort aus Keyword_brazil_cpf wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="48268-796">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-796">The checksum passes.</span></span>

<span data-ttu-id="48268-797">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-798">Die Funktion Func_brazil_cpf sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-799">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-799">The checksum passes.</span></span>

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-800">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="48268-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="48268-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="48268-802">CPF</span><span class="sxs-lookup"><span data-stu-id="48268-802">CPF</span></span>
- <span data-ttu-id="48268-803">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="48268-803">Identification</span></span>
- <span data-ttu-id="48268-804">Registrierung</span><span class="sxs-lookup"><span data-stu-id="48268-804">Registration</span></span>
- <span data-ttu-id="48268-805">Umsatz</span><span class="sxs-lookup"><span data-stu-id="48268-805">Revenue</span></span>
- <span data-ttu-id="48268-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="48268-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="48268-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="48268-807">Imposto</span></span> 
- <span data-ttu-id="48268-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="48268-808">Identificação</span></span> 
- <span data-ttu-id="48268-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="48268-809">Inscrição</span></span> 
- <span data-ttu-id="48268-810">Receita</span><span class="sxs-lookup"><span data-stu-id="48268-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="48268-811">Brasilien – Juristische Personennummer (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="48268-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="48268-812">Format</span><span class="sxs-lookup"><span data-stu-id="48268-812">Format</span></span>

<span data-ttu-id="48268-813">14 Ziffern, die eine Registrierungsnummer, eine Zweignummer und Prüfnziffern sowie Trennzeichen umfassen</span><span class="sxs-lookup"><span data-stu-id="48268-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-814">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-814">Pattern</span></span>
<span data-ttu-id="48268-815">14 Ziffern plus Trennzeichen:</span><span class="sxs-lookup"><span data-stu-id="48268-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="48268-816">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-816">Two digits</span></span> 
- <span data-ttu-id="48268-817">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="48268-817">A period</span></span> 
- <span data-ttu-id="48268-818">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-818">Three digits</span></span> 
- <span data-ttu-id="48268-819">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="48268-819">A period</span></span> 
- <span data-ttu-id="48268-820">Drei Ziffern (diese ersten acht Ziffern sind die Registrierungsnummer) </span><span class="sxs-lookup"><span data-stu-id="48268-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="48268-821">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="48268-821">A forward slash</span></span> 
- <span data-ttu-id="48268-822">Vierstellige Zweignummer </span><span class="sxs-lookup"><span data-stu-id="48268-822">Four-digit branch number</span></span> 
- <span data-ttu-id="48268-823">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-823">A hyphen</span></span> 
- <span data-ttu-id="48268-824">Zwei Ziffern, die Prüfziffern sind</span><span class="sxs-lookup"><span data-stu-id="48268-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-825">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-825">Checksum</span></span>

<span data-ttu-id="48268-826">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-827">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-827">Definition</span></span>

<span data-ttu-id="48268-828">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-829">Die Funktion Func_brazil_cnpj sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-830">Ein Schlüsselwort aus Keyword_brazil_cnpj wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="48268-831">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-831">The checksum passes.</span></span>

<span data-ttu-id="48268-832">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-833">Die Funktion Func_brazil_cnpj sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-834">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-834">The checksum passes.</span></span>

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-835">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="48268-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="48268-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="48268-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="48268-837">CNPJ</span></span> 
- <span data-ttu-id="48268-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="48268-838">CNPJ/MF</span></span> 
- <span data-ttu-id="48268-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="48268-839">CNPJ-MF</span></span> 
- <span data-ttu-id="48268-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="48268-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="48268-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="48268-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="48268-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="48268-842">Legal entity</span></span> 
- <span data-ttu-id="48268-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="48268-843">Legal entities</span></span> 
- <span data-ttu-id="48268-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="48268-844">Registration Status</span></span> 
- <span data-ttu-id="48268-845">Business</span><span class="sxs-lookup"><span data-stu-id="48268-845">Business</span></span> 
- <span data-ttu-id="48268-846">Company</span><span class="sxs-lookup"><span data-stu-id="48268-846">Company</span></span>
- <span data-ttu-id="48268-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="48268-847">CNPJ</span></span> 
- <span data-ttu-id="48268-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="48268-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="48268-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="48268-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="48268-850">CGC</span><span class="sxs-lookup"><span data-stu-id="48268-850">CGC</span></span> 
- <span data-ttu-id="48268-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="48268-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="48268-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="48268-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="48268-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="48268-853">Situação cadastral</span></span> 
- <span data-ttu-id="48268-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="48268-854">Inscrição</span></span> 
- <span data-ttu-id="48268-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="48268-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="48268-856">	Brasilien – Personalausweis (RG)</span><span class="sxs-lookup"><span data-stu-id="48268-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="48268-857">Format</span><span class="sxs-lookup"><span data-stu-id="48268-857">Format</span></span>

<span data-ttu-id="48268-858">Registro Geral (altes Format): neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="48268-859">Registro de Identidade (RIC) (neues Format): 11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-860">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-860">Pattern</span></span>

<span data-ttu-id="48268-861">Registro Geral (altes Format):</span><span class="sxs-lookup"><span data-stu-id="48268-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="48268-862">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-862">Two digits</span></span> 
- <span data-ttu-id="48268-863">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="48268-863">A period</span></span> 
- <span data-ttu-id="48268-864">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-864">Three digits</span></span> 
- <span data-ttu-id="48268-865">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="48268-865">A period</span></span> 
- <span data-ttu-id="48268-866">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-866">Three digits</span></span> 
- <span data-ttu-id="48268-867">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-867">A hyphen</span></span> 
- <span data-ttu-id="48268-868">Eine Ziffer als Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="48268-868">One digit which is a check digit</span></span>

<span data-ttu-id="48268-869">Registro de Identidade (RIC) (neues Format):</span><span class="sxs-lookup"><span data-stu-id="48268-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="48268-870">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-870">10 digits</span></span> 
- <span data-ttu-id="48268-871">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-871">A hyphen</span></span> 
- <span data-ttu-id="48268-872">Eine Ziffer als Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="48268-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-873">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-873">Checksum</span></span>

<span data-ttu-id="48268-874">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-875">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-875">Definition</span></span>

<span data-ttu-id="48268-876">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-877">Die Funktion Func_brazil_rg sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-878">Ein Schlüsselwort aus Keyword_brazil_rg wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="48268-879">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-879">The checksum passes.</span></span>

<span data-ttu-id="48268-880">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-881">Die Funktion Func_brazil_rg sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-882">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-882">The checksum passes.</span></span>

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-883">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="48268-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="48268-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="48268-885">Cédula de identidade Personalausweis National ID número de rregistro Registro de Iidentidade Registro Geral RG (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung beachtet) RIC (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung beachtet)</span><span class="sxs-lookup"><span data-stu-id="48268-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="48268-886">Kanadische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="48268-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-887">Format</span><span class="sxs-lookup"><span data-stu-id="48268-887">Format</span></span>

<span data-ttu-id="48268-888">Sieben oder zwölf Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-889">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-889">Pattern</span></span>

<span data-ttu-id="48268-890">Eine kanadische Kontonummer umfasst sieben oder zwölf Ziffern.</span><span class="sxs-lookup"><span data-stu-id="48268-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="48268-891">Eine kanadische Bankkontonummer setzt sich wie folgt zusammen:</span><span class="sxs-lookup"><span data-stu-id="48268-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="48268-892">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-892">Five digits</span></span> 
- <span data-ttu-id="48268-893">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-893">A hyphen</span></span> 
- <span data-ttu-id="48268-894">Drei Ziffern oder</span><span class="sxs-lookup"><span data-stu-id="48268-894">Three digits OR</span></span>
- <span data-ttu-id="48268-895">Eine 0 (null) </span><span class="sxs-lookup"><span data-stu-id="48268-895">A zero "0"</span></span> 
- <span data-ttu-id="48268-896">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-897">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-897">Checksum</span></span>

<span data-ttu-id="48268-898">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-899">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-899">Definition</span></span>

<span data-ttu-id="48268-900">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-901">Der reguläre Ausdruck Regex_canada_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-902">Ein Schlüsselwort aus Keyword_canada_bank_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="48268-903">Der reguläre Ausdruck Regex_canada_bank_account_transit_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="48268-904">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-905">Der reguläre Ausdruck Regex_canada_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-906">Ein Schlüsselwort aus Keyword_canada_bank_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-907">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="48268-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="48268-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="48268-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="48268-909">canada savings bonds</span></span>
- <span data-ttu-id="48268-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="48268-910">canada revenue agency</span></span>
- <span data-ttu-id="48268-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="48268-911">canadian financial institution</span></span>
- <span data-ttu-id="48268-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="48268-912">direct deposit form</span></span>
- <span data-ttu-id="48268-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="48268-913">canadian citizen</span></span>
- <span data-ttu-id="48268-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="48268-914">legal representative</span></span>
- <span data-ttu-id="48268-915">notary public</span><span class="sxs-lookup"><span data-stu-id="48268-915">notary public</span></span>
- <span data-ttu-id="48268-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="48268-916">commissioner for oaths</span></span>
- <span data-ttu-id="48268-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="48268-917">child care benefit</span></span>
- <span data-ttu-id="48268-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="48268-918">universal child care</span></span>
- <span data-ttu-id="48268-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="48268-919">canada child tax benefit</span></span>
- <span data-ttu-id="48268-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="48268-920">income tax benefit</span></span>
- <span data-ttu-id="48268-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="48268-921">harmonized sales tax</span></span>
- <span data-ttu-id="48268-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="48268-922">social insurance number</span></span>
- <span data-ttu-id="48268-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="48268-923">income tax refund</span></span>
- <span data-ttu-id="48268-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="48268-924">child tax benefit</span></span>
- <span data-ttu-id="48268-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="48268-925">territorial payments</span></span>
- <span data-ttu-id="48268-926">institution number</span><span class="sxs-lookup"><span data-stu-id="48268-926">institution number</span></span>
- <span data-ttu-id="48268-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="48268-927">deposit request</span></span>
- <span data-ttu-id="48268-928">banking information</span><span class="sxs-lookup"><span data-stu-id="48268-928">banking information</span></span>
- <span data-ttu-id="48268-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="48268-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="48268-930">Kanadische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-931">Format</span><span class="sxs-lookup"><span data-stu-id="48268-931">Format</span></span>

<span data-ttu-id="48268-932">Variiert je nach Provinz</span><span class="sxs-lookup"><span data-stu-id="48268-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-933">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-933">Pattern</span></span>

<span data-ttu-id="48268-934">Verschiedene Muster in Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec und Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="48268-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-935">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-935">Checksum</span></span>

<span data-ttu-id="48268-936">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-937">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-937">Definition</span></span>

<span data-ttu-id="48268-938">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-939">Die Funktion Func_[province_name]_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-940">Ein Schlüsselwort aus Keyword_[province_name]_drivers_license_name wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="48268-941">Ein Schlüsselwort aus Keyword_canada_drivers_license wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-942">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="48268-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="48268-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="48268-944">Die Abkürzung für die Provinz, z. B. AB</span><span class="sxs-lookup"><span data-stu-id="48268-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="48268-945">Der Name der Provinz, beispielsweise „Alberta“</span><span class="sxs-lookup"><span data-stu-id="48268-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="48268-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="48268-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="48268-947">DL</span><span class="sxs-lookup"><span data-stu-id="48268-947">DL</span></span>
- <span data-ttu-id="48268-948">DLS</span><span class="sxs-lookup"><span data-stu-id="48268-948">DLS</span></span>
- <span data-ttu-id="48268-949">CDL</span><span class="sxs-lookup"><span data-stu-id="48268-949">CDL</span></span>
- <span data-ttu-id="48268-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="48268-950">CDLS</span></span>
- <span data-ttu-id="48268-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="48268-951">DriverLic</span></span>
- <span data-ttu-id="48268-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="48268-952">DriverLics</span></span>
- <span data-ttu-id="48268-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="48268-953">DriverLicense</span></span>
- <span data-ttu-id="48268-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="48268-954">DriverLicenses</span></span>
- <span data-ttu-id="48268-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="48268-955">DriverLicence</span></span>
- <span data-ttu-id="48268-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="48268-956">DriverLicences</span></span>
- <span data-ttu-id="48268-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="48268-957">Driver Lic</span></span>
- <span data-ttu-id="48268-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="48268-958">Driver Lics</span></span>
- <span data-ttu-id="48268-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="48268-959">Driver License</span></span>
- <span data-ttu-id="48268-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-960">Driver Licenses</span></span>
- <span data-ttu-id="48268-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="48268-961">Driver Licence</span></span>
- <span data-ttu-id="48268-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="48268-962">Driver Licences</span></span>
- <span data-ttu-id="48268-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="48268-963">DriversLic</span></span>
- <span data-ttu-id="48268-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="48268-964">DriversLics</span></span>
- <span data-ttu-id="48268-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="48268-965">DriversLicence</span></span>
- <span data-ttu-id="48268-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="48268-966">DriversLicences</span></span>
- <span data-ttu-id="48268-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="48268-967">DriversLicense</span></span>
- <span data-ttu-id="48268-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="48268-968">DriversLicenses</span></span>
- <span data-ttu-id="48268-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="48268-969">Drivers Lic</span></span>
- <span data-ttu-id="48268-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="48268-970">Drivers Lics</span></span>
- <span data-ttu-id="48268-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="48268-971">Drivers License</span></span>
- <span data-ttu-id="48268-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-972">Drivers Licenses</span></span>
- <span data-ttu-id="48268-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="48268-973">Drivers Licence</span></span>
- <span data-ttu-id="48268-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="48268-974">Drivers Licences</span></span>
- <span data-ttu-id="48268-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="48268-975">Driver'Lic</span></span>
- <span data-ttu-id="48268-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="48268-976">Driver'Lics</span></span>
- <span data-ttu-id="48268-977">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="48268-977">Driver'License</span></span>
- <span data-ttu-id="48268-978">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-978">Driver'Licenses</span></span>
- <span data-ttu-id="48268-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="48268-979">Driver'Licence</span></span>
- <span data-ttu-id="48268-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="48268-980">Driver'Licences</span></span>
- <span data-ttu-id="48268-981">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="48268-981">Driver' Lic</span></span>
- <span data-ttu-id="48268-982">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="48268-982">Driver' Lics</span></span>
- <span data-ttu-id="48268-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="48268-983">Driver' License</span></span>
- <span data-ttu-id="48268-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-984">Driver' Licenses</span></span>
- <span data-ttu-id="48268-985">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="48268-985">Driver' Licence</span></span>
- <span data-ttu-id="48268-986">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="48268-986">Driver' Licences</span></span>
- <span data-ttu-id="48268-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="48268-987">Driver'sLic</span></span>
- <span data-ttu-id="48268-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="48268-988">Driver'sLics</span></span>
- <span data-ttu-id="48268-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="48268-989">Driver'sLicense</span></span>
- <span data-ttu-id="48268-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="48268-990">Driver'sLicenses</span></span>
- <span data-ttu-id="48268-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="48268-991">Driver'sLicence</span></span>
- <span data-ttu-id="48268-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="48268-992">Driver'sLicences</span></span>
- <span data-ttu-id="48268-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="48268-993">Driver's Lic</span></span>
- <span data-ttu-id="48268-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="48268-994">Driver's Lics</span></span>
- <span data-ttu-id="48268-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="48268-995">Driver's License</span></span>
- <span data-ttu-id="48268-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-996">Driver's Licenses</span></span>
- <span data-ttu-id="48268-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="48268-997">Driver's Licence</span></span>
- <span data-ttu-id="48268-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="48268-998">Driver's Licences</span></span>
- <span data-ttu-id="48268-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="48268-999">Permis de Conduire</span></span>
- <span data-ttu-id="48268-1000">id</span><span class="sxs-lookup"><span data-stu-id="48268-1000">id</span></span>
- <span data-ttu-id="48268-1001">ids</span><span class="sxs-lookup"><span data-stu-id="48268-1001">ids</span></span>
- <span data-ttu-id="48268-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="48268-1002">idcard number</span></span>
- <span data-ttu-id="48268-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="48268-1003">idcard numbers</span></span>
- <span data-ttu-id="48268-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="48268-1004">idcard #</span></span>
- <span data-ttu-id="48268-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="48268-1005">idcard #s</span></span>
- <span data-ttu-id="48268-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="48268-1006">idcard card</span></span>
- <span data-ttu-id="48268-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="48268-1007">idcard cards</span></span>
- <span data-ttu-id="48268-1008">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="48268-1008">idcard</span></span>
- <span data-ttu-id="48268-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="48268-1009">identification number</span></span>
- <span data-ttu-id="48268-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="48268-1010">identification numbers</span></span>
- <span data-ttu-id="48268-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="48268-1011">identification #</span></span>
- <span data-ttu-id="48268-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="48268-1012">identification #s</span></span>
- <span data-ttu-id="48268-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="48268-1013">identification card</span></span>
- <span data-ttu-id="48268-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="48268-1014">identification cards</span></span>
- <span data-ttu-id="48268-1015">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="48268-1015">identification</span></span> 
- <span data-ttu-id="48268-1016">DL #</span><span class="sxs-lookup"><span data-stu-id="48268-1016">DL#</span></span>
- <span data-ttu-id="48268-1017">DLS #</span><span class="sxs-lookup"><span data-stu-id="48268-1017">DLS#</span></span> 
- <span data-ttu-id="48268-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="48268-1018">CDL#</span></span> 
- <span data-ttu-id="48268-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="48268-1019">CDLS#</span></span> 
- <span data-ttu-id="48268-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="48268-1020">DriverLic#</span></span> 
- <span data-ttu-id="48268-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="48268-1021">DriverLics#</span></span> 
- <span data-ttu-id="48268-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="48268-1022">DriverLicense#</span></span> 
- <span data-ttu-id="48268-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="48268-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="48268-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="48268-1024">DriverLicence#</span></span> 
- <span data-ttu-id="48268-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="48268-1025">DriverLicences#</span></span> 
- <span data-ttu-id="48268-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-1026">Driver Lic#</span></span>
- <span data-ttu-id="48268-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-1027">Driver Lics#</span></span> 
- <span data-ttu-id="48268-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="48268-1028">Driver License#</span></span> 
- <span data-ttu-id="48268-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="48268-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="48268-1030">Driver License#</span></span> 
- <span data-ttu-id="48268-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="48268-1031">Driver Licences#</span></span> 
- <span data-ttu-id="48268-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="48268-1032">DriversLic#</span></span> 
- <span data-ttu-id="48268-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="48268-1033">DriversLics#</span></span> 
- <span data-ttu-id="48268-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="48268-1034">DriversLicense#</span></span> 
- <span data-ttu-id="48268-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="48268-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="48268-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="48268-1036">DriversLicence#</span></span> 
- <span data-ttu-id="48268-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="48268-1037">DriversLicences#</span></span> 
- <span data-ttu-id="48268-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="48268-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="48268-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="48268-1040">Drivers License#</span></span> 
- <span data-ttu-id="48268-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="48268-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="48268-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="48268-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="48268-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="48268-1044">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="48268-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="48268-1045">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="48268-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="48268-1046">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="48268-1046">Driver'License#</span></span> 
- <span data-ttu-id="48268-1047">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="48268-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="48268-1048">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="48268-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="48268-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="48268-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="48268-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="48268-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="48268-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="48268-1052">Driver' License#</span></span> 
- <span data-ttu-id="48268-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="48268-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="48268-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="48268-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="48268-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="48268-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="48268-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="48268-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="48268-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="48268-1058">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="48268-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="48268-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="48268-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="48268-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="48268-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="48268-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="48268-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="48268-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="48268-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="48268-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="48268-1064">Driver's License#</span></span> 
- <span data-ttu-id="48268-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="48268-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="48268-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="48268-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="48268-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="48268-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="48268-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="48268-1069">ID #</span><span class="sxs-lookup"><span data-stu-id="48268-1069">id#</span></span> 
- <span data-ttu-id="48268-1070">IDs #</span><span class="sxs-lookup"><span data-stu-id="48268-1070">ids#</span></span> 
- <span data-ttu-id="48268-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="48268-1071">idcard card#</span></span> 
- <span data-ttu-id="48268-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="48268-1072">idcard cards#</span></span> 
- <span data-ttu-id="48268-1073">Personalausweis #</span><span class="sxs-lookup"><span data-stu-id="48268-1073">idcard#</span></span> 
- <span data-ttu-id="48268-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="48268-1074">identification card#</span></span> 
- <span data-ttu-id="48268-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="48268-1075">identification cards#</span></span> 
- <span data-ttu-id="48268-1076">Identifizierung #</span><span class="sxs-lookup"><span data-stu-id="48268-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="48268-1077">Kanadische Health Service-Nummer</span><span class="sxs-lookup"><span data-stu-id="48268-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1078">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1078">Format</span></span>

<span data-ttu-id="48268-1079">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1080">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1080">Pattern</span></span>

<span data-ttu-id="48268-1081">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1082">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1082">Checksum</span></span>

<span data-ttu-id="48268-1083">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1084">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1084">Definition</span></span>

<span data-ttu-id="48268-1085">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1086">Der reguläre Ausdruck Regex_canada_health_service_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1087">Ein Schlüsselwort aus Keyword_canada_health_service_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1088">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="48268-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="48268-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="48268-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="48268-1090">personal health number</span></span>
- <span data-ttu-id="48268-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="48268-1091">patient information</span></span>
- <span data-ttu-id="48268-1092">health services</span><span class="sxs-lookup"><span data-stu-id="48268-1092">health services</span></span>
- <span data-ttu-id="48268-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="48268-1093">speciality services</span></span>
- <span data-ttu-id="48268-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="48268-1094">automobile accident</span></span>
- <span data-ttu-id="48268-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="48268-1095">patient hospital</span></span>
- <span data-ttu-id="48268-1096">Psychiater</span><span class="sxs-lookup"><span data-stu-id="48268-1096">psychiatrist</span></span>
- <span data-ttu-id="48268-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="48268-1097">workers compensation</span></span>
- <span data-ttu-id="48268-1098">Disability</span><span class="sxs-lookup"><span data-stu-id="48268-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="48268-1099">Kanadische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1100">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1100">Format</span></span>

<span data-ttu-id="48268-1101">Zwei Großbuchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1102">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1102">Pattern</span></span>

<span data-ttu-id="48268-1103">Zwei Großbuchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1104">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1104">Checksum</span></span>

<span data-ttu-id="48268-1105">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1106">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1106">Definition</span></span>

<span data-ttu-id="48268-1107">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1108">Der reguläre Ausdruck Regex_canada_passport_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1109">Ein Schlüsselwort aus Keyword_canada_passport_number oder Keyword_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1110">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="48268-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="48268-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="48268-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="48268-1112">canadian citizenship</span></span>
- <span data-ttu-id="48268-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="48268-1113">canadian passport</span></span>
- <span data-ttu-id="48268-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="48268-1114">passport application</span></span>
- <span data-ttu-id="48268-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="48268-1115">passport photos</span></span>
- <span data-ttu-id="48268-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="48268-1116">certified translator</span></span>
- <span data-ttu-id="48268-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="48268-1117">canadian citizens</span></span>
- <span data-ttu-id="48268-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="48268-1118">processing times</span></span>
- <span data-ttu-id="48268-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="48268-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="48268-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="48268-1120">Keyword_passport</span></span>

- <span data-ttu-id="48268-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="48268-1121">Passport Number</span></span>
- <span data-ttu-id="48268-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="48268-1122">Passport No</span></span>
- <span data-ttu-id="48268-1123">Passport#</span><span class="sxs-lookup"><span data-stu-id="48268-1123">Passport #</span></span>
- <span data-ttu-id="48268-1124">Pass #</span><span class="sxs-lookup"><span data-stu-id="48268-1124">Passport#</span></span>
- <span data-ttu-id="48268-1125">Passport-Nr</span><span class="sxs-lookup"><span data-stu-id="48268-1125">PassportID</span></span>
- <span data-ttu-id="48268-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="48268-1126">Passportno</span></span>
- <span data-ttu-id="48268-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="48268-1127">passportnumber</span></span>
- <span data-ttu-id="48268-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="48268-1128">パスポート</span></span>
- <span data-ttu-id="48268-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="48268-1129">パスポート番号</span></span>
- <span data-ttu-id="48268-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="48268-1130">パスポートのNum</span></span>
- <span data-ttu-id="48268-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="48268-1131">パスポート＃</span></span>
- <span data-ttu-id="48268-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="48268-1132">Numéro de passeport</span></span>
- <span data-ttu-id="48268-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="48268-1133">Passeport n °</span></span>
- <span data-ttu-id="48268-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="48268-1134">Passeport Non</span></span>
- <span data-ttu-id="48268-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="48268-1135">Passeport #</span></span>
- <span data-ttu-id="48268-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="48268-1136">Passeport#</span></span>
- <span data-ttu-id="48268-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="48268-1137">PasseportNon</span></span>
- <span data-ttu-id="48268-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="48268-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="48268-1139">Kanadische Personal Health Identification-Nummer (PHIN)</span><span class="sxs-lookup"><span data-stu-id="48268-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="48268-1140">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1140">Format</span></span>

<span data-ttu-id="48268-1141">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1142">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1142">Pattern</span></span>

<span data-ttu-id="48268-1143">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1144">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1144">Checksum</span></span>

<span data-ttu-id="48268-1145">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1146">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1146">Definition</span></span>

<span data-ttu-id="48268-1147">Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: der reguläre Ausdruck Regex_canada_phin findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="48268-1148">Mindestens zwei Schlüsselwörter aus Keyword_canada_phin oder Keyword_canada_provinces werden gefunden..</span><span class="sxs-lookup"><span data-stu-id="48268-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1149">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="48268-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="48268-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="48268-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="48268-1151">social insurance number</span></span>
- <span data-ttu-id="48268-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="48268-1152">health information act</span></span>
- <span data-ttu-id="48268-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="48268-1153">income tax information</span></span>
- <span data-ttu-id="48268-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="48268-1154">manitoba health</span></span>
- <span data-ttu-id="48268-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="48268-1155">health registration</span></span>
- <span data-ttu-id="48268-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="48268-1156">prescription purchases</span></span>
- <span data-ttu-id="48268-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="48268-1157">benefit eligibility</span></span>
- <span data-ttu-id="48268-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="48268-1158">personal health</span></span>
- <span data-ttu-id="48268-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="48268-1159">power of attorney</span></span>
- <span data-ttu-id="48268-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="48268-1160">registration number</span></span>
- <span data-ttu-id="48268-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="48268-1161">personal health number</span></span>
- <span data-ttu-id="48268-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="48268-1162">practitioner referral</span></span>
- <span data-ttu-id="48268-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="48268-1163">wellness professional</span></span>
- <span data-ttu-id="48268-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="48268-1164">patient referral</span></span>
- <span data-ttu-id="48268-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="48268-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="48268-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="48268-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="48268-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="48268-1167">Nunavut</span></span>
- <span data-ttu-id="48268-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="48268-1168">Quebec</span></span>
- <span data-ttu-id="48268-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="48268-1169">Northwest Territories</span></span>
- <span data-ttu-id="48268-1170">Ontario</span><span class="sxs-lookup"><span data-stu-id="48268-1170">Ontario</span></span>
- <span data-ttu-id="48268-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="48268-1171">British Columbia</span></span>
- <span data-ttu-id="48268-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="48268-1172">Alberta</span></span>
- <span data-ttu-id="48268-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="48268-1173">Saskatchewan</span></span>
- <span data-ttu-id="48268-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="48268-1174">Manitoba</span></span>
- <span data-ttu-id="48268-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="48268-1175">Yukon</span></span>
- <span data-ttu-id="48268-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="48268-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="48268-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="48268-1177">New Brunswick</span></span>
- <span data-ttu-id="48268-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="48268-1178">Nova Scotia</span></span>
- <span data-ttu-id="48268-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="48268-1179">Prince Edward Island</span></span>
- <span data-ttu-id="48268-1180">Kanada</span><span class="sxs-lookup"><span data-stu-id="48268-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="48268-1181">Kanadische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1182">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1182">Format</span></span>

<span data-ttu-id="48268-1183">Neun Ziffern mit optionalen Bindestrichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1184">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1184">Pattern</span></span>

<span data-ttu-id="48268-1185">Formatiert</span><span class="sxs-lookup"><span data-stu-id="48268-1185">Formatted:</span></span>
- <span data-ttu-id="48268-1186">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1186">Three digits</span></span> 
- <span data-ttu-id="48268-1187">Ein Bindestrich oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-1187">A hyphen or space</span></span> 
- <span data-ttu-id="48268-1188">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1188">Three digits</span></span> 
- <span data-ttu-id="48268-1189">Ein Bindestrich oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-1189">A hyphen or space</span></span> 
- <span data-ttu-id="48268-1190">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1190">Three digits</span></span>

<span data-ttu-id="48268-1191">Unformatiert: neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1192">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1192">Checksum</span></span>

<span data-ttu-id="48268-1193">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1194">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1194">Definition</span></span>

<span data-ttu-id="48268-1195">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1196">Die Funktion Func_canadian_sin findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1197">Mindestens zwei dieser eine beliebige Kombination der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="48268-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="48268-1198">Ein Schlüsselwort aus Keyword_sin wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="48268-1199">Ein Schlüsselwort aus Keyword_sin_collaborative wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="48268-1200">Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="48268-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="48268-1201">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1201">The checksum passes.</span></span>

<span data-ttu-id="48268-1202">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1203">Die Funktion Func_unformatted_canadian_sin findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1204">Ein Schlüsselwort aus Keyword_sin wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="48268-1205">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1205">The checksum passes.</span></span>

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1206">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="48268-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="48268-1207">Keyword_sin</span></span>

- <span data-ttu-id="48268-1208">sin</span><span class="sxs-lookup"><span data-stu-id="48268-1208">sin</span></span> 
- <span data-ttu-id="48268-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="48268-1209">social insurance</span></span> 
- <span data-ttu-id="48268-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="48268-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="48268-1211">Todsünden</span><span class="sxs-lookup"><span data-stu-id="48268-1211">sins</span></span> 
- <span data-ttu-id="48268-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="48268-1212">ssn</span></span> 
- <span data-ttu-id="48268-1213">Sozialversicherungsnummern</span><span class="sxs-lookup"><span data-stu-id="48268-1213">ssns</span></span> 
- <span data-ttu-id="48268-1214">social security</span><span class="sxs-lookup"><span data-stu-id="48268-1214">social security</span></span> 
- <span data-ttu-id="48268-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="48268-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="48268-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="48268-1216">national identification number</span></span> 
- <span data-ttu-id="48268-1217">national id</span><span class="sxs-lookup"><span data-stu-id="48268-1217">national id</span></span> 
- <span data-ttu-id="48268-1218">Sin #</span><span class="sxs-lookup"><span data-stu-id="48268-1218">sin#</span></span> 
- <span data-ttu-id="48268-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="48268-1219">soc ins</span></span> 
- <span data-ttu-id="48268-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="48268-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="48268-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="48268-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="48268-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="48268-1222">driver's license</span></span> 
- <span data-ttu-id="48268-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="48268-1223">drivers license</span></span> 
- <span data-ttu-id="48268-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="48268-1224">driver's licence</span></span> 
- <span data-ttu-id="48268-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48268-1225">drivers licence</span></span> 
- <span data-ttu-id="48268-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="48268-1226">DOB</span></span> 
- <span data-ttu-id="48268-1227">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="48268-1227">Birthdate</span></span> 
- <span data-ttu-id="48268-1228">Geburtstag</span><span class="sxs-lookup"><span data-stu-id="48268-1228">Birthday</span></span> 
- <span data-ttu-id="48268-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="48268-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="48268-1230">	Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="48268-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1231">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1231">Format</span></span>

<span data-ttu-id="48268-1232">7-8 Ziffern Plus Trennzeichen für eine Prüfziffer oder einen Buchstaben</span><span class="sxs-lookup"><span data-stu-id="48268-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1233">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1233">Pattern</span></span>

<span data-ttu-id="48268-1234">7-8 Ziffern plus Trennzeichen:</span><span class="sxs-lookup"><span data-stu-id="48268-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="48268-1235">1-2 Ziffern </span><span class="sxs-lookup"><span data-stu-id="48268-1235">1-2 digits</span></span> 
- <span data-ttu-id="48268-1236">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="48268-1236">A period</span></span> 
- <span data-ttu-id="48268-1237">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1237">Three digits</span></span> 
- <span data-ttu-id="48268-1238">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="48268-1238">A period</span></span> 
- <span data-ttu-id="48268-1239">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1239">Three digits</span></span> 
- <span data-ttu-id="48268-1240">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-1240">A dash</span></span> 
- <span data-ttu-id="48268-1241">Eine Ziffer oder ein Buchstabe (Groß-/Kleinschreibung nicht unterschieden), die bzw. der eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="48268-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1242">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1242">Checksum</span></span>

<span data-ttu-id="48268-1243">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1244">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1244">Definition</span></span>

<span data-ttu-id="48268-1245">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1246">Die Funktion Func_chile_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1247">Ein Schlüsselwort aus Keyword_chile_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="48268-1248">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1248">The checksum passes.</span></span>

<span data-ttu-id="48268-1249">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1250">Die Funktion Func_chile_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1251">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1251">The checksum passes.</span></span>

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1252">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="48268-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="48268-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="48268-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="48268-1254">National Identification Number</span></span> 
- <span data-ttu-id="48268-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="48268-1255">Identity card</span></span> 
- <span data-ttu-id="48268-1256">ID</span><span class="sxs-lookup"><span data-stu-id="48268-1256">ID</span></span> 
- <span data-ttu-id="48268-1257">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="48268-1257">Identification</span></span> 
- <span data-ttu-id="48268-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="48268-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="48268-1259">Ausführen</span><span class="sxs-lookup"><span data-stu-id="48268-1259">RUN</span></span> 
- <span data-ttu-id="48268-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="48268-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="48268-1261">Rut</span><span class="sxs-lookup"><span data-stu-id="48268-1261">RUT</span></span> 
- <span data-ttu-id="48268-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="48268-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="48268-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="48268-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="48268-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="48268-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="48268-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="48268-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="48268-1266">	China (PRC) – Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1267">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1267">Format</span></span>

<span data-ttu-id="48268-1268">18 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1269">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1269">Pattern</span></span>

<span data-ttu-id="48268-1270">18 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-1270">18 digits:</span></span>
- <span data-ttu-id="48268-1271">Sechs Ziffern, die einen Adresscode angeben </span><span class="sxs-lookup"><span data-stu-id="48268-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="48268-1272">Acht Ziffern im Fomat JJJJMMTT, wobei es sich um das Geburtsdatum handelt </span><span class="sxs-lookup"><span data-stu-id="48268-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="48268-1273">Drei Ziffern, die ein Reihenfolgencode sind </span><span class="sxs-lookup"><span data-stu-id="48268-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="48268-1274">Eine Ziffer als Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="48268-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1275">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1275">Checksum</span></span>

<span data-ttu-id="48268-1276">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1277">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1277">Definition</span></span>

<span data-ttu-id="48268-1278">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1279">Die Funktion Func_china_resident_id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1280">Ein Schlüsselwort aus Keyword_china_resident_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="48268-1281">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1281">The checksum passes.</span></span>

<span data-ttu-id="48268-1282">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1283">Die Funktion Func_china_resident_id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1284">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1284">The checksum passes.</span></span>

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1285">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="48268-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="48268-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="48268-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="48268-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="48268-1288">PRC</span><span class="sxs-lookup"><span data-stu-id="48268-1288">PRC</span></span> 
- <span data-ttu-id="48268-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="48268-1289">National Identification Card</span></span> 
- <span data-ttu-id="48268-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="48268-1290">身份证</span></span> 
- <span data-ttu-id="48268-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="48268-1291">居民 身份证</span></span> 
- <span data-ttu-id="48268-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="48268-1292">居民身份证</span></span> 
- <span data-ttu-id="48268-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="48268-1293">鉴定</span></span> 
- <span data-ttu-id="48268-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="48268-1294">身分證</span></span> 
- <span data-ttu-id="48268-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="48268-1295">居民 身份證</span></span>
- <span data-ttu-id="48268-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="48268-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="48268-1297">Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="48268-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1298">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1298">Format</span></span>

<span data-ttu-id="48268-1299">14 bis 16 Ziffern, die formatiert oder unformatiert (dddddddddddddddd) sein können und die den Luhn-Test bestehen müssen.</span><span class="sxs-lookup"><span data-stu-id="48268-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1300">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1300">Pattern</span></span>

<span data-ttu-id="48268-1301">Sehr komplexe und robuste Muster, die Karten aller wichtigen Marken weltweit, einschließlich Visa, MasterCard, Discover-Karte, JCB, American Express, Geschenkgutscheine und Restaurantkarten erkennen.</span><span class="sxs-lookup"><span data-stu-id="48268-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1302">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1302">Checksum</span></span>

<span data-ttu-id="48268-1303">Ja, die Luhn-Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1304">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1304">Definition</span></span>

<span data-ttu-id="48268-1305">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1306">Die Funktion Func_credit_card findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1307">Eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="48268-1307">One of the following is true:</span></span>
    - <span data-ttu-id="48268-1308">Ein Schlüsselwort aus Keyword_cc_verification wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="48268-1309">Ein Schlüsselwort aus Keyword_cc_name wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="48268-1310">Die Funktion Func_expiration_date findet ein Datum im richtigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="48268-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="48268-1311">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1311">The checksum passes.</span></span>

<span data-ttu-id="48268-1312">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1313">Die Funktion Func_credit_card findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1314">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1314">The checksum passes.</span></span>

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1315">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="48268-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="48268-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="48268-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="48268-1317">card verification</span></span>
- <span data-ttu-id="48268-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="48268-1318">card identification number</span></span>
- <span data-ttu-id="48268-1319">CVN</span><span class="sxs-lookup"><span data-stu-id="48268-1319">cvn</span></span>
- <span data-ttu-id="48268-1320">cid</span><span class="sxs-lookup"><span data-stu-id="48268-1320">cid</span></span>
- <span data-ttu-id="48268-1321">CVC2</span><span class="sxs-lookup"><span data-stu-id="48268-1321">cvc2</span></span>
- <span data-ttu-id="48268-1322">CVV2</span><span class="sxs-lookup"><span data-stu-id="48268-1322">cvv2</span></span>
- <span data-ttu-id="48268-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="48268-1323">pin block</span></span>
- <span data-ttu-id="48268-1324">security code</span><span class="sxs-lookup"><span data-stu-id="48268-1324">security code</span></span>
- <span data-ttu-id="48268-1325">security number</span><span class="sxs-lookup"><span data-stu-id="48268-1325">security number</span></span>
- <span data-ttu-id="48268-1326">security no</span><span class="sxs-lookup"><span data-stu-id="48268-1326">security no</span></span>
- <span data-ttu-id="48268-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="48268-1327">issue number</span></span>
- <span data-ttu-id="48268-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="48268-1328">issue no</span></span>
- <span data-ttu-id="48268-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="48268-1329">cryptogramme</span></span>
- <span data-ttu-id="48268-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="48268-1330">numéro de sécurité</span></span>
- <span data-ttu-id="48268-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="48268-1331">numero de securite</span></span>
- <span data-ttu-id="48268-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="48268-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="48268-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="48268-1334">prüfziffer</span></span>
- <span data-ttu-id="48268-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="48268-1335">prufziffer</span></span>
- <span data-ttu-id="48268-1336">Sicherheitskode</span><span class="sxs-lookup"><span data-stu-id="48268-1336">sicherheits Kode</span></span>
- <span data-ttu-id="48268-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="48268-1337">sicherheitscode</span></span>
- <span data-ttu-id="48268-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="48268-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="48268-1339">verfalldatum</span></span>
- <span data-ttu-id="48268-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="48268-1340">codice di verifica</span></span>
- <span data-ttu-id="48268-1341">COD.</span><span class="sxs-lookup"><span data-stu-id="48268-1341">cod.</span></span> <span data-ttu-id="48268-1342">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="48268-1342">sicurezza</span></span>
- <span data-ttu-id="48268-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="48268-1343">cod sicurezza</span></span>
- <span data-ttu-id="48268-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="48268-1344">n autorizzazione</span></span>
- <span data-ttu-id="48268-1345">Código</span><span class="sxs-lookup"><span data-stu-id="48268-1345">código</span></span>
- <span data-ttu-id="48268-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="48268-1346">codigo</span></span>
- <span data-ttu-id="48268-1347">COD.</span><span class="sxs-lookup"><span data-stu-id="48268-1347">cod.</span></span> <span data-ttu-id="48268-1348">SEG</span><span class="sxs-lookup"><span data-stu-id="48268-1348">seg</span></span>
- <span data-ttu-id="48268-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="48268-1349">cod seg</span></span>
- <span data-ttu-id="48268-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1350">código de segurança</span></span>
- <span data-ttu-id="48268-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="48268-1351">codigo de seguranca</span></span>
- <span data-ttu-id="48268-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1352">codigo de segurança</span></span>
- <span data-ttu-id="48268-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="48268-1353">código de seguranca</span></span>
- <span data-ttu-id="48268-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="48268-1354">cód.</span></span> <span data-ttu-id="48268-1355">Segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1355">segurança</span></span>
- <span data-ttu-id="48268-1356">COD.</span><span class="sxs-lookup"><span data-stu-id="48268-1356">cod.</span></span> <span data-ttu-id="48268-1357">Seguranca COD.</span><span class="sxs-lookup"><span data-stu-id="48268-1357">seguranca cod.</span></span> <span data-ttu-id="48268-1358">Segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1358">segurança</span></span>
- <span data-ttu-id="48268-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="48268-1359">cód.</span></span> <span data-ttu-id="48268-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="48268-1360">seguranca</span></span>
- <span data-ttu-id="48268-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1361">cód segurança</span></span>
- <span data-ttu-id="48268-1362">COD Seguranca COD Segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="48268-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="48268-1363">cód seguranca</span></span>
- <span data-ttu-id="48268-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="48268-1364">número de verificação</span></span>
- <span data-ttu-id="48268-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="48268-1365">numero de verificacao</span></span>
- <span data-ttu-id="48268-1366">Ablauf</span><span class="sxs-lookup"><span data-stu-id="48268-1366">ablauf</span></span>
- <span data-ttu-id="48268-1367">Gültig bis</span><span class="sxs-lookup"><span data-stu-id="48268-1367">gültig bis</span></span>
- <span data-ttu-id="48268-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="48268-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="48268-1369">Gultig bis</span><span class="sxs-lookup"><span data-stu-id="48268-1369">gultig bis</span></span>
- <span data-ttu-id="48268-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="48268-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="48268-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="48268-1371">scadenza</span></span>
- <span data-ttu-id="48268-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="48268-1372">data scad</span></span>
- <span data-ttu-id="48268-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="48268-1373">fecha de expiracion</span></span>
- <span data-ttu-id="48268-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="48268-1374">fecha de venc</span></span>
- <span data-ttu-id="48268-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="48268-1375">vencimiento</span></span>
- <span data-ttu-id="48268-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="48268-1376">válido hasta</span></span>
- <span data-ttu-id="48268-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="48268-1377">valido hasta</span></span>
- <span data-ttu-id="48268-1378">VTO</span><span class="sxs-lookup"><span data-stu-id="48268-1378">vto</span></span>
- <span data-ttu-id="48268-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="48268-1379">data de expiração</span></span>
- <span data-ttu-id="48268-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="48268-1380">data de expiracao</span></span>
- <span data-ttu-id="48268-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="48268-1381">data em que expira</span></span>
- <span data-ttu-id="48268-1382">validade</span><span class="sxs-lookup"><span data-stu-id="48268-1382">validade</span></span>
- <span data-ttu-id="48268-1383">Valor</span><span class="sxs-lookup"><span data-stu-id="48268-1383">valor</span></span>
- <span data-ttu-id="48268-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="48268-1384">vencimento</span></span>
- <span data-ttu-id="48268-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="48268-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="48268-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="48268-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="48268-1387">Amex</span><span class="sxs-lookup"><span data-stu-id="48268-1387">amex</span></span>
- <span data-ttu-id="48268-1388">american express</span><span class="sxs-lookup"><span data-stu-id="48268-1388">american express</span></span>
- <span data-ttu-id="48268-1389">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="48268-1389">americanexpress</span></span>
- <span data-ttu-id="48268-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="48268-1390">Visa</span></span>
- <span data-ttu-id="48268-1391">MasterCard</span><span class="sxs-lookup"><span data-stu-id="48268-1391">mastercard</span></span>
- <span data-ttu-id="48268-1392">master card</span><span class="sxs-lookup"><span data-stu-id="48268-1392">master card</span></span>
- <span data-ttu-id="48268-1393">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="48268-1393">mc</span></span> 
- <span data-ttu-id="48268-1394">MasterCards gesichert</span><span class="sxs-lookup"><span data-stu-id="48268-1394">mastercards</span></span>
- <span data-ttu-id="48268-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="48268-1395">master cards</span></span>
- <span data-ttu-id="48268-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="48268-1396">diner's Club</span></span>
- <span data-ttu-id="48268-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="48268-1397">diners club</span></span>
- <span data-ttu-id="48268-1398">DinersClub</span><span class="sxs-lookup"><span data-stu-id="48268-1398">dinersclub</span></span>
- <span data-ttu-id="48268-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="48268-1399">discover card</span></span>
- <span data-ttu-id="48268-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="48268-1400">discovercard</span></span>
- <span data-ttu-id="48268-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="48268-1401">discover cards</span></span>
- <span data-ttu-id="48268-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="48268-1402">JCB</span></span>
- <span data-ttu-id="48268-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="48268-1403">japanese card bureau</span></span>
- <span data-ttu-id="48268-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="48268-1404">carte blanche</span></span>
- <span data-ttu-id="48268-1405">CarteBlanche</span><span class="sxs-lookup"><span data-stu-id="48268-1405">carteblanche</span></span>
- <span data-ttu-id="48268-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="48268-1406">credit card</span></span>
- <span data-ttu-id="48268-1407">CC #</span><span class="sxs-lookup"><span data-stu-id="48268-1407">cc#</span></span>
- <span data-ttu-id="48268-1408">cc #:</span><span class="sxs-lookup"><span data-stu-id="48268-1408">cc#:</span></span>
- <span data-ttu-id="48268-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="48268-1409">expiration date</span></span>
- <span data-ttu-id="48268-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="48268-1410">exp date</span></span>
- <span data-ttu-id="48268-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="48268-1411">expiry date</span></span>
- <span data-ttu-id="48268-1412">Datum d'expiration</span><span class="sxs-lookup"><span data-stu-id="48268-1412">date d'expiration</span></span>
- <span data-ttu-id="48268-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="48268-1413">date d'exp</span></span>
- <span data-ttu-id="48268-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="48268-1414">date expiration</span></span>
- <span data-ttu-id="48268-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="48268-1415">bank card</span></span>
- <span data-ttu-id="48268-1416">Bankcard</span><span class="sxs-lookup"><span data-stu-id="48268-1416">bankcard</span></span>
- <span data-ttu-id="48268-1417">card number</span><span class="sxs-lookup"><span data-stu-id="48268-1417">card number</span></span>
- <span data-ttu-id="48268-1418">card num</span><span class="sxs-lookup"><span data-stu-id="48268-1418">card num</span></span>
- <span data-ttu-id="48268-1419">cardNumber</span><span class="sxs-lookup"><span data-stu-id="48268-1419">cardnumber</span></span>
- <span data-ttu-id="48268-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="48268-1420">cardnumbers</span></span>
- <span data-ttu-id="48268-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="48268-1421">card numbers</span></span>
- <span data-ttu-id="48268-1422">CreditCard</span><span class="sxs-lookup"><span data-stu-id="48268-1422">creditcard</span></span>
- <span data-ttu-id="48268-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="48268-1423">credit cards</span></span>
- <span data-ttu-id="48268-1424">creditCards</span><span class="sxs-lookup"><span data-stu-id="48268-1424">creditcards</span></span>
- <span data-ttu-id="48268-1425">Angaben</span><span class="sxs-lookup"><span data-stu-id="48268-1425">ccn</span></span>
- <span data-ttu-id="48268-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="48268-1426">card holder</span></span>
- <span data-ttu-id="48268-1427">Inhaber</span><span class="sxs-lookup"><span data-stu-id="48268-1427">cardholder</span></span>
- <span data-ttu-id="48268-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="48268-1428">card holders</span></span>
- <span data-ttu-id="48268-1429">Inhaber</span><span class="sxs-lookup"><span data-stu-id="48268-1429">cardholders</span></span>
- <span data-ttu-id="48268-1430">check card</span><span class="sxs-lookup"><span data-stu-id="48268-1430">check card</span></span>
- <span data-ttu-id="48268-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="48268-1431">checkcard</span></span>
- <span data-ttu-id="48268-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="48268-1432">check cards</span></span>
- <span data-ttu-id="48268-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="48268-1433">checkcards</span></span>
- <span data-ttu-id="48268-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="48268-1434">debit card</span></span>
- <span data-ttu-id="48268-1435">Debitkarte</span><span class="sxs-lookup"><span data-stu-id="48268-1435">debitcard</span></span>
- <span data-ttu-id="48268-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="48268-1436">debit cards</span></span>
- <span data-ttu-id="48268-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="48268-1437">debitcards</span></span>
- <span data-ttu-id="48268-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="48268-1438">atm card</span></span>
- <span data-ttu-id="48268-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="48268-1439">atmcard</span></span>
- <span data-ttu-id="48268-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="48268-1440">atm cards</span></span>
- <span data-ttu-id="48268-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="48268-1441">atmcards</span></span>
- <span data-ttu-id="48268-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="48268-1442">enroute</span></span>
- <span data-ttu-id="48268-1443">en route</span><span class="sxs-lookup"><span data-stu-id="48268-1443">en route</span></span>
- <span data-ttu-id="48268-1444">card type</span><span class="sxs-lookup"><span data-stu-id="48268-1444">card type</span></span>
- <span data-ttu-id="48268-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="48268-1445">carte bancaire</span></span>
- <span data-ttu-id="48268-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="48268-1446">carte de crédit</span></span>
- <span data-ttu-id="48268-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="48268-1447">carte de credit</span></span>
- <span data-ttu-id="48268-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="48268-1448">numéro de carte</span></span>
- <span data-ttu-id="48268-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="48268-1449">numero de carte</span></span>
- <span data-ttu-id="48268-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="48268-1450">nº de la carte</span></span>
- <span data-ttu-id="48268-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="48268-1451">nº de carte</span></span>
- <span data-ttu-id="48268-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="48268-1452">kreditkarte</span></span>
- <span data-ttu-id="48268-1453">Karte</span><span class="sxs-lookup"><span data-stu-id="48268-1453">karte</span></span>
- <span data-ttu-id="48268-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="48268-1454">karteninhaber</span></span>
- <span data-ttu-id="48268-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="48268-1455">karteninhabers</span></span>
- <span data-ttu-id="48268-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="48268-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="48268-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="48268-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="48268-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="48268-1458">kreditkartentyp</span></span>
- <span data-ttu-id="48268-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="48268-1459">eigentümername</span></span>
- <span data-ttu-id="48268-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="48268-1460">kartennr</span></span> 
- <span data-ttu-id="48268-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="48268-1461">kartennummer</span></span>
- <span data-ttu-id="48268-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="48268-1462">kreditkartennummer</span></span>
- <span data-ttu-id="48268-1463">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="48268-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="48268-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="48268-1464">carta di credito</span></span>
- <span data-ttu-id="48268-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="48268-1465">carta credito</span></span>
- <span data-ttu-id="48268-1466">Carta</span><span class="sxs-lookup"><span data-stu-id="48268-1466">carta</span></span>
- <span data-ttu-id="48268-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="48268-1467">n carta</span></span>
- <span data-ttu-id="48268-1468">Nr.</span><span class="sxs-lookup"><span data-stu-id="48268-1468">nr.</span></span> <span data-ttu-id="48268-1469">Carta</span><span class="sxs-lookup"><span data-stu-id="48268-1469">carta</span></span>
- <span data-ttu-id="48268-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="48268-1470">nr carta</span></span>
- <span data-ttu-id="48268-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="48268-1471">numero carta</span></span>
- <span data-ttu-id="48268-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="48268-1472">numero della carta</span></span>
- <span data-ttu-id="48268-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="48268-1473">numero di carta</span></span>
- <span data-ttu-id="48268-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="48268-1474">tarjeta credito</span></span>
- <span data-ttu-id="48268-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="48268-1475">tarjeta de credito</span></span>
- <span data-ttu-id="48268-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="48268-1476">tarjeta crédito</span></span>
- <span data-ttu-id="48268-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="48268-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="48268-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="48268-1478">tarjeta de atm</span></span>
- <span data-ttu-id="48268-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="48268-1479">tarjeta atm</span></span>
- <span data-ttu-id="48268-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="48268-1480">tarjeta debito</span></span>
- <span data-ttu-id="48268-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="48268-1481">tarjeta de debito</span></span>
- <span data-ttu-id="48268-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="48268-1482">tarjeta débito</span></span>
- <span data-ttu-id="48268-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="48268-1483">tarjeta de débito</span></span>
- <span data-ttu-id="48268-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="48268-1484">nº de tarjeta</span></span>
- <span data-ttu-id="48268-1485">Nein.</span><span class="sxs-lookup"><span data-stu-id="48268-1485">no.</span></span> <span data-ttu-id="48268-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="48268-1486">de tarjeta</span></span>
- <span data-ttu-id="48268-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="48268-1487">no de tarjeta</span></span>
- <span data-ttu-id="48268-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="48268-1488">numero de tarjeta</span></span>
- <span data-ttu-id="48268-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="48268-1489">número de tarjeta</span></span>
- <span data-ttu-id="48268-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="48268-1490">tarjeta no</span></span>
- <span data-ttu-id="48268-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="48268-1491">tarjetahabiente</span></span>
- <span data-ttu-id="48268-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="48268-1492">cartão de crédito</span></span>
- <span data-ttu-id="48268-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="48268-1493">cartão de credito</span></span>
- <span data-ttu-id="48268-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="48268-1494">cartao de crédito</span></span>
- <span data-ttu-id="48268-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="48268-1495">cartao de credito</span></span>
- <span data-ttu-id="48268-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="48268-1496">cartão de débito</span></span>
- <span data-ttu-id="48268-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="48268-1497">cartao de débito</span></span>
- <span data-ttu-id="48268-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="48268-1498">cartão de debito</span></span>
- <span data-ttu-id="48268-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="48268-1499">cartao de debito</span></span>
- <span data-ttu-id="48268-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="48268-1500">débito automático</span></span>
- <span data-ttu-id="48268-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="48268-1501">debito automatico</span></span>
- <span data-ttu-id="48268-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1502">número do cartão</span></span>
- <span data-ttu-id="48268-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1503">numero do cartão</span></span> 
- <span data-ttu-id="48268-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1504">número do cartao</span></span>
- <span data-ttu-id="48268-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1505">numero do cartao</span></span>
- <span data-ttu-id="48268-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1506">número de cartão</span></span>
- <span data-ttu-id="48268-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1507">numero de cartão</span></span>
- <span data-ttu-id="48268-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1508">número de cartao</span></span>
- <span data-ttu-id="48268-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1509">numero de cartao</span></span>
- <span data-ttu-id="48268-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1510">nº do cartão</span></span>
- <span data-ttu-id="48268-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1511">nº do cartao</span></span>
- <span data-ttu-id="48268-1512">nº.</span><span class="sxs-lookup"><span data-stu-id="48268-1512">nº.</span></span> <span data-ttu-id="48268-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1513">do cartão</span></span>
- <span data-ttu-id="48268-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1514">no do cartão</span></span>
- <span data-ttu-id="48268-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1515">no do cartao</span></span>
- <span data-ttu-id="48268-1516">Nein.</span><span class="sxs-lookup"><span data-stu-id="48268-1516">no.</span></span> <span data-ttu-id="48268-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1517">do cartão</span></span>
- <span data-ttu-id="48268-1518">Nein.</span><span class="sxs-lookup"><span data-stu-id="48268-1518">no.</span></span> <span data-ttu-id="48268-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="48268-1520">	Kroatien – Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1521">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1521">Format</span></span>

<span data-ttu-id="48268-1522">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1523">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1523">Pattern</span></span>

<span data-ttu-id="48268-1524">Neun aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1525">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1525">Checksum</span></span>

<span data-ttu-id="48268-1526">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1527">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1527">Definition</span></span>

<span data-ttu-id="48268-1528">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1529">Die Funktion Func_croatia_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1530">Ein Schlüsselwort aus Keyword_croatia_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1531">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="48268-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="48268-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="48268-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="48268-1533">Croatian identity card</span></span>
- <span data-ttu-id="48268-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="48268-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="48268-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="48268-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1536">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1536">Format</span></span>

<span data-ttu-id="48268-1537">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1538">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1538">Pattern</span></span>

<span data-ttu-id="48268-1539">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-1539">11 digits:</span></span>
- <span data-ttu-id="48268-1540">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1540">10 digits</span></span> 
- <span data-ttu-id="48268-1541">Letzte Ziffer ist eine Prüfziffer für den Zweck des internationalen Datenaustauschs, die Buchstaben HR werden vor den elf Ziffern hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="48268-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1542">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1542">Checksum</span></span>

<span data-ttu-id="48268-1543">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1544">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1544">Definition</span></span>

<span data-ttu-id="48268-1545">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1546">Die Funktion Func_croatia_oib_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1547">Ein Schlüsselwort aus Keyword_croatia_oib_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="48268-1548">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1548">The checksum passes.</span></span>

<span data-ttu-id="48268-1549">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1550">Die Funktion Func_croatia_oib_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1551">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1551">The checksum passes.</span></span>

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1552">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="48268-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="48268-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="48268-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="48268-1554">Personal Identification Number</span></span>
- <span data-ttu-id="48268-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="48268-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="48268-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="48268-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="48268-1557">Tschechische Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1558">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1558">Format</span></span>

<span data-ttu-id="48268-1559">Neun Ziffern mit optionalem Schrägstrich (altes Format) 10 Ziffern mit optionalem Schrägstrich (neues Format)</span><span class="sxs-lookup"><span data-stu-id="48268-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1560">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1560">Pattern</span></span>

<span data-ttu-id="48268-1561">Neun Ziffern (altes Format):</span><span class="sxs-lookup"><span data-stu-id="48268-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="48268-1562">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1562">Nine digits</span></span>

<span data-ttu-id="48268-1563">ODER</span><span class="sxs-lookup"><span data-stu-id="48268-1563">OR</span></span>

- <span data-ttu-id="48268-1564">Sechs Ziffern, die das Geburtsdatum darstellen.</span><span class="sxs-lookup"><span data-stu-id="48268-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="48268-1565">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="48268-1565">A forward slash</span></span>
- <span data-ttu-id="48268-1566">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1566">Three digits</span></span>

<span data-ttu-id="48268-1567">10 Ziffern (neues Format):</span><span class="sxs-lookup"><span data-stu-id="48268-1567">10 digits (new format):</span></span>
- <span data-ttu-id="48268-1568">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1568">10 digits</span></span>

<span data-ttu-id="48268-1569">ODER</span><span class="sxs-lookup"><span data-stu-id="48268-1569">OR</span></span>

- <span data-ttu-id="48268-1570">Sechs Ziffern, die das Geburtsdatum darstellen.</span><span class="sxs-lookup"><span data-stu-id="48268-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="48268-1571">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="48268-1571">A forward slash</span></span> 
- <span data-ttu-id="48268-1572">Vier Ziffern, wobei die letzte Ziffer eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="48268-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1573">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1573">Checksum</span></span>

<span data-ttu-id="48268-1574">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1575">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1575">Definition</span></span>

<span data-ttu-id="48268-1576">Eine DLP-Richtlinie ist 85% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_czech_id_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="48268-1577">Ein Schlüsselwort aus Keyword_czech_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="48268-1578">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="48268-1579">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1579">Keywords</span></span>

- <span data-ttu-id="48268-1580">Tschechische Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1580">czech personal identity number</span></span>
- <span data-ttu-id="48268-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="48268-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="48268-1582">	Dänemark – Persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1583">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1583">Format</span></span>

<span data-ttu-id="48268-1584">10 Ziffern, die einen Bindestrich enthalten</span><span class="sxs-lookup"><span data-stu-id="48268-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1585">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1585">Pattern</span></span>

<span data-ttu-id="48268-1586">10 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-1586">10 digits:</span></span>
- <span data-ttu-id="48268-1587">Sechs Ziffern im Format TTMMJJ, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="48268-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="48268-1588">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-1588">A hyphen</span></span> 
- <span data-ttu-id="48268-1589">Vier Ziffern, bei denen die letzte Ziffer eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="48268-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1590">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1590">Checksum</span></span>

<span data-ttu-id="48268-1591">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1592">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1592">Definition</span></span>

<span data-ttu-id="48268-1593">Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: der reguläre Ausdruck Regex_denmark_id findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="48268-1594">Ein Schlüsselwort aus Keyword_denmark_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="48268-1595">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1596">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="48268-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="48268-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="48268-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="48268-1598">Personal Identification Number</span></span>
- <span data-ttu-id="48268-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="48268-1599">CPR</span></span>
- <span data-ttu-id="48268-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="48268-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="48268-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="48268-1602">Drug Enforcement Agency (DEA)-Nummer</span><span class="sxs-lookup"><span data-stu-id="48268-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1603">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1603">Format</span></span>

<span data-ttu-id="48268-1604">Zwei Buchstaben gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1605">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1605">Pattern</span></span>

<span data-ttu-id="48268-1606">Das Muster muss Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="48268-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="48268-1607">Einen Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) aus der folgenden Gruppe möglicher Buchstaben: abcdefghjklmnprstux, was einem Registrantencode entspricht</span><span class="sxs-lookup"><span data-stu-id="48268-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="48268-1608">Ein Buchstabe (bei dem die Groß-und Kleinschreibung nicht beachtet wird), der dem ersten Buchstaben des Nachnamens des Registrants entspricht</span><span class="sxs-lookup"><span data-stu-id="48268-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="48268-1609">Sieben Ziffern, von denen die letzte die Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="48268-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1610">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1610">Checksum</span></span>

<span data-ttu-id="48268-1611">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1612">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1612">Definition</span></span>

<span data-ttu-id="48268-1613">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1614">Die Funktion Func_dea_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1615">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1616">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1616">Keywords</span></span>

<span data-ttu-id="48268-1617">Keine</span><span class="sxs-lookup"><span data-stu-id="48268-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="48268-1618">EU Debit Card-Nummer</span><span class="sxs-lookup"><span data-stu-id="48268-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1619">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1619">Format</span></span>

<span data-ttu-id="48268-1620">16 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1621">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1621">Pattern</span></span>

<span data-ttu-id="48268-1622">Sehr komplexes und robustes Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1623">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1623">Checksum</span></span>

<span data-ttu-id="48268-1624">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1625">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1625">Definition</span></span>

<span data-ttu-id="48268-1626">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1627">Die Funktion Func_eu_debit_card findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1628">Mindestens eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="48268-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="48268-1629">Ein Schlüsselwort aus Keyword_eu_debit_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="48268-1630">Ein Schlüsselwort aus Keyword_card_terms_dict wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="48268-1631">Ein Schlüsselwort aus Keyword_card_security_terms_dict wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="48268-1632">Ein Schlüsselwort aus Keyword_card_expiration_terms_dict wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="48268-1633">Die Funktion Func_expiration_date findet ein Datum im richtigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="48268-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="48268-1634">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1634">The checksum passes.</span></span>

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1635">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="48268-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="48268-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="48268-1637">account number</span><span class="sxs-lookup"><span data-stu-id="48268-1637">account number</span></span> 
- <span data-ttu-id="48268-1638">card number</span><span class="sxs-lookup"><span data-stu-id="48268-1638">card number</span></span> 
- <span data-ttu-id="48268-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="48268-1639">card no.</span></span> 
- <span data-ttu-id="48268-1640">security number</span><span class="sxs-lookup"><span data-stu-id="48268-1640">security number</span></span> 
- <span data-ttu-id="48268-1641">CC #</span><span class="sxs-lookup"><span data-stu-id="48268-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="48268-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="48268-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="48268-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="48268-1643">acct nbr</span></span> 
- <span data-ttu-id="48268-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="48268-1644">acct num</span></span> 
- <span data-ttu-id="48268-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="48268-1645">acct no</span></span> 
- <span data-ttu-id="48268-1646">american express</span><span class="sxs-lookup"><span data-stu-id="48268-1646">american express</span></span> 
- <span data-ttu-id="48268-1647">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="48268-1647">americanexpress</span></span> 
- <span data-ttu-id="48268-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="48268-1648">americano espresso</span></span> 
- <span data-ttu-id="48268-1649">Amex</span><span class="sxs-lookup"><span data-stu-id="48268-1649">amex</span></span> 
- <span data-ttu-id="48268-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="48268-1650">atm card</span></span> 
- <span data-ttu-id="48268-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="48268-1651">atm cards</span></span> 
- <span data-ttu-id="48268-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="48268-1652">atm kaart</span></span> 
- <span data-ttu-id="48268-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="48268-1653">atmcard</span></span> 
- <span data-ttu-id="48268-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="48268-1654">atmcards</span></span> 
- <span data-ttu-id="48268-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="48268-1655">atmkaart</span></span> 
- <span data-ttu-id="48268-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="48268-1656">atmkaarten</span></span> 
- <span data-ttu-id="48268-1657">Bancontact</span><span class="sxs-lookup"><span data-stu-id="48268-1657">bancontact</span></span> 
- <span data-ttu-id="48268-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="48268-1658">bank card</span></span> 
- <span data-ttu-id="48268-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="48268-1659">bankkaart</span></span> 
- <span data-ttu-id="48268-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="48268-1660">card holder</span></span> 
- <span data-ttu-id="48268-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="48268-1661">card holders</span></span> 
- <span data-ttu-id="48268-1662">card num</span><span class="sxs-lookup"><span data-stu-id="48268-1662">card num</span></span> 
- <span data-ttu-id="48268-1663">card number</span><span class="sxs-lookup"><span data-stu-id="48268-1663">card number</span></span> 
- <span data-ttu-id="48268-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="48268-1664">card numbers</span></span> 
- <span data-ttu-id="48268-1665">card type</span><span class="sxs-lookup"><span data-stu-id="48268-1665">card type</span></span> 
- <span data-ttu-id="48268-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="48268-1666">cardano numerico</span></span> 
- <span data-ttu-id="48268-1667">Inhaber</span><span class="sxs-lookup"><span data-stu-id="48268-1667">cardholder</span></span> 
- <span data-ttu-id="48268-1668">Inhaber</span><span class="sxs-lookup"><span data-stu-id="48268-1668">cardholders</span></span> 
- <span data-ttu-id="48268-1669">cardNumber</span><span class="sxs-lookup"><span data-stu-id="48268-1669">cardnumber</span></span> 
- <span data-ttu-id="48268-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="48268-1670">cardnumbers</span></span> 
- <span data-ttu-id="48268-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="48268-1671">carta bianca</span></span> 
- <span data-ttu-id="48268-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="48268-1672">carta credito</span></span> 
- <span data-ttu-id="48268-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="48268-1673">carta di credito</span></span> 
- <span data-ttu-id="48268-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="48268-1674">cartao de credito</span></span> 
- <span data-ttu-id="48268-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="48268-1675">cartao de crédito</span></span> 
- <span data-ttu-id="48268-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="48268-1676">cartao de debito</span></span> 
- <span data-ttu-id="48268-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="48268-1677">cartao de débito</span></span> 
- <span data-ttu-id="48268-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="48268-1678">carte bancaire</span></span> 
- <span data-ttu-id="48268-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="48268-1679">carte blanche</span></span> 
- <span data-ttu-id="48268-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="48268-1680">carte bleue</span></span> 
- <span data-ttu-id="48268-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="48268-1681">carte de credit</span></span> 
- <span data-ttu-id="48268-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="48268-1682">carte de crédit</span></span> 
- <span data-ttu-id="48268-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="48268-1683">carte di credito</span></span> 
- <span data-ttu-id="48268-1684">CarteBlanche</span><span class="sxs-lookup"><span data-stu-id="48268-1684">carteblanche</span></span> 
- <span data-ttu-id="48268-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="48268-1685">cartão de credito</span></span> 
- <span data-ttu-id="48268-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="48268-1686">cartão de crédito</span></span> 
- <span data-ttu-id="48268-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="48268-1687">cartão de debito</span></span> 
- <span data-ttu-id="48268-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="48268-1688">cartão de débito</span></span> 
- <span data-ttu-id="48268-1689">cb</span><span class="sxs-lookup"><span data-stu-id="48268-1689">cb</span></span> 
- <span data-ttu-id="48268-1690">Angaben</span><span class="sxs-lookup"><span data-stu-id="48268-1690">ccn</span></span> 
- <span data-ttu-id="48268-1691">check card</span><span class="sxs-lookup"><span data-stu-id="48268-1691">check card</span></span> 
- <span data-ttu-id="48268-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="48268-1692">check cards</span></span> 
- <span data-ttu-id="48268-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="48268-1693">checkcard</span></span>
- <span data-ttu-id="48268-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="48268-1694">checkcards</span></span> 
- <span data-ttu-id="48268-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="48268-1695">chequekaart</span></span> 
- <span data-ttu-id="48268-1696">Cirrus</span><span class="sxs-lookup"><span data-stu-id="48268-1696">cirrus</span></span> 
- <span data-ttu-id="48268-1697">Cirrus-EDC-Maestro</span><span class="sxs-lookup"><span data-stu-id="48268-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="48268-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="48268-1698">controlekaart</span></span> 
- <span data-ttu-id="48268-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="48268-1699">controlekaarten</span></span> 
- <span data-ttu-id="48268-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="48268-1700">credit card</span></span> 
- <span data-ttu-id="48268-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="48268-1701">credit cards</span></span> 
- <span data-ttu-id="48268-1702">CreditCard</span><span class="sxs-lookup"><span data-stu-id="48268-1702">creditcard</span></span> 
- <span data-ttu-id="48268-1703">creditCards</span><span class="sxs-lookup"><span data-stu-id="48268-1703">creditcards</span></span> 
- <span data-ttu-id="48268-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="48268-1704">debetkaart</span></span> 
- <span data-ttu-id="48268-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="48268-1705">debetkaarten</span></span> 
- <span data-ttu-id="48268-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="48268-1706">debit card</span></span> 
- <span data-ttu-id="48268-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="48268-1707">debit cards</span></span> 
- <span data-ttu-id="48268-1708">Debitkarte</span><span class="sxs-lookup"><span data-stu-id="48268-1708">debitcard</span></span> 
- <span data-ttu-id="48268-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="48268-1709">debitcards</span></span> 
- <span data-ttu-id="48268-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="48268-1710">debito automatico</span></span> 
- <span data-ttu-id="48268-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="48268-1711">diners club</span></span> 
- <span data-ttu-id="48268-1712">DinersClub</span><span class="sxs-lookup"><span data-stu-id="48268-1712">dinersclub</span></span> 
- <span data-ttu-id="48268-1713">ermitteln</span><span class="sxs-lookup"><span data-stu-id="48268-1713">discover</span></span> 
- <span data-ttu-id="48268-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="48268-1714">discover card</span></span> 
- <span data-ttu-id="48268-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="48268-1715">discover cards</span></span> 
- <span data-ttu-id="48268-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="48268-1716">discovercard</span></span> 
- <span data-ttu-id="48268-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="48268-1717">discovercards</span></span> 
- <span data-ttu-id="48268-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="48268-1718">débito automático</span></span>
- <span data-ttu-id="48268-1719">EDC</span><span class="sxs-lookup"><span data-stu-id="48268-1719">edc</span></span> 
- <span data-ttu-id="48268-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="48268-1720">eigentümername</span></span> 
- <span data-ttu-id="48268-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="48268-1721">european debit card</span></span> 
- <span data-ttu-id="48268-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="48268-1722">hoofdkaart</span></span> 
- <span data-ttu-id="48268-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="48268-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="48268-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="48268-1724">in viaggio</span></span> 
- <span data-ttu-id="48268-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="48268-1725">japanese card bureau</span></span> 
- <span data-ttu-id="48268-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="48268-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="48268-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="48268-1727">jcb</span></span> 
- <span data-ttu-id="48268-1728">Kaart</span><span class="sxs-lookup"><span data-stu-id="48268-1728">kaart</span></span> 
- <span data-ttu-id="48268-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="48268-1729">kaart num</span></span> 
- <span data-ttu-id="48268-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="48268-1730">kaartaantal</span></span> 
- <span data-ttu-id="48268-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="48268-1731">kaartaantallen</span></span> 
- <span data-ttu-id="48268-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="48268-1732">kaarthouder</span></span> 
- <span data-ttu-id="48268-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="48268-1733">kaarthouders</span></span> 
- <span data-ttu-id="48268-1734">Karte</span><span class="sxs-lookup"><span data-stu-id="48268-1734">karte</span></span>  
- <span data-ttu-id="48268-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="48268-1735">karteninhaber</span></span> 
- <span data-ttu-id="48268-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="48268-1736">karteninhabers</span></span>
- <span data-ttu-id="48268-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="48268-1737">kartennr</span></span> 
- <span data-ttu-id="48268-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="48268-1738">kartennummer</span></span> 
- <span data-ttu-id="48268-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="48268-1739">kreditkarte</span></span> 
- <span data-ttu-id="48268-1740">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="48268-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="48268-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="48268-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="48268-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="48268-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="48268-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="48268-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="48268-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="48268-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="48268-1745">Maestro</span><span class="sxs-lookup"><span data-stu-id="48268-1745">maestro</span></span> 
- <span data-ttu-id="48268-1746">master card</span><span class="sxs-lookup"><span data-stu-id="48268-1746">master card</span></span> 
- <span data-ttu-id="48268-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="48268-1747">master cards</span></span> 
- <span data-ttu-id="48268-1748">MasterCard</span><span class="sxs-lookup"><span data-stu-id="48268-1748">mastercard</span></span> 
- <span data-ttu-id="48268-1749">MasterCards gesichert</span><span class="sxs-lookup"><span data-stu-id="48268-1749">mastercards</span></span> 
- <span data-ttu-id="48268-1750">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="48268-1750">mc</span></span> 
- <span data-ttu-id="48268-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="48268-1751">mister cash</span></span> 
- <span data-ttu-id="48268-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="48268-1752">n carta</span></span> 
- <span data-ttu-id="48268-1753">Carta</span><span class="sxs-lookup"><span data-stu-id="48268-1753">carta</span></span> 
- <span data-ttu-id="48268-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="48268-1754">no de tarjeta</span></span> 
- <span data-ttu-id="48268-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1755">no do cartao</span></span> 
- <span data-ttu-id="48268-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1756">no do cartão</span></span> 
- <span data-ttu-id="48268-1757">Nein.</span><span class="sxs-lookup"><span data-stu-id="48268-1757">no.</span></span> <span data-ttu-id="48268-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="48268-1758">de tarjeta</span></span> 
- <span data-ttu-id="48268-1759">Nein.</span><span class="sxs-lookup"><span data-stu-id="48268-1759">no.</span></span> <span data-ttu-id="48268-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1760">do cartao</span></span> 
- <span data-ttu-id="48268-1761">Nein.</span><span class="sxs-lookup"><span data-stu-id="48268-1761">no.</span></span> <span data-ttu-id="48268-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1762">do cartão</span></span> 
- <span data-ttu-id="48268-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="48268-1763">nr carta</span></span> 
- <span data-ttu-id="48268-1764">Nr.</span><span class="sxs-lookup"><span data-stu-id="48268-1764">nr.</span></span> <span data-ttu-id="48268-1765">Carta</span><span class="sxs-lookup"><span data-stu-id="48268-1765">carta</span></span> 
- <span data-ttu-id="48268-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="48268-1766">numeri di scheda</span></span> 
- <span data-ttu-id="48268-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="48268-1767">numero carta</span></span> 
- <span data-ttu-id="48268-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1768">numero de cartao</span></span> 
- <span data-ttu-id="48268-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="48268-1769">numero de carte</span></span> 
- <span data-ttu-id="48268-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1770">numero de cartão</span></span> 
- <span data-ttu-id="48268-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="48268-1771">numero de tarjeta</span></span>
- <span data-ttu-id="48268-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="48268-1772">numero della carta</span></span> 
- <span data-ttu-id="48268-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="48268-1773">numero di carta</span></span> 
- <span data-ttu-id="48268-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="48268-1774">numero di scheda</span></span> 
- <span data-ttu-id="48268-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1775">numero do cartao</span></span> 
- <span data-ttu-id="48268-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1776">numero do cartão</span></span> 
- <span data-ttu-id="48268-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="48268-1777">numéro de carte</span></span> 
- <span data-ttu-id="48268-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="48268-1778">nº carta</span></span> 
- <span data-ttu-id="48268-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="48268-1779">nº de carte</span></span> 
- <span data-ttu-id="48268-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="48268-1780">nº de la carte</span></span> 
- <span data-ttu-id="48268-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="48268-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="48268-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1782">nº do cartao</span></span> 
- <span data-ttu-id="48268-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1783">nº do cartão</span></span> 
- <span data-ttu-id="48268-1784">nº.</span><span class="sxs-lookup"><span data-stu-id="48268-1784">nº.</span></span> <span data-ttu-id="48268-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1785">do cartão</span></span> 
- <span data-ttu-id="48268-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1786">número de cartao</span></span> 
- <span data-ttu-id="48268-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="48268-1787">número de cartão</span></span> 
- <span data-ttu-id="48268-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="48268-1788">número de tarjeta</span></span> 
- <span data-ttu-id="48268-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="48268-1789">número do cartao</span></span> 
- <span data-ttu-id="48268-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="48268-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="48268-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="48268-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="48268-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="48268-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="48268-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="48268-1793">scheda della banca</span></span> 
- <span data-ttu-id="48268-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="48268-1794">scheda di controllo</span></span> 
- <span data-ttu-id="48268-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="48268-1795">scheda di debito</span></span> 
- <span data-ttu-id="48268-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="48268-1796">scheda matrice</span></span> 
- <span data-ttu-id="48268-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="48268-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="48268-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="48268-1798">schede di controllo</span></span> 
- <span data-ttu-id="48268-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="48268-1799">schede di debito</span></span> 
- <span data-ttu-id="48268-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="48268-1800">schede matrici</span></span> 
- <span data-ttu-id="48268-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="48268-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="48268-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="48268-1802">scoprono le schede</span></span> 
- <span data-ttu-id="48268-1803">Solo</span><span class="sxs-lookup"><span data-stu-id="48268-1803">solo</span></span> 
- <span data-ttu-id="48268-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="48268-1804">supporti di scheda</span></span> 
- <span data-ttu-id="48268-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="48268-1805">supporto di scheda</span></span> 
- <span data-ttu-id="48268-1806">Schalter</span><span class="sxs-lookup"><span data-stu-id="48268-1806">switch</span></span> 
- <span data-ttu-id="48268-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="48268-1807">tarjeta atm</span></span> 
- <span data-ttu-id="48268-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="48268-1808">tarjeta credito</span></span> 
- <span data-ttu-id="48268-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="48268-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="48268-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="48268-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="48268-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="48268-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="48268-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="48268-1812">tarjeta debito</span></span> 
- <span data-ttu-id="48268-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="48268-1813">tarjeta no</span></span>
- <span data-ttu-id="48268-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="48268-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="48268-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="48268-1815">tipo della scheda</span></span> 
- <span data-ttu-id="48268-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="48268-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="48268-1817">Scheda</span><span class="sxs-lookup"><span data-stu-id="48268-1817">scheda</span></span> 
- <span data-ttu-id="48268-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="48268-1818">v pay</span></span> 
- <span data-ttu-id="48268-1819">v-Pay</span><span class="sxs-lookup"><span data-stu-id="48268-1819">v-pay</span></span> 
- <span data-ttu-id="48268-1820">Visa</span><span class="sxs-lookup"><span data-stu-id="48268-1820">visa</span></span> 
- <span data-ttu-id="48268-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="48268-1821">visa plus</span></span> 
- <span data-ttu-id="48268-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="48268-1822">visa electron</span></span> 
- <span data-ttu-id="48268-1823">Visto</span><span class="sxs-lookup"><span data-stu-id="48268-1823">visto</span></span> 
- <span data-ttu-id="48268-1824">Visum</span><span class="sxs-lookup"><span data-stu-id="48268-1824">visum</span></span> 
- <span data-ttu-id="48268-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="48268-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="48268-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="48268-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="48268-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="48268-1827">card identification number</span></span>
- <span data-ttu-id="48268-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="48268-1828">card verification</span></span> 
- <span data-ttu-id="48268-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="48268-1829">cardi la verifica</span></span> 
- <span data-ttu-id="48268-1830">cid</span><span class="sxs-lookup"><span data-stu-id="48268-1830">cid</span></span> 
- <span data-ttu-id="48268-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="48268-1831">cod seg</span></span> 
- <span data-ttu-id="48268-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="48268-1832">cod seguranca</span></span> 
- <span data-ttu-id="48268-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1833">cod segurança</span></span> 
- <span data-ttu-id="48268-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="48268-1834">cod sicurezza</span></span> 
- <span data-ttu-id="48268-1835">COD.</span><span class="sxs-lookup"><span data-stu-id="48268-1835">cod.</span></span> <span data-ttu-id="48268-1836">SEG</span><span class="sxs-lookup"><span data-stu-id="48268-1836">seg</span></span> 
- <span data-ttu-id="48268-1837">COD.</span><span class="sxs-lookup"><span data-stu-id="48268-1837">cod.</span></span> <span data-ttu-id="48268-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="48268-1838">seguranca</span></span> 
- <span data-ttu-id="48268-1839">COD.</span><span class="sxs-lookup"><span data-stu-id="48268-1839">cod.</span></span> <span data-ttu-id="48268-1840">Segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1840">segurança</span></span> 
- <span data-ttu-id="48268-1841">COD.</span><span class="sxs-lookup"><span data-stu-id="48268-1841">cod.</span></span> <span data-ttu-id="48268-1842">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="48268-1842">sicurezza</span></span> 
- <span data-ttu-id="48268-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="48268-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="48268-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="48268-1844">codice di verifica</span></span> 
- <span data-ttu-id="48268-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="48268-1845">codigo</span></span> 
- <span data-ttu-id="48268-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="48268-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="48268-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1847">codigo de segurança</span></span> 
- <span data-ttu-id="48268-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="48268-1848">crittogramma</span></span> 
- <span data-ttu-id="48268-1849">Kryptogramm</span><span class="sxs-lookup"><span data-stu-id="48268-1849">cryptogram</span></span> 
- <span data-ttu-id="48268-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="48268-1850">cryptogramme</span></span> 
- <span data-ttu-id="48268-1851">CV2</span><span class="sxs-lookup"><span data-stu-id="48268-1851">cv2</span></span> 
- <span data-ttu-id="48268-1852">CVC</span><span class="sxs-lookup"><span data-stu-id="48268-1852">cvc</span></span> 
- <span data-ttu-id="48268-1853">CVC2</span><span class="sxs-lookup"><span data-stu-id="48268-1853">cvc2</span></span> 
- <span data-ttu-id="48268-1854">CVN</span><span class="sxs-lookup"><span data-stu-id="48268-1854">cvn</span></span> 
- <span data-ttu-id="48268-1855">CVV</span><span class="sxs-lookup"><span data-stu-id="48268-1855">cvv</span></span> 
- <span data-ttu-id="48268-1856">CVV2</span><span class="sxs-lookup"><span data-stu-id="48268-1856">cvv2</span></span> 
- <span data-ttu-id="48268-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="48268-1857">cód seguranca</span></span> 
- <span data-ttu-id="48268-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1858">cód segurança</span></span> 
- <span data-ttu-id="48268-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="48268-1859">cód.</span></span> <span data-ttu-id="48268-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="48268-1860">seguranca</span></span> 
- <span data-ttu-id="48268-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="48268-1861">cód.</span></span> <span data-ttu-id="48268-1862">Segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1862">segurança</span></span> 
- <span data-ttu-id="48268-1863">Código</span><span class="sxs-lookup"><span data-stu-id="48268-1863">código</span></span> 
- <span data-ttu-id="48268-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="48268-1864">código de seguranca</span></span> 
- <span data-ttu-id="48268-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="48268-1865">código de segurança</span></span> 
- <span data-ttu-id="48268-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="48268-1866">de kaart controle</span></span> 
- <span data-ttu-id="48268-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="48268-1867">geeft nr uit</span></span> 
- <span data-ttu-id="48268-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="48268-1868">issue no</span></span> 
- <span data-ttu-id="48268-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="48268-1869">issue number</span></span> 
- <span data-ttu-id="48268-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="48268-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="48268-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="48268-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="48268-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="48268-1873">kwestieaantal</span></span> 
- <span data-ttu-id="48268-1874">Nein.</span><span class="sxs-lookup"><span data-stu-id="48268-1874">no.</span></span> <span data-ttu-id="48268-1875">Dell ' edizione</span><span class="sxs-lookup"><span data-stu-id="48268-1875">dell'edizione</span></span> 
- <span data-ttu-id="48268-1876">Nein.</span><span class="sxs-lookup"><span data-stu-id="48268-1876">no.</span></span> <span data-ttu-id="48268-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="48268-1877">di sicurezza</span></span> 
- <span data-ttu-id="48268-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="48268-1878">numero de securite</span></span> 
- <span data-ttu-id="48268-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="48268-1879">numero de verificacao</span></span> 
- <span data-ttu-id="48268-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="48268-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="48268-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="48268-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="48268-1882">Scheda</span><span class="sxs-lookup"><span data-stu-id="48268-1882">scheda</span></span> 
- <span data-ttu-id="48268-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="48268-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="48268-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="48268-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="48268-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="48268-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="48268-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="48268-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="48268-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="48268-1887">número de verificação</span></span> 
- <span data-ttu-id="48268-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="48268-1888">perno il blocco</span></span> 
- <span data-ttu-id="48268-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="48268-1889">pin block</span></span> 
- <span data-ttu-id="48268-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="48268-1890">prufziffer</span></span> 
- <span data-ttu-id="48268-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="48268-1891">prüfziffer</span></span> 
- <span data-ttu-id="48268-1892">security code</span><span class="sxs-lookup"><span data-stu-id="48268-1892">security code</span></span> 
- <span data-ttu-id="48268-1893">security no</span><span class="sxs-lookup"><span data-stu-id="48268-1893">security no</span></span> 
- <span data-ttu-id="48268-1894">security number</span><span class="sxs-lookup"><span data-stu-id="48268-1894">security number</span></span> 
- <span data-ttu-id="48268-1895">Sicherheitskode</span><span class="sxs-lookup"><span data-stu-id="48268-1895">sicherheits kode</span></span> 
- <span data-ttu-id="48268-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="48268-1896">sicherheitscode</span></span> 
- <span data-ttu-id="48268-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="48268-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="48268-1898">speldblok</span></span> 
- <span data-ttu-id="48268-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="48268-1899">veiligheid nr</span></span> 
- <span data-ttu-id="48268-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="48268-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="48268-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="48268-1901">veiligheidscode</span></span> 
- <span data-ttu-id="48268-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="48268-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="48268-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="48268-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="48268-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="48268-1905">Ablauf</span><span class="sxs-lookup"><span data-stu-id="48268-1905">ablauf</span></span> 
- <span data-ttu-id="48268-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="48268-1906">data de expiracao</span></span> 
- <span data-ttu-id="48268-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="48268-1907">data de expiração</span></span> 
- <span data-ttu-id="48268-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="48268-1908">data del exp</span></span> 
- <span data-ttu-id="48268-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="48268-1909">data di exp</span></span> 
- <span data-ttu-id="48268-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="48268-1910">data di scadenza</span></span> 
- <span data-ttu-id="48268-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="48268-1911">data em que expira</span></span> 
- <span data-ttu-id="48268-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="48268-1912">data scad</span></span> 
- <span data-ttu-id="48268-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="48268-1913">data scadenza</span></span> 
- <span data-ttu-id="48268-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="48268-1914">date de validité</span></span> 
- <span data-ttu-id="48268-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="48268-1915">datum afloop</span></span> 
- <span data-ttu-id="48268-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="48268-1916">datum van exp</span></span> 
- <span data-ttu-id="48268-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="48268-1917">de afloop</span></span> 
- <span data-ttu-id="48268-1918">Espira</span><span class="sxs-lookup"><span data-stu-id="48268-1918">espira</span></span> 
- <span data-ttu-id="48268-1919">Espira</span><span class="sxs-lookup"><span data-stu-id="48268-1919">espira</span></span> 
- <span data-ttu-id="48268-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="48268-1920">exp date</span></span> 
- <span data-ttu-id="48268-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="48268-1921">exp datum</span></span> 
- <span data-ttu-id="48268-1922">Ablauf</span><span class="sxs-lookup"><span data-stu-id="48268-1922">expiration</span></span> 
- <span data-ttu-id="48268-1923">ablaufen</span><span class="sxs-lookup"><span data-stu-id="48268-1923">expire</span></span> 
- <span data-ttu-id="48268-1924">abläuft</span><span class="sxs-lookup"><span data-stu-id="48268-1924">expires</span></span> 
- <span data-ttu-id="48268-1925">Ablauf</span><span class="sxs-lookup"><span data-stu-id="48268-1925">expiry</span></span> 
- <span data-ttu-id="48268-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="48268-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="48268-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="48268-1927">fecha de venc</span></span> 
- <span data-ttu-id="48268-1928">Gultig bis</span><span class="sxs-lookup"><span data-stu-id="48268-1928">gultig bis</span></span> 
- <span data-ttu-id="48268-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="48268-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="48268-1930">Gültig bis</span><span class="sxs-lookup"><span data-stu-id="48268-1930">gültig bis</span></span> 
- <span data-ttu-id="48268-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="48268-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="48268-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="48268-1932">la scadenza</span></span> 
- <span data-ttu-id="48268-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="48268-1933">scadenza</span></span> 
- <span data-ttu-id="48268-1934">valable</span><span class="sxs-lookup"><span data-stu-id="48268-1934">valable</span></span> 
- <span data-ttu-id="48268-1935">validade</span><span class="sxs-lookup"><span data-stu-id="48268-1935">validade</span></span> 
- <span data-ttu-id="48268-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="48268-1936">valido hasta</span></span> 
- <span data-ttu-id="48268-1937">Valor</span><span class="sxs-lookup"><span data-stu-id="48268-1937">valor</span></span> 
- <span data-ttu-id="48268-1938">venc</span><span class="sxs-lookup"><span data-stu-id="48268-1938">venc</span></span> 
- <span data-ttu-id="48268-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="48268-1939">vencimento</span></span> 
- <span data-ttu-id="48268-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="48268-1940">vencimiento</span></span> 
- <span data-ttu-id="48268-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="48268-1941">verloopt</span></span> 
- <span data-ttu-id="48268-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="48268-1942">vervaldag</span></span> 
- <span data-ttu-id="48268-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="48268-1943">vervaldatum</span></span> 
- <span data-ttu-id="48268-1944">VTO</span><span class="sxs-lookup"><span data-stu-id="48268-1944">vto</span></span> 
- <span data-ttu-id="48268-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="48268-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="48268-1946">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1946">EU Driver's License Number</span></span>

<span data-ttu-id="48268-1947">Weitere Informationen finden Sie unter [EU-Führerscheinnummer vertraulicher Informationstyp](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="48268-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="48268-1948">EU-nationale Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1948">EU National Identification Number</span></span>

<span data-ttu-id="48268-1949">Weitere Informationen finden Sie unter [sensible Informationstypen für die nationale Identifikationsnummer der EU](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="48268-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="48268-1950">EU-Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="48268-1950">EU Passport Number</span></span>

<span data-ttu-id="48268-1951">Weitere Informationen finden Sie unter [sensible Informationstypen für EU-Passport-Nummern](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="48268-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="48268-1952">EU-Sozialversicherungsnummer oder gleichwertige ID</span><span class="sxs-lookup"><span data-stu-id="48268-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="48268-1953">Weitere Informationen finden Sie unter [EU-Sozialversicherungsnummer oder gleichwertiger ID-Typ für vertrauliche Informationen](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="48268-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="48268-1954">EU-Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="48268-1955">Weitere Informationen finden Sie unter [vertraulicher Informationstyp der EU-Steueridentifikationsnummer](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="48268-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="48268-1956">Finland National ID (Finnischer Personalausweis)</span><span class="sxs-lookup"><span data-stu-id="48268-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="48268-1957">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1957">Format</span></span>

<span data-ttu-id="48268-1958">Sechs Ziffern plus ein Zeichen, das ein Jahrhundert angibt, plus drei Ziffern plus einer Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="48268-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1959">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1959">Pattern</span></span>

<span data-ttu-id="48268-1960">Das Muster muss Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="48268-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="48268-1961">Sechs Ziffern im Format TTMMJJ, die ein Geburtsdatum darstellen</span><span class="sxs-lookup"><span data-stu-id="48268-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="48268-1962">Jahrhundertkennzeichnung (entweder „-“, „+“ oder „a“)</span><span class="sxs-lookup"><span data-stu-id="48268-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="48268-1963">Dreistellige persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="48268-1964">Eine Ziffer oder ein Buchstabe (Groß-/Kleinschreibung irrelevant), die bzw. der eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="48268-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1965">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1965">Checksum</span></span>

<span data-ttu-id="48268-1966">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1967">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1967">Definition</span></span>

<span data-ttu-id="48268-1968">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1969">Die Funktion Func_finnish_national_id findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1970">Ein Schlüsselwort aus Keyword_finnish_national_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="48268-1971">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-1972">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1972">Keywords</span></span>

- <span data-ttu-id="48268-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="48268-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="48268-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="48268-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="48268-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="48268-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="48268-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="48268-1976">Personbeteckning</span></span>
- <span data-ttu-id="48268-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="48268-1978">Finnland – Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1978">Finland Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1979">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1979">Format</span></span>
<span data-ttu-id="48268-1980">Kombination aus neun Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1980">Combination of nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1981">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1981">Pattern</span></span>
<span data-ttu-id="48268-1982">Kombination von neun Buchstaben und Ziffern: zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet) sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1982">Combination of nine letters and digits: Two letters (not case sensitive) Seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1983">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1983">Checksum</span></span>
<span data-ttu-id="48268-1984">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-1984">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-1985">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-1985">Definition</span></span>
<span data-ttu-id="48268-1986">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-1986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-1987">Der reguläre Ausdruck Regex_finland_passport_number findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-1987">The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-1988">Ein Schlüsselwort aus Keyword_finland_passport_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-1988">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
```xml
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="48268-1989">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-1989">Keywords</span></span>
- <span data-ttu-id="48268-1990">Keyword_finland_passport_number</span><span class="sxs-lookup"><span data-stu-id="48268-1990">Keyword_finland_passport_number</span></span>
- <span data-ttu-id="48268-1991">Pass</span><span class="sxs-lookup"><span data-stu-id="48268-1991">Passport</span></span>
- <span data-ttu-id="48268-1992">Passi</span><span class="sxs-lookup"><span data-stu-id="48268-1992">Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="48268-1993">Französische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-1993">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-1994">Format</span><span class="sxs-lookup"><span data-stu-id="48268-1994">Format</span></span>

<span data-ttu-id="48268-1995">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-1995">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-1996">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-1996">Pattern</span></span>

<span data-ttu-id="48268-1997">12 Ziffern mit Validierung, um ähnliche Muster ( z. B. französische Telefonnummern) auszuschließen</span><span class="sxs-lookup"><span data-stu-id="48268-1997">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-1998">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-1998">Checksum</span></span>

<span data-ttu-id="48268-1999">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-1999">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2000">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2000">Definition</span></span>

<span data-ttu-id="48268-2001">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2001">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2002">Die Funktion Func_french_drivers_license findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2002">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2003">Mindestens eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="48268-2003">At least one of the following is true:</span></span>
- <span data-ttu-id="48268-2004">Ein Schlüsselwort aus Keyword_french_drivers_license wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2004">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="48268-2005">Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="48268-2005">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2006">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2006">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="48268-2007">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="48268-2007">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="48268-2008">drivers licence</span><span class="sxs-lookup"><span data-stu-id="48268-2008">drivers licence</span></span>
- <span data-ttu-id="48268-2009">drivers license</span><span class="sxs-lookup"><span data-stu-id="48268-2009">drivers license</span></span>
- <span data-ttu-id="48268-2010">Führerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2010">driving licence</span></span>
- <span data-ttu-id="48268-2011">driving license</span><span class="sxs-lookup"><span data-stu-id="48268-2011">driving license</span></span>
- <span data-ttu-id="48268-2012">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="48268-2012">permis de conduire</span></span>
- <span data-ttu-id="48268-2013">licence number</span><span class="sxs-lookup"><span data-stu-id="48268-2013">licence number</span></span>
- <span data-ttu-id="48268-2014">license number</span><span class="sxs-lookup"><span data-stu-id="48268-2014">license number</span></span>
- <span data-ttu-id="48268-2015">licence numbers</span><span class="sxs-lookup"><span data-stu-id="48268-2015">licence numbers</span></span>
- <span data-ttu-id="48268-2016">license numbers</span><span class="sxs-lookup"><span data-stu-id="48268-2016">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="48268-2017">Französische Carte nationale d'identité (CNI)</span><span class="sxs-lookup"><span data-stu-id="48268-2017">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="48268-2018">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2018">Format</span></span>

<span data-ttu-id="48268-2019">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2019">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2020">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2020">Pattern</span></span>

<span data-ttu-id="48268-2021">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2021">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2022">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2022">Checksum</span></span>

<span data-ttu-id="48268-2023">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2023">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2024">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2024">Definition</span></span>

<span data-ttu-id="48268-2025">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2025">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2026">Der reguläre Ausdruck Regex_france_cni findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2026">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2027">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2027">Keywords</span></span>

<span data-ttu-id="48268-2028">Keine</span><span class="sxs-lookup"><span data-stu-id="48268-2028">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="48268-2029">Französische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2029">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2030">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2030">Format</span></span>

<span data-ttu-id="48268-2031">Neun Ziffern und Buchstaben</span><span class="sxs-lookup"><span data-stu-id="48268-2031">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2032">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2032">Pattern</span></span>

<span data-ttu-id="48268-2033">Neun Ziffern und Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="48268-2033">Nine digits and letters:</span></span>
- <span data-ttu-id="48268-2034">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2034">Two digits</span></span> 
- <span data-ttu-id="48268-2035">Zwei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="48268-2035">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="48268-2036">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2036">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2037">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2037">Checksum</span></span>

<span data-ttu-id="48268-2038">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2038">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2039">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2039">Definition</span></span>

<span data-ttu-id="48268-2040">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2040">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2041">Die Funktion Func_fr_passport findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2041">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2042">Ein Schlüsselwort aus Keyword_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2042">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2043">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2043">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="48268-2044">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="48268-2044">Keyword_passport</span></span>

- <span data-ttu-id="48268-2045">Passport Number</span><span class="sxs-lookup"><span data-stu-id="48268-2045">Passport Number</span></span>
- <span data-ttu-id="48268-2046">Passport No</span><span class="sxs-lookup"><span data-stu-id="48268-2046">Passport No</span></span>
- <span data-ttu-id="48268-2047">Passport#</span><span class="sxs-lookup"><span data-stu-id="48268-2047">Passport #</span></span>
- <span data-ttu-id="48268-2048">Pass #</span><span class="sxs-lookup"><span data-stu-id="48268-2048">Passport#</span></span>
- <span data-ttu-id="48268-2049">Passport-Nr</span><span class="sxs-lookup"><span data-stu-id="48268-2049">PassportID</span></span>
- <span data-ttu-id="48268-2050">Passportno</span><span class="sxs-lookup"><span data-stu-id="48268-2050">Passportno</span></span>
- <span data-ttu-id="48268-2051">passportnumber</span><span class="sxs-lookup"><span data-stu-id="48268-2051">passportnumber</span></span>
- <span data-ttu-id="48268-2052">パスポート</span><span class="sxs-lookup"><span data-stu-id="48268-2052">パスポート</span></span>
- <span data-ttu-id="48268-2053">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="48268-2053">パスポート番号</span></span>
- <span data-ttu-id="48268-2054">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="48268-2054">パスポートのNum</span></span>
- <span data-ttu-id="48268-2055">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="48268-2055">パスポート ＃</span></span> 
- <span data-ttu-id="48268-2056">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="48268-2056">Numéro de passeport</span></span>
- <span data-ttu-id="48268-2057">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="48268-2057">Passeport n °</span></span>
- <span data-ttu-id="48268-2058">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="48268-2058">Passeport Non</span></span>
- <span data-ttu-id="48268-2059">Passeport#</span><span class="sxs-lookup"><span data-stu-id="48268-2059">Passeport #</span></span>
- <span data-ttu-id="48268-2060">Passeport #</span><span class="sxs-lookup"><span data-stu-id="48268-2060">Passeport#</span></span>
- <span data-ttu-id="48268-2061">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="48268-2061">PasseportNon</span></span>
- <span data-ttu-id="48268-2062">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="48268-2062">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="48268-2063">Französische Sozialversicherungsnummer (INSEE)</span><span class="sxs-lookup"><span data-stu-id="48268-2063">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="48268-2064">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2064">Format</span></span>

<span data-ttu-id="48268-2065">15 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2065">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2066">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2066">Pattern</span></span>

<span data-ttu-id="48268-2067">Muss einem von zwei Mustern entsprechen:</span><span class="sxs-lookup"><span data-stu-id="48268-2067">Must match one of two patterns:</span></span>
- <span data-ttu-id="48268-2068">13 Ziffern, gefolgt von einem Leerzeichen, gefolgt von zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2068">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="48268-2069">oder</span><span class="sxs-lookup"><span data-stu-id="48268-2069">or</span></span>
- <span data-ttu-id="48268-2070">15 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2070">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2071">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2071">Checksum</span></span>

<span data-ttu-id="48268-2072">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2072">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2073">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2073">Definition</span></span>

<span data-ttu-id="48268-2074">Eine DLP-Richtlinie ist zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2074">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2075">Die Funktion Func_french_insee oder Func_fr_insee findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2075">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2076">Ein Schlüsselwort aus Keyword_fr_insee wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2076">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="48268-2077">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2077">The checksum passes.</span></span>

<span data-ttu-id="48268-2078">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2078">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2079">Die Funktion Func_french_insee oder Func_fr_insee findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2079">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2080">Es wurde kein Schlüsselwort aus Keyword_fr_insee gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2080">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="48268-2081">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2081">The checksum passes.</span></span>

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2082">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2082">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="48268-2083">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="48268-2083">Keyword_fr_insee</span></span>

- <span data-ttu-id="48268-2084">INSEE</span><span class="sxs-lookup"><span data-stu-id="48268-2084">insee</span></span>
- <span data-ttu-id="48268-2085">securité sociale</span><span class="sxs-lookup"><span data-stu-id="48268-2085">securité sociale</span></span>
- <span data-ttu-id="48268-2086">securite sociale</span><span class="sxs-lookup"><span data-stu-id="48268-2086">securite sociale</span></span>
- <span data-ttu-id="48268-2087">national id</span><span class="sxs-lookup"><span data-stu-id="48268-2087">national id</span></span>
- <span data-ttu-id="48268-2088">national identification</span><span class="sxs-lookup"><span data-stu-id="48268-2088">national identification</span></span>
- <span data-ttu-id="48268-2089">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="48268-2089">numéro d'identité</span></span>
- <span data-ttu-id="48268-2090">no d'identité</span><span class="sxs-lookup"><span data-stu-id="48268-2090">no d'identité</span></span>
- <span data-ttu-id="48268-2091">Nein.</span><span class="sxs-lookup"><span data-stu-id="48268-2091">no.</span></span> <span data-ttu-id="48268-2092">d ' identité</span><span class="sxs-lookup"><span data-stu-id="48268-2092">d'identité</span></span>
- <span data-ttu-id="48268-2093">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="48268-2093">numero d'identite</span></span>
- <span data-ttu-id="48268-2094">no d'identite</span><span class="sxs-lookup"><span data-stu-id="48268-2094">no d'identite</span></span>
- <span data-ttu-id="48268-2095">Nein.</span><span class="sxs-lookup"><span data-stu-id="48268-2095">no.</span></span> <span data-ttu-id="48268-2096">d'identite</span><span class="sxs-lookup"><span data-stu-id="48268-2096">d'identite</span></span>
- <span data-ttu-id="48268-2097">social security number</span><span class="sxs-lookup"><span data-stu-id="48268-2097">social security number</span></span>
- <span data-ttu-id="48268-2098">social security code</span><span class="sxs-lookup"><span data-stu-id="48268-2098">social security code</span></span>
- <span data-ttu-id="48268-2099">social insurance number</span><span class="sxs-lookup"><span data-stu-id="48268-2099">social insurance number</span></span>
- <span data-ttu-id="48268-2100">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="48268-2100">le numéro d'identification nationale</span></span>
- <span data-ttu-id="48268-2101">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="48268-2101">d'identité nationale</span></span>
- <span data-ttu-id="48268-2102">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="48268-2102">numéro de sécurité sociale</span></span>
- <span data-ttu-id="48268-2103">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="48268-2103">le code de la sécurité sociale</span></span>
- <span data-ttu-id="48268-2104">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="48268-2104">numéro d'assurance sociale</span></span>
- <span data-ttu-id="48268-2105">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="48268-2105">numéro de sécu</span></span>
- <span data-ttu-id="48268-2106">code sécu</span><span class="sxs-lookup"><span data-stu-id="48268-2106">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="48268-2107">Deutsche Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2107">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2108">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2108">Format</span></span>

<span data-ttu-id="48268-2109">Kombination von 11 Ziffern und Buchstaben</span><span class="sxs-lookup"><span data-stu-id="48268-2109">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2110">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2110">Pattern</span></span>

<span data-ttu-id="48268-2111">11 Zahlen und Buchstaben (ohne Beachtung der Groß-/Kleinschreibung):</span><span class="sxs-lookup"><span data-stu-id="48268-2111">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="48268-2112">Eine Ziffer oder ein Buchstabe</span><span class="sxs-lookup"><span data-stu-id="48268-2112">A digit or letter</span></span> 
- <span data-ttu-id="48268-2113">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2113">Two digits</span></span> 
- <span data-ttu-id="48268-2114">Sechs Ziffern oder Buchstaben</span><span class="sxs-lookup"><span data-stu-id="48268-2114">Six digits or letters</span></span> 
- <span data-ttu-id="48268-2115">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="48268-2115">A digit</span></span> 
- <span data-ttu-id="48268-2116">Eine Ziffer oder ein Buchstabe</span><span class="sxs-lookup"><span data-stu-id="48268-2116">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2117">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2117">Checksum</span></span>

<span data-ttu-id="48268-2118">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2118">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2119">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2119">Definition</span></span>

<span data-ttu-id="48268-2120">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2120">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2121">Die Funktion Func_german_drivers_license findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2121">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2122">Mindestens eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="48268-2122">At least one of the following is true:</span></span>
    - <span data-ttu-id="48268-2123">Ein Schlüsselwort aus Keyword_german_drivers_license_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2123">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="48268-2124">Ein Schlüsselwort aus Keyword_german_drivers_license_collaborative wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2124">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="48268-2125">Ein Schlüsselwort aus Keyword_german_drivers_license wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2125">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="48268-2126">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2126">The checksum passes.</span></span>

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2127">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2127">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="48268-2128">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="48268-2128">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="48268-2129">Führerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2129">Führerschein</span></span>
- <span data-ttu-id="48268-2130">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2130">Fuhrerschein</span></span>
- <span data-ttu-id="48268-2131">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2131">Fuehrerschein</span></span>
- <span data-ttu-id="48268-2132">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2132">Führerscheinnummer</span></span>
- <span data-ttu-id="48268-2133">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2133">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="48268-2134">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2134">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="48268-2135">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="48268-2135">Führerschein-</span></span> 
- <span data-ttu-id="48268-2136">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="48268-2136">Fuhrerschein-</span></span> 
- <span data-ttu-id="48268-2137">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="48268-2137">Fuehrerschein-</span></span> 
- <span data-ttu-id="48268-2138">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="48268-2138">FührerscheinnummerNr</span></span>
- <span data-ttu-id="48268-2139">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="48268-2139">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="48268-2140">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="48268-2140">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="48268-2141">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="48268-2141">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="48268-2142">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="48268-2142">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="48268-2143">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="48268-2143">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="48268-2144">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="48268-2144">Führerschein- Nr</span></span>
- <span data-ttu-id="48268-2145">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="48268-2145">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="48268-2146">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="48268-2146">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="48268-2147">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="48268-2147">Führerschein- Klasse</span></span> 
- <span data-ttu-id="48268-2148">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="48268-2148">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="48268-2149">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="48268-2149">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="48268-2150">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="48268-2150">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="48268-2151">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="48268-2151">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="48268-2152">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="48268-2152">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="48268-2153">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="48268-2153">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="48268-2154">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="48268-2154">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="48268-2155">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="48268-2155">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="48268-2156">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="48268-2156">Führerschein- Nr</span></span> 
- <span data-ttu-id="48268-2157">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="48268-2157">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="48268-2158">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="48268-2158">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="48268-2159">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="48268-2159">Führerschein- Klasse</span></span> 
- <span data-ttu-id="48268-2160">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="48268-2160">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="48268-2161">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="48268-2161">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="48268-2162">DL</span><span class="sxs-lookup"><span data-stu-id="48268-2162">DL</span></span> 
- <span data-ttu-id="48268-2163">DLS</span><span class="sxs-lookup"><span data-stu-id="48268-2163">DLS</span></span>
- <span data-ttu-id="48268-2164">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="48268-2164">Driv Lic</span></span> 
- <span data-ttu-id="48268-2165">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="48268-2165">Driv Licen</span></span> 
- <span data-ttu-id="48268-2166">Driv License</span><span class="sxs-lookup"><span data-stu-id="48268-2166">Driv License</span></span>
- <span data-ttu-id="48268-2167">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-2167">Driv Licenses</span></span> 
- <span data-ttu-id="48268-2168">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="48268-2168">Driv Licence</span></span> 
- <span data-ttu-id="48268-2169">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="48268-2169">Driv Licences</span></span> 
- <span data-ttu-id="48268-2170">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="48268-2170">Driv Lic</span></span> 
- <span data-ttu-id="48268-2171">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="48268-2171">Driver Licen</span></span> 
- <span data-ttu-id="48268-2172">Driver License</span><span class="sxs-lookup"><span data-stu-id="48268-2172">Driver License</span></span> 
- <span data-ttu-id="48268-2173">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-2173">Driver Licenses</span></span> 
- <span data-ttu-id="48268-2174">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="48268-2174">Driver Licence</span></span> 
- <span data-ttu-id="48268-2175">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="48268-2175">Driver Licences</span></span> 
- <span data-ttu-id="48268-2176">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="48268-2176">Drivers Lic</span></span> 
- <span data-ttu-id="48268-2177">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="48268-2177">Drivers Licen</span></span> 
- <span data-ttu-id="48268-2178">Drivers License</span><span class="sxs-lookup"><span data-stu-id="48268-2178">Drivers License</span></span> 
- <span data-ttu-id="48268-2179">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-2179">Drivers Licenses</span></span> 
- <span data-ttu-id="48268-2180">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="48268-2180">Drivers Licence</span></span> 
- <span data-ttu-id="48268-2181">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="48268-2181">Drivers Licences</span></span> 
- <span data-ttu-id="48268-2182">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="48268-2182">Driver's Lic</span></span> 
- <span data-ttu-id="48268-2183">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="48268-2183">Driver's Licen</span></span> 
- <span data-ttu-id="48268-2184">Driver's License</span><span class="sxs-lookup"><span data-stu-id="48268-2184">Driver's License</span></span> 
- <span data-ttu-id="48268-2185">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-2185">Driver's Licenses</span></span> 
- <span data-ttu-id="48268-2186">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="48268-2186">Driver's Licence</span></span> 
- <span data-ttu-id="48268-2187">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="48268-2187">Driver's Licences</span></span> 
- <span data-ttu-id="48268-2188">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="48268-2188">Driving Lic</span></span> 
- <span data-ttu-id="48268-2189">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="48268-2189">Driving Licen</span></span> 
- <span data-ttu-id="48268-2190">Driving License</span><span class="sxs-lookup"><span data-stu-id="48268-2190">Driving License</span></span> 
- <span data-ttu-id="48268-2191">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-2191">Driving Licenses</span></span> 
- <span data-ttu-id="48268-2192">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="48268-2192">Driving Licence</span></span> 
- <span data-ttu-id="48268-2193">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="48268-2193">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="48268-2194">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="48268-2194">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="48268-2195">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2195">Nr-Führerschein</span></span> 
- <span data-ttu-id="48268-2196">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2196">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="48268-2197">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2197">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="48268-2198">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2198">No-Führerschein</span></span> 
- <span data-ttu-id="48268-2199">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2199">No-Fuhrerschein</span></span> 
- <span data-ttu-id="48268-2200">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2200">No-Fuehrerschein</span></span> 
- <span data-ttu-id="48268-2201">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2201">N-Führerschein</span></span> 
- <span data-ttu-id="48268-2202">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2202">N-Fuhrerschein</span></span> 
- <span data-ttu-id="48268-2203">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2203">N-Fuehrerschein</span></span>
- <span data-ttu-id="48268-2204">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2204">Nr-Führerschein</span></span> 
- <span data-ttu-id="48268-2205">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2205">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="48268-2206">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2206">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="48268-2207">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2207">No-Führerschein</span></span> 
- <span data-ttu-id="48268-2208">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2208">No-Fuhrerschein</span></span> 
- <span data-ttu-id="48268-2209">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2209">No-Fuehrerschein</span></span> 
- <span data-ttu-id="48268-2210">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2210">N-Führerschein</span></span> 
- <span data-ttu-id="48268-2211">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2211">N-Fuhrerschein</span></span> 
- <span data-ttu-id="48268-2212">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="48268-2212">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="48268-2213">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="48268-2213">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="48268-2214">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="48268-2214">ausstellungsdatum</span></span>
- <span data-ttu-id="48268-2215">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="48268-2215">ausstellungsort</span></span>
- <span data-ttu-id="48268-2216">Ausstellende Behöde</span><span class="sxs-lookup"><span data-stu-id="48268-2216">ausstellende behöde</span></span>
- <span data-ttu-id="48268-2217">Ausstellende Behorde</span><span class="sxs-lookup"><span data-stu-id="48268-2217">ausstellende behorde</span></span>
- <span data-ttu-id="48268-2218">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="48268-2218">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="48268-2219">Deutsche Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2219">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2220">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2220">Format</span></span>

<span data-ttu-id="48268-2221">10 Ziffern oder Buchstaben</span><span class="sxs-lookup"><span data-stu-id="48268-2221">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2222">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2222">Pattern</span></span>

<span data-ttu-id="48268-2223">Das Muster muss Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="48268-2223">Pattern must include all of the following:</span></span>
- <span data-ttu-id="48268-2224">Das erste Zeichen ist eine Ziffer oder ein Buchstabe aus dieser Gruppe (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="48268-2224">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="48268-2225">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2225">Three digits</span></span> 
- <span data-ttu-id="48268-2226">Fünf Ziffern oder Buchstaben aus dieser Gruppe (C -H, J-N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="48268-2226">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="48268-2227">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="48268-2227">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2228">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2228">Checksum</span></span>

<span data-ttu-id="48268-2229">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2229">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2230">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2230">Definition</span></span>

<span data-ttu-id="48268-2231">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2231">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2232">Die Funktion Func_german_passport findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2232">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2233">Ein Schlüsselwort aus einer der fünf Schlüsselwortlisten wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2233">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="48268-2234">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2234">The checksum passes.</span></span>

<span data-ttu-id="48268-2235">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2236">Die Funktion Func_german_passport_data findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2236">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2237">Ein Schlüsselwort aus einer der fünf Schlüsselwortlisten wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2237">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="48268-2238">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2238">The checksum passes.</span></span>

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2239">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2239">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="48268-2240">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="48268-2240">Keyword_german_passport</span></span>

- <span data-ttu-id="48268-2241">Reisepass</span><span class="sxs-lookup"><span data-stu-id="48268-2241">reisepass</span></span>
- <span data-ttu-id="48268-2242">reisepasse</span><span class="sxs-lookup"><span data-stu-id="48268-2242">reisepasse</span></span>
- <span data-ttu-id="48268-2243">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2243">reisepassnummer</span></span>
- <span data-ttu-id="48268-2244">Pass</span><span class="sxs-lookup"><span data-stu-id="48268-2244">passport</span></span>
- <span data-ttu-id="48268-2245">Pässe</span><span class="sxs-lookup"><span data-stu-id="48268-2245">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="48268-2246">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="48268-2246">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="48268-2247">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="48268-2247">geburtsdatum</span></span>
- <span data-ttu-id="48268-2248">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="48268-2248">ausstellungsdatum</span></span>
- <span data-ttu-id="48268-2249">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="48268-2249">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="48268-2250">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="48268-2250">Keyword_german_passport_number</span></span>

<span data-ttu-id="48268-2251">No-Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="48268-2251">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="48268-2252">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="48268-2252">Keyword_german_passport1</span></span>

<span data-ttu-id="48268-2253">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="48268-2253">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="48268-2254">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="48268-2254">Keyword_german_passport2</span></span>

<span data-ttu-id="48268-2255">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="48268-2255">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="48268-2256">Deutsche Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2256">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2257">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2257">Format</span></span>

<span data-ttu-id="48268-2258">Seit dem 1. November 2010: neun Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2258">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="48268-2259">Vom 1. April 1987 bis 31. Oktober 2010:10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2259">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2260">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2260">Pattern</span></span>

<span data-ttu-id="48268-2261">Seit 1. November 2010:</span><span class="sxs-lookup"><span data-stu-id="48268-2261">Since 1 November 2010:</span></span>
- <span data-ttu-id="48268-2262">Ein Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="48268-2262">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="48268-2263">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2263">Eight digits</span></span>

<span data-ttu-id="48268-2264">Vom 1. April 1987 bis 31. Oktober 2010:</span><span class="sxs-lookup"><span data-stu-id="48268-2264">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="48268-2265">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2265">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2266">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2266">Checksum</span></span>

<span data-ttu-id="48268-2267">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2267">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2268">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2268">Definition</span></span>

<span data-ttu-id="48268-2269">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2269">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2270">Der reguläre Ausdruck Regex_germany_id_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2270">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2271">Ein Schlüsselwort aus Keyword_germany_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2271">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2272">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2272">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="48268-2273">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="48268-2273">Keyword_germany_id_card</span></span>

- <span data-ttu-id="48268-2274">Identity Card</span><span class="sxs-lookup"><span data-stu-id="48268-2274">Identity Card</span></span>
- <span data-ttu-id="48268-2275">ID</span><span class="sxs-lookup"><span data-stu-id="48268-2275">ID</span></span>
- <span data-ttu-id="48268-2276">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="48268-2276">Identification</span></span>
- <span data-ttu-id="48268-2277">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="48268-2277">Personalausweis</span></span>
- <span data-ttu-id="48268-2278">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2278">Identifizierungsnummer</span></span>
- <span data-ttu-id="48268-2279">Ausweis</span><span class="sxs-lookup"><span data-stu-id="48268-2279">Ausweis</span></span>
- <span data-ttu-id="48268-2280">Identifikation</span><span class="sxs-lookup"><span data-stu-id="48268-2280">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="48268-2281">Griechenland – Personalausweis</span><span class="sxs-lookup"><span data-stu-id="48268-2281">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="48268-2282">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2282">Format</span></span>

<span data-ttu-id="48268-2283">Kombination von 7-8 Buchstaben und Zahlen plus einem Gedankenstrich</span><span class="sxs-lookup"><span data-stu-id="48268-2283">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2284">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2284">Pattern</span></span>

<span data-ttu-id="48268-2285">Sieben Buchstaben und Zahlen (altes Format):</span><span class="sxs-lookup"><span data-stu-id="48268-2285">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="48268-2286">Ein Buchstabe (jeder Buchstabe des griechischen Alphabets) </span><span class="sxs-lookup"><span data-stu-id="48268-2286">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="48268-2287">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-2287">A dash</span></span> 
- <span data-ttu-id="48268-2288">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2288">Six digits</span></span>

<span data-ttu-id="48268-2289">Acht Buchstaben und Zahlen (neues Format):</span><span class="sxs-lookup"><span data-stu-id="48268-2289">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="48268-2290">Zwei Buchstaben, deren Großbuchstabe sowohl im griechischen als auch lateinischen Alphabet (ABEZHIKMNOPTYX) vorkommt </span><span class="sxs-lookup"><span data-stu-id="48268-2290">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="48268-2291">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-2291">A dash</span></span> 
- <span data-ttu-id="48268-2292">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2292">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2293">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2293">Checksum</span></span>

<span data-ttu-id="48268-2294">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2294">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2295">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2295">Definition</span></span>

<span data-ttu-id="48268-2296">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2297">Der reguläre Ausdruck Regex_greece_id_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2297">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2298">Ein Schlüsselwort aus Keyword_greece_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2298">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2299">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2299">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="48268-2300">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="48268-2300">Keyword_greece_id_card</span></span>

- <span data-ttu-id="48268-2301">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="48268-2301">Greek identity Card</span></span>
- <span data-ttu-id="48268-2302">Tautotita</span><span class="sxs-lookup"><span data-stu-id="48268-2302">Tautotita</span></span>
- <span data-ttu-id="48268-2303">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="48268-2303">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="48268-2304">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="48268-2304">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="48268-2305">Hongkong (HKID) - Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2305">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2306">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2306">Format</span></span>

<span data-ttu-id="48268-2307">Kombination aus 8-9Buchstaben und Zahlen sowie optionale Klammern um das letzte Zeichen</span><span class="sxs-lookup"><span data-stu-id="48268-2307">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2308">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2308">Pattern</span></span>

<span data-ttu-id="48268-2309">Kombination aus Buchstaben 8-9 Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="48268-2309">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="48268-2310">1-2 Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="48268-2310">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="48268-2311">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2311">Six digits</span></span> 
- <span data-ttu-id="48268-2312">Das letzte Zeichen (eine Ziffer oder der Buchstabe A), bei dem es sich um die Prüfziffer handelt, die optional in Klammern eingeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="48268-2312">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2313">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2313">Checksum</span></span>

<span data-ttu-id="48268-2314">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2314">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2315">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2315">Definition</span></span>

<span data-ttu-id="48268-2316">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2317">Die Funktion Func_hong_kong_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2317">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2318">Ein Schlüsselwort aus Keyword_hong_kong_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2318">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="48268-2319">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2319">The checksum passes.</span></span>

<span data-ttu-id="48268-2320">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2320">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2321">Die Funktion Func_hong_kong_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2321">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2322">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2322">The checksum passes.</span></span>

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2323">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2323">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="48268-2324">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="48268-2324">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="48268-2325">Hong Kong Identity Card</span><span class="sxs-lookup"><span data-stu-id="48268-2325">hong kong identity card</span></span>
- <span data-ttu-id="48268-2326">HKIDC</span><span class="sxs-lookup"><span data-stu-id="48268-2326">HKIDC</span></span>
- <span data-ttu-id="48268-2327">id card</span><span class="sxs-lookup"><span data-stu-id="48268-2327">id card</span></span>
- <span data-ttu-id="48268-2328">identity card</span><span class="sxs-lookup"><span data-stu-id="48268-2328">identity card</span></span>
- <span data-ttu-id="48268-2329">HK-Personalausweis</span><span class="sxs-lookup"><span data-stu-id="48268-2329">hk identity card</span></span>
- <span data-ttu-id="48268-2330">Hong Kong-ID</span><span class="sxs-lookup"><span data-stu-id="48268-2330">hong kong id</span></span>
- <span data-ttu-id="48268-2331">香港身份證</span><span class="sxs-lookup"><span data-stu-id="48268-2331">香港身份證</span></span>
- <span data-ttu-id="48268-2332">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="48268-2332">香港永久性居民身份證</span></span>
- <span data-ttu-id="48268-2333">身份證</span><span class="sxs-lookup"><span data-stu-id="48268-2333">身份證</span></span>
- <span data-ttu-id="48268-2334">身份証</span><span class="sxs-lookup"><span data-stu-id="48268-2334">身份証</span></span>
- <span data-ttu-id="48268-2335">身分證</span><span class="sxs-lookup"><span data-stu-id="48268-2335">身分證</span></span>
- <span data-ttu-id="48268-2336">身分証</span><span class="sxs-lookup"><span data-stu-id="48268-2336">身分証</span></span>
- <span data-ttu-id="48268-2337">香港身份証</span><span class="sxs-lookup"><span data-stu-id="48268-2337">香港身份証</span></span>
- <span data-ttu-id="48268-2338">香港身分證</span><span class="sxs-lookup"><span data-stu-id="48268-2338">香港身分證</span></span>
- <span data-ttu-id="48268-2339">香港身分証</span><span class="sxs-lookup"><span data-stu-id="48268-2339">香港身分証</span></span>
- <span data-ttu-id="48268-2340">香港身份證</span><span class="sxs-lookup"><span data-stu-id="48268-2340">香港身份證</span></span>
- <span data-ttu-id="48268-2341">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="48268-2341">香港居民身份證</span></span>
- <span data-ttu-id="48268-2342">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="48268-2342">香港居民身份証</span></span>
- <span data-ttu-id="48268-2343">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="48268-2343">香港居民身分證</span></span>
- <span data-ttu-id="48268-2344">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="48268-2344">香港居民身分証</span></span>
- <span data-ttu-id="48268-2345">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="48268-2345">香港永久性居民身份証</span></span>
- <span data-ttu-id="48268-2346">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="48268-2346">香港永久性居民身分證</span></span>
- <span data-ttu-id="48268-2347">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="48268-2347">香港永久性居民身分証</span></span>
- <span data-ttu-id="48268-2348">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="48268-2348">香港永久性居民身份證</span></span>
- <span data-ttu-id="48268-2349">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="48268-2349">香港非永久性居民身份證</span></span>
- <span data-ttu-id="48268-2350">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="48268-2350">香港非永久性居民身份証</span></span>
- <span data-ttu-id="48268-2351">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="48268-2351">香港非永久性居民身分證</span></span>
- <span data-ttu-id="48268-2352">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="48268-2352">香港非永久性居民身分証</span></span>
- <span data-ttu-id="48268-2353">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="48268-2353">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="48268-2354">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="48268-2354">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="48268-2355">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="48268-2355">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="48268-2356">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="48268-2356">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="48268-2357">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="48268-2357">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="48268-2358">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="48268-2358">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="48268-2359">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="48268-2359">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="48268-2360">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="48268-2360">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="48268-2361">Indien – Permanente Kontonummer</span><span class="sxs-lookup"><span data-stu-id="48268-2361">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="48268-2362">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2362">Format</span></span>

<span data-ttu-id="48268-2363">10 Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2363">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2364">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2364">Pattern</span></span>

<span data-ttu-id="48268-2365">10 Buchstaben oder Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-2365">10 letters or digits:</span></span>
- <span data-ttu-id="48268-2366">Fünf Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="48268-2366">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="48268-2367">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2367">Four digits</span></span> 
- <span data-ttu-id="48268-2368">Ein Buchstabe, der eine alphabetische Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="48268-2368">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2369">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2369">Checksum</span></span>

<span data-ttu-id="48268-2370">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2370">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2371">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2371">Definition</span></span>

<span data-ttu-id="48268-2372">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2372">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2373">Der reguläre Ausdruck Regex_india_permanent_account_number findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2373">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2374">Ein Schlüsselwort aus Keyword_india_permanent_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2374">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="48268-2375">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2375">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2376">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2376">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="48268-2377">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="48268-2377">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="48268-2378">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-2378">Permanent Account Number</span></span> 
- <span data-ttu-id="48268-2379">Schwenken</span><span class="sxs-lookup"><span data-stu-id="48268-2379">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="48268-2380">Indien - Eindeutige Identifikationsnummer (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="48268-2380">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2381">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2381">Format</span></span>

<span data-ttu-id="48268-2382">12 Ziffern mit optionalen Leerzeichen oder Bindestrichen</span><span class="sxs-lookup"><span data-stu-id="48268-2382">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2383">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2383">Pattern</span></span>

<span data-ttu-id="48268-2384">12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-2384">12 digits:</span></span>
- <span data-ttu-id="48268-2385">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2385">Four digits</span></span> 
- <span data-ttu-id="48268-2386">Eine optionales Leerzeichen oder ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-2386">An optional space or dash</span></span> 
- <span data-ttu-id="48268-2387">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2387">Four digits</span></span> 
- <span data-ttu-id="48268-2388">Eine optionales Leerzeichen oder ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-2388">An optional space or dash</span></span> 
- <span data-ttu-id="48268-2389">Die letzte Ziffer, die eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="48268-2389">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2390">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2390">Checksum</span></span>

<span data-ttu-id="48268-2391">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2391">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2392">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2392">Definition</span></span>

<span data-ttu-id="48268-2393">Eine DLP-Richtlinie ist 85% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_india_aadhaar findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2393">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="48268-2394">Ein Schlüsselwort aus Keyword_india_aadhar wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2394">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="48268-2395">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2395">The checksum passes.</span></span>
<span data-ttu-id="48268-2396">Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_india_aadhaar findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="48268-2397">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2397">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="48268-2398">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2398">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="48268-2399">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="48268-2399">Keyword_india_aadhar</span></span>
- <span data-ttu-id="48268-2400">Aadhar</span><span class="sxs-lookup"><span data-stu-id="48268-2400">Aadhar</span></span>
- <span data-ttu-id="48268-2401">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="48268-2401">Aadhaar</span></span>
- <span data-ttu-id="48268-2402">UID</span><span class="sxs-lookup"><span data-stu-id="48268-2402">UID</span></span>
- <span data-ttu-id="48268-2403">आधार</span><span class="sxs-lookup"><span data-stu-id="48268-2403">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="48268-2404">Indonesien – Perosonalausweisnummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="48268-2404">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2405">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2405">Format</span></span>

<span data-ttu-id="48268-2406">16 Ziffern mit optionalen Punkten</span><span class="sxs-lookup"><span data-stu-id="48268-2406">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2407">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2407">Pattern</span></span>

<span data-ttu-id="48268-2408">16 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-2408">16 digits:</span></span>
- <span data-ttu-id="48268-2409">Zweistelliger Provinzcode </span><span class="sxs-lookup"><span data-stu-id="48268-2409">Two-digit province code</span></span> 
- <span data-ttu-id="48268-2410">Ein Punkt (optional) </span><span class="sxs-lookup"><span data-stu-id="48268-2410">A period (optional)</span></span> 
- <span data-ttu-id="48268-2411">Zweistelliger Regency- oder Stadtcode </span><span class="sxs-lookup"><span data-stu-id="48268-2411">Two-digit regency or city code</span></span> 
- <span data-ttu-id="48268-2412">Zweistelliger Subdistrict-Code </span><span class="sxs-lookup"><span data-stu-id="48268-2412">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="48268-2413">Ein Punkt (optional) </span><span class="sxs-lookup"><span data-stu-id="48268-2413">A period (optional)</span></span> 
- <span data-ttu-id="48268-2414">Sechs Ziffern im Format TTMMJJ, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="48268-2414">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="48268-2415">Ein Punkt (optional) </span><span class="sxs-lookup"><span data-stu-id="48268-2415">A period (optional)</span></span> 
- <span data-ttu-id="48268-2416">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2416">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2417">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2417">Checksum</span></span>

<span data-ttu-id="48268-2418">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2419">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2419">Definition</span></span>

<span data-ttu-id="48268-2420">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2421">Der reguläre Ausdruck Regex_indonesia_id_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2421">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2422">Ein Schlüsselwort aus Keyword_indonesia_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2422">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="48268-2423">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2423">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2424">Der reguläre Ausdruck Regex_indonesia_id_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2424">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2425">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2425">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="48268-2426">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="48268-2426">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="48268-2427">KTP</span><span class="sxs-lookup"><span data-stu-id="48268-2427">KTP</span></span>
- <span data-ttu-id="48268-2428">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="48268-2428">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="48268-2429">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="48268-2429">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="48268-2430">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="48268-2430">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="48268-2431">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2431">Format</span></span>

<span data-ttu-id="48268-2432">Landesvorwahl (zwei Buchstaben) plus Prüfziffern (zwei Ziffern) plus BBAN-Nummer (bis zu 30 Zeichen)</span><span class="sxs-lookup"><span data-stu-id="48268-2432">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2433">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2433">Pattern</span></span>

<span data-ttu-id="48268-2434">Das Muster muss Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="48268-2434">Pattern must include all of the following:</span></span>

- <span data-ttu-id="48268-2435">Landesvorwahl mit zwei Buchstaben</span><span class="sxs-lookup"><span data-stu-id="48268-2435">Two-letter country code</span></span>
- <span data-ttu-id="48268-2436">Zwei Prüfziffern (gefolgt von einem optionalen Leerzeichen)</span><span class="sxs-lookup"><span data-stu-id="48268-2436">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="48268-2437">1-7 Gruppen von vier Buchstaben oder Ziffern (können durch Leerzeichengetrennt werden)</span><span class="sxs-lookup"><span data-stu-id="48268-2437">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="48268-2438">1 bis 3 Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2438">1-3 letters or digits</span></span>

<span data-ttu-id="48268-2439">Das Format für jedes Land unterscheidet sich geringfügig.</span><span class="sxs-lookup"><span data-stu-id="48268-2439">The format for each country is slightly different.</span></span> <span data-ttu-id="48268-2440">Der Typ der IBAN-vertraulichen Informationen deckt diese 60 Länder ab:</span><span class="sxs-lookup"><span data-stu-id="48268-2440">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="48268-2441">AD, AE, Al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, Do, EE, es, fi, FO, Fr, GB, ge, GI, GL, GR, HR, HU, IE, IL, is, IT, kW, KZ, LB, Li, lt, LU, LV, MC, MD, me, MK, Mr, MT, mu, NL, No, PL, PT, RO, RS, Sa, SE, Si, SK, SM, TN, TR, VG</span><span class="sxs-lookup"><span data-stu-id="48268-2441">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2442">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2442">Checksum</span></span>

<span data-ttu-id="48268-2443">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2443">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2444">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2444">Definition</span></span>

<span data-ttu-id="48268-2445">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2445">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2446">Die Funktion Func_iban findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2446">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2447">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2447">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2448">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2448">Keywords</span></span>

<span data-ttu-id="48268-2449">Keine</span><span class="sxs-lookup"><span data-stu-id="48268-2449">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="48268-2450">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="48268-2450">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="48268-2451">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2451">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="48268-2452">IPv4</span><span class="sxs-lookup"><span data-stu-id="48268-2452">IPv4:</span></span>
<span data-ttu-id="48268-2453">Komplexes Muster, das formatierte (Punkte) und unformatierte (keine Punkte) Versionen der IPv4-Adressen angibt</span><span class="sxs-lookup"><span data-stu-id="48268-2453">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="48268-2454">IPv6</span><span class="sxs-lookup"><span data-stu-id="48268-2454">IPv6:</span></span>
<span data-ttu-id="48268-2455"> Komplexes Muster, das formatierte IPv6-Nummern angibt (schließt Doppelpunkte ein)</span><span class="sxs-lookup"><span data-stu-id="48268-2455">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2456">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2456">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2457">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2457">Checksum</span></span>

<span data-ttu-id="48268-2458">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2458">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2459">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2459">Definition</span></span>

<span data-ttu-id="48268-2460">Für IPv6 ist eine DLP-Richtlinie zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2460">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2461">Der reguläre Ausdruck Regex_ipv6_address findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2461">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2462">Es wurde kein Schlüsselwort aus Keyword_ipaddress gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2462">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="48268-2463">Für IPv4 ist eine DLP-Richtlinie zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2463">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2464">Der reguläre Ausdruck Regex_ipv4_address findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2464">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2465">Ein Schlüsselwort aus Keyword_ipaddress wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2465">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="48268-2466">Für IPv6 ist eine DLP-Richtlinie zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2466">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2467">Der reguläre Ausdruck Regex_ipv6_address findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2467">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2468">Es wurde kein Schlüsselwort aus Keyword_ipaddress gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2468">No keyword from Keyword_ipaddress is found.</span></span>

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2469">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2469">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="48268-2470">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="48268-2470">Keyword_ipaddress</span></span>

- <span data-ttu-id="48268-2471">IP (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung unterschieden)</span><span class="sxs-lookup"><span data-stu-id="48268-2471">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="48268-2472">ip address</span><span class="sxs-lookup"><span data-stu-id="48268-2472">ip address</span></span> 
- <span data-ttu-id="48268-2473">IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="48268-2473">ip addresses</span></span>
- <span data-ttu-id="48268-2474">internet protocol</span><span class="sxs-lookup"><span data-stu-id="48268-2474">internet protocol</span></span>
- <span data-ttu-id="48268-2475">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="48268-2475">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="48268-2476">Internationale Klassifikation von Krankheiten (ICD-10-cm)</span><span class="sxs-lookup"><span data-stu-id="48268-2476">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="48268-2477">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2477">Format</span></span>

<span data-ttu-id="48268-2478">Wörterbuch</span><span class="sxs-lookup"><span data-stu-id="48268-2478">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2479">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2479">Pattern</span></span>

<span data-ttu-id="48268-2480">Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="48268-2480">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2481">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2481">Checksum</span></span>

<span data-ttu-id="48268-2482">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2482">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2483">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2483">Definition</span></span>

<span data-ttu-id="48268-2484">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2485">Ein Schlüsselwort aus Dictionary_icd_10_updated wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2485">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="48268-2486">Ein Schlüsselwort aus Dictionary_icd_10_codes wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2486">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="48268-2487">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2487">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2488">Ein Schlüsselwort aus Dictionary_icd_10_ aktualisiert wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2488">A keyword from Dictionary_icd_10_ updated is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

<span data-ttu-id="48268-2489">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2489">Keywords</span></span>

<span data-ttu-id="48268-2490">Ein beliebiger Ausdruck aus dem Dictionary_icd_10_updated Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, zehnte Revision, klinische Änderung (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="48268-2490">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="48268-2491">Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungs Codes.</span><span class="sxs-lookup"><span data-stu-id="48268-2491">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="48268-2492">Ein beliebiger Ausdruck aus dem Dictionary_icd_10_codes Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, zehnte Revision, klinische Änderung (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="48268-2492">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="48268-2493">Dieser Typ sucht nur nach Versicherungs Codes, nicht nach der Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="48268-2493">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="48268-2494">Internationale Klassifikation von Krankheiten (ICD-9-cm)</span><span class="sxs-lookup"><span data-stu-id="48268-2494">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="48268-2495">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2495">Format</span></span>

<span data-ttu-id="48268-2496">Wörterbuch</span><span class="sxs-lookup"><span data-stu-id="48268-2496">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2497">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2497">Pattern</span></span>

<span data-ttu-id="48268-2498">Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="48268-2498">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2499">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2499">Checksum</span></span>

<span data-ttu-id="48268-2500">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2500">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2501">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2501">Definition</span></span>

<span data-ttu-id="48268-2502">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2502">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2503">Ein Schlüsselwort aus Dictionary_icd_9_updated wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2503">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="48268-2504">Ein Schlüsselwort aus Dictionary_icd_9_codes wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2504">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="48268-2505">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2505">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2506">Ein Schlüsselwort aus Dictionary_icd_9_updated wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2506">A keyword from Dictionary_icd_9_updated is found.</span></span>

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2507">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2507">Keywords</span></span>

<span data-ttu-id="48268-2508">Ein beliebiger Ausdruck aus dem Dictionary_icd_9_updated Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, neunte Revision, klinische Änderung (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="48268-2508">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="48268-2509">Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungs Codes.</span><span class="sxs-lookup"><span data-stu-id="48268-2509">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="48268-2510">Ein beliebiger Ausdruck aus dem Dictionary_icd_9_codes Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, neunte Revision, klinische Änderung (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="48268-2510">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="48268-2511">Dieser Typ sucht nur nach Versicherungs Codes, nicht nach der Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="48268-2511">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="48268-2512">Irland – Personal Public Service-Nummer (PPS)</span><span class="sxs-lookup"><span data-stu-id="48268-2512">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2513">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2513">Format</span></span>

<span data-ttu-id="48268-2514">Altes Format (bis 31. Dez. 2012):</span><span class="sxs-lookup"><span data-stu-id="48268-2514">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="48268-2515">Sieben Ziffern, gefolgt von 1-2 Buchstaben </span><span class="sxs-lookup"><span data-stu-id="48268-2515">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="48268-2516">Neues Format (1 Jan 2013 und danach):</span><span class="sxs-lookup"><span data-stu-id="48268-2516">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="48268-2517">Sieben Ziffern, gefolgt von zwei Buchstaben</span><span class="sxs-lookup"><span data-stu-id="48268-2517">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2518">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2518">Pattern</span></span>

<span data-ttu-id="48268-2519">Altes Format (bis 31. Dez. 2012):</span><span class="sxs-lookup"><span data-stu-id="48268-2519">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="48268-2520">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="48268-2520">Seven digits</span></span> 
- <span data-ttu-id="48268-2521">1-2 Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="48268-2521">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="48268-2522">Neues Format (1 Jan 2013 und danach):</span><span class="sxs-lookup"><span data-stu-id="48268-2522">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="48268-2523">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="48268-2523">Seven digits</span></span> 
- <span data-ttu-id="48268-2524">Ein Buchstabe (Groß-/Kleinschreibung irrelevant), wobei es sich um eine alphabetische Prüfziffer handelt </span><span class="sxs-lookup"><span data-stu-id="48268-2524">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="48268-2525">Die Buchstaben "A" oder "H" (Groß-/Kleinschreibung irrelevant)</span><span class="sxs-lookup"><span data-stu-id="48268-2525">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2526">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2526">Checksum</span></span>

<span data-ttu-id="48268-2527">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2527">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2528">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2528">Definition</span></span>

<span data-ttu-id="48268-2529">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2530">Die Funktion Func_ireland_pps sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2530">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2531">Eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="48268-2531">One of the following is true:</span></span>
    - <span data-ttu-id="48268-2532">Ein Schlüsselwort aus Keyword_ireland_pps wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2532">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="48268-2533">Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="48268-2533">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="48268-2534">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2534">The checksum passes.</span></span>

<span data-ttu-id="48268-2535">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2535">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2536">Die Funktion Func_ireland_pps sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2536">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2537">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2537">The checksum passes.</span></span>

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2538">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2538">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="48268-2539">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="48268-2539">Keyword_ireland_pps</span></span>

- <span data-ttu-id="48268-2540">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="48268-2540">Personal Public Service Number</span></span> 
- <span data-ttu-id="48268-2541">PPS Number</span><span class="sxs-lookup"><span data-stu-id="48268-2541">PPS Number</span></span> 
- <span data-ttu-id="48268-2542">PPS Num</span><span class="sxs-lookup"><span data-stu-id="48268-2542">PPS Num</span></span> 
- <span data-ttu-id="48268-2543">PPS No.</span><span class="sxs-lookup"><span data-stu-id="48268-2543">PPS No.</span></span> 
- <span data-ttu-id="48268-2544">PPS #</span><span class="sxs-lookup"><span data-stu-id="48268-2544">PPS #</span></span> 
- <span data-ttu-id="48268-2545">PPS #</span><span class="sxs-lookup"><span data-stu-id="48268-2545">PPS#</span></span> 
- <span data-ttu-id="48268-2546">PPSN</span><span class="sxs-lookup"><span data-stu-id="48268-2546">PPSN</span></span> 
- <span data-ttu-id="48268-2547">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="48268-2547">Public Services Card</span></span> 
- <span data-ttu-id="48268-2548">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="48268-2548">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="48268-2549">Uimh.</span><span class="sxs-lookup"><span data-stu-id="48268-2549">Uimh.</span></span> <span data-ttu-id="48268-2550">PSP</span><span class="sxs-lookup"><span data-stu-id="48268-2550">PSP</span></span> 
- <span data-ttu-id="48268-2551">PSP</span><span class="sxs-lookup"><span data-stu-id="48268-2551">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="48268-2552">Israelische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="48268-2552">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2553">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2553">Format</span></span>

<span data-ttu-id="48268-2554">13 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2554">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2555">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2555">Pattern</span></span>

<span data-ttu-id="48268-2556">Formatiert</span><span class="sxs-lookup"><span data-stu-id="48268-2556">Formatted:</span></span>
- <span data-ttu-id="48268-2557">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2557">Two digits</span></span> 
- <span data-ttu-id="48268-2558">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-2558">A dash</span></span> 
- <span data-ttu-id="48268-2559">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2559">Three digits</span></span> 
- <span data-ttu-id="48268-2560">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-2560">A dash</span></span> 
- <span data-ttu-id="48268-2561">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2561">Eight digits</span></span>

<span data-ttu-id="48268-2562">Unformatiert</span><span class="sxs-lookup"><span data-stu-id="48268-2562">Unformatted:</span></span>
- <span data-ttu-id="48268-2563">	13 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2563">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2564">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2564">Checksum</span></span>

<span data-ttu-id="48268-2565">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2565">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2566">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2566">Definition</span></span>

<span data-ttu-id="48268-2567">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2568">Der reguläre Ausdruck Regex_israel_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2568">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2569">Ein Schlüsselwort aus Keyword_israel_bank_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2569">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2570">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2570">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="48268-2571">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="48268-2571">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="48268-2572">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-2572">Bank Account Number</span></span> 
- <span data-ttu-id="48268-2573">Bank Account</span><span class="sxs-lookup"><span data-stu-id="48268-2573">Bank Account</span></span> 
- <span data-ttu-id="48268-2574">Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-2574">Account Number</span></span> 
- <span data-ttu-id="48268-2575">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="48268-2575">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="48268-2576">Israelische Ausweis-ID</span><span class="sxs-lookup"><span data-stu-id="48268-2576">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="48268-2577">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2577">Format</span></span>

<span data-ttu-id="48268-2578">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2578">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2579">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2579">Pattern</span></span>

<span data-ttu-id="48268-2580">Neun aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2580">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2581">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2581">Checksum</span></span>

<span data-ttu-id="48268-2582">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2582">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2583">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2583">Definition</span></span>

<span data-ttu-id="48268-2584">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2585">Die Funktion Func_israeli_national_id_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2585">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2586">Ein Schlüsselwort aus Keyword_Israel_National_ID wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2586">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="48268-2587">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2587">The checksum passes.</span></span>

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2588">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2588">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="48268-2589">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="48268-2589">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="48268-2590">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="48268-2590">מספר זהות</span></span> 
- <span data-ttu-id="48268-2591">National ID Number</span><span class="sxs-lookup"><span data-stu-id="48268-2591">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="48268-2592">Italienische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2592">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2593">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2593">Format</span></span>

<span data-ttu-id="48268-2594">Eine Kombination von 10 Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2594">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2595">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2595">Pattern</span></span>

- <span data-ttu-id="48268-2596">Eine Kombination aus 10 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-2596">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="48268-2597">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="48268-2597">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="48268-2598">Der Buchstabe „A“ oder „W“ (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="48268-2598">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="48268-2599">Sieben Buchstaben (ohne Beachtung der Groß-/Kleinschreibung), Ziffern oder der Unterstrich</span><span class="sxs-lookup"><span data-stu-id="48268-2599">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="48268-2600">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="48268-2600">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2601">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2601">Checksum</span></span>

<span data-ttu-id="48268-2602">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2602">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2603">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2603">Definition</span></span>

<span data-ttu-id="48268-2604">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2604">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2605">Der reguläre Ausdruck Regex_italy_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2605">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2606">Ein Schlüsselwort aus Keyword_italy_drivers_license_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2606">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2607">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2607">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="48268-2608">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="48268-2608">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="48268-2609">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="48268-2609">numero di patente di guida</span></span> 
- <span data-ttu-id="48268-2610">patente di guida</span><span class="sxs-lookup"><span data-stu-id="48268-2610">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="48268-2611">Japanische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="48268-2611">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2612">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2612">Format</span></span>

<span data-ttu-id="48268-2613">Sieben oder acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2613">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2614">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2614">Pattern</span></span>

<span data-ttu-id="48268-2615">Bankkontonummer:</span><span class="sxs-lookup"><span data-stu-id="48268-2615">Bank account number:</span></span>
- <span data-ttu-id="48268-2616">Sieben oder acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2616">Seven or eight digits</span></span>
- <span data-ttu-id="48268-2617">Niederlassungscode der Bank:</span><span class="sxs-lookup"><span data-stu-id="48268-2617">Bank account branch code:</span></span>
- <span data-ttu-id="48268-2618">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2618">Four digits</span></span> 
- <span data-ttu-id="48268-2619">Ein Leerzeichen oder ein Bindestrich (optional)</span><span class="sxs-lookup"><span data-stu-id="48268-2619">A space or dash (optional)</span></span> 
- <span data-ttu-id="48268-2620">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2620">Three digits</span></span>

<span data-ttu-id="48268-2621">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2621">Checksum</span></span>

<span data-ttu-id="48268-2622">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2622">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2623">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2623">Definition</span></span>

<span data-ttu-id="48268-2624">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2625">Die Funktion Func_jp_bank_account findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2625">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2626">Ein Schlüsselwort aus Keyword_jp_bank_account wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2626">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="48268-2627">Eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="48268-2627">One of the following is true:</span></span>
- <span data-ttu-id="48268-2628">Die Funktion Func_jp_bank_account_branch_code findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2628">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2629">Ein Schlüsselwort aus Keyword_jp_bank_branch_code wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2629">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="48268-2630">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2631">Die Funktion Func_jp_bank_account findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2631">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2632">Ein Schlüsselwort aus Keyword_jp_bank_account wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2632">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2633">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2633">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="48268-2634">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="48268-2634">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="48268-2635">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-2635">Checking Account Number</span></span> 
- <span data-ttu-id="48268-2636">Checking Account</span><span class="sxs-lookup"><span data-stu-id="48268-2636">Checking Account</span></span> 
- <span data-ttu-id="48268-2637">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="48268-2637">Checking Account #</span></span> 
- <span data-ttu-id="48268-2638">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="48268-2638">Checking Acct Number</span></span> 
- <span data-ttu-id="48268-2639">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="48268-2639">Checking Acct #</span></span> 
- <span data-ttu-id="48268-2640">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="48268-2640">Checking Acct No.</span></span> 
- <span data-ttu-id="48268-2641">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="48268-2641">Checking Account No.</span></span> 
- <span data-ttu-id="48268-2642">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-2642">Bank Account Number</span></span> 
- <span data-ttu-id="48268-2643">Bank Account</span><span class="sxs-lookup"><span data-stu-id="48268-2643">Bank Account</span></span> 
- <span data-ttu-id="48268-2644">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="48268-2644">Bank Account #</span></span> 
- <span data-ttu-id="48268-2645">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="48268-2645">Bank Acct Number</span></span> 
- <span data-ttu-id="48268-2646">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="48268-2646">Bank Acct #</span></span> 
- <span data-ttu-id="48268-2647">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="48268-2647">Bank Acct No.</span></span> 
- <span data-ttu-id="48268-2648">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="48268-2648">Bank Account No.</span></span> 
- <span data-ttu-id="48268-2649">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-2649">Savings Account Number</span></span> 
- <span data-ttu-id="48268-2650">Savings Account</span><span class="sxs-lookup"><span data-stu-id="48268-2650">Savings Account</span></span> 
- <span data-ttu-id="48268-2651">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="48268-2651">Savings Account #</span></span> 
- <span data-ttu-id="48268-2652">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="48268-2652">Savings Acct Number</span></span> 
- <span data-ttu-id="48268-2653">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="48268-2653">Savings Acct #</span></span> 
- <span data-ttu-id="48268-2654">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="48268-2654">Savings Acct No.</span></span> 
- <span data-ttu-id="48268-2655">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="48268-2655">Savings Account No.</span></span> 
- <span data-ttu-id="48268-2656">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-2656">Debit Account Number</span></span> 
- <span data-ttu-id="48268-2657">Debit Account</span><span class="sxs-lookup"><span data-stu-id="48268-2657">Debit Account</span></span> 
- <span data-ttu-id="48268-2658">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="48268-2658">Debit Account #</span></span> 
- <span data-ttu-id="48268-2659">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="48268-2659">Debit Acct Number</span></span> 
- <span data-ttu-id="48268-2660">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="48268-2660">Debit Acct #</span></span> 
- <span data-ttu-id="48268-2661">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="48268-2661">Debit Acct No.</span></span> 
- <span data-ttu-id="48268-2662">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="48268-2662">Debit Account No.</span></span> 
- <span data-ttu-id="48268-2663">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="48268-2663">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="48268-2664">#アカウントの確認, 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="48268-2664">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="48268-2665">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="48268-2665">＃勘定の確認</span></span> 
- <span data-ttu-id="48268-2666">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="48268-2666">勘定番号の確認</span></span> 
- <span data-ttu-id="48268-2667">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="48268-2667">口座番号の確認</span></span> 
- <span data-ttu-id="48268-2668">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="48268-2668">銀行口座番号</span></span> 
- <span data-ttu-id="48268-2669">銀行口座</span><span class="sxs-lookup"><span data-stu-id="48268-2669">銀行口座</span></span> 
- <span data-ttu-id="48268-2670">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="48268-2670">銀行口座＃</span></span> 
- <span data-ttu-id="48268-2671">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="48268-2671">銀行の勘定番号</span></span> 
- <span data-ttu-id="48268-2672">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="48268-2672">銀行のacct＃</span></span> 
- <span data-ttu-id="48268-2673">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="48268-2673">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="48268-2674">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="48268-2674">銀行口座番号</span></span>
- <span data-ttu-id="48268-2675">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="48268-2675">普通預金口座番号</span></span> 
- <span data-ttu-id="48268-2676">預金口座</span><span class="sxs-lookup"><span data-stu-id="48268-2676">預金口座</span></span> 
- <span data-ttu-id="48268-2677">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="48268-2677">貯蓄口座＃</span></span> 
- <span data-ttu-id="48268-2678">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="48268-2678">貯蓄勘定の数</span></span> 
- <span data-ttu-id="48268-2679">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="48268-2679">貯蓄勘定＃</span></span> 
- <span data-ttu-id="48268-2680">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="48268-2680">貯蓄勘定番号</span></span> 
- <span data-ttu-id="48268-2681">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="48268-2681">普通預金口座番号</span></span> 
- <span data-ttu-id="48268-2682">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="48268-2682">引き落とし口座番号</span></span> 
- <span data-ttu-id="48268-2683">口座番号</span><span class="sxs-lookup"><span data-stu-id="48268-2683">口座番号</span></span> 
- <span data-ttu-id="48268-2684">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="48268-2684">口座番号＃</span></span> 
- <span data-ttu-id="48268-2685">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="48268-2685">デビットのacct番号</span></span> 
- <span data-ttu-id="48268-2686">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="48268-2686">デビット勘定＃</span></span> 
- <span data-ttu-id="48268-2687">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="48268-2687">デビットACCTの番号</span></span> 
- <span data-ttu-id="48268-2688">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="48268-2688">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="48268-2689">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="48268-2689">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="48268-2690">Otemachi</span><span class="sxs-lookup"><span data-stu-id="48268-2690">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="48268-2691">Japanische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2691">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2692">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2692">Format</span></span>

<span data-ttu-id="48268-2693">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2693">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2694">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2694">Pattern</span></span>

<span data-ttu-id="48268-2695">12 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2695">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2696">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2696">Checksum</span></span>

<span data-ttu-id="48268-2697">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2697">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2698">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2698">Definition</span></span>

<span data-ttu-id="48268-2699">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2699">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2700">Die Funktion Func_jp_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2700">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2701">Ein Schlüsselwort aus Keyword_jp_drivers_license_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2701">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2702">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2702">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="48268-2703">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="48268-2703">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="48268-2704">DL #</span><span class="sxs-lookup"><span data-stu-id="48268-2704">dl#</span></span> 
- <span data-ttu-id="48268-2705">DL</span><span class="sxs-lookup"><span data-stu-id="48268-2705">DL＃</span></span> 
- <span data-ttu-id="48268-2706">DLS #</span><span class="sxs-lookup"><span data-stu-id="48268-2706">dls#</span></span> 
- <span data-ttu-id="48268-2707">DLS</span><span class="sxs-lookup"><span data-stu-id="48268-2707">DLS＃</span></span> 
- <span data-ttu-id="48268-2708">driver license</span><span class="sxs-lookup"><span data-stu-id="48268-2708">driver license</span></span> 
- <span data-ttu-id="48268-2709">driver licenses</span><span class="sxs-lookup"><span data-stu-id="48268-2709">driver licenses</span></span> 
- <span data-ttu-id="48268-2710">drivers license</span><span class="sxs-lookup"><span data-stu-id="48268-2710">drivers license</span></span> 
- <span data-ttu-id="48268-2711">driver's license</span><span class="sxs-lookup"><span data-stu-id="48268-2711">driver's license</span></span> 
- <span data-ttu-id="48268-2712">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="48268-2712">drivers licenses</span></span> 
- <span data-ttu-id="48268-2713">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="48268-2713">driver's licenses</span></span> 
- <span data-ttu-id="48268-2714">driving licence</span><span class="sxs-lookup"><span data-stu-id="48268-2714">driving licence</span></span> 
- <span data-ttu-id="48268-2715">lic #</span><span class="sxs-lookup"><span data-stu-id="48268-2715">lic#</span></span> 
- <span data-ttu-id="48268-2716">LIC</span><span class="sxs-lookup"><span data-stu-id="48268-2716">LIC＃</span></span> 
- <span data-ttu-id="48268-2717">LiCS #</span><span class="sxs-lookup"><span data-stu-id="48268-2717">lics#</span></span> 
- <span data-ttu-id="48268-2718">state id</span><span class="sxs-lookup"><span data-stu-id="48268-2718">state id</span></span> 
- <span data-ttu-id="48268-2719">state identification</span><span class="sxs-lookup"><span data-stu-id="48268-2719">state identification</span></span> 
- <span data-ttu-id="48268-2720">state identification number</span><span class="sxs-lookup"><span data-stu-id="48268-2720">state identification number</span></span> 
- <span data-ttu-id="48268-2721">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="48268-2721">低所得国＃</span></span> 
- <span data-ttu-id="48268-2722">免許証</span><span class="sxs-lookup"><span data-stu-id="48268-2722">免許証</span></span> 
- <span data-ttu-id="48268-2723">状態ID</span><span class="sxs-lookup"><span data-stu-id="48268-2723">状態ID</span></span>
- <span data-ttu-id="48268-2724">状態の識別</span><span class="sxs-lookup"><span data-stu-id="48268-2724">状態の識別</span></span> 
- <span data-ttu-id="48268-2725">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="48268-2725">状態の識別番号</span></span> 
- <span data-ttu-id="48268-2726">運転免許</span><span class="sxs-lookup"><span data-stu-id="48268-2726">運転免許</span></span> 
- <span data-ttu-id="48268-2727">運転免許証</span><span class="sxs-lookup"><span data-stu-id="48268-2727">運転免許証</span></span> 
- <span data-ttu-id="48268-2728">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="48268-2728">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="48268-2729">Japanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2729">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2730">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2730">Format</span></span>

<span data-ttu-id="48268-2731">Zwei Buchstaben gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2731">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2732">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2732">Pattern</span></span>

<span data-ttu-id="48268-2733">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2733">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2734">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2734">Checksum</span></span>

<span data-ttu-id="48268-2735">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2736">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2736">Definition</span></span>

<span data-ttu-id="48268-2737">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2738">Die Funktion Func_jp_passport findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2738">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2739">Ein Schlüsselwort aus Keyword_jp_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2739">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2740">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2740">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="48268-2741">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="48268-2741">Keyword_jp_passport</span></span>

- <span data-ttu-id="48268-2742">パスポート</span><span class="sxs-lookup"><span data-stu-id="48268-2742">パスポート</span></span> 
- <span data-ttu-id="48268-2743">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="48268-2743">パスポート番号</span></span> 
- <span data-ttu-id="48268-2744">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="48268-2744">パスポートのNum</span></span> 
- <span data-ttu-id="48268-2745">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="48268-2745">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="48268-2746">Japanische Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2746">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2747">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2747">Format</span></span>

<span data-ttu-id="48268-2748">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2748">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2749">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2749">Pattern</span></span>

<span data-ttu-id="48268-2750">11 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2750">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2751">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2751">Checksum</span></span>

<span data-ttu-id="48268-2752">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2752">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2753">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2753">Definition</span></span>

<span data-ttu-id="48268-2754">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2755">Die Funktion Func_jp_resident_registration_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2755">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2756">Ein Schlüsselwort aus Keyword_jp_resident_registration_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2756">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2757">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2757">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="48268-2758">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="48268-2758">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="48268-2759">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="48268-2759">Resident Registration Number</span></span>
- <span data-ttu-id="48268-2760">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="48268-2760">Resident Register Number</span></span> 
- <span data-ttu-id="48268-2761">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="48268-2761">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="48268-2762">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="48268-2762">Resident Registration No.</span></span> 
- <span data-ttu-id="48268-2763">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="48268-2763">Resident Register No.</span></span> 
- <span data-ttu-id="48268-2764">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="48268-2764">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="48268-2765">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="48268-2765">Basic Resident Register No.</span></span> 
- <span data-ttu-id="48268-2766">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="48268-2766">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="48268-2767">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="48268-2767">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="48268-2768">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="48268-2768">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="48268-2769">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="48268-2769">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="48268-2770">Japanische Sozialversicherungsnummer (SIN)</span><span class="sxs-lookup"><span data-stu-id="48268-2770">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="48268-2771">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2771">Format</span></span>

<span data-ttu-id="48268-2772">7-12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2772">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2773">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2773">Pattern</span></span>

<span data-ttu-id="48268-2774">7 bis 12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-2774">7-12 digits:</span></span>
- <span data-ttu-id="48268-2775">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2775">Four digits</span></span> 
- <span data-ttu-id="48268-2776">Ein Bindestrich (optional)</span><span class="sxs-lookup"><span data-stu-id="48268-2776">A hyphen (optional)</span></span> 
- <span data-ttu-id="48268-2777">Sechs Ziffern oder</span><span class="sxs-lookup"><span data-stu-id="48268-2777">Six digits OR</span></span>
- <span data-ttu-id="48268-2778">7-12 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2778">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2779">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2779">Checksum</span></span>

<span data-ttu-id="48268-2780">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2780">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2781">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2781">Definition</span></span>

<span data-ttu-id="48268-2782">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2782">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2783">Die Funktion Func_jp_sin findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2783">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2784">Ein Schlüsselwort aus Keyword_jp_sin wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2784">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="48268-2785">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2785">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2786">Die Funktion Func_jp_sin_pre_1997 findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2786">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2787">Ein Schlüsselwort aus Keyword_jp_sin wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2787">A keyword from Keyword_jp_sin is found.</span></span>

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2788">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2788">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="48268-2789">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="48268-2789">Keyword_jp_sin</span></span>

- <span data-ttu-id="48268-2790">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="48268-2790">Social Insurance No.</span></span> 
- <span data-ttu-id="48268-2791">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="48268-2791">Social Insurance Num</span></span> 
- <span data-ttu-id="48268-2792">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="48268-2792">Social Insurance Number</span></span> 
- <span data-ttu-id="48268-2793">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="48268-2793">社会保険のテンキー</span></span> 
- <span data-ttu-id="48268-2794">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="48268-2794">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="48268-2795">Japanische Residenz Kartennummer</span><span class="sxs-lookup"><span data-stu-id="48268-2795">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2796">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2796">Format</span></span>

<span data-ttu-id="48268-2797">12 Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2797">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2798">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2798">Pattern</span></span>

<span data-ttu-id="48268-2799">12 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-2799">12 letters and digits:</span></span>
- <span data-ttu-id="48268-2800">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="48268-2800">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="48268-2801">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2801">Eight digits</span></span> 
- <span data-ttu-id="48268-2802">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="48268-2802">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2803">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2803">Checksum</span></span>

<span data-ttu-id="48268-2804">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2804">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2805">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2805">Definition</span></span>

<span data-ttu-id="48268-2806">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2807">Der reguläre Ausdruck Regex_jp_residence_card_number findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2807">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2808">Ein Schlüsselwort aus Keyword_jp_residence_card_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2808">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2809">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2809">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="48268-2810">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="48268-2810">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="48268-2811">Wohnsitz Kartennummer</span><span class="sxs-lookup"><span data-stu-id="48268-2811">Residence card number</span></span>
- <span data-ttu-id="48268-2812">Residenzkarte Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2812">Residence card no</span></span>
- <span data-ttu-id="48268-2813">Aufenthaltskarte #</span><span class="sxs-lookup"><span data-stu-id="48268-2813">Residence card #</span></span>
- <span data-ttu-id="48268-2814">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="48268-2814">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="48268-2815">Malaysia -ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="48268-2815">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2816">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2816">Format</span></span>

<span data-ttu-id="48268-2817">12 Ziffern mit optionalen Bindestrichen</span><span class="sxs-lookup"><span data-stu-id="48268-2817">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2818">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2818">Pattern</span></span>

<span data-ttu-id="48268-2819">12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-2819">12 digits:</span></span>
- <span data-ttu-id="48268-2820">Sechs Ziffern im Format JJMMTT, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="48268-2820">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="48268-2821">Ein Bindestrich (optional) </span><span class="sxs-lookup"><span data-stu-id="48268-2821">A dash (optional)</span></span> 
- <span data-ttu-id="48268-2822">Zwei Buchstaben als Code für den Geburtsort </span><span class="sxs-lookup"><span data-stu-id="48268-2822">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="48268-2823">Ein Bindestrich (optional) </span><span class="sxs-lookup"><span data-stu-id="48268-2823">A dash (optional)</span></span> 
- <span data-ttu-id="48268-2824">Drei beliebige Ziffern </span><span class="sxs-lookup"><span data-stu-id="48268-2824">Three random digits</span></span> 
- <span data-ttu-id="48268-2825">Einstelliger Code für das Geschlecht</span><span class="sxs-lookup"><span data-stu-id="48268-2825">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2826">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2826">Checksum</span></span>

<span data-ttu-id="48268-2827">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2827">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2828">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2828">Definition</span></span>

<span data-ttu-id="48268-2829">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2829">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2830">Der reguläre Ausdruck Regex_malaysia_id_card_number findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2830">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2831">Ein Schlüsselwort aus Keyword_malaysia_id_card_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2831">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2832">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2832">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="48268-2833">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="48268-2833">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="48268-2834">digitale Anwendungs Karte</span><span class="sxs-lookup"><span data-stu-id="48268-2834">digital application card</span></span>
- <span data-ttu-id="48268-2835">i/c</span><span class="sxs-lookup"><span data-stu-id="48268-2835">i/c</span></span>
- <span data-ttu-id="48268-2836">i/c Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2836">i/c no</span></span>
- <span data-ttu-id="48268-2837">IK</span><span class="sxs-lookup"><span data-stu-id="48268-2837">ic</span></span>
- <span data-ttu-id="48268-2838">IC Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2838">ic no</span></span>
- <span data-ttu-id="48268-2839">id card</span><span class="sxs-lookup"><span data-stu-id="48268-2839">id card</span></span>
- <span data-ttu-id="48268-2840">Ausweis</span><span class="sxs-lookup"><span data-stu-id="48268-2840">identification Card</span></span>
- <span data-ttu-id="48268-2841">identity card</span><span class="sxs-lookup"><span data-stu-id="48268-2841">identity card</span></span>
- <span data-ttu-id="48268-2842">k/p</span><span class="sxs-lookup"><span data-stu-id="48268-2842">k/p</span></span>
- <span data-ttu-id="48268-2843">k/p Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2843">k/p no</span></span>
- <span data-ttu-id="48268-2844">Kad akuan Diri</span><span class="sxs-lookup"><span data-stu-id="48268-2844">kad akuan diri</span></span>
- <span data-ttu-id="48268-2845">Kad aplikasi Digital</span><span class="sxs-lookup"><span data-stu-id="48268-2845">kad aplikasi digital</span></span>
- <span data-ttu-id="48268-2846">Kad Einführung in Malaysia</span><span class="sxs-lookup"><span data-stu-id="48268-2846">kad pengenalan malaysia</span></span>
- <span data-ttu-id="48268-2847">KP</span><span class="sxs-lookup"><span data-stu-id="48268-2847">kp</span></span>
- <span data-ttu-id="48268-2848">KP Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2848">kp no</span></span>
- <span data-ttu-id="48268-2849">MyKAD</span><span class="sxs-lookup"><span data-stu-id="48268-2849">mykad</span></span>
- <span data-ttu-id="48268-2850">mykas</span><span class="sxs-lookup"><span data-stu-id="48268-2850">mykas</span></span>
- <span data-ttu-id="48268-2851">mykid</span><span class="sxs-lookup"><span data-stu-id="48268-2851">mykid</span></span>
- <span data-ttu-id="48268-2852">mypr</span><span class="sxs-lookup"><span data-stu-id="48268-2852">mypr</span></span>
- <span data-ttu-id="48268-2853">mytentera</span><span class="sxs-lookup"><span data-stu-id="48268-2853">mytentera</span></span>
- <span data-ttu-id="48268-2854">Malaysia-Personalausweis</span><span class="sxs-lookup"><span data-stu-id="48268-2854">malaysia identity card</span></span>
- <span data-ttu-id="48268-2855">malaysischer Personalausweis</span><span class="sxs-lookup"><span data-stu-id="48268-2855">malaysian identity card</span></span>
- <span data-ttu-id="48268-2856">NRIC</span><span class="sxs-lookup"><span data-stu-id="48268-2856">nric</span></span>
- <span data-ttu-id="48268-2857">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="48268-2857">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="48268-2858">Niederlande – Bürgerdienstnummer (BSN)</span><span class="sxs-lookup"><span data-stu-id="48268-2858">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2859">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2859">Format</span></span>

<span data-ttu-id="48268-2860">8-9 Ziffern mit optionalen Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-2860">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2861">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2861">Pattern</span></span>

<span data-ttu-id="48268-2862">8-9 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-2862">8-9 digits:</span></span>
- <span data-ttu-id="48268-2863">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2863">Three digits</span></span> 
- <span data-ttu-id="48268-2864">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="48268-2864">A space (optional)</span></span> 
- <span data-ttu-id="48268-2865">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2865">Three digits</span></span> 
- <span data-ttu-id="48268-2866">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="48268-2866">A space (optional)</span></span> 
- <span data-ttu-id="48268-2867">2-3 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2867">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2868">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2868">Checksum</span></span>

<span data-ttu-id="48268-2869">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2869">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2870">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2870">Definition</span></span>

<span data-ttu-id="48268-2871">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2871">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2872">Die Funktion Func_netherlands_bsn sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2872">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2873">Ein Schlüsselwort aus Keyword_netherlands_bsn wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2873">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="48268-2874">Die Funktion Func_eu_date2 findet ein Datum im richtigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="48268-2874">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="48268-2875">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2875">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2876">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2876">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="48268-2877">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="48268-2877">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="48268-2878">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="48268-2878">Citizen service number</span></span> 
- <span data-ttu-id="48268-2879">BSN</span><span class="sxs-lookup"><span data-stu-id="48268-2879">BSN</span></span> 
- <span data-ttu-id="48268-2880">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="48268-2880">Burgerservicenummer</span></span> 
- <span data-ttu-id="48268-2881">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="48268-2881">Sofinummer</span></span> 
- <span data-ttu-id="48268-2882">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="48268-2882">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="48268-2883">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2883">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="48268-2884">Neuseeländische Gesundheitsministeriumsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2884">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2885">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2885">Format</span></span>

<span data-ttu-id="48268-2886">Drei Buchstaben, ein Leerzeichen (optional) und vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2886">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2887">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2887">Pattern</span></span>

<span data-ttu-id="48268-2888">Drei Buchstaben (Groß-/Kleinschreibung nicht beachtet) ein Leerzeichen (optional) vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2888">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2889">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2889">Checksum</span></span>

<span data-ttu-id="48268-2890">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2890">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2891">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2891">Definition</span></span>

<span data-ttu-id="48268-2892">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2892">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2893">Die Funktion Func_new_zealand_ministry_of_health_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2893">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2894">Ein Schlüsselwort aus Keyword_nz_terms wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2894">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="48268-2895">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2895">The checksum passes.</span></span>

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="48268-2896">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2896">Keywords</span></span>

<span data-ttu-id="48268-2897">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="48268-2897">Keyword_nz_terms</span></span>

- <span data-ttu-id="48268-2898">Nhi</span><span class="sxs-lookup"><span data-stu-id="48268-2898">NHI</span></span> 
- <span data-ttu-id="48268-2899">New Zealand</span><span class="sxs-lookup"><span data-stu-id="48268-2899">New Zealand</span></span> 
- <span data-ttu-id="48268-2900">Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="48268-2900">Health</span></span> 
- <span data-ttu-id="48268-2901">Behandlung</span><span class="sxs-lookup"><span data-stu-id="48268-2901">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="48268-2902">Norwegen – Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2902">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2903">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2903">Format</span></span>

<span data-ttu-id="48268-2904">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2905">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2905">Pattern</span></span>

<span data-ttu-id="48268-2906">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-2906">11 digits:</span></span>
- <span data-ttu-id="48268-2907">Sechs Ziffern im Format TTMMJJ, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="48268-2907">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="48268-2908">Dreistellige individuelle Zahl </span><span class="sxs-lookup"><span data-stu-id="48268-2908">Three-digit individual number</span></span> 
- <span data-ttu-id="48268-2909">Zwei Prüfziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2909">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2910">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2910">Checksum</span></span>

<span data-ttu-id="48268-2911">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2912">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2912">Definition</span></span>

<span data-ttu-id="48268-2913">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2913">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2914">Die Funktion Func_norway_id_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2914">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2915">Ein Schlüsselwort aus Keyword_norway_id_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2915">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="48268-2916">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2916">The checksum passes.</span></span>
- <span data-ttu-id="48268-2917">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2917">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2918">Die Funktion Func_norway_id_numbe sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2918">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2919">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2919">The checksum passes.</span></span>

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2920">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2920">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="48268-2921">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="48268-2921">Keyword_norway_id_number</span></span>

- <span data-ttu-id="48268-2922">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="48268-2922">Personal identification number</span></span>
- <span data-ttu-id="48268-2923">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="48268-2923">Norwegian ID Number</span></span>
- <span data-ttu-id="48268-2924">ID Number</span><span class="sxs-lookup"><span data-stu-id="48268-2924">ID Number</span></span>
- <span data-ttu-id="48268-2925">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="48268-2925">Identification</span></span>
- <span data-ttu-id="48268-2926">Personnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2926">Personnummer</span></span>
- <span data-ttu-id="48268-2927">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-2927">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="48268-2928">Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="48268-2928">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-2929">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2929">Format</span></span>

<span data-ttu-id="48268-2930">12 Ziffern, durch Bindestriche getrennt</span><span class="sxs-lookup"><span data-stu-id="48268-2930">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2931">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2931">Pattern</span></span>

<span data-ttu-id="48268-2932">12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-2932">12 digits:</span></span>
- <span data-ttu-id="48268-2933">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2933">Four digits</span></span> 
- <span data-ttu-id="48268-2934">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-2934">A hyphen</span></span> 
- <span data-ttu-id="48268-2935">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="48268-2935">Seven digits</span></span> 
- <span data-ttu-id="48268-2936">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-2936">A hyphen</span></span> 
- <span data-ttu-id="48268-2937">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="48268-2937">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2938">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2938">Checksum</span></span>

<span data-ttu-id="48268-2939">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-2939">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2940">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2940">Definition</span></span>

<span data-ttu-id="48268-2941">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2942">Der reguläre Ausdruck Regex_philippines_unified_id findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2942">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2943">Ein Schlüsselwort aus Keyword_philippines_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2943">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2944">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2944">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="48268-2945">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="48268-2945">Keyword_philippines_id</span></span>

- <span data-ttu-id="48268-2946">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="48268-2946">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="48268-2947">Umid</span><span class="sxs-lookup"><span data-stu-id="48268-2947">UMID</span></span> 
- <span data-ttu-id="48268-2948">Identity Card</span><span class="sxs-lookup"><span data-stu-id="48268-2948">Identity Card</span></span> 
- <span data-ttu-id="48268-2949">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="48268-2949">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="48268-2950">Polen Personalausweis</span><span class="sxs-lookup"><span data-stu-id="48268-2950">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="48268-2951">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2951">Format</span></span>

<span data-ttu-id="48268-2952">Drei Buchstaben und sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2952">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2953">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2953">Pattern</span></span>

<span data-ttu-id="48268-2954">Drei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2954">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2955">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2955">Checksum</span></span>

<span data-ttu-id="48268-2956">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2956">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2957">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2957">Definition</span></span>

<span data-ttu-id="48268-2958">Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_polish_national_id findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-2958">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="48268-2959">Ein Schlüsselwort aus Keyword_polish_national_id_passport_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2959">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="48268-2960">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2960">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2961">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2961">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="48268-2962">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="48268-2962">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="48268-2963">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="48268-2963">Dowód osobisty</span></span>
- <span data-ttu-id="48268-2964">Numer dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="48268-2964">Numer dowodu osobistego</span></span>
- <span data-ttu-id="48268-2965">Nazwa i Numer dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="48268-2965">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="48268-2966">Nazwa i Nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="48268-2966">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="48268-2967">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="48268-2967">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="48268-2968">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="48268-2968">Dowód Tożsamości</span></span>
- <span data-ttu-id="48268-2969">Dow.</span><span class="sxs-lookup"><span data-stu-id="48268-2969">dow.</span></span> <span data-ttu-id="48268-2970">OS.</span><span class="sxs-lookup"><span data-stu-id="48268-2970">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="48268-2971">Polnische ID-Karte (PESEL)</span><span class="sxs-lookup"><span data-stu-id="48268-2971">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="48268-2972">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2972">Format</span></span>

<span data-ttu-id="48268-2973">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2973">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2974">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2974">Pattern</span></span>

<span data-ttu-id="48268-2975">11 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2975">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2976">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2976">Checksum</span></span>

<span data-ttu-id="48268-2977">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2977">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2978">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2978">Definition</span></span>

<span data-ttu-id="48268-2979">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2979">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2980">Die Funktion Func_pesel_identification_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2980">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2981">Ein Schlüsselwort aus Keyword_pesel_identification_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2981">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="48268-2982">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2982">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-2983">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2983">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="48268-2984">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="48268-2984">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="48268-2985">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="48268-2985">Nr PESEL</span></span>
- <span data-ttu-id="48268-2986">PESEL</span><span class="sxs-lookup"><span data-stu-id="48268-2986">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="48268-2987">Polen Reisepass</span><span class="sxs-lookup"><span data-stu-id="48268-2987">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="48268-2988">Format</span><span class="sxs-lookup"><span data-stu-id="48268-2988">Format</span></span>

<span data-ttu-id="48268-2989">Zwei Buchstaben und sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2989">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-2990">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-2990">Pattern</span></span>

<span data-ttu-id="48268-2991">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-2991">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-2992">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-2992">Checksum</span></span>

<span data-ttu-id="48268-2993">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-2993">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-2994">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-2994">Definition</span></span>

<span data-ttu-id="48268-2995">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-2995">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-2996">Die Funktion Func_polish_passport_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-2996">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-2997">Ein Schlüsselwort aus Keyword_polish_national_id_passport_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-2997">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="48268-2998">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-2998">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="48268-2999">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-2999">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="48268-3000">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="48268-3000">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="48268-3001">Numer paszportu</span><span class="sxs-lookup"><span data-stu-id="48268-3001">Numer paszportu</span></span>
- <span data-ttu-id="48268-3002">Nr.</span><span class="sxs-lookup"><span data-stu-id="48268-3002">Nr.</span></span> <span data-ttu-id="48268-3003">Paszportu</span><span class="sxs-lookup"><span data-stu-id="48268-3003">Paszportu</span></span>
- <span data-ttu-id="48268-3004">Paszport</span><span class="sxs-lookup"><span data-stu-id="48268-3004">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="48268-3005">Portugal – Bürgerkartennummer</span><span class="sxs-lookup"><span data-stu-id="48268-3005">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3006">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3006">Format</span></span>

<span data-ttu-id="48268-3007">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3007">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3008">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3008">Pattern</span></span>

<span data-ttu-id="48268-3009">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3009">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3010">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3010">Checksum</span></span>

<span data-ttu-id="48268-3011">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3011">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3012">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3012">Definition</span></span>

<span data-ttu-id="48268-3013">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3013">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3014">Der reguläre Ausdruck Regex_portugal_citizen_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3014">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3015">Ein Schlüsselwort aus Keyword_portugal_citizen_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3015">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3016">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3016">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="48268-3017">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="48268-3017">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="48268-3018">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="48268-3018">Citizen Card</span></span>
- <span data-ttu-id="48268-3019">National ID Card</span><span class="sxs-lookup"><span data-stu-id="48268-3019">National ID Card</span></span>
- <span data-ttu-id="48268-3020">CC</span><span class="sxs-lookup"><span data-stu-id="48268-3020">CC</span></span>
- <span data-ttu-id="48268-3021">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="48268-3021">Cartão de Cidadão</span></span>
- <span data-ttu-id="48268-3022">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="48268-3022">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="48268-3023">Saudi-Arabische Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="48268-3023">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="48268-3024">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3024">Format</span></span>

<span data-ttu-id="48268-3025">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3025">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3026">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3026">Pattern</span></span>

<span data-ttu-id="48268-3027">10 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3027">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3028">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3028">Checksum</span></span>

<span data-ttu-id="48268-3029">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3029">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3030">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3030">Definition</span></span>

<span data-ttu-id="48268-3031">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3031">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3032">Der reguläre Ausdruck Regex_saudi_arabia_national_id findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3032">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3033">Ein Schlüsselwort aus Keyword_saudi_arabia_national_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3033">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3034">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3034">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="48268-3035">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="48268-3035">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="48268-3036">Identification Card</span><span class="sxs-lookup"><span data-stu-id="48268-3036">Identification Card</span></span> 
- <span data-ttu-id="48268-3037">I card number</span><span class="sxs-lookup"><span data-stu-id="48268-3037">I card number</span></span> 
- <span data-ttu-id="48268-3038">ID number</span><span class="sxs-lookup"><span data-stu-id="48268-3038">ID number</span></span> 
- <span data-ttu-id="48268-3039">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="48268-3039">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="48268-3040">Singapur – National Registration Identity Card-Nummer (NRIC)</span><span class="sxs-lookup"><span data-stu-id="48268-3040">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3041">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3041">Format</span></span>

<span data-ttu-id="48268-3042">Neun Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3042">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3043">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3043">Pattern</span></span>

- <span data-ttu-id="48268-3044">Neun Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-3044">Nine letters and digits:</span></span>
- <span data-ttu-id="48268-3045">Die Buchstaben "F", "G", "S" oder "T" (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="48268-3045">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="48268-3046">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="48268-3046">Seven digits</span></span> 
- <span data-ttu-id="48268-3047">Eine alphabetische Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="48268-3047">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3048">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3048">Checksum</span></span>

<span data-ttu-id="48268-3049">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-3049">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3050">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3050">Definition</span></span>

<span data-ttu-id="48268-3051">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3051">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3052">Der reguläre Ausdruck Regex_singapore_nric findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3052">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3053">Ein Schlüsselwort aus Keyword_singapore_nric wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3053">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="48268-3054">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-3054">The checksum passes.</span></span>

<span data-ttu-id="48268-3055">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3055">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3056">Der reguläre Ausdruck Regex_singapore_nric findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3056">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3057">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-3057">The checksum passes.</span></span>

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3058">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3058">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="48268-3059">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="48268-3059">Keyword_singapore_nric</span></span>

- <span data-ttu-id="48268-3060">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="48268-3060">National Registration Identity Card</span></span> 
- <span data-ttu-id="48268-3061">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="48268-3061">Identity Card Number</span></span> 
- <span data-ttu-id="48268-3062">NRIC</span><span class="sxs-lookup"><span data-stu-id="48268-3062">NRIC</span></span> 
- <span data-ttu-id="48268-3063">IK</span><span class="sxs-lookup"><span data-stu-id="48268-3063">IC</span></span> 
- <span data-ttu-id="48268-3064">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="48268-3064">Foreign Identification Number</span></span> 
- <span data-ttu-id="48268-3065">FIN</span><span class="sxs-lookup"><span data-stu-id="48268-3065">FIN</span></span> 
- <span data-ttu-id="48268-3066">身份证</span><span class="sxs-lookup"><span data-stu-id="48268-3066">身份证</span></span> 
- <span data-ttu-id="48268-3067">身份證</span><span class="sxs-lookup"><span data-stu-id="48268-3067">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="48268-3068">Südafrika – Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-3068">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3069">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3069">Format</span></span>

<span data-ttu-id="48268-3070">13 Ziffern, die Leerzeichen enthalten können</span><span class="sxs-lookup"><span data-stu-id="48268-3070">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3071">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3071">Pattern</span></span>

<span data-ttu-id="48268-3072">13 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-3072">13 digits:</span></span>
- <span data-ttu-id="48268-3073">Sechs Ziffern im Format JJMMTT, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="48268-3073">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="48268-3074">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3074">Four digits</span></span> 
- <span data-ttu-id="48268-3075">Ein einstelliger Citizenship-Indikator </span><span class="sxs-lookup"><span data-stu-id="48268-3075">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="48268-3076">Die Ziffer "8" oder "9" </span><span class="sxs-lookup"><span data-stu-id="48268-3076">The digit "8" or "9"</span></span> 
- <span data-ttu-id="48268-3077">Eine Ziffer als Prüfsummenziffer</span><span class="sxs-lookup"><span data-stu-id="48268-3077">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3078">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3078">Checksum</span></span>

<span data-ttu-id="48268-3079">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-3079">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3080">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3080">Definition</span></span>

<span data-ttu-id="48268-3081">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3082">Die Funktion Func_south_africa_identification_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3082">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3083">Ein Schlüsselwort aus Keyword_south_africa_identification_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3083">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="48268-3084">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-3084">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3085">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3085">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="48268-3086">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="48268-3086">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="48268-3087">Identity card</span><span class="sxs-lookup"><span data-stu-id="48268-3087">Identity card</span></span>
- <span data-ttu-id="48268-3088">ID</span><span class="sxs-lookup"><span data-stu-id="48268-3088">ID</span></span>
- <span data-ttu-id="48268-3089">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="48268-3089">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="48268-3090">Südkorea – Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-3090">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3091">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3091">Format</span></span>

<span data-ttu-id="48268-3092">13 Ziffern, die einen Bindestrich enthalten</span><span class="sxs-lookup"><span data-stu-id="48268-3092">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3093">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3093">Pattern</span></span>

<span data-ttu-id="48268-3094">13 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-3094">13 digits:</span></span>
- <span data-ttu-id="48268-3095">Sechs Ziffern im Format JJMMTT, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="48268-3095">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="48268-3096">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="48268-3096">A hyphen</span></span> 
- <span data-ttu-id="48268-3097">Eine Ziffer, die durch das Jahrhundert und das Geschlecht bestimmt wird </span><span class="sxs-lookup"><span data-stu-id="48268-3097">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="48268-3098">Vierstelliger Code für die Geburtsregion </span><span class="sxs-lookup"><span data-stu-id="48268-3098">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="48268-3099">Eine Ziffer, um Personen zu unterscheiden, für die die vorhergehenden Zahlen identisch sind </span><span class="sxs-lookup"><span data-stu-id="48268-3099">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="48268-3100">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="48268-3100">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3101">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3101">Checksum</span></span>

<span data-ttu-id="48268-3102">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-3102">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3103">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3103">Definition</span></span>

<span data-ttu-id="48268-3104">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3104">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3105">Die Funktion Func_south_korea_resident_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3105">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3106">Ein Schlüsselwort aus Keyword_south_korea_resident_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3106">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="48268-3107">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-3107">The checksum passes.</span></span>

<span data-ttu-id="48268-3108">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3108">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3109">Die Funktion Func_south_korea_resident_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3109">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3110">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-3110">The checksum passes.</span></span>

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3111">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3111">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="48268-3112">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="48268-3112">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="48268-3113">National ID card</span><span class="sxs-lookup"><span data-stu-id="48268-3113">National ID card</span></span> 
- <span data-ttu-id="48268-3114">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="48268-3114">Citizen's Registration Number</span></span> 
- <span data-ttu-id="48268-3115">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="48268-3115">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="48268-3116">RRN</span><span class="sxs-lookup"><span data-stu-id="48268-3116">RRN</span></span> 
- <span data-ttu-id="48268-3117">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="48268-3117">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="48268-3118">Spanische Sozialversicherungsnummer (SSN)</span><span class="sxs-lookup"><span data-stu-id="48268-3118">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="48268-3119">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3119">Format</span></span>

<span data-ttu-id="48268-3120">11-12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3120">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3121">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3121">Pattern</span></span>

<span data-ttu-id="48268-3122">11-12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-3122">11-12 digits:</span></span>
- <span data-ttu-id="48268-3123">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3123">Two digits</span></span> 
- <span data-ttu-id="48268-3124">Ein Schrägstrich (optional)</span><span class="sxs-lookup"><span data-stu-id="48268-3124">A forward slash (optional)</span></span> 
- <span data-ttu-id="48268-3125">7 bis 8 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3125">7-8 digits</span></span> 
- <span data-ttu-id="48268-3126">Ein Schrägstrich (optional)</span><span class="sxs-lookup"><span data-stu-id="48268-3126">A forward slash (optional)</span></span> 
- <span data-ttu-id="48268-3127">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3127">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3128">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3128">Checksum</span></span>

<span data-ttu-id="48268-3129">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-3129">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3130">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3130">Definition</span></span>

<span data-ttu-id="48268-3131">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3132">Die Funktion Func_spanish_social_security_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3132">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3133">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-3133">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3134">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3134">Keywords</span></span>

<span data-ttu-id="48268-3135">Keine</span><span class="sxs-lookup"><span data-stu-id="48268-3135">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="48268-3136">SQL Server Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="48268-3136">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="48268-3137">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3137">Format</span></span>

<span data-ttu-id="48268-3138">Die Zeichenfolge "Benutzer-ID", "Benutzer-ID", "UID" oder "UserID", gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="48268-3138">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3139">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3139">Pattern</span></span>

- <span data-ttu-id="48268-3140">Die Zeichenfolge "Benutzer-ID", "Benutzer-ID", "UID" oder "UserID"</span><span class="sxs-lookup"><span data-stu-id="48268-3140">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="48268-3141">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-3141">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="48268-3142">Die Zeichenfolge "Password" oder "pwd", wobei "pwd" kein Kleinbuchstabe vorangestellt ist</span><span class="sxs-lookup"><span data-stu-id="48268-3142">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="48268-3143">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-3143">An equal sign (=)</span></span>
- <span data-ttu-id="48268-3144">Ein beliebiges Zeichen, das kein Dollarzeichen ($), Prozentzeichen (%), größer als das Symbol (>), Symbol (@), Anführungszeichen ("), Semikolon (;), linke geschweifte Klammer ([) oder linke Klammer ({) ist.</span><span class="sxs-lookup"><span data-stu-id="48268-3144">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="48268-3145">Eine beliebige Kombination von 7-128 Zeichen, die kein Semikolon sind (;), Schrägstrich (/) oder Anführungszeichen (")</span><span class="sxs-lookup"><span data-stu-id="48268-3145">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="48268-3146">Ein Semikolon (;) oder Anführungszeichen (")</span><span class="sxs-lookup"><span data-stu-id="48268-3146">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3147">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3147">Checksum</span></span>

<span data-ttu-id="48268-3148">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3148">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3149">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3149">Definition</span></span>

<span data-ttu-id="48268-3150">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3150">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3151">Der reguläre Ausdruck CEP_Regex_SQLServerConnectionString findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3151">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3152">Ein Schlüsselwort aus CEP_GlobalFilter wurde **nicht** gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3152">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="48268-3153">Der reguläre Ausdruck CEP_PasswordPlaceHolder findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3153">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3154">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3154">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3155">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3155">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="48268-3156">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="48268-3156">CEP_GlobalFilter</span></span>

- <span data-ttu-id="48268-3157">Einige-Kennwort</span><span class="sxs-lookup"><span data-stu-id="48268-3157">some-password</span></span>
- <span data-ttu-id="48268-3158">somepassword</span><span class="sxs-lookup"><span data-stu-id="48268-3158">somepassword</span></span>
- <span data-ttu-id="48268-3159">secretPassword</span><span class="sxs-lookup"><span data-stu-id="48268-3159">secretPassword</span></span>
- <span data-ttu-id="48268-3160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48268-3160">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="48268-3161">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="48268-3161">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="48268-3162">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="48268-3162">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="48268-3163">Password oder PWD gefolgt von 0-2 Leerzeichen, ein Gleichheitszeichen (=), 0-2 Leerzeichen und ein Sternchen (\*)--oder--</span><span class="sxs-lookup"><span data-stu-id="48268-3163">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="48268-3164">Password oder PWD gefolgt von:</span><span class="sxs-lookup"><span data-stu-id="48268-3164">Password or pwd followed by:</span></span>
    - <span data-ttu-id="48268-3165">Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="48268-3165">Equal sign (=)</span></span>
    - <span data-ttu-id="48268-3166">Kleiner als-Symbol (<)</span><span class="sxs-lookup"><span data-stu-id="48268-3166">Less than symbol (<)</span></span>
    - <span data-ttu-id="48268-3167">Eine beliebige Kombination von 1-200 Zeichen mit groß-oder Kleinbuchstaben, Ziffern, einem Sternchen (\*), einem Bindestrich (-), einem Unterstrich (_) oder einem Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-3167">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="48268-3168">Größer als-Symbol (>)</span><span class="sxs-lookup"><span data-stu-id="48268-3168">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="48268-3169">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="48268-3169">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="48268-3170">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="48268-3170">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="48268-3171">contoso</span><span class="sxs-lookup"><span data-stu-id="48268-3171">contoso</span></span>
- <span data-ttu-id="48268-3172">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="48268-3172">fabrikam</span></span>
- <span data-ttu-id="48268-3173">Northwind</span><span class="sxs-lookup"><span data-stu-id="48268-3173">northwind</span></span>
- <span data-ttu-id="48268-3174">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="48268-3174">sandbox</span></span>
- <span data-ttu-id="48268-3175">OneBox</span><span class="sxs-lookup"><span data-stu-id="48268-3175">onebox</span></span>
- <span data-ttu-id="48268-3176">localhost</span><span class="sxs-lookup"><span data-stu-id="48268-3176">localhost</span></span>
- <span data-ttu-id="48268-3177">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="48268-3177">127.0.0.1</span></span>
- <span data-ttu-id="48268-3178">testacs.</span><span class="sxs-lookup"><span data-stu-id="48268-3178">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="48268-3179">com</span><span class="sxs-lookup"><span data-stu-id="48268-3179">com</span></span>
- <span data-ttu-id="48268-3180">s-int.</span><span class="sxs-lookup"><span data-stu-id="48268-3180">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="48268-3181">NET</span><span class="sxs-lookup"><span data-stu-id="48268-3181">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="48268-3182">Schwedische Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="48268-3182">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="48268-3183">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3183">Format</span></span>

<span data-ttu-id="48268-3184">10 oder 12 Ziffern und ein optionales Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-3184">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3185">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3185">Pattern</span></span>

<span data-ttu-id="48268-3186">10 oder 12 Ziffern und ein optionals Trennzeichen:</span><span class="sxs-lookup"><span data-stu-id="48268-3186">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="48268-3187">2 bis 4 Ziffern (optional)</span><span class="sxs-lookup"><span data-stu-id="48268-3187">2-4 digits (optional)</span></span> 
- <span data-ttu-id="48268-3188">Sechs Ziffern im Datumsformat JJMMTT</span><span class="sxs-lookup"><span data-stu-id="48268-3188">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="48268-3189">Trennzeichen „-“ oder „+“ (optional) und</span><span class="sxs-lookup"><span data-stu-id="48268-3189">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="48268-3190">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3190">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3191">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3191">Checksum</span></span>

<span data-ttu-id="48268-3192">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-3192">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3193">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3193">Definition</span></span>

<span data-ttu-id="48268-3194">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3194">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3195">Die Funktion Func_swedish_national_identifier findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3195">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3196">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-3196">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3197">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3197">Keywords</span></span>

<span data-ttu-id="48268-3198">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3198">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="48268-3199">Schwedische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="48268-3199">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3200">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3200">Format</span></span>

<span data-ttu-id="48268-3201">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3201">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3202">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3202">Pattern</span></span>

<span data-ttu-id="48268-3203">Acht aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3203">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3204">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3204">Checksum</span></span>

<span data-ttu-id="48268-3205">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3205">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3206">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3206">Definition</span></span>

<span data-ttu-id="48268-3207">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3208">Der reguläre Ausdruck Regex_sweden_passport_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3208">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3209">Eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="48268-3209">One of the following is true:</span></span>
    - <span data-ttu-id="48268-3210">Ein Schlüsselwort aus Keyword_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3210">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="48268-3211">Ein Schlüsselwort aus Keyword_sweden_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3211">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3212">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3212">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="48268-3213">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="48268-3213">Keyword_sweden_passport</span></span>

- <span data-ttu-id="48268-3214">visa requirements</span><span class="sxs-lookup"><span data-stu-id="48268-3214">visa requirements</span></span> 
- <span data-ttu-id="48268-3215">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="48268-3215">Alien Registration Card</span></span> 
- <span data-ttu-id="48268-3216">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="48268-3216">Schengen visas</span></span> 
- <span data-ttu-id="48268-3217">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="48268-3217">Schengen visa</span></span> 
- <span data-ttu-id="48268-3218">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="48268-3218">Visa Processing</span></span> 
- <span data-ttu-id="48268-3219">Visa Type</span><span class="sxs-lookup"><span data-stu-id="48268-3219">Visa Type</span></span> 
- <span data-ttu-id="48268-3220">Single Entry</span><span class="sxs-lookup"><span data-stu-id="48268-3220">Single Entry</span></span> 
- <span data-ttu-id="48268-3221">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="48268-3221">Multiple Entry</span></span> 
- <span data-ttu-id="48268-3222">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="48268-3222">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="48268-3223">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="48268-3223">Keyword_passport</span></span>

- <span data-ttu-id="48268-3224">Passport Number</span><span class="sxs-lookup"><span data-stu-id="48268-3224">Passport Number</span></span> 
- <span data-ttu-id="48268-3225">Passport No</span><span class="sxs-lookup"><span data-stu-id="48268-3225">Passport No</span></span> 
- <span data-ttu-id="48268-3226">Passport#</span><span class="sxs-lookup"><span data-stu-id="48268-3226">Passport #</span></span> 
- <span data-ttu-id="48268-3227">Pass #</span><span class="sxs-lookup"><span data-stu-id="48268-3227">Passport#</span></span> 
- <span data-ttu-id="48268-3228">Passport-Nr</span><span class="sxs-lookup"><span data-stu-id="48268-3228">PassportID</span></span> 
- <span data-ttu-id="48268-3229">Passportno</span><span class="sxs-lookup"><span data-stu-id="48268-3229">Passportno</span></span> 
- <span data-ttu-id="48268-3230">passportnumber</span><span class="sxs-lookup"><span data-stu-id="48268-3230">passportnumber</span></span> 
- <span data-ttu-id="48268-3231">パスポート</span><span class="sxs-lookup"><span data-stu-id="48268-3231">パスポート</span></span> 
- <span data-ttu-id="48268-3232">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="48268-3232">パスポート番号</span></span> 
- <span data-ttu-id="48268-3233">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="48268-3233">パスポートのNum</span></span> 
- <span data-ttu-id="48268-3234">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="48268-3234">パスポート＃</span></span> 
- <span data-ttu-id="48268-3235">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="48268-3235">Numéro de passeport</span></span> 
- <span data-ttu-id="48268-3236">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="48268-3236">Passeport n °</span></span> 
- <span data-ttu-id="48268-3237">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="48268-3237">Passeport Non</span></span> 
- <span data-ttu-id="48268-3238">Passeport#</span><span class="sxs-lookup"><span data-stu-id="48268-3238">Passeport #</span></span> 
- <span data-ttu-id="48268-3239">Passeport #</span><span class="sxs-lookup"><span data-stu-id="48268-3239">Passeport#</span></span> 
- <span data-ttu-id="48268-3240">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="48268-3240">PasseportNon</span></span> 
- <span data-ttu-id="48268-3241">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="48268-3241">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="48268-3242">SWIFT-Code</span><span class="sxs-lookup"><span data-stu-id="48268-3242">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="48268-3243">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3243">Format</span></span>

<span data-ttu-id="48268-3244">Vier Buchstaben, gefolgt von 5-31 Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3244">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3245">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3245">Pattern</span></span>

<span data-ttu-id="48268-3246">Vier Buchstaben, gefolgt von 5 bis 31 Buchstaben oder Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-3246">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="48268-3247">Vier Buchstaben für den Bankcode (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="48268-3247">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="48268-3248">Ein optionales Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-3248">An optional space</span></span> 
- <span data-ttu-id="48268-3249">4 bis 28 Buchstaben oder Ziffern (BBAN, Basic Bank Account Number)</span><span class="sxs-lookup"><span data-stu-id="48268-3249">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="48268-3250">Ein optionales Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-3250">An optional space</span></span> 
- <span data-ttu-id="48268-3251">1 bis 3 Buchstaben oder Ziffern (Rest des BBAN)</span><span class="sxs-lookup"><span data-stu-id="48268-3251">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3252">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3252">Checksum</span></span>

<span data-ttu-id="48268-3253">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3253">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3254">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3254">Definition</span></span>

<span data-ttu-id="48268-3255">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3256">Der reguläre Ausdruck Regex_swift findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3256">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3257">Ein Schlüsselwort aus Keyword_swift wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3257">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3258">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3258">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="48268-3259">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="48268-3259">Keyword_swift</span></span>

- <span data-ttu-id="48268-3260">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="48268-3260">international organization for standardization 9362</span></span> 
- <span data-ttu-id="48268-3261">iso 9362</span><span class="sxs-lookup"><span data-stu-id="48268-3261">iso 9362</span></span> 
- <span data-ttu-id="48268-3262">iso9362</span><span class="sxs-lookup"><span data-stu-id="48268-3262">iso9362</span></span> 
- <span data-ttu-id="48268-3263">SWIFT\#</span><span class="sxs-lookup"><span data-stu-id="48268-3263">swift\#</span></span> 
- <span data-ttu-id="48268-3264">Swiftcode</span><span class="sxs-lookup"><span data-stu-id="48268-3264">swiftcode</span></span> 
- <span data-ttu-id="48268-3265">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="48268-3265">swiftnumber</span></span> 
- <span data-ttu-id="48268-3266">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="48268-3266">swiftroutingnumber</span></span> 
- <span data-ttu-id="48268-3267">swift code</span><span class="sxs-lookup"><span data-stu-id="48268-3267">swift code</span></span> 
- <span data-ttu-id="48268-3268">swift number #</span><span class="sxs-lookup"><span data-stu-id="48268-3268">swift number #</span></span> 
- <span data-ttu-id="48268-3269">swift routing number</span><span class="sxs-lookup"><span data-stu-id="48268-3269">swift routing number</span></span> 
- <span data-ttu-id="48268-3270">bic number</span><span class="sxs-lookup"><span data-stu-id="48268-3270">bic number</span></span> 
- <span data-ttu-id="48268-3271">bic code</span><span class="sxs-lookup"><span data-stu-id="48268-3271">bic code</span></span> 
- <span data-ttu-id="48268-3272">BIC\#</span><span class="sxs-lookup"><span data-stu-id="48268-3272">bic \#</span></span> 
- <span data-ttu-id="48268-3273">BIC\#</span><span class="sxs-lookup"><span data-stu-id="48268-3273">bic\#</span></span> 
- <span data-ttu-id="48268-3274">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="48268-3274">bank identifier code</span></span> 
- <span data-ttu-id="48268-3275">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="48268-3275">標準化9362</span></span> 
- <span data-ttu-id="48268-3276">迅速＃</span><span class="sxs-lookup"><span data-stu-id="48268-3276">迅速＃</span></span> 
- <span data-ttu-id="48268-3277">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="48268-3277">SWIFTコード</span></span> 
- <span data-ttu-id="48268-3278">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="48268-3278">SWIFT番号</span></span> 
- <span data-ttu-id="48268-3279">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="48268-3279">迅速なルーティング番号</span></span> 
- <span data-ttu-id="48268-3280">BIC番号</span><span class="sxs-lookup"><span data-stu-id="48268-3280">BIC番号</span></span> 
- <span data-ttu-id="48268-3281">BICコード</span><span class="sxs-lookup"><span data-stu-id="48268-3281">BICコード</span></span> 
- <span data-ttu-id="48268-3282">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="48268-3282">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="48268-3283">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="48268-3283">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="48268-3284">rapide\#</span><span class="sxs-lookup"><span data-stu-id="48268-3284">rapide \#</span></span> 
- <span data-ttu-id="48268-3285">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="48268-3285">code SWIFT</span></span> 
- <span data-ttu-id="48268-3286">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="48268-3286">le numéro de swift</span></span> 
- <span data-ttu-id="48268-3287">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="48268-3287">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="48268-3288">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="48268-3288">le numéro BIC</span></span> 
- <span data-ttu-id="48268-3289">\#BIC</span><span class="sxs-lookup"><span data-stu-id="48268-3289">\# BIC</span></span> 
- <span data-ttu-id="48268-3290">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="48268-3290">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="48268-3291">Taiwanesicher Personalausweis</span><span class="sxs-lookup"><span data-stu-id="48268-3291">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="48268-3292">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3292">Format</span></span>

<span data-ttu-id="48268-3293">Ein Buchstabe (auf Englisch) gefolgt von neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3293">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3294">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3294">Pattern</span></span>

<span data-ttu-id="48268-3295">Ein Buchstabe (Englisch), gefolgt von neun Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-3295">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="48268-3296">Ein Buchstabe (Englisch, Groß-/Kleinschreibung wird nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="48268-3296">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="48268-3297">Die Ziffer 1 oder 2</span><span class="sxs-lookup"><span data-stu-id="48268-3297">The digit "1" or "2"</span></span> 
- <span data-ttu-id="48268-3298">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3298">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3299">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3299">Checksum</span></span>

<span data-ttu-id="48268-3300">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-3300">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3301">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3301">Definition</span></span>

<span data-ttu-id="48268-3302">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3302">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3303">Die Funktion Func_taiwanese_national_id findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3303">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3304">Ein Schlüsselwort aus Keyword_taiwanese_national_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3304">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="48268-3305">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-3305">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3306">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3306">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="48268-3307">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="48268-3307">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="48268-3308">身份證字號</span><span class="sxs-lookup"><span data-stu-id="48268-3308">身份證字號</span></span> 
- <span data-ttu-id="48268-3309">身份證</span><span class="sxs-lookup"><span data-stu-id="48268-3309">身份證</span></span> 
- <span data-ttu-id="48268-3310">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="48268-3310">身份證號碼</span></span> 
- <span data-ttu-id="48268-3311">身份證號</span><span class="sxs-lookup"><span data-stu-id="48268-3311">身份證號</span></span> 
- <span data-ttu-id="48268-3312">身分證字號</span><span class="sxs-lookup"><span data-stu-id="48268-3312">身分證字號</span></span> 
- <span data-ttu-id="48268-3313">身分證</span><span class="sxs-lookup"><span data-stu-id="48268-3313">身分證</span></span> 
- <span data-ttu-id="48268-3314">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="48268-3314">身分證號碼</span></span> 
- <span data-ttu-id="48268-3315">身份證號</span><span class="sxs-lookup"><span data-stu-id="48268-3315">身份證號</span></span> 
- <span data-ttu-id="48268-3316">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="48268-3316">身分證統一編號</span></span> 
- <span data-ttu-id="48268-3317">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="48268-3317">國民身分證統一編號</span></span> 
- <span data-ttu-id="48268-3318">簽名</span><span class="sxs-lookup"><span data-stu-id="48268-3318">簽名</span></span> 
- <span data-ttu-id="48268-3319">蓋章</span><span class="sxs-lookup"><span data-stu-id="48268-3319">蓋章</span></span> 
- <span data-ttu-id="48268-3320">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="48268-3320">簽名或蓋章</span></span> 
- <span data-ttu-id="48268-3321">簽章</span><span class="sxs-lookup"><span data-stu-id="48268-3321">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="48268-3322">	Taiwan – Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="48268-3322">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3323">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3323">Format</span></span>

- <span data-ttu-id="48268-3324">Biometrische Passport-Nummer: neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3324">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="48268-3325">Nicht biometrische Passport-Nummer: neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3325">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3326">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3326">Pattern</span></span>
<span data-ttu-id="48268-3327">Biometrische Passnummer:</span><span class="sxs-lookup"><span data-stu-id="48268-3327">Biometric passport number:</span></span>
- <span data-ttu-id="48268-3328">Die Ziffer "3" </span><span class="sxs-lookup"><span data-stu-id="48268-3328">The digit "3"</span></span> 
- <span data-ttu-id="48268-3329">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3329">Eight digits</span></span>

<span data-ttu-id="48268-3330">Nicht biometrische Passnummer:</span><span class="sxs-lookup"><span data-stu-id="48268-3330">Non-biometric passport number:</span></span>
- <span data-ttu-id="48268-3331">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3331">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3332">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3332">Checksum</span></span>

<span data-ttu-id="48268-3333">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3333">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3334">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3334">Definition</span></span>

<span data-ttu-id="48268-3335">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3336">Der reguläre Ausdruck Regex_taiwan_passport findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3336">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3337">Ein Schlüsselwort aus Keyword_taiwan_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3337">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3338">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3338">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="48268-3339">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="48268-3339">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="48268-3340">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="48268-3340">ROC passport number</span></span> 
- <span data-ttu-id="48268-3341">Passport number</span><span class="sxs-lookup"><span data-stu-id="48268-3341">Passport number</span></span> 
- <span data-ttu-id="48268-3342">Passport no</span><span class="sxs-lookup"><span data-stu-id="48268-3342">Passport no</span></span> 
- <span data-ttu-id="48268-3343">Passport Num</span><span class="sxs-lookup"><span data-stu-id="48268-3343">Passport Num</span></span> 
- <span data-ttu-id="48268-3344">Passport #</span><span class="sxs-lookup"><span data-stu-id="48268-3344">Passport #</span></span> 
- <span data-ttu-id="48268-3345">护照</span><span class="sxs-lookup"><span data-stu-id="48268-3345">护照</span></span> 
- <span data-ttu-id="48268-3346">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="48268-3346">中華民國護照</span></span> 
- <span data-ttu-id="48268-3347">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="48268-3347">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="48268-3348">Taiwan – Einwohnerzertifikatsnummer (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="48268-3348">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3349">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3349">Format</span></span>

<span data-ttu-id="48268-3350">10 Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3350">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3351">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3351">Pattern</span></span>

<span data-ttu-id="48268-3352">10 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-3352">10 letters and digits:</span></span>
- <span data-ttu-id="48268-3353">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="48268-3353">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="48268-3354">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3354">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3355">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3355">Checksum</span></span>

<span data-ttu-id="48268-3356">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3356">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3357">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3357">Definition</span></span>

<span data-ttu-id="48268-3358">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3358">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3359">Der reguläre Ausdruck Regex_taiwan_resident_certificate findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3359">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3360">Ein Schlüsselwort aus Keyword_taiwan_resident_certificate wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3360">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3361">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3361">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="48268-3362">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="48268-3362">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="48268-3363">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="48268-3363">Resident Certificate</span></span> 
- <span data-ttu-id="48268-3364">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="48268-3364">Resident Cert</span></span> 
- <span data-ttu-id="48268-3365">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="48268-3365">Resident Cert.</span></span> 
- <span data-ttu-id="48268-3366">Identification card</span><span class="sxs-lookup"><span data-stu-id="48268-3366">Identification card</span></span> 
- <span data-ttu-id="48268-3367">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="48268-3367">Alien Resident Certificate</span></span> 
- <span data-ttu-id="48268-3368">ARC</span><span class="sxs-lookup"><span data-stu-id="48268-3368">ARC</span></span> 
- <span data-ttu-id="48268-3369">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="48268-3369">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="48268-3370">TARC</span><span class="sxs-lookup"><span data-stu-id="48268-3370">TARC</span></span> 
- <span data-ttu-id="48268-3371">居留證</span><span class="sxs-lookup"><span data-stu-id="48268-3371">居留證</span></span> 
- <span data-ttu-id="48268-3372">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="48268-3372">外僑居留證</span></span> 
- <span data-ttu-id="48268-3373">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="48268-3373">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="48268-3374">Thai-Populations Kennzeichnungs Code</span><span class="sxs-lookup"><span data-stu-id="48268-3374">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="48268-3375">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3375">Format</span></span>

<span data-ttu-id="48268-3376">13 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3376">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3377">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3377">Pattern</span></span>

<span data-ttu-id="48268-3378">13 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-3378">13 digits:</span></span>
- <span data-ttu-id="48268-3379">Die erste Ziffer ist nicht 0 oder 9.</span><span class="sxs-lookup"><span data-stu-id="48268-3379">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="48268-3380">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3380">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3381">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3381">Checksum</span></span>

<span data-ttu-id="48268-3382">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-3382">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3383">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3383">Definition</span></span>

<span data-ttu-id="48268-3384">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3384">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3385">Die Funktion Func_Thai_Citizen_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3385">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3386">Ein Schlüsselwort aus Keyword_Thai_Citizen_Id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3386">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="48268-3387">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3387">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3388">Die Funktion Func_Thai_Citizen_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3388">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3389">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3389">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="48268-3390">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="48268-3390">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="48268-3391">ID Number</span><span class="sxs-lookup"><span data-stu-id="48268-3391">ID Number</span></span>
- <span data-ttu-id="48268-3392">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-3392">Identification Number</span></span>
- <span data-ttu-id="48268-3393">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="48268-3393">บัตรประชาชน</span></span>
- <span data-ttu-id="48268-3394">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="48268-3394">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="48268-3395">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="48268-3395">บัตรประชาชน</span></span>
- <span data-ttu-id="48268-3396">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="48268-3396">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="48268-3397">Türkische nationale Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-3397">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3398">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3398">Format</span></span>

<span data-ttu-id="48268-3399">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3399">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3400">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3400">Pattern</span></span>

<span data-ttu-id="48268-3401">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3401">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3402">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3402">Checksum</span></span>

<span data-ttu-id="48268-3403">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-3403">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3404">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3404">Definition</span></span>

<span data-ttu-id="48268-3405">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3405">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3406">Die Funktion Func_Turkish_National_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3406">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3407">Ein Schlüsselwort aus Keyword_Turkish_National_Id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3407">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="48268-3408">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3408">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3409">Die Funktion Func_Turkish_National_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3409">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3410">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3410">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="48268-3411">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="48268-3411">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="48268-3412">TC KİMLİK Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3412">TC Kimlik No</span></span>
- <span data-ttu-id="48268-3413">TC KİMLİK numarası</span><span class="sxs-lookup"><span data-stu-id="48268-3413">TC Kimlik numarası</span></span>
- <span data-ttu-id="48268-3414">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="48268-3414">Vatandaşlık numarası</span></span>
- <span data-ttu-id="48268-3415">Vatandaşlık Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3415">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="48268-p142">Britische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3418">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3418">Format</span></span>

<span data-ttu-id="48268-3419">Kombination aus 18 Buchstaben und Ziffern im angegebenen Format</span><span class="sxs-lookup"><span data-stu-id="48268-3419">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3420">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3420">Pattern</span></span>

<span data-ttu-id="48268-3421">18 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="48268-3421">18 letters and digits:</span></span>
- <span data-ttu-id="48268-3422">Fünf Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) oder die Ziffer 9 anstelle eines Buchstabens</span><span class="sxs-lookup"><span data-stu-id="48268-3422">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="48268-3423">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="48268-3423">One digit</span></span> 
- <span data-ttu-id="48268-3424">Fünf Ziffern im Datumsformat MMDDY für das Geburtsdatum (das siebte Zeichen wird um 50 erhöht, wenn der Fahrer weiblich ist, d. h. 51 bis 62 statt 01 bis 12).</span><span class="sxs-lookup"><span data-stu-id="48268-3424">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="48268-3425">Zwei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) oder die Ziffer 9 anstelle eines Buchstabens</span><span class="sxs-lookup"><span data-stu-id="48268-3425">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="48268-3426">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3426">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3427">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3427">Checksum</span></span>

<span data-ttu-id="48268-3428">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-3428">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3429">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3429">Definition</span></span>

<span data-ttu-id="48268-3430">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3430">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3431">Die Funktion Func_uk_drivers_license findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3431">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3432">Ein Schlüsselwort aus Keyword_uk_drivers_license wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3432">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="48268-3433">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-3433">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3434">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3434">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="48268-3435">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="48268-3435">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="48268-3436">DVLA</span><span class="sxs-lookup"><span data-stu-id="48268-3436">DVLA</span></span> 
- <span data-ttu-id="48268-3437">light vans</span><span class="sxs-lookup"><span data-stu-id="48268-3437">light vans</span></span> 
- <span data-ttu-id="48268-3438">Quads entwickelt</span><span class="sxs-lookup"><span data-stu-id="48268-3438">quadbikes</span></span> 
- <span data-ttu-id="48268-3439">motor cars</span><span class="sxs-lookup"><span data-stu-id="48268-3439">motor cars</span></span> 
- <span data-ttu-id="48268-3440">125cc</span><span class="sxs-lookup"><span data-stu-id="48268-3440">125cc</span></span> 
- <span data-ttu-id="48268-3441">Beiwagen</span><span class="sxs-lookup"><span data-stu-id="48268-3441">sidecar</span></span> 
- <span data-ttu-id="48268-3442">Dreiräder</span><span class="sxs-lookup"><span data-stu-id="48268-3442">tricycles</span></span> 
- <span data-ttu-id="48268-3443">Motorrad</span><span class="sxs-lookup"><span data-stu-id="48268-3443">motorcycles</span></span> 
- <span data-ttu-id="48268-3444">photocard licence</span><span class="sxs-lookup"><span data-stu-id="48268-3444">photocard licence</span></span> 
- <span data-ttu-id="48268-3445">learner drivers</span><span class="sxs-lookup"><span data-stu-id="48268-3445">learner drivers</span></span> 
- <span data-ttu-id="48268-3446">licence holder</span><span class="sxs-lookup"><span data-stu-id="48268-3446">licence holder</span></span> 
- <span data-ttu-id="48268-3447">licence holders</span><span class="sxs-lookup"><span data-stu-id="48268-3447">licence holders</span></span> 
- <span data-ttu-id="48268-3448">driving licences</span><span class="sxs-lookup"><span data-stu-id="48268-3448">driving licences</span></span> 
- <span data-ttu-id="48268-3449">driving licence</span><span class="sxs-lookup"><span data-stu-id="48268-3449">driving licence</span></span> 
- <span data-ttu-id="48268-3450">dual control car</span><span class="sxs-lookup"><span data-stu-id="48268-3450">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="48268-p143">Britische Wählerverzeichnisnummer</span><span class="sxs-lookup"><span data-stu-id="48268-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3453">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3453">Format</span></span>

<span data-ttu-id="48268-3454">Zwei Buchstaben gefolgt von 1-4 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3454">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3455">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3455">Pattern</span></span>

<span data-ttu-id="48268-3456">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von 1-4 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3456">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3457">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3457">Checksum</span></span>

<span data-ttu-id="48268-3458">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3459">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3459">Definition</span></span>

<span data-ttu-id="48268-3460">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3460">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3461">Der reguläre Ausdruck Regex_uk_electoral findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3461">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3462">Ein Schlüsselwort aus Keyword_uk_electoral wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3462">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3463">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3463">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="48268-3464">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="48268-3464">Keyword_uk_electoral</span></span>

- <span data-ttu-id="48268-3465">council nomination</span><span class="sxs-lookup"><span data-stu-id="48268-3465">council nomination</span></span> 
- <span data-ttu-id="48268-3466">nomination form</span><span class="sxs-lookup"><span data-stu-id="48268-3466">nomination form</span></span> 
- <span data-ttu-id="48268-3467">electoral register</span><span class="sxs-lookup"><span data-stu-id="48268-3467">electoral register</span></span> 
- <span data-ttu-id="48268-3468">electoral roll</span><span class="sxs-lookup"><span data-stu-id="48268-3468">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="48268-p144">Britische National Health Service-Nummer</span><span class="sxs-lookup"><span data-stu-id="48268-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3471">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3471">Format</span></span>

<span data-ttu-id="48268-3472">10-17 Ziffern, durch Leerzeichen getrennt</span><span class="sxs-lookup"><span data-stu-id="48268-3472">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3473">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3473">Pattern</span></span>

<span data-ttu-id="48268-3474">10 bis 17 Stellen:</span><span class="sxs-lookup"><span data-stu-id="48268-3474">10-17 digits:</span></span>
- <span data-ttu-id="48268-3475">3 oder 10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3475">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="48268-3476">Ein Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-3476">A space</span></span> 
- <span data-ttu-id="48268-3477">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3477">Three digits</span></span> 
- <span data-ttu-id="48268-3478">Ein Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="48268-3478">A space</span></span> 
- <span data-ttu-id="48268-3479">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3479">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3480">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3480">Checksum</span></span>

<span data-ttu-id="48268-3481">Ja</span><span class="sxs-lookup"><span data-stu-id="48268-3481">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3482">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3482">Definition</span></span>

<span data-ttu-id="48268-3483">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3483">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3484">Die Funktion Func_uk_nhs_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3484">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3485">Eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="48268-3485">One of the following is true:</span></span>
    - <span data-ttu-id="48268-3486">Ein Schlüsselwort aus Keyword_uk_nhs_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3486">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="48268-3487">Ein Schlüsselwort aus Keyword_uk_nhs_number1 wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3487">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="48268-3488">Ein Schlüsselwort aus Keyword_uk_nhs_number_dob wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3488">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="48268-3489">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="48268-3489">The checksum passes.</span></span>

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3490">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3490">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="48268-3491">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="48268-3491">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="48268-3492">national health service</span><span class="sxs-lookup"><span data-stu-id="48268-3492">national health service</span></span> 
- <span data-ttu-id="48268-3493">NHS</span><span class="sxs-lookup"><span data-stu-id="48268-3493">nhs</span></span> 
- <span data-ttu-id="48268-3494">health services authority</span><span class="sxs-lookup"><span data-stu-id="48268-3494">health services authority</span></span> 
- <span data-ttu-id="48268-3495">health authority</span><span class="sxs-lookup"><span data-stu-id="48268-3495">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="48268-3496">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="48268-3496">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="48268-3497">patient id</span><span class="sxs-lookup"><span data-stu-id="48268-3497">patient id</span></span> 
- <span data-ttu-id="48268-3498">patient identification</span><span class="sxs-lookup"><span data-stu-id="48268-3498">patient identification</span></span> 
- <span data-ttu-id="48268-3499">patient no</span><span class="sxs-lookup"><span data-stu-id="48268-3499">patient no</span></span> 
- <span data-ttu-id="48268-3500">patient number</span><span class="sxs-lookup"><span data-stu-id="48268-3500">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="48268-3501">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="48268-3501">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="48268-3502">GP</span><span class="sxs-lookup"><span data-stu-id="48268-3502">GP</span></span> 
- <span data-ttu-id="48268-3503">DOB</span><span class="sxs-lookup"><span data-stu-id="48268-3503">DOB</span></span> 
- <span data-ttu-id="48268-3504">D. O. B</span><span class="sxs-lookup"><span data-stu-id="48268-3504">D.O.B</span></span> 
- <span data-ttu-id="48268-3505">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="48268-3505">Date of Birth</span></span> 
- <span data-ttu-id="48268-3506">Birth Date</span><span class="sxs-lookup"><span data-stu-id="48268-3506">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="48268-p145">Britische nationale Versicherungsnummer (NINO)</span><span class="sxs-lookup"><span data-stu-id="48268-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="48268-3509">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3509">Format</span></span>

<span data-ttu-id="48268-3510">7 Zeichen oder 9 Zeichen, getrennt durch Leerzeichen oder Bindestriche</span><span class="sxs-lookup"><span data-stu-id="48268-3510">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3511">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3511">Pattern</span></span>

<span data-ttu-id="48268-3512">Zwei mögliche Muster:</span><span class="sxs-lookup"><span data-stu-id="48268-3512">Two possible patterns:</span></span>

- <span data-ttu-id="48268-3513">Zwei Buchstaben (gültige Ninos verwenden nur bestimmte Zeichen in diesem Präfix, die von diesem Muster überprüft werden; Groß-/Kleinschreibung wird nicht berücksichtigt)</span><span class="sxs-lookup"><span data-stu-id="48268-3513">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="48268-3514">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3514">Six digits</span></span>
- <span data-ttu-id="48268-3515">Entweder "A", "B", "C" oder "'d" (wie das Präfix sind nur bestimmte Zeichen im Suffix zulässig; Groß-/Kleinschreibung wird nicht berücksichtigt)</span><span class="sxs-lookup"><span data-stu-id="48268-3515">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="48268-3516">ODER</span><span class="sxs-lookup"><span data-stu-id="48268-3516">OR</span></span>

- <span data-ttu-id="48268-3517">Zwei Buchstaben</span><span class="sxs-lookup"><span data-stu-id="48268-3517">Two letters</span></span>
- <span data-ttu-id="48268-3518">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-3518">A space or dash</span></span>
- <span data-ttu-id="48268-3519">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3519">Two digits</span></span>
- <span data-ttu-id="48268-3520">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-3520">A space or dash</span></span>
- <span data-ttu-id="48268-3521">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3521">Two digits</span></span>
- <span data-ttu-id="48268-3522">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-3522">A space or dash</span></span>
- <span data-ttu-id="48268-3523">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3523">Two digits</span></span>
- <span data-ttu-id="48268-3524">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-3524">A space or dash</span></span>
- <span data-ttu-id="48268-3525">Entweder "A", "B", "C" oder "'d"</span><span class="sxs-lookup"><span data-stu-id="48268-3525">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3526">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3526">Checksum</span></span>

<span data-ttu-id="48268-3527">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3527">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3528">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3528">Definition</span></span>

<span data-ttu-id="48268-3529">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3530">Die Funktion Func_uk_nino findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3530">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3531">Ein Schlüsselwort aus Keyword_uk_nino wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3531">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="48268-3532">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3532">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3533">Die Funktion Func_uk_nino findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3533">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3534">Es wurde kein Schlüsselwort aus Keyword_uk_nino gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3534">No keyword from Keyword_uk_nino is found.</span></span>

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3535">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3535">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="48268-3536">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="48268-3536">Keyword_uk_nino</span></span>

- <span data-ttu-id="48268-3537">national insurance number</span><span class="sxs-lookup"><span data-stu-id="48268-3537">national insurance number</span></span> 
- <span data-ttu-id="48268-3538">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="48268-3538">national insurance contributions</span></span> 
- <span data-ttu-id="48268-3539">protection act</span><span class="sxs-lookup"><span data-stu-id="48268-3539">protection act</span></span> 
- <span data-ttu-id="48268-3540">Versicherungs</span><span class="sxs-lookup"><span data-stu-id="48268-3540">insurance</span></span> 
- <span data-ttu-id="48268-3541">social security number</span><span class="sxs-lookup"><span data-stu-id="48268-3541">social security number</span></span> 
- <span data-ttu-id="48268-3542">insurance application</span><span class="sxs-lookup"><span data-stu-id="48268-3542">insurance application</span></span> 
- <span data-ttu-id="48268-3543">medical application</span><span class="sxs-lookup"><span data-stu-id="48268-3543">medical application</span></span> 
- <span data-ttu-id="48268-3544">social insurance</span><span class="sxs-lookup"><span data-stu-id="48268-3544">social insurance</span></span> 
- <span data-ttu-id="48268-3545">medical attention</span><span class="sxs-lookup"><span data-stu-id="48268-3545">medical attention</span></span> 
- <span data-ttu-id="48268-3546">social security</span><span class="sxs-lookup"><span data-stu-id="48268-3546">social security</span></span> 
- <span data-ttu-id="48268-3547">great britain</span><span class="sxs-lookup"><span data-stu-id="48268-3547">great britain</span></span> 
- <span data-ttu-id="48268-3548">Versicherungs</span><span class="sxs-lookup"><span data-stu-id="48268-3548">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="48268-p146">US-amerikanische/britische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="48268-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3551">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3551">Format</span></span>

<span data-ttu-id="48268-3552">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3552">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3553">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3553">Pattern</span></span>

<span data-ttu-id="48268-3554">Neun aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3554">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3555">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3555">Checksum</span></span>

<span data-ttu-id="48268-3556">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3556">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3557">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3557">Definition</span></span>

<span data-ttu-id="48268-3558">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3558">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3559">Die Funktion Func_usa_uk_passport findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3559">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3560">Ein Schlüsselwort aus Keyword_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3560">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3561">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3561">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="48268-3562">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="48268-3562">Keyword_passport</span></span>

- <span data-ttu-id="48268-3563">Passport Number</span><span class="sxs-lookup"><span data-stu-id="48268-3563">Passport Number</span></span> 
- <span data-ttu-id="48268-3564">Passport No</span><span class="sxs-lookup"><span data-stu-id="48268-3564">Passport No</span></span> 
- <span data-ttu-id="48268-3565">Passport#</span><span class="sxs-lookup"><span data-stu-id="48268-3565">Passport #</span></span> 
- <span data-ttu-id="48268-3566">Pass #</span><span class="sxs-lookup"><span data-stu-id="48268-3566">Passport#</span></span> 
- <span data-ttu-id="48268-3567">Passport-Nr</span><span class="sxs-lookup"><span data-stu-id="48268-3567">PassportID</span></span> 
- <span data-ttu-id="48268-3568">Passportno</span><span class="sxs-lookup"><span data-stu-id="48268-3568">Passportno</span></span> 
- <span data-ttu-id="48268-3569">passportnumber</span><span class="sxs-lookup"><span data-stu-id="48268-3569">passportnumber</span></span> 
- <span data-ttu-id="48268-3570">パスポート</span><span class="sxs-lookup"><span data-stu-id="48268-3570">パスポート</span></span> 
- <span data-ttu-id="48268-3571">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="48268-3571">パスポート番号</span></span> 
- <span data-ttu-id="48268-3572">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="48268-3572">パスポートのNum</span></span> 
- <span data-ttu-id="48268-3573">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="48268-3573">パスポート＃</span></span> 
- <span data-ttu-id="48268-3574">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="48268-3574">Numéro de passeport</span></span> 
- <span data-ttu-id="48268-3575">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="48268-3575">Passeport n °</span></span> 
- <span data-ttu-id="48268-3576">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="48268-3576">Passeport Non</span></span> 
- <span data-ttu-id="48268-3577">Passeport#</span><span class="sxs-lookup"><span data-stu-id="48268-3577">Passeport #</span></span> 
- <span data-ttu-id="48268-3578">Passeport #</span><span class="sxs-lookup"><span data-stu-id="48268-3578">Passeport#</span></span> 
- <span data-ttu-id="48268-3579">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="48268-3579">PasseportNon</span></span> 
- <span data-ttu-id="48268-3580">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="48268-3580">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="48268-3581">US-Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="48268-3581">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3582">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3582">Format</span></span>

<span data-ttu-id="48268-3583">8-17 Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3583">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3584">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3584">Pattern</span></span>

<span data-ttu-id="48268-3585">8-17 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3585">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3586">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3586">Checksum</span></span>

<span data-ttu-id="48268-3587">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3587">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3588">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3588">Definition</span></span>

<span data-ttu-id="48268-3589">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3589">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3590">Der reguläre Ausdruck Regex_usa_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3590">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3591">Ein Schlüsselwort aus Keyword_usa_Bank_Account wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3591">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3592">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3592">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="48268-3593">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="48268-3593">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="48268-3594">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-3594">Checking Account Number</span></span> 
- <span data-ttu-id="48268-3595">Checking Account</span><span class="sxs-lookup"><span data-stu-id="48268-3595">Checking Account</span></span> 
- <span data-ttu-id="48268-3596">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="48268-3596">Checking Account #</span></span> 
- <span data-ttu-id="48268-3597">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="48268-3597">Checking Acct Number</span></span> 
- <span data-ttu-id="48268-3598">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="48268-3598">Checking Acct #</span></span> 
- <span data-ttu-id="48268-3599">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="48268-3599">Checking Acct No.</span></span> 
- <span data-ttu-id="48268-3600">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="48268-3600">Checking Account No.</span></span> 
- <span data-ttu-id="48268-3601">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-3601">Bank Account Number</span></span> 
- <span data-ttu-id="48268-3602">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="48268-3602">Bank Account #</span></span> 
- <span data-ttu-id="48268-3603">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="48268-3603">Bank Acct Number</span></span> 
- <span data-ttu-id="48268-3604">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="48268-3604">Bank Acct #</span></span> 
- <span data-ttu-id="48268-3605">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="48268-3605">Bank Acct No.</span></span> 
- <span data-ttu-id="48268-3606">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="48268-3606">Bank Account No.</span></span> 
- <span data-ttu-id="48268-3607">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-3607">Savings Account Number</span></span> 
- <span data-ttu-id="48268-3608">Savings Account</span><span class="sxs-lookup"><span data-stu-id="48268-3608">Savings Account.</span></span> 
- <span data-ttu-id="48268-3609">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="48268-3609">Savings Account #</span></span> 
- <span data-ttu-id="48268-3610">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="48268-3610">Savings Acct Number</span></span> 
- <span data-ttu-id="48268-3611">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="48268-3611">Savings Acct #</span></span> 
- <span data-ttu-id="48268-3612">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="48268-3612">Savings Acct No.</span></span> 
- <span data-ttu-id="48268-3613">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="48268-3613">Savings Account No.</span></span> 
- <span data-ttu-id="48268-3614">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="48268-3614">Debit Account Number</span></span> 
- <span data-ttu-id="48268-3615">Debit Account</span><span class="sxs-lookup"><span data-stu-id="48268-3615">Debit Account</span></span> 
- <span data-ttu-id="48268-3616">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="48268-3616">Debit Account #</span></span> 
- <span data-ttu-id="48268-3617">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="48268-3617">Debit Acct Number</span></span> 
- <span data-ttu-id="48268-3618">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="48268-3618">Debit Acct #</span></span> 
- <span data-ttu-id="48268-3619">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="48268-3619">Debit Acct No.</span></span> 
- <span data-ttu-id="48268-3620">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="48268-3620">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="48268-3621">US-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="48268-3621">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="48268-3622">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3622">Format</span></span>

<span data-ttu-id="48268-3623">Abhängig vom Bundesstaat</span><span class="sxs-lookup"><span data-stu-id="48268-3623">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3624">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3624">Pattern</span></span>

<span data-ttu-id="48268-3625">Abhängig vom Bundesstaat – am Beispiel für New York:</span><span class="sxs-lookup"><span data-stu-id="48268-3625">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="48268-3626">Neun Ziffern, die wie DDD DDD DDD formatiert sind, stimmen überein.</span><span class="sxs-lookup"><span data-stu-id="48268-3626">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="48268-3627">Neun Ziffern wie ddddddddd werden nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3627">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3628">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3628">Checksum</span></span>

<span data-ttu-id="48268-3629">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3629">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3630">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3630">Definition</span></span>

<span data-ttu-id="48268-3631">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3631">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3632">Die Funktion Func_new_york_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3632">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3633">Ein Schlüsselwort aus Keyword_[state_name]_drivers_license_name wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3633">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="48268-3634">Ein Schlüsselwort aus Keyword_us_drivers_license wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3634">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="48268-3635">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3635">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3636">Die Funktion Func_new_york_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3636">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3637">Ein Schlüsselwort aus Keyword_[state_name]_drivers_license_name wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3637">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="48268-3638">Ein Schlüsselwort aus Keyword_us_drivers_license_abbreviations wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3638">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="48268-3639">Es wurde kein Schlüsselwort aus Keyword_us_drivers_license gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3639">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3640">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3640">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="48268-3641">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="48268-3641">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="48268-3642">DL</span><span class="sxs-lookup"><span data-stu-id="48268-3642">DL</span></span> 
- <span data-ttu-id="48268-3643">DLS</span><span class="sxs-lookup"><span data-stu-id="48268-3643">DLS</span></span> 
- <span data-ttu-id="48268-3644">CDL</span><span class="sxs-lookup"><span data-stu-id="48268-3644">CDL</span></span> 
- <span data-ttu-id="48268-3645">CDLS</span><span class="sxs-lookup"><span data-stu-id="48268-3645">CDLS</span></span> 
- <span data-ttu-id="48268-3646">ID</span><span class="sxs-lookup"><span data-stu-id="48268-3646">ID</span></span> 
- <span data-ttu-id="48268-3647">IDs</span><span class="sxs-lookup"><span data-stu-id="48268-3647">IDs</span></span> 
- <span data-ttu-id="48268-3648">DL #</span><span class="sxs-lookup"><span data-stu-id="48268-3648">DL#</span></span> 
- <span data-ttu-id="48268-3649">DLS #</span><span class="sxs-lookup"><span data-stu-id="48268-3649">DLS#</span></span> 
- <span data-ttu-id="48268-3650">CDL #</span><span class="sxs-lookup"><span data-stu-id="48268-3650">CDL#</span></span> 
- <span data-ttu-id="48268-3651">CDLS #</span><span class="sxs-lookup"><span data-stu-id="48268-3651">CDLS#</span></span> 
- <span data-ttu-id="48268-3652">ID #</span><span class="sxs-lookup"><span data-stu-id="48268-3652">ID#</span></span>
- <span data-ttu-id="48268-3653">IDs #</span><span class="sxs-lookup"><span data-stu-id="48268-3653">IDs#</span></span> 
- <span data-ttu-id="48268-3654">ID number</span><span class="sxs-lookup"><span data-stu-id="48268-3654">ID number</span></span> 
- <span data-ttu-id="48268-3655">ID numbers</span><span class="sxs-lookup"><span data-stu-id="48268-3655">ID numbers</span></span> 
- <span data-ttu-id="48268-3656">LIC</span><span class="sxs-lookup"><span data-stu-id="48268-3656">LIC</span></span> 
- <span data-ttu-id="48268-3657">LIC #</span><span class="sxs-lookup"><span data-stu-id="48268-3657">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="48268-3658">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="48268-3658">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="48268-3659">DriverLic</span><span class="sxs-lookup"><span data-stu-id="48268-3659">DriverLic</span></span> 
- <span data-ttu-id="48268-3660">DriverLics</span><span class="sxs-lookup"><span data-stu-id="48268-3660">DriverLics</span></span> 
- <span data-ttu-id="48268-3661">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="48268-3661">DriverLicense</span></span> 
- <span data-ttu-id="48268-3662">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="48268-3662">DriverLicenses</span></span> 
- <span data-ttu-id="48268-3663">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="48268-3663">Driver Lic</span></span> 
- <span data-ttu-id="48268-3664">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="48268-3664">Driver Lics</span></span> 
- <span data-ttu-id="48268-3665">Driver License</span><span class="sxs-lookup"><span data-stu-id="48268-3665">Driver License</span></span> 
- <span data-ttu-id="48268-3666">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-3666">Driver Licenses</span></span> 
- <span data-ttu-id="48268-3667">DriversLic</span><span class="sxs-lookup"><span data-stu-id="48268-3667">DriversLic</span></span> 
- <span data-ttu-id="48268-3668">DriversLics</span><span class="sxs-lookup"><span data-stu-id="48268-3668">DriversLics</span></span> 
- <span data-ttu-id="48268-3669">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="48268-3669">DriversLicense</span></span> 
- <span data-ttu-id="48268-3670">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="48268-3670">DriversLicenses</span></span> 
- <span data-ttu-id="48268-3671">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="48268-3671">Drivers Lic</span></span> 
- <span data-ttu-id="48268-3672">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="48268-3672">Drivers Lics</span></span> 
- <span data-ttu-id="48268-3673">Drivers License</span><span class="sxs-lookup"><span data-stu-id="48268-3673">Drivers License</span></span> 
- <span data-ttu-id="48268-3674">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-3674">Drivers Licenses</span></span> 
- <span data-ttu-id="48268-3675">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="48268-3675">Driver'Lic</span></span> 
- <span data-ttu-id="48268-3676">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="48268-3676">Driver'Lics</span></span> 
- <span data-ttu-id="48268-3677">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="48268-3677">Driver'License</span></span> 
- <span data-ttu-id="48268-3678">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-3678">Driver'Licenses</span></span> 
- <span data-ttu-id="48268-3679">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="48268-3679">Driver' Lic</span></span> 
- <span data-ttu-id="48268-3680">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="48268-3680">Driver' Lics</span></span> 
- <span data-ttu-id="48268-3681">Driver' License</span><span class="sxs-lookup"><span data-stu-id="48268-3681">Driver' License</span></span> 
- <span data-ttu-id="48268-3682">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-3682">Driver' Licenses</span></span>
- <span data-ttu-id="48268-3683">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="48268-3683">Driver'sLic</span></span> 
- <span data-ttu-id="48268-3684">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="48268-3684">Driver'sLics</span></span> 
- <span data-ttu-id="48268-3685">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="48268-3685">Driver'sLicense</span></span> 
- <span data-ttu-id="48268-3686">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="48268-3686">Driver'sLicenses</span></span> 
- <span data-ttu-id="48268-3687">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="48268-3687">Driver's Lic</span></span> 
- <span data-ttu-id="48268-3688">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="48268-3688">Driver's Lics</span></span> 
- <span data-ttu-id="48268-3689">Driver's License</span><span class="sxs-lookup"><span data-stu-id="48268-3689">Driver's License</span></span> 
- <span data-ttu-id="48268-3690">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="48268-3690">Driver's Licenses</span></span> 
- <span data-ttu-id="48268-3691">identification number</span><span class="sxs-lookup"><span data-stu-id="48268-3691">identification number</span></span> 
- <span data-ttu-id="48268-3692">identification numbers</span><span class="sxs-lookup"><span data-stu-id="48268-3692">identification numbers</span></span> 
- <span data-ttu-id="48268-3693">identification#</span><span class="sxs-lookup"><span data-stu-id="48268-3693">identification #</span></span> 
- <span data-ttu-id="48268-3694">id card</span><span class="sxs-lookup"><span data-stu-id="48268-3694">id card</span></span> 
- <span data-ttu-id="48268-3695">id cards</span><span class="sxs-lookup"><span data-stu-id="48268-3695">id cards</span></span> 
- <span data-ttu-id="48268-3696">identification card</span><span class="sxs-lookup"><span data-stu-id="48268-3696">identification card</span></span> 
- <span data-ttu-id="48268-3697">identification cards</span><span class="sxs-lookup"><span data-stu-id="48268-3697">identification cards</span></span> 
- <span data-ttu-id="48268-3698">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="48268-3698">DriverLic#</span></span> 
- <span data-ttu-id="48268-3699">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="48268-3699">DriverLics#</span></span> 
- <span data-ttu-id="48268-3700">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="48268-3700">DriverLicense#</span></span> 
- <span data-ttu-id="48268-3701">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="48268-3701">DriverLicenses#</span></span> 
- <span data-ttu-id="48268-3702">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-3702">Driver Lic#</span></span> 
- <span data-ttu-id="48268-3703">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-3703">Driver Lics#</span></span> 
- <span data-ttu-id="48268-3704">Driver License#</span><span class="sxs-lookup"><span data-stu-id="48268-3704">Driver License#</span></span> 
- <span data-ttu-id="48268-3705">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-3705">Driver Licenses#</span></span> 
- <span data-ttu-id="48268-3706">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="48268-3706">DriversLic#</span></span> 
- <span data-ttu-id="48268-3707">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="48268-3707">DriversLics#</span></span> 
- <span data-ttu-id="48268-3708">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="48268-3708">DriversLicense#</span></span> 
- <span data-ttu-id="48268-3709">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="48268-3709">DriversLicenses#</span></span> 
- <span data-ttu-id="48268-3710">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-3710">Drivers Lic#</span></span> 
- <span data-ttu-id="48268-3711">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-3711">Drivers Lics#</span></span> 
- <span data-ttu-id="48268-3712">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="48268-3712">Drivers License#</span></span> 
- <span data-ttu-id="48268-3713">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-3713">Drivers Licenses#</span></span> 
- <span data-ttu-id="48268-3714">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="48268-3714">Driver'Lic#</span></span> 
- <span data-ttu-id="48268-3715">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="48268-3715">Driver'Lics#</span></span> 
- <span data-ttu-id="48268-3716">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="48268-3716">Driver'License#</span></span> 
- <span data-ttu-id="48268-3717">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="48268-3717">Driver'Licenses#</span></span> 
- <span data-ttu-id="48268-3718">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-3718">Driver' Lic#</span></span> 
- <span data-ttu-id="48268-3719">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-3719">Driver' Lics#</span></span> 
- <span data-ttu-id="48268-3720">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="48268-3720">Driver' License#</span></span> 
- <span data-ttu-id="48268-3721">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-3721">Driver' Licenses#</span></span> 
- <span data-ttu-id="48268-3722">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="48268-3722">Driver'sLic#</span></span> 
- <span data-ttu-id="48268-3723">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="48268-3723">Driver'sLics#</span></span> 
- <span data-ttu-id="48268-3724">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="48268-3724">Driver'sLicense#</span></span> 
- <span data-ttu-id="48268-3725">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="48268-3725">Driver'sLicenses#</span></span> 
- <span data-ttu-id="48268-3726">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="48268-3726">Driver's Lic#</span></span> 
- <span data-ttu-id="48268-3727">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="48268-3727">Driver's Lics#</span></span> 
- <span data-ttu-id="48268-3728">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="48268-3728">Driver's License#</span></span> 
- <span data-ttu-id="48268-3729">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="48268-3729">Driver's Licenses#</span></span> 
- <span data-ttu-id="48268-3730">id card#</span><span class="sxs-lookup"><span data-stu-id="48268-3730">id card#</span></span> 
- <span data-ttu-id="48268-3731">id cards#</span><span class="sxs-lookup"><span data-stu-id="48268-3731">id cards#</span></span> 
- <span data-ttu-id="48268-3732">identification card#</span><span class="sxs-lookup"><span data-stu-id="48268-3732">identification card#</span></span> 
- <span data-ttu-id="48268-3733">identification cards#</span><span class="sxs-lookup"><span data-stu-id="48268-3733">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="48268-3734">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="48268-3734">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="48268-3735">Abkürzung für Bundesstaat (z. B. „NY“)</span><span class="sxs-lookup"><span data-stu-id="48268-3735">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="48268-3736">Name des Bundesstaats (z. B. „New York“)</span><span class="sxs-lookup"><span data-stu-id="48268-3736">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="48268-3737">US-Steueridentifikationsnummer (ITIN)</span><span class="sxs-lookup"><span data-stu-id="48268-3737">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="48268-3738">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3738">Format</span></span>

<span data-ttu-id="48268-3739">Neun Ziffern, die mit "9" beginnen und "7" oder "8" als vierte Ziffer enthalten, optional mit Leerzeichen oder Bindestrichen formatiert</span><span class="sxs-lookup"><span data-stu-id="48268-3739">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3740">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3740">Pattern</span></span>

<span data-ttu-id="48268-3741">Formatiert</span><span class="sxs-lookup"><span data-stu-id="48268-3741">Formatted:</span></span>
- <span data-ttu-id="48268-3742">Die Ziffer 9</span><span class="sxs-lookup"><span data-stu-id="48268-3742">The digit "9"</span></span> 
- <span data-ttu-id="48268-3743">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3743">Two digits</span></span> 
- <span data-ttu-id="48268-3744">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-3744">A space or dash</span></span> 
- <span data-ttu-id="48268-3745">Eine 7 oder 8</span><span class="sxs-lookup"><span data-stu-id="48268-3745">A "7" or "8"</span></span> 
- <span data-ttu-id="48268-3746">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="48268-3746">A digit</span></span> 
- <span data-ttu-id="48268-3747">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="48268-3747">A space, or dash</span></span> 
- <span data-ttu-id="48268-3748">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3748">Four digits</span></span>

<span data-ttu-id="48268-3749">Unformatiert</span><span class="sxs-lookup"><span data-stu-id="48268-3749">Unformatted:</span></span>
- <span data-ttu-id="48268-3750">Die Ziffer 9</span><span class="sxs-lookup"><span data-stu-id="48268-3750">The digit "9"</span></span> 
- <span data-ttu-id="48268-3751">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3751">Two digits</span></span> 
- <span data-ttu-id="48268-3752">Eine 7 oder 8</span><span class="sxs-lookup"><span data-stu-id="48268-3752">A "7" or "8"</span></span> 
- <span data-ttu-id="48268-3753">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="48268-3753">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3754">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3754">Checksum</span></span>

<span data-ttu-id="48268-3755">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3755">No</span></span>

### <a name="definition"></a><span data-ttu-id="48268-3756">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3756">Definition</span></span>

<span data-ttu-id="48268-3757">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3757">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3758">Die Funktion Func_formatted_itin findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3758">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3759">Mindestens eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="48268-3759">At least one of the following is true:</span></span>
    - <span data-ttu-id="48268-3760">Ein Schlüsselwort aus Keyword_itin wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3760">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="48268-3761">Die Funktion Func_us_address findet eine Adresse im richtigen Format.</span><span class="sxs-lookup"><span data-stu-id="48268-3761">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="48268-3762">Die Funktion Func_us_date findet ein Datum im richtigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="48268-3762">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="48268-3763">Ein Schlüsselwort aus Keyword_itin_collaborative wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3763">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="48268-3764">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3765">Die Funktion Func_unformatted_itin findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3765">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3766">Mindestens eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="48268-3766">At least one of the following is true:</span></span>
    - <span data-ttu-id="48268-3767">Ein Schlüsselwort aus Keyword_itin_collaborative wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3767">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="48268-3768">Die Funktion Func_us_address findet eine Adresse im richtigen Format.</span><span class="sxs-lookup"><span data-stu-id="48268-3768">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="48268-3769">Die Funktion Func_us_date findet ein Datum im richtigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="48268-3769">The function Func_us_date finds a date in the right date format.</span></span>

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3770">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3770">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="48268-3771">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="48268-3771">Keyword_itin</span></span>

- <span data-ttu-id="48268-3772">Steuer</span><span class="sxs-lookup"><span data-stu-id="48268-3772">taxpayer</span></span> 
- <span data-ttu-id="48268-3773">tax id</span><span class="sxs-lookup"><span data-stu-id="48268-3773">tax id</span></span> 
- <span data-ttu-id="48268-3774">tax identification</span><span class="sxs-lookup"><span data-stu-id="48268-3774">tax identification</span></span> 
- <span data-ttu-id="48268-3775">Itin</span><span class="sxs-lookup"><span data-stu-id="48268-3775">itin</span></span> 
- <span data-ttu-id="48268-3776">SSN</span><span class="sxs-lookup"><span data-stu-id="48268-3776">ssn</span></span> 
- <span data-ttu-id="48268-3777">Zinn</span><span class="sxs-lookup"><span data-stu-id="48268-3777">tin</span></span> 
- <span data-ttu-id="48268-3778">social security</span><span class="sxs-lookup"><span data-stu-id="48268-3778">social security</span></span> 
- <span data-ttu-id="48268-3779">tax payer</span><span class="sxs-lookup"><span data-stu-id="48268-3779">tax payer</span></span> 
- <span data-ttu-id="48268-3780">itins</span><span class="sxs-lookup"><span data-stu-id="48268-3780">itins</span></span> 
- <span data-ttu-id="48268-3781">per Taxi</span><span class="sxs-lookup"><span data-stu-id="48268-3781">taxid</span></span> 
- <span data-ttu-id="48268-3782">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="48268-3782">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="48268-3783">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="48268-3783">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="48268-3784">Lizenz</span><span class="sxs-lookup"><span data-stu-id="48268-3784">License</span></span> 
- <span data-ttu-id="48268-3785">DL</span><span class="sxs-lookup"><span data-stu-id="48268-3785">DL</span></span> 
- <span data-ttu-id="48268-3786">DOB</span><span class="sxs-lookup"><span data-stu-id="48268-3786">DOB</span></span> 
- <span data-ttu-id="48268-3787">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="48268-3787">Birthdate</span></span> 
- <span data-ttu-id="48268-3788">Geburtstag</span><span class="sxs-lookup"><span data-stu-id="48268-3788">Birthday</span></span> 
- <span data-ttu-id="48268-3789">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="48268-3789">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="48268-3790">US-Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="48268-3790">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="48268-3791">Format</span><span class="sxs-lookup"><span data-stu-id="48268-3791">Format</span></span>

<span data-ttu-id="48268-3792">9 Ziffern in formatiertem oder unformatiertem Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3792">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="48268-3793">Wenn ein SSN vor Mitte 2011 ausgegeben wird, weist es eine starke Formatierung auf, bei der bestimmte Teile der Zahl in bestimmte Bereiche fallen müssen, um gültig zu sein (aber keine Prüfsumme).</span><span class="sxs-lookup"><span data-stu-id="48268-3793">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="48268-3794">Muster</span><span class="sxs-lookup"><span data-stu-id="48268-3794">Pattern</span></span>

<span data-ttu-id="48268-3795">Vier Funktionen suchen nach Sozialversicherungsnummern in vier verschiedenen Mustern:</span><span class="sxs-lookup"><span data-stu-id="48268-3795">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="48268-3796">Func_ssn findet Sozialversicherungsnummern mit starker Formatierung vor 2011, die mit Bindestrichen oder Leerzeichen formatiert sind (DDD-DD-dddd oder DDD DD dddd)</span><span class="sxs-lookup"><span data-stu-id="48268-3796">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="48268-3797">Func_unformatted_ssn findet Sozialversicherungsnummern mit starker Formatierung vor 2011, die als neun aufeinanderfolgende Ziffern (ddddddddd) unformatiert sind.</span><span class="sxs-lookup"><span data-stu-id="48268-3797">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="48268-3798">Func_randomized_formatted_ssn findet Post-2011-Sozialversicherungsnummern, die mit Bindestrichen oder Leerzeichen formatiert sind (DDD-DD-dddd oder DDD DD dddd)</span><span class="sxs-lookup"><span data-stu-id="48268-3798">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="48268-3799">Func_randomized_unformatted_ssn findet Post-2011 Sozialversicherungsnummern, die als neun aufeinanderfolgende Ziffern (ddddddddd) unformatiert sind.</span><span class="sxs-lookup"><span data-stu-id="48268-3799">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="48268-3800">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="48268-3800">Checksum</span></span>

<span data-ttu-id="48268-3801">Nein</span><span class="sxs-lookup"><span data-stu-id="48268-3801">No</span></span>


### <a name="definition"></a><span data-ttu-id="48268-3802">Definition</span><span class="sxs-lookup"><span data-stu-id="48268-3802">Definition</span></span>

<span data-ttu-id="48268-3803">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3803">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3804">Die Funktion Func_ssn findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3804">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3805">Ein Schlüsselwort aus Keyword_ssn wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3805">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="48268-3806">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3807">Die Funktion Func_unformatted_ssn sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48268-3807">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3808">Ein Schlüsselwort aus Keyword_ssn wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3808">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="48268-3809">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3809">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3810">Die Funktion Func_randomized_formatted_ssn findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3810">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3811">Ein Schlüsselwort aus Keyword_ssn wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3811">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="48268-3812">Eine DLP-Richtlinie ist zu 55 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="48268-3812">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="48268-3813">Die Funktion Func_randomized_unformatted_ssn findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48268-3813">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="48268-3814">Ein Schlüsselwort aus Keyword_ssn wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="48268-3814">A keyword from Keyword_ssn is found.</span></span>


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a><span data-ttu-id="48268-3815">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48268-3815">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="48268-3816">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="48268-3816">Keyword_ssn</span></span>

- <span data-ttu-id="48268-3817">Social Security</span><span class="sxs-lookup"><span data-stu-id="48268-3817">Social Security</span></span> 
- <span data-ttu-id="48268-3818">Social Security#</span><span class="sxs-lookup"><span data-stu-id="48268-3818">Social Security#</span></span> 
- <span data-ttu-id="48268-3819">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="48268-3819">Soc Sec</span></span> 
- <span data-ttu-id="48268-3820">SSN</span><span class="sxs-lookup"><span data-stu-id="48268-3820">SSN</span></span> 
- <span data-ttu-id="48268-3821">Sozialversicherungsnummern</span><span class="sxs-lookup"><span data-stu-id="48268-3821">SSNS</span></span> 
- <span data-ttu-id="48268-3822">SSN #</span><span class="sxs-lookup"><span data-stu-id="48268-3822">SSN#</span></span> 
- <span data-ttu-id="48268-3823">SS #</span><span class="sxs-lookup"><span data-stu-id="48268-3823">SS#</span></span> 
- <span data-ttu-id="48268-3824">SSID</span><span class="sxs-lookup"><span data-stu-id="48268-3824">SSID</span></span> 
   
