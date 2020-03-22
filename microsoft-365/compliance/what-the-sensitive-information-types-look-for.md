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
ms.openlocfilehash: bd74551b7e8b2d659724a1222e115a479db76ec8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894301"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="2e5c0-104">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-104">What the sensitive information types look for</span></span>

<span data-ttu-id="2e5c0-105">Die Verhinderung von Datenverlust (Data Loss &amp; Prevention, DLP) im Office 365 Security Compliance Center umfasst viele Arten von vertraulichen Informationen, die Sie in ihren DLP-Richtlinien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="2e5c0-106">Dieses Thema enthält eine Liste aller dieser vertraulichen Informationstypen und zeigt, was eine DLP-Richtlinie sucht, wenn sie den jeweiligen Typen erkennt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="2e5c0-107">Ein vertraulicher Informationstyp wird durch ein Muster definiert, das durch einen regulären Ausdruck oder eine Funktion identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="2e5c0-108">Darüber hinaus können auch belegende Hinweise wie Schlüsselwörter oder Prüfsummen zum Identifizieren eines Typs vertraulicher Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="2e5c0-109">Beim Auswertungsprozess können auch die Zuverlässigkeitsstufe und die Näherung herangezogen werden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="2e5c0-110">ABA Routing Number (US-Bankleitzahl)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-111">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-111">Format</span></span>

<span data-ttu-id="2e5c0-112">9 Ziffern in formatiertem oder unformatiertem Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-113">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-113">Pattern</span></span>

<span data-ttu-id="2e5c0-114">Formatiert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-114">Formatted:</span></span>
- <span data-ttu-id="2e5c0-115">Vier Ziffern, beginnend mit 0, 1, 2, 3, 6, 7 oder 8</span><span class="sxs-lookup"><span data-stu-id="2e5c0-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="2e5c0-116">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-116">A hyphen</span></span>
- <span data-ttu-id="2e5c0-117">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-117">Four digits</span></span>
- <span data-ttu-id="2e5c0-118">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-118">A hyphen</span></span>
- <span data-ttu-id="2e5c0-119">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-119">A digit</span></span>

<span data-ttu-id="2e5c0-120">Unformatiert: 9 aufeinanderfolgende Ziffern, beginnend mit 0, 1, 2, 3, 6, 7 oder 8</span><span class="sxs-lookup"><span data-stu-id="2e5c0-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="2e5c0-121">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-121">Checksum</span></span>

<span data-ttu-id="2e5c0-122">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-123">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-123">Definition</span></span>

<span data-ttu-id="2e5c0-124">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-125">Die Funktion Func_aba_routing findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-126">Ein Schlüsselwort aus Keyword_ABA_Routing wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="2e5c0-127">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="2e5c0-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="2e5c0-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="2e5c0-129">ABA</span><span class="sxs-lookup"><span data-stu-id="2e5c0-129">aba</span></span>
- <span data-ttu-id="2e5c0-130">aba #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-130">aba #</span></span>
- <span data-ttu-id="2e5c0-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-131">aba routing #</span></span>
- <span data-ttu-id="2e5c0-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-132">aba routing number</span></span>
- <span data-ttu-id="2e5c0-133">ABA #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-133">aba#</span></span>
- <span data-ttu-id="2e5c0-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-134">abarouting#</span></span>
- <span data-ttu-id="2e5c0-135">aba number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-135">aba number</span></span>
- <span data-ttu-id="2e5c0-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-136">abaroutingnumber</span></span>
- <span data-ttu-id="2e5c0-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-137">american bank association routing #</span></span>
- <span data-ttu-id="2e5c0-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-138">american bank association routing number</span></span>
- <span data-ttu-id="2e5c0-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="2e5c0-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="2e5c0-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-141">bank routing number</span></span>
- <span data-ttu-id="2e5c0-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-142">bankrouting#</span></span>
- <span data-ttu-id="2e5c0-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-143">bankroutingnumber</span></span>
- <span data-ttu-id="2e5c0-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-144">routing transit number</span></span>
- <span data-ttu-id="2e5c0-145">RTN</span><span class="sxs-lookup"><span data-stu-id="2e5c0-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="2e5c0-146">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-147">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-147">Format</span></span>

<span data-ttu-id="2e5c0-148">Acht Ziffern, durch Punkte getrennt</span><span class="sxs-lookup"><span data-stu-id="2e5c0-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-149">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-149">Pattern</span></span>

<span data-ttu-id="2e5c0-150">Acht Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-150">Eight digits:</span></span>
- <span data-ttu-id="2e5c0-151">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-151">Two digits</span></span>
- <span data-ttu-id="2e5c0-152">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-152">A period</span></span>
- <span data-ttu-id="2e5c0-153">Drei Ziffern </span><span class="sxs-lookup"><span data-stu-id="2e5c0-153">Three digits</span></span>
- <span data-ttu-id="2e5c0-154">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-154">A period</span></span>
- <span data-ttu-id="2e5c0-155">Drei Ziffern </span><span class="sxs-lookup"><span data-stu-id="2e5c0-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-156">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-156">Checksum</span></span>

<span data-ttu-id="2e5c0-157">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-158">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-158">Definition</span></span>

<span data-ttu-id="2e5c0-159">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-160">Der reguläre Ausdruck Regex_argentina_national_id findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-161">Ein Schlüsselwort aus Keyword_argentina_national_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-162">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="2e5c0-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="2e5c0-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="2e5c0-165">Identität</span><span class="sxs-lookup"><span data-stu-id="2e5c0-165">Identity</span></span> 
- <span data-ttu-id="2e5c0-166">Identification National Identity Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="2e5c0-167">DNI</span><span class="sxs-lookup"><span data-stu-id="2e5c0-167">DNI</span></span> 
- <span data-ttu-id="2e5c0-168">Nic-nationales Personenregister</span><span class="sxs-lookup"><span data-stu-id="2e5c0-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="2e5c0-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="2e5c0-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="2e5c0-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="2e5c0-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="2e5c0-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="2e5c0-171">Identidad</span></span> 
- <span data-ttu-id="2e5c0-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="2e5c0-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="2e5c0-173">Australische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-174">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-174">Format</span></span>

<span data-ttu-id="2e5c0-175">6-10 Stellen mit oder ohne Bankfilialnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-176">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-176">Pattern</span></span>

<span data-ttu-id="2e5c0-177">Kontonummer hat 6-10 Stellen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="2e5c0-178">Australische Bankleitzahl:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="2e5c0-179">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-179">Three digits</span></span> 
- <span data-ttu-id="2e5c0-180">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-180">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-181">Drei Stellen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-182">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-182">Checksum</span></span>

<span data-ttu-id="2e5c0-183">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-184">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-184">Definition</span></span>

<span data-ttu-id="2e5c0-185">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-186">Der reguläre Ausdruck Regex_australia_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="2e5c0-187">Ein Schlüsselwort aus Keyword_australia_bank_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="2e5c0-188">Der reguläre Ausdruck Regex_australia_bank_account_number_bsb findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="2e5c0-189">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-190">Der reguläre Ausdruck Regex_australia_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="2e5c0-191">Ein Schlüsselwort aus Keyword_australia_bank_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-192">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="2e5c0-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="2e5c0-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="2e5c0-194">swift bank code</span></span>
- <span data-ttu-id="2e5c0-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="2e5c0-195">correspondent bank</span></span>
- <span data-ttu-id="2e5c0-196">base currency</span><span class="sxs-lookup"><span data-stu-id="2e5c0-196">base currency</span></span>
- <span data-ttu-id="2e5c0-197">usa account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-197">usa account</span></span>
- <span data-ttu-id="2e5c0-198">holder address</span><span class="sxs-lookup"><span data-stu-id="2e5c0-198">holder address</span></span>
- <span data-ttu-id="2e5c0-199">bank address</span><span class="sxs-lookup"><span data-stu-id="2e5c0-199">bank address</span></span>
- <span data-ttu-id="2e5c0-200">information account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-200">information account</span></span>
- <span data-ttu-id="2e5c0-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-201">fund transfers</span></span>
- <span data-ttu-id="2e5c0-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="2e5c0-202">bank charges</span></span>
- <span data-ttu-id="2e5c0-203">bank details</span><span class="sxs-lookup"><span data-stu-id="2e5c0-203">bank details</span></span>
- <span data-ttu-id="2e5c0-204">banking information</span><span class="sxs-lookup"><span data-stu-id="2e5c0-204">banking information</span></span>
- <span data-ttu-id="2e5c0-205">full names</span><span class="sxs-lookup"><span data-stu-id="2e5c0-205">full names</span></span>
- <span data-ttu-id="2e5c0-206">IAEO</span><span class="sxs-lookup"><span data-stu-id="2e5c0-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="2e5c0-207">Australische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-208">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-208">Format</span></span>

<span data-ttu-id="2e5c0-209">Neun Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-210">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-210">Pattern</span></span>

<span data-ttu-id="2e5c0-211">Neun Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="2e5c0-212">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-213">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-213">Two digits</span></span> 
- <span data-ttu-id="2e5c0-214">Fünf Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="2e5c0-215">ODER</span><span class="sxs-lookup"><span data-stu-id="2e5c0-215">OR</span></span>

- <span data-ttu-id="2e5c0-216">1-2 optionale Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-217">4 bis 9 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-217">4-9 digits</span></span>

<span data-ttu-id="2e5c0-218">ODER</span><span class="sxs-lookup"><span data-stu-id="2e5c0-218">OR</span></span>

- <span data-ttu-id="2e5c0-219">Neun Ziffern oder Buchstaben (Groß-/Kleinschreibung irrelevant)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-220">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-220">Checksum</span></span>

<span data-ttu-id="2e5c0-221">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-222">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-222">Definition</span></span>

<span data-ttu-id="2e5c0-223">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-224">Der reguläre Ausdruck Regex_australia_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-225">Ein Schlüsselwort aus Keyword_australia_drivers_license_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="2e5c0-226">Es wurde kein Schlüsselwort aus Keyword_australia_drivers_license_number_exclusions gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-227">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="2e5c0-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="2e5c0-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="2e5c0-229">international driving permits</span></span>
- <span data-ttu-id="2e5c0-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="2e5c0-230">australian automobile association</span></span>
- <span data-ttu-id="2e5c0-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-231">international driving permit</span></span>
- <span data-ttu-id="2e5c0-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-232">DriverLicence</span></span>
- <span data-ttu-id="2e5c0-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-233">DriverLicences</span></span>
- <span data-ttu-id="2e5c0-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-234">Driver Lic</span></span>
- <span data-ttu-id="2e5c0-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-235">Driver Licence</span></span>
- <span data-ttu-id="2e5c0-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-236">Driver Licences</span></span>
- <span data-ttu-id="2e5c0-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-237">DriversLic</span></span>
- <span data-ttu-id="2e5c0-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-238">DriversLicence</span></span>
- <span data-ttu-id="2e5c0-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-239">DriversLicences</span></span>
- <span data-ttu-id="2e5c0-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-240">Drivers Lic</span></span>
- <span data-ttu-id="2e5c0-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-241">Drivers Lics</span></span>
- <span data-ttu-id="2e5c0-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-242">Drivers Licence</span></span>
- <span data-ttu-id="2e5c0-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-243">Drivers Licences</span></span>
- <span data-ttu-id="2e5c0-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-244">Driver'Lic</span></span>
- <span data-ttu-id="2e5c0-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-245">Driver'Lics</span></span>
- <span data-ttu-id="2e5c0-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-246">Driver'Licence</span></span>
- <span data-ttu-id="2e5c0-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-247">Driver'Licences</span></span>
- <span data-ttu-id="2e5c0-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-248">Driver' Lic</span></span>
- <span data-ttu-id="2e5c0-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-249">Driver' Lics</span></span>
- <span data-ttu-id="2e5c0-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-250">Driver' Licence</span></span>
- <span data-ttu-id="2e5c0-251">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-251">Driver' Licences</span></span>
- <span data-ttu-id="2e5c0-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-252">Driver'sLic</span></span>
- <span data-ttu-id="2e5c0-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-253">Driver'sLics</span></span>
- <span data-ttu-id="2e5c0-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-254">Driver'sLicence</span></span>
- <span data-ttu-id="2e5c0-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-255">Driver'sLicences</span></span>
- <span data-ttu-id="2e5c0-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-256">Driver's Lic</span></span>
- <span data-ttu-id="2e5c0-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-257">Driver's Lics</span></span>
- <span data-ttu-id="2e5c0-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-258">Driver's Licence</span></span>
- <span data-ttu-id="2e5c0-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-259">Driver's Licences</span></span>
- <span data-ttu-id="2e5c0-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-260">DriverLic#</span></span>
- <span data-ttu-id="2e5c0-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-261">DriverLics#</span></span>
- <span data-ttu-id="2e5c0-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-262">DriverLicence#</span></span>
- <span data-ttu-id="2e5c0-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-263">DriverLicences#</span></span>
- <span data-ttu-id="2e5c0-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-264">Driver Lic#</span></span>
- <span data-ttu-id="2e5c0-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-265">Driver Lics#</span></span>
- <span data-ttu-id="2e5c0-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-266">Driver Licence#</span></span>
- <span data-ttu-id="2e5c0-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-267">Driver Licences#</span></span>
- <span data-ttu-id="2e5c0-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-268">DriversLic#</span></span>
- <span data-ttu-id="2e5c0-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-269">DriversLics#</span></span>
- <span data-ttu-id="2e5c0-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-270">DriversLicence#</span></span>
- <span data-ttu-id="2e5c0-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-271">DriversLicences#</span></span>
- <span data-ttu-id="2e5c0-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-272">Drivers Lic#</span></span>
- <span data-ttu-id="2e5c0-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-273">Drivers Lics#</span></span>
- <span data-ttu-id="2e5c0-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-274">Drivers Licence#</span></span>
- <span data-ttu-id="2e5c0-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-275">Drivers Licences#</span></span>
- <span data-ttu-id="2e5c0-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-276">Driver'Lic#</span></span>
- <span data-ttu-id="2e5c0-277">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-277">Driver'Lics#</span></span>
- <span data-ttu-id="2e5c0-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-278">Driver'Licence#</span></span>
- <span data-ttu-id="2e5c0-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-279">Driver'Licences#</span></span>
- <span data-ttu-id="2e5c0-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-280">Driver' Lic#</span></span>
- <span data-ttu-id="2e5c0-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-281">Driver' Lics#</span></span>
- <span data-ttu-id="2e5c0-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-282">Driver' Licence#</span></span>
- <span data-ttu-id="2e5c0-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-283">Driver' Licences#</span></span>
- <span data-ttu-id="2e5c0-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-284">Driver'sLic#</span></span>
- <span data-ttu-id="2e5c0-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-285">Driver'sLics#</span></span>
- <span data-ttu-id="2e5c0-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-286">Driver'sLicence#</span></span>
- <span data-ttu-id="2e5c0-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-287">Driver'sLicences#</span></span>
- <span data-ttu-id="2e5c0-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-288">Driver's Lic#</span></span>
- <span data-ttu-id="2e5c0-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-289">Driver's Lics#</span></span>
- <span data-ttu-id="2e5c0-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-290">Driver's Licence#</span></span>
- <span data-ttu-id="2e5c0-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="2e5c0-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="2e5c0-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="2e5c0-293">aaa</span><span class="sxs-lookup"><span data-stu-id="2e5c0-293">aaa</span></span>
- <span data-ttu-id="2e5c0-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="2e5c0-294">DriverLicense</span></span>
- <span data-ttu-id="2e5c0-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-295">DriverLicenses</span></span>
- <span data-ttu-id="2e5c0-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-296">Driver License</span></span>
- <span data-ttu-id="2e5c0-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-297">Driver Licenses</span></span>
- <span data-ttu-id="2e5c0-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="2e5c0-298">DriversLicense</span></span>
- <span data-ttu-id="2e5c0-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-299">DriversLicenses</span></span>
- <span data-ttu-id="2e5c0-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-300">Drivers License</span></span>
- <span data-ttu-id="2e5c0-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-301">Drivers Licenses</span></span>
- <span data-ttu-id="2e5c0-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-302">Driver'License</span></span>
- <span data-ttu-id="2e5c0-303">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-303">Driver'Licenses</span></span>
- <span data-ttu-id="2e5c0-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-304">Driver' License</span></span>
- <span data-ttu-id="2e5c0-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-305">Driver' Licenses</span></span>
- <span data-ttu-id="2e5c0-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="2e5c0-306">Driver'sLicense</span></span>
- <span data-ttu-id="2e5c0-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-307">Driver'sLicenses</span></span>
- <span data-ttu-id="2e5c0-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-308">Driver's License</span></span>
- <span data-ttu-id="2e5c0-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-309">Driver's Licenses</span></span>
- <span data-ttu-id="2e5c0-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-310">DriverLicense#</span></span>
- <span data-ttu-id="2e5c0-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-311">DriverLicenses#</span></span>
- <span data-ttu-id="2e5c0-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-312">Driver License#</span></span>
- <span data-ttu-id="2e5c0-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-313">Driver Licenses#</span></span>
- <span data-ttu-id="2e5c0-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-314">DriversLicense#</span></span>
- <span data-ttu-id="2e5c0-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-315">DriversLicenses#</span></span>
- <span data-ttu-id="2e5c0-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-316">Drivers License#</span></span>
- <span data-ttu-id="2e5c0-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-317">Drivers Licenses#</span></span>
- <span data-ttu-id="2e5c0-318">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-318">Driver'License#</span></span>
- <span data-ttu-id="2e5c0-319">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-319">Driver'Licenses#</span></span>
- <span data-ttu-id="2e5c0-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-320">Driver' License#</span></span>
- <span data-ttu-id="2e5c0-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-321">Driver' Licenses#</span></span>
- <span data-ttu-id="2e5c0-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-322">Driver'sLicense#</span></span>
- <span data-ttu-id="2e5c0-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="2e5c0-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-324">Driver's License#</span></span>
- <span data-ttu-id="2e5c0-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="2e5c0-326">Australische Medical Account-Nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-327">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-327">Format</span></span>

<span data-ttu-id="2e5c0-328">10-11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-329">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-329">Pattern</span></span>

<span data-ttu-id="2e5c0-330">10-11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-330">10-11 digits:</span></span>
- <span data-ttu-id="2e5c0-331">Erste Ziffer im Bereich von 2-6</span><span class="sxs-lookup"><span data-stu-id="2e5c0-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="2e5c0-332">Neunte Ziffer ist eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="2e5c0-333">Zehnte Ziffer ist die Ausgabeziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="2e5c0-334">Elfte Ziffer (optional) ist die Einzelziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-335">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-335">Checksum</span></span>

<span data-ttu-id="2e5c0-336">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-337">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-337">Definition</span></span>

<span data-ttu-id="2e5c0-338">Eine DLP-Richtlinie ist zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-339">Die Funktion Func_australian_medical_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-340">Ein Schlüsselwort aus Keyword_Australia_Medical_Account_Number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="2e5c0-341">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-341">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-342">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-343">Die Funktion Func_australian_medical_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-344">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-345">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="2e5c0-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="2e5c0-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="2e5c0-347">bank account details</span></span>
- <span data-ttu-id="2e5c0-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="2e5c0-348">medicare payments</span></span>
- <span data-ttu-id="2e5c0-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-349">mortgage account</span></span>
- <span data-ttu-id="2e5c0-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="2e5c0-350">bank payments</span></span>
- <span data-ttu-id="2e5c0-351">information branch</span><span class="sxs-lookup"><span data-stu-id="2e5c0-351">information branch</span></span>
- <span data-ttu-id="2e5c0-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="2e5c0-352">credit card loan</span></span>
- <span data-ttu-id="2e5c0-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="2e5c0-353">department of human services</span></span>
- <span data-ttu-id="2e5c0-354">local service</span><span class="sxs-lookup"><span data-stu-id="2e5c0-354">local service</span></span>
- <span data-ttu-id="2e5c0-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="2e5c0-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="2e5c0-356">Australische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-357">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-357">Format</span></span>

<span data-ttu-id="2e5c0-358">Ein Buchstabe gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-359">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-359">Pattern</span></span>

<span data-ttu-id="2e5c0-360">Ein Buchstabe (Groß-/Kleinschreibung irrelevant) gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-361">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-361">Checksum</span></span>

<span data-ttu-id="2e5c0-362">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-363">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-363">Definition</span></span>

<span data-ttu-id="2e5c0-364">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-365">Der reguläre Ausdruck Regex_australia_passport_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-366">Ein Schlüsselwort aus Keyword_passport oder Keyword_australia_passport_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-367">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="2e5c0-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-368">Keyword_passport</span></span>

- <span data-ttu-id="2e5c0-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-369">Passport Number</span></span>
- <span data-ttu-id="2e5c0-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="2e5c0-370">Passport No</span></span>
- <span data-ttu-id="2e5c0-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-371">Passport #</span></span>
- <span data-ttu-id="2e5c0-372">Pass #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-372">Passport#</span></span>
- <span data-ttu-id="2e5c0-373">Passport-Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-373">PassportID</span></span>
- <span data-ttu-id="2e5c0-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="2e5c0-374">Passportno</span></span>
- <span data-ttu-id="2e5c0-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-375">passportnumber</span></span>
- <span data-ttu-id="2e5c0-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="2e5c0-376">パスポート</span></span>
- <span data-ttu-id="2e5c0-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-377">パスポート番号</span></span>
- <span data-ttu-id="2e5c0-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-378">パスポートのNum</span></span>
- <span data-ttu-id="2e5c0-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-379">パスポート ＃</span></span> 
- <span data-ttu-id="2e5c0-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-380">Numéro de passeport</span></span>
- <span data-ttu-id="2e5c0-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2e5c0-381">Passeport n °</span></span>
- <span data-ttu-id="2e5c0-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="2e5c0-382">Passeport Non</span></span>
- <span data-ttu-id="2e5c0-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-383">Passeport #</span></span>
- <span data-ttu-id="2e5c0-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-384">Passeport#</span></span>
- <span data-ttu-id="2e5c0-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2e5c0-385">PasseportNon</span></span>
- <span data-ttu-id="2e5c0-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2e5c0-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="2e5c0-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="2e5c0-388">Pass</span><span class="sxs-lookup"><span data-stu-id="2e5c0-388">passport</span></span>
- <span data-ttu-id="2e5c0-389">passport details</span><span class="sxs-lookup"><span data-stu-id="2e5c0-389">passport details</span></span>
- <span data-ttu-id="2e5c0-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="2e5c0-390">immigration and citizenship</span></span>
- <span data-ttu-id="2e5c0-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="2e5c0-391">commonwealth of australia</span></span>
- <span data-ttu-id="2e5c0-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="2e5c0-392">department of immigration</span></span>
- <span data-ttu-id="2e5c0-393">residential address</span><span class="sxs-lookup"><span data-stu-id="2e5c0-393">residential address</span></span>
- <span data-ttu-id="2e5c0-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="2e5c0-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="2e5c0-395">Visa</span><span class="sxs-lookup"><span data-stu-id="2e5c0-395">visa</span></span>
- <span data-ttu-id="2e5c0-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-396">national identity card</span></span>
- <span data-ttu-id="2e5c0-397">passport number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-397">passport number</span></span>
- <span data-ttu-id="2e5c0-398">travel document</span><span class="sxs-lookup"><span data-stu-id="2e5c0-398">travel document</span></span>
- <span data-ttu-id="2e5c0-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="2e5c0-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="2e5c0-400">Australische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-401">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-401">Format</span></span>

<span data-ttu-id="2e5c0-402">8-9 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-403">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-403">Pattern</span></span>

<span data-ttu-id="2e5c0-404">8 bis 9 Ziffern, die in der Regel wie folgt mit Leerzeichen dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="2e5c0-405">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-405">Three digits</span></span> 
- <span data-ttu-id="2e5c0-406">Ein optionales Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-406">An optional space</span></span> 
- <span data-ttu-id="2e5c0-407">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-407">Three digits</span></span> 
- <span data-ttu-id="2e5c0-408">Ein optionales Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-408">An optional space</span></span> 
- <span data-ttu-id="2e5c0-409">2 bis 3 Ziffern, wobei die letzte Ziffer eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="2e5c0-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-410">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-410">Checksum</span></span>

<span data-ttu-id="2e5c0-411">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-412">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-412">Definition</span></span>

<span data-ttu-id="2e5c0-413">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-414">Die Funktion Func_australian_tax_file_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-415">Es wurde kein Schlüsselwort aus Keyword_Australia_Tax_File_Number oder Keyword_number_exclusions gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="2e5c0-416">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-417">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="2e5c0-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="2e5c0-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-419">australian business number</span></span>
- <span data-ttu-id="2e5c0-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="2e5c0-420">marginal tax rate</span></span>
- <span data-ttu-id="2e5c0-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="2e5c0-421">medicare levy</span></span>
- <span data-ttu-id="2e5c0-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-422">portfolio number</span></span>
- <span data-ttu-id="2e5c0-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="2e5c0-423">service veterans</span></span>
- <span data-ttu-id="2e5c0-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="2e5c0-424">withholding tax</span></span>
- <span data-ttu-id="2e5c0-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="2e5c0-425">individual tax return</span></span>
- <span data-ttu-id="2e5c0-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="2e5c0-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="2e5c0-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="2e5c0-428">00000000</span><span class="sxs-lookup"><span data-stu-id="2e5c0-428">00000000</span></span>
- <span data-ttu-id="2e5c0-429">11111111</span><span class="sxs-lookup"><span data-stu-id="2e5c0-429">11111111</span></span>
- <span data-ttu-id="2e5c0-430">22222222</span><span class="sxs-lookup"><span data-stu-id="2e5c0-430">22222222</span></span>
- <span data-ttu-id="2e5c0-431">33333333</span><span class="sxs-lookup"><span data-stu-id="2e5c0-431">33333333</span></span>
- <span data-ttu-id="2e5c0-432">44444444</span><span class="sxs-lookup"><span data-stu-id="2e5c0-432">44444444</span></span>
- <span data-ttu-id="2e5c0-433">55555555</span><span class="sxs-lookup"><span data-stu-id="2e5c0-433">55555555</span></span>
- <span data-ttu-id="2e5c0-434">66666666</span><span class="sxs-lookup"><span data-stu-id="2e5c0-434">66666666</span></span>
- <span data-ttu-id="2e5c0-435">77777777</span><span class="sxs-lookup"><span data-stu-id="2e5c0-435">77777777</span></span>
- <span data-ttu-id="2e5c0-436">88888888</span><span class="sxs-lookup"><span data-stu-id="2e5c0-436">88888888</span></span>
- <span data-ttu-id="2e5c0-437">99999999</span><span class="sxs-lookup"><span data-stu-id="2e5c0-437">99999999</span></span>
- <span data-ttu-id="2e5c0-438">000000000</span><span class="sxs-lookup"><span data-stu-id="2e5c0-438">000000000</span></span>
- <span data-ttu-id="2e5c0-439">111111111</span><span class="sxs-lookup"><span data-stu-id="2e5c0-439">111111111</span></span>
- <span data-ttu-id="2e5c0-440">222222222</span><span class="sxs-lookup"><span data-stu-id="2e5c0-440">222222222</span></span>
- <span data-ttu-id="2e5c0-441">333333333</span><span class="sxs-lookup"><span data-stu-id="2e5c0-441">333333333</span></span>
- <span data-ttu-id="2e5c0-442">444444444</span><span class="sxs-lookup"><span data-stu-id="2e5c0-442">444444444</span></span>
- <span data-ttu-id="2e5c0-443">555555555</span><span class="sxs-lookup"><span data-stu-id="2e5c0-443">555555555</span></span>
- <span data-ttu-id="2e5c0-444">666666666</span><span class="sxs-lookup"><span data-stu-id="2e5c0-444">666666666</span></span>
- <span data-ttu-id="2e5c0-445">777777777</span><span class="sxs-lookup"><span data-stu-id="2e5c0-445">777777777</span></span>
- <span data-ttu-id="2e5c0-446">888888888</span><span class="sxs-lookup"><span data-stu-id="2e5c0-446">888888888</span></span>
- <span data-ttu-id="2e5c0-447">999999999</span><span class="sxs-lookup"><span data-stu-id="2e5c0-447">999999999</span></span>
- <span data-ttu-id="2e5c0-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="2e5c0-448">0000000000</span></span>
- <span data-ttu-id="2e5c0-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="2e5c0-449">1111111111</span></span>
- <span data-ttu-id="2e5c0-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="2e5c0-450">2222222222</span></span>
- <span data-ttu-id="2e5c0-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="2e5c0-451">3333333333</span></span>
- <span data-ttu-id="2e5c0-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="2e5c0-452">4444444444</span></span>
- <span data-ttu-id="2e5c0-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="2e5c0-453">5555555555</span></span>
- <span data-ttu-id="2e5c0-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="2e5c0-454">6666666666</span></span>
- <span data-ttu-id="2e5c0-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="2e5c0-455">7777777777</span></span>
- <span data-ttu-id="2e5c0-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="2e5c0-456">8888888888</span></span>
- <span data-ttu-id="2e5c0-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="2e5c0-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="2e5c0-458">Azure DocumentDB-Authentifizierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="2e5c0-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-459">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-459">Format</span></span>

<span data-ttu-id="2e5c0-460">Die Zeichenfolge "DocumentDb" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-461">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-461">Pattern</span></span>

- <span data-ttu-id="2e5c0-462">Die Zeichenfolge "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="2e5c0-463">Eine beliebige Kombination von zwischen 3-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2e5c0-464">Ein größer als-Symbol (>), ein Gleichheitszeichen (=), ein Anführungszeichen (") oder ein Apostroph (')</span><span class="sxs-lookup"><span data-stu-id="2e5c0-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="2e5c0-465">Eine beliebige Kombination von 86 unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2e5c0-466">Zwei Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-467">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-467">Checksum</span></span>

<span data-ttu-id="2e5c0-468">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-469">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-469">Definition</span></span>

<span data-ttu-id="2e5c0-470">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-471">Der reguläre Ausdruck CEP_Regex_AzureDocumentDBAuthKey findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-472">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-473">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="2e5c0-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2e5c0-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2e5c0-475">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2e5c0-476">contoso</span><span class="sxs-lookup"><span data-stu-id="2e5c0-476">contoso</span></span>
- <span data-ttu-id="2e5c0-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2e5c0-477">fabrikam</span></span>
- <span data-ttu-id="2e5c0-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-478">northwind</span></span>
- <span data-ttu-id="2e5c0-479">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-479">sandbox</span></span>
- <span data-ttu-id="2e5c0-480">OneBox</span><span class="sxs-lookup"><span data-stu-id="2e5c0-480">onebox</span></span>
- <span data-ttu-id="2e5c0-481">localhost</span><span class="sxs-lookup"><span data-stu-id="2e5c0-481">localhost</span></span>
- <span data-ttu-id="2e5c0-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2e5c0-482">127.0.0.1</span></span>
- <span data-ttu-id="2e5c0-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-484">com</span><span class="sxs-lookup"><span data-stu-id="2e5c0-484">com</span></span>
- <span data-ttu-id="2e5c0-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-486">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="2e5c0-487">Azure IaaS-Datenbankverbindungszeichenfolge und Azure SQL-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e5c0-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-488">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-488">Format</span></span>

<span data-ttu-id="2e5c0-489">Die Zeichenfolge "Server", "Server" oder "Datenquelle", gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten, einschließlich der Zeichenfolge "cloudapp. Azure" aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-490">com "oder" cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-491">NET "oder" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-492">NET "und die Zeichenfolge" Password "oder" Password "oder" pwd ".</span><span class="sxs-lookup"><span data-stu-id="2e5c0-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-493">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-493">Pattern</span></span>

- <span data-ttu-id="2e5c0-494">Die Zeichenfolge "Server", "Server" oder "Datenquelle"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="2e5c0-495">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-496">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-496">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-497">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-498">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2e5c0-499">Die Zeichenfolge "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-500">com "," cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-501">NET "oder" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-502">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-502">net"</span></span>
- <span data-ttu-id="2e5c0-503">Eine beliebige Kombination von zwischen 1-300 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2e5c0-504">Die Zeichenfolge "Password", "Password" oder "pwd"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="2e5c0-505">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-506">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-506">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-507">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-508">Ein oder mehrere Zeichen, bei denen es sich nicht um ein Semikolon handelt (;), Anführungszeichen (") oder Apostroph (')</span><span class="sxs-lookup"><span data-stu-id="2e5c0-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="2e5c0-509">Ein Semikolon (;), Anführungszeichen (") oder Apostroph (')</span><span class="sxs-lookup"><span data-stu-id="2e5c0-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-510">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-510">Checksum</span></span>

<span data-ttu-id="2e5c0-511">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-512">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-512">Definition</span></span>

<span data-ttu-id="2e5c0-513">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-514">Der reguläre Ausdruck CEP_Regex_AzureConnectionString findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-515">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-516">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="2e5c0-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2e5c0-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2e5c0-518">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2e5c0-519">contoso</span><span class="sxs-lookup"><span data-stu-id="2e5c0-519">contoso</span></span>
- <span data-ttu-id="2e5c0-520">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2e5c0-520">fabrikam</span></span>
- <span data-ttu-id="2e5c0-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-521">northwind</span></span>
- <span data-ttu-id="2e5c0-522">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-522">sandbox</span></span>
- <span data-ttu-id="2e5c0-523">OneBox</span><span class="sxs-lookup"><span data-stu-id="2e5c0-523">onebox</span></span>
- <span data-ttu-id="2e5c0-524">localhost</span><span class="sxs-lookup"><span data-stu-id="2e5c0-524">localhost</span></span>
- <span data-ttu-id="2e5c0-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2e5c0-525">127.0.0.1</span></span>
- <span data-ttu-id="2e5c0-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-527">com</span><span class="sxs-lookup"><span data-stu-id="2e5c0-527">com</span></span>
- <span data-ttu-id="2e5c0-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-529">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="2e5c0-530">Azurey-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e5c0-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-531">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-531">Format</span></span>

<span data-ttu-id="2e5c0-532">Die Zeichenfolge "Hostname" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten beschrieben sind, einschließlich der Zeichenfolgen "Azure-Devices".</span><span class="sxs-lookup"><span data-stu-id="2e5c0-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-533">NET "und" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="2e5c0-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-534">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-534">Pattern</span></span>

- <span data-ttu-id="2e5c0-535">Die Zeichenfolge "Hostname"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-535">The string "HostName"</span></span>
- <span data-ttu-id="2e5c0-536">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-537">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-537">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-538">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-539">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2e5c0-540">Die Zeichenfolge "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-541">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-541">net"</span></span>
- <span data-ttu-id="2e5c0-542">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2e5c0-543">Die Zeichenfolge "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="2e5c0-544">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-545">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-545">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-546">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-547">Eine beliebige Kombination von 43 unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2e5c0-548">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-549">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-549">Checksum</span></span>

<span data-ttu-id="2e5c0-550">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-551">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-551">Definition</span></span>

<span data-ttu-id="2e5c0-552">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-553">Der reguläre Ausdruck CEP_Regex_AzureIoTConnectionString findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-554">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-555">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="2e5c0-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2e5c0-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2e5c0-557">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2e5c0-558">contoso</span><span class="sxs-lookup"><span data-stu-id="2e5c0-558">contoso</span></span>
- <span data-ttu-id="2e5c0-559">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2e5c0-559">fabrikam</span></span>
- <span data-ttu-id="2e5c0-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-560">northwind</span></span>
- <span data-ttu-id="2e5c0-561">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-561">sandbox</span></span>
- <span data-ttu-id="2e5c0-562">OneBox</span><span class="sxs-lookup"><span data-stu-id="2e5c0-562">onebox</span></span>
- <span data-ttu-id="2e5c0-563">localhost</span><span class="sxs-lookup"><span data-stu-id="2e5c0-563">localhost</span></span>
- <span data-ttu-id="2e5c0-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2e5c0-564">127.0.0.1</span></span>
- <span data-ttu-id="2e5c0-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-566">com</span><span class="sxs-lookup"><span data-stu-id="2e5c0-566">com</span></span>
- <span data-ttu-id="2e5c0-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-568">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="2e5c0-569">Kennwort für Azure-Veröffentlichungseinstellung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-570">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-570">Format</span></span>

<span data-ttu-id="2e5c0-571">Die Zeichenfolge "benutzerkwt =" gefolgt von einer alphanumerischen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-572">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-572">Pattern</span></span>

- <span data-ttu-id="2e5c0-573">Die Zeichenfolge "benutzerkwt ="</span><span class="sxs-lookup"><span data-stu-id="2e5c0-573">The string "userpwd="</span></span>
- <span data-ttu-id="2e5c0-574">Eine beliebige Kombination von 60 Kleinbuchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="2e5c0-575">Ein Anführungszeichen (")</span><span class="sxs-lookup"><span data-stu-id="2e5c0-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-576">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-576">Checksum</span></span>

<span data-ttu-id="2e5c0-577">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-578">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-578">Definition</span></span>

<span data-ttu-id="2e5c0-579">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-580">Der reguläre Ausdruck CEP_Regex_AzurePublishSettingPasswords findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-581">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="2e5c0-582">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="2e5c0-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2e5c0-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2e5c0-584">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2e5c0-585">contoso</span><span class="sxs-lookup"><span data-stu-id="2e5c0-585">contoso</span></span>
- <span data-ttu-id="2e5c0-586">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2e5c0-586">fabrikam</span></span>
- <span data-ttu-id="2e5c0-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-587">northwind</span></span>
- <span data-ttu-id="2e5c0-588">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-588">sandbox</span></span>
- <span data-ttu-id="2e5c0-589">OneBox</span><span class="sxs-lookup"><span data-stu-id="2e5c0-589">onebox</span></span>
- <span data-ttu-id="2e5c0-590">localhost</span><span class="sxs-lookup"><span data-stu-id="2e5c0-590">localhost</span></span>
- <span data-ttu-id="2e5c0-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2e5c0-591">127.0.0.1</span></span>
- <span data-ttu-id="2e5c0-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-593">com</span><span class="sxs-lookup"><span data-stu-id="2e5c0-593">com</span></span>
- <span data-ttu-id="2e5c0-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-595">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="2e5c0-596">Azure-Zeichenfolgen-Cache-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e5c0-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-597">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-597">Format</span></span>

<span data-ttu-id="2e5c0-598">Die Zeichenfolge "" Codestring. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-599">NET ", gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster dargestellt werden, einschließlich der Zeichenfolge" Password "oder" pwd ".</span><span class="sxs-lookup"><span data-stu-id="2e5c0-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-600">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-600">Pattern</span></span>

- <span data-ttu-id="2e5c0-601">Die Zeichenfolge "" Codestring. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-602">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-602">net"</span></span>
- <span data-ttu-id="2e5c0-603">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2e5c0-604">Die Zeichenfolge "Password" oder "pwd"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="2e5c0-605">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-606">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-606">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-607">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-608">Eine beliebige Kombination von 43 Zeichen mit unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2e5c0-609">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-610">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-610">Checksum</span></span>

<span data-ttu-id="2e5c0-611">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-612">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-612">Definition</span></span>

<span data-ttu-id="2e5c0-613">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-614">Der reguläre Ausdruck CEP_Regex_AzureRedisCacheConnectionString findet Inhalte, die mit dem Muster übereinstimmen..</span><span class="sxs-lookup"><span data-stu-id="2e5c0-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="2e5c0-615">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-616">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="2e5c0-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2e5c0-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2e5c0-618">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2e5c0-619">contoso</span><span class="sxs-lookup"><span data-stu-id="2e5c0-619">contoso</span></span>
- <span data-ttu-id="2e5c0-620">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2e5c0-620">fabrikam</span></span>
- <span data-ttu-id="2e5c0-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-621">northwind</span></span>
- <span data-ttu-id="2e5c0-622">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-622">sandbox</span></span>
- <span data-ttu-id="2e5c0-623">OneBox</span><span class="sxs-lookup"><span data-stu-id="2e5c0-623">onebox</span></span>
- <span data-ttu-id="2e5c0-624">localhost</span><span class="sxs-lookup"><span data-stu-id="2e5c0-624">localhost</span></span>
- <span data-ttu-id="2e5c0-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2e5c0-625">127.0.0.1</span></span>
- <span data-ttu-id="2e5c0-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-627">com</span><span class="sxs-lookup"><span data-stu-id="2e5c0-627">com</span></span>
- <span data-ttu-id="2e5c0-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-629">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="2e5c0-630">Azure-SAS</span><span class="sxs-lookup"><span data-stu-id="2e5c0-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-631">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-631">Format</span></span>

<span data-ttu-id="2e5c0-632">Die Zeichenfolge "SIG" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-633">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-633">Pattern</span></span>

- <span data-ttu-id="2e5c0-634">Die Zeichenfolge "SIG"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-634">The string "sig"</span></span>
- <span data-ttu-id="2e5c0-635">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-636">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-636">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-637">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-638">Eine beliebige Kombination von zwischen 43-53 Zeichen, die klein-oder Großbuchstaben, Ziffern oder das Prozentzeichen (%)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="2e5c0-639">Die Zeichenfolge "% 3D"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-639">The string "%3d"</span></span>
- <span data-ttu-id="2e5c0-640">Ein beliebiges Zeichen, das kein niedriger oder groß geschriebener Buchstabe, eine Ziffer oder ein Prozentzeichen ist (%)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-641">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-641">Checksum</span></span>

<span data-ttu-id="2e5c0-642">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-643">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-643">Definition</span></span>

<span data-ttu-id="2e5c0-644">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-645">Der reguläre Ausdruck CEP_Regex_AzureSAS findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="2e5c0-646">Azure Service Bus-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e5c0-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-647">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-647">Format</span></span>

<span data-ttu-id="2e5c0-648">Die Zeichenfolge "Endpoint" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten, einschließlich der Zeichenfolgen "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-649">NET "und" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="2e5c0-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-650">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-650">Pattern</span></span>

- <span data-ttu-id="2e5c0-651">Die Zeichenfolge "Endpoint"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-651">The string "EndPoint"</span></span>
- <span data-ttu-id="2e5c0-652">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-653">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-653">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-654">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-655">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2e5c0-656">Die Zeichenfolge "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-657">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-657">net"</span></span>
- <span data-ttu-id="2e5c0-658">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2e5c0-659">Die Zeichenfolge "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="2e5c0-660">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-661">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-661">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-662">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-663">Eine beliebige Kombination von 43 Zeichen mit unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2e5c0-664">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-665">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-665">Checksum</span></span>

<span data-ttu-id="2e5c0-666">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-667">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-667">Definition</span></span>

<span data-ttu-id="2e5c0-668">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-669">Der reguläre Ausdruck CEP_Regex_AzureServiceBusConnectionString findet Inhalte, die mit dem Muster übereinstimmen..</span><span class="sxs-lookup"><span data-stu-id="2e5c0-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="2e5c0-670">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-671">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="2e5c0-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2e5c0-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2e5c0-673">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2e5c0-674">contoso</span><span class="sxs-lookup"><span data-stu-id="2e5c0-674">contoso</span></span>
- <span data-ttu-id="2e5c0-675">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2e5c0-675">fabrikam</span></span>
- <span data-ttu-id="2e5c0-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-676">northwind</span></span>
- <span data-ttu-id="2e5c0-677">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-677">sandbox</span></span>
- <span data-ttu-id="2e5c0-678">OneBox</span><span class="sxs-lookup"><span data-stu-id="2e5c0-678">onebox</span></span>
- <span data-ttu-id="2e5c0-679">localhost</span><span class="sxs-lookup"><span data-stu-id="2e5c0-679">localhost</span></span>
- <span data-ttu-id="2e5c0-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2e5c0-680">127.0.0.1</span></span>
- <span data-ttu-id="2e5c0-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-682">com</span><span class="sxs-lookup"><span data-stu-id="2e5c0-682">com</span></span>
- <span data-ttu-id="2e5c0-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-684">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="2e5c0-685">Azure Storage-Kontoschlüssel</span><span class="sxs-lookup"><span data-stu-id="2e5c0-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-686">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-686">Format</span></span>

<span data-ttu-id="2e5c0-687">Die Zeichenfolge "DefaultEndpointsProtocol", gefolgt von den Zeichen und Zeichenfolgen, die in dem Muster unten, einschließlich der Zeichenfolge "AccountKey", dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-688">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-688">Pattern</span></span>

- <span data-ttu-id="2e5c0-689">Die Zeichenfolge "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="2e5c0-690">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-691">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-691">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-692">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-693">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2e5c0-694">Die Zeichenfolge "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-694">The string "AccountKey"</span></span>
- <span data-ttu-id="2e5c0-695">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-696">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-696">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-697">0-2 Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="2e5c0-698">Eine beliebige Kombination von 86 Zeichen mit unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2e5c0-699">Zwei Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-700">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-700">Checksum</span></span>

<span data-ttu-id="2e5c0-701">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-702">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-702">Definition</span></span>

<span data-ttu-id="2e5c0-703">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-704">Der reguläre Ausdruck CEP_Regex_AzureStorageAccountKey findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-705">Der reguläre Ausdruck CEP_AzureEmulatorStorageAccountFilter findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-706">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-707">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="2e5c0-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="2e5c0-709">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2e5c0-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="2e5c0-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="2e5c0-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2e5c0-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2e5c0-712">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2e5c0-713">contoso</span><span class="sxs-lookup"><span data-stu-id="2e5c0-713">contoso</span></span>
- <span data-ttu-id="2e5c0-714">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2e5c0-714">fabrikam</span></span>
- <span data-ttu-id="2e5c0-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-715">northwind</span></span>
- <span data-ttu-id="2e5c0-716">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-716">sandbox</span></span>
- <span data-ttu-id="2e5c0-717">OneBox</span><span class="sxs-lookup"><span data-stu-id="2e5c0-717">onebox</span></span>
- <span data-ttu-id="2e5c0-718">localhost</span><span class="sxs-lookup"><span data-stu-id="2e5c0-718">localhost</span></span>
- <span data-ttu-id="2e5c0-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2e5c0-719">127.0.0.1</span></span>
- <span data-ttu-id="2e5c0-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-721">com</span><span class="sxs-lookup"><span data-stu-id="2e5c0-721">com</span></span>
- <span data-ttu-id="2e5c0-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-723">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="2e5c0-724">Azure Storage-Kontoschlüssel (generisch)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-725">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-725">Format</span></span>

<span data-ttu-id="2e5c0-726">Eine beliebige Kombination von 86 unter-oder Großbuchstaben, Ziffern, den Schrägstrich (/) oder Pluszeichen (+), vorangestellt oder gefolgt von den im Muster unten beschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-727">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-727">Pattern</span></span>

- <span data-ttu-id="2e5c0-728">0-1 des größer als-Symbols (>), Apostroph ('), Gleichheitszeichen (=), Anführungszeichen (") oder Nummernzeichen (#)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="2e5c0-729">Eine beliebige Kombination von 86 Zeichen mit unter-oder Großbuchstaben, Ziffern, dem Schrägstrich (/) oder Pluszeichen (+)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2e5c0-730">Zwei Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="2e5c0-731">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-731">Checksum</span></span>

<span data-ttu-id="2e5c0-732">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-733">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-733">Definition</span></span>

<span data-ttu-id="2e5c0-734">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-735">Der reguläre Ausdruck CEP_Regex_AzureStorageAccountKeyGeneric findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="2e5c0-736">Belgien – Nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-737">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-737">Format</span></span>

<span data-ttu-id="2e5c0-738">11 Ziffern plus Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-739">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-739">Pattern</span></span>

<span data-ttu-id="2e5c0-740">11 Ziffern plus Trennzeichen:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="2e5c0-741">Sechs Ziffern und zwei Punkte im Format JJ.MM.TT für das Geburtsdatum </span><span class="sxs-lookup"><span data-stu-id="2e5c0-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="2e5c0-742">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-742">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-743">Drei aufeinander folgende Ziffern (ungerade für Männer, gerade für Frauen) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="2e5c0-744">Ein Punkt</span><span class="sxs-lookup"><span data-stu-id="2e5c0-744">A period</span></span> 
- <span data-ttu-id="2e5c0-745">Zwei Ziffern als Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-746">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-746">Checksum</span></span>

<span data-ttu-id="2e5c0-747">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-748">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-748">Definition</span></span>

<span data-ttu-id="2e5c0-749">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-750">Die Funktion Func_belgium_national_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-751">Ein Schlüsselwort aus Keyword_belgium_national_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="2e5c0-752">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-753">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="2e5c0-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="2e5c0-755">Identität</span><span class="sxs-lookup"><span data-stu-id="2e5c0-755">Identity</span></span>
- <span data-ttu-id="2e5c0-756">Registrierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-756">Registration</span></span>
- <span data-ttu-id="2e5c0-757">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-757">Identification</span></span> 
- <span data-ttu-id="2e5c0-758">ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-758">ID</span></span> 
- <span data-ttu-id="2e5c0-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="2e5c0-759">Identiteitskaart</span></span>
- <span data-ttu-id="2e5c0-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-760">Registratie nummer</span></span> 
- <span data-ttu-id="2e5c0-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-761">Identificatie nummer</span></span> 
- <span data-ttu-id="2e5c0-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-762">Identiteit</span></span>
- <span data-ttu-id="2e5c0-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="2e5c0-763">Registratie</span></span>
- <span data-ttu-id="2e5c0-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="2e5c0-764">Identificatie</span></span> 
- <span data-ttu-id="2e5c0-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="2e5c0-765">Carte d’identité</span></span> 
- <span data-ttu-id="2e5c0-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="2e5c0-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="2e5c0-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="2e5c0-767">numéro d'identification</span></span>
- <span data-ttu-id="2e5c0-768">identité</span><span class="sxs-lookup"><span data-stu-id="2e5c0-768">identité</span></span> 
- <span data-ttu-id="2e5c0-769">Inschrift</span><span class="sxs-lookup"><span data-stu-id="2e5c0-769">inscription</span></span> 
- <span data-ttu-id="2e5c0-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="2e5c0-770">Identifikation</span></span>
- <span data-ttu-id="2e5c0-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-771">Identifizierung</span></span>
- <span data-ttu-id="2e5c0-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-772">Identifikationsnummer</span></span>
- <span data-ttu-id="2e5c0-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-773">Personalausweis</span></span>
- <span data-ttu-id="2e5c0-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-774">Registrierung</span></span>
- <span data-ttu-id="2e5c0-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="2e5c0-776">Brazil CPF Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-777">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-777">Format</span></span>

<span data-ttu-id="2e5c0-778">11 Ziffern, die eine Prüfziffer umfassen und die formatiert oder unformatiert sein können</span><span class="sxs-lookup"><span data-stu-id="2e5c0-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-779">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-779">Pattern</span></span>

<span data-ttu-id="2e5c0-780">Formatiert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-780">Formatted:</span></span>
- <span data-ttu-id="2e5c0-781">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-781">Three digits</span></span> 
- <span data-ttu-id="2e5c0-782">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-782">A period</span></span> 
- <span data-ttu-id="2e5c0-783">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-783">Three digits</span></span> 
- <span data-ttu-id="2e5c0-784">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-784">A period</span></span> 
- <span data-ttu-id="2e5c0-785">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-785">Three digits</span></span> 
- <span data-ttu-id="2e5c0-786">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-786">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-787">Zwei Ziffern, die Prüfziffern sind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-787">Two digits which are check digits</span></span>

<span data-ttu-id="2e5c0-788">Unformatiert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-788">Unformatted:</span></span>
- <span data-ttu-id="2e5c0-789">11 Ziffern, wobei die letzten beiden Ziffern Prüfziffern sind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-790">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-790">Checksum</span></span>

<span data-ttu-id="2e5c0-791">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-792">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-792">Definition</span></span>

<span data-ttu-id="2e5c0-793">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-794">Die Funktion Func_brazil_cpf sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-795">Ein Schlüsselwort aus Keyword_brazil_cpf wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="2e5c0-796">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-796">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-797">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-798">Die Funktion Func_brazil_cpf sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-799">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-800">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="2e5c0-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="2e5c0-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="2e5c0-802">CPF</span><span class="sxs-lookup"><span data-stu-id="2e5c0-802">CPF</span></span>
- <span data-ttu-id="2e5c0-803">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-803">Identification</span></span>
- <span data-ttu-id="2e5c0-804">Registrierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-804">Registration</span></span>
- <span data-ttu-id="2e5c0-805">Umsatz</span><span class="sxs-lookup"><span data-stu-id="2e5c0-805">Revenue</span></span>
- <span data-ttu-id="2e5c0-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="2e5c0-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="2e5c0-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="2e5c0-807">Imposto</span></span> 
- <span data-ttu-id="2e5c0-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="2e5c0-808">Identificação</span></span> 
- <span data-ttu-id="2e5c0-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="2e5c0-809">Inscrição</span></span> 
- <span data-ttu-id="2e5c0-810">Receita</span><span class="sxs-lookup"><span data-stu-id="2e5c0-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="2e5c0-811">Brasilien – Juristische Personennummer (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-812">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-812">Format</span></span>

<span data-ttu-id="2e5c0-813">14 Ziffern, die eine Registrierungsnummer, eine Zweignummer und Prüfnziffern sowie Trennzeichen umfassen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-814">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-814">Pattern</span></span>
<span data-ttu-id="2e5c0-815">14 Ziffern plus Trennzeichen:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="2e5c0-816">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-816">Two digits</span></span> 
- <span data-ttu-id="2e5c0-817">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-817">A period</span></span> 
- <span data-ttu-id="2e5c0-818">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-818">Three digits</span></span> 
- <span data-ttu-id="2e5c0-819">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-819">A period</span></span> 
- <span data-ttu-id="2e5c0-820">Drei Ziffern (diese ersten acht Ziffern sind die Registrierungsnummer) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="2e5c0-821">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-821">A forward slash</span></span> 
- <span data-ttu-id="2e5c0-822">Vierstellige Zweignummer </span><span class="sxs-lookup"><span data-stu-id="2e5c0-822">Four-digit branch number</span></span> 
- <span data-ttu-id="2e5c0-823">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-823">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-824">Zwei Ziffern, die Prüfziffern sind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-825">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-825">Checksum</span></span>

<span data-ttu-id="2e5c0-826">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-827">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-827">Definition</span></span>

<span data-ttu-id="2e5c0-828">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-829">Die Funktion Func_brazil_cnpj sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-830">Ein Schlüsselwort aus Keyword_brazil_cnpj wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="2e5c0-831">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-831">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-832">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-833">Die Funktion Func_brazil_cnpj sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-834">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-835">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="2e5c0-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="2e5c0-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="2e5c0-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="2e5c0-837">CNPJ</span></span> 
- <span data-ttu-id="2e5c0-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="2e5c0-838">CNPJ/MF</span></span> 
- <span data-ttu-id="2e5c0-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="2e5c0-839">CNPJ-MF</span></span> 
- <span data-ttu-id="2e5c0-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="2e5c0-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="2e5c0-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="2e5c0-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="2e5c0-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="2e5c0-842">Legal entity</span></span> 
- <span data-ttu-id="2e5c0-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="2e5c0-843">Legal entities</span></span> 
- <span data-ttu-id="2e5c0-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="2e5c0-844">Registration Status</span></span> 
- <span data-ttu-id="2e5c0-845">Business</span><span class="sxs-lookup"><span data-stu-id="2e5c0-845">Business</span></span> 
- <span data-ttu-id="2e5c0-846">Company</span><span class="sxs-lookup"><span data-stu-id="2e5c0-846">Company</span></span>
- <span data-ttu-id="2e5c0-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="2e5c0-847">CNPJ</span></span> 
- <span data-ttu-id="2e5c0-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="2e5c0-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="2e5c0-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="2e5c0-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="2e5c0-850">CGC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-850">CGC</span></span> 
- <span data-ttu-id="2e5c0-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="2e5c0-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="2e5c0-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="2e5c0-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="2e5c0-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="2e5c0-853">Situação cadastral</span></span> 
- <span data-ttu-id="2e5c0-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="2e5c0-854">Inscrição</span></span> 
- <span data-ttu-id="2e5c0-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="2e5c0-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="2e5c0-856">	Brasilien – Personalausweis (RG)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-857">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-857">Format</span></span>

<span data-ttu-id="2e5c0-858">Registro Geral (altes Format): neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="2e5c0-859">Registro de Identidade (RIC) (neues Format): 11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-860">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-860">Pattern</span></span>

<span data-ttu-id="2e5c0-861">Registro Geral (altes Format):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="2e5c0-862">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-862">Two digits</span></span> 
- <span data-ttu-id="2e5c0-863">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-863">A period</span></span> 
- <span data-ttu-id="2e5c0-864">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-864">Three digits</span></span> 
- <span data-ttu-id="2e5c0-865">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-865">A period</span></span> 
- <span data-ttu-id="2e5c0-866">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-866">Three digits</span></span> 
- <span data-ttu-id="2e5c0-867">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-867">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-868">Eine Ziffer als Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-868">One digit which is a check digit</span></span>

<span data-ttu-id="2e5c0-869">Registro de Identidade (RIC) (neues Format):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="2e5c0-870">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-870">10 digits</span></span> 
- <span data-ttu-id="2e5c0-871">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-871">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-872">Eine Ziffer als Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-873">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-873">Checksum</span></span>

<span data-ttu-id="2e5c0-874">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-875">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-875">Definition</span></span>

<span data-ttu-id="2e5c0-876">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-877">Die Funktion Func_brazil_rg sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-878">Ein Schlüsselwort aus Keyword_brazil_rg wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="2e5c0-879">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-879">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-880">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-881">Die Funktion Func_brazil_rg sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-882">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-883">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="2e5c0-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="2e5c0-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="2e5c0-885">Cédula de identidade Personalausweis National ID número de rregistro Registro de Iidentidade Registro Geral RG (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung beachtet) RIC (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung beachtet)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="2e5c0-886">Kanadische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-887">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-887">Format</span></span>

<span data-ttu-id="2e5c0-888">Sieben oder zwölf Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-889">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-889">Pattern</span></span>

<span data-ttu-id="2e5c0-890">Eine kanadische Kontonummer umfasst sieben oder zwölf Ziffern.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="2e5c0-891">Eine kanadische Bankkontonummer setzt sich wie folgt zusammen:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="2e5c0-892">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-892">Five digits</span></span> 
- <span data-ttu-id="2e5c0-893">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-893">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-894">Drei Ziffern oder</span><span class="sxs-lookup"><span data-stu-id="2e5c0-894">Three digits OR</span></span>
- <span data-ttu-id="2e5c0-895">Eine 0 (null) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-895">A zero "0"</span></span> 
- <span data-ttu-id="2e5c0-896">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-897">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-897">Checksum</span></span>

<span data-ttu-id="2e5c0-898">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-899">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-899">Definition</span></span>

<span data-ttu-id="2e5c0-900">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-901">Der reguläre Ausdruck Regex_canada_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-902">Ein Schlüsselwort aus Keyword_canada_bank_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="2e5c0-903">Der reguläre Ausdruck Regex_canada_bank_account_transit_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="2e5c0-904">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-905">Der reguläre Ausdruck Regex_canada_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-906">Ein Schlüsselwort aus Keyword_canada_bank_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-907">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="2e5c0-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="2e5c0-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="2e5c0-909">canada savings bonds</span></span>
- <span data-ttu-id="2e5c0-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="2e5c0-910">canada revenue agency</span></span>
- <span data-ttu-id="2e5c0-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="2e5c0-911">canadian financial institution</span></span>
- <span data-ttu-id="2e5c0-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="2e5c0-912">direct deposit form</span></span>
- <span data-ttu-id="2e5c0-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-913">canadian citizen</span></span>
- <span data-ttu-id="2e5c0-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="2e5c0-914">legal representative</span></span>
- <span data-ttu-id="2e5c0-915">notary public</span><span class="sxs-lookup"><span data-stu-id="2e5c0-915">notary public</span></span>
- <span data-ttu-id="2e5c0-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="2e5c0-916">commissioner for oaths</span></span>
- <span data-ttu-id="2e5c0-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-917">child care benefit</span></span>
- <span data-ttu-id="2e5c0-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="2e5c0-918">universal child care</span></span>
- <span data-ttu-id="2e5c0-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-919">canada child tax benefit</span></span>
- <span data-ttu-id="2e5c0-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-920">income tax benefit</span></span>
- <span data-ttu-id="2e5c0-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="2e5c0-921">harmonized sales tax</span></span>
- <span data-ttu-id="2e5c0-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-922">social insurance number</span></span>
- <span data-ttu-id="2e5c0-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="2e5c0-923">income tax refund</span></span>
- <span data-ttu-id="2e5c0-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-924">child tax benefit</span></span>
- <span data-ttu-id="2e5c0-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="2e5c0-925">territorial payments</span></span>
- <span data-ttu-id="2e5c0-926">institution number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-926">institution number</span></span>
- <span data-ttu-id="2e5c0-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="2e5c0-927">deposit request</span></span>
- <span data-ttu-id="2e5c0-928">banking information</span><span class="sxs-lookup"><span data-stu-id="2e5c0-928">banking information</span></span>
- <span data-ttu-id="2e5c0-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="2e5c0-930">Kanadische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-931">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-931">Format</span></span>

<span data-ttu-id="2e5c0-932">Variiert je nach Provinz</span><span class="sxs-lookup"><span data-stu-id="2e5c0-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-933">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-933">Pattern</span></span>

<span data-ttu-id="2e5c0-934">Verschiedene Muster in Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec und Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="2e5c0-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-935">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-935">Checksum</span></span>

<span data-ttu-id="2e5c0-936">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-937">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-937">Definition</span></span>

<span data-ttu-id="2e5c0-938">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-939">Die Funktion Func_[province_name]_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-940">Ein Schlüsselwort aus Keyword_[province_name]_drivers_license_name wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="2e5c0-941">Ein Schlüsselwort aus Keyword_canada_drivers_license wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-942">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="2e5c0-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="2e5c0-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="2e5c0-944">Die Abkürzung für die Provinz, z. B. AB</span><span class="sxs-lookup"><span data-stu-id="2e5c0-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="2e5c0-945">Der Name der Provinz, beispielsweise „Alberta“</span><span class="sxs-lookup"><span data-stu-id="2e5c0-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="2e5c0-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="2e5c0-947">DL</span><span class="sxs-lookup"><span data-stu-id="2e5c0-947">DL</span></span>
- <span data-ttu-id="2e5c0-948">DLS</span><span class="sxs-lookup"><span data-stu-id="2e5c0-948">DLS</span></span>
- <span data-ttu-id="2e5c0-949">CDL</span><span class="sxs-lookup"><span data-stu-id="2e5c0-949">CDL</span></span>
- <span data-ttu-id="2e5c0-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="2e5c0-950">CDLS</span></span>
- <span data-ttu-id="2e5c0-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-951">DriverLic</span></span>
- <span data-ttu-id="2e5c0-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-952">DriverLics</span></span>
- <span data-ttu-id="2e5c0-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="2e5c0-953">DriverLicense</span></span>
- <span data-ttu-id="2e5c0-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-954">DriverLicenses</span></span>
- <span data-ttu-id="2e5c0-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-955">DriverLicence</span></span>
- <span data-ttu-id="2e5c0-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-956">DriverLicences</span></span>
- <span data-ttu-id="2e5c0-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-957">Driver Lic</span></span>
- <span data-ttu-id="2e5c0-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-958">Driver Lics</span></span>
- <span data-ttu-id="2e5c0-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-959">Driver License</span></span>
- <span data-ttu-id="2e5c0-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-960">Driver Licenses</span></span>
- <span data-ttu-id="2e5c0-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-961">Driver Licence</span></span>
- <span data-ttu-id="2e5c0-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-962">Driver Licences</span></span>
- <span data-ttu-id="2e5c0-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-963">DriversLic</span></span>
- <span data-ttu-id="2e5c0-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-964">DriversLics</span></span>
- <span data-ttu-id="2e5c0-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-965">DriversLicence</span></span>
- <span data-ttu-id="2e5c0-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-966">DriversLicences</span></span>
- <span data-ttu-id="2e5c0-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="2e5c0-967">DriversLicense</span></span>
- <span data-ttu-id="2e5c0-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-968">DriversLicenses</span></span>
- <span data-ttu-id="2e5c0-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-969">Drivers Lic</span></span>
- <span data-ttu-id="2e5c0-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-970">Drivers Lics</span></span>
- <span data-ttu-id="2e5c0-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-971">Drivers License</span></span>
- <span data-ttu-id="2e5c0-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-972">Drivers Licenses</span></span>
- <span data-ttu-id="2e5c0-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-973">Drivers Licence</span></span>
- <span data-ttu-id="2e5c0-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-974">Drivers Licences</span></span>
- <span data-ttu-id="2e5c0-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-975">Driver'Lic</span></span>
- <span data-ttu-id="2e5c0-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-976">Driver'Lics</span></span>
- <span data-ttu-id="2e5c0-977">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-977">Driver'License</span></span>
- <span data-ttu-id="2e5c0-978">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-978">Driver'Licenses</span></span>
- <span data-ttu-id="2e5c0-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-979">Driver'Licence</span></span>
- <span data-ttu-id="2e5c0-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-980">Driver'Licences</span></span>
- <span data-ttu-id="2e5c0-981">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-981">Driver' Lic</span></span>
- <span data-ttu-id="2e5c0-982">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-982">Driver' Lics</span></span>
- <span data-ttu-id="2e5c0-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-983">Driver' License</span></span>
- <span data-ttu-id="2e5c0-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-984">Driver' Licenses</span></span>
- <span data-ttu-id="2e5c0-985">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-985">Driver' Licence</span></span>
- <span data-ttu-id="2e5c0-986">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-986">Driver' Licences</span></span>
- <span data-ttu-id="2e5c0-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-987">Driver'sLic</span></span>
- <span data-ttu-id="2e5c0-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-988">Driver'sLics</span></span>
- <span data-ttu-id="2e5c0-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="2e5c0-989">Driver'sLicense</span></span>
- <span data-ttu-id="2e5c0-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-990">Driver'sLicenses</span></span>
- <span data-ttu-id="2e5c0-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-991">Driver'sLicence</span></span>
- <span data-ttu-id="2e5c0-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-992">Driver'sLicences</span></span>
- <span data-ttu-id="2e5c0-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-993">Driver's Lic</span></span>
- <span data-ttu-id="2e5c0-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-994">Driver's Lics</span></span>
- <span data-ttu-id="2e5c0-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-995">Driver's License</span></span>
- <span data-ttu-id="2e5c0-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-996">Driver's Licenses</span></span>
- <span data-ttu-id="2e5c0-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-997">Driver's Licence</span></span>
- <span data-ttu-id="2e5c0-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-998">Driver's Licences</span></span>
- <span data-ttu-id="2e5c0-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="2e5c0-999">Permis de Conduire</span></span>
- <span data-ttu-id="2e5c0-1000">id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1000">id</span></span>
- <span data-ttu-id="2e5c0-1001">ids</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1001">ids</span></span>
- <span data-ttu-id="2e5c0-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1002">idcard number</span></span>
- <span data-ttu-id="2e5c0-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1003">idcard numbers</span></span>
- <span data-ttu-id="2e5c0-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1004">idcard #</span></span>
- <span data-ttu-id="2e5c0-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1005">idcard #s</span></span>
- <span data-ttu-id="2e5c0-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1006">idcard card</span></span>
- <span data-ttu-id="2e5c0-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1007">idcard cards</span></span>
- <span data-ttu-id="2e5c0-1008">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1008">idcard</span></span>
- <span data-ttu-id="2e5c0-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1009">identification number</span></span>
- <span data-ttu-id="2e5c0-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1010">identification numbers</span></span>
- <span data-ttu-id="2e5c0-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1011">identification #</span></span>
- <span data-ttu-id="2e5c0-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1012">identification #s</span></span>
- <span data-ttu-id="2e5c0-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1013">identification card</span></span>
- <span data-ttu-id="2e5c0-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1014">identification cards</span></span>
- <span data-ttu-id="2e5c0-1015">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1015">identification</span></span> 
- <span data-ttu-id="2e5c0-1016">DL #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1016">DL#</span></span>
- <span data-ttu-id="2e5c0-1017">DLS #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1017">DLS#</span></span> 
- <span data-ttu-id="2e5c0-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1018">CDL#</span></span> 
- <span data-ttu-id="2e5c0-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1019">CDLS#</span></span> 
- <span data-ttu-id="2e5c0-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1020">DriverLic#</span></span> 
- <span data-ttu-id="2e5c0-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1021">DriverLics#</span></span> 
- <span data-ttu-id="2e5c0-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1022">DriverLicense#</span></span> 
- <span data-ttu-id="2e5c0-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="2e5c0-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1024">DriverLicence#</span></span> 
- <span data-ttu-id="2e5c0-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1025">DriverLicences#</span></span> 
- <span data-ttu-id="2e5c0-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1026">Driver Lic#</span></span>
- <span data-ttu-id="2e5c0-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1027">Driver Lics#</span></span> 
- <span data-ttu-id="2e5c0-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1028">Driver License#</span></span> 
- <span data-ttu-id="2e5c0-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="2e5c0-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1030">Driver License#</span></span> 
- <span data-ttu-id="2e5c0-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1031">Driver Licences#</span></span> 
- <span data-ttu-id="2e5c0-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1032">DriversLic#</span></span> 
- <span data-ttu-id="2e5c0-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1033">DriversLics#</span></span> 
- <span data-ttu-id="2e5c0-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1034">DriversLicense#</span></span> 
- <span data-ttu-id="2e5c0-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="2e5c0-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1036">DriversLicence#</span></span> 
- <span data-ttu-id="2e5c0-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1037">DriversLicences#</span></span> 
- <span data-ttu-id="2e5c0-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="2e5c0-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="2e5c0-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1040">Drivers License#</span></span> 
- <span data-ttu-id="2e5c0-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="2e5c0-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="2e5c0-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="2e5c0-1044">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="2e5c0-1045">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="2e5c0-1046">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1046">Driver'License#</span></span> 
- <span data-ttu-id="2e5c0-1047">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="2e5c0-1048">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="2e5c0-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="2e5c0-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="2e5c0-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="2e5c0-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1052">Driver' License#</span></span> 
- <span data-ttu-id="2e5c0-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="2e5c0-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="2e5c0-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="2e5c0-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="2e5c0-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="2e5c0-1058">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="2e5c0-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="2e5c0-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="2e5c0-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="2e5c0-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="2e5c0-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="2e5c0-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1064">Driver's License#</span></span> 
- <span data-ttu-id="2e5c0-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="2e5c0-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="2e5c0-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="2e5c0-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="2e5c0-1069">ID #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1069">id#</span></span> 
- <span data-ttu-id="2e5c0-1070">IDs #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1070">ids#</span></span> 
- <span data-ttu-id="2e5c0-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1071">idcard card#</span></span> 
- <span data-ttu-id="2e5c0-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1072">idcard cards#</span></span> 
- <span data-ttu-id="2e5c0-1073">Personalausweis #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1073">idcard#</span></span> 
- <span data-ttu-id="2e5c0-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1074">identification card#</span></span> 
- <span data-ttu-id="2e5c0-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1075">identification cards#</span></span> 
- <span data-ttu-id="2e5c0-1076">Identifizierung #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="2e5c0-1077">Kanadische Health Service-Nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1078">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1078">Format</span></span>

<span data-ttu-id="2e5c0-1079">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1080">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1080">Pattern</span></span>

<span data-ttu-id="2e5c0-1081">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1082">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1082">Checksum</span></span>

<span data-ttu-id="2e5c0-1083">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1084">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1084">Definition</span></span>

<span data-ttu-id="2e5c0-1085">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1086">Der reguläre Ausdruck Regex_canada_health_service_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1087">Ein Schlüsselwort aus Keyword_canada_health_service_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-1088">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="2e5c0-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="2e5c0-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1090">personal health number</span></span>
- <span data-ttu-id="2e5c0-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1091">patient information</span></span>
- <span data-ttu-id="2e5c0-1092">health services</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1092">health services</span></span>
- <span data-ttu-id="2e5c0-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1093">speciality services</span></span>
- <span data-ttu-id="2e5c0-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1094">automobile accident</span></span>
- <span data-ttu-id="2e5c0-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1095">patient hospital</span></span>
- <span data-ttu-id="2e5c0-1096">Psychiater</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1096">psychiatrist</span></span>
- <span data-ttu-id="2e5c0-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1097">workers compensation</span></span>
- <span data-ttu-id="2e5c0-1098">Disability</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="2e5c0-1099">Kanadische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1100">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1100">Format</span></span>

<span data-ttu-id="2e5c0-1101">Zwei Großbuchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1102">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1102">Pattern</span></span>

<span data-ttu-id="2e5c0-1103">Zwei Großbuchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1104">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1104">Checksum</span></span>

<span data-ttu-id="2e5c0-1105">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1106">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1106">Definition</span></span>

<span data-ttu-id="2e5c0-1107">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1108">Der reguläre Ausdruck Regex_canada_passport_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1109">Ein Schlüsselwort aus Keyword_canada_passport_number oder Keyword_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-1110">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="2e5c0-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="2e5c0-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1112">canadian citizenship</span></span>
- <span data-ttu-id="2e5c0-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1113">canadian passport</span></span>
- <span data-ttu-id="2e5c0-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1114">passport application</span></span>
- <span data-ttu-id="2e5c0-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1115">passport photos</span></span>
- <span data-ttu-id="2e5c0-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1116">certified translator</span></span>
- <span data-ttu-id="2e5c0-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1117">canadian citizens</span></span>
- <span data-ttu-id="2e5c0-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1118">processing times</span></span>
- <span data-ttu-id="2e5c0-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="2e5c0-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1120">Keyword_passport</span></span>

- <span data-ttu-id="2e5c0-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1121">Passport Number</span></span>
- <span data-ttu-id="2e5c0-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1122">Passport No</span></span>
- <span data-ttu-id="2e5c0-1123">Passport#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1123">Passport #</span></span>
- <span data-ttu-id="2e5c0-1124">Pass #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1124">Passport#</span></span>
- <span data-ttu-id="2e5c0-1125">Passport-Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1125">PassportID</span></span>
- <span data-ttu-id="2e5c0-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1126">Passportno</span></span>
- <span data-ttu-id="2e5c0-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1127">passportnumber</span></span>
- <span data-ttu-id="2e5c0-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1128">パスポート</span></span>
- <span data-ttu-id="2e5c0-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1129">パスポート番号</span></span>
- <span data-ttu-id="2e5c0-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1130">パスポートのNum</span></span>
- <span data-ttu-id="2e5c0-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1131">パスポート＃</span></span>
- <span data-ttu-id="2e5c0-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1132">Numéro de passeport</span></span>
- <span data-ttu-id="2e5c0-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1133">Passeport n °</span></span>
- <span data-ttu-id="2e5c0-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1134">Passeport Non</span></span>
- <span data-ttu-id="2e5c0-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1135">Passeport #</span></span>
- <span data-ttu-id="2e5c0-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1136">Passeport#</span></span>
- <span data-ttu-id="2e5c0-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1137">PasseportNon</span></span>
- <span data-ttu-id="2e5c0-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="2e5c0-1139">Kanadische Personal Health Identification-Nummer (PHIN)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1140">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1140">Format</span></span>

<span data-ttu-id="2e5c0-1141">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1142">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1142">Pattern</span></span>

<span data-ttu-id="2e5c0-1143">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1144">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1144">Checksum</span></span>

<span data-ttu-id="2e5c0-1145">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1146">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1146">Definition</span></span>

<span data-ttu-id="2e5c0-1147">Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: der reguläre Ausdruck Regex_canada_phin findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="2e5c0-1148">Mindestens zwei Schlüsselwörter aus Keyword_canada_phin oder Keyword_canada_provinces werden gefunden..</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-1149">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="2e5c0-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="2e5c0-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1151">social insurance number</span></span>
- <span data-ttu-id="2e5c0-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1152">health information act</span></span>
- <span data-ttu-id="2e5c0-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1153">income tax information</span></span>
- <span data-ttu-id="2e5c0-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1154">manitoba health</span></span>
- <span data-ttu-id="2e5c0-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1155">health registration</span></span>
- <span data-ttu-id="2e5c0-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1156">prescription purchases</span></span>
- <span data-ttu-id="2e5c0-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1157">benefit eligibility</span></span>
- <span data-ttu-id="2e5c0-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1158">personal health</span></span>
- <span data-ttu-id="2e5c0-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1159">power of attorney</span></span>
- <span data-ttu-id="2e5c0-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1160">registration number</span></span>
- <span data-ttu-id="2e5c0-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1161">personal health number</span></span>
- <span data-ttu-id="2e5c0-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1162">practitioner referral</span></span>
- <span data-ttu-id="2e5c0-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1163">wellness professional</span></span>
- <span data-ttu-id="2e5c0-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1164">patient referral</span></span>
- <span data-ttu-id="2e5c0-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="2e5c0-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="2e5c0-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1167">Nunavut</span></span>
- <span data-ttu-id="2e5c0-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1168">Quebec</span></span>
- <span data-ttu-id="2e5c0-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1169">Northwest Territories</span></span>
- <span data-ttu-id="2e5c0-1170">Ontario</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1170">Ontario</span></span>
- <span data-ttu-id="2e5c0-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1171">British Columbia</span></span>
- <span data-ttu-id="2e5c0-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1172">Alberta</span></span>
- <span data-ttu-id="2e5c0-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1173">Saskatchewan</span></span>
- <span data-ttu-id="2e5c0-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1174">Manitoba</span></span>
- <span data-ttu-id="2e5c0-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1175">Yukon</span></span>
- <span data-ttu-id="2e5c0-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="2e5c0-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1177">New Brunswick</span></span>
- <span data-ttu-id="2e5c0-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1178">Nova Scotia</span></span>
- <span data-ttu-id="2e5c0-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1179">Prince Edward Island</span></span>
- <span data-ttu-id="2e5c0-1180">Kanada</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="2e5c0-1181">Kanadische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1182">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1182">Format</span></span>

<span data-ttu-id="2e5c0-1183">Neun Ziffern mit optionalen Bindestrichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1184">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1184">Pattern</span></span>

<span data-ttu-id="2e5c0-1185">Formatiert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1185">Formatted:</span></span>
- <span data-ttu-id="2e5c0-1186">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1186">Three digits</span></span> 
- <span data-ttu-id="2e5c0-1187">Ein Bindestrich oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1187">A hyphen or space</span></span> 
- <span data-ttu-id="2e5c0-1188">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1188">Three digits</span></span> 
- <span data-ttu-id="2e5c0-1189">Ein Bindestrich oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1189">A hyphen or space</span></span> 
- <span data-ttu-id="2e5c0-1190">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1190">Three digits</span></span>

<span data-ttu-id="2e5c0-1191">Unformatiert: neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1192">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1192">Checksum</span></span>

<span data-ttu-id="2e5c0-1193">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1194">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1194">Definition</span></span>

<span data-ttu-id="2e5c0-1195">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1196">Die Funktion Func_canadian_sin findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1197">Mindestens zwei dieser eine beliebige Kombination der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="2e5c0-1198">Ein Schlüsselwort aus Keyword_sin wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="2e5c0-1199">Ein Schlüsselwort aus Keyword_sin_collaborative wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="2e5c0-1200">Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2e5c0-1201">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1201">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-1202">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1203">Die Funktion Func_unformatted_canadian_sin findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1204">Ein Schlüsselwort aus Keyword_sin wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="2e5c0-1205">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-1206">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="2e5c0-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1207">Keyword_sin</span></span>

- <span data-ttu-id="2e5c0-1208">sin</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1208">sin</span></span> 
- <span data-ttu-id="2e5c0-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1209">social insurance</span></span> 
- <span data-ttu-id="2e5c0-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="2e5c0-1211">Todsünden</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1211">sins</span></span> 
- <span data-ttu-id="2e5c0-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1212">ssn</span></span> 
- <span data-ttu-id="2e5c0-1213">Sozialversicherungsnummern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1213">ssns</span></span> 
- <span data-ttu-id="2e5c0-1214">social security</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1214">social security</span></span> 
- <span data-ttu-id="2e5c0-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="2e5c0-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1216">national identification number</span></span> 
- <span data-ttu-id="2e5c0-1217">national id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1217">national id</span></span> 
- <span data-ttu-id="2e5c0-1218">Sin #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1218">sin#</span></span> 
- <span data-ttu-id="2e5c0-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1219">soc ins</span></span> 
- <span data-ttu-id="2e5c0-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="2e5c0-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="2e5c0-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1222">driver's license</span></span> 
- <span data-ttu-id="2e5c0-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1223">drivers license</span></span> 
- <span data-ttu-id="2e5c0-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1224">driver's licence</span></span> 
- <span data-ttu-id="2e5c0-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1225">drivers licence</span></span> 
- <span data-ttu-id="2e5c0-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1226">DOB</span></span> 
- <span data-ttu-id="2e5c0-1227">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1227">Birthdate</span></span> 
- <span data-ttu-id="2e5c0-1228">Geburtstag</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1228">Birthday</span></span> 
- <span data-ttu-id="2e5c0-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="2e5c0-1230">	Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1231">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1231">Format</span></span>

<span data-ttu-id="2e5c0-1232">7-8 Ziffern Plus Trennzeichen für eine Prüfziffer oder einen Buchstaben</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1233">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1233">Pattern</span></span>

<span data-ttu-id="2e5c0-1234">7-8 Ziffern plus Trennzeichen:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="2e5c0-1235">1-2 Ziffern </span><span class="sxs-lookup"><span data-stu-id="2e5c0-1235">1-2 digits</span></span> 
- <span data-ttu-id="2e5c0-1236">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-1236">A period</span></span> 
- <span data-ttu-id="2e5c0-1237">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1237">Three digits</span></span> 
- <span data-ttu-id="2e5c0-1238">Ein Punkt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-1238">A period</span></span> 
- <span data-ttu-id="2e5c0-1239">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1239">Three digits</span></span> 
- <span data-ttu-id="2e5c0-1240">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1240">A dash</span></span> 
- <span data-ttu-id="2e5c0-1241">Eine Ziffer oder ein Buchstabe (Groß-/Kleinschreibung nicht unterschieden), die bzw. der eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1242">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1242">Checksum</span></span>

<span data-ttu-id="2e5c0-1243">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1244">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1244">Definition</span></span>

<span data-ttu-id="2e5c0-1245">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1246">Die Funktion Func_chile_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1247">Ein Schlüsselwort aus Keyword_chile_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="2e5c0-1248">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1248">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-1249">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1250">Die Funktion Func_chile_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1251">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-1252">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="2e5c0-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="2e5c0-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1254">National Identification Number</span></span> 
- <span data-ttu-id="2e5c0-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1255">Identity card</span></span> 
- <span data-ttu-id="2e5c0-1256">ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1256">ID</span></span> 
- <span data-ttu-id="2e5c0-1257">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1257">Identification</span></span> 
- <span data-ttu-id="2e5c0-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="2e5c0-1259">Ausführen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1259">RUN</span></span> 
- <span data-ttu-id="2e5c0-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="2e5c0-1261">Rut</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1261">RUT</span></span> 
- <span data-ttu-id="2e5c0-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="2e5c0-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="2e5c0-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="2e5c0-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="2e5c0-1266">	China (PRC) – Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1267">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1267">Format</span></span>

<span data-ttu-id="2e5c0-1268">18 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1269">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1269">Pattern</span></span>

<span data-ttu-id="2e5c0-1270">18 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1270">18 digits:</span></span>
- <span data-ttu-id="2e5c0-1271">Sechs Ziffern, die einen Adresscode angeben </span><span class="sxs-lookup"><span data-stu-id="2e5c0-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="2e5c0-1272">Acht Ziffern im Fomat JJJJMMTT, wobei es sich um das Geburtsdatum handelt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2e5c0-1273">Drei Ziffern, die ein Reihenfolgencode sind </span><span class="sxs-lookup"><span data-stu-id="2e5c0-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="2e5c0-1274">Eine Ziffer als Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1275">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1275">Checksum</span></span>

<span data-ttu-id="2e5c0-1276">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1277">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1277">Definition</span></span>

<span data-ttu-id="2e5c0-1278">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1279">Die Funktion Func_china_resident_id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1280">Ein Schlüsselwort aus Keyword_china_resident_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="2e5c0-1281">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1281">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-1282">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1283">Die Funktion Func_china_resident_id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1284">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-1285">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="2e5c0-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="2e5c0-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="2e5c0-1288">PRC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1288">PRC</span></span> 
- <span data-ttu-id="2e5c0-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1289">National Identification Card</span></span> 
- <span data-ttu-id="2e5c0-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1290">身份证</span></span> 
- <span data-ttu-id="2e5c0-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1291">居民 身份证</span></span> 
- <span data-ttu-id="2e5c0-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1292">居民身份证</span></span> 
- <span data-ttu-id="2e5c0-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1293">鉴定</span></span> 
- <span data-ttu-id="2e5c0-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1294">身分證</span></span> 
- <span data-ttu-id="2e5c0-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1295">居民 身份證</span></span>
- <span data-ttu-id="2e5c0-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="2e5c0-1297">Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1298">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1298">Format</span></span>

<span data-ttu-id="2e5c0-1299">14 bis 16 Ziffern, die formatiert oder unformatiert (dddddddddddddddd) sein können und die den Luhn-Test bestehen müssen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1300">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1300">Pattern</span></span>

<span data-ttu-id="2e5c0-1301">Sehr komplexe und robuste Muster, die Karten aller wichtigen Marken weltweit, einschließlich Visa, MasterCard, Discover-Karte, JCB, American Express, Geschenkgutscheine und Restaurantkarten erkennen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1302">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1302">Checksum</span></span>

<span data-ttu-id="2e5c0-1303">Ja, die Luhn-Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1304">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1304">Definition</span></span>

<span data-ttu-id="2e5c0-1305">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1306">Die Funktion Func_credit_card findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1307">Eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1307">One of the following is true:</span></span>
    - <span data-ttu-id="2e5c0-1308">Ein Schlüsselwort aus Keyword_cc_verification wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="2e5c0-1309">Ein Schlüsselwort aus Keyword_cc_name wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="2e5c0-1310">Die Funktion Func_expiration_date findet ein Datum im richtigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2e5c0-1311">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1311">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-1312">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1313">Die Funktion Func_credit_card findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1314">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-1315">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="2e5c0-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="2e5c0-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1317">card verification</span></span>
- <span data-ttu-id="2e5c0-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1318">card identification number</span></span>
- <span data-ttu-id="2e5c0-1319">CVN</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1319">cvn</span></span>
- <span data-ttu-id="2e5c0-1320">cid</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1320">cid</span></span>
- <span data-ttu-id="2e5c0-1321">CVC2</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1321">cvc2</span></span>
- <span data-ttu-id="2e5c0-1322">CVV2</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1322">cvv2</span></span>
- <span data-ttu-id="2e5c0-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1323">pin block</span></span>
- <span data-ttu-id="2e5c0-1324">security code</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1324">security code</span></span>
- <span data-ttu-id="2e5c0-1325">security number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1325">security number</span></span>
- <span data-ttu-id="2e5c0-1326">security no</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1326">security no</span></span>
- <span data-ttu-id="2e5c0-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1327">issue number</span></span>
- <span data-ttu-id="2e5c0-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1328">issue no</span></span>
- <span data-ttu-id="2e5c0-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1329">cryptogramme</span></span>
- <span data-ttu-id="2e5c0-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1330">numéro de sécurité</span></span>
- <span data-ttu-id="2e5c0-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1331">numero de securite</span></span>
- <span data-ttu-id="2e5c0-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="2e5c0-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="2e5c0-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1334">prüfziffer</span></span>
- <span data-ttu-id="2e5c0-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1335">prufziffer</span></span>
- <span data-ttu-id="2e5c0-1336">Sicherheitskode</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1336">sicherheits Kode</span></span>
- <span data-ttu-id="2e5c0-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1337">sicherheitscode</span></span>
- <span data-ttu-id="2e5c0-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="2e5c0-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1339">verfalldatum</span></span>
- <span data-ttu-id="2e5c0-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1340">codice di verifica</span></span>
- <span data-ttu-id="2e5c0-1341">COD.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1341">cod.</span></span> <span data-ttu-id="2e5c0-1342">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1342">sicurezza</span></span>
- <span data-ttu-id="2e5c0-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1343">cod sicurezza</span></span>
- <span data-ttu-id="2e5c0-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1344">n autorizzazione</span></span>
- <span data-ttu-id="2e5c0-1345">Código</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1345">código</span></span>
- <span data-ttu-id="2e5c0-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1346">codigo</span></span>
- <span data-ttu-id="2e5c0-1347">COD.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1347">cod.</span></span> <span data-ttu-id="2e5c0-1348">SEG</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1348">seg</span></span>
- <span data-ttu-id="2e5c0-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1349">cod seg</span></span>
- <span data-ttu-id="2e5c0-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1350">código de segurança</span></span>
- <span data-ttu-id="2e5c0-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1351">codigo de seguranca</span></span>
- <span data-ttu-id="2e5c0-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1352">codigo de segurança</span></span>
- <span data-ttu-id="2e5c0-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1353">código de seguranca</span></span>
- <span data-ttu-id="2e5c0-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1354">cód.</span></span> <span data-ttu-id="2e5c0-1355">Segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1355">segurança</span></span>
- <span data-ttu-id="2e5c0-1356">COD.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1356">cod.</span></span> <span data-ttu-id="2e5c0-1357">Seguranca COD.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1357">seguranca cod.</span></span> <span data-ttu-id="2e5c0-1358">Segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1358">segurança</span></span>
- <span data-ttu-id="2e5c0-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1359">cód.</span></span> <span data-ttu-id="2e5c0-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1360">seguranca</span></span>
- <span data-ttu-id="2e5c0-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1361">cód segurança</span></span>
- <span data-ttu-id="2e5c0-1362">COD Seguranca COD Segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="2e5c0-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1363">cód seguranca</span></span>
- <span data-ttu-id="2e5c0-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1364">número de verificação</span></span>
- <span data-ttu-id="2e5c0-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1365">numero de verificacao</span></span>
- <span data-ttu-id="2e5c0-1366">Ablauf</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1366">ablauf</span></span>
- <span data-ttu-id="2e5c0-1367">Gültig bis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1367">gültig bis</span></span>
- <span data-ttu-id="2e5c0-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="2e5c0-1369">Gultig bis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1369">gultig bis</span></span>
- <span data-ttu-id="2e5c0-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="2e5c0-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1371">scadenza</span></span>
- <span data-ttu-id="2e5c0-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1372">data scad</span></span>
- <span data-ttu-id="2e5c0-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1373">fecha de expiracion</span></span>
- <span data-ttu-id="2e5c0-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1374">fecha de venc</span></span>
- <span data-ttu-id="2e5c0-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1375">vencimiento</span></span>
- <span data-ttu-id="2e5c0-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1376">válido hasta</span></span>
- <span data-ttu-id="2e5c0-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1377">valido hasta</span></span>
- <span data-ttu-id="2e5c0-1378">VTO</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1378">vto</span></span>
- <span data-ttu-id="2e5c0-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1379">data de expiração</span></span>
- <span data-ttu-id="2e5c0-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1380">data de expiracao</span></span>
- <span data-ttu-id="2e5c0-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1381">data em que expira</span></span>
- <span data-ttu-id="2e5c0-1382">validade</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1382">validade</span></span>
- <span data-ttu-id="2e5c0-1383">Valor</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1383">valor</span></span>
- <span data-ttu-id="2e5c0-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1384">vencimento</span></span>
- <span data-ttu-id="2e5c0-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="2e5c0-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="2e5c0-1387">Amex</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1387">amex</span></span>
- <span data-ttu-id="2e5c0-1388">american express</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1388">american express</span></span>
- <span data-ttu-id="2e5c0-1389">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1389">americanexpress</span></span>
- <span data-ttu-id="2e5c0-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1390">Visa</span></span>
- <span data-ttu-id="2e5c0-1391">MasterCard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1391">mastercard</span></span>
- <span data-ttu-id="2e5c0-1392">master card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1392">master card</span></span>
- <span data-ttu-id="2e5c0-1393">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1393">mc</span></span> 
- <span data-ttu-id="2e5c0-1394">MasterCards gesichert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1394">mastercards</span></span>
- <span data-ttu-id="2e5c0-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1395">master cards</span></span>
- <span data-ttu-id="2e5c0-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1396">diner's Club</span></span>
- <span data-ttu-id="2e5c0-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1397">diners club</span></span>
- <span data-ttu-id="2e5c0-1398">DinersClub</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1398">dinersclub</span></span>
- <span data-ttu-id="2e5c0-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1399">discover card</span></span>
- <span data-ttu-id="2e5c0-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1400">discovercard</span></span>
- <span data-ttu-id="2e5c0-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1401">discover cards</span></span>
- <span data-ttu-id="2e5c0-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1402">JCB</span></span>
- <span data-ttu-id="2e5c0-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1403">japanese card bureau</span></span>
- <span data-ttu-id="2e5c0-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1404">carte blanche</span></span>
- <span data-ttu-id="2e5c0-1405">CarteBlanche</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1405">carteblanche</span></span>
- <span data-ttu-id="2e5c0-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1406">credit card</span></span>
- <span data-ttu-id="2e5c0-1407">CC #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1407">cc#</span></span>
- <span data-ttu-id="2e5c0-1408">cc #:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1408">cc#:</span></span>
- <span data-ttu-id="2e5c0-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1409">expiration date</span></span>
- <span data-ttu-id="2e5c0-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1410">exp date</span></span>
- <span data-ttu-id="2e5c0-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1411">expiry date</span></span>
- <span data-ttu-id="2e5c0-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1412">date d’expiration</span></span>
- <span data-ttu-id="2e5c0-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1413">date d'exp</span></span>
- <span data-ttu-id="2e5c0-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1414">date expiration</span></span>
- <span data-ttu-id="2e5c0-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1415">bank card</span></span>
- <span data-ttu-id="2e5c0-1416">Bankcard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1416">bankcard</span></span>
- <span data-ttu-id="2e5c0-1417">card number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1417">card number</span></span>
- <span data-ttu-id="2e5c0-1418">card num</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1418">card num</span></span>
- <span data-ttu-id="2e5c0-1419">cardNumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1419">cardnumber</span></span>
- <span data-ttu-id="2e5c0-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1420">cardnumbers</span></span>
- <span data-ttu-id="2e5c0-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1421">card numbers</span></span>
- <span data-ttu-id="2e5c0-1422">CreditCard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1422">creditcard</span></span>
- <span data-ttu-id="2e5c0-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1423">credit cards</span></span>
- <span data-ttu-id="2e5c0-1424">creditCards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1424">creditcards</span></span>
- <span data-ttu-id="2e5c0-1425">Angaben</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1425">ccn</span></span>
- <span data-ttu-id="2e5c0-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1426">card holder</span></span>
- <span data-ttu-id="2e5c0-1427">Inhaber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1427">cardholder</span></span>
- <span data-ttu-id="2e5c0-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1428">card holders</span></span>
- <span data-ttu-id="2e5c0-1429">Inhaber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1429">cardholders</span></span>
- <span data-ttu-id="2e5c0-1430">check card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1430">check card</span></span>
- <span data-ttu-id="2e5c0-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1431">checkcard</span></span>
- <span data-ttu-id="2e5c0-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1432">check cards</span></span>
- <span data-ttu-id="2e5c0-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1433">checkcards</span></span>
- <span data-ttu-id="2e5c0-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1434">debit card</span></span>
- <span data-ttu-id="2e5c0-1435">Debitkarte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1435">debitcard</span></span>
- <span data-ttu-id="2e5c0-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1436">debit cards</span></span>
- <span data-ttu-id="2e5c0-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1437">debitcards</span></span>
- <span data-ttu-id="2e5c0-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1438">atm card</span></span>
- <span data-ttu-id="2e5c0-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1439">atmcard</span></span>
- <span data-ttu-id="2e5c0-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1440">atm cards</span></span>
- <span data-ttu-id="2e5c0-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1441">atmcards</span></span>
- <span data-ttu-id="2e5c0-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1442">enroute</span></span>
- <span data-ttu-id="2e5c0-1443">en route</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1443">en route</span></span>
- <span data-ttu-id="2e5c0-1444">card type</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1444">card type</span></span>
- <span data-ttu-id="2e5c0-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1445">carte bancaire</span></span>
- <span data-ttu-id="2e5c0-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1446">carte de crédit</span></span>
- <span data-ttu-id="2e5c0-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1447">carte de credit</span></span>
- <span data-ttu-id="2e5c0-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1448">numéro de carte</span></span>
- <span data-ttu-id="2e5c0-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1449">numero de carte</span></span>
- <span data-ttu-id="2e5c0-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1450">nº de la carte</span></span>
- <span data-ttu-id="2e5c0-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1451">nº de carte</span></span>
- <span data-ttu-id="2e5c0-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1452">kreditkarte</span></span>
- <span data-ttu-id="2e5c0-1453">Karte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1453">karte</span></span>
- <span data-ttu-id="2e5c0-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1454">karteninhaber</span></span>
- <span data-ttu-id="2e5c0-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1455">karteninhabers</span></span>
- <span data-ttu-id="2e5c0-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="2e5c0-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="2e5c0-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1458">kreditkartentyp</span></span>
- <span data-ttu-id="2e5c0-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1459">eigentümername</span></span>
- <span data-ttu-id="2e5c0-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1460">kartennr</span></span> 
- <span data-ttu-id="2e5c0-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1461">kartennummer</span></span>
- <span data-ttu-id="2e5c0-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1462">kreditkartennummer</span></span>
- <span data-ttu-id="2e5c0-1463">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="2e5c0-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1464">carta di credito</span></span>
- <span data-ttu-id="2e5c0-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1465">carta credito</span></span>
- <span data-ttu-id="2e5c0-1466">Carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1466">carta</span></span>
- <span data-ttu-id="2e5c0-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1467">n carta</span></span>
- <span data-ttu-id="2e5c0-1468">Nr.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1468">nr.</span></span> <span data-ttu-id="2e5c0-1469">Carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1469">carta</span></span>
- <span data-ttu-id="2e5c0-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1470">nr carta</span></span>
- <span data-ttu-id="2e5c0-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1471">numero carta</span></span>
- <span data-ttu-id="2e5c0-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1472">numero della carta</span></span>
- <span data-ttu-id="2e5c0-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1473">numero di carta</span></span>
- <span data-ttu-id="2e5c0-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1474">tarjeta credito</span></span>
- <span data-ttu-id="2e5c0-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1475">tarjeta de credito</span></span>
- <span data-ttu-id="2e5c0-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1476">tarjeta crédito</span></span>
- <span data-ttu-id="2e5c0-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="2e5c0-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1478">tarjeta de atm</span></span>
- <span data-ttu-id="2e5c0-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1479">tarjeta atm</span></span>
- <span data-ttu-id="2e5c0-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1480">tarjeta debito</span></span>
- <span data-ttu-id="2e5c0-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1481">tarjeta de debito</span></span>
- <span data-ttu-id="2e5c0-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1482">tarjeta débito</span></span>
- <span data-ttu-id="2e5c0-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1483">tarjeta de débito</span></span>
- <span data-ttu-id="2e5c0-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1484">nº de tarjeta</span></span>
- <span data-ttu-id="2e5c0-1485">Nein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1485">no.</span></span> <span data-ttu-id="2e5c0-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1486">de tarjeta</span></span>
- <span data-ttu-id="2e5c0-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1487">no de tarjeta</span></span>
- <span data-ttu-id="2e5c0-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1488">numero de tarjeta</span></span>
- <span data-ttu-id="2e5c0-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1489">número de tarjeta</span></span>
- <span data-ttu-id="2e5c0-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1490">tarjeta no</span></span>
- <span data-ttu-id="2e5c0-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1491">tarjetahabiente</span></span>
- <span data-ttu-id="2e5c0-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1492">cartão de crédito</span></span>
- <span data-ttu-id="2e5c0-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1493">cartão de credito</span></span>
- <span data-ttu-id="2e5c0-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1494">cartao de crédito</span></span>
- <span data-ttu-id="2e5c0-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1495">cartao de credito</span></span>
- <span data-ttu-id="2e5c0-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1496">cartão de débito</span></span>
- <span data-ttu-id="2e5c0-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1497">cartao de débito</span></span>
- <span data-ttu-id="2e5c0-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1498">cartão de debito</span></span>
- <span data-ttu-id="2e5c0-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1499">cartao de debito</span></span>
- <span data-ttu-id="2e5c0-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1500">débito automático</span></span>
- <span data-ttu-id="2e5c0-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1501">debito automatico</span></span>
- <span data-ttu-id="2e5c0-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1502">número do cartão</span></span>
- <span data-ttu-id="2e5c0-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1503">numero do cartão</span></span> 
- <span data-ttu-id="2e5c0-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1504">número do cartao</span></span>
- <span data-ttu-id="2e5c0-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1505">numero do cartao</span></span>
- <span data-ttu-id="2e5c0-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1506">número de cartão</span></span>
- <span data-ttu-id="2e5c0-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1507">numero de cartão</span></span>
- <span data-ttu-id="2e5c0-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1508">número de cartao</span></span>
- <span data-ttu-id="2e5c0-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1509">numero de cartao</span></span>
- <span data-ttu-id="2e5c0-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1510">nº do cartão</span></span>
- <span data-ttu-id="2e5c0-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1511">nº do cartao</span></span>
- <span data-ttu-id="2e5c0-1512">nº.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1512">nº.</span></span> <span data-ttu-id="2e5c0-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1513">do cartão</span></span>
- <span data-ttu-id="2e5c0-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1514">no do cartão</span></span>
- <span data-ttu-id="2e5c0-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1515">no do cartao</span></span>
- <span data-ttu-id="2e5c0-1516">Nein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1516">no.</span></span> <span data-ttu-id="2e5c0-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1517">do cartão</span></span>
- <span data-ttu-id="2e5c0-1518">Nein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1518">no.</span></span> <span data-ttu-id="2e5c0-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="2e5c0-1520">	Kroatien – Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1521">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1521">Format</span></span>

<span data-ttu-id="2e5c0-1522">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1523">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1523">Pattern</span></span>

<span data-ttu-id="2e5c0-1524">Neun aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1525">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1525">Checksum</span></span>

<span data-ttu-id="2e5c0-1526">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1527">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1527">Definition</span></span>

<span data-ttu-id="2e5c0-1528">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1529">Die Funktion Func_croatia_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1530">Ein Schlüsselwort aus Keyword_croatia_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-1531">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="2e5c0-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="2e5c0-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1533">Croatian identity card</span></span>
- <span data-ttu-id="2e5c0-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="2e5c0-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1536">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1536">Format</span></span>

<span data-ttu-id="2e5c0-1537">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1538">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1538">Pattern</span></span>

<span data-ttu-id="2e5c0-1539">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1539">11 digits:</span></span>
- <span data-ttu-id="2e5c0-1540">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1540">10 digits</span></span> 
- <span data-ttu-id="2e5c0-1541">Letzte Ziffer ist eine Prüfziffer für den Zweck des internationalen Datenaustauschs, die Buchstaben HR werden vor den elf Ziffern hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1542">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1542">Checksum</span></span>

<span data-ttu-id="2e5c0-1543">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1544">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1544">Definition</span></span>

<span data-ttu-id="2e5c0-1545">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1546">Die Funktion Func_croatia_oib_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1547">Ein Schlüsselwort aus Keyword_croatia_oib_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="2e5c0-1548">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1548">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-1549">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1550">Die Funktion Func_croatia_oib_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1551">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-1552">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="2e5c0-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="2e5c0-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1554">Personal Identification Number</span></span>
- <span data-ttu-id="2e5c0-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="2e5c0-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="2e5c0-1557">Tschechische Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1558">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1558">Format</span></span>

<span data-ttu-id="2e5c0-1559">Neun Ziffern mit optionalem Schrägstrich (altes Format) 10 Ziffern mit optionalem Schrägstrich (neues Format)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1560">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1560">Pattern</span></span>

<span data-ttu-id="2e5c0-1561">Neun Ziffern (altes Format):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="2e5c0-1562">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1562">Nine digits</span></span>

<span data-ttu-id="2e5c0-1563">ODER</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1563">OR</span></span>

- <span data-ttu-id="2e5c0-1564">Sechs Ziffern, die das Geburtsdatum darstellen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="2e5c0-1565">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-1565">A forward slash</span></span>
- <span data-ttu-id="2e5c0-1566">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1566">Three digits</span></span>

<span data-ttu-id="2e5c0-1567">10 Ziffern (neues Format):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1567">10 digits (new format):</span></span>
- <span data-ttu-id="2e5c0-1568">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1568">10 digits</span></span>

<span data-ttu-id="2e5c0-1569">ODER</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1569">OR</span></span>

- <span data-ttu-id="2e5c0-1570">Sechs Ziffern, die das Geburtsdatum darstellen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="2e5c0-1571">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-1571">A forward slash</span></span> 
- <span data-ttu-id="2e5c0-1572">Vier Ziffern, wobei die letzte Ziffer eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1573">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1573">Checksum</span></span>

<span data-ttu-id="2e5c0-1574">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1575">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1575">Definition</span></span>

<span data-ttu-id="2e5c0-1576">Eine DLP-Richtlinie ist 85% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_czech_id_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="2e5c0-1577">Ein Schlüsselwort aus Keyword_czech_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="2e5c0-1578">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="2e5c0-1579">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1579">Keywords</span></span>

- <span data-ttu-id="2e5c0-1580">Tschechische Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1580">czech personal identity number</span></span>
- <span data-ttu-id="2e5c0-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="2e5c0-1582">	Dänemark – Persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1583">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1583">Format</span></span>

<span data-ttu-id="2e5c0-1584">10 Ziffern, die einen Bindestrich enthalten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1585">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1585">Pattern</span></span>

<span data-ttu-id="2e5c0-1586">10 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1586">10 digits:</span></span>
- <span data-ttu-id="2e5c0-1587">Sechs Ziffern im Format TTMMJJ, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="2e5c0-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="2e5c0-1588">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-1588">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-1589">Vier Ziffern, bei denen die letzte Ziffer eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1590">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1590">Checksum</span></span>

<span data-ttu-id="2e5c0-1591">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1592">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1592">Definition</span></span>

<span data-ttu-id="2e5c0-1593">Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: der reguläre Ausdruck Regex_denmark_id findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="2e5c0-1594">Ein Schlüsselwort aus Keyword_denmark_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="2e5c0-1595">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-1596">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="2e5c0-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="2e5c0-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1598">Personal Identification Number</span></span>
- <span data-ttu-id="2e5c0-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1599">CPR</span></span>
- <span data-ttu-id="2e5c0-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="2e5c0-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="2e5c0-1602">Drug Enforcement Agency (DEA)-Nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1603">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1603">Format</span></span>

<span data-ttu-id="2e5c0-1604">Zwei Buchstaben gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1605">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1605">Pattern</span></span>

<span data-ttu-id="2e5c0-1606">Das Muster muss Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="2e5c0-1607">Einen Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) aus der folgenden Gruppe möglicher Buchstaben: abcdefghjklmnprstux, was einem Registrantencode entspricht</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="2e5c0-1608">Ein Buchstabe (bei dem die Groß-und Kleinschreibung nicht beachtet wird), der dem ersten Buchstaben des Nachnamens des Registrants entspricht</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="2e5c0-1609">Sieben Ziffern, von denen die letzte die Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1610">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1610">Checksum</span></span>

<span data-ttu-id="2e5c0-1611">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1612">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1612">Definition</span></span>

<span data-ttu-id="2e5c0-1613">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1614">Die Funktion Func_dea_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1615">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-1616">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1616">Keywords</span></span>

<span data-ttu-id="2e5c0-1617">Keine</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="2e5c0-1618">EU Debit Card-Nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1619">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1619">Format</span></span>

<span data-ttu-id="2e5c0-1620">16 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1621">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1621">Pattern</span></span>

<span data-ttu-id="2e5c0-1622">Sehr komplexes und robustes Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1623">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1623">Checksum</span></span>

<span data-ttu-id="2e5c0-1624">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1625">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1625">Definition</span></span>

<span data-ttu-id="2e5c0-1626">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1627">Die Funktion Func_eu_debit_card findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1628">Mindestens eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="2e5c0-1629">Ein Schlüsselwort aus Keyword_eu_debit_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="2e5c0-1630">Ein Schlüsselwort aus Keyword_card_terms_dict wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="2e5c0-1631">Ein Schlüsselwort aus Keyword_card_security_terms_dict wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="2e5c0-1632">Ein Schlüsselwort aus Keyword_card_expiration_terms_dict wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="2e5c0-1633">Die Funktion Func_expiration_date findet ein Datum im richtigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2e5c0-1634">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-1635">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="2e5c0-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="2e5c0-1637">account number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1637">account number</span></span> 
- <span data-ttu-id="2e5c0-1638">card number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1638">card number</span></span> 
- <span data-ttu-id="2e5c0-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1639">card no.</span></span> 
- <span data-ttu-id="2e5c0-1640">security number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1640">security number</span></span> 
- <span data-ttu-id="2e5c0-1641">CC #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="2e5c0-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="2e5c0-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1643">acct nbr</span></span> 
- <span data-ttu-id="2e5c0-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1644">acct num</span></span> 
- <span data-ttu-id="2e5c0-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1645">acct no</span></span> 
- <span data-ttu-id="2e5c0-1646">american express</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1646">american express</span></span> 
- <span data-ttu-id="2e5c0-1647">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1647">americanexpress</span></span> 
- <span data-ttu-id="2e5c0-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1648">americano espresso</span></span> 
- <span data-ttu-id="2e5c0-1649">Amex</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1649">amex</span></span> 
- <span data-ttu-id="2e5c0-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1650">atm card</span></span> 
- <span data-ttu-id="2e5c0-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1651">atm cards</span></span> 
- <span data-ttu-id="2e5c0-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1652">atm kaart</span></span> 
- <span data-ttu-id="2e5c0-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1653">atmcard</span></span> 
- <span data-ttu-id="2e5c0-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1654">atmcards</span></span> 
- <span data-ttu-id="2e5c0-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1655">atmkaart</span></span> 
- <span data-ttu-id="2e5c0-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1656">atmkaarten</span></span> 
- <span data-ttu-id="2e5c0-1657">Bancontact</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1657">bancontact</span></span> 
- <span data-ttu-id="2e5c0-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1658">bank card</span></span> 
- <span data-ttu-id="2e5c0-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1659">bankkaart</span></span> 
- <span data-ttu-id="2e5c0-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1660">card holder</span></span> 
- <span data-ttu-id="2e5c0-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1661">card holders</span></span> 
- <span data-ttu-id="2e5c0-1662">card num</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1662">card num</span></span> 
- <span data-ttu-id="2e5c0-1663">card number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1663">card number</span></span> 
- <span data-ttu-id="2e5c0-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1664">card numbers</span></span> 
- <span data-ttu-id="2e5c0-1665">card type</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1665">card type</span></span> 
- <span data-ttu-id="2e5c0-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1666">cardano numerico</span></span> 
- <span data-ttu-id="2e5c0-1667">Inhaber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1667">cardholder</span></span> 
- <span data-ttu-id="2e5c0-1668">Inhaber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1668">cardholders</span></span> 
- <span data-ttu-id="2e5c0-1669">cardNumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1669">cardnumber</span></span> 
- <span data-ttu-id="2e5c0-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1670">cardnumbers</span></span> 
- <span data-ttu-id="2e5c0-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1671">carta bianca</span></span> 
- <span data-ttu-id="2e5c0-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1672">carta credito</span></span> 
- <span data-ttu-id="2e5c0-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1673">carta di credito</span></span> 
- <span data-ttu-id="2e5c0-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1674">cartao de credito</span></span> 
- <span data-ttu-id="2e5c0-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1675">cartao de crédito</span></span> 
- <span data-ttu-id="2e5c0-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1676">cartao de debito</span></span> 
- <span data-ttu-id="2e5c0-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1677">cartao de débito</span></span> 
- <span data-ttu-id="2e5c0-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1678">carte bancaire</span></span> 
- <span data-ttu-id="2e5c0-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1679">carte blanche</span></span> 
- <span data-ttu-id="2e5c0-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1680">carte bleue</span></span> 
- <span data-ttu-id="2e5c0-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1681">carte de credit</span></span> 
- <span data-ttu-id="2e5c0-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1682">carte de crédit</span></span> 
- <span data-ttu-id="2e5c0-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1683">carte di credito</span></span> 
- <span data-ttu-id="2e5c0-1684">CarteBlanche</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1684">carteblanche</span></span> 
- <span data-ttu-id="2e5c0-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1685">cartão de credito</span></span> 
- <span data-ttu-id="2e5c0-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1686">cartão de crédito</span></span> 
- <span data-ttu-id="2e5c0-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1687">cartão de debito</span></span> 
- <span data-ttu-id="2e5c0-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1688">cartão de débito</span></span> 
- <span data-ttu-id="2e5c0-1689">cb</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1689">cb</span></span> 
- <span data-ttu-id="2e5c0-1690">Angaben</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1690">ccn</span></span> 
- <span data-ttu-id="2e5c0-1691">check card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1691">check card</span></span> 
- <span data-ttu-id="2e5c0-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1692">check cards</span></span> 
- <span data-ttu-id="2e5c0-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1693">checkcard</span></span>
- <span data-ttu-id="2e5c0-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1694">checkcards</span></span> 
- <span data-ttu-id="2e5c0-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1695">chequekaart</span></span> 
- <span data-ttu-id="2e5c0-1696">Cirrus</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1696">cirrus</span></span> 
- <span data-ttu-id="2e5c0-1697">Cirrus-EDC-Maestro</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="2e5c0-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1698">controlekaart</span></span> 
- <span data-ttu-id="2e5c0-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1699">controlekaarten</span></span> 
- <span data-ttu-id="2e5c0-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1700">credit card</span></span> 
- <span data-ttu-id="2e5c0-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1701">credit cards</span></span> 
- <span data-ttu-id="2e5c0-1702">CreditCard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1702">creditcard</span></span> 
- <span data-ttu-id="2e5c0-1703">creditCards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1703">creditcards</span></span> 
- <span data-ttu-id="2e5c0-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1704">debetkaart</span></span> 
- <span data-ttu-id="2e5c0-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1705">debetkaarten</span></span> 
- <span data-ttu-id="2e5c0-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1706">debit card</span></span> 
- <span data-ttu-id="2e5c0-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1707">debit cards</span></span> 
- <span data-ttu-id="2e5c0-1708">Debitkarte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1708">debitcard</span></span> 
- <span data-ttu-id="2e5c0-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1709">debitcards</span></span> 
- <span data-ttu-id="2e5c0-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1710">debito automatico</span></span> 
- <span data-ttu-id="2e5c0-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1711">diners club</span></span> 
- <span data-ttu-id="2e5c0-1712">DinersClub</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1712">dinersclub</span></span> 
- <span data-ttu-id="2e5c0-1713">ermitteln</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1713">discover</span></span> 
- <span data-ttu-id="2e5c0-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1714">discover card</span></span> 
- <span data-ttu-id="2e5c0-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1715">discover cards</span></span> 
- <span data-ttu-id="2e5c0-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1716">discovercard</span></span> 
- <span data-ttu-id="2e5c0-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1717">discovercards</span></span> 
- <span data-ttu-id="2e5c0-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1718">débito automático</span></span>
- <span data-ttu-id="2e5c0-1719">EDC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1719">edc</span></span> 
- <span data-ttu-id="2e5c0-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1720">eigentümername</span></span> 
- <span data-ttu-id="2e5c0-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1721">european debit card</span></span> 
- <span data-ttu-id="2e5c0-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1722">hoofdkaart</span></span> 
- <span data-ttu-id="2e5c0-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="2e5c0-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1724">in viaggio</span></span> 
- <span data-ttu-id="2e5c0-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1725">japanese card bureau</span></span> 
- <span data-ttu-id="2e5c0-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="2e5c0-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1727">jcb</span></span> 
- <span data-ttu-id="2e5c0-1728">Kaart</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1728">kaart</span></span> 
- <span data-ttu-id="2e5c0-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1729">kaart num</span></span> 
- <span data-ttu-id="2e5c0-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1730">kaartaantal</span></span> 
- <span data-ttu-id="2e5c0-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1731">kaartaantallen</span></span> 
- <span data-ttu-id="2e5c0-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1732">kaarthouder</span></span> 
- <span data-ttu-id="2e5c0-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1733">kaarthouders</span></span> 
- <span data-ttu-id="2e5c0-1734">Karte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1734">karte</span></span>  
- <span data-ttu-id="2e5c0-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1735">karteninhaber</span></span> 
- <span data-ttu-id="2e5c0-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1736">karteninhabers</span></span>
- <span data-ttu-id="2e5c0-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1737">kartennr</span></span> 
- <span data-ttu-id="2e5c0-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1738">kartennummer</span></span> 
- <span data-ttu-id="2e5c0-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1739">kreditkarte</span></span> 
- <span data-ttu-id="2e5c0-1740">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="2e5c0-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="2e5c0-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="2e5c0-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="2e5c0-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="2e5c0-1745">Maestro</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1745">maestro</span></span> 
- <span data-ttu-id="2e5c0-1746">master card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1746">master card</span></span> 
- <span data-ttu-id="2e5c0-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1747">master cards</span></span> 
- <span data-ttu-id="2e5c0-1748">MasterCard</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1748">mastercard</span></span> 
- <span data-ttu-id="2e5c0-1749">MasterCards gesichert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1749">mastercards</span></span> 
- <span data-ttu-id="2e5c0-1750">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1750">mc</span></span> 
- <span data-ttu-id="2e5c0-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1751">mister cash</span></span> 
- <span data-ttu-id="2e5c0-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1752">n carta</span></span> 
- <span data-ttu-id="2e5c0-1753">Carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1753">carta</span></span> 
- <span data-ttu-id="2e5c0-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1754">no de tarjeta</span></span> 
- <span data-ttu-id="2e5c0-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1755">no do cartao</span></span> 
- <span data-ttu-id="2e5c0-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1756">no do cartão</span></span> 
- <span data-ttu-id="2e5c0-1757">Nein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1757">no.</span></span> <span data-ttu-id="2e5c0-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1758">de tarjeta</span></span> 
- <span data-ttu-id="2e5c0-1759">Nein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1759">no.</span></span> <span data-ttu-id="2e5c0-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1760">do cartao</span></span> 
- <span data-ttu-id="2e5c0-1761">Nein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1761">no.</span></span> <span data-ttu-id="2e5c0-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1762">do cartão</span></span> 
- <span data-ttu-id="2e5c0-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1763">nr carta</span></span> 
- <span data-ttu-id="2e5c0-1764">Nr.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1764">nr.</span></span> <span data-ttu-id="2e5c0-1765">Carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1765">carta</span></span> 
- <span data-ttu-id="2e5c0-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1766">numeri di scheda</span></span> 
- <span data-ttu-id="2e5c0-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1767">numero carta</span></span> 
- <span data-ttu-id="2e5c0-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1768">numero de cartao</span></span> 
- <span data-ttu-id="2e5c0-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1769">numero de carte</span></span> 
- <span data-ttu-id="2e5c0-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1770">numero de cartão</span></span> 
- <span data-ttu-id="2e5c0-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1771">numero de tarjeta</span></span>
- <span data-ttu-id="2e5c0-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1772">numero della carta</span></span> 
- <span data-ttu-id="2e5c0-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1773">numero di carta</span></span> 
- <span data-ttu-id="2e5c0-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1774">numero di scheda</span></span> 
- <span data-ttu-id="2e5c0-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1775">numero do cartao</span></span> 
- <span data-ttu-id="2e5c0-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1776">numero do cartão</span></span> 
- <span data-ttu-id="2e5c0-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1777">numéro de carte</span></span> 
- <span data-ttu-id="2e5c0-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1778">nº carta</span></span> 
- <span data-ttu-id="2e5c0-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1779">nº de carte</span></span> 
- <span data-ttu-id="2e5c0-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1780">nº de la carte</span></span> 
- <span data-ttu-id="2e5c0-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="2e5c0-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1782">nº do cartao</span></span> 
- <span data-ttu-id="2e5c0-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1783">nº do cartão</span></span> 
- <span data-ttu-id="2e5c0-1784">nº.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1784">nº.</span></span> <span data-ttu-id="2e5c0-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1785">do cartão</span></span> 
- <span data-ttu-id="2e5c0-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1786">número de cartao</span></span> 
- <span data-ttu-id="2e5c0-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1787">número de cartão</span></span> 
- <span data-ttu-id="2e5c0-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1788">número de tarjeta</span></span> 
- <span data-ttu-id="2e5c0-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1789">número do cartao</span></span> 
- <span data-ttu-id="2e5c0-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="2e5c0-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="2e5c0-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="2e5c0-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1793">scheda della banca</span></span> 
- <span data-ttu-id="2e5c0-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1794">scheda di controllo</span></span> 
- <span data-ttu-id="2e5c0-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1795">scheda di debito</span></span> 
- <span data-ttu-id="2e5c0-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1796">scheda matrice</span></span> 
- <span data-ttu-id="2e5c0-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="2e5c0-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1798">schede di controllo</span></span> 
- <span data-ttu-id="2e5c0-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1799">schede di debito</span></span> 
- <span data-ttu-id="2e5c0-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1800">schede matrici</span></span> 
- <span data-ttu-id="2e5c0-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="2e5c0-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1802">scoprono le schede</span></span> 
- <span data-ttu-id="2e5c0-1803">Solo</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1803">solo</span></span> 
- <span data-ttu-id="2e5c0-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1804">supporti di scheda</span></span> 
- <span data-ttu-id="2e5c0-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1805">supporto di scheda</span></span> 
- <span data-ttu-id="2e5c0-1806">Schalter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1806">switch</span></span> 
- <span data-ttu-id="2e5c0-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1807">tarjeta atm</span></span> 
- <span data-ttu-id="2e5c0-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1808">tarjeta credito</span></span> 
- <span data-ttu-id="2e5c0-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="2e5c0-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="2e5c0-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="2e5c0-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1812">tarjeta debito</span></span> 
- <span data-ttu-id="2e5c0-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1813">tarjeta no</span></span>
- <span data-ttu-id="2e5c0-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="2e5c0-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1815">tipo della scheda</span></span> 
- <span data-ttu-id="2e5c0-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="2e5c0-1817">Scheda</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1817">scheda</span></span> 
- <span data-ttu-id="2e5c0-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1818">v pay</span></span> 
- <span data-ttu-id="2e5c0-1819">v-Pay</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1819">v-pay</span></span> 
- <span data-ttu-id="2e5c0-1820">Visa</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1820">visa</span></span> 
- <span data-ttu-id="2e5c0-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1821">visa plus</span></span> 
- <span data-ttu-id="2e5c0-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1822">visa electron</span></span> 
- <span data-ttu-id="2e5c0-1823">Visto</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1823">visto</span></span> 
- <span data-ttu-id="2e5c0-1824">Visum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1824">visum</span></span> 
- <span data-ttu-id="2e5c0-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="2e5c0-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="2e5c0-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1827">card identification number</span></span>
- <span data-ttu-id="2e5c0-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1828">card verification</span></span> 
- <span data-ttu-id="2e5c0-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1829">cardi la verifica</span></span> 
- <span data-ttu-id="2e5c0-1830">cid</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1830">cid</span></span> 
- <span data-ttu-id="2e5c0-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1831">cod seg</span></span> 
- <span data-ttu-id="2e5c0-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1832">cod seguranca</span></span> 
- <span data-ttu-id="2e5c0-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1833">cod segurança</span></span> 
- <span data-ttu-id="2e5c0-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1834">cod sicurezza</span></span> 
- <span data-ttu-id="2e5c0-1835">COD.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1835">cod.</span></span> <span data-ttu-id="2e5c0-1836">SEG</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1836">seg</span></span> 
- <span data-ttu-id="2e5c0-1837">COD.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1837">cod.</span></span> <span data-ttu-id="2e5c0-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1838">seguranca</span></span> 
- <span data-ttu-id="2e5c0-1839">COD.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1839">cod.</span></span> <span data-ttu-id="2e5c0-1840">Segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1840">segurança</span></span> 
- <span data-ttu-id="2e5c0-1841">COD.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1841">cod.</span></span> <span data-ttu-id="2e5c0-1842">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1842">sicurezza</span></span> 
- <span data-ttu-id="2e5c0-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="2e5c0-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1844">codice di verifica</span></span> 
- <span data-ttu-id="2e5c0-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1845">codigo</span></span> 
- <span data-ttu-id="2e5c0-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="2e5c0-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1847">codigo de segurança</span></span> 
- <span data-ttu-id="2e5c0-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1848">crittogramma</span></span> 
- <span data-ttu-id="2e5c0-1849">Kryptogramm</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1849">cryptogram</span></span> 
- <span data-ttu-id="2e5c0-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1850">cryptogramme</span></span> 
- <span data-ttu-id="2e5c0-1851">CV2</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1851">cv2</span></span> 
- <span data-ttu-id="2e5c0-1852">CVC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1852">cvc</span></span> 
- <span data-ttu-id="2e5c0-1853">CVC2</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1853">cvc2</span></span> 
- <span data-ttu-id="2e5c0-1854">CVN</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1854">cvn</span></span> 
- <span data-ttu-id="2e5c0-1855">CVV</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1855">cvv</span></span> 
- <span data-ttu-id="2e5c0-1856">CVV2</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1856">cvv2</span></span> 
- <span data-ttu-id="2e5c0-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1857">cód seguranca</span></span> 
- <span data-ttu-id="2e5c0-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1858">cód segurança</span></span> 
- <span data-ttu-id="2e5c0-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1859">cód.</span></span> <span data-ttu-id="2e5c0-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1860">seguranca</span></span> 
- <span data-ttu-id="2e5c0-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1861">cód.</span></span> <span data-ttu-id="2e5c0-1862">Segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1862">segurança</span></span> 
- <span data-ttu-id="2e5c0-1863">Código</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1863">código</span></span> 
- <span data-ttu-id="2e5c0-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1864">código de seguranca</span></span> 
- <span data-ttu-id="2e5c0-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1865">código de segurança</span></span> 
- <span data-ttu-id="2e5c0-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1866">de kaart controle</span></span> 
- <span data-ttu-id="2e5c0-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1867">geeft nr uit</span></span> 
- <span data-ttu-id="2e5c0-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1868">issue no</span></span> 
- <span data-ttu-id="2e5c0-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1869">issue number</span></span> 
- <span data-ttu-id="2e5c0-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="2e5c0-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="2e5c0-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="2e5c0-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1873">kwestieaantal</span></span> 
- <span data-ttu-id="2e5c0-1874">Nein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1874">no.</span></span> <span data-ttu-id="2e5c0-1875">Dell ' edizione</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1875">dell'edizione</span></span> 
- <span data-ttu-id="2e5c0-1876">Nein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1876">no.</span></span> <span data-ttu-id="2e5c0-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1877">di sicurezza</span></span> 
- <span data-ttu-id="2e5c0-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1878">numero de securite</span></span> 
- <span data-ttu-id="2e5c0-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1879">numero de verificacao</span></span> 
- <span data-ttu-id="2e5c0-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="2e5c0-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="2e5c0-1882">Scheda</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1882">scheda</span></span> 
- <span data-ttu-id="2e5c0-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="2e5c0-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="2e5c0-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="2e5c0-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="2e5c0-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1887">número de verificação</span></span> 
- <span data-ttu-id="2e5c0-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1888">perno il blocco</span></span> 
- <span data-ttu-id="2e5c0-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1889">pin block</span></span> 
- <span data-ttu-id="2e5c0-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1890">prufziffer</span></span> 
- <span data-ttu-id="2e5c0-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1891">prüfziffer</span></span> 
- <span data-ttu-id="2e5c0-1892">security code</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1892">security code</span></span> 
- <span data-ttu-id="2e5c0-1893">security no</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1893">security no</span></span> 
- <span data-ttu-id="2e5c0-1894">security number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1894">security number</span></span> 
- <span data-ttu-id="2e5c0-1895">Sicherheitskode</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1895">sicherheits kode</span></span> 
- <span data-ttu-id="2e5c0-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1896">sicherheitscode</span></span> 
- <span data-ttu-id="2e5c0-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="2e5c0-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1898">speldblok</span></span> 
- <span data-ttu-id="2e5c0-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1899">veiligheid nr</span></span> 
- <span data-ttu-id="2e5c0-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="2e5c0-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1901">veiligheidscode</span></span> 
- <span data-ttu-id="2e5c0-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="2e5c0-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="2e5c0-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="2e5c0-1905">Ablauf</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1905">ablauf</span></span> 
- <span data-ttu-id="2e5c0-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1906">data de expiracao</span></span> 
- <span data-ttu-id="2e5c0-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1907">data de expiração</span></span> 
- <span data-ttu-id="2e5c0-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1908">data del exp</span></span> 
- <span data-ttu-id="2e5c0-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1909">data di exp</span></span> 
- <span data-ttu-id="2e5c0-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1910">data di scadenza</span></span> 
- <span data-ttu-id="2e5c0-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1911">data em que expira</span></span> 
- <span data-ttu-id="2e5c0-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1912">data scad</span></span> 
- <span data-ttu-id="2e5c0-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1913">data scadenza</span></span> 
- <span data-ttu-id="2e5c0-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1914">date de validité</span></span> 
- <span data-ttu-id="2e5c0-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1915">datum afloop</span></span> 
- <span data-ttu-id="2e5c0-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1916">datum van exp</span></span> 
- <span data-ttu-id="2e5c0-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1917">de afloop</span></span> 
- <span data-ttu-id="2e5c0-1918">Espira</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1918">espira</span></span> 
- <span data-ttu-id="2e5c0-1919">Espira</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1919">espira</span></span> 
- <span data-ttu-id="2e5c0-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1920">exp date</span></span> 
- <span data-ttu-id="2e5c0-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1921">exp datum</span></span> 
- <span data-ttu-id="2e5c0-1922">Ablauf</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1922">expiration</span></span> 
- <span data-ttu-id="2e5c0-1923">ablaufen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1923">expire</span></span> 
- <span data-ttu-id="2e5c0-1924">abläuft</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1924">expires</span></span> 
- <span data-ttu-id="2e5c0-1925">Ablauf</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1925">expiry</span></span> 
- <span data-ttu-id="2e5c0-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="2e5c0-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1927">fecha de venc</span></span> 
- <span data-ttu-id="2e5c0-1928">Gultig bis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1928">gultig bis</span></span> 
- <span data-ttu-id="2e5c0-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="2e5c0-1930">Gültig bis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1930">gültig bis</span></span> 
- <span data-ttu-id="2e5c0-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="2e5c0-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1932">la scadenza</span></span> 
- <span data-ttu-id="2e5c0-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1933">scadenza</span></span> 
- <span data-ttu-id="2e5c0-1934">valable</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1934">valable</span></span> 
- <span data-ttu-id="2e5c0-1935">validade</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1935">validade</span></span> 
- <span data-ttu-id="2e5c0-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1936">valido hasta</span></span> 
- <span data-ttu-id="2e5c0-1937">Valor</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1937">valor</span></span> 
- <span data-ttu-id="2e5c0-1938">venc</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1938">venc</span></span> 
- <span data-ttu-id="2e5c0-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1939">vencimento</span></span> 
- <span data-ttu-id="2e5c0-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1940">vencimiento</span></span> 
- <span data-ttu-id="2e5c0-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1941">verloopt</span></span> 
- <span data-ttu-id="2e5c0-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1942">vervaldag</span></span> 
- <span data-ttu-id="2e5c0-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1943">vervaldatum</span></span> 
- <span data-ttu-id="2e5c0-1944">VTO</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1944">vto</span></span> 
- <span data-ttu-id="2e5c0-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="2e5c0-1946">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1946">EU Driver's License Number</span></span>

<span data-ttu-id="2e5c0-1947">Weitere Informationen finden Sie unter [EU-Führerscheinnummer vertraulicher Informationstyp](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="2e5c0-1948">EU-nationale Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1948">EU National Identification Number</span></span>

<span data-ttu-id="2e5c0-1949">Weitere Informationen finden Sie unter [sensible Informationstypen für die nationale Identifikationsnummer der EU](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="2e5c0-1950">EU-Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1950">EU Passport Number</span></span>

<span data-ttu-id="2e5c0-1951">Weitere Informationen finden Sie unter [sensible Informationstypen für EU-Passport-Nummern](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="2e5c0-1952">EU-Sozialversicherungsnummer oder gleichwertige ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="2e5c0-1953">Weitere Informationen finden Sie unter [EU-Sozialversicherungsnummer oder gleichwertiger ID-Typ für vertrauliche Informationen](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="2e5c0-1954">EU-Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="2e5c0-1955">Weitere Informationen finden Sie unter [vertraulicher Informationstyp der EU-Steueridentifikationsnummer](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="2e5c0-1956">Finland National ID (Finnischer Personalausweis)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1957">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1957">Format</span></span>

<span data-ttu-id="2e5c0-1958">Sechs Ziffern plus ein Zeichen, das ein Jahrhundert angibt, plus drei Ziffern plus einer Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1959">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1959">Pattern</span></span>

<span data-ttu-id="2e5c0-1960">Das Muster muss Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="2e5c0-1961">Sechs Ziffern im Format TTMMJJ, die ein Geburtsdatum darstellen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="2e5c0-1962">Jahrhundertkennzeichnung (entweder „-“, „+“ oder „a“)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="2e5c0-1963">Dreistellige persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="2e5c0-1964">Eine Ziffer oder ein Buchstabe (Groß-/Kleinschreibung irrelevant), die bzw. der eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1965">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1965">Checksum</span></span>

<span data-ttu-id="2e5c0-1966">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1967">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1967">Definition</span></span>

<span data-ttu-id="2e5c0-1968">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1969">Die Funktion Func_finnish_national_id findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1970">Ein Schlüsselwort aus Keyword_finnish_national_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="2e5c0-1971">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-1972">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1972">Keywords</span></span>

- <span data-ttu-id="2e5c0-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="2e5c0-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="2e5c0-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="2e5c0-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1976">Personbeteckning</span></span>
- <span data-ttu-id="2e5c0-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="2e5c0-1978">Finnland – Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1978">Finland Passport Number</span></span>

<span data-ttu-id="2e5c0-1979">Format Kombination von neun Buchstaben und Ziffern Muster Kombination aus neun Buchstaben und Ziffern: zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet) siebenstellige Prüfsumme keine Definition eine DLP-Richtlinie ist 75% zuversichtlich, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb eines Proximity of 300 Characters: der reguläre Ausdruck Regex_finland_passport_number findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="2e5c0-1980">Ein Schlüsselwort aus Keyword_finland_passport_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="2e5c0-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="2e5c0-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span></span>
<span data-ttu-id="2e5c0-1982">Schlüsselwörter Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="2e5c0-1983">Französische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-1984">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1984">Format</span></span>

<span data-ttu-id="2e5c0-1985">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-1986">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1986">Pattern</span></span>

<span data-ttu-id="2e5c0-1987">12 Ziffern mit Validierung, um ähnliche Muster ( z. B. französische Telefonnummern) auszuschließen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-1988">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1988">Checksum</span></span>

<span data-ttu-id="2e5c0-1989">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-1990">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1990">Definition</span></span>

<span data-ttu-id="2e5c0-1991">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-1992">Die Funktion Func_french_drivers_license findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-1993">Mindestens eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="2e5c0-1994">Ein Schlüsselwort aus Keyword_french_drivers_license wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="2e5c0-1995">Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-1996">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="2e5c0-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="2e5c0-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1998">drivers licence</span></span>
- <span data-ttu-id="2e5c0-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-1999">drivers license</span></span>
- <span data-ttu-id="2e5c0-2000">Führerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2000">driving licence</span></span>
- <span data-ttu-id="2e5c0-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2001">driving license</span></span>
- <span data-ttu-id="2e5c0-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2002">permis de conduire</span></span>
- <span data-ttu-id="2e5c0-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2003">licence number</span></span>
- <span data-ttu-id="2e5c0-2004">license number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2004">license number</span></span>
- <span data-ttu-id="2e5c0-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2005">licence numbers</span></span>
- <span data-ttu-id="2e5c0-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="2e5c0-2007">Französische Carte nationale d'identité (CNI)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2008">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2008">Format</span></span>

<span data-ttu-id="2e5c0-2009">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2010">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2010">Pattern</span></span>

<span data-ttu-id="2e5c0-2011">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2012">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2012">Checksum</span></span>

<span data-ttu-id="2e5c0-2013">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2014">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2014">Definition</span></span>

<span data-ttu-id="2e5c0-2015">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2016">Der reguläre Ausdruck Regex_france_cni findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2017">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2017">Keywords</span></span>

<span data-ttu-id="2e5c0-2018">Keine</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="2e5c0-2019">Französische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2020">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2020">Format</span></span>

<span data-ttu-id="2e5c0-2021">Neun Ziffern und Buchstaben</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2022">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2022">Pattern</span></span>

<span data-ttu-id="2e5c0-2023">Neun Ziffern und Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="2e5c0-2024">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2024">Two digits</span></span> 
- <span data-ttu-id="2e5c0-2025">Zwei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-2026">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2027">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2027">Checksum</span></span>

<span data-ttu-id="2e5c0-2028">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2029">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2029">Definition</span></span>

<span data-ttu-id="2e5c0-2030">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2031">Die Funktion Func_fr_passport findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2032">Ein Schlüsselwort aus Keyword_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2033">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="2e5c0-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2034">Keyword_passport</span></span>

- <span data-ttu-id="2e5c0-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2035">Passport Number</span></span>
- <span data-ttu-id="2e5c0-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2036">Passport No</span></span>
- <span data-ttu-id="2e5c0-2037">Passport#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2037">Passport #</span></span>
- <span data-ttu-id="2e5c0-2038">Pass #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2038">Passport#</span></span>
- <span data-ttu-id="2e5c0-2039">Passport-Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2039">PassportID</span></span>
- <span data-ttu-id="2e5c0-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2040">Passportno</span></span>
- <span data-ttu-id="2e5c0-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2041">passportnumber</span></span>
- <span data-ttu-id="2e5c0-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2042">パスポート</span></span>
- <span data-ttu-id="2e5c0-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2043">パスポート番号</span></span>
- <span data-ttu-id="2e5c0-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2044">パスポートのNum</span></span>
- <span data-ttu-id="2e5c0-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2045">パスポート ＃</span></span> 
- <span data-ttu-id="2e5c0-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2046">Numéro de passeport</span></span>
- <span data-ttu-id="2e5c0-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2047">Passeport n °</span></span>
- <span data-ttu-id="2e5c0-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2048">Passeport Non</span></span>
- <span data-ttu-id="2e5c0-2049">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2049">Passeport #</span></span>
- <span data-ttu-id="2e5c0-2050">Passeport #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2050">Passeport#</span></span>
- <span data-ttu-id="2e5c0-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2051">PasseportNon</span></span>
- <span data-ttu-id="2e5c0-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="2e5c0-2053">Französische Sozialversicherungsnummer (INSEE)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2054">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2054">Format</span></span>

<span data-ttu-id="2e5c0-2055">15 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2056">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2056">Pattern</span></span>

<span data-ttu-id="2e5c0-2057">Muss einem von zwei Mustern entsprechen:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="2e5c0-2058">13 Ziffern, gefolgt von einem Leerzeichen, gefolgt von zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="2e5c0-2059">oder</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2059">or</span></span>
- <span data-ttu-id="2e5c0-2060">15 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2061">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2061">Checksum</span></span>

<span data-ttu-id="2e5c0-2062">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2063">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2063">Definition</span></span>

<span data-ttu-id="2e5c0-2064">Eine DLP-Richtlinie ist zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2065">Die Funktion Func_french_insee oder Func_fr_insee findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2066">Ein Schlüsselwort aus Keyword_fr_insee wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="2e5c0-2067">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2067">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-2068">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2069">Die Funktion Func_french_insee oder Func_fr_insee findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2070">Es wurde kein Schlüsselwort aus Keyword_fr_insee gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="2e5c0-2071">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2072">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="2e5c0-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="2e5c0-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2074">insee</span></span>
- <span data-ttu-id="2e5c0-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2075">securité sociale</span></span>
- <span data-ttu-id="2e5c0-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2076">securite sociale</span></span>
- <span data-ttu-id="2e5c0-2077">national id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2077">national id</span></span>
- <span data-ttu-id="2e5c0-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2078">national identification</span></span>
- <span data-ttu-id="2e5c0-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2079">numéro d'identité</span></span>
- <span data-ttu-id="2e5c0-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2080">no d'identité</span></span>
- <span data-ttu-id="2e5c0-2081">Nein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2081">no.</span></span> <span data-ttu-id="2e5c0-2082">d ' identité</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2082">d'identité</span></span>
- <span data-ttu-id="2e5c0-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2083">numero d'identite</span></span>
- <span data-ttu-id="2e5c0-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2084">no d'identite</span></span>
- <span data-ttu-id="2e5c0-2085">Nein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2085">no.</span></span> <span data-ttu-id="2e5c0-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2086">d'identite</span></span>
- <span data-ttu-id="2e5c0-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2087">social security number</span></span>
- <span data-ttu-id="2e5c0-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2088">social security code</span></span>
- <span data-ttu-id="2e5c0-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2089">social insurance number</span></span>
- <span data-ttu-id="2e5c0-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="2e5c0-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2091">d'identité nationale</span></span>
- <span data-ttu-id="2e5c0-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="2e5c0-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="2e5c0-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="2e5c0-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2095">numéro de sécu</span></span>
- <span data-ttu-id="2e5c0-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="2e5c0-2097">Deutsche Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2098">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2098">Format</span></span>

<span data-ttu-id="2e5c0-2099">Kombination von 11 Ziffern und Buchstaben</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2100">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2100">Pattern</span></span>

<span data-ttu-id="2e5c0-2101">11 Zahlen und Buchstaben (ohne Beachtung der Groß-/Kleinschreibung):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="2e5c0-2102">Eine Ziffer oder ein Buchstabe</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2102">A digit or letter</span></span> 
- <span data-ttu-id="2e5c0-2103">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2103">Two digits</span></span> 
- <span data-ttu-id="2e5c0-2104">Sechs Ziffern oder Buchstaben</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2104">Six digits or letters</span></span> 
- <span data-ttu-id="2e5c0-2105">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2105">A digit</span></span> 
- <span data-ttu-id="2e5c0-2106">Eine Ziffer oder ein Buchstabe</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2107">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2107">Checksum</span></span>

<span data-ttu-id="2e5c0-2108">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2109">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2109">Definition</span></span>

<span data-ttu-id="2e5c0-2110">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2111">Die Funktion Func_german_drivers_license findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2112">Mindestens eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="2e5c0-2113">Ein Schlüsselwort aus Keyword_german_drivers_license_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="2e5c0-2114">Ein Schlüsselwort aus Keyword_german_drivers_license_collaborative wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="2e5c0-2115">Ein Schlüsselwort aus Keyword_german_drivers_license wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="2e5c0-2116">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2117">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="2e5c0-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="2e5c0-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2119">Führerschein</span></span>
- <span data-ttu-id="2e5c0-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2120">Fuhrerschein</span></span>
- <span data-ttu-id="2e5c0-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2121">Fuehrerschein</span></span>
- <span data-ttu-id="2e5c0-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="2e5c0-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="2e5c0-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="2e5c0-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2125">Führerschein-</span></span> 
- <span data-ttu-id="2e5c0-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="2e5c0-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="2e5c0-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="2e5c0-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="2e5c0-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="2e5c0-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="2e5c0-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="2e5c0-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="2e5c0-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="2e5c0-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="2e5c0-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="2e5c0-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="2e5c0-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="2e5c0-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="2e5c0-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="2e5c0-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="2e5c0-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="2e5c0-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="2e5c0-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="2e5c0-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="2e5c0-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="2e5c0-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="2e5c0-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="2e5c0-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="2e5c0-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="2e5c0-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="2e5c0-2152">DL</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2152">DL</span></span> 
- <span data-ttu-id="2e5c0-2153">DLS</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2153">DLS</span></span>
- <span data-ttu-id="2e5c0-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2154">Driv Lic</span></span> 
- <span data-ttu-id="2e5c0-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2155">Driv Licen</span></span> 
- <span data-ttu-id="2e5c0-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2156">Driv License</span></span>
- <span data-ttu-id="2e5c0-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2157">Driv Licenses</span></span> 
- <span data-ttu-id="2e5c0-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2158">Driv Licence</span></span> 
- <span data-ttu-id="2e5c0-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2159">Driv Licences</span></span> 
- <span data-ttu-id="2e5c0-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2160">Driv Lic</span></span> 
- <span data-ttu-id="2e5c0-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2161">Driver Licen</span></span> 
- <span data-ttu-id="2e5c0-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2162">Driver License</span></span> 
- <span data-ttu-id="2e5c0-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2163">Driver Licenses</span></span> 
- <span data-ttu-id="2e5c0-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2164">Driver Licence</span></span> 
- <span data-ttu-id="2e5c0-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2165">Driver Licences</span></span> 
- <span data-ttu-id="2e5c0-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2166">Drivers Lic</span></span> 
- <span data-ttu-id="2e5c0-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2167">Drivers Licen</span></span> 
- <span data-ttu-id="2e5c0-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2168">Drivers License</span></span> 
- <span data-ttu-id="2e5c0-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="2e5c0-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2170">Drivers Licence</span></span> 
- <span data-ttu-id="2e5c0-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2171">Drivers Licences</span></span> 
- <span data-ttu-id="2e5c0-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2172">Driver's Lic</span></span> 
- <span data-ttu-id="2e5c0-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2173">Driver's Licen</span></span> 
- <span data-ttu-id="2e5c0-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2174">Driver's License</span></span> 
- <span data-ttu-id="2e5c0-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="2e5c0-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2176">Driver's Licence</span></span> 
- <span data-ttu-id="2e5c0-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2177">Driver's Licences</span></span> 
- <span data-ttu-id="2e5c0-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2178">Driving Lic</span></span> 
- <span data-ttu-id="2e5c0-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2179">Driving Licen</span></span> 
- <span data-ttu-id="2e5c0-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2180">Driving License</span></span> 
- <span data-ttu-id="2e5c0-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2181">Driving Licenses</span></span> 
- <span data-ttu-id="2e5c0-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2182">Driving Licence</span></span> 
- <span data-ttu-id="2e5c0-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="2e5c0-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="2e5c0-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="2e5c0-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="2e5c0-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="2e5c0-2188">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2188">No-Führerschein</span></span> 
- <span data-ttu-id="2e5c0-2189">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="2e5c0-2190">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="2e5c0-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2191">N-Führerschein</span></span> 
- <span data-ttu-id="2e5c0-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="2e5c0-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="2e5c0-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="2e5c0-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="2e5c0-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="2e5c0-2197">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2197">No-Führerschein</span></span> 
- <span data-ttu-id="2e5c0-2198">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="2e5c0-2199">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="2e5c0-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2200">N-Führerschein</span></span> 
- <span data-ttu-id="2e5c0-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="2e5c0-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="2e5c0-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="2e5c0-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="2e5c0-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2205">ausstellungsort</span></span>
- <span data-ttu-id="2e5c0-2206">Ausstellende Behöde</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2206">ausstellende behöde</span></span>
- <span data-ttu-id="2e5c0-2207">Ausstellende Behorde</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2207">ausstellende behorde</span></span>
- <span data-ttu-id="2e5c0-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="2e5c0-2209">Deutsche Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2210">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2210">Format</span></span>

<span data-ttu-id="2e5c0-2211">10 Ziffern oder Buchstaben</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2212">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2212">Pattern</span></span>

<span data-ttu-id="2e5c0-2213">Das Muster muss Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="2e5c0-2214">Das erste Zeichen ist eine Ziffer oder ein Buchstabe aus dieser Gruppe (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="2e5c0-2215">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2215">Three digits</span></span> 
- <span data-ttu-id="2e5c0-2216">Fünf Ziffern oder Buchstaben aus dieser Gruppe (C -H, J-N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="2e5c0-2217">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2218">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2218">Checksum</span></span>

<span data-ttu-id="2e5c0-2219">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2220">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2220">Definition</span></span>

<span data-ttu-id="2e5c0-2221">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2222">Die Funktion Func_german_passport findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2223">Ein Schlüsselwort aus einer der fünf Schlüsselwortlisten wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="2e5c0-2224">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2224">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-2225">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2226">Die Funktion Func_german_passport_data findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2227">Ein Schlüsselwort aus einer der fünf Schlüsselwortlisten wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="2e5c0-2228">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2229">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="2e5c0-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="2e5c0-2231">Reisepass</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2231">reisepass</span></span>
- <span data-ttu-id="2e5c0-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2232">reisepasse</span></span>
- <span data-ttu-id="2e5c0-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2233">reisepassnummer</span></span>
- <span data-ttu-id="2e5c0-2234">Pass</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2234">passport</span></span>
- <span data-ttu-id="2e5c0-2235">Pässe</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="2e5c0-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="2e5c0-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2237">geburtsdatum</span></span>
- <span data-ttu-id="2e5c0-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="2e5c0-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="2e5c0-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="2e5c0-2241">No-Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="2e5c0-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="2e5c0-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="2e5c0-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="2e5c0-2245">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="2e5c0-2246">Deutsche Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2247">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2247">Format</span></span>

<span data-ttu-id="2e5c0-2248">Seit dem 1. November 2010: neun Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="2e5c0-2249">Vom 1. April 1987 bis 31. Oktober 2010:10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2250">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2250">Pattern</span></span>

<span data-ttu-id="2e5c0-2251">Seit 1. November 2010:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="2e5c0-2252">Ein Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-2253">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2253">Eight digits</span></span>

<span data-ttu-id="2e5c0-2254">Vom 1. April 1987 bis 31. Oktober 2010:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="2e5c0-2255">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2256">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2256">Checksum</span></span>

<span data-ttu-id="2e5c0-2257">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2258">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2258">Definition</span></span>

<span data-ttu-id="2e5c0-2259">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2260">Der reguläre Ausdruck Regex_germany_id_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2261">Ein Schlüsselwort aus Keyword_germany_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2262">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="2e5c0-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="2e5c0-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2264">Identity Card</span></span>
- <span data-ttu-id="2e5c0-2265">ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2265">ID</span></span>
- <span data-ttu-id="2e5c0-2266">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2266">Identification</span></span>
- <span data-ttu-id="2e5c0-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2267">Personalausweis</span></span>
- <span data-ttu-id="2e5c0-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="2e5c0-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2269">Ausweis</span></span>
- <span data-ttu-id="2e5c0-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="2e5c0-2271">Griechenland – Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2272">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2272">Format</span></span>

<span data-ttu-id="2e5c0-2273">Kombination von 7-8 Buchstaben und Zahlen plus einem Gedankenstrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2274">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2274">Pattern</span></span>

<span data-ttu-id="2e5c0-2275">Sieben Buchstaben und Zahlen (altes Format):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="2e5c0-2276">Ein Buchstabe (jeder Buchstabe des griechischen Alphabets) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="2e5c0-2277">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2277">A dash</span></span> 
- <span data-ttu-id="2e5c0-2278">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2278">Six digits</span></span>

<span data-ttu-id="2e5c0-2279">Acht Buchstaben und Zahlen (neues Format):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="2e5c0-2280">Zwei Buchstaben, deren Großbuchstabe sowohl im griechischen als auch lateinischen Alphabet (ABEZHIKMNOPTYX) vorkommt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="2e5c0-2281">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2281">A dash</span></span> 
- <span data-ttu-id="2e5c0-2282">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2283">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2283">Checksum</span></span>

<span data-ttu-id="2e5c0-2284">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2285">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2285">Definition</span></span>

<span data-ttu-id="2e5c0-2286">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2287">Der reguläre Ausdruck Regex_greece_id_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2288">Ein Schlüsselwort aus Keyword_greece_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2289">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="2e5c0-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="2e5c0-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2291">Greek identity Card</span></span>
- <span data-ttu-id="2e5c0-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2292">Tautotita</span></span>
- <span data-ttu-id="2e5c0-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="2e5c0-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="2e5c0-2295">Hongkong (HKID) - Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2296">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2296">Format</span></span>

<span data-ttu-id="2e5c0-2297">Kombination aus 8-9Buchstaben und Zahlen sowie optionale Klammern um das letzte Zeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2298">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2298">Pattern</span></span>

<span data-ttu-id="2e5c0-2299">Kombination aus Buchstaben 8-9 Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="2e5c0-2300">1-2 Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-2301">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2301">Six digits</span></span> 
- <span data-ttu-id="2e5c0-2302">Das letzte Zeichen (eine Ziffer oder der Buchstabe A), bei dem es sich um die Prüfziffer handelt, die optional in Klammern eingeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2303">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2303">Checksum</span></span>

<span data-ttu-id="2e5c0-2304">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2305">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2305">Definition</span></span>

<span data-ttu-id="2e5c0-2306">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2307">Die Funktion Func_hong_kong_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2308">Ein Schlüsselwort aus Keyword_hong_kong_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="2e5c0-2309">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2309">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-2310">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2311">Die Funktion Func_hong_kong_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2312">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2313">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="2e5c0-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="2e5c0-2315">Hong Kong Identity Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2315">hong kong identity card</span></span>
- <span data-ttu-id="2e5c0-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2316">HKIDC</span></span>
- <span data-ttu-id="2e5c0-2317">id card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2317">id card</span></span>
- <span data-ttu-id="2e5c0-2318">identity card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2318">identity card</span></span>
- <span data-ttu-id="2e5c0-2319">HK-Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2319">hk identity card</span></span>
- <span data-ttu-id="2e5c0-2320">Hong Kong-ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2320">hong kong id</span></span>
- <span data-ttu-id="2e5c0-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2321">香港身份證</span></span>
- <span data-ttu-id="2e5c0-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="2e5c0-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2323">身份證</span></span>
- <span data-ttu-id="2e5c0-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2324">身份証</span></span>
- <span data-ttu-id="2e5c0-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2325">身分證</span></span>
- <span data-ttu-id="2e5c0-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2326">身分証</span></span>
- <span data-ttu-id="2e5c0-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2327">香港身份証</span></span>
- <span data-ttu-id="2e5c0-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2328">香港身分證</span></span>
- <span data-ttu-id="2e5c0-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2329">香港身分証</span></span>
- <span data-ttu-id="2e5c0-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2330">香港身份證</span></span>
- <span data-ttu-id="2e5c0-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2331">香港居民身份證</span></span>
- <span data-ttu-id="2e5c0-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2332">香港居民身份証</span></span>
- <span data-ttu-id="2e5c0-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2333">香港居民身分證</span></span>
- <span data-ttu-id="2e5c0-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2334">香港居民身分証</span></span>
- <span data-ttu-id="2e5c0-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="2e5c0-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="2e5c0-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="2e5c0-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="2e5c0-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="2e5c0-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="2e5c0-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="2e5c0-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="2e5c0-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="2e5c0-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="2e5c0-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="2e5c0-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="2e5c0-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="2e5c0-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="2e5c0-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="2e5c0-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="2e5c0-2351">Indien – Permanente Kontonummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2352">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2352">Format</span></span>

<span data-ttu-id="2e5c0-2353">10 Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2354">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2354">Pattern</span></span>

<span data-ttu-id="2e5c0-2355">10 Buchstaben oder Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2355">10 letters or digits:</span></span>
- <span data-ttu-id="2e5c0-2356">Fünf Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-2357">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2357">Four digits</span></span> 
- <span data-ttu-id="2e5c0-2358">Ein Buchstabe, der eine alphabetische Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2359">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2359">Checksum</span></span>

<span data-ttu-id="2e5c0-2360">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2361">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2361">Definition</span></span>

<span data-ttu-id="2e5c0-2362">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2363">Der reguläre Ausdruck Regex_india_permanent_account_number findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2364">Ein Schlüsselwort aus Keyword_india_permanent_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="2e5c0-2365">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2366">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="2e5c0-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="2e5c0-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="2e5c0-2369">Schwenken</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="2e5c0-2370">Indien - Eindeutige Identifikationsnummer (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2371">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2371">Format</span></span>

<span data-ttu-id="2e5c0-2372">12 Ziffern mit optionalen Leerzeichen oder Bindestrichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2373">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2373">Pattern</span></span>

<span data-ttu-id="2e5c0-2374">12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2374">12 digits:</span></span>
- <span data-ttu-id="2e5c0-2375">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2375">Four digits</span></span> 
- <span data-ttu-id="2e5c0-2376">Eine optionales Leerzeichen oder ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2376">An optional space or dash</span></span> 
- <span data-ttu-id="2e5c0-2377">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2377">Four digits</span></span> 
- <span data-ttu-id="2e5c0-2378">Eine optionales Leerzeichen oder ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2378">An optional space or dash</span></span> 
- <span data-ttu-id="2e5c0-2379">Die letzte Ziffer, die eine Prüfziffer ist</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2380">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2380">Checksum</span></span>

<span data-ttu-id="2e5c0-2381">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2382">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2382">Definition</span></span>

<span data-ttu-id="2e5c0-2383">Eine DLP-Richtlinie ist 85% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_india_aadhaar findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="2e5c0-2384">Ein Schlüsselwort aus Keyword_india_aadhar wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="2e5c0-2385">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2385">The checksum passes.</span></span>
<span data-ttu-id="2e5c0-2386">Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_india_aadhaar findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="2e5c0-2387">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2387">The checksum passes.</span></span>
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
### <a name="keywords"></a><span data-ttu-id="2e5c0-2388">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="2e5c0-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="2e5c0-2390">Aadhar</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2390">Aadhar</span></span>
- <span data-ttu-id="2e5c0-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2391">Aadhaar</span></span>
- <span data-ttu-id="2e5c0-2392">UID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2392">UID</span></span>
- <span data-ttu-id="2e5c0-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="2e5c0-2394">Indonesien – Perosonalausweisnummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2395">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2395">Format</span></span>

<span data-ttu-id="2e5c0-2396">16 Ziffern mit optionalen Punkten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2397">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2397">Pattern</span></span>

<span data-ttu-id="2e5c0-2398">16 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2398">16 digits:</span></span>
- <span data-ttu-id="2e5c0-2399">Zweistelliger Provinzcode </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2399">Two-digit province code</span></span> 
- <span data-ttu-id="2e5c0-2400">Ein Punkt (optional) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2400">A period (optional)</span></span> 
- <span data-ttu-id="2e5c0-2401">Zweistelliger Regency- oder Stadtcode </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="2e5c0-2402">Zweistelliger Subdistrict-Code </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="2e5c0-2403">Ein Punkt (optional) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2403">A period (optional)</span></span> 
- <span data-ttu-id="2e5c0-2404">Sechs Ziffern im Format TTMMJJ, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="2e5c0-2405">Ein Punkt (optional) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2405">A period (optional)</span></span> 
- <span data-ttu-id="2e5c0-2406">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2407">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2407">Checksum</span></span>

<span data-ttu-id="2e5c0-2408">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2409">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2409">Definition</span></span>

<span data-ttu-id="2e5c0-2410">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2411">Der reguläre Ausdruck Regex_indonesia_id_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2412">Ein Schlüsselwort aus Keyword_indonesia_id_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="2e5c0-2413">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2414">Der reguläre Ausdruck Regex_indonesia_id_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2415">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="2e5c0-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="2e5c0-2417">KTP</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2417">KTP</span></span>
- <span data-ttu-id="2e5c0-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="2e5c0-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="2e5c0-2420">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2421">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2421">Format</span></span>

<span data-ttu-id="2e5c0-2422">Landesvorwahl (zwei Buchstaben) plus Prüfziffern (zwei Ziffern) plus BBAN-Nummer (bis zu 30 Zeichen)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2423">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2423">Pattern</span></span>

<span data-ttu-id="2e5c0-2424">Das Muster muss Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="2e5c0-2425">Landesvorwahl mit zwei Buchstaben</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2425">Two-letter country code</span></span>
- <span data-ttu-id="2e5c0-2426">Zwei Prüfziffern (gefolgt von einem optionalen Leerzeichen)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="2e5c0-2427">1-7 Gruppen von vier Buchstaben oder Ziffern (können durch Leerzeichengetrennt werden)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="2e5c0-2428">1 bis 3 Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2428">1-3 letters or digits</span></span>

<span data-ttu-id="2e5c0-2429">Das Format für jedes Land unterscheidet sich geringfügig.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2429">The format for each country is slightly different.</span></span> <span data-ttu-id="2e5c0-2430">Der Typ der IBAN-vertraulichen Informationen deckt diese 60 Länder ab:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2430">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="2e5c0-2431">AD, AE, Al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, Do, EE, es, fi, FO, Fr, GB, ge, GI, GL, GR, HR, HU, IE, IL, is, IT, kW, KZ, LB, Li, lt, LU, LV, MC, MD, me, MK, Mr, MT, mu , NL, No, PL, PT, RO, RS, Sa, SE, Si, SK, SM, TN, TR, VG</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2432">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2432">Checksum</span></span>

<span data-ttu-id="2e5c0-2433">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2434">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2434">Definition</span></span>

<span data-ttu-id="2e5c0-2435">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2436">Die Funktion Func_iban findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2437">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2438">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2438">Keywords</span></span>

<span data-ttu-id="2e5c0-2439">Keine</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="2e5c0-2440">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2441">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="2e5c0-2442">IPv4</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2442">IPv4:</span></span>
<span data-ttu-id="2e5c0-2443">Komplexes Muster, das formatierte (Punkte) und unformatierte (keine Punkte) Versionen der IPv4-Adressen angibt</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="2e5c0-2444">IPv6</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2444">IPv6:</span></span>
<span data-ttu-id="2e5c0-2445"> Komplexes Muster, das formatierte IPv6-Nummern angibt (schließt Doppelpunkte ein)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2446">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2447">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2447">Checksum</span></span>

<span data-ttu-id="2e5c0-2448">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2449">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2449">Definition</span></span>

<span data-ttu-id="2e5c0-2450">Für IPv6 ist eine DLP-Richtlinie zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2451">Der reguläre Ausdruck Regex_ipv6_address findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2452">Es wurde kein Schlüsselwort aus Keyword_ipaddress gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="2e5c0-2453">Für IPv4 ist eine DLP-Richtlinie zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2454">Der reguläre Ausdruck Regex_ipv4_address findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2455">Ein Schlüsselwort aus Keyword_ipaddress wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="2e5c0-2456">Für IPv6 ist eine DLP-Richtlinie zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2457">Der reguläre Ausdruck Regex_ipv6_address findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2458">Es wurde kein Schlüsselwort aus Keyword_ipaddress gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2458">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2459">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="2e5c0-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="2e5c0-2461">IP (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung unterschieden)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="2e5c0-2462">ip address</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2462">ip address</span></span> 
- <span data-ttu-id="2e5c0-2463">IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2463">ip addresses</span></span>
- <span data-ttu-id="2e5c0-2464">internet protocol</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2464">internet protocol</span></span>
- <span data-ttu-id="2e5c0-2465">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="2e5c0-2466">Internationale Klassifikation von Krankheiten (ICD-10-cm)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2467">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2467">Format</span></span>

<span data-ttu-id="2e5c0-2468">Wörterbuch</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2469">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2469">Pattern</span></span>

<span data-ttu-id="2e5c0-2470">Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2471">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2471">Checksum</span></span>

<span data-ttu-id="2e5c0-2472">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2473">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2473">Definition</span></span>

<span data-ttu-id="2e5c0-2474">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2475">Ein Schlüsselwort aus Dictionary_icd_10_updated wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="2e5c0-2476">Ein Schlüsselwort aus Dictionary_icd_10_codes wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="2e5c0-2477">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2478">Ein Schlüsselwort aus Dictionary_icd_10_ aktualisiert wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

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

<span data-ttu-id="2e5c0-2479">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2479">Keywords</span></span>

<span data-ttu-id="2e5c0-2480">Ein beliebiger Ausdruck aus dem Dictionary_icd_10_updated Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, zehnte Revision, klinische Änderung (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="2e5c0-2481">Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungs Codes.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="2e5c0-2482">Ein beliebiger Ausdruck aus dem Dictionary_icd_10_codes Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, zehnte Revision, klinische Änderung (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="2e5c0-2483">Dieser Typ sucht nur nach Versicherungs Codes, nicht nach der Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="2e5c0-2484">Internationale Klassifikation von Krankheiten (ICD-9-cm)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2485">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2485">Format</span></span>

<span data-ttu-id="2e5c0-2486">Wörterbuch</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2487">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2487">Pattern</span></span>

<span data-ttu-id="2e5c0-2488">Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2489">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2489">Checksum</span></span>

<span data-ttu-id="2e5c0-2490">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2491">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2491">Definition</span></span>

<span data-ttu-id="2e5c0-2492">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2493">Ein Schlüsselwort aus Dictionary_icd_9_updated wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="2e5c0-2494">Ein Schlüsselwort aus Dictionary_icd_9_codes wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="2e5c0-2495">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2496">Ein Schlüsselwort aus Dictionary_icd_9_updated wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2497">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2497">Keywords</span></span>

<span data-ttu-id="2e5c0-2498">Ein beliebiger Ausdruck aus dem Dictionary_icd_9_updated Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, neunte Revision, klinische Änderung (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="2e5c0-2499">Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungs Codes.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="2e5c0-2500">Ein beliebiger Ausdruck aus dem Dictionary_icd_9_codes Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, neunte Revision, klinische Änderung (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="2e5c0-2501">Dieser Typ sucht nur nach Versicherungs Codes, nicht nach der Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="2e5c0-2502">Irland – Personal Public Service-Nummer (PPS)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2503">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2503">Format</span></span>

<span data-ttu-id="2e5c0-2504">Altes Format (bis 31. Dez. 2012):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="2e5c0-2505">Sieben Ziffern, gefolgt von 1-2 Buchstaben </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="2e5c0-2506">Neues Format (1 Jan 2013 und danach):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="2e5c0-2507">Sieben Ziffern, gefolgt von zwei Buchstaben</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2508">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2508">Pattern</span></span>

<span data-ttu-id="2e5c0-2509">Altes Format (bis 31. Dez. 2012):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="2e5c0-2510">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2510">Seven digits</span></span> 
- <span data-ttu-id="2e5c0-2511">1-2 Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="2e5c0-2512">Neues Format (1 Jan 2013 und danach):</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="2e5c0-2513">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2513">Seven digits</span></span> 
- <span data-ttu-id="2e5c0-2514">Ein Buchstabe (Groß-/Kleinschreibung irrelevant), wobei es sich um eine alphabetische Prüfziffer handelt </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="2e5c0-2515">Die Buchstaben "A" oder "H" (Groß-/Kleinschreibung irrelevant)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2516">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2516">Checksum</span></span>

<span data-ttu-id="2e5c0-2517">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2518">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2518">Definition</span></span>

<span data-ttu-id="2e5c0-2519">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2520">Die Funktion Func_ireland_pps sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2521">Eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2521">One of the following is true:</span></span>
    - <span data-ttu-id="2e5c0-2522">Ein Schlüsselwort aus Keyword_ireland_pps wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="2e5c0-2523">Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2e5c0-2524">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2524">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-2525">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2526">Die Funktion Func_ireland_pps sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2527">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2527">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2528">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="2e5c0-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="2e5c0-2530">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="2e5c0-2531">PPS Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2531">PPS Number</span></span> 
- <span data-ttu-id="2e5c0-2532">PPS Num</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2532">PPS Num</span></span> 
- <span data-ttu-id="2e5c0-2533">PPS No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2533">PPS No.</span></span> 
- <span data-ttu-id="2e5c0-2534">PPS #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2534">PPS #</span></span> 
- <span data-ttu-id="2e5c0-2535">PPS #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2535">PPS#</span></span> 
- <span data-ttu-id="2e5c0-2536">PPSN</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2536">PPSN</span></span> 
- <span data-ttu-id="2e5c0-2537">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2537">Public Services Card</span></span> 
- <span data-ttu-id="2e5c0-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="2e5c0-2539">Uimh.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2539">Uimh.</span></span> <span data-ttu-id="2e5c0-2540">PSP</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2540">PSP</span></span> 
- <span data-ttu-id="2e5c0-2541">PSP</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="2e5c0-2542">Israelische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2543">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2543">Format</span></span>

<span data-ttu-id="2e5c0-2544">13 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2545">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2545">Pattern</span></span>

<span data-ttu-id="2e5c0-2546">Formatiert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2546">Formatted:</span></span>
- <span data-ttu-id="2e5c0-2547">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2547">Two digits</span></span> 
- <span data-ttu-id="2e5c0-2548">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2548">A dash</span></span> 
- <span data-ttu-id="2e5c0-2549">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2549">Three digits</span></span> 
- <span data-ttu-id="2e5c0-2550">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2550">A dash</span></span> 
- <span data-ttu-id="2e5c0-2551">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2551">Eight digits</span></span>

<span data-ttu-id="2e5c0-2552">Unformatiert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2552">Unformatted:</span></span>
- <span data-ttu-id="2e5c0-2553">	13 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2554">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2554">Checksum</span></span>

<span data-ttu-id="2e5c0-2555">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2556">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2556">Definition</span></span>

<span data-ttu-id="2e5c0-2557">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2558">Der reguläre Ausdruck Regex_israel_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2559">Ein Schlüsselwort aus Keyword_israel_bank_account_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2560">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="2e5c0-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="2e5c0-2562">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2562">Bank Account Number</span></span> 
- <span data-ttu-id="2e5c0-2563">Bank Account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2563">Bank Account</span></span> 
- <span data-ttu-id="2e5c0-2564">Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2564">Account Number</span></span> 
- <span data-ttu-id="2e5c0-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="2e5c0-2566">Israelische Ausweis-ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2567">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2567">Format</span></span>

<span data-ttu-id="2e5c0-2568">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2569">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2569">Pattern</span></span>

<span data-ttu-id="2e5c0-2570">Neun aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2571">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2571">Checksum</span></span>

<span data-ttu-id="2e5c0-2572">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2573">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2573">Definition</span></span>

<span data-ttu-id="2e5c0-2574">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2575">Die Funktion Func_israeli_national_id_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2576">Ein Schlüsselwort aus Keyword_Israel_National_ID wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="2e5c0-2577">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2577">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2578">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="2e5c0-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="2e5c0-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2580">מספר זהות</span></span> 
- <span data-ttu-id="2e5c0-2581">National ID Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="2e5c0-2582">Italienische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2583">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2583">Format</span></span>

<span data-ttu-id="2e5c0-2584">Eine Kombination von 10 Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2585">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2585">Pattern</span></span>

- <span data-ttu-id="2e5c0-2586">Eine Kombination aus 10 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="2e5c0-2587">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-2588">Der Buchstabe „A“ oder „W“ (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-2589">Sieben Buchstaben (ohne Beachtung der Groß-/Kleinschreibung), Ziffern oder der Unterstrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="2e5c0-2590">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2591">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2591">Checksum</span></span>

<span data-ttu-id="2e5c0-2592">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2593">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2593">Definition</span></span>

<span data-ttu-id="2e5c0-2594">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2595">Der reguläre Ausdruck Regex_italy_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2596">Ein Schlüsselwort aus Keyword_italy_drivers_license_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2597">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="2e5c0-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="2e5c0-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="2e5c0-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="2e5c0-2601">Japanische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2602">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2602">Format</span></span>

<span data-ttu-id="2e5c0-2603">Sieben oder acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2604">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2604">Pattern</span></span>

<span data-ttu-id="2e5c0-2605">Bankkontonummer:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2605">Bank account number:</span></span>
- <span data-ttu-id="2e5c0-2606">Sieben oder acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2606">Seven or eight digits</span></span>
- <span data-ttu-id="2e5c0-2607">Niederlassungscode der Bank:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2607">Bank account branch code:</span></span>
- <span data-ttu-id="2e5c0-2608">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2608">Four digits</span></span> 
- <span data-ttu-id="2e5c0-2609">Ein Leerzeichen oder ein Bindestrich (optional)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="2e5c0-2610">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2610">Three digits</span></span>

<span data-ttu-id="2e5c0-2611">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2611">Checksum</span></span>

<span data-ttu-id="2e5c0-2612">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2613">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2613">Definition</span></span>

<span data-ttu-id="2e5c0-2614">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2615">Die Funktion Func_jp_bank_account findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2616">Ein Schlüsselwort aus Keyword_jp_bank_account wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="2e5c0-2617">Eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2617">One of the following is true:</span></span>
- <span data-ttu-id="2e5c0-2618">Die Funktion Func_jp_bank_account_branch_code findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2619">Ein Schlüsselwort aus Keyword_jp_bank_branch_code wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="2e5c0-2620">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2621">Die Funktion Func_jp_bank_account findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2622">Ein Schlüsselwort aus Keyword_jp_bank_account wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2623">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="2e5c0-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="2e5c0-2625">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2625">Checking Account Number</span></span> 
- <span data-ttu-id="2e5c0-2626">Checking Account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2626">Checking Account</span></span> 
- <span data-ttu-id="2e5c0-2627">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2627">Checking Account #</span></span> 
- <span data-ttu-id="2e5c0-2628">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="2e5c0-2629">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2629">Checking Acct #</span></span> 
- <span data-ttu-id="2e5c0-2630">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="2e5c0-2631">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2631">Checking Account No.</span></span> 
- <span data-ttu-id="2e5c0-2632">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2632">Bank Account Number</span></span> 
- <span data-ttu-id="2e5c0-2633">Bank Account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2633">Bank Account</span></span> 
- <span data-ttu-id="2e5c0-2634">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2634">Bank Account #</span></span> 
- <span data-ttu-id="2e5c0-2635">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="2e5c0-2636">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2636">Bank Acct #</span></span> 
- <span data-ttu-id="2e5c0-2637">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="2e5c0-2638">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2638">Bank Account No.</span></span> 
- <span data-ttu-id="2e5c0-2639">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2639">Savings Account Number</span></span> 
- <span data-ttu-id="2e5c0-2640">Savings Account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2640">Savings Account</span></span> 
- <span data-ttu-id="2e5c0-2641">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2641">Savings Account #</span></span> 
- <span data-ttu-id="2e5c0-2642">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="2e5c0-2643">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2643">Savings Acct #</span></span> 
- <span data-ttu-id="2e5c0-2644">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="2e5c0-2645">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2645">Savings Account No.</span></span> 
- <span data-ttu-id="2e5c0-2646">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2646">Debit Account Number</span></span> 
- <span data-ttu-id="2e5c0-2647">Debit Account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2647">Debit Account</span></span> 
- <span data-ttu-id="2e5c0-2648">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2648">Debit Account #</span></span> 
- <span data-ttu-id="2e5c0-2649">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="2e5c0-2650">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2650">Debit Acct #</span></span> 
- <span data-ttu-id="2e5c0-2651">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="2e5c0-2652">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2652">Debit Account No.</span></span> 
- <span data-ttu-id="2e5c0-2653">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="2e5c0-2654">#アカウントの確認, 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="2e5c0-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="2e5c0-2656">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="2e5c0-2657">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2657">口座番号の確認</span></span> 
- <span data-ttu-id="2e5c0-2658">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2658">銀行口座番号</span></span> 
- <span data-ttu-id="2e5c0-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2659">銀行口座</span></span> 
- <span data-ttu-id="2e5c0-2660">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2660">銀行口座＃</span></span> 
- <span data-ttu-id="2e5c0-2661">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="2e5c0-2662">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="2e5c0-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="2e5c0-2664">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2664">銀行口座番号</span></span>
- <span data-ttu-id="2e5c0-2665">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="2e5c0-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2666">預金口座</span></span> 
- <span data-ttu-id="2e5c0-2667">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="2e5c0-2668">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="2e5c0-2669">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="2e5c0-2670">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="2e5c0-2671">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="2e5c0-2672">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="2e5c0-2673">口座番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2673">口座番号</span></span> 
- <span data-ttu-id="2e5c0-2674">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2674">口座番号＃</span></span> 
- <span data-ttu-id="2e5c0-2675">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="2e5c0-2676">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="2e5c0-2677">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="2e5c0-2678">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="2e5c0-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="2e5c0-2680">Otemachi</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="2e5c0-2681">Japanische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2682">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2682">Format</span></span>

<span data-ttu-id="2e5c0-2683">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2684">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2684">Pattern</span></span>

<span data-ttu-id="2e5c0-2685">12 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2686">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2686">Checksum</span></span>

<span data-ttu-id="2e5c0-2687">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2688">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2688">Definition</span></span>

<span data-ttu-id="2e5c0-2689">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2690">Die Funktion Func_jp_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2691">Ein Schlüsselwort aus Keyword_jp_drivers_license_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2692">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="2e5c0-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="2e5c0-2694">DL #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2694">dl#</span></span> 
- <span data-ttu-id="2e5c0-2695">DL</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2695">DL＃</span></span> 
- <span data-ttu-id="2e5c0-2696">DLS #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2696">dls#</span></span> 
- <span data-ttu-id="2e5c0-2697">DLS</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2697">DLS＃</span></span> 
- <span data-ttu-id="2e5c0-2698">driver license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2698">driver license</span></span> 
- <span data-ttu-id="2e5c0-2699">driver licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2699">driver licenses</span></span> 
- <span data-ttu-id="2e5c0-2700">drivers license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2700">drivers license</span></span> 
- <span data-ttu-id="2e5c0-2701">driver's license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2701">driver's license</span></span> 
- <span data-ttu-id="2e5c0-2702">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2702">drivers licenses</span></span> 
- <span data-ttu-id="2e5c0-2703">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2703">driver's licenses</span></span> 
- <span data-ttu-id="2e5c0-2704">driving licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2704">driving licence</span></span> 
- <span data-ttu-id="2e5c0-2705">lic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2705">lic#</span></span> 
- <span data-ttu-id="2e5c0-2706">LIC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2706">LIC＃</span></span> 
- <span data-ttu-id="2e5c0-2707">LiCS #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2707">lics#</span></span> 
- <span data-ttu-id="2e5c0-2708">state id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2708">state id</span></span> 
- <span data-ttu-id="2e5c0-2709">state identification</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2709">state identification</span></span> 
- <span data-ttu-id="2e5c0-2710">state identification number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2710">state identification number</span></span> 
- <span data-ttu-id="2e5c0-2711">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2711">低所得国＃</span></span> 
- <span data-ttu-id="2e5c0-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2712">免許証</span></span> 
- <span data-ttu-id="2e5c0-2713">状態ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2713">状態ID</span></span>
- <span data-ttu-id="2e5c0-2714">状態の識別</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2714">状態の識別</span></span> 
- <span data-ttu-id="2e5c0-2715">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2715">状態の識別番号</span></span> 
- <span data-ttu-id="2e5c0-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2716">運転免許</span></span> 
- <span data-ttu-id="2e5c0-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2717">運転免許証</span></span> 
- <span data-ttu-id="2e5c0-2718">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="2e5c0-2719">Japanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2720">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2720">Format</span></span>

<span data-ttu-id="2e5c0-2721">Zwei Buchstaben gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2722">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2722">Pattern</span></span>

<span data-ttu-id="2e5c0-2723">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2724">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2724">Checksum</span></span>

<span data-ttu-id="2e5c0-2725">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2726">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2726">Definition</span></span>

<span data-ttu-id="2e5c0-2727">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2728">Die Funktion Func_jp_passport findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2729">Ein Schlüsselwort aus Keyword_jp_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2730">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="2e5c0-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="2e5c0-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2732">パスポート</span></span> 
- <span data-ttu-id="2e5c0-2733">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2733">パスポート番号</span></span> 
- <span data-ttu-id="2e5c0-2734">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2734">パスポートのNum</span></span> 
- <span data-ttu-id="2e5c0-2735">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="2e5c0-2736">Japanische Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2737">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2737">Format</span></span>

<span data-ttu-id="2e5c0-2738">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2739">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2739">Pattern</span></span>

<span data-ttu-id="2e5c0-2740">11 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2741">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2741">Checksum</span></span>

<span data-ttu-id="2e5c0-2742">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2743">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2743">Definition</span></span>

<span data-ttu-id="2e5c0-2744">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2745">Die Funktion Func_jp_resident_registration_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2746">Ein Schlüsselwort aus Keyword_jp_resident_registration_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2747">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="2e5c0-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="2e5c0-2749">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2749">Resident Registration Number</span></span>
- <span data-ttu-id="2e5c0-2750">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2750">Resident Register Number</span></span> 
- <span data-ttu-id="2e5c0-2751">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="2e5c0-2752">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="2e5c0-2753">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2753">Resident Register No.</span></span> 
- <span data-ttu-id="2e5c0-2754">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="2e5c0-2755">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="2e5c0-2756">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="2e5c0-2757">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="2e5c0-2758">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="2e5c0-2759">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="2e5c0-2760">Japanische Sozialversicherungsnummer (SIN)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2761">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2761">Format</span></span>

<span data-ttu-id="2e5c0-2762">7-12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2763">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2763">Pattern</span></span>

<span data-ttu-id="2e5c0-2764">7 bis 12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2764">7-12 digits:</span></span>
- <span data-ttu-id="2e5c0-2765">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2765">Four digits</span></span> 
- <span data-ttu-id="2e5c0-2766">Ein Bindestrich (optional)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="2e5c0-2767">Sechs Ziffern oder</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2767">Six digits OR</span></span>
- <span data-ttu-id="2e5c0-2768">7-12 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2769">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2769">Checksum</span></span>

<span data-ttu-id="2e5c0-2770">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2771">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2771">Definition</span></span>

<span data-ttu-id="2e5c0-2772">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2773">Die Funktion Func_jp_sin findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2774">Ein Schlüsselwort aus Keyword_jp_sin wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="2e5c0-2775">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2776">Die Funktion Func_jp_sin_pre_1997 findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2777">Ein Schlüsselwort aus Keyword_jp_sin wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2777">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2778">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="2e5c0-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="2e5c0-2780">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="2e5c0-2781">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="2e5c0-2782">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="2e5c0-2783">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="2e5c0-2784">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="2e5c0-2785">Japanische Residenz Kartennummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2786">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2786">Format</span></span>

<span data-ttu-id="2e5c0-2787">12 Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2788">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2788">Pattern</span></span>

<span data-ttu-id="2e5c0-2789">12 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2789">12 letters and digits:</span></span>
- <span data-ttu-id="2e5c0-2790">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="2e5c0-2791">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2791">Eight digits</span></span> 
- <span data-ttu-id="2e5c0-2792">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2793">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2793">Checksum</span></span>

<span data-ttu-id="2e5c0-2794">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2795">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2795">Definition</span></span>

<span data-ttu-id="2e5c0-2796">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2797">Der reguläre Ausdruck Regex_jp_residence_card_number findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2798">Ein Schlüsselwort aus Keyword_jp_residence_card_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2799">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="2e5c0-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="2e5c0-2801">Wohnsitz Kartennummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2801">Residence card number</span></span>
- <span data-ttu-id="2e5c0-2802">Residenzkarte Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2802">Residence card no</span></span>
- <span data-ttu-id="2e5c0-2803">Aufenthaltskarte #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2803">Residence card #</span></span>
- <span data-ttu-id="2e5c0-2804">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="2e5c0-2805">Malaysia -ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2806">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2806">Format</span></span>

<span data-ttu-id="2e5c0-2807">12 Ziffern mit optionalen Bindestrichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2808">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2808">Pattern</span></span>

<span data-ttu-id="2e5c0-2809">12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2809">12 digits:</span></span>
- <span data-ttu-id="2e5c0-2810">Sechs Ziffern im Format JJMMTT, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2e5c0-2811">Ein Bindestrich (optional) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2811">A dash (optional)</span></span> 
- <span data-ttu-id="2e5c0-2812">Zwei Buchstaben als Code für den Geburtsort </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="2e5c0-2813">Ein Bindestrich (optional) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2813">A dash (optional)</span></span> 
- <span data-ttu-id="2e5c0-2814">Drei beliebige Ziffern </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2814">Three random digits</span></span> 
- <span data-ttu-id="2e5c0-2815">Einstelliger Code für das Geschlecht</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2816">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2816">Checksum</span></span>

<span data-ttu-id="2e5c0-2817">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2818">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2818">Definition</span></span>

<span data-ttu-id="2e5c0-2819">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2820">Der reguläre Ausdruck Regex_malaysia_id_card_number findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2821">Ein Schlüsselwort aus Keyword_malaysia_id_card_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2822">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="2e5c0-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="2e5c0-2824">digitale Anwendungs Karte</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2824">digital application card</span></span>
- <span data-ttu-id="2e5c0-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2825">i/c</span></span>
- <span data-ttu-id="2e5c0-2826">i/c Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2826">i/c no</span></span>
- <span data-ttu-id="2e5c0-2827">IK</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2827">ic</span></span>
- <span data-ttu-id="2e5c0-2828">IC Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2828">ic no</span></span>
- <span data-ttu-id="2e5c0-2829">id card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2829">id card</span></span>
- <span data-ttu-id="2e5c0-2830">Ausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2830">identification Card</span></span>
- <span data-ttu-id="2e5c0-2831">identity card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2831">identity card</span></span>
- <span data-ttu-id="2e5c0-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2832">k/p</span></span>
- <span data-ttu-id="2e5c0-2833">k/p Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2833">k/p no</span></span>
- <span data-ttu-id="2e5c0-2834">Kad akuan Diri</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2834">kad akuan diri</span></span>
- <span data-ttu-id="2e5c0-2835">Kad aplikasi Digital</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="2e5c0-2836">Kad Einführung in Malaysia</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="2e5c0-2837">KP</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2837">kp</span></span>
- <span data-ttu-id="2e5c0-2838">KP Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2838">kp no</span></span>
- <span data-ttu-id="2e5c0-2839">MyKAD</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2839">mykad</span></span>
- <span data-ttu-id="2e5c0-2840">mykas</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2840">mykas</span></span>
- <span data-ttu-id="2e5c0-2841">mykid</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2841">mykid</span></span>
- <span data-ttu-id="2e5c0-2842">mypr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2842">mypr</span></span>
- <span data-ttu-id="2e5c0-2843">mytentera</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2843">mytentera</span></span>
- <span data-ttu-id="2e5c0-2844">Malaysia-Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2844">malaysia identity card</span></span>
- <span data-ttu-id="2e5c0-2845">malaysischer Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2845">malaysian identity card</span></span>
- <span data-ttu-id="2e5c0-2846">NRIC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2846">nric</span></span>
- <span data-ttu-id="2e5c0-2847">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="2e5c0-2848">Niederlande – Bürgerdienstnummer (BSN)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2849">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2849">Format</span></span>

<span data-ttu-id="2e5c0-2850">8-9 Ziffern mit optionalen Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2851">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2851">Pattern</span></span>

<span data-ttu-id="2e5c0-2852">8-9 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2852">8-9 digits:</span></span>
- <span data-ttu-id="2e5c0-2853">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2853">Three digits</span></span> 
- <span data-ttu-id="2e5c0-2854">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2854">A space (optional)</span></span> 
- <span data-ttu-id="2e5c0-2855">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2855">Three digits</span></span> 
- <span data-ttu-id="2e5c0-2856">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2856">A space (optional)</span></span> 
- <span data-ttu-id="2e5c0-2857">2-3 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2858">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2858">Checksum</span></span>

<span data-ttu-id="2e5c0-2859">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2860">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2860">Definition</span></span>

<span data-ttu-id="2e5c0-2861">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2862">Die Funktion Func_netherlands_bsn sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2863">Ein Schlüsselwort aus Keyword_netherlands_bsn wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="2e5c0-2864">Die Funktion Func_eu_date2 findet ein Datum im richtigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="2e5c0-2865">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2865">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2866">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="2e5c0-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="2e5c0-2868">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2868">Citizen service number</span></span> 
- <span data-ttu-id="2e5c0-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2869">BSN</span></span> 
- <span data-ttu-id="2e5c0-2870">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="2e5c0-2871">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2871">Sofinummer</span></span> 
- <span data-ttu-id="2e5c0-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="2e5c0-2873">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="2e5c0-2874">Neuseeländische Gesundheitsministeriumsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2875">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2875">Format</span></span>

<span data-ttu-id="2e5c0-2876">Drei Buchstaben, ein Leerzeichen (optional) und vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2877">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2877">Pattern</span></span>

<span data-ttu-id="2e5c0-2878">Drei Buchstaben (Groß-/Kleinschreibung nicht beachtet) ein Leerzeichen (optional) vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2879">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2879">Checksum</span></span>

<span data-ttu-id="2e5c0-2880">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2881">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2881">Definition</span></span>

<span data-ttu-id="2e5c0-2882">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2883">Die Funktion Func_new_zealand_ministry_of_health_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2884">Ein Schlüsselwort aus Keyword_nz_terms wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="2e5c0-2885">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2885">The checksum passes.</span></span>

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

<span data-ttu-id="2e5c0-2886">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2886">Keywords</span></span>

<span data-ttu-id="2e5c0-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="2e5c0-2888">Nhi</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2888">NHI</span></span> 
- <span data-ttu-id="2e5c0-2889">New Zealand</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2889">New Zealand</span></span> 
- <span data-ttu-id="2e5c0-2890">Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2890">Health</span></span> 
- <span data-ttu-id="2e5c0-2891">Behandlung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="2e5c0-2892">Norwegen – Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2893">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2893">Format</span></span>

<span data-ttu-id="2e5c0-2894">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2895">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2895">Pattern</span></span>

<span data-ttu-id="2e5c0-2896">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2896">11 digits:</span></span>
- <span data-ttu-id="2e5c0-2897">Sechs Ziffern im Format TTMMJJ, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="2e5c0-2898">Dreistellige individuelle Zahl </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="2e5c0-2899">Zwei Prüfziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2900">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2900">Checksum</span></span>

<span data-ttu-id="2e5c0-2901">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2902">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2902">Definition</span></span>

<span data-ttu-id="2e5c0-2903">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2904">Die Funktion Func_norway_id_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2905">Ein Schlüsselwort aus Keyword_norway_id_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="2e5c0-2906">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2906">The checksum passes.</span></span>
- <span data-ttu-id="2e5c0-2907">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2908">Die Funktion Func_norway_id_numbe sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2909">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2909">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2910">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="2e5c0-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="2e5c0-2912">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2912">Personal identification number</span></span>
- <span data-ttu-id="2e5c0-2913">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="2e5c0-2914">ID Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2914">ID Number</span></span>
- <span data-ttu-id="2e5c0-2915">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2915">Identification</span></span>
- <span data-ttu-id="2e5c0-2916">Personnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2916">Personnummer</span></span>
- <span data-ttu-id="2e5c0-2917">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="2e5c0-2918">Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2919">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2919">Format</span></span>

<span data-ttu-id="2e5c0-2920">12 Ziffern, durch Bindestriche getrennt</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2921">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2921">Pattern</span></span>

<span data-ttu-id="2e5c0-2922">12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2922">12 digits:</span></span>
- <span data-ttu-id="2e5c0-2923">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2923">Four digits</span></span> 
- <span data-ttu-id="2e5c0-2924">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2924">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-2925">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2925">Seven digits</span></span> 
- <span data-ttu-id="2e5c0-2926">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-2926">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-2927">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2928">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2928">Checksum</span></span>

<span data-ttu-id="2e5c0-2929">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2930">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2930">Definition</span></span>

<span data-ttu-id="2e5c0-2931">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2932">Der reguläre Ausdruck Regex_philippines_unified_id findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2933">Ein Schlüsselwort aus Keyword_philippines_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2934">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="2e5c0-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="2e5c0-2936">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="2e5c0-2937">Umid</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2937">UMID</span></span> 
- <span data-ttu-id="2e5c0-2938">Identity Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2938">Identity Card</span></span> 
- <span data-ttu-id="2e5c0-2939">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="2e5c0-2940">Polen Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2941">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2941">Format</span></span>

<span data-ttu-id="2e5c0-2942">Drei Buchstaben und sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2943">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2943">Pattern</span></span>

<span data-ttu-id="2e5c0-2944">Drei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2945">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2945">Checksum</span></span>

<span data-ttu-id="2e5c0-2946">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2947">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2947">Definition</span></span>

<span data-ttu-id="2e5c0-2948">Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_polish_national_id findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="2e5c0-2949">Ein Schlüsselwort aus Keyword_polish_national_id_passport_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="2e5c0-2950">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2951">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="2e5c0-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="2e5c0-2953">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2953">Dowód osobisty</span></span>
- <span data-ttu-id="2e5c0-2954">Numer dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="2e5c0-2955">Nazwa i Numer dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="2e5c0-2956">Nazwa i Nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="2e5c0-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="2e5c0-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="2e5c0-2959">Dow.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2959">dow.</span></span> <span data-ttu-id="2e5c0-2960">OS.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="2e5c0-2961">Polnische ID-Karte (PESEL)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2962">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2962">Format</span></span>

<span data-ttu-id="2e5c0-2963">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2964">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2964">Pattern</span></span>

<span data-ttu-id="2e5c0-2965">11 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2966">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2966">Checksum</span></span>

<span data-ttu-id="2e5c0-2967">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2968">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2968">Definition</span></span>

<span data-ttu-id="2e5c0-2969">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2970">Die Funktion Func_pesel_identification_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2971">Ein Schlüsselwort aus Keyword_pesel_identification_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="2e5c0-2972">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-2973">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="2e5c0-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="2e5c0-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2975">Nr PESEL</span></span>
- <span data-ttu-id="2e5c0-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="2e5c0-2977">Polen Reisepass</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2978">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2978">Format</span></span>

<span data-ttu-id="2e5c0-2979">Zwei Buchstaben und sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2980">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2980">Pattern</span></span>

<span data-ttu-id="2e5c0-2981">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-2982">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2982">Checksum</span></span>

<span data-ttu-id="2e5c0-2983">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-2984">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2984">Definition</span></span>

<span data-ttu-id="2e5c0-2985">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-2986">Die Funktion Func_polish_passport_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-2987">Ein Schlüsselwort aus Keyword_polish_national_id_passport_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="2e5c0-2988">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2988">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-2989">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="2e5c0-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="2e5c0-2991">Numer paszportu</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2991">Numer paszportu</span></span>
- <span data-ttu-id="2e5c0-2992">Nr.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2992">Nr.</span></span> <span data-ttu-id="2e5c0-2993">Paszportu</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2993">Paszportu</span></span>
- <span data-ttu-id="2e5c0-2994">Paszport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="2e5c0-2995">Portugal – Bürgerkartennummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-2996">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2996">Format</span></span>

<span data-ttu-id="2e5c0-2997">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-2998">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2998">Pattern</span></span>

<span data-ttu-id="2e5c0-2999">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3000">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3000">Checksum</span></span>

<span data-ttu-id="2e5c0-3001">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3002">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3002">Definition</span></span>

<span data-ttu-id="2e5c0-3003">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3004">Der reguläre Ausdruck Regex_portugal_citizen_card findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3005">Ein Schlüsselwort aus Keyword_portugal_citizen_card wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3006">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="2e5c0-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="2e5c0-3008">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3008">Citizen Card</span></span>
- <span data-ttu-id="2e5c0-3009">National ID Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3009">National ID Card</span></span>
- <span data-ttu-id="2e5c0-3010">CC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3010">CC</span></span>
- <span data-ttu-id="2e5c0-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="2e5c0-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="2e5c0-3013">Saudi-Arabische Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3014">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3014">Format</span></span>

<span data-ttu-id="2e5c0-3015">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3016">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3016">Pattern</span></span>

<span data-ttu-id="2e5c0-3017">10 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3018">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3018">Checksum</span></span>

<span data-ttu-id="2e5c0-3019">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3020">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3020">Definition</span></span>

<span data-ttu-id="2e5c0-3021">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3022">Der reguläre Ausdruck Regex_saudi_arabia_national_id findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3023">Ein Schlüsselwort aus Keyword_saudi_arabia_national_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3024">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="2e5c0-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="2e5c0-3026">Identification Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3026">Identification Card</span></span> 
- <span data-ttu-id="2e5c0-3027">I card number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3027">I card number</span></span> 
- <span data-ttu-id="2e5c0-3028">ID number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3028">ID number</span></span> 
- <span data-ttu-id="2e5c0-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="2e5c0-3030">Singapur – National Registration Identity Card-Nummer (NRIC)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3031">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3031">Format</span></span>

<span data-ttu-id="2e5c0-3032">Neun Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3033">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3033">Pattern</span></span>

- <span data-ttu-id="2e5c0-3034">Neun Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="2e5c0-3035">Die Buchstaben "F", "G", "S" oder "T" (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-3036">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3036">Seven digits</span></span> 
- <span data-ttu-id="2e5c0-3037">Eine alphabetische Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3038">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3038">Checksum</span></span>

<span data-ttu-id="2e5c0-3039">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3040">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3040">Definition</span></span>

<span data-ttu-id="2e5c0-3041">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3042">Der reguläre Ausdruck Regex_singapore_nric findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3043">Ein Schlüsselwort aus Keyword_singapore_nric wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="2e5c0-3044">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3044">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-3045">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3046">Der reguläre Ausdruck Regex_singapore_nric findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3047">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3047">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3048">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="2e5c0-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="2e5c0-3050">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="2e5c0-3051">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3051">Identity Card Number</span></span> 
- <span data-ttu-id="2e5c0-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3052">NRIC</span></span> 
- <span data-ttu-id="2e5c0-3053">IK</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3053">IC</span></span> 
- <span data-ttu-id="2e5c0-3054">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="2e5c0-3055">FIN</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3055">FIN</span></span> 
- <span data-ttu-id="2e5c0-3056">身份证</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3056">身份证</span></span> 
- <span data-ttu-id="2e5c0-3057">身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="2e5c0-3058">Südafrika – Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3059">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3059">Format</span></span>

<span data-ttu-id="2e5c0-3060">13 Ziffern, die Leerzeichen enthalten können</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3061">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3061">Pattern</span></span>

<span data-ttu-id="2e5c0-3062">13 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3062">13 digits:</span></span>
- <span data-ttu-id="2e5c0-3063">Sechs Ziffern im Format JJMMTT, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2e5c0-3064">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3064">Four digits</span></span> 
- <span data-ttu-id="2e5c0-3065">Ein einstelliger Citizenship-Indikator </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="2e5c0-3066">Die Ziffer "8" oder "9" </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="2e5c0-3067">Eine Ziffer als Prüfsummenziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3068">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3068">Checksum</span></span>

<span data-ttu-id="2e5c0-3069">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3070">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3070">Definition</span></span>

<span data-ttu-id="2e5c0-3071">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3072">Die Funktion Func_south_africa_identification_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3073">Ein Schlüsselwort aus Keyword_south_africa_identification_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="2e5c0-3074">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3075">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="2e5c0-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="2e5c0-3077">Identity card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3077">Identity card</span></span>
- <span data-ttu-id="2e5c0-3078">ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3078">ID</span></span>
- <span data-ttu-id="2e5c0-3079">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="2e5c0-3080">Südkorea – Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3081">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3081">Format</span></span>

<span data-ttu-id="2e5c0-3082">13 Ziffern, die einen Bindestrich enthalten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3083">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3083">Pattern</span></span>

<span data-ttu-id="2e5c0-3084">13 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3084">13 digits:</span></span>
- <span data-ttu-id="2e5c0-3085">Sechs Ziffern im Format JJMMTT, die das Geburtsdatum angeben </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2e5c0-3086">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3086">A hyphen</span></span> 
- <span data-ttu-id="2e5c0-3087">Eine Ziffer, die durch das Jahrhundert und das Geschlecht bestimmt wird </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="2e5c0-3088">Vierstelliger Code für die Geburtsregion </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="2e5c0-3089">Eine Ziffer, um Personen zu unterscheiden, für die die vorhergehenden Zahlen identisch sind </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="2e5c0-3090">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3091">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3091">Checksum</span></span>

<span data-ttu-id="2e5c0-3092">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3093">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3093">Definition</span></span>

<span data-ttu-id="2e5c0-3094">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3095">Die Funktion Func_south_korea_resident_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3096">Ein Schlüsselwort aus Keyword_south_korea_resident_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="2e5c0-3097">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3097">The checksum passes.</span></span>

<span data-ttu-id="2e5c0-3098">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3099">Die Funktion Func_south_korea_resident_number sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3100">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3100">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3101">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="2e5c0-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="2e5c0-3103">National ID card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3103">National ID card</span></span> 
- <span data-ttu-id="2e5c0-3104">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="2e5c0-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="2e5c0-3106">RRN</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3106">RRN</span></span> 
- <span data-ttu-id="2e5c0-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="2e5c0-3108">Spanische Sozialversicherungsnummer (SSN)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3109">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3109">Format</span></span>

<span data-ttu-id="2e5c0-3110">11-12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3111">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3111">Pattern</span></span>

<span data-ttu-id="2e5c0-3112">11-12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3112">11-12 digits:</span></span>
- <span data-ttu-id="2e5c0-3113">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3113">Two digits</span></span> 
- <span data-ttu-id="2e5c0-3114">Ein Schrägstrich (optional)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="2e5c0-3115">7 bis 8 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3115">7-8 digits</span></span> 
- <span data-ttu-id="2e5c0-3116">Ein Schrägstrich (optional)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="2e5c0-3117">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3118">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3118">Checksum</span></span>

<span data-ttu-id="2e5c0-3119">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3120">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3120">Definition</span></span>

<span data-ttu-id="2e5c0-3121">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3122">Die Funktion Func_spanish_social_security_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3123">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3124">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3124">Keywords</span></span>

<span data-ttu-id="2e5c0-3125">Keine</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="2e5c0-3126">SQL Server Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3127">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3127">Format</span></span>

<span data-ttu-id="2e5c0-3128">Die Zeichenfolge "Benutzer-ID", "Benutzer-ID", "UID" oder "UserID", gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3129">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3129">Pattern</span></span>

- <span data-ttu-id="2e5c0-3130">Die Zeichenfolge "Benutzer-ID", "Benutzer-ID", "UID" oder "UserID"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="2e5c0-3131">Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2e5c0-3132">Die Zeichenfolge "Password" oder "pwd", wobei "pwd" kein Kleinbuchstabe vorangestellt ist</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="2e5c0-3133">Ein Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3133">An equal sign (=)</span></span>
- <span data-ttu-id="2e5c0-3134">Ein beliebiges Zeichen, das kein Dollarzeichen ($), Prozentzeichen (%), größer als das Symbol (>), Symbol (@), Anführungszeichen ("), Semikolon (;), linke geschweifte Klammer ([) oder linke Klammer ({) ist.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="2e5c0-3135">Eine beliebige Kombination von 7-128 Zeichen, die kein Semikolon sind (;), Schrägstrich (/) oder Anführungszeichen (")</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="2e5c0-3136">Ein Semikolon (;) oder Anführungszeichen (")</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3137">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3137">Checksum</span></span>

<span data-ttu-id="2e5c0-3138">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3139">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3139">Definition</span></span>

<span data-ttu-id="2e5c0-3140">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3141">Der reguläre Ausdruck CEP_Regex_SQLServerConnectionString findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3142">Ein Schlüsselwort aus CEP_GlobalFilter wurde **nicht** gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="2e5c0-3143">Der reguläre Ausdruck CEP_PasswordPlaceHolder findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3144">Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3145">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="2e5c0-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="2e5c0-3147">Einige-Kennwort</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3147">some-password</span></span>
- <span data-ttu-id="2e5c0-3148">somepassword</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3148">somepassword</span></span>
- <span data-ttu-id="2e5c0-3149">secretPassword</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3149">secretPassword</span></span>
- <span data-ttu-id="2e5c0-3150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="2e5c0-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="2e5c0-3152">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2e5c0-3153">Password oder PWD gefolgt von 0-2 Leerzeichen, ein Gleichheitszeichen (=), 0-2 Leerzeichen und ein Sternchen (\*)--oder--</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="2e5c0-3154">Password oder PWD gefolgt von:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="2e5c0-3155">Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="2e5c0-3156">Kleiner als-Symbol (<)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="2e5c0-3157">Eine beliebige Kombination von 1-200 Zeichen mit groß-oder Kleinbuchstaben, Ziffern, einem Sternchen (\*), einem Bindestrich (-), einem Unterstrich (_) oder einem Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="2e5c0-3158">Größer als-Symbol (>)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="2e5c0-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2e5c0-3160">(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2e5c0-3161">contoso</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3161">contoso</span></span>
- <span data-ttu-id="2e5c0-3162">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3162">fabrikam</span></span>
- <span data-ttu-id="2e5c0-3163">Northwind</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3163">northwind</span></span>
- <span data-ttu-id="2e5c0-3164">Sandkasten</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3164">sandbox</span></span>
- <span data-ttu-id="2e5c0-3165">OneBox</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3165">onebox</span></span>
- <span data-ttu-id="2e5c0-3166">localhost</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3166">localhost</span></span>
- <span data-ttu-id="2e5c0-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3167">127.0.0.1</span></span>
- <span data-ttu-id="2e5c0-3168">testacs.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-3169">com</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3169">com</span></span>
- <span data-ttu-id="2e5c0-3170">s-int.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2e5c0-3171">NET</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="2e5c0-3172">Schwedische Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3173">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3173">Format</span></span>

<span data-ttu-id="2e5c0-3174">10 oder 12 Ziffern und ein optionales Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3175">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3175">Pattern</span></span>

<span data-ttu-id="2e5c0-3176">10 oder 12 Ziffern und ein optionals Trennzeichen:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="2e5c0-3177">2 bis 4 Ziffern (optional)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="2e5c0-3178">Sechs Ziffern im Datumsformat JJMMTT</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="2e5c0-3179">Trennzeichen „-“ oder „+“ (optional) und</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="2e5c0-3180">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3181">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3181">Checksum</span></span>

<span data-ttu-id="2e5c0-3182">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3183">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3183">Definition</span></span>

<span data-ttu-id="2e5c0-3184">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3185">Die Funktion Func_swedish_national_identifier findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3186">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3187">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3187">Keywords</span></span>

<span data-ttu-id="2e5c0-3188">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="2e5c0-3189">Schwedische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3190">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3190">Format</span></span>

<span data-ttu-id="2e5c0-3191">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3192">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3192">Pattern</span></span>

<span data-ttu-id="2e5c0-3193">Acht aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3194">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3194">Checksum</span></span>

<span data-ttu-id="2e5c0-3195">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3196">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3196">Definition</span></span>

<span data-ttu-id="2e5c0-3197">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3198">Der reguläre Ausdruck Regex_sweden_passport_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3199">Eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3199">One of the following is true:</span></span>
    - <span data-ttu-id="2e5c0-3200">Ein Schlüsselwort aus Keyword_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="2e5c0-3201">Ein Schlüsselwort aus Keyword_sweden_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3201">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3202">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="2e5c0-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="2e5c0-3204">visa requirements</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3204">visa requirements</span></span> 
- <span data-ttu-id="2e5c0-3205">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="2e5c0-3206">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3206">Schengen visas</span></span> 
- <span data-ttu-id="2e5c0-3207">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3207">Schengen visa</span></span> 
- <span data-ttu-id="2e5c0-3208">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3208">Visa Processing</span></span> 
- <span data-ttu-id="2e5c0-3209">Visa Type</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3209">Visa Type</span></span> 
- <span data-ttu-id="2e5c0-3210">Single Entry</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3210">Single Entry</span></span> 
- <span data-ttu-id="2e5c0-3211">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3211">Multiple Entry</span></span> 
- <span data-ttu-id="2e5c0-3212">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="2e5c0-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3213">Keyword_passport</span></span>

- <span data-ttu-id="2e5c0-3214">Passport Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3214">Passport Number</span></span> 
- <span data-ttu-id="2e5c0-3215">Passport No</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3215">Passport No</span></span> 
- <span data-ttu-id="2e5c0-3216">Passport#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3216">Passport #</span></span> 
- <span data-ttu-id="2e5c0-3217">Pass #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3217">Passport#</span></span> 
- <span data-ttu-id="2e5c0-3218">Passport-Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3218">PassportID</span></span> 
- <span data-ttu-id="2e5c0-3219">Passportno</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3219">Passportno</span></span> 
- <span data-ttu-id="2e5c0-3220">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3220">passportnumber</span></span> 
- <span data-ttu-id="2e5c0-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3221">パスポート</span></span> 
- <span data-ttu-id="2e5c0-3222">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3222">パスポート番号</span></span> 
- <span data-ttu-id="2e5c0-3223">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3223">パスポートのNum</span></span> 
- <span data-ttu-id="2e5c0-3224">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3224">パスポート＃</span></span> 
- <span data-ttu-id="2e5c0-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="2e5c0-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3226">Passeport n °</span></span> 
- <span data-ttu-id="2e5c0-3227">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3227">Passeport Non</span></span> 
- <span data-ttu-id="2e5c0-3228">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3228">Passeport #</span></span> 
- <span data-ttu-id="2e5c0-3229">Passeport #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3229">Passeport#</span></span> 
- <span data-ttu-id="2e5c0-3230">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3230">PasseportNon</span></span> 
- <span data-ttu-id="2e5c0-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="2e5c0-3232">SWIFT-Code</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3233">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3233">Format</span></span>

<span data-ttu-id="2e5c0-3234">Vier Buchstaben, gefolgt von 5-31 Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3235">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3235">Pattern</span></span>

<span data-ttu-id="2e5c0-3236">Vier Buchstaben, gefolgt von 5 bis 31 Buchstaben oder Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="2e5c0-3237">Vier Buchstaben für den Bankcode (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-3238">Ein optionales Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3238">An optional space</span></span> 
- <span data-ttu-id="2e5c0-3239">4 bis 28 Buchstaben oder Ziffern (BBAN, Basic Bank Account Number)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="2e5c0-3240">Ein optionales Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3240">An optional space</span></span> 
- <span data-ttu-id="2e5c0-3241">1 bis 3 Buchstaben oder Ziffern (Rest des BBAN)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3242">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3242">Checksum</span></span>

<span data-ttu-id="2e5c0-3243">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3244">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3244">Definition</span></span>

<span data-ttu-id="2e5c0-3245">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3246">Der reguläre Ausdruck Regex_swift findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3247">Ein Schlüsselwort aus Keyword_swift wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3248">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="2e5c0-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3249">Keyword_swift</span></span>

- <span data-ttu-id="2e5c0-3250">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="2e5c0-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3251">iso 9362</span></span> 
- <span data-ttu-id="2e5c0-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3252">iso9362</span></span> 
- <span data-ttu-id="2e5c0-3253">SWIFT\#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3253">swift\#</span></span> 
- <span data-ttu-id="2e5c0-3254">Swiftcode</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3254">swiftcode</span></span> 
- <span data-ttu-id="2e5c0-3255">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3255">swiftnumber</span></span> 
- <span data-ttu-id="2e5c0-3256">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="2e5c0-3257">swift code</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3257">swift code</span></span> 
- <span data-ttu-id="2e5c0-3258">swift number #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3258">swift number #</span></span> 
- <span data-ttu-id="2e5c0-3259">swift routing number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3259">swift routing number</span></span> 
- <span data-ttu-id="2e5c0-3260">bic number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3260">bic number</span></span> 
- <span data-ttu-id="2e5c0-3261">bic code</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3261">bic code</span></span> 
- <span data-ttu-id="2e5c0-3262">BIC\#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3262">bic \#</span></span> 
- <span data-ttu-id="2e5c0-3263">BIC\#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3263">bic\#</span></span> 
- <span data-ttu-id="2e5c0-3264">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3264">bank identifier code</span></span> 
- <span data-ttu-id="2e5c0-3265">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3265">標準化9362</span></span> 
- <span data-ttu-id="2e5c0-3266">迅速＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3266">迅速＃</span></span> 
- <span data-ttu-id="2e5c0-3267">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3267">SWIFTコード</span></span> 
- <span data-ttu-id="2e5c0-3268">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3268">SWIFT番号</span></span> 
- <span data-ttu-id="2e5c0-3269">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="2e5c0-3270">BIC番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3270">BIC番号</span></span> 
- <span data-ttu-id="2e5c0-3271">BICコード</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3271">BICコード</span></span> 
- <span data-ttu-id="2e5c0-3272">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="2e5c0-3273">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="2e5c0-3274">rapide\#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3274">rapide \#</span></span> 
- <span data-ttu-id="2e5c0-3275">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3275">code SWIFT</span></span> 
- <span data-ttu-id="2e5c0-3276">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3276">le numéro de swift</span></span> 
- <span data-ttu-id="2e5c0-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="2e5c0-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3278">le numéro BIC</span></span> 
- <span data-ttu-id="2e5c0-3279">\#BIC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3279">\# BIC</span></span> 
- <span data-ttu-id="2e5c0-3280">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="2e5c0-3281">Taiwanesicher Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3282">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3282">Format</span></span>

<span data-ttu-id="2e5c0-3283">Ein Buchstabe (auf Englisch) gefolgt von neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3284">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3284">Pattern</span></span>

<span data-ttu-id="2e5c0-3285">Ein Buchstabe (Englisch), gefolgt von neun Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="2e5c0-3286">Ein Buchstabe (Englisch, Groß-/Kleinschreibung wird nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-3287">Die Ziffer 1 oder 2</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="2e5c0-3288">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3289">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3289">Checksum</span></span>

<span data-ttu-id="2e5c0-3290">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3291">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3291">Definition</span></span>

<span data-ttu-id="2e5c0-3292">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3293">Die Funktion Func_taiwanese_national_id findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3294">Ein Schlüsselwort aus Keyword_taiwanese_national_id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="2e5c0-3295">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3296">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="2e5c0-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="2e5c0-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3298">身份證字號</span></span> 
- <span data-ttu-id="2e5c0-3299">身份證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3299">身份證</span></span> 
- <span data-ttu-id="2e5c0-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3300">身份證號碼</span></span> 
- <span data-ttu-id="2e5c0-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3301">身份證號</span></span> 
- <span data-ttu-id="2e5c0-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3302">身分證字號</span></span> 
- <span data-ttu-id="2e5c0-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3303">身分證</span></span> 
- <span data-ttu-id="2e5c0-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3304">身分證號碼</span></span> 
- <span data-ttu-id="2e5c0-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3305">身份證號</span></span> 
- <span data-ttu-id="2e5c0-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3306">身分證統一編號</span></span> 
- <span data-ttu-id="2e5c0-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="2e5c0-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3308">簽名</span></span> 
- <span data-ttu-id="2e5c0-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3309">蓋章</span></span> 
- <span data-ttu-id="2e5c0-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="2e5c0-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="2e5c0-3312">	Taiwan – Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3313">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3313">Format</span></span>

- <span data-ttu-id="2e5c0-3314">Biometrische Passport-Nummer: neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="2e5c0-3315">Nicht biometrische Passport-Nummer: neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3316">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3316">Pattern</span></span>
<span data-ttu-id="2e5c0-3317">Biometrische Passnummer:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3317">Biometric passport number:</span></span>
- <span data-ttu-id="2e5c0-3318">Die Ziffer "3" </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3318">The digit "3"</span></span> 
- <span data-ttu-id="2e5c0-3319">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3319">Eight digits</span></span>

<span data-ttu-id="2e5c0-3320">Nicht biometrische Passnummer:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="2e5c0-3321">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3322">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3322">Checksum</span></span>

<span data-ttu-id="2e5c0-3323">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3324">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3324">Definition</span></span>

<span data-ttu-id="2e5c0-3325">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3326">Der reguläre Ausdruck Regex_taiwan_passport findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3327">Ein Schlüsselwort aus Keyword_taiwan_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3328">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="2e5c0-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="2e5c0-3330">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3330">ROC passport number</span></span> 
- <span data-ttu-id="2e5c0-3331">Passport number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3331">Passport number</span></span> 
- <span data-ttu-id="2e5c0-3332">Passport no</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3332">Passport no</span></span> 
- <span data-ttu-id="2e5c0-3333">Passport Num</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3333">Passport Num</span></span> 
- <span data-ttu-id="2e5c0-3334">Passport #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3334">Passport #</span></span> 
- <span data-ttu-id="2e5c0-3335">护照</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3335">护照</span></span> 
- <span data-ttu-id="2e5c0-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3336">中華民國護照</span></span> 
- <span data-ttu-id="2e5c0-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="2e5c0-3338">Taiwan – Einwohnerzertifikatsnummer (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3339">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3339">Format</span></span>

<span data-ttu-id="2e5c0-3340">10 Buchstaben und Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3341">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3341">Pattern</span></span>

<span data-ttu-id="2e5c0-3342">10 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3342">10 letters and digits:</span></span>
- <span data-ttu-id="2e5c0-3343">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant) </span><span class="sxs-lookup"><span data-stu-id="2e5c0-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="2e5c0-3344">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3345">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3345">Checksum</span></span>

<span data-ttu-id="2e5c0-3346">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3347">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3347">Definition</span></span>

<span data-ttu-id="2e5c0-3348">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3349">Der reguläre Ausdruck Regex_taiwan_resident_certificate findet Inhalte, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3350">Ein Schlüsselwort aus Keyword_taiwan_resident_certificate wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3351">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="2e5c0-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="2e5c0-3353">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3353">Resident Certificate</span></span> 
- <span data-ttu-id="2e5c0-3354">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3354">Resident Cert</span></span> 
- <span data-ttu-id="2e5c0-3355">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3355">Resident Cert.</span></span> 
- <span data-ttu-id="2e5c0-3356">Identification card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3356">Identification card</span></span> 
- <span data-ttu-id="2e5c0-3357">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="2e5c0-3358">ARC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3358">ARC</span></span> 
- <span data-ttu-id="2e5c0-3359">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="2e5c0-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3360">TARC</span></span> 
- <span data-ttu-id="2e5c0-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3361">居留證</span></span> 
- <span data-ttu-id="2e5c0-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3362">外僑居留證</span></span> 
- <span data-ttu-id="2e5c0-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="2e5c0-3364">Thai-Populations Kennzeichnungs Code</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3365">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3365">Format</span></span>

<span data-ttu-id="2e5c0-3366">13 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3367">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3367">Pattern</span></span>

<span data-ttu-id="2e5c0-3368">13 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3368">13 digits:</span></span>
- <span data-ttu-id="2e5c0-3369">Die erste Ziffer ist nicht 0 oder 9.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="2e5c0-3370">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3371">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3371">Checksum</span></span>

<span data-ttu-id="2e5c0-3372">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3373">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3373">Definition</span></span>

<span data-ttu-id="2e5c0-3374">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3375">Die Funktion Func_Thai_Citizen_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3376">Ein Schlüsselwort aus Keyword_Thai_Citizen_Id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="2e5c0-3377">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3378">Die Funktion Func_Thai_Citizen_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3379">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="2e5c0-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="2e5c0-3381">ID Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3381">ID Number</span></span>
- <span data-ttu-id="2e5c0-3382">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3382">Identification Number</span></span>
- <span data-ttu-id="2e5c0-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="2e5c0-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="2e5c0-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="2e5c0-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="2e5c0-3387">Türkische nationale Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3388">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3388">Format</span></span>

<span data-ttu-id="2e5c0-3389">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3390">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3390">Pattern</span></span>

<span data-ttu-id="2e5c0-3391">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3392">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3392">Checksum</span></span>

<span data-ttu-id="2e5c0-3393">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3394">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3394">Definition</span></span>

<span data-ttu-id="2e5c0-3395">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3396">Die Funktion Func_Turkish_National_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3397">Ein Schlüsselwort aus Keyword_Turkish_National_Id wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="2e5c0-3398">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3399">Die Funktion Func_Turkish_National_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3400">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="2e5c0-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="2e5c0-3402">TC KİMLİK Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3402">TC Kimlik No</span></span>
- <span data-ttu-id="2e5c0-3403">TC KİMLİK numarası</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="2e5c0-3404">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="2e5c0-3405">Vatandaşlık Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="2e5c0-p144">Britische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-p144">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3408">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3408">Format</span></span>

<span data-ttu-id="2e5c0-3409">Kombination aus 18 Buchstaben und Ziffern im angegebenen Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3410">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3410">Pattern</span></span>

<span data-ttu-id="2e5c0-3411">18 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3411">18 letters and digits:</span></span>
- <span data-ttu-id="2e5c0-3412">Fünf Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) oder die Ziffer 9 anstelle eines Buchstabens</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="2e5c0-3413">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3413">One digit</span></span> 
- <span data-ttu-id="2e5c0-3414">Fünf Ziffern im Datumsformat MMDDY für das Geburtsdatum (das siebte Zeichen wird um 50 erhöht, wenn der Fahrer weiblich ist, d. h. 51 bis 62 statt 01 bis 12).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3414">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="2e5c0-3415">Zwei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) oder die Ziffer 9 anstelle eines Buchstabens</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="2e5c0-3416">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3417">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3417">Checksum</span></span>

<span data-ttu-id="2e5c0-3418">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3419">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3419">Definition</span></span>

<span data-ttu-id="2e5c0-3420">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3421">Die Funktion Func_uk_drivers_license findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3422">Ein Schlüsselwort aus Keyword_uk_drivers_license wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="2e5c0-3423">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3424">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="2e5c0-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="2e5c0-3426">DVLA</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3426">DVLA</span></span> 
- <span data-ttu-id="2e5c0-3427">light vans</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3427">light vans</span></span> 
- <span data-ttu-id="2e5c0-3428">Quads entwickelt</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3428">quadbikes</span></span> 
- <span data-ttu-id="2e5c0-3429">motor cars</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3429">motor cars</span></span> 
- <span data-ttu-id="2e5c0-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3430">125cc</span></span> 
- <span data-ttu-id="2e5c0-3431">Beiwagen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3431">sidecar</span></span> 
- <span data-ttu-id="2e5c0-3432">Dreiräder</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3432">tricycles</span></span> 
- <span data-ttu-id="2e5c0-3433">Motorrad</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3433">motorcycles</span></span> 
- <span data-ttu-id="2e5c0-3434">photocard licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3434">photocard licence</span></span> 
- <span data-ttu-id="2e5c0-3435">learner drivers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3435">learner drivers</span></span> 
- <span data-ttu-id="2e5c0-3436">licence holder</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3436">licence holder</span></span> 
- <span data-ttu-id="2e5c0-3437">licence holders</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3437">licence holders</span></span> 
- <span data-ttu-id="2e5c0-3438">driving licences</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3438">driving licences</span></span> 
- <span data-ttu-id="2e5c0-3439">driving licence</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3439">driving licence</span></span> 
- <span data-ttu-id="2e5c0-3440">dual control car</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="2e5c0-p145">Britische Wählerverzeichnisnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-p145">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3443">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3443">Format</span></span>

<span data-ttu-id="2e5c0-3444">Zwei Buchstaben gefolgt von 1-4 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3445">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3445">Pattern</span></span>

<span data-ttu-id="2e5c0-3446">Zwei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von 1-4 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3447">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3447">Checksum</span></span>

<span data-ttu-id="2e5c0-3448">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3449">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3449">Definition</span></span>

<span data-ttu-id="2e5c0-3450">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3451">Der reguläre Ausdruck Regex_uk_electoral findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3452">Ein Schlüsselwort aus Keyword_uk_electoral wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3452">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3453">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="2e5c0-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="2e5c0-3455">council nomination</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3455">council nomination</span></span> 
- <span data-ttu-id="2e5c0-3456">nomination form</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3456">nomination form</span></span> 
- <span data-ttu-id="2e5c0-3457">electoral register</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3457">electoral register</span></span> 
- <span data-ttu-id="2e5c0-3458">electoral roll</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="2e5c0-p146">Britische National Health Service-Nummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-p146">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3461">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3461">Format</span></span>

<span data-ttu-id="2e5c0-3462">10-17 Ziffern, durch Leerzeichen getrennt</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3463">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3463">Pattern</span></span>

<span data-ttu-id="2e5c0-3464">10 bis 17 Stellen:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3464">10-17 digits:</span></span>
- <span data-ttu-id="2e5c0-3465">3 oder 10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="2e5c0-3466">Ein Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3466">A space</span></span> 
- <span data-ttu-id="2e5c0-3467">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3467">Three digits</span></span> 
- <span data-ttu-id="2e5c0-3468">Ein Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3468">A space</span></span> 
- <span data-ttu-id="2e5c0-3469">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3470">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3470">Checksum</span></span>

<span data-ttu-id="2e5c0-3471">Ja</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3472">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3472">Definition</span></span>

<span data-ttu-id="2e5c0-3473">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3474">Die Funktion Func_uk_nhs_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3475">Eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3475">One of the following is true:</span></span>
    - <span data-ttu-id="2e5c0-3476">Ein Schlüsselwort aus Keyword_uk_nhs_number wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="2e5c0-3477">Ein Schlüsselwort aus Keyword_uk_nhs_number1 wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="2e5c0-3478">Ein Schlüsselwort aus Keyword_uk_nhs_number_dob wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="2e5c0-3479">Die Prüfsumme stimmt.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3479">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3480">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="2e5c0-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="2e5c0-3482">national health service</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3482">national health service</span></span> 
- <span data-ttu-id="2e5c0-3483">NHS</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3483">nhs</span></span> 
- <span data-ttu-id="2e5c0-3484">health services authority</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3484">health services authority</span></span> 
- <span data-ttu-id="2e5c0-3485">health authority</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="2e5c0-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="2e5c0-3487">patient id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3487">patient id</span></span> 
- <span data-ttu-id="2e5c0-3488">patient identification</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3488">patient identification</span></span> 
- <span data-ttu-id="2e5c0-3489">patient no</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3489">patient no</span></span> 
- <span data-ttu-id="2e5c0-3490">patient number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="2e5c0-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="2e5c0-3492">GP</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3492">GP</span></span> 
- <span data-ttu-id="2e5c0-3493">DOB</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3493">DOB</span></span> 
- <span data-ttu-id="2e5c0-3494">D. O. B</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3494">D.O.B</span></span> 
- <span data-ttu-id="2e5c0-3495">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3495">Date of Birth</span></span> 
- <span data-ttu-id="2e5c0-3496">Birth Date</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="2e5c0-p147">Britische nationale Versicherungsnummer (NINO)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-p147">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3499">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3499">Format</span></span>

<span data-ttu-id="2e5c0-3500">7 Zeichen oder 9 Zeichen, getrennt durch Leerzeichen oder Bindestriche</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3501">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3501">Pattern</span></span>

<span data-ttu-id="2e5c0-3502">Zwei mögliche Muster:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3502">Two possible patterns:</span></span>

- <span data-ttu-id="2e5c0-3503">Zwei Buchstaben (gültige Ninos verwenden nur bestimmte Zeichen in diesem Präfix, die von diesem Muster überprüft werden; Groß-/Kleinschreibung wird nicht berücksichtigt)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="2e5c0-3504">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3504">Six digits</span></span>
- <span data-ttu-id="2e5c0-3505">Entweder "A", "B", "C" oder "'d" (wie das Präfix sind nur bestimmte Zeichen im Suffix zulässig; Groß-/Kleinschreibung wird nicht berücksichtigt)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="2e5c0-3506">ODER</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3506">OR</span></span>

- <span data-ttu-id="2e5c0-3507">Zwei Buchstaben</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3507">Two letters</span></span>
- <span data-ttu-id="2e5c0-3508">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3508">A space or dash</span></span>
- <span data-ttu-id="2e5c0-3509">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3509">Two digits</span></span>
- <span data-ttu-id="2e5c0-3510">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3510">A space or dash</span></span>
- <span data-ttu-id="2e5c0-3511">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3511">Two digits</span></span>
- <span data-ttu-id="2e5c0-3512">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3512">A space or dash</span></span>
- <span data-ttu-id="2e5c0-3513">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3513">Two digits</span></span>
- <span data-ttu-id="2e5c0-3514">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3514">A space or dash</span></span>
- <span data-ttu-id="2e5c0-3515">Entweder "A", "B", "C" oder "'d"</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3516">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3516">Checksum</span></span>

<span data-ttu-id="2e5c0-3517">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3518">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3518">Definition</span></span>

<span data-ttu-id="2e5c0-3519">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3520">Die Funktion Func_uk_nino findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3521">Ein Schlüsselwort aus Keyword_uk_nino wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="2e5c0-3522">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3523">Die Funktion Func_uk_nino findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3524">Es wurde kein Schlüsselwort aus Keyword_uk_nino gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3524">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3525">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="2e5c0-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="2e5c0-3527">national insurance number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3527">national insurance number</span></span> 
- <span data-ttu-id="2e5c0-3528">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3528">national insurance contributions</span></span> 
- <span data-ttu-id="2e5c0-3529">protection act</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3529">protection act</span></span> 
- <span data-ttu-id="2e5c0-3530">Versicherungs</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3530">insurance</span></span> 
- <span data-ttu-id="2e5c0-3531">social security number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3531">social security number</span></span> 
- <span data-ttu-id="2e5c0-3532">insurance application</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3532">insurance application</span></span> 
- <span data-ttu-id="2e5c0-3533">medical application</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3533">medical application</span></span> 
- <span data-ttu-id="2e5c0-3534">social insurance</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3534">social insurance</span></span> 
- <span data-ttu-id="2e5c0-3535">medical attention</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3535">medical attention</span></span> 
- <span data-ttu-id="2e5c0-3536">social security</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3536">social security</span></span> 
- <span data-ttu-id="2e5c0-3537">great britain</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3537">great britain</span></span> 
- <span data-ttu-id="2e5c0-3538">Versicherungs</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="2e5c0-p148">US-amerikanische/britische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-p148">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3541">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3541">Format</span></span>

<span data-ttu-id="2e5c0-3542">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3543">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3543">Pattern</span></span>

<span data-ttu-id="2e5c0-3544">Neun aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3545">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3545">Checksum</span></span>

<span data-ttu-id="2e5c0-3546">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3547">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3547">Definition</span></span>

<span data-ttu-id="2e5c0-3548">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3549">Die Funktion Func_usa_uk_passport findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3550">Ein Schlüsselwort aus Keyword_passport wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3551">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="2e5c0-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3552">Keyword_passport</span></span>

- <span data-ttu-id="2e5c0-3553">Passport Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3553">Passport Number</span></span> 
- <span data-ttu-id="2e5c0-3554">Passport No</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3554">Passport No</span></span> 
- <span data-ttu-id="2e5c0-3555">Passport#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3555">Passport #</span></span> 
- <span data-ttu-id="2e5c0-3556">Pass #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3556">Passport#</span></span> 
- <span data-ttu-id="2e5c0-3557">Passport-Nr</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3557">PassportID</span></span> 
- <span data-ttu-id="2e5c0-3558">Passportno</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3558">Passportno</span></span> 
- <span data-ttu-id="2e5c0-3559">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3559">passportnumber</span></span> 
- <span data-ttu-id="2e5c0-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3560">パスポート</span></span> 
- <span data-ttu-id="2e5c0-3561">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3561">パスポート番号</span></span> 
- <span data-ttu-id="2e5c0-3562">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3562">パスポートのNum</span></span> 
- <span data-ttu-id="2e5c0-3563">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3563">パスポート＃</span></span> 
- <span data-ttu-id="2e5c0-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="2e5c0-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3565">Passeport n °</span></span> 
- <span data-ttu-id="2e5c0-3566">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3566">Passeport Non</span></span> 
- <span data-ttu-id="2e5c0-3567">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3567">Passeport #</span></span> 
- <span data-ttu-id="2e5c0-3568">Passeport #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3568">Passeport#</span></span> 
- <span data-ttu-id="2e5c0-3569">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3569">PasseportNon</span></span> 
- <span data-ttu-id="2e5c0-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="2e5c0-3571">US-Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3572">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3572">Format</span></span>

<span data-ttu-id="2e5c0-3573">8-17 Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3574">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3574">Pattern</span></span>

<span data-ttu-id="2e5c0-3575">8-17 aufeinanderfolgende Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3576">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3576">Checksum</span></span>

<span data-ttu-id="2e5c0-3577">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3578">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3578">Definition</span></span>

<span data-ttu-id="2e5c0-3579">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3580">Der reguläre Ausdruck Regex_usa_bank_account_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3581">Ein Schlüsselwort aus Keyword_usa_Bank_Account wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2e5c0-3582">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="2e5c0-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="2e5c0-3584">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3584">Checking Account Number</span></span> 
- <span data-ttu-id="2e5c0-3585">Checking Account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3585">Checking Account</span></span> 
- <span data-ttu-id="2e5c0-3586">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3586">Checking Account #</span></span> 
- <span data-ttu-id="2e5c0-3587">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="2e5c0-3588">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3588">Checking Acct #</span></span> 
- <span data-ttu-id="2e5c0-3589">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="2e5c0-3590">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3590">Checking Account No.</span></span> 
- <span data-ttu-id="2e5c0-3591">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3591">Bank Account Number</span></span> 
- <span data-ttu-id="2e5c0-3592">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3592">Bank Account #</span></span> 
- <span data-ttu-id="2e5c0-3593">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="2e5c0-3594">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3594">Bank Acct #</span></span> 
- <span data-ttu-id="2e5c0-3595">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="2e5c0-3596">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3596">Bank Account No.</span></span> 
- <span data-ttu-id="2e5c0-3597">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3597">Savings Account Number</span></span> 
- <span data-ttu-id="2e5c0-3598">Savings Account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3598">Savings Account.</span></span> 
- <span data-ttu-id="2e5c0-3599">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3599">Savings Account #</span></span> 
- <span data-ttu-id="2e5c0-3600">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="2e5c0-3601">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3601">Savings Acct #</span></span> 
- <span data-ttu-id="2e5c0-3602">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="2e5c0-3603">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3603">Savings Account No.</span></span> 
- <span data-ttu-id="2e5c0-3604">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3604">Debit Account Number</span></span> 
- <span data-ttu-id="2e5c0-3605">Debit Account</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3605">Debit Account</span></span> 
- <span data-ttu-id="2e5c0-3606">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3606">Debit Account #</span></span> 
- <span data-ttu-id="2e5c0-3607">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="2e5c0-3608">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3608">Debit Acct #</span></span> 
- <span data-ttu-id="2e5c0-3609">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="2e5c0-3610">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="2e5c0-3611">US-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3612">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3612">Format</span></span>

<span data-ttu-id="2e5c0-3613">Abhängig vom Bundesstaat</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3614">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3614">Pattern</span></span>

<span data-ttu-id="2e5c0-3615">Abhängig vom Bundesstaat – am Beispiel für New York:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="2e5c0-3616">Neun Ziffern, die wie DDD DDD DDD formatiert sind, stimmen überein.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="2e5c0-3617">Neun Ziffern wie ddddddddd werden nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3618">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3618">Checksum</span></span>

<span data-ttu-id="2e5c0-3619">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3620">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3620">Definition</span></span>

<span data-ttu-id="2e5c0-3621">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3622">Die Funktion Func_new_york_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3623">Ein Schlüsselwort aus Keyword_[state_name]_drivers_license_name wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="2e5c0-3624">Ein Schlüsselwort aus Keyword_us_drivers_license wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="2e5c0-3625">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3626">Die Funktion Func_new_york_drivers_license_number findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3627">Ein Schlüsselwort aus Keyword_[state_name]_drivers_license_name wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="2e5c0-3628">Ein Schlüsselwort aus Keyword_us_drivers_license_abbreviations wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="2e5c0-3629">Es wurde kein Schlüsselwort aus Keyword_us_drivers_license gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3630">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="2e5c0-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="2e5c0-3632">DL</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3632">DL</span></span> 
- <span data-ttu-id="2e5c0-3633">DLS</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3633">DLS</span></span> 
- <span data-ttu-id="2e5c0-3634">CDL</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3634">CDL</span></span> 
- <span data-ttu-id="2e5c0-3635">CDLS</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3635">CDLS</span></span> 
- <span data-ttu-id="2e5c0-3636">ID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3636">ID</span></span> 
- <span data-ttu-id="2e5c0-3637">IDs</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3637">IDs</span></span> 
- <span data-ttu-id="2e5c0-3638">DL #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3638">DL#</span></span> 
- <span data-ttu-id="2e5c0-3639">DLS #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3639">DLS#</span></span> 
- <span data-ttu-id="2e5c0-3640">CDL #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3640">CDL#</span></span> 
- <span data-ttu-id="2e5c0-3641">CDLS #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3641">CDLS#</span></span> 
- <span data-ttu-id="2e5c0-3642">ID #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3642">ID#</span></span>
- <span data-ttu-id="2e5c0-3643">IDs #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3643">IDs#</span></span> 
- <span data-ttu-id="2e5c0-3644">ID number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3644">ID number</span></span> 
- <span data-ttu-id="2e5c0-3645">ID numbers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3645">ID numbers</span></span> 
- <span data-ttu-id="2e5c0-3646">LIC</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3646">LIC</span></span> 
- <span data-ttu-id="2e5c0-3647">LIC #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="2e5c0-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="2e5c0-3649">DriverLic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3649">DriverLic</span></span> 
- <span data-ttu-id="2e5c0-3650">DriverLics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3650">DriverLics</span></span> 
- <span data-ttu-id="2e5c0-3651">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3651">DriverLicense</span></span> 
- <span data-ttu-id="2e5c0-3652">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3652">DriverLicenses</span></span> 
- <span data-ttu-id="2e5c0-3653">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3653">Driver Lic</span></span> 
- <span data-ttu-id="2e5c0-3654">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3654">Driver Lics</span></span> 
- <span data-ttu-id="2e5c0-3655">Driver License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3655">Driver License</span></span> 
- <span data-ttu-id="2e5c0-3656">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3656">Driver Licenses</span></span> 
- <span data-ttu-id="2e5c0-3657">DriversLic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3657">DriversLic</span></span> 
- <span data-ttu-id="2e5c0-3658">DriversLics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3658">DriversLics</span></span> 
- <span data-ttu-id="2e5c0-3659">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3659">DriversLicense</span></span> 
- <span data-ttu-id="2e5c0-3660">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3660">DriversLicenses</span></span> 
- <span data-ttu-id="2e5c0-3661">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3661">Drivers Lic</span></span> 
- <span data-ttu-id="2e5c0-3662">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3662">Drivers Lics</span></span> 
- <span data-ttu-id="2e5c0-3663">Drivers License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3663">Drivers License</span></span> 
- <span data-ttu-id="2e5c0-3664">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="2e5c0-3665">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3665">Driver'Lic</span></span> 
- <span data-ttu-id="2e5c0-3666">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3666">Driver'Lics</span></span> 
- <span data-ttu-id="2e5c0-3667">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3667">Driver'License</span></span> 
- <span data-ttu-id="2e5c0-3668">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="2e5c0-3669">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3669">Driver' Lic</span></span> 
- <span data-ttu-id="2e5c0-3670">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3670">Driver' Lics</span></span> 
- <span data-ttu-id="2e5c0-3671">Driver' License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3671">Driver' License</span></span> 
- <span data-ttu-id="2e5c0-3672">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3672">Driver' Licenses</span></span>
- <span data-ttu-id="2e5c0-3673">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3673">Driver'sLic</span></span> 
- <span data-ttu-id="2e5c0-3674">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3674">Driver'sLics</span></span> 
- <span data-ttu-id="2e5c0-3675">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="2e5c0-3676">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="2e5c0-3677">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3677">Driver's Lic</span></span> 
- <span data-ttu-id="2e5c0-3678">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3678">Driver's Lics</span></span> 
- <span data-ttu-id="2e5c0-3679">Driver's License</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3679">Driver's License</span></span> 
- <span data-ttu-id="2e5c0-3680">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="2e5c0-3681">identification number</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3681">identification number</span></span> 
- <span data-ttu-id="2e5c0-3682">identification numbers</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3682">identification numbers</span></span> 
- <span data-ttu-id="2e5c0-3683">identification#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3683">identification #</span></span> 
- <span data-ttu-id="2e5c0-3684">id card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3684">id card</span></span> 
- <span data-ttu-id="2e5c0-3685">id cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3685">id cards</span></span> 
- <span data-ttu-id="2e5c0-3686">identification card</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3686">identification card</span></span> 
- <span data-ttu-id="2e5c0-3687">identification cards</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3687">identification cards</span></span> 
- <span data-ttu-id="2e5c0-3688">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3688">DriverLic#</span></span> 
- <span data-ttu-id="2e5c0-3689">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3689">DriverLics#</span></span> 
- <span data-ttu-id="2e5c0-3690">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3690">DriverLicense#</span></span> 
- <span data-ttu-id="2e5c0-3691">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="2e5c0-3692">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3692">Driver Lic#</span></span> 
- <span data-ttu-id="2e5c0-3693">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3693">Driver Lics#</span></span> 
- <span data-ttu-id="2e5c0-3694">Driver License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3694">Driver License#</span></span> 
- <span data-ttu-id="2e5c0-3695">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="2e5c0-3696">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3696">DriversLic#</span></span> 
- <span data-ttu-id="2e5c0-3697">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3697">DriversLics#</span></span> 
- <span data-ttu-id="2e5c0-3698">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3698">DriversLicense#</span></span> 
- <span data-ttu-id="2e5c0-3699">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="2e5c0-3700">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="2e5c0-3701">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="2e5c0-3702">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3702">Drivers License#</span></span> 
- <span data-ttu-id="2e5c0-3703">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="2e5c0-3704">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="2e5c0-3705">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="2e5c0-3706">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3706">Driver'License#</span></span> 
- <span data-ttu-id="2e5c0-3707">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="2e5c0-3708">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="2e5c0-3709">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="2e5c0-3710">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3710">Driver' License#</span></span> 
- <span data-ttu-id="2e5c0-3711">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="2e5c0-3712">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="2e5c0-3713">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="2e5c0-3714">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="2e5c0-3715">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="2e5c0-3716">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="2e5c0-3717">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="2e5c0-3718">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3718">Driver's License#</span></span> 
- <span data-ttu-id="2e5c0-3719">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="2e5c0-3720">id card#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3720">id card#</span></span> 
- <span data-ttu-id="2e5c0-3721">id cards#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3721">id cards#</span></span> 
- <span data-ttu-id="2e5c0-3722">identification card#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3722">identification card#</span></span> 
- <span data-ttu-id="2e5c0-3723">identification cards#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="2e5c0-3724">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="2e5c0-3725">Abkürzung für Bundesstaat (z. B. „NY“)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="2e5c0-3726">Name des Bundesstaats (z. B. „New York“)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="2e5c0-3727">US-Steueridentifikationsnummer (ITIN)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3728">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3728">Format</span></span>

<span data-ttu-id="2e5c0-3729">Neun Ziffern, die mit "9" beginnen und "7" oder "8" als vierte Ziffer enthalten, optional mit Leerzeichen oder Bindestrichen formatiert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3730">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3730">Pattern</span></span>

<span data-ttu-id="2e5c0-3731">Formatiert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3731">Formatted:</span></span>
- <span data-ttu-id="2e5c0-3732">Die Ziffer 9</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3732">The digit "9"</span></span> 
- <span data-ttu-id="2e5c0-3733">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3733">Two digits</span></span> 
- <span data-ttu-id="2e5c0-3734">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3734">A space or dash</span></span> 
- <span data-ttu-id="2e5c0-3735">Eine 7 oder 8</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="2e5c0-3736">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3736">A digit</span></span> 
- <span data-ttu-id="2e5c0-3737">Ein Leerzeichen oder ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3737">A space, or dash</span></span> 
- <span data-ttu-id="2e5c0-3738">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3738">Four digits</span></span>

<span data-ttu-id="2e5c0-3739">Unformatiert</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3739">Unformatted:</span></span>
- <span data-ttu-id="2e5c0-3740">Die Ziffer 9</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3740">The digit "9"</span></span> 
- <span data-ttu-id="2e5c0-3741">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3741">Two digits</span></span> 
- <span data-ttu-id="2e5c0-3742">Eine 7 oder 8</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="2e5c0-3743">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3744">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3744">Checksum</span></span>

<span data-ttu-id="2e5c0-3745">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="2e5c0-3746">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3746">Definition</span></span>

<span data-ttu-id="2e5c0-3747">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3748">Die Funktion Func_formatted_itin findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3749">Mindestens eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="2e5c0-3750">Ein Schlüsselwort aus Keyword_itin wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="2e5c0-3751">Die Funktion Func_us_address findet eine Adresse im richtigen Format.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="2e5c0-3752">Die Funktion Func_us_date findet ein Datum im richtigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="2e5c0-3753">Ein Schlüsselwort aus Keyword_itin_collaborative wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="2e5c0-3754">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3755">Die Funktion Func_unformatted_itin findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3756">Mindestens eine der folgenden Bedingungen trifft zu:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="2e5c0-3757">Ein Schlüsselwort aus Keyword_itin_collaborative wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="2e5c0-3758">Die Funktion Func_us_address findet eine Adresse im richtigen Format.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="2e5c0-3759">Die Funktion Func_us_date findet ein Datum im richtigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3759">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3760">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="2e5c0-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3761">Keyword_itin</span></span>

- <span data-ttu-id="2e5c0-3762">Steuer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3762">taxpayer</span></span> 
- <span data-ttu-id="2e5c0-3763">tax id</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3763">tax id</span></span> 
- <span data-ttu-id="2e5c0-3764">tax identification</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3764">tax identification</span></span> 
- <span data-ttu-id="2e5c0-3765">Itin</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3765">itin</span></span> 
- <span data-ttu-id="2e5c0-3766">SSN</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3766">ssn</span></span> 
- <span data-ttu-id="2e5c0-3767">Zinn</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3767">tin</span></span> 
- <span data-ttu-id="2e5c0-3768">social security</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3768">social security</span></span> 
- <span data-ttu-id="2e5c0-3769">tax payer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3769">tax payer</span></span> 
- <span data-ttu-id="2e5c0-3770">itins</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3770">itins</span></span> 
- <span data-ttu-id="2e5c0-3771">per Taxi</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3771">taxid</span></span> 
- <span data-ttu-id="2e5c0-3772">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="2e5c0-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="2e5c0-3774">Lizenz</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3774">License</span></span> 
- <span data-ttu-id="2e5c0-3775">DL</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3775">DL</span></span> 
- <span data-ttu-id="2e5c0-3776">DOB</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3776">DOB</span></span> 
- <span data-ttu-id="2e5c0-3777">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3777">Birthdate</span></span> 
- <span data-ttu-id="2e5c0-3778">Geburtstag</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3778">Birthday</span></span> 
- <span data-ttu-id="2e5c0-3779">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="2e5c0-3780">US-Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="2e5c0-3781">Format</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3781">Format</span></span>

<span data-ttu-id="2e5c0-3782">9 Ziffern in formatiertem oder unformatiertem Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="2e5c0-3783">Wenn ein SSN vor Mitte 2011 ausgegeben wird, weist es eine starke Formatierung auf, bei der bestimmte Teile der Zahl in bestimmte Bereiche fallen müssen, um gültig zu sein (aber keine Prüfsumme).</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="2e5c0-3784">Muster</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3784">Pattern</span></span>

<span data-ttu-id="2e5c0-3785">Vier Funktionen suchen nach Sozialversicherungsnummern in vier verschiedenen Mustern:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="2e5c0-3786">Func_ssn findet Sozialversicherungsnummern mit starker Formatierung vor 2011, die mit Bindestrichen oder Leerzeichen formatiert sind (DDD-DD-dddd oder DDD DD dddd)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="2e5c0-3787">Func_unformatted_ssn findet Sozialversicherungsnummern mit starker Formatierung vor 2011, die als neun aufeinanderfolgende Ziffern (ddddddddd) unformatiert sind.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="2e5c0-3788">Func_randomized_formatted_ssn findet Post-2011-Sozialversicherungsnummern, die mit Bindestrichen oder Leerzeichen formatiert sind (DDD-DD-dddd oder DDD DD dddd)</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="2e5c0-3789">Func_randomized_unformatted_ssn findet Post-2011 Sozialversicherungsnummern, die als neun aufeinanderfolgende Ziffern (ddddddddd) unformatiert sind.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="2e5c0-3790">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3790">Checksum</span></span>

<span data-ttu-id="2e5c0-3791">Nein</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="2e5c0-3792">Definition</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3792">Definition</span></span>

<span data-ttu-id="2e5c0-3793">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3794">Die Funktion Func_ssn findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3795">Ein Schlüsselwort aus Keyword_ssn wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3795">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="2e5c0-3796">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3797">Die Funktion Func_unformatted_ssn sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3797">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3798">Ein Schlüsselwort aus Keyword_ssn wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3798">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="2e5c0-3799">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3799">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3800">Die Funktion Func_randomized_formatted_ssn findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3800">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3801">Ein Schlüsselwort aus Keyword_ssn wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3801">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="2e5c0-3802">Eine DLP-Richtlinie ist zu 55 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3802">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2e5c0-3803">Die Funktion Func_randomized_unformatted_ssn findet Inhalte, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3803">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2e5c0-3804">Ein Schlüsselwort aus Keyword_ssn wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3804">A keyword from Keyword_ssn is found.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="2e5c0-3805">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3805">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="2e5c0-3806">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3806">Keyword_ssn</span></span>

- <span data-ttu-id="2e5c0-3807">Social Security</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3807">Social Security</span></span> 
- <span data-ttu-id="2e5c0-3808">Social Security#</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3808">Social Security#</span></span> 
- <span data-ttu-id="2e5c0-3809">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3809">Soc Sec</span></span> 
- <span data-ttu-id="2e5c0-3810">SSN</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3810">SSN</span></span> 
- <span data-ttu-id="2e5c0-3811">Sozialversicherungsnummern</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3811">SSNS</span></span> 
- <span data-ttu-id="2e5c0-3812">SSN #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3812">SSN#</span></span> 
- <span data-ttu-id="2e5c0-3813">SS #</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3813">SS#</span></span> 
- <span data-ttu-id="2e5c0-3814">SSID</span><span class="sxs-lookup"><span data-stu-id="2e5c0-3814">SSID</span></span> 
   
